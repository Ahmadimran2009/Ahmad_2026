---

---

# PPR blog

Personalized Project Reference (PPR)

# Parts of PPR, Component C of CPT:

## 4 Code segments to be submitted
- List creation
- List processing
- Function (with parameters that goes through the list and has an if else statement, sequencing, selection, iteration)
- Call to function

# List Creation


```python
def get(self):            
    items = FridgeItem.query.all()
    
    if not items:
        return jsonify({"message": "No items found in the fridge."}), 404
    
    return jsonify([item.read() for item in items]), 200

```

Explanation: This Python function retrieves all fridge items from the FridgeItem database table using query.all(). If no items are found, it returns a 404 response with a message. Otherwise, it processes each item by calling its .read() method, converting the database objects into dictionaries. The function then returns the full list of fridge items as a JSON response with a 200 status.

# List Process


```python
json_ready = [item.read() for item in items]
```

Explanation: This line creates a new list called json_ready by iterating over each item in the items list. It uses list comprehension ([] with a loop inside) to efficiently process each fridge item. The .read() method converts each database object into a dictionary, making the data JSON serializable and ready for response.

# Function (with parameters, and if-else statement)


```python
@token_required()
def post(self):
    current_user = g.current_user  # Get the authenticated user
    data = request.get_json()  # Parse JSON request data

    # Validate required field
    if not data or not data.get('name'):
        return jsonify({'message': 'Grocery item must have a name'}), 400  

    # Create a new grocery item
    grocery_item = GroceryItem(
        name=data['name'],
        quantity=data.get('quantity', 1),  # Default quantity is 1
        category=data.get('category', 'Uncategorized'),  # Default category
        expiration_date=data.get('expiration_date'),
        user_id=current_user.id  # Associate item with the user
    )

    grocery_item.create()  # Save to database
    return jsonify({'message': 'Grocery item added successfully', 'item': grocery_item.read()}), 201
```

Explanation: This function adds a new grocery item for the current user. It accepts JSON input, extracts necessary fields, and associates the item with the logged-in user. The function includes validation using g.current_user, ensuring that only authenticated users can add groceries. If no name is provided, it returns an error. Successfully added items are saved to the database and returned as a JSON response.

# call to Function


```python
async function addGroceryItem(name, quantity, category, expirationDate) {
  const groceryData = {
    name,
    quantity: quantity || 1, // Default to 1 if not provided
    category: category || "Uncategorized", // Default category
    expiration_date: expirationDate,
  };

  try {
    const response = await fetch(`${pythonURI}/api/groceries`, {
      ...fetchOptions,
      method: 'POST',
      body: JSON.stringify(groceryData),
    });

    if (!response.ok) {
      throw new Error(`Failed to add grocery: ${response.statusText}`);
    }

    const result = await response.json();
    console.log('Grocery item added successfully:', result);

  } catch (error) {
    console.error('Error adding grocery item:', error);
    alert('Error adding grocery item: ' + error.message);
  }
}
```

Explanation: This line calls the database to retrieve all grocery items. It fetches every record in the GroceryItem table and returns them as a list of model instances, representing all groceries stored in the fridge.

# Summary

Data Compilation: Collects all grocery items into a structured list for easy access and display.

Functionality: Handles adding new grocery items, linking them to specific users, and ensuring proper validation to prevent errors.

API Interaction: Facilitates retrieving and displaying stored groceries through GET requests, allowing users to manage their fridge inventory effortlessly.

This API streamlines grocery management by enabling secure, efficient, and organized handling of food items, ensuring a seamless user experience

<script src="https://utteranc.es/client.js"
        repo="Ahmadimran2009/Ahmad_2025"
        issue-term="title"
        label="blogpost-comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>

<script src="https://utteranc.es/client.js"
        repo="Ahmadimran2009/Ahmad_2025"
        issue-term="title"
        label="blogpost-comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>
