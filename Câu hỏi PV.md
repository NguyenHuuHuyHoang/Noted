- Junior
- Giới thiệu bản thân: Tên tuổi, đã từng học gì, kinh nghiệm làm việc, điểm mạnh điểm yếu, mục tiêu theo đuổi trong ngắn hạn, dài hạn, mong muốn về môi trường làm việc như thế nào ? …

    Hỏi về quá trình làm việc tại cty cũ. Đã từng làm những dự án gì, được học những cái gì. Lí do nghỉ việc là gì ?
    Biết gì về JS ?
    Các kiểu dữ liệu trong JS (phân biệt null và undefined)
    Các kiểu khai báo dữ liệu trong JS (chú ý Var, let, const, phân biệt những khác nhau giữa các kiểu khai báo). Scope la gì, Closure là gì ? (Hoisting...)
    Bất đồng bộ là gì, cơ chế xử lí của JS. Event loop là gì, Call stack là gì hoạt động như thế nào ? So sánh các cách xử lí của JS: callback, promise, async, await…
    Các cách xử lí với mảng. Cách tối ưu để tìm một đối tượng có thuộc tính bất kì trong 1 mảng gồm các đối tượng, xóa một đối tượng được chỉ định trong mảng....
    Các feature trong ES6 là gì ? Arrow function, spread, set, destructring, map, filter, reduce (map, filter, reduce khác gì nhau), Promise, String interpolation, Map, Set, Iterator, For-of, Class…
    Từ khóa “this”, context
    Object, OOP
    Dom, Dom ảo là gì, hoạt động như thế nào
    Life cycle của Vue
    Data binding là gì
    GET, POST là gì, khác nhau như thế nào. Giả sử muốn upload một file thì làm như thế nào
    CSS hidden và display none khác gì nhau. Đã từng dùng SASS bao giờ chưa? Có thể kể tên các convention khi code Html, Css ko?
    Thuật toán tìm kiếm, sắp xếp
    Cấu trúc dữ liệu

    👉Còn đây là bài test của 1 chỗ mình từng pv nhé ae
    (Mình nhớ đc 1 ít với search 1 ít, còn lại là những câu mình chưa trả lời do quên cộng với chưa nghiên cứu kĩ về cái đó)

Note:
- You can answer in Vietnamese
- About programming questions, you can use Pseudo code or any programming language
👉Q1. Name the differences between array and linked list in: storage allocation, the order of the elements, accessing the element, insertion and deletion, searching, memory utilization and memory required.
Array:
Storage allocation: Được cấp phát trong thời gian biên dịch, trước khi chạy chương trình
Order of the elements: Các phần tử lưu trữ liên tiếp
Accessing the element: Truy cập trực tiếp theo index
Insertion and deletion: Chậm hơn vì vị trí bộ nhớ liên tiếp và cố định
Searching: Tìm kiếm nhị phân, tuyến tính
Memory utilization and memory required: Yêu cầu bộ nhớ ít hơn nhưng ko hiệu quả
Link listed:
Storage allocation: Được cấp phát trong thời gian chạy chương trình
Order of the elements: Các phần tử lưu trữ ngẫu nhiên
Accessing the element: Truy cập tuần tự từ vị trí đầu tiên
Insertion and deletion: Nhanh hơn
Searching: tuyến tính
Memory utilization and memory required: Yêu cầu bộ nhớ nhiều hơn nhưng hiệu quả hơn
👉Q2. Given a list of integers, how to check if a number exists in that list?

    Duyệt danh sách, so sánh số đó với các phần tử trong list

👉Q3. What are the differences between Stack and Queue?
Cả hai đều là kiểu dữ liệu tuyến tính
Stack: Nguyên tắc Last in First out, phần tử nào vào cuối cùng được xử lí đầu tiên; Dùng một đầu vào để thêm hoặc xóa dữ liệu; Push và Pop;
Queue: Nguyên tắc First in First out, ai đến trước đc xử lí trước; Dùng 2 đầu để thêm và xóa dữ liệu; Enqueue và Dequeue
👉Q4. Write a function to check for balanced parentheses in an expression. For example:
let isBalanced = (input) => {
let brackets = "[]{}()<>"
let stack = []
for(let bracket of input) {
let bracketsIndex = brackets.indexOf(bracket)
if(bracketsIndex % 2 === 0) {
stack.push(bracketsIndex + 1)
} else {
if(stack.pop() !== bracketsIndex) {
return false;
}
}
}
return stack.length === 0
}
👉Q5. What is the difference between a tree and a graph?
👉Q6. Given a Fibonacci sequence, denoted , that is:
Write a function to calculate .
👉Q7. How do you represent the n-n relationship in a relational database?
👉Q8. What is database normalization? Why should we need to normalize when designs a new database?
👉Q9. What is index used for in databases?

    Dùng để đánh dấu sắp xếp dữ liệu giúp truy vấn dễ dàng hơn

👉Q10. Which of the basic data structures is the most suitable if you need to store the directory structure on your hard drive?

    Tree
    Queue
    Array
    Stack

👉Q11. Descriptive how Merge Sort works?
👉Q12. How do you check an array is sorted?

    Duyệt mảng lần lượt tìm số nhỏ nhất trong mảng. Nếu có một số nào nhỏ hơn số đang duyệt thì mảng chưa đc sort và ngược lại (trường hợp sắp xếp từ nhỏ đến lớn)

👉Q13. What is Hash table? How to handle collision?
👉Q14. Palindrome is a sequence of characters which reads the same backward as forward. eg: abcdcba, madam, 10801
How do you check a given string is palindrome?

    Đảo ngược chuỗi, so sánh từng phần tử của chuỗi đảo ngược với chuỗi ban đầu, giống nhau hết thì là palindrome

👉Q15. Given below undirected graph, what is the shortest path (i.e the least nodes) from Node 1 to Node 8? And explain your answer.
👉Q16. Blue is a lazy professor, so he wants to automate all of his works. He wrote a program that runs every day. The program will scan all his class' students and if today is the end of the month, the program will send grade to their parents. Otherwise, will send grade to his students' email. The following is his program, how could you improve his code?
is_end_month = check_end_month(today)
list_students = get_all_students_by_class('CS')
for student in list_students:
if is_end_month:
grade = get_grade(student)
send_grade_to_email(grade, student.parent_email)
else:
grade = get_grade(student)
send_grade_to_email(grade, student.email)
👉Q17. Given the following table, write a SQL to list all customers' name that has more than 7 orders.
👉Q18. Binary Search Tree, is a node-based binary tree data structure which has the following properties:

    The left subtree of a node contains only nodes with keys lesser than the node’s key.
    The right subtree of a node contains only nodes with keys greater than the node’s key.
    The left and right subtree each must also be a binary search tree.
    There must be no duplicate nodes

Given a binary search tree, implement function to search a given key from the root. The function return the node contains the key, otherwise return NULL. Function: search_bst(root, key)(example BST)