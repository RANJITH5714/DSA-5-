# Data structure to store a binary tree node
class Node:
    def __init__(self, data=None, left=None, right=None):
        self.data = data
        self.left = left
        self.right = right
 
 
# Recursive function to perform inorder traversal on the tree
def inorder(root):
 
   # return if the current node is empty
   if root is None:
        return
 
   # Traverse the left subtree
   inorder(root.left)
 
  # Display the data part of the root (or current node)
  print(root.data, end=' ')
 
   # Traverse the right subtree
  inorder(root.right)
 
 
if __name__ == '__main__':
 
   ''' Construct the following tree
               1
             /   \
            /     \
           2       3
          /      /   \
         /      /     \
        4      5       6
              / \
             /   \
            7     8
    '''
 
   root = Node(1)
   root.left = Node(2)
   root.right = Node(3)
   root.left.left = Node(4)
   root.right.left = Node(5)
   root.right.right = Node(6)
   root.right.left.left = Node(7)
   root.right.left.right = Node(8)
 
   inorder(root)
   
from collections import deque
 
 
# Data structure to store a binary tree node
class Node:
    def __init__(self, data=None, left=None, right=None):
        self.data = data
        self.left = left
        self.right = right
 
 
# Iterative function to perform inorder traversal on the tree
def inorderIterative(root):
 
   # create an empty stack
   stack = deque()
 
   # start from the root node (set current node to the root node)
   curr = root
 
   # if the current node is None and the stack is also empty, we are done
   while stack or curr:
 
   # if the current node exists, push it into the stack (defer it)
   # and move to its left child
   if curr:
            stack.append(curr)
            curr = curr.left
        else:
            # otherwise, if the current node is None, pop an element from the stack,
            # print it, and finally set the current node to its right child
            curr = stack.pop()
            print(curr.data, end=' ')
 
   curr = curr.right
 
 
if __name__ == '__main__':
 
   ''' Construct the following tree
               1
             /   \
            /     \
           2       3
          /      /   \
         /      /     \
        4      5       6
              / \
             /   \
            7     8
    '''
 
   root = Node(1)
   root.left = Node(2)
   root.right = Node(3)
   root.left.left = Node(4)
   root.right.left = Node(5)
   root.right.right = Node(6)
   root.right.left.left = Node(7)
   root.right.left.right = Node(8)
 
   inorderIterative(root)
   # Naive method to find a pair in a list with the given sum
def findPair(nums, target):
	# consider each element except the last
	for i in range(len(nums) - 1):
	# start from the i'th element until the last element
		for j in range(i + 1, len(nums)):
 	# if the desired sum is found, print it
			if nums[i] + nums[j] == target:
				print('Pair found', (nums[i], nums[j]))
				return
	# No pair with the given sum exists in the list
	print('Pair not found')
if __name__ == '__main__':

nums = [8, 7, 2, 5, 3, 1]
	target = 10

findPair(nums, target)
# Function to find a pair in an array with a given sum using sorting
def findPair(nums, target):
 
   # sort the list in ascending order
   nums.sort()
 
   # maintain two indices pointing to endpoints of the list
   (low, high) = (0, len(nums) - 1)
 
   # reduce the search space `nums[low…high]` at each iteration of the loop
 
   # loop till the search space is exhausted
   while low < high:
 
   if nums[low] + nums[high] == target:        # target found
            print('Pair found', (nums[low], nums[high]))
            return
 
   # increment `low` index if the total is less than the desired sum;
   # decrement `high` index if the total is more than the desired sum
   if nums[low] + nums[high] < target:
            low = low + 1
        else:
            high = high - 1
 
   # No pair with the given sum exists
   print('Pair not found')
 
 
if __name__ == '__main__':
 
   nums = [8, 7, 2, 5, 3, 1]
    target = 10
 
   findPair(nums, target)
   # Data structure to store a binary tree node
class Node:
    def __init__(self, data=None, left=None, right=None):
        self.data = data
        self.left = left
        self.right = right
 
 
# Recursive function to perform postorder traversal on the tree
def postorder(root):
 
  # return if the current node is empty
   if root is None:
        return
 
  # Traverse the left subtree
  postorder(root.left)
 
  # Traverse the right subtree
  postorder(root.right)
 
   # Display the data part of the root (or current node)
  print(root.data, end=' ')
 
 
if __name__ == '__main__':
 
   ''' Construct the following tree
               1
             /   \
            /     \
           2       3
          /      /   \
         /      /     \
        4      5       6
              / \
             /   \
            7     8
    '''
 
   root = Node(1)
   root.left = Node(2)
   root.right = Node(3)
   root.left.left = Node(4)
   root.right.left = Node(5)
   root.right.right = Node(6)
   root.right.left.left = Node(7)
   root.right.left.right = Node(8)
 
   postorder(root)
   
from collections import deque
 
 
# Data structure to store a binary tree node
class Node:
    def __init__(self, data=None, left=None, right=None):
        self.data = data
        self.left = left
        self.right = right
 
 
# Iterative function to perform postorder traversal on the tree
def postorderIterative(root):
 
  # return if the tree is empty
  if root is None:
        return
 
  # create an empty stack and push the root node
  stack = deque()
  stack.append(root)
 
   # create another stack to store postorder traversal
   out = deque()
 
   # loop till stack is empty
   while stack:
 
   # pop a node from the stack and push the data into the output stack
   curr = stack.pop()
   out.append(curr.data)
 
   # push the left and right child of the popped node into the stack
   if curr.left:
       stack.append(curr.left)
 
   if curr.right:
       stack.append(curr.right)
 
   # print postorder traversal
  while out:
        print(out.pop(), end=' ')
 
 
if __name__ == '__main__':
 
  ''' Construct the following tree
               1
             /   \
            /     \
           2       3
          /      /   \
         /      /     \
        4      5       6
              / \
             /   \
            7     8
    '''
 
   root = Node(1)
  root.left = Node(2)
  root.right = Node(3)
  root.left.left = Node(4)
  root.right.left = Node(5)
  root.right.right = Node(6)
  root.right.left.left = Node(7)
  root.right.left.right = Node(8)
 
  postorderIterative(root)
 
 


 


 
 

