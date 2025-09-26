
### AIM:
To design and implement a Python function for calculating the volume of a cone , integrate it with a chat completion system utilizing the function-calling feature of a large language model (LLM).

### PROBLEM STATEMENT:
Design and implement a system where a user can input dimensions of a cone (radius and height), 
And the system calculates its volume by invoking a Python function using the function-calling capabilities of an LLM.

### DESIGN STEPS:

#### STEP 1:
Import the necessary libraries, including:
math for mathematical operations.
json for handling arguments in structured form.
(Optional) openai for actual LLM integration.
#### STEP 2:
Define a Python function calculate_cone_volume(radius, height) that computes the volume of a cone using the formula:
          <img width="482" height="111" alt="image" src="https://github.com/user-attachments/assets/78386eef-5498-4a4f-8d1a-7f5bbf9cf63a" />

#### STEP 3:
Integrate the function into an LLM-based function-calling system by:

  Taking the user query.
  Simulating the LLM deciding to call the function.
  Passing arguments in JSON format.
  Extracting arguments and invoking the Python function.
  Displaying the result in a natural language response.
### PROGRAM:
~~~
import json
import math

# Function to calculate cone volume
def calculate_cone_volume(radius: float, height: float) -> dict:
    """
    Volume of a cone = (1/3) * π * r² * h
    """
    volume = (1/3) * math.pi * (radius ** 2) * height
    return {"radius": radius, "height": height, "volume": volume}

# Simulated "LLM function call" response
user_message = "What is the volume of a cone with radius 20 cm and height 40 cm?"

# Pretend the LLM decided to call our function
function_call = {
    "name": "calculate_cone_volume",
    "arguments": json.dumps({"radius": 20, "height": 40})
}

# Extract arguments and call Python function
arguments = json.loads(function_call["arguments"])
result = calculate_cone_volume(**arguments)

# Simulated AI natural language reply
print("AI Response: The volume of the cone is approximately {:.2f} cubic units.".format(result["volume"]))


~~~
### OUTPUT:
<img width="1235" height="602" alt="image" src="https://github.com/user-attachments/assets/cbc3c57e-c87d-4b51-8a86-81e652ab8917" />



### RESULT:
Thus, The Python program successfully calculates the volume of a cone for the given radius and height.
