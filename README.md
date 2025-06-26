# RecursiveArrayAddition
A program to match the parentheises stored in a string using stack data structure.


def is_parentheses_matched(expression):
    stack = []

    # Dictionary to hold matching pairs
    matching_parentheses = {')': '(', '}': '{', ']': '['}

    for char in expression:
        if char in "([{":
            stack.append(char)
        elif char in ")]}":
            if not stack or stack[-1] != matching_parentheses[char]:
                return False  # Mismatch found or stack is empty
            stack.pop()  # Matching pair found

    # If stack is empty, all parentheses are matched
    return len(stack) == 0

# Example usage
expression = "{[()]}()[]"
print("Expression:", expression)

if is_parentheses_matched(expression):
    print("Parentheses are properly matched ✅")
else:
    print("Parentheses are NOT matched ❌")

# Output
Expression: {[()]}()[]
Parentheses are properly matched ✅
