<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: KANISH TR  </h3>
<h3>Register Number: 212224060116</h3>


<h3>AIM:</h3>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<h3>Theory</h3>
<h3>Medicine prescribing agent:</h3>
<p>Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.</p>
<hr>
<h3>PEAS DESCRIPTION:</h3>
<table>
  <tr>
    <td><strong>Agent Type</strong></td>
    <td><strong>Performance</strong></td>
     <td><strong>Environment</strong></td>
    <td><strong>Actuators</strong></td>
    <td><strong>Sensors</strong></td>
  </tr>
    <tr>
    <td><strong>Medicine prescribing agent</strong></td>
    <td><strong>Treating unhealthy, agent movement</strong></td>
     <td><strong>Rooms, Patient</strong></td>
    <td><strong>Medicine, Treatment</strong></td>
    <td><strong>Location, Temperature of patient</strong></td>
  </tr>
</table>
<hr>
<H3>DESIGN STEPS</H3>
<h3>STEP 1:Identifying the input:</h3>
<p>Temperature from patients, Location.</p>
<h3>STEP 2:Identifying the output:</h3>
<p>Prescribe medicine if the patient in a random has a fever.</p>
<h3>STEP 3:Developing the PEAS description:</h3>
<p>PEAS description is developed by the performance, environment, actuators, and sensors in an agent.</p>
<h3>STEP 4:Implementing the AI agent:</h3>
<p>Treat unhealthy patients in each room. And check for the unhealthy patients in random room</p>
<h3>STEP 5:</h3>
<p>Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented</p>
<H3>PROGRAM:</H3>

```
import random
ROOMS = ["Room 1", "Room 2"]
FEVER_THRESHOLD = 98.5
environment = {
    "Room 1": round(random.uniform(97.0, 101.0), 1),
    "Room 2": round(random.uniform(97.0, 101.0), 1)
}
agent_location = "Room 1"
performance_score = 0

def check_temperature(room):
    temp = environment[room]
    print(f"Checking {room}... Patient temperature: {temp}°F")
    return temp

def treat_patient(room):
    global performance_score
    print(f"Treating patient in {room}... ")
    performance_score += 1 

def move_to(room):
    global agent_location, performance_score
    if agent_location != room:
        print(f"Moving from {agent_location} to {room}... ")
        agent_location = room
        performance_score -= 1  
print("Medicine Prescribing Agent Simulation Started \n")

for room in ROOMS:
    move_to(room)
    temp = check_temperature(room)
    if temp > FEVER_THRESHOLD:
        treat_patient(room)
    else:
        print(f"No treatment needed in {room}.\n")
print("\nSimulation Complete!")
print(f"Final Performance Score: {performance_score}")
print("Environment State:", environment)
```

OUTPUT:

<img width="1060" height="511" alt="image" src="https://github.com/user-attachments/assets/421c4595-9890-403d-92f3-185ff8b4805e" />

RESULT:

Thus the AI agent is developed successfully
