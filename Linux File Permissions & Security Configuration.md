## Project Context
As a member of the security team supporting a research division, my role in this scenario is to audit directory and file permissions to ensure they align with organizational security standards. This project demonstrates how to use Linux commands, specifically `chmod`, to double-check current access levels and alter permissions for users/owners, groups, and others to correct any identified vulnerabilities and incorrect permission assignments.

## 1. Check file and directory details
To check the details for all files and directories simultaneously in a single command, I executed the following:
```bash
ls -la
```
## 2. Describe the permissions string
The 10-character string belonging to "drafts" is `drwx--x---`. This string indicates the following:
*   `d`: Indicates that "drafts" is a directory.
*   `rwx`: The current permissions allow the user (owner) to read, write, and execute.
*   `--x`: Groups are only allowed to execute.
*   `---`: Others are not given permission to interact with the directory.

## 3. Change file permissions
`project_k.txt` is the only file in the current output that requires changes to its access permissions. Currently, "others" are allowed to write to this file, which is a direct breach of company security guidelines. To fix this, I removed their write permissions. Since they were already denied all other permissions on this file, I executed the following command:
```bash
chmod o= project_k.txt
```
(Note: chmod o-w project_k.txt would also accomplish this result.)

## 4. Change file permissions on a hidden file
To align the file permissions on the hidden file `.project_x.txt` with company security protocols, I modified the user's ability from read and write to read-only. For groups, I removed their write permissions and granted them read permissions that they did not previously have. 

Since I needed to change multiple permissions for different entities simultaneously, I executed the following command:
```bash
chmod u=r,g=r .project_x.txt
```

## 5. Change directory permissions
Upon checking the permissions for the "drafts" directory, I noticed that groups had execute permissions, when only the owner "researcher2" should be allowed to interact with the directory and its contents. 

To remedy this, I reset the group permissions to no access. The "others" category already had no access, and the current owner/user permissions were already correct. I executed the following command:
```bash
chmod g= drafts
```
(Note: chmod g-x drafts would also accomplish the same end goal, as groups only had execute permissions.)

## Summary
In this exercise, I took on the role of a security team member responsible for double-checking file and directory permissions. I changed the permissions of the directory so that only the user/owner, "researcher2," could access and interact with the directory and its contents. I also modified permissions on both a hidden file and a normal accessible file, systematically adding and removing permissions for their respective users, groups, and others.
