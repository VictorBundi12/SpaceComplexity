  GROUP MEMBERS:

  
VICTOR BUNDI SCT221-0176/2023
BRIAN MWANGI SCT221-0334/2023
MOSES NYAMANYI SCT221-0297/2023

# SpaceComplexity
Space complexity of recursive  algorithm
algorithm test(n)
{ 
    if (n > 0) {
        print n 
        test(n-1)  // First Recursive Call
        test(n-1)  // Second Recursive Call
    }
}

The algorithm prioritizes completing the first recursive call (the "left" child) entirely before beginning the second recursive call (the "right" child).
Space Complexity Mechanism: Space complexity in recursive algorithms is determined by the Call Stack. Each active function call occupies a "stack frame" in memory.
The maximum space required is proportional only to the maximum depth of the recursion tree.

Assuming n = 4
Start: test(4) is called.
    Stack Depth: 1 | Output: 4
        Step 1: test(4) pauses to call its first child: test(3).
        Stack Depth: 2 | Output: 3
            Step 2: test(3) pauses to call its first child: test(2).
            Stack Depth: 3 | Output: 2
                Step 3: test(2) pauses to call its first child: test(1).
                Stack Depth: 4 | Output: 1
                    Step 4: test(1) calls test(0).
                    Stack Depth: 5 (MAXIMUM) | test(0) hits base case (0≯0). Returns immediately.
                    Memory for test(0) is released.
                    Step 5: test(1) calls its second child test(0).
                    Stack Depth: 5 (MAXIMUM) | test(0) hits base case. Returns.
                    Memory for test(0) is released.
                test(1) finishes and returns.
                Memory for test(1) is released. Stack Depth drops to 3.
                Step 6: test(2) resumes and calls its second child: test(1).
                Stack Depth: 4 | Output: 1
                    This utilizes the memory space previously freed by Step 3.
                    Step 7: test(1) calls test(0) (Left), then test(0) (Right).
                    Stack Depth: 5 | Both base cases hit and return.
                test(1) finishes and returns.
            test(2) finishes and returns.
            Memory for test(2) is released. Stack Depth drops to 2.
            Step 8: test(3) resumes and calls its second child: test(2).
            Stack Depth: 3 | Output: 2
                This utilizes the memory space previously freed by Step 2.
                Step 9: test(2) calls test(1) (Left), prints 1, recurses, returns.
                Step 10: test(2) calls test(1) (Right), prints 1, recurses, returns.
            test(2) finishes and returns.
        test(3) finishes and returns.
        Memory for test(3) is released. Stack Depth drops to 1.
        Step 11: test(4) resumes and calls its second child: test(3).
        Stack Depth: 2 | Output: 3
            Note: This entire branch runs exactly like Step 1, reusing the same stack space.
            [Repeats logic of Steps 2–10]
        test(3) finishes and returns.
    test(4) finishes and returns. End. Stack is empty.

    As seen in Step 4 and Step 5, the stack depth reaches a maximum of 5 frames (test(4) → 3 → 2 → 1 → 0).
MaxDepth = n + 1(drop the constant) to get the Space Complexity as O(n).
