==1 - Git Commit==
Setup Git
trỏ vào thư mục => sau đó gõ git init.
*Noted*
Khi tạo một project mới thì người ta thường tạo ra một file README.md để cho mọi người biết project này có tác dụng gì.
- git status dùng để cho biết là có file nào thay đổi chưa được check (mới tạo hay đã sửa) thể hiện bằng màu đỏ
- dùng git add [File] để chuyển từ màu đỏ sang màu xanh lá
- commit làm một việc là đóng gói những file màu xanh lá thành một object và đặt tên thay đổi bằng một mô tả gì đó. vd git commit -m 'add README file'. Nếu commit thành công sẽ có mã số của commit
- nếu lần đầu xài git thì phải config mới sử dụng commit được. git config --global user.email [Tên email] và git config --global user.name [tên], cái này chỉ làm lần đầu tiên
- sau khi commit thì git status sẽ chuyển thành không có gì thay đổi hết.
==2 - Log, Show, Diff==

`Git Log`
- git log là cho xem lịch sử những commit nào đã được tạo, thứ tự cái cũ ở dưới cái mới ở trên.
`Git show`
- git show thì phải truyền cái id của commit để show nội dung của commit, dấu + màu xanh lá là nội dung commit
`Git add . để thêm tất cả file`
`Git diff`
- git diff để xem nội dung của những file có modified (git status show ra). Ấn chữ q trên bàn phím để thoát ra.
==3 - Các thuật ngữ Working dir, Staging area, Repository==
`Working dir`
- là thư mục đang làm việc
`Staging area`
- khi git add file thì các file thay đổi ở working dir sẽ nằm ở staging area. khi git commit thì những file đang nằm ở staging area sẽ chuyển vào git respository
`Repository`
- là tập hợp các commit, muốn xem thì sử dụng git log.
- gitk để mở một cửa sổ giao diện người dùng để xem những commit
==4 - Checkout, reset ==
`Checkout`
- git checkout -- [tên file] dùng để bỏ thay đổi ra khỏi working dir
`reset`
- git reset HEAD(có thể có hoặc không) [tên file] dùng để bỏ file đang ở staging area ra khỏi 
==5 - Branching & Merging==
`Branching`
- Là tạo nhánh mới trong git.
- git branch là câu lệnh cho biết có nhánh gì, master là nhánh chính, lưu những bản code sẽ được đưa lên server.
- khi làm một project nào đấy, có nhiều trang khác nhau, mỗi khi viết một chức năng nào đấy sẽ làm một nhánh mới để không ảnh hưởng tới nhánh master thì đảm bảo nhánh master là bản hoạt động trơn tru nhất, ít lỗi.
- git checkout -b [tên của branch] vd feature/dog-class  *checkout là chuyển sang nhánh đó làm việc*
- nếu checkout từ nhánh master thì cả branch và master điều trỏ vào thằng cuói cùng, nếu git commit thì thằng master sẽ trỏ vào branch
- git checkout [tên branch] để quay về nhánh đó. master => quay về nhánh master, khi đó sẽ bỏ code ở nhánh branch và code thành master. trường hợp quay về nhánh branch thì sẽ thay đổi code
`Merging`
- git merge động tác kéo những thay đổi từ một branch khác vào branch nào đấy vd kéo từ branch vào master
- bước 1,  check out vào master sau đó git merge branch
- sau đó master và branch sẽ trỏ vào cùng commit
`Delete branch`
- git branch -D [tên branch] xóa branch đi, nên dùng để làm respo sạch sẽ những branch nào không dùng nữa thì bỏ đi
==6 - git reset==
- git reset dùng để redo những commit không vừa ý
`git reset --soft`
- git reset --soft [id commit] sau đó master sẽ nhảy về vị trí commit và trở lại trạng thái trước khi đóng gói (commit) show các file ở trong staging area. 
`git resst --mix`
- git reset --mix [id commit] chuyển về trạng thái các file ở trạng thái working dir, show các file đã thay đổi hoặc mới thêm vào.
`git reset --hard`
- git reset --hard [id commit] bỏ hẳn commit trước đó đi và quay lại trạng thái ở commit được truyền vào, bỏ hẳn các commit trên đường đi.
==7 - git revert ==
- trả lại trạng thái lúc trước, khác với reset ở chỗ là không phải commit mới nhất mà cách vài ngày. nếu dùng git reset thì sẽ xóa commit và những thằng từ nó đến commit hiện tại, còn revert thì sẽ thay đổi những commit từ + thành - và không ảnh hưởng tới những commit sau nó
- git revert [id commit], phương thức này rất là nguy hiểm nên cố gắng tránh sử dụng, nó sẽ tạo ra 1 commit đảo ngược lại commit revert và thay thế nó. Cách tốt nhất là tạo một commit ở trên và sửa những chỗ cần sửa
==8 - .gitignore==
- file này sẽ nằm trong project, mình sẽ tạo ra nó, mục đích là bỏ qua những file mà không muốn commit, không hiển thị ra khi git status.
`chalk là một module tô màu cho giao diện command line vd như khi console.log`
- để sử dụng thì phải cài đặt:
1 - npm init
2 - npm install chalk --save
- thông thường thì sẽ không muốn commit node_modules vì chứa quá nhiều thứ mà sẽ commit package.json vì khi gửi project cho mọi người, chỉ cần package.json, người ta chi cần gõ npm install thì mọi người chỉ cần npm install sẽ cài đặt rất là nhanh
- để tránh commit folder node_modules thì sẽ tạo file .gitignore
`.gitignore`
- chúng ta thêm tên thư mục hoặc tên file muốn tránh commit vào trong file .gitignore, nên ignore file từ khi khi chưa commit bao giờ.
==9 - github==
- khi làm việc từ 2 người trở lên trong cùng 1 project, để trao đổi file cho nhau thì sử dụng github để lưu trữ lịch sử commit chung. 1 người push lên github, người còn lại pull về.
- cộng đồng github có nhiều project hay, đa phần object open source sử dụng github
- lợi ích của việc dùng github là mỗi bài tập thì post 1 repo khác nhau. Khi đi tuyển dụng thì thường đánh giá cao việc làm việc nhiều thông qua github
- những project nào làm cho công ty mang tính bí mật thì không nên xài github hoặc mua tài khoản cho phép dùng private respo hoặc xài những git server khác như gitlab, bitbucket
==10 - git credential==
- dùng để lưu thông tin đăng nhập mỗi lần git push để tránh hỏi đi hỏi lại.
- git config --global credential.helper store => tạo ra một file ./git-credentials lưu trữ thông tin đăng nhập dưới dạng raw text, rất dễ bị lộ thông tin đăng nhập.
-  git config --global credential.helper "cache --timeout=18000" => 18000s = 5h lưu thông tin đăng nhập vào ram, sẽ phải gõ lại sau 5 tiếng.
-  ubuntu google "gnome-keyring" "git ssh"
==11 - Git clone & pull==
- Chưa bao giờ có local respo trên máy thì sử dụng git clone để copy nguyên bản git respo trên github về máy 
- git clone [Đường link respo lấy từ github] copy tất cả commit về máy, lúc này các máy sẽ có lịch sử commit giống nhau
- git pull sẽ lấy những thay đổi sau khi push commit lên server.
==12 - Push a branch==
- để làm việc trong nhóm thì có quy trình làm việc như sau: mỗi công việc nhỏ sẽ tạo một cái branch để làm, sau đó push branch đó lên github để mọi người đều có thể tham gia cùng làm, người quản lý github đó sẽ tạo một pull resquest on github, sẽ có người review code, và cuối cùng là merge vào master.
-  trước khi code phải check out ra khỏi branch master.
-  git push origin [tên branch] dùng để push branch lên respo
==13 - Pull request==
- Chọn new pull resquest (muốn branch ghép vào branch master)trong github, đặt tên cho pull request sao cho có ý nghĩa vd như task này vè vấn đề gì, viết những thông tin cần thiết giải thích về pull resquest muốn làm
- Trong 1 pull resquest có 1 hoặc nhiều commit. Nếu 1 người khác muốn review code thì sẽ click vào pull resquest => files changed => review changes có thể comment ở trong. khi nào xong thì ấn vào finish review => submit review
- Khi nào review xong rồi thì ấn vào Merge pull request thường là người leader project review xong rồi sẽ ấn vào.
==14 - Code review ==
- Review code offline là bên A tải pull request lên, bên B tải code về máy mình và review. Test ở trên github chỉ có thể xem code viết sai hoặc có gọn gàng hay không chứ không thể nào kiểm tra việc chạy có lỗi hay không
- Để những tải những commit đã merge về thì sử dụng git pull
- sử dụng git fetch (git remote -v)  origin [tên của brand pull request] => git checkout [brand] => trường hợp sử dụng npm mà trong .gitignore node_modules thì phải sử dụng lệnh npm install để cài nhưng module còn thiếu sau đó review code, ok hết thì quay lên pull request chọn approved để báo tested, kiểm tra xong rồi nhảy sang master và remove branch đi, để đồng bộ dữ liệu với github thì phải git pull
==15- Resolve conflict sử dụng rebase==
- giải quyết các xung đột giữa các commit.
- Xung đột giữa các commit xảy ra khi cả 2 người đều checkout ra 2 branch khác nhau.
TH1: Thay đổi cùng một file, cùng một dòng
TH2: 1 người xóa file X, 1 người sử file X
- Cách giải quyết: 
`Method 1`
- sử dụng git rebase
- xử lý conflict
- push again with -f
- nguyên tắc xử lý conflict, conflict xảy ra trên branch nào thì người chủ của branch đó phải đi fix.
- kĩ thuật rebase yêu cầu, đang ở branch phải rebase, git rebase master, sửa file đang conflict, git add [file conflict đã sửa], git rebase --continue, git push origin [tên branch] -f nếu nhiều người cùng dùng trên 1 branch thì hạn chế dùng -f vì sẽ thay đổi lịch sử commit trên github, xấu nhất là -f lên master, nếu làm 1 mình ở branch thì không sao.
- phải commit -f vì lịch sử commit đã thay đổi do rebase đã xóa những commit lúc trước
==16 - Resolve conflict sử dụng merge==
`Method 2`
- gộp nhánh master đã cập nhật vào nhánh chức năng
- xử lý conflict
- commit và push
- checkout master, pull về , checkout [branch], git merge master, xử lý file conflict, git add [file conflict đã sửa], git commit => git push origin [branch]
==17 - Next step==
`Contribute to a open-sourced project`
- Fork 1 project về là tạo ra 1 bản copy của 1 project trên account github, sau khi fork về thì sẽ có 1 repo như repo gốc, muốn sửa lỗi thì tạo 1 feature branch để sửa, sau đó tạo pull request cho người chủ repo, sau khi người chủ repo kiểm tra thì sẽ merge branch vào
`README.md`
- Viết theo dạng markdown, thường thể hiện ở trang chủ của repo mình
- Để học markdown => google markdown cheatsheet, markdown online editor, khi test ok rồi thì copy vào file README.md và push 
`Issue tracking`
- Nếu trong quá trình viết gặp bug thì sẽ viết issue để báo người phát triển project để biết lỗi và sửa.
`Trending on github`
- mỗi repo trên github có star đánh giá
`Oh my zsh`
- Tô điểm cho terminal
`GUI tools`
- Google Git GUI Clients vd Source Tree, Git Kraken, Git Desktop
`Learn more about git`
- Google git tutorial
`Learn vim or nano`

