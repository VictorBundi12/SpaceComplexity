  GROUP MEMBERS
VICTOR BUNDI SCT221-01176/2023
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
