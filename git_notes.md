# GIT AND GITHUB NOTES

## BASIC COMMITS
```git
git config --global user.name "name"
```
for your by default name 
```git 
git config --global user.email "email@female.com"
```
for your by default email
```git 
git config --global core.editor "code --wait"
```
for by defult editor
```git
git config --global core.autocrlf
```
for converting windows command into mac or vice versa
```git 
git config --global -e
```
for editing already maked changes

## STAGES

**U - untracked**
- click on source control
- click on initialize repository

**A - added or staged**
- in source control, a changes section will appear.
- click on `+` icon just in front og your file name that you want to add.
- your files action now will be monitized.

**M - modified after commit**
- whenever you make any changes in your file after making a checkpoint this will appears.

**C - commited**

    *TO CHECK YOUR STAGE*

    type `git config -s` in terminal
yeh unki stage nhi bta pata jo file commit ho chuki hai or commit hone k baad koi changes nhi hue hai.

## TO CHECK HOW MANY CHANGES CHECKPOINTS YOU MADE

- click on new terminals
- type `git log --oneline` 

## MAKING A CHECKPOINT

- apna code likho
- source control mai jaake checkpoint ka nam yah description likho
- click on commit

## TO IGNORE ANY FILE EXISTING IN FOLDER

- create a file named `.gitignore`.
- type file name that you want to ignore.

## RESET 

piche wale checkpoint pe jaane k liye reset use krte hai.

there are three options in reset =>
- **HARD**

`git reset --hard HEAD~1`
> here the code will be undoen by 1 checkpoint in the whole folder
- **SOFT**
- **MIXED**

## BRANCHING

It's like mtlb hmara koi main code hai or hme  usme kuch add krana hai kisi user sai toh hm main file mai add na krake use ek copy deynge jiska use krke woh user usme apna feature add krskta hai or end mai un dono file ko merge karke duplicate file ko dlt kardenge.
> data of merged main file and the duplicate file of user will be same

`git branch` 
iska use krke hm chk kr skte hai ki kitni branches hai.

## THREE WAY MERGE

agr bde level pai branching krae toh kuch major issues aa skte hai like hmari main file kuch ese features bhi aachuke haii jo duplicate file mai nahi present hai tohh is case mai git hme deta hai `conflict` ki dono file mai same code nahi hai. is time pe wo hmse 3 option dega.

- accept current change
- accept incoming change
- accept both changes

|work|code|remark|
|:----:|:----:|:----|
|For Switching Branch| `git switch <branch name>`||
|For Merging |`git merge <duplicate branch name>`|you must be on your main branch|
|for getting full merging path|`git log --online --graph`|
|to delete git|``|
|to clear|`clear`|
|To Delete|`git branch -d <branch name>`|
|to create and switch a branch at the same time|`git switch -C <branch name>`|
|to stash|`git stash`|
|To apply stash |`git stash apply`|
|to delete the saved stash|`git stash clear`|
|for cloning a into your system|`git clone <repo url>`|
## stashing
jab aap kisi branch mein kaam kr rhe ho and aapne kuchh code likha hai and aapne us code ko commit nahi kiya hai, aur aap doosri branch mein jaane ki koshish krte ho to git aapko bolta hai ki bhai saved nahi changes delete ho jaayege hum chaahe to un changes ko delete hone de yaa fir un changes ko draft kr skte hai, jab bhi draft karege to wo changes naa hi delete honge na hi add honge but beech mein kahi dale rahege fir aap us branch mein jab waapas aaye to wo changes waapas se apply kr skte ho

- like jb aapko dusri branch mai switch karna ho bina commit kre toh use kro `git stash`

- is se code draft save ho jata hai or jb waps aake drafted code dekhna ho tb use krte h `git stash apply` us se woh code visible hojata hai or usko edit yah commit kar skte h.

- agr woh draft saved code use nhi karna or delete karna hai toh use `git stash clear`.

## git code for adding file in a repository
```git
echo "# practice" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/prriisa/practice.git
git push -u origin main
```

## push an existing repository from the command line
```git
git remote add origin https://github.com/prriisa/practice.git
git branch -M main
git push -u origin main
```

## SOME COMMON STEPS

- main banda folder and initial files banaayega

apne desktop pe (VS Code mai)
- ab usse github par daal de

terminal ka use krke code toh upr diya hi huaa hai 
- collaborators add kare

github pe jaake invite requests send kijiye

- saare bande us repo se cloning karein

for cloning a repo into your device you just need to `git clone <repo url>`
is se aapka code desktop pe aajaega

- [VERY IMPORTANT] apni branch create karein

kuchbhi edit krne se phle nyi branch bnaye whi kuch code kre.

- apna code usi branch mein likhein
- complete hone par commit dein and push kar dein
- inform karein teammate ko about the commit
- merger banda fetch karega and merge karega and
reg

for fetching use `git fetch`,
then merge karega, aab ise github pe upload krne k liye push karna pdega. `git push origin main`

aab yeh code sbke desktop pe laane k liye sbko `git pull` karna hoga.
