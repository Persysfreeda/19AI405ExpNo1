<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: Persys freeda J </h3>
<h3>Register Number/Staff Id: 212224060185</h3>


<h3>AIM:</h3>
<br>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<br>
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

import random

class MedicinePrescribingAgent:
    def __init__(self):
        self.performance = 0
        self.current_room = None
        self.rooms = {"Room1": None, "Room2": None}

    def take_temperature(self):
        # Randomly generate temperature for each room
        for room in self.rooms:
            self.rooms[room] = round(random.uniform(97.0, 102.0), 1)

    def check_and_treat(self, room):
        temp = self.rooms[room]
        print(f"\nChecking {room}... Temperature: {temp}°F")

        if temp > 98.5:
            print(f"→ {room}: Patient is unhealthy. Prescribing medicine 💊")
            self.performance += 10
        else:
            print(f"→ {room}: Patient is healthy 🙂")

    def move_to_room(self, new_room):
        if self.current_room and self.current_room != new_room:
            print(f"\nMoving from {self.current_room} to {new_room}...")
            self.performance -= 1
        self.current_room = new_room

    def start(self):
        print("🏥 Medicine Prescribing Agent started...\n")
        self.take_temperature()

        for room in self.rooms:
            self.move_to_room(room)
            self.check_and_treat(room)

        print("\n✅ Checking completed!")
        print(f"Final Performance Score: {self.performance}")

# Run the simulation
agent = MedicinePrescribingAgent()
agent.start()

<img width="672" height="511" alt="image" src="https://github.com/user-attachments/assets/2031ebfa-4326-41e2-bbc6-1a9ab65495a2" />

