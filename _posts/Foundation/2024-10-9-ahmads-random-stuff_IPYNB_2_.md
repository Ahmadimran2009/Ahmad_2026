---

---

# 1. Fridge API blog introduction


The Fridge Feature helps users manage ingredients and discover recipes based on what they have on hand. Users can add ingredients (e.g., "tomato, mozzarella, basil") to their virtual fridge, which are stored and linked to their user ID for personalized use. Through various endpoints, users can add ingredients via a POST request, retrieve their stored ingredients with a GET request, or search for recipes that utilize their available items. This functionality simplifies meal planning and reduces waste by making the most of existing ingredients.


# 2. Frontend Features

# Adding your ingredients



```python
const addFridgeBtn = document.getElementById('addFridgeBtn');
const ingredientsInput = document.getElementById('ingredients');
const userIdInput = document.getElementById('user_id');
const fridgeList = document.getElementById('fridgeList');
const API_URL = "http://localhost:8887/fridge";
// Add ingredients to fridge
addFridgeBtn.addEventListener('click', async () => {
    try {
        const response = await fetch(API_URL, {
            method: 'POST', // Specifies a POST request
            headers: {
                'Content-Type': 'application/json', // Sets the content type as JSON
            },
            body: JSON.stringify({
                ingredients: ingredientsInput.value, // Ingredients input by user
                user_id: userIdInput.value,         // User ID input by user
            }),
        });
        if (!response.ok) {
            throw new Error(`HTTP error! Status: ${response.status}`);
        }


        const data = await response.json();
        alert('Ingredients added successfully');
        displayFridgeItems(userIdInput.value); // Refreshes the fridge list for the user
    } catch (error) {
        console.error('Error:', error);
        alert(`An error occurred: ${error.message}`);
    }
});

```

This code enables users to add ingredients and their User ID to a virtual fridge by clicking a button. When the button is clicked, it triggers an event listener that sends a POST request to a backend API. The request includes the ingredients and User ID as JSON data. If the request is successful, it alerts the user and refreshes the displayed list of ingredients for that specific User ID by calling a function to fetch and show the updated fridge contents. If there's an error, it alerts the user and logs the issue for debugging.


# 3. Backend features

# CRUD endpoints



```python
@fridge_api.route('/fridge/add', methods=['POST'])
def add_grocery():
    try:
        # Log the incoming request data and headers
        logger.debug("Request headers: %s", request.headers)
        logger.debug("Request data: %s", request.data)
        # Get the data from the request
        data = request.get_json()
        if not data:
            logger.error("Invalid JSON data")
            return jsonify({'error': 'Invalid JSON data'}), 400


        # Validate the data (ensure grocery and user_id are provided)
        grocery = data.get('grocery')
        user_identifier = 1
        quantity = data.get('quantity')


        if not grocery:
            logger.error("grocery are required")
            return jsonify({'error': 'grocery are required'}), 400


        # Create a new Fridge entry
        new_fridge = Fridge(grocery=grocery, user_id=user_identifier, quantity=data.get('quantity'))
        new_fridge.create()
        return jsonify(new_fridge.read()), 201


    except Exception as e:
        logger.exception("An error occurred while adding grocery")
        return jsonify({'error': str(e)}), 500
  @fridge_api.route('/fridge', methods=['GET'])
def get_fridges():
    try:
        fridges = Fridge.query.all()
        return jsonify([fridge.read() for fridge in fridges])
    except Exception as e:
        logger.exception("An error occurred while fetching fridges")
        return jsonify({'error': str(e)}), 500
    @fridge_api.route('/fridge/delete', methods=['DELETE'])
def delete_fridges():
try:
        data = request.get_json()
        # Find the current post from the database table(s)
        fridge = Fridge.query.get(data['id'])
        if fridge is None:
            return {'message': 'Fridges not found'}, 404
        # Delete the post using the ORM method defined in the model
        fridge.delete()
        # Return response
        return jsonify({"message": "Grocery deleted"})
    except Exception as e:
        logger.exception("An error occurred while fetching fridges")
        return jsonify({'error': str(e)}), 500
@fridge_api.route('/fridge/update', methods=['PUT'])
def update_fridges():
try:
        data = request.get_json()
        # Find the current post from the database table(s)
        fridge = Fridge.query.get(data['id'])
        fridge._quantity = data['quantity']
        if fridge is None:
            return {'message': 'Fridges not found'}, 404
        # Delete the post using the ORM method defined in the model
        fridge.update(data)
        # Return response
        return jsonify({"message": "Grocery update"})
     except Exception as e:
        logger.exception("An error occurred while fetching fridges")
        return jsonify({'error': str(e)}), 500

```

the API follows the CRUD (Create, Read, Update, Delete) pattern using Flask and SQLAlchemy. The POST (/fridge/add) method allows users to add a grocery item by sending JSON data, which is validated and stored in the database. The GET (/fridge) method retrieves all stored groceries and returns them in JSON format. The DELETE (/fridge/delete) method removes a grocery item based on its ID, returning a success or "not found" message. The PUT (/fridge/update) method updates the quantity of an existing grocery item by finding it in the database and modifying its value. Each route includes error handling to log issues and return appropriate status codes.
       


