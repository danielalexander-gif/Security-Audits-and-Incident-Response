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
To open `"allow_list.txt"`, the file must first be imported and labeled by writing `import_file = "allow_list.txt"`. I then used a `with` statement in conjunction with the `.open()` function to open the file in read mode, knowing that `with` automatically closes the file once the statement finishes. In `open(import_file, "r")`, there are two arguments separated by a comma: the first specifies which file to open, and the second (`"r"`) specifies the action, which in this case is reading the file as the variable `file`.

```python
import_file = "allow_list.txt"
with open(import_file, "r") as file:
```

#### 2. Read the file contents
To read the file, the `.read()`  method must be used to convert the contents into a string. Since the `open()` function included the read argument, I can call the `.read()` function inside the block. It is applied to the file variable, and the output is then labeled and stored in the variable `ip_addresses`.

```python
ip_addresses = file.read()
```

#### 3. Convert the string into a list
Next, the contents of the file need to be converted from a string into a list using `.split().` Defining `ip_addresses = ip_addresses.split()` tells the machine that this updated variable is the same as the first, except it is now organized in a list format split on the whitespace.

```python
ip_addresses = ip_addresses.split()
```

#### 4. Iterate through and remove restricted IP addresses
To iterate through the list, I used a `for` loop. This statement tells the system that for every element in the 'ip_addresses' list, it should display each element, and the for loop allows this process to continue looping until complete.

```python
for element in ip_addresses:
    print(element)
```

#### 5. Remove IP addresses that are on the remove list
At this point, we need to remove any IP addresses that are also on the `remove_list`. With this if statement added, if an element from `remove_list` is found in `ip_addresses`, that element is removed from the list using `.remove(element)`, and the updated `ip_addresses` list is printed.

```python
if element in remove_list:
    ip_addresses.remove(element)
print(ip_addresses)
```

#### 6. Update the file with the revised list of IP addresses
Now I need to update the allow list with the new list of IP addresses post-removal. Using `.join()` converts the list back into a string with characters that separate each element, and `"\n"` instructs the format of the Python output to place every new element on a new line. Next, the `with` statement using `w` tells the computer that I want to write over the contents of the original file. Since `.write()` writes string data to a file and replaces existing data—essentially overwriting it passing `ip_addresses` as an argument into `file.write(ip_addresses)` rewrites `"allow_list.txt"` with the updated variable data. This writes the revised allow list as a string to the file and prevents anyone who was removed from the list from keeping access. 

```python
iip_addresses = " ".join(ip_addresses)

# Build `with` statement to rewrite the original file
with open(import_file, "w") as file:
  # Rewrite the file, replacing its contents with `ip_addresses`
  file.write(ip_addresses)
```

### Summary
For a “company” I created an algorithm to identify and remove elements or in this case ip addresses that are on the allow list that should no longer have access.[cite: 1] To accomplish this the algorithm needed to convert a string to a stored list to edit, be converted back into a string and written over with a revised list.[cite: 1]
