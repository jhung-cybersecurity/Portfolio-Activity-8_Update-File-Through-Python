# Project Scenario

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
**Run Result:**
```
allow_list.txt
['192.168.97.225', '192.168.158.170', '192.168.201.40', '192.168.58.57']
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

  #Use `.read()` to read the imported file and store it ariable named `ip_addresses`
  ip_addresses = file.read()

# Display `ip_addresses`
print(ip_addresses)
```

**Run Result:**


**Workflow Explanation:**


