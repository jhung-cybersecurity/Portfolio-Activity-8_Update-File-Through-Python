# Portfolio Scenario

You are a security professional working at a health care company. As part of your job, you're required to regularly update a file that identifies the employees who can access restricted content. The contents of the file are based on who is working with personal patient records. Employees are restricted access based on their IP address. There is an allow list for IP addresses permitted to sign into the restricted subnetwork. There's also a remove list that identifies which employees you must remove from this allow list.

Your task is to create an algorithm that uses Python code to check whether the allow list contains any IP addresses identified on the remove list. If so, you should remove those IP addresses from the file containing the allow list.

## Step 1: Open the file that contains the allow list

**Code**
```Python
# Assign `import_file` to the name of the file
import_file = "allow_list.txt"

# Assign `remove_list` to a list of IP addresses that are no longer allowed to access restricted information
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]

#Display `import_file`
print(import_file)

#Display `remove_list`
print(remove_list)
```

**Workflow Explanation:**  

First I assign `import_file` to the name of the given file `allow_list.txt`. Then I assign `remove_list` to the given IP addresses.  
Lastly, I pass both codes through `print()` to display the result to complete this task.


## Step2: Read the file contents

**Code**
```Python
# Assign `import_file` to the name of the file
import_file = "allow_list.txt"

# Assign `remove_list` to a list of IP addresses that are no longer allowed to access restricted information
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]

# Using `with` statement to read the contents of the file
with open(import_file, "r") as file:

  #Use `.read()` to read the imported file and store it variable named `ip_addresses`
  ip_addresses = file.read()

# Display `ip_addresses`
print(ip_addresses)
```

**Workflow Explanation:**  

I use the `with` statement to ensure the file closes properly after my code. Then I use `open()` statement and pass it through `"r"` to read the file.
Next I make sure I indent the next line and use `.read()` to read the imported file and store it in `ip_addresses`. Lastly, I use `print()` to display the code.

## Step 3: Convert the string into a list

**Code**
```Python
# Assign `import_file` to the name of the file
import_file = "allow_list.txt"

# Assign `remove_list` to a list of IP addresses that are no longer allowed to access restricted information
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]

# Using `with` statement to read the contents of the file
with open(import_file, "r") as file:

  #Use `.read()` to read the imported file and store it variable named `ip_addresses`
  ip_addresses = file.read()

# Use `.split()` to convert `ip_addresses from a string to a list
ip_addresses = ip_addresses.split()

# Display `ip_addresses`
print(ip_addresses)
```
**Workflow Explanation:**  

I need to remove individual IP addresses from the allow list and in order to do so, I need to change IP addresses to be in a list format. I achieve this task by using `.split()`.

## Step 4: Iterate through the remove list

**Code**
```Python
# Assign `import_file` to the name of the file
import_file = "allow_list.txt"

# Assign `remove_list` to a list of IP addresses that are no longer allowed to access restricted information
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]

# Using `with` statement to read the contents of the file
with open(import_file, "r") as file:

  #Use `.read()` to read the imported file and store it variable named `ip_addresses`
  ip_addresses = file.read()

# Use `.split()` to convert `ip_addresses from a string to a list
ip_addresses = ip_addresses.split()

# Building iterative statement
# Name loop variable `element`
# Loop through `ip_addresses`
for element in ip_addresses:

  # Display `element` in every iteration
  print(element)
```

**Workflow Explanation:**  

I was provided with a second list called `remove_list` which contains all the IP addresses that should be removed from the `ip_addresses` list.
In the code above, I use the `for` loop to iterate through the `remove_list` and I use `element` as the loop variable. I am not using the `while` loop here because we want the code to run continously without a condition. 

## Step 5: Remove IP addressses that are on the remove list  

**Code**
```Python
# Assign `import_file` to the name of the file
import_file = "allow_list.txt"

# Assign `remove_list` to a list of IP addresses that are no longer allowed to access restricted information
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]

# Using `with` statement to read the contents of the file
with open(import_file, "r") as file:

  #Use `.read()` to read the imported file and store it variable named `ip_addresses`
  ip_addresses = file.read()

# Use `.split()` to convert `ip_addresses from a string to a list
ip_addresses = ip_addresses.split()

# Building iterative statement
# Name loop variable `element`
# Loop through `ip_addresses`
for element in ip_addresses:

  # Build conditional statement; if current element is in `remove_list`,
  if element in remove_list:

      # then current element should be removed from `ip_addresses`
      ip_addresses.remove(element)

# Display `ip_addresses`
print(ip_addresses)
```

**Workflow Explanation:**  

Here, my goal is to write an iterative statement that removes all the IP addresses from the `allow_list.txt` that are also on the `remove_list`. I achieve that by using an `if` conditional statement within the `for` loop statment. I use the `.remove()` method and pass it through `element`, which is a variable that was assigned in the previous lines. The `.remove()` method is possible here because there are no duplicates in the `ip_addresses` list. Finally, I display `ip_addresses` for my result. 

## Step 6: Update the file with the revised list of IP addresses  

**Code**
```Python
# Assign `import_file` to the name of the file
import_file = "allow_list.txt"

# Assign `remove_list` to a list of IP addresses that are no longer allowed to access restricted information
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]

# Using `with` statement to read the contents of the file
with open(import_file, "r") as file:

  #Use `.read()` to read the imported file and store it variable named `ip_addresses`
  ip_addresses = file.read()

# Use `.split()` to convert `ip_addresses from a string to a list
ip_addresses = ip_addresses.split()

# Building iterative statement
# Name loop variable `element`
# Loop through `ip_addresses`
for element in ip_addresses:

  # Build conditional statement; if current element is in `remove_list`,
  if element in remove_list:

      # then current element should be removed from `ip_addresses`
      ip_addresses.remove(element)

# Convert `ip_addresses` back to a string so that it can be written back into the text file
ip_addresses = " ".join(ip_addresses)

# Build `with` statement to rewrite the original file
with open(import_file, "w") as file:

  # Rewrite the file, replacing its contents with `ip_addresses`
  file.write(ip_addresses)
```

**Workflow Explanation:**  

Now that I'm done removing the IP addresses, I need to update the original file. First, I have to convert `ip_addresses` list back to a string. I achieve this by using `.join()` method. In my `.join()` code, I type out `" "` with a space in between the double quotes to seperate the IP addresses so they're not clumped together when I run the code. Then I pass the `.join()` statement through `ip_addresses`. Lastly, to update the original file, I use the same line of code starting with the `with` statement but this time, I use `"w"`, or "write". Then, I rewrite the file by replacing its contents with `ip_addresses`.

## Summary  

I wrote an algorithm to first identify the IP addresses which are needed to be removed from the `allow_list.txt` file of approved IP addresses. Before moving onto the next step, I need to convert the file into a string to be read, then converting this string to a list stored in the variable `ip_addresses`. Next I use the `for` iterative statement to evaluate if the `element` is part of the `ip_addresses` list. If it is, I set the condition of the Python code to remove the specified IP addresses by using the `.remove()` method. Now that the main task is completed, I then need to convert `ip_addresses` back to a string so that it can be written back into the text file. I achieve this by using the `.join()` method and with a `" "` statement before to make it more readable. Lastly, I update the original file with our newly updated file with the `.write()` method. 
