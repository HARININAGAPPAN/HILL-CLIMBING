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
['*', '`']
Score: 57  Solution: *`
['*', '>']
Score: 57  Solution: *`
['z', '`']
Score: 27  Solution: z`
['.', '`']
Score: 27  Solution: z`
['z', 'R']
Score: 27  Solution: z`
['k', '`']
Score: 12  Solution: k`
['k', '9']
Score: 12  Solution: k`
['k', '"']
Score: 12  Solution: k`
['k', 'b']
Score: 10  Solution: kb
['k', '/']
Score: 10  Solution: kb
['k', 'n']
Score: 10  Solution: kb
['k', '\t']
Score: 10  Solution: kb
['k', 'E']
Score: 10  Solution: kb
['k', '[']
Score: 10  Solution: kb
['<', 'b']
Score: 10  Solution: kb
['k', ')']
Score: 10  Solution: kb
['K', 'b']
Score: 10  Solution: kb
['k', '"']
Score: 10  Solution: kb
[';', 'b']
Score: 10  Solution: kb
['k', 'e']
Score: 10  Solution: kb
['k', 'f']
Score: 10  Solution: kb
['+', 'b']
Score: 10  Solution: kb
['k', 'F']
Score: 10  Solution: kb
['k', 'n']
Score: 10  Solution: kb
['B', 'b']
Score: 10  Solution: kb
['k', 'l']
Score: 10  Solution: kb
['k', 'c']
Score: 10  Solution: kb
['s', 'b']
Score: 10  Solution: kb
['X', 'b']
Score: 9  Solution: Xb
['X', 'a']
Score: 9  Solution: Xb
['X', 'y']
Score: 9  Solution: Xb
['X', '"']
Score: 9  Solution: Xb
['S', 'b']
Score: 9  Solution: Xb
['X', '$']
Score: 9  Solution: Xb
['n', 'b']
Score: 9  Solution: Xb
['X', '^']
Score: 9  Solution: Xb
['c', 'b']
Score: 2  Solution: cb
['c', '=']
Score: 2  Solution: cb
['c', '&']
Score: 2  Solution: cb
['b', 'b']
Score: 1  Solution: bb
['%', 'b']
Score: 1  Solution: bb
[',', 'b']
Score: 1  Solution: bb
[' ', 'b']
Score: 1  Solution: bb
['-', 'b']
Score: 1  Solution: bb
['i', 'b']
Score: 1  Solution: bb
['b', '=']
Score: 1  Solution: bb
['b', 'F']
Score: 1  Solution: bb
['^', 'b']
Score: 1  Solution: bb
['b', 'U']
Score: 1  Solution: bb
['b', 'D']
Score: 1  Solution: bb
['N', 'b']
Score: 1  Solution: bb
['H', 'b']
Score: 1  Solution: bb
['b', 'j']
Score: 1  Solution: bb
['b', 'k']
Score: 1  Solution: bb
['q', 'b']
Score: 1  Solution: bb
['?', 'b']
Score: 1  Solution: bb
['h', 'b']
Score: 1  Solution: bb
['b', '/']
Score: 1  Solution: bb
['b', '_']
Score: 1  Solution: bb
['b', '&']
Score: 1  Solution: bb
['\n', 'b']
Score: 1  Solution: bb
['B', 'b']
Score: 1  Solution: bb
['b', 'a']
Score: 1  Solution: bb
['1', 'b']
Score: 1  Solution: bb
['2', 'b']
Score: 1  Solution: bb
['b', ':']
Score: 1  Solution: bb
['b', ';']
Score: 1  Solution: bb
['b', '3']
Score: 1  Solution: bb
['b', '<']
Score: 1  Solution: bb
['b', '~']
Score: 1  Solution: bb
[',', 'b']
Score: 1  Solution: bb
['x', 'b']
Score: 1  Solution: bb
['b', 'M']
Score: 1  Solution: bb
['b', 'Y']
Score: 1  Solution: bb
[';', 'b']
Score: 1  Solution: bb
['A', 'b']
Score: 1  Solution: bb
['b', "'"]
Score: 1  Solution: bb
['b', '~']
Score: 1  Solution: bb
['l', 'b']
Score: 1  Solution: bb
['b', '@']
Score: 1  Solution: bb
['b', '&']
Score: 1  Solution: bb
['|', 'b']
Score: 1  Solution: bb
['b', '/']
Score: 1  Solution: bb
['T', 'b']
Score: 1  Solution: bb
['q', 'b']
Score: 1  Solution: bb
['T', 'b']
Score: 1  Solution: bb
['b', '~']
Score: 1  Solution: bb
['k', 'b']
Score: 1  Solution: bb
['E', 'b']
Score: 1  Solution: bb
['\x0b', 'b']
Score: 1  Solution: bb
['b', '\x0b']
Score: 1  Solution: bb
['O', 'b']
Score: 1  Solution: bb
['b', 'W']
Score: 1  Solution: bb
['b', '$']
Score: 1  Solution: bb
['b', '\\']
Score: 1  Solution: bb
['\x0b', 'b']
Score: 1  Solution: bb
['\x0b', 'b']
Score: 1  Solution: bb
['b', 'D']
Score: 1  Solution: bb
['b', 'q']
Score: 1  Solution: bb
['b', '(']
Score: 1  Solution: bb
['S', 'b']
Score: 1  Solution: bb
["'", 'b']
Score: 1  Solution: bb
['>', 'b']
Score: 1  Solution: bb
['b', '8']
Score: 1  Solution: bb
['b', '=']
Score: 1  Solution: bb
['h', 'b']
Score: 1  Solution: bb
['b', '?']
Score: 1  Solution: bb
['c', 'b']
Score: 1  Solution: bb
['b', '~']
Score: 1  Solution: bb
['b', 'a']
Score: 1  Solution: bb
['(', 'b']
Score: 1  Solution: bb
['b', 'n']
Score: 1  Solution: bb
['[', 'b']
Score: 1  Solution: bb
['b', '\x0b']
Score: 1  Solution: bb
['c', 'b']
Score: 1  Solution: bb
['b', 'T']
Score: 1  Solution: bb
['b', '5']
Score: 1  Solution: bb
['m', 'b']
Score: 1  Solution: bb
['b', '0']
Score: 1  Solution: bb
[';', 'b']
Score: 1  Solution: bb
['H', 'b']
Score: 1  Solution: bb
['b', ']']
Score: 1  Solution: bb
['m', 'b']
Score: 1  Solution: bb
['b', 'b']
Score: 1  Solution: bb
['o', 'b']
Score: 1  Solution: bb
['b', '6']
Score: 1  Solution: bb
['U', 'b']
Score: 1  Solution: bb
['R', 'b']
Score: 1  Solution: bb
['4', 'b']
Score: 1  Solution: bb
['b', '@']
Score: 1  Solution: bb
['b', 'r']
Score: 1  Solution: bb
['b', '\t']
Score: 1  Solution: bb
['b', 'U']
Score: 1  Solution: bb
['b', '\r']
Score: 1  Solution: bb
['W', 'b']
Score: 1  Solution: bb
['M', 'b']
Score: 1  Solution: bb
['b', 'S']
Score: 1  Solution: bb
['b', 'p']
Score: 1  Solution: bb
['b', '>']
Score: 1  Solution: bb
['b', 'z']
Score: 1  Solution: bb
['=', 'b']
Score: 1  Solution: bb
['K', 'b']
Score: 1  Solution: bb
['b', '/']
Score: 1  Solution: bb
['b', '\x0c']
Score: 1  Solution: bb
['b', 'b']
Score: 1  Solution: bb
['b', '9']
Score: 1  Solution: bb
['S', 'b']
Score: 1  Solution: bb
['b', '$']
Score: 1  Solution: bb
['b', '<']
Score: 1  Solution: bb
['b', 'j']
Score: 1  Solution: bb
['b', 'A']
Score: 1  Solution: bb
['b', 'l']
Score: 1  Solution: bb
['b', 'w']
Score: 1  Solution: bb
['@', 'b']
Score: 1  Solution: bb
['_', 'b']
Score: 1  Solution: bb
['w', 'b']
Score: 1  Solution: bb
['0', 'b']
Score: 1  Solution: bb
['b', '+']
Score: 1  Solution: bb
['v', 'b']
Score: 1  Solution: bb
['b', '\n']
Score: 1  Solution: bb
['R', 'b']
Score: 1  Solution: bb
['b', '[']
Score: 1  Solution: bb
['G', 'b']
Score: 1  Solution: bb
['b', '<']
Score: 1  Solution: bb
['p', 'b']
Score: 1  Solution: bb
['b', 'R']
Score: 1  Solution: bb
['b', 'm']
Score: 1  Solution: bb
['h', 'b']
Score: 1  Solution: bb
['+', 'b']
Score: 1  Solution: bb
['e', 'b']
Score: 1  Solution: bb
[']', 'b']
Score: 1  Solution: bb
[' ', 'b']
Score: 1  Solution: bb
["'", 'b']
Score: 1  Solution: bb
['F', 'b']
Score: 1  Solution: bb
['v', 'b']
Score: 1  Solution: bb
['T', 'b']
Score: 1  Solution: bb
['/', 'b']
Score: 1  Solution: bb
['b', 'h']
Score: 1  Solution: bb
['x', 'b']
Score: 1  Solution: bb
['V', 'b']
Score: 1  Solution: bb
['b', '~']
Score: 1  Solution: bb
['b', '_']
Score: 1  Solution: bb
['b', ';']
Score: 1  Solution: bb
['b', 'b']
Score: 1  Solution: bb
['h', 'b']
Score: 1  Solution: bb
['[', 'b']
Score: 1  Solution: bb
['4', 'b']
Score: 1  Solution: bb
['b', ']']
Score: 1  Solution: bb
['b', 'B']
Score: 1  Solution: bb
['b', 'P']
Score: 1  Solution: bb
['/', 'b']
Score: 1  Solution: bb
['~', 'b']
Score: 1  Solution: bb
['b', 'C']
Score: 1  Solution: bb
['/', 'b']
Score: 1  Solution: bb
['W', 'b']
Score: 1  Solution: bb
['b', 'J']
Score: 1  Solution: bb
['b', 'y']
Score: 1  Solution: bb
['b', '2']
Score: 1  Solution: bb
['b', '?']
Score: 1  Solution: bb
['\x0b', 'b']
Score: 1  Solution: bb
['5', 'b']
Score: 1  Solution: bb
['A', 'b']
Score: 1  Solution: bb
['b', 'R']
Score: 1  Solution: bb
['V', 'b']
Score: 1  Solution: bb
['b', "'"]
Score: 1  Solution: bb
['F', 'b']
Score: 1  Solution: bb
['w', 'b']
Score: 1  Solution: bb
['-', 'b']
Score: 1  Solution: bb
['b', 't']
Score: 1  Solution: bb
['b', '"']
Score: 1  Solution: bb
['.', 'b']
Score: 1  Solution: bb
['1', 'b']
Score: 1  Solution: bb
['b', '\x0b']
Score: 1  Solution: bb
['b', '%']
Score: 1  Solution: bb
['b', 'i']
Score: 1  Solution: bb
['b', 'k']
Score: 1  Solution: bb
['U', 'b']
Score: 1  Solution: bb
['b', 'R']
Score: 1  Solution: bb
['b', 'G']
Score: 1  Solution: bb
['b', 'j']
Score: 1  Solution: bb
['b', 'y']
Score: 1  Solution: bb
['b', ']']
Score: 1  Solution: bb
['b', 'F']
Score: 1  Solution: bb
['r', 'b']
Score: 1  Solution: bb
['=', 'b']
Score: 1  Solution: bb
['A', 'b']
Score: 1  Solution: bb
['b', '7']
Score: 1  Solution: bb
['(', 'b']
Score: 1  Solution: bb
['b', '&']
Score: 1  Solution: bb
['@', 'b']
Score: 1  Solution: bb
['1', 'b']
Score: 1  Solution: bb
['a', 'b']
Score: 0  Solution: ab

Target String Found!

<img width="1042" height="685" alt="image" src="https://github.com/user-attachments/assets/b8d1398f-9538-485e-8650-0795eda28bf6" />

<img width="1087" height="631" alt="image" src="https://github.com/user-attachments/assets/f2f414a8-b5ee-4240-86b7-0a9e03e73a8f" />

## Result:

Thus, the Simple Hill Climbing algorithm was implemented successfully in Python. The program generates a random string, evaluates its difference from the target string, and improves the solution through random mutations until the target string is found.