# Database functionality


```python
def initFridge():
    """
    Initialize the Fridge table and add sample data to the table.
    """
    with app.app_context():
        """Create database and tables"""
        db.create_all()
        """Sample data for fridge entries"""
        fridges = [
            Fridge(ingredients='chicken, garlic, lemon', user_id=1, recipes=[]),
            Fridge(ingredients='tomato, mozzarella, basil', user_id=1, recipes=[]),
            Fridge(ingredients='potato, cheese, butter', user_id=2, recipes=[]),
        ]
       
        for fridge in fridges:
            try:
                fridge.create()
                print(f"Record created: {repr(fridge)}")
            except IntegrityError:
                db.session.remove()
                print(f"Record already exists or error: {fridge._ingredients}")
```

This code initializes the Fridge table by first creating all tables with db.create_all() and then adds some sample data entries into the fridge table.


# 4. API communication


```python
const response = await fetch(API_URL, {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
        ingredients: ingredientsInput.value,
        user_id: userIdInput.value,
    }),
});

```

This code implements a user interface for managing ingredients in a virtual fridge, with API communication to handle data storage and retrieval. When users input their ingredients and user ID, they can click a button that triggers a POST request to an API endpoint (http://localhost:8887/fridge), sending the data as JSON. If successful, it confirms the addition and fetches the updated fridge contents via a GET request to the same API with the user's ID as a query parameter. The response, containing the user's stored ingredients, is dynamically displayed on the page. This functionality ensures seamless interaction between the frontend and backend, enabling users to manage their fridge items easily.


# 5. challenges and improvement


Challenges


    -Enabling automatic updates for the fridge.
    -Managing errors when the API behaves unexpectedly.
    -Troubleshooting API responses to identify issues.


Improvements


    -Better error messages: Make error messages clearer when data is missing or incorrect.
    -Faster database queries: Speed up database queries for better performance.
    -Validate inputs: Check the data more carefully (e.g., correct format for ingredients).
    -Prevent overload: Add rate limiting to avoid too many requests at once.


# 6. Addressing learning requirements


Discuss the return/response from the method with Algorithm (fetch) and how you handle data.


The API endpoints return JSON responses based on the request type:
POST (/fridge/add): Returns 201 and the created grocery data if successful. If JSON is invalid or required fields are missing, it returns 400. On server errors, it returns 500.
GET (/fridge): Returns 200 with a list of groceries or 500 if an error occurs.
DELETE (/fridge/delete): If the grocery exists, it returns 200 with a success message. If not, it returns 404. Server errors return 500.
PUT (/fridge/update): Updates a grocery item’s quantity, returning 200 on success or 404 if the item doesn’t exist. Server errors return 500.


Show how changing data or method triggers a different response, specifically normal conditions and error conditions.

Normal Conditions:
Sending correct JSON to POST adds a grocery and returns 201.
Fetching with GET returns a 200 status and all stored groceries.
DELETE with a valid ID removes the item and returns 200.
PUT with a valid ID updates the quantity and returns 200.
Error Conditions:
POST with missing or invalid data returns 400.
DELETE or PUT with a non-existent ID returns 404.
Database or unexpected server issues return 500.




# This blog covers the key learning objectives by showcasing the following:


-Collaborative and creative programming: The project brings together both frontend and backend elements, requiring teamwork and creative problem-solving.


-Group and individual efforts: The blog outlines the team's goal (creating a platform for free-response questions) and my personal contributions (frontend development, API integration, and CRUD operations).


-Input/Output examples: It includes user input examples (e.g., topic selection, form submissions) and the corresponding outputs (API responses, DOM updates).


-API request handling: Postman examples and frontend fetch requests demonstrate how data is sent and processed through RESTful APIs.


-Database management: It shows how to initialize, query, and restore test data using SQLAlchemy.


-Algorithmic logic: CRUD operations and frontend communication display the use of sequencing, selection, and iteration.


-Error handling: The blog also highlights how the backend handles invalid inputs and provides appropriate responses.


By covering these areas, the blog presents a thorough view of the project's technical implementation and the associated learning outcomes.


# Third party libraries


    -SQLAlchemy: Makes working with databases easier.
    -Google generative AI: AI chatbox


# Conclusion


In conclusion, Sprint 4 was a productive phase where I improved both the frontend and backend components. I learned to manage and interact with databases, handle errors, and optimize API performance. The updates made, such as clearer error messages and faster database queries, enhanced the user experience. This sprint deepened my understanding of technical development and teamwork, setting the foundation for future improvements.


# more

Sequencing Order: data is first received from a HTTP url request, then validated, processed, and stored or fetched from the database.
Selection: The program checks for specific conditions before proceeding, e.g., whether a grocery exists before attempting to update or delete it.
Iteration: The program can iterate over multiple recipes when fetching a list of them from the database.
