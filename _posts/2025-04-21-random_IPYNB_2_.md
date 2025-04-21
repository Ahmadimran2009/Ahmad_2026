---

---

# Popcorn hack 1

A random algorithm uses chance to make decisions, so it can produce different results each time. It’s useful in coding for things like games (shuffling cards), security (adding unpredictability), and simulations (mimicking real-life randomness). Randomness can also speed up some algorithms or help when exact solutions are hard to find. The College Board may ask about how random algorithms produce different outcomes and why they’re useful, like in games or simulations. Questions focus on understanding unpredictability, fairness, and the role of randomness in solving real-world problems.

# Popcorn hack 2




```python
import random

# Updated list of activities
activities = [
    'Lift weights at the gym',
    'Work on coding project',
    'Practice soccer skills',
    'Meal prep a healthy lunch',
    'Study AP Biology flashcards',
    'Take a 20-minute power nap',
    'Go for a walk while listening to a podcast',
    'Stretch and do mobility exercises',
    'Watch a documentary',
    'Do a quick home workout',
    'Clean your room and organize your desk'
]

# Randomly choose an activity
random_activity = random.choice(activities)

# Display the chosen activity
random_activity

```




    'Go for a walk while listening to a podcast'



This code gives a random outcome out of the activities listed, this time I got 'Go for a walk while listening to a podcast'

# Popcorn hack 3



```python
import random

# Updated names and party activities
hosts = ['Ahmad', 'Arhaan', 'Manas', 'Kree', 'Vasanth']
activities = ['music station', 'snack table', 'photo booth', 'game zone', 'welcome desk']

# Shuffle the activities to randomly assign them
random.shuffle(activities)

# Assign each host to a randomly shuffled activity
assignments = [f"{hosts[i]} will be monitoring the {activities[i]}!" for i in range(len(hosts))]
assignments

```




    ['Ahmad will be monitoring the photo booth!',
     'Arhaan will be monitoring the music station!',
     'Manas will be monitoring the snack table!',
     'Kree will be monitoring the welcome desk!',
     'Vasanth will be monitoring the game zone!']



# Results

'Ahmad will be monitoring the photo booth!',
'Arhaan will be monitoring the music station!',
'Manas will be monitoring the snack table!',
'Kree will be monitoring the welcome desk!',
'Vasanth will be monitoring the game zone!'

# Popcorn hack 1



```python
import random

# Simulating a number spinner with a custom range (e.g., 1 to 20)
spinner_range = list(range(1, 21))  # Spinner with numbers from 1 to 20

# Randomly select a number from the spinner
spinner_result = random.choice(spinner_range)

spinner_result
```




    4



# Result
4

# Popcorn hack 2


```python
import random

def play_rock_paper_scissors():
    choices = ['rock', 'paper', 'scissors']
    computer_choice = random.choice(choices)
    user_choice = input("Enter your choice (rock, paper, or scissors): ")

    if user_choice not in choices:
        print("Invalid choice. Please try again.")
        return

    print("Computer chose:", computer_choice)
    print("You chose:", user_choice)

    if user_choice == computer_choice:
        print("It's a tie!")
    elif (user_choice == 'rock' and computer_choice == 'scissors') or (user_choice == 'paper' and computer_choice == 'rock') or (user_choice == 'scissors' and computer_choice == 'paper'):
        print("You win!")
    else:
        print("You lose!")

play_rock_paper_scissors()
```

    Computer chose: scissors
    You chose: paper
    You lose!


# Results

Rock is a win
scissors is a loss
paper is a loss

# Homework Hacks




```python
import random

# List of 15 students
students = [
    'Ahmad', 'Zara', 'Leo', 'Maya', 'Jaden',
    'Sofia', 'Noah', 'Olivia', 'Ethan', 'Ava',
    'Liam', 'Emma', 'Jackson', 'Aria', 'Lucas'
]

# Creative team names
teams = ['Team Thunder', 'Team Phoenix', 'Team Eclipse']

# Dictionary to hold team assignments
team_assignments = {team: [] for team in teams}

# Randomly assign each student to a team
for student in students:
    team = random.choice(teams)
    team_assignments[team].append(student)

# Print the assignments
for team, members in team_assignments.items():
    print(f"{team}: {', '.join(members)}")

```

    Team Thunder: Ahmad, Leo, Maya, Sofia, Noah, Liam, Emma, Aria
    Team Phoenix: Ethan, Ava, Jackson
    Team Eclipse: Zara, Jaden, Olivia, Lucas



```python
import random

# List of possible weather types
weather_types = ['Sunny', 'Cloudy', 'Rainy']

# Simulate the weather for 7 days
forecast = {f"Day {i+1}": random.choice(weather_types) for i in range(7)}

forecast

```




    {'Day 1': 'Sunny',
     'Day 2': 'Sunny',
     'Day 3': 'Sunny',
     'Day 4': 'Rainy',
     'Day 5': 'Cloudy',
     'Day 6': 'Cloudy',
     'Day 7': 'Cloudy'}




```python
import random

# Simulate a coffee shop with 5 customers, each with a random service time between 1 and 5 minutes
customer_count = 5
service_times = [random.randint(1, 5) for _ in range(customer_count)]

# Calculate the total time to serve all customers
total_service_time = sum(service_times)

# Simulate the queue and print each customer's service time
queue_details = {f"Customer {i+1}": service_times[i] for i in range(customer_count)}

queue_details, total_service_time

```




    ({'Customer 1': 1,
      'Customer 2': 3,
      'Customer 3': 3,
      'Customer 4': 2,
      'Customer 5': 2},
     11)


