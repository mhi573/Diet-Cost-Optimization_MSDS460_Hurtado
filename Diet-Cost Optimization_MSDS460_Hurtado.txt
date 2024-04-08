# -*- coding: utf-8 -*-

import numpy as np

from pulp import LpVariable, LpProblem, LpMaximize, LpStatus, value, LpMinimize

#Analysis 1
# Define the variables
Potatoes = LpVariable("Potatoes", 0, None)
Yogurt = LpVariable("Greek Yogurt", 0, None)
Chicken = LpVariable("Chicken Thigh", 0, None)
Sausage = LpVariable("Polish Sausage", 0, None)
Egg = LpVariable("Egg", 0, None)

# Define the problem
prob = LpProblem("problem", LpMinimize)

# Define constraints
prob += 100*Yogurt + 80*Chicken + 400*Sausage + 70*Egg <= 35000
prob += 0.07*Potatoes + 0.13*Yogurt + 0.25*Chicken + 0.17*Sausage + 0.07*Egg >= 14
prob += 2*Potatoes + 14*Yogurt + 17*Chicken + 6*Sausage + 6*Egg >= 350
prob += 1*Egg >= 140
prob += 170*Yogurt + 30*Egg >= 9100
prob += 0.90*Potatoes + 0.40*Chicken + 0.90*Egg >= 126
prob += 440*Potatoes + 220*Yogurt + 250*Chicken + 376*Sausage + 70*Egg >= 32900

# Define the objective function
prob += 0.55*Potatoes + 0.70*Yogurt + 0.84*Chicken + 0.41*Sausage + 0.40*Egg

# Solve the problem
status = prob.solve()
print(f"{prob}")
print(f"status={LpStatus[status]}")

# Print the results
for variable in prob.variables():
    print(f"{variable.name} = {variable.varValue}")
    
print(f"Objective = {value(prob.objective)}")  

#Analysis 2
# Define the variables
Potatoes = LpVariable("Potatoes", 0, None)
Yogurt = LpVariable("Greek Yogurt", 0, None)
Chicken = LpVariable("Chicken Thigh", 0, None)
Sausage = LpVariable("Polish Sausage", 0, None)
Egg = LpVariable("Egg", 0, None)

# Define the problem
prob = LpProblem("problem", LpMinimize)

# Define constraints
prob += 100*Yogurt + 80*Chicken + 400*Sausage + 70*Egg <= 35000
prob += 0.07*Potatoes + 0.13*Yogurt + 0.25*Chicken + 0.17*Sausage + 0.07*Egg >= 14
prob += 2*Potatoes + 14*Yogurt + 17*Chicken + 6*Sausage + 6*Egg >= 350
prob += 1*Egg >= 140
prob += 170*Yogurt + 30*Egg >= 9100
prob += 0.90*Potatoes + 0.40*Chicken + 0.90*Egg >= 126
prob += 440*Potatoes + 220*Yogurt + 250*Chicken + 376*Sausage + 70*Egg >= 32900

# Add constraints 
prob += Potatoes >= 1
prob += Yogurt >= 1
prob += Chicken >= 1
prob += Sausage >= 1
prob += Egg >= 1

# Define the objective function
prob += 0.55*Potatoes + 0.70*Yogurt + 0.84*Chicken + 0.41*Sausage + 0.40*Egg

# Solve the problem
status = prob.solve()
print(f"{prob}")
print(f"status={LpStatus[status]}")

# Print the results
for variable in prob.variables():
    print(f"{variable.name} = {variable.varValue}")
    
print(f"Objective = {value(prob.objective)}")  

#Analysis 3
# Define the variables
Potatoes = LpVariable("Potatoes", 0, None)
Yogurt = LpVariable("Greek Yogurt", 0, None)
Chicken = LpVariable("Chicken Thigh", 0, None)
Sausage = LpVariable("Polish Sausage", 0, None)
Egg = LpVariable("Egg", 0, None)

# Define the problem
prob = LpProblem("problem", LpMinimize)

# Define constraints
prob += 100*Yogurt + 80*Chicken + 400*Sausage + 70*Egg <= 35000
prob += 0.07*Potatoes + 0.13*Yogurt + 0.25*Chicken + 0.17*Sausage + 0.07*Egg >= 14
prob += 2*Potatoes + 14*Yogurt + 17*Chicken + 6*Sausage + 6*Egg >= 350
prob += 170*Yogurt + 30*Egg >= 9100
prob += 0.90*Potatoes + 0.40*Chicken + 0.90*Egg >= 126
prob += 440*Potatoes + 220*Yogurt + 250*Chicken + 376*Sausage + 70*Egg >= 32900

# Add constraints 
prob += Potatoes >= 1
prob += Yogurt >= 1
prob += Chicken >= 1
prob += Sausage >= 1
prob += Egg >= 1

# Define the objective function
prob += 0.55*Potatoes + 0.70*Yogurt + 0.84*Chicken + 0.41*Sausage + 0.40*Egg

# Solve the problem
status = prob.solve()
print(f"{prob}")
print(f"status={LpStatus[status]}")

# Print the results
for variable in prob.variables():
    print(f"{variable.name} = {variable.varValue}")
    
print(f"Objective = {value(prob.objective)}")  


