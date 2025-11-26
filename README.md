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
