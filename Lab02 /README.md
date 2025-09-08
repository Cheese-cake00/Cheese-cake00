Lab 02

- Name: Caeden Tisler
- Email Tisler.3@wright.edu

## Part 1 Answers

Full / absolute path to your private key file: /home/caede

Command to SSH to AWS instance:
```
[ssh -i ceg2350-aws-vm.pem ubuntu@34.193.176.71]
```

## Part 2 Answers

1. `chmod u+r bubbles.txt`
    - Means: This means that the user can read bubble.txt
    - Assessment: This would be fine beacause unless you wanted bubble.txt to be private its ok for user to read it
2. `chmod u=rw,g-w,o-x banana.cabana`
    - Means: user can read and write, the group can no longer write, and others cannot exicute the file 
    - Assessment: the user beign able to read and write is fine, taking away the ability to write from the group is fine but we dont know what permissions they already have other than they previously had access to writing  and taking away the ability to exicute is also fine again we dont know what other permisions they alreay had if any
3. `chmod a=w snow.md`
    - Means: this would overight everything and give only the ability to write to everyone
    - Assessment: this would be a bad thing because not onlyis giving everyone the ability to edit a file not a great idea, not being able to read the file is bad
4. `chmod 751 program`
    - Means: this means that the user gets all perms (rwx) and the group gets reading and exicuting and others get to exicute it
    - Assessment: this would be fine as as standard program would have the user as all perms the group probably people llowed to edit the program and then others are able to use the program
5. `chmod -R ug+w share`
    - Means: this gives the user and the group the writing perm for all file in the directory share 
    - Assessment: this would be a good thing because supposably the files in the directory need editing and the user and the group need thoughs perms to edit them

## Part 3 Answers

1. Command to create new user: sudo adduser user1
2. Path to new user's home directory: /home/user1
3. Evaluate if `ubuntu` can add files to new user's home directory: no it can't add a file it has no permission
4. Command to switch to new user: sudo su - user1
5. Command(s) to go to new user's home directory: the previous command entered the home directory
6. Evaluate if new user can add files to user's home directory: yes i can add files to the new users directory
7. Command to return to `ubuntu` user: exit 
8. Command to return to `ubuntu` home directory: already it the home from the last command

## Part 4 Answers

1. Command(s) to create group named `squad` and add members: sudo addgroup squad
2. Command(s) to add `ubuntu` & user to group `squad`: sudo usermod -aG squad ubuntu
                                                       sudo usermod -aG squad caede
4. Command(s) to allow `squad` to view the `ubuntu` user's home directory contents: sudo chmod g+r /home/ubuntu
5. Command(s) to modify `share` to have group ownership of `squad`: sudo chown :squad share
6. Describe your tests and commands with the user account: works being as user caede i can see test.txt in ubuntu's home
7. Describe the full set of permissions / settings that enable the user to make edits: caede can make a file in share because the group has reading and writing permissions

## Part 5 Answers

For each, write the command used or answer the question posed.

1. Command(s) to make file using `sudo`: sudo touch madwithsudo.txt
2. Command(s) to make file with `root`: sudo su, touch madewithroot.txt
3. Describe / compare ownership and permissions of files: they are the same perms and the owners of both are root
4. Which account can do what actions? (Type Y or N in columns)

Contents inside of `share`
| Account   | Can View  | Can Edit  | Can Change Permissions    |
| ---       | ---       | ---       | ---                       |
| `root`    |   y        |    y       |            y               |
| `ubuntu`  |   y        |    y       |            y               |
| `BOB`     |    y       |     y      |            n               |

`madewithsudo.txt`
| Account   | Can View  | Can Edit  | Can Change Permissions    |
| ---       | ---       | ---       | ---                       |
| `root`    |     y      |      y     |             y              |
| `ubuntu`  |     y      |      y     |              y             |
| `BOB`     |      y     |      n     |               n            |

5. Command(s) to modify permissions: sudo chown ubuntu:squad madwithsudo.txt, sudo chmod 662 madwithsudo.txt
6. How to give user account `sudo`:


