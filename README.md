<h3 align="center">Turing Machine Simulator</h3>

  <p align="center">
    A simple Turing Machine Simulator made in python.
    <br />
    <a href="https://github.com/github_username/repo_name"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/github_username/repo_name">View Demo</a>
    ·
    <a href="https://github.com/github_username/repo_name/issues">Report Bug</a>
    ·
    <a href="https://github.com/github_username/repo_name/issues">Request Feature</a>
  </p>
</div>A turing machine is a hypothetical computer, invented in 1936 by the British mathematician Alan Turing, that can evaluate any computable function. Though hypothetical, turing machines play a large role in computer science. Many variants of turing machines have been devised; the purpose of this exercise is to build a simulator for a particular type of turing machine.

The hardware of our turing machine consists of a read/write head and an infinite tape divided into cells that passes across the read/write head. Each cell on the tape contains a symbol, which we take as an ascii character; there is a special blank symbol that is present in all cells which are not yet written. The read/write head can see one cell at a time, read its contents, and write a new symbol (possibly the blank symbol) to the cell.

The software of our turing machine consists of a table encoding a transition function and a state register that maintains the current state. In our machine, states are numbered with non-negative integers; the machine always starts in state zero, and halts if it enters a negative-numbered state. The program being executed by the turing machine is encoded in the transition function, which takes two inputs, the current state and the symbol in the current cell, and then writes a new symbol (or the same symbol, or the special symbol blank) in the current cell, then either moves the read/write head one cell to the left or one cell to the right or remains in the same place, then resets the state to a new state. The transition function is thus encoded in a table of 5-tuples q1 s1 s2 d q2 where q1 is the current state, s1 is the symbol currently under the read/write head, s2 is the symbol to be written, d is the direction to move the tape, and q2 is the next state to enter.

As an example, consider the tape _ _ _ [1] 1 1 + 1 1 1 1 1 _ _ _. This is our notation for a tape that contains, in the middle of an infinite number of blanks, the nine symbols consisting of three one’s, a plus sign, and five one’s, with the read/write head positioned over the first one; the tape can be considered to model the problem of adding the two numbers three and five. The program

    0 1 1 R 0
    0 + 1 R 1
    1 1 1 R 1
    1 _ _ L 2
    2 1 _ L -1

adds the two numbers and writes _ _ _ 1 1 1 1 1 1 1 [1] _ _ _ as its output.

Write a function that takes a turing-machine program and a tape and simulates the action of a turing machine, writing the final tape as output.