# Nested List Comprehensions

## Simple comprehension

```python
matrix = [] 
  
for i in range(5): 
      
    # Append an empty sublist inside the list 
    matrix.append([]) 
      
    for j in range(5): 
        matrix[i].append(j) 
```
```python
matrix = [[j for j in range(5)] for i in range(5)] 
```

## Nested comprehension

```python
matrix = [[1, 2, 3], [4, 5], [6, 7, 8, 9]] 
  
flatten_matrix = [] 
  
for sublist in matrix: 
    for val in sublist: 
        flatten_matrix.append(val) 
```
```python
flatten_matrix = [val
                  for sublist in matrix
                  for val in sublist]
```

## Nested comprehension with condition

```python
planets = [['Mercury', 'Venus', 'Earth'], ['Mars', 'Jupiter', 'Saturn'], ['Uranus', 'Neptune', 'Pluto']] 
  
flatten_planets = [] 
  
for sublist in planets: 
    for planet in sublist: 
          
        if len(planet) < 6: 
            flatten_planets.append(planet) 
```
```python
flatten_planets = [planet 
                   for sublist in planets 
                   for planet in sublist 
                   if len(planet) < 6] 
```


Source: https://www.geeksforgeeks.org/nested-list-comprehensions-in-python/
