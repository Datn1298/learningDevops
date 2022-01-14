# Version Control with Git
## Basic Concepts of Git
- Git là 1 hệ thống quản lý phiên bản phân tán
- cung cấp cho người dùng kho lưu trữ riêng chứa toàn bộ lịch sử thay đổi

## Setup git repository (remote and local)
- Git global setup
	- git config --global user.name "username"
	- git config --global user.email mail

## Working with Git (git status, git commit, git add, git push)
1. Git status
- Kiểm tra trạng thái của các file trong các thư mục làm việc
- Cú pháp:
	- Kiểm tra tất cả: git status
	- Kiểm tra trong folder cụ thể: git status folder_name
2. Git add
- Dùng để đưa 1 tập tin vào Staging Area
- Cú pháp:
	- Thêm 1 file cụ thể: git add file_name
	- Thêm tất cả các file: git add all
3. Git commit
- Commit: Git lưu lại 1 snapshot của các sự thay đổi trong thư mục làm việc
- Các file, thư mục đã thay đổi phải ở trong Staging Area
- Cú pháp:
	- git commit -m "msg"
	- git commit -F path_to_file
4. Git log
- Hiện thị lịch sử commit
- Cú pháp
	- git log
5. Git diff
- Hiển thị thông tin thay đổi
	- Khi có sự thay đổi của thư mục làm việc mà chưa chỉ mục, xem sự thay đổi cú pháp với commit gần nhất:
		- Cú pháp: git diff
	- Kiểm tra sử thạt đổi của staging
		- Cú pháp: git diff --staged
	- Kiểm tra thay đổi giữa 2 commit
		- Cú pháp: git diff commit1 commit2
	- Kiểm tra thay đổi của 2 nhánh
		- git diff branch1 branch2
6. Git reset
- Huỷ commit cuối cùng
	- Cú pháp: git reset --soft HEAD~1
- Nếu đã dùng lệnh git add để cập nhật thay đổi vào vùng staging, có thể hủy thao tác này bằng cách thực hiện lệnh
	- Cú pháp: git reset
4. Git pull
- Pull requests thể hiện các đề xuất thay đổi cho nhánh chính
- Lệnh git pull được sử dụng để thêm các thay đổi vào nhánh chính
- Cú pháp
	- git pull <:remote:> <:branch:>
5. Git push
- Cập nhật các nhánh với những thay đổi mới nhất mà bạn đã commit
- Cú pháp:
	- git push

## Initialize Git project locally
1. Tạo 1 git project locally
- Cú pháp:
	- git init project_name
2. Copy 1 git repository từ remote source
- Cú pháp:
	- git clone clone_git_url
3. Fork
- là bản sao của 1 repo

## Concept of Branches
## Merge Requests
## Deleting Branches
## Avoiding Merge Commits (rebase)
## Resolving Merge Conflicts
## Don't track certain files (.gitignore)
## Save work-in-progress changes (git stash)
## Going back in history (git checkout)
## Undoing commits (git revert, git reset)
## Merging Branches
## Git for DevOps
