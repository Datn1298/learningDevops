# Version Control with Git
## Basic Concepts of Git
- Git là 1 hệ thống quản lý phiên bản phân tán
- cung cấp cho người dùng kho lưu trữ riêng chứa toàn bộ lịch sử thay đổi

## Setup git repository (remote and local)
1 Git global setup
```
$ git config --global user.name "username"
$ git config --global user.email mail
```

## Working with Git (git status, git commit, git add, git push)
1. Git status
- Kiểm tra trạng thái của các file trong các thư mục làm việc
````
# Kiểm tra tất cả
$ git status

# Kiểm tra trong folder cụ thể
$ git status folder_name
````

2. Git add
- Dùng để đưa 1 tập tin vào Staging Area
````
# Thêm 1 file cụ thể: 
$ git add file_name

# Thêm tất cả các file: 
$ git add all
$ git add .
````

3. Git commit
- Commit: Git lưu lại 1 snapshot của các sự thay đổi trong thư mục làm việc
- Các file, thư mục đã thay đổi phải ở trong Staging Area
````
$ git commit -m "msg"
$ git commit -F path_to_file
````

4. Git reset
````
# Huỷ commit cuối cùng
$ git reset --soft HEAD~1
````
- Nếu đã dùng lệnh git add để cập nhật thay đổi vào vùng staging, có thể hủy thao tác này bằng cách thực hiện lệnh
````
$ git reset
````

5. Git pull
- Lấy về thông tin từ remote và cập nhật vào các nhánh của local repo.
````
$ git pull <:remote:> <:branch:>
````
- git pull = git fetch + git merge

6. Git fetch
- Lấy về thông tin từ remote, chưa tích hợp thay đổi của local repo
````
$ git fetch 
````

7. Git push
- Để đẩy các commit mới ở local repo lên remote repo
````
$ git push
````

## Review history
1. Git log
- Hiện thị lịch sử commit
````
git log
````

2. Git diff
- Hiển thị thông tin thay đổi
	- Khi có sự thay đổi của thư mục làm việc mà chưa chỉ mục, xem sự thay đổi cú pháp với commit gần nhất:
````
$ git diff
````
	- Kiểm tra sử thạt đổi của staging
````
$ git diff --staged
````
	- Kiểm tra thay đổi giữa 2 commit
````
$ git diff commit1 commit2
````
	- Kiểm tra thay đổi của 2 nhánh
````
$ git diff branch1 branch2
````

3. Git show

## Initialize Git project locally
1. Tạo 1 git project locally
````
$ git init project_name
````
2. Copy 1 git repository từ remote source
````
$ git clone clone_git_url
````
3. Fork
- là bản sao của 1 repo

## Branches
1. Liệt kê các branches
````
$ git branch
````

2. Tạo branch mới
```` 
$ git branch branch_name
````

3. Chuyển branch
````
$ git checkout branch_name
````

4. Xoá branch
````
$ git brach -d branch_name
````

5. Merge request
- Khi chuyển qua nhánh khác, nên tạo merge request ngay khi có commit đầu tiên
- Git Merge
	- Sử dụng merge sẽ tạo ra 1 commit mới kết hợp từ 2 commit cuối cùng của 2 nhánh
	- Log commit sẽ ko bị thay đổi và thứ tự commit sẽ được sắp xếp theo thứ tự thời gian
````
$ git merge branch_name
````
- Git Rebase
	- Sử dụng Rebase sẽ đưa toàn bộ nhánh đang sử dụng lên đầu nhánh master
	- Log commit sẽ bị thay đổi theo
````
$ git rebase branch_name
````

## Concept of Branches
## Resolving Merge Conflicts
## Don't track certain files (.gitignore)
## Save work-in-progress changes (git stash)
- Dùng cho trường hợp: khi trong quá trình làm việc
	- đang sử dụng nhánh A, mà phải qua nhánh B để sửu lỗi
	- k muốn thực hiện commit dư thừa
- Git stash cho phép lưu những thay đổi mà k cần thiết phải commit
	- dễ dàng chuyển sang nhánh khác mà k mất code
````
# Đưa toàn bộ vào staged
$ git add .

# Sử dụng stash để thay đổi mà k cần commit:
$ git stash # hoặc git stash save

# Xem lại các thay đổi đã lưu
$ git stash list

# Để lấy lại thay đổi được lưu trong danh sách:
$ git stash apply "stash@{n}"

# Để lấy lại thay đổi gần nhất và xoá lần lưu trước đó: 
$ git stash pop

# Để xoá 1 lần lưu chỉ định
$	git stash drop "stash@{n}"

# Để xoá tất cả
$ git stash clear
````

## Git for DevOps
