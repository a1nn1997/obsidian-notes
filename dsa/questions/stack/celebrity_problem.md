
# code 

```python
class Solution:
    # Function to find if there is a celebrity in the party or not.
    def celebrity(self, M, n):
        # Initialize left and right pointers
        left = 0
        right = n - 1

        # Loop until left is less than right
        while left < right:
            # If the left person knows the right person, move left forward
            if M[left][right] == 1:
                left += 1
            # Otherwise, move right backward
            else:
                right -= 1

        # Check if the left person is a potential celebrity
        for i in range(n):
            # If the left person knows anyone to the right or someone to the right doesn't know the left person,
            # return -1 indicating no celebrity found
            if i != left and (M[left][i] == 1 or M[i][left] == 0):
                return -1

        # Return the index of the potential celebrity
        return left

```