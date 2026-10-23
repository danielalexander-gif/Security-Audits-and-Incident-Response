# Algorithm_for_file_updates_in_Python.md

**Context:** [PLACEHOLDER: We will write the simulation disclaimer here so recruiters know it's a lab environment.]

**Objective:** [PLACEHOLDER: We will write a 1-sentence goal for the Python script.]
**Skills & Tools Demonstrated:** [PLACEHOLDER: We will list Python, Automation, etc.]

### Executive Summary
[PLACEHOLDER: We will write a 3-sentence summary of what the script does for management.]

### Project Description
In this simulated scenario, a company manages its network access using a simple text file of approved IP addresses. To automate their security updates, I implemented a Python script that opens the file, removes any restricted IP addresses, and overwrites the document with the revised allow-list.

### Python Algorithm Breakdown

#### 1. Open the file that contains the allow list
To access the allow list, the file name must first be imported and assigned to a variable, which I labeled as `import_file`. I then used a `with` statement in conjunction with the `.open()` function to open the file in read mode, specified by the `"r"` argument. Using the `with` statement is essential here because it automatically closes the file after the block of code executes, preventing resource leaks.

```python
import_file = "allow_list.txt"
with open(import_file, "r") as file:
```

#### 2. Read the file contents
To read the file's contents, the `.read()` method must be used to convert the data into a string. This read function is applied to the open `file` variable, and the resulting string of approved IP addresses is then labeled and stored in a new variable called `ip_addresses`.

```python
ip_addresses = file.read()
```

#### 3. Convert the string into a list
To manipulate the data and remove specific IPs, the contents of the file need to be converted from a string into a list format. I used the `.split()` method, which separates the string based on whitespace and organizes the data into a list. This redefines the `ip_addresses` variable as a list, allowing the algorithm to isolate and evaluate each individual IP address.

```python
ip_addresses = ip_addresses.split()
```

#### 4. Iterate through and remove restricted IP addresses
To identify IP addresses that should no longer have access, I used a `for` loop to iterate through every element in the `ip_addresses` list. Inside this loop, I added an `if` statement to check if the current element is also found in the `remove_list`. If a match is found, the `.remove()` function is applied to delete that specific element from the `ip_addresses` list. 

```python
for element in ip_addresses:
    if element in remove_list:
        ip_addresses.remove(element)
```

#### 5. Remove IP addresses that are on the remove list
At this point we need to remove IP addresses that are also on the list called remove_list[cite: 1] To do that we need to add if element in remove_list: ip_addresses.remove(element) print(ip_addresses)[cite: 1] Now if an element from remove list is found in ip_addresses then the element of the list will be removed and then ip_addresses will be printed[cite: 1]

#### 6. Update the file with the revised list of IP addresses 
Now I need the allow list to update with the new list of ip addresses post removal.[cite: 1] ip_addresses = " ".join(ip_addresses)[cite: 1] .join() converts the list back into a string with characters that separate each element.[cite: 1] Then the argument created is passed as an argument to .write() to write to the file “allow_list.txt.[cite: 1] (“\n”) here is instructing the format of the python output to place every new element on a new line.[cite: 1] # Build `with` statement to rewrite the original file with open(import_file, "w") as file: This statement tells the computer that you want to write over contents of a file.[cite: 1] .write() writes string data to a file and or replaces data hence “overwriting” # Rewrite the file, replacing its contents with `ip_addresses` file.write(ip_addresses)[cite: 1] This portion writes the alow list as a string to “allow_list.txt”[cite: 1] This prevents anyone who was removed from the list.[cite: 1] It rewrites the file and that the file.write replaces data with the variable data.[cite: 1]

### Summary
For a “company” I created an algorithm to identify and remove elements or in this case ip addresses that are on the allow list that should no longer have access.[cite: 1] To accomplish this the algorithm needed to convert a string to a stored list to edit, be converted back into a string and written over with a revised list.[cite: 1]
