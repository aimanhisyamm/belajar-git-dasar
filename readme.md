# Git Dasar
```
3ab43a6 (HEAD -> master) Menambahkan readme.txt di .gitignore
a260735 Menambah file4.txt
74aab56 Menambah .gitignore
008f5c5 Revert "Merubah file2.txt menjadi file_2.txt"
d187367 Menambah file3.txt sebanyak 2 baris
67eb55d Merubah file2.txt menjadi file_2.txt
6c21349 Menghapus file3.txt
1092352 Melakukan perubahan di file1.txt dan file2.txt
8016f48 Menambah baris baru di file3.txt
14d0e57 Menambah file3.txt
095e517 Menambah file2.txt
56357c9 Menambah file1.txt

git log --oneline --graph

git show <hash>
git show 1092352

git diff 56357c9 HEAD
git diff 1092352 HEAD
git diff 14d0e57 1092352

git reset --soft 6c21349
git reset --soft 67eb55d

git reset --mixed 6c21349
git reset --mixed 67eb55d

git reset --hard 6c21349
git reset --hard 67eb55d

git commit --amend -m "Menambah file3.txt sebanyak 2 baris"

git checkout 8016f48 -- file1.txt
git checkout master
git branch --show-current

git revert <hash>

git blame file1.txts
git show 95757c14

git config --global alias.logone "log --oneline"
git config --global alias.loggraph "log --oneline --graph"
```

# Git Branching
```
git branch --show-current

git branch develop
git branch --list
git switch develop
git branch -m development #Mengubah Nama Branch

git switch master
git branch -d development
git branch --delete development

git branch feature/1
git checkout feature/1
git log --oneline --graph

git checkout master
git merge feature/1
git merge --abort

* 9e280d3 (HEAD -> feature/c) Feature C - file4
* 2db226d Feature C - file3
* 3625ec2 Feature C - file2
* ab489ac Feature C - file1

git cherry-pick ab489ac
git cherry-pick 2db226d


* 931bba1 (HEAD) Release version 1.0.2
* 1d3ddfb Release version 1.0.1
* 6f05b66 Release version 1.0.0

git tag 1.0.0 6f05b66
git tag 1.0.1 1d3ddfb
git tag 1.0.2 931bba1

git tag -l
git tag --list
git checkout 1.0.0


git tag -d 1.0.1
git tag --delete 1.0.1

git stash push -m "Perubahan feauture d"
git stash list
git stash show 0
git stash apply 0
git stash drop 0
git stash clear

git branch feature/rebase
git checkout feature/rebase
git rebase master
git checkout master
git merge feature/rebase

git branch feature/merge-squash
git checkout master
git merge --squash feature/merge-squash
```

# ignore.txt
```
008f5c5 (HEAD -> master) Revert "Merubah file2.txt menjadi file_2.txt"
d187367 Menambah file3.txt sebanyak 2 baris
67eb55d Merubah file2.txt menjadi file_2.txt
6c21349 Menghapus file3.txt
1092352 Melakukan perubahan di file1.txt dan file2.txt
8016f48 Menambah baris baru di file3.txt
14d0e57 Menambah file3.txt
095e517 Menambah file2.txt
56357c9 Menambah file1.txt

git show <hash>

git diff 56357c9 HEAD
git diff 1092352 HEAD
git diff 14d0e57 1092352

git reset --soft 6c21349
git reset --soft 67eb55d

git reset --mixed 6c21349
git reset --mixed 67eb55d

git reset --hard 6c21349
git reset --hard 67eb55d

git checkout 8016f48 -- file1.txt

git branch --show-current

git revert <hash>

git blame file1.txt
```