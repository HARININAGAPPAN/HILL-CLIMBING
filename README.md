<h1>ExpNo 5 : Implement Simple Hill Climbing Algorithm</h1> 
<h3>Name:  Harini N         </h3>
<h3>Register Number: 212223040057             </h3>
<H3>Aim:</H3>
<p>Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration </p>
<h2> Theory: </h2>
<p>Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space.
Feedback is provided in terms of heuristic function
</p>


<h2>Algorithm:</h2>
<p>
<ol>
 <li> Evaluate the initial state.If it is a goal state then return it and quit. Otherwise, continue with initial state as current state.</li> 
<li>Loop until a solution is found or there are no new operators left to be applied in current state:
<ul><li>Select an operator that has not yet been applied to the current state and apply it to produce a new state</li>
<li>Evaluate the new state:
  <ul>
<li>if it is a goal state, then return it and quit</li>
<li>if it is not a goal state but better than current state then make new state as current state</li>
<li>if it is not better than current state then continue in the loop</li>
    </ul>
</li>
</ul>
</li>
</ol>

</p>
<hr>
<h3> Steps Applied:</h3>
<h3>Step-1</h3>
<p> Generate Random String of the length equal to the given String</p>
<h3>Step-2</h3>
<p>Mutate the randomized string each character at a time</p>
<h3>Step-3</h3>
<p> Evaluate the fitness function or Heuristic Function</p>
<h3>Step-4:</h3>
<p> Lopp Step -2 and Step-3  until we achieve the score to be Zero to achieve Global Minima.</p>

<hr>
## code:

```
import random
import string

def generate_random_solution(answer):
    l = len(answer)                                                                # Find the length of the answer
    return [random.choice(string.printable) for _ in range(l)]

def evaluate(solution, answer):
    print(solution)
    target = list(answer)
    diff = 0

    for i in range(len(target)):
        s = solution[i]
        t = target[i]

        diff += abs(ord(s) - ord(t))

    return diff

def mutate_solution(solution):
    ind = random.randint(0, len(solution) - 1)
    solution[ind] = random.choice(string.printable)
    return solution



def SimpleHillClimbing():
    answer = input("Enter the String:")

    best = generate_random_solution(answer)
    best_score = evaluate(best, answer)

    while True:
        print("Score:", best_score, " Solution:", "".join(best))

        if best_score == 0:
            print("\nTarget String Found!")
            break

        new_solution = mutate_solution(list(best))
        score = evaluate(new_solution, answer)

        if score < best_score:
            best = new_solution
            best_score = score

SimpleHillClimbing()

```


<h2>String:</h2> ab
<h2>Output:</h2>
Enter the String:ab


<img width="1042" height="685" alt="image" src="https://github.com/user-attachments/assets/b8d1398f-9538-485e-8650-0795eda28bf6" />

<img width="1087" height="631" alt="image" src="https://github.com/user-attachments/assets/f2f414a8-b5ee-4240-86b7-0a9e03e73a8f" />

## Result:

Thus, the Simple Hill Climbing algorithm was implemented successfully in Python. The program generates a random string, evaluates its difference from the target string, and improves the solution through random mutations until the target string is found.

