# Algorithm_for_file_updates_in_Python.md

**Context:** [PLACEHOLDER: We will write the simulation disclaimer here so recruiters know it's a lab environment.]

**Objective:** [PLACEHOLDER: We will write a 1-sentence goal for the Python script.]
**Skills & Tools Demonstrated:** [PLACEHOLDER: We will list Python, Automation, etc.]

### Executive Summary
[PLACEHOLDER: We will write a 3-sentence summary of what the script does for management.]

### Project Description
At the company traffic is controlled with a list of allowed ip addresses.[cite: 1] An algorithm must be made to automate identifying ip addresses that shouldn’t have access too, and updates the list of allowed ip addresses.[cite: 1]

### Python Algorithm Breakdown

#### 1. Open the file that contains the allow list
To open the file “allow_list.txt” use with open(import_file, "r") as file: but first must be imported and labeled by writing import_file = “allow_list.txt”[cite: 1] The with statement is used in conjunction with the .open() function to open the file in read mode.[cite: 1] With closes the file after the with statement.[cite: 1] .open( import_file,”r”) has two functions separated by a comma.[cite: 1] The first specifies which file to open and the second “r” specifies the action which in this case is reading.[cite: 1] The as variable file[cite: 1]

#### 2. Read the file contents
To read the file,  .read() must be used to convert the to the string.[cite: 1] Since the open function included the argument I can call the read function in.[cite: 1] Read is applied to the file variable that is then labeled and stored as “ip_addresses”[cite: 1]

#### 3. Convert the string into a list
Now the contents of the file need to be converted into a string.[cite: 1] Now .split() will be used in order to convert the string into a list.[cite: 1] Defining ip_addresses = ip_addresses.split() tells the machine that this second variable is the same as the first except should be put in a list format split on the white space because of .split()[cite: 1]

#### 4. Iterate through the remove list
To iterate through the remove list i need to use for element in ip_addresses: print(element)[cite: 1] This statement tells the system that for every element in the list called ip_addresses display every element.[cite: 1] The for loop allows this to continue looping until complete.[cite: 1]

#### 5. Remove IP addresses that are on the remove list
At this point we need to remove IP addresses that are also on the list called remove_list[cite: 1] To do that we need to add if element in remove_list: ip_addresses.remove(element) print(ip_addresses)[cite: 1] Now if an element from remove list is found in ip_addresses then the element of the list will be removed and then ip_addresses will be printed[cite: 1]

#### 6. Update the file with the revised list of IP addresses 
Now I need the allow list to update with the new list of ip addresses post removal.[cite: 1] ip_addresses = " ".join(ip_addresses)[cite: 1] .join() converts the list back into a string with characters that separate each element.[cite: 1] Then the argument created is passed as an argument to .write() to write to the file “allow_list.txt.[cite: 1] (“\n”) here is instructing the format of the python output to place every new element on a new line.[cite: 1] # Build `with` statement to rewrite the original file with open(import_file, "w") as file: This statement tells the computer that you want to write over contents of a file.[cite: 1] .write() writes string data to a file and or replaces data hence “overwriting” # Rewrite the file, replacing its contents with `ip_addresses` file.write(ip_addresses)[cite: 1] This portion writes the alow list as a string to “allow_list.txt”[cite: 1] This prevents anyone who was removed from the list.[cite: 1] It rewrites the file and that the file.write replaces data with the variable data.[cite: 1]

### Summary
For a “company” I created an algorithm to identify and remove elements or in this case ip addresses that are on the allow list that should no longer have access.[cite: 1] To accomplish this the algorithm needed to convert a string to a stored list to edit, be converted back into a string and written over with a revised list.[cite: 1]
