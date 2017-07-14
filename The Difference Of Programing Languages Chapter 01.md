# I. So Sánh hai ngôn ngữ C++ và Java
## a. Sự khác nhau về quá trình biên dịch thông dịch
+ Java là ngôn ngữ lập trình thông dịch (interpreted language). Trên Java khi thực thi chương trình thì mã nguồn được biên dịch bởi IDE (ví dụ: Netbean, Eclipse, ...) thành một mã trung gian (java bytecode) -> Sau đó các mã trung gian sẽ được JVM (chạy nền trên những nền tảng cụ thể) biên dịch.

+ C++ là ngôn ngữ lập trình biên dịch (compiled language). là ngôn ngữ có mã nguồn được trình biên dịch (ví dụ Visual Studio), biên dịch sang binary code (chứa trong các tập tin .exe hoặc là .dll. Sau đó hệ điều hành sẽ  thực thi các file .dll và .exe.

**Từ đặc điểm trên:** **C++** có lợi thế về tốc độ vì không thông qua quá trình thông dịch sang mã trung gian. Tuy nhiên nó bị hạn chế về mặt nền tảng đó là chị chạy trên nền tảng Window. Ngược lại **Java** mục tiêu ban đầu khi ra mắt được gắn với câu giới thiệu là *WORA* (Write once, run anywhere) để phản ánh những lợi ích về đa nền tảng, điều mà **C++** không có được. Vì những lợi ích về cross-platform mà tốc độ của nó sẽ bị hạn chế hơn.

## b. So sánh OOP giữa Java và C++
| Đặc điểm                      | C++                   | Java                  |
| ----------------------------- |-----------------------|-----------------------|
| **Ngôn ngữ thuần Hướng đối tượng**| Không phải là ngôn ngữ thuần hướng đối tượng | Là ngôn ngữ thuần hướng đối tượng, mọi thành phần của nó thuộc về Class|
| **Access Modifier**   | Là public, private, protected. Nếu không khai báo Access Modifier thì nó được setting là private. Riêng với protected thì phương thức, biến được truy cập trong lớp định nghĩa nó và các lớp kế thừa nó.|Ngoài 3 phạm vi của C++ Java có thêm defauft nghĩa là được truy cập bên trong package. Nếu không khai báo Access Modifier thì nó được mặc định là defauft. Với phạm vi protected nó còn bị giới hạn bởi package là bên ngoài package thì chỉ có lớp con được truy cập, bên trong package thì được truy cập.|
| **Operator Overloading** | Có thể nạp chồng các toán tử  += -= *= /= >> <<.   |Java không cho phép nạp chồng toán tử mà chỉ được sử dụng phép cộng chuổi "str = strA + strB".|
|**Hổ trợ lớp thuần túy ảo**|**Có hỗ trợ lớp thuần ảo**|**Không hỗ trợ lớp thuần ảo**|
|**Lớp ảo(trừu tượng)**|Được nhận biết khi các phương thức được khai báo với từ  khóa virtual. |Một Abstract Class được định nghĩa khi class đó được gán từ khóa abstract ở đầu class.|
|**Hổ trợ Interface**| Không hổ trợ interface tuy nhiên có thể giả một lớp tương tự Interface bằng một lớp ảo.|Được hổ trợ sử dụng Interface trong thiết kế Hướng đối tượng.|
|**Đa kế thừa**| Ở C++ được hổ trợ đa kế thừa, nghĩa là một lớp lớp có thể kế thừa được từ nhiều lớp.|Với Java thì không được hổ trợ đa kế thừa. Một lớp chỉ được kế thừa từ một Lớp nhưng khác với C++ là nó được hổ trợ Interface nên nó có thể implement nhiều Interface.|
|**Lớp không thể kế thừa**|Một khi có một lớp được tạo ra, thì các lớp con đều có thể kế thừa nó|Với Java, khi đánh dấu bằng từ khóa *final* ở đầu class thì lớp đó không được kế thừa|
|**Lớp Cha của mọi lớp**| Với một lớp được tạo ra mà không kế thừa bất kì lớp nào khác thì lớp này không có lớp Cha nền định nghĩa trên không tồn tại với C++|Tuy nhiên, với ngôn ngữ Java vì nó là ngôn ngữ thuần hướng đối tượng nên nó tồn tại lớp Object là lớp cha của tất cả mọi lớp.|
|**Tổ chức Class**|C++ có tổ chức lớp gọn gàng hơn, bởi phần khai báo và định nghĩa các method có thể được tách ra 2 tập tin .cpp và .h|Toàn bộ khai báo và định nghĩa phải gói gọn trong 1 class trong 1 tập tin .java|
|**Abstract Method**|Được định nghĩa với từ khóa virtual trước method|Abstract Method được định nghĩa với từ khóa abstract ở đầu method và những method này thì không có định nghĩa trong thân hàm.|
|**Định nghĩa không gian tên**|Được định nghĩa bằng các khai báo namespace "Name"{ Khai báo lớp}| Trong Java Namespace chính là tên của package chứa class đó.|
|**Hàm chính**|Hàm main không thuộc bất cứ lớp nào cả.| Hàm main thuộc một class|
|**Hàm hủy**|Trong C++, phải gọi hàm hủy để dọn dẹp bộ nhớ. Để tối ưu bộ nhớ đòi hỏi sự tỉ mỉ khi gọi hàm này| Java có GC, bộ thu dọn rác => Java tối ưu về bộ nhớ hơn C++|
|**Hàm khởi tạo**| Không cho phép gọi hàm khởi tạo của lớp này trong lớp khác|Cho phép gọi hàm khởi tạo của một lớp trong một lớp khác|

**Kết luận:** 
Qua các so sánh về tính chất hướng đối tượng của hai ngôn ngữ trên, thì chúng ta có thể sử dụng được các Design Pattern cho phù hợp với mục đích của chương trình.

## c. So sánh về kiểu dữ liệu.
+ Trong Java tồn lại 2 loại kiểu dữ liệu đó là: kiểu dữ liệu cơ sở (Primitive Data Type) và kiểu dữ liệu tham chiếu (Reference Data Type ).
    - Kiểu dữ liệu cơ sở bao gồm:  byte, short, int, long, float, double, boolean, char.
    - Kiểu dữ liệu tham chiếu bao gồm các kiểu dữ liệu còn lại.
+ Trong C++ chỉ tồn tại kiểu dữ liệu cơ sở và KDL con trỏ.
+ Điểm chung đó là đều có kiểu dữ liệu do người dùng định nghĩa

**Tính bảo mật của dữ liệu:**
 Java không hổ trợ truy cập bộ nhớ trực tiếp. Tất cả phải thông qua phương thức của lớp  và không có  phương thức nào có thể thay đỗi giá trị của một tham chiếu được định sẳn.
 C++ hổ trợ truy cập bộ nhớ trực tiếp thông qua con trỏ. Có thể thay đỗi giá trị trực tiếp của biến tham chiếu
 
 Vậy nên: với việc không hổ trợ truy cập bộ nhớ trực tiếp của Java thì làm tăng tính bảo mật cho dữ liệu hơn.

**Tại sao Java lại không dùng con trỏ?**

Ví dụ với C++ ta khai báo một mảng 2 phẩn tử. Tại thời điểm khi chưa khởi tạo giá trị cho mảng nhưng ta vẫn có thể truy xuất dến bất kì phần tử nào của mảng. Tức là truy xuất vượt quá kích thước mảng đẫ khai báo.

**Dấn đến:**
 Người lập trình phải kiểm soát được các con trỏ đã khai báo để không bị ảnh hưởng đến chương trình bởi các kết quả sai lệch hoặc là các lỗi tràn bộ nhớ. Với Java sau khi loại bỏ  con trỏ và dùng các biến tham chiếu. Nếu khai báo một mảng n phần tử thì ta không thể truy xuất ra được ngoài vùng đã khai báo. Khi truy xuất vượt giới hạn như vậy thì complier sẽ throw exception.

# II. So sánh ReactJS và Vue.js
## 1. ReactJS và Vue.js là gì?
**ReactJS** là một thư viện JavaScript dùng để xây dựng giao diện người dùng. Và mục tiêu chính của nó là xử lí user interface trong các ứng dụng. Tính năng quan trọng và có giá trị nhất của ReactJS đó là khả năng xây dựng các add-ons, các add-ons này có thể tự cập nhật thay vì phải reload các trang bổ sung. ReactJS hướng tới môi trường native, cho sự linh hoạt về giao diện ở nhiều situations và environments.
**Vue.js** là một progressive framework dùng để xây dựng giao diện người dùng. Đặc biệt là Vue.js 2.0 cũng đang hướng tới môi trường native. Tuy nhiên nó vẫn chỉ đang tập trung vào Web development. Vue.js hướng tới View-Model Layer trên mẫu MVVM.

## 2. Điểm giống nhau của 2 ngôn ngữ này
+ Sử dụng Virtual DOM (Virtual DOM là một đối tượng có chứa các thông tin để tạo ra một Actual DOM).
+ Cung cấp các View components có thể reactive và compose được. Nghĩa là các view sẽ thay đỗi tùy theo những hoàn cảnh khác nhau
+ Tập trung vào các thư viện quan trọng vì các thư viện đồng hành đã quản lý routing và global state.

## 3. Điểm mạnh và điểm yếu của chúng?
### a. Điểm mạnh và yếu của ReactJS.
+ ĐIỂM MẠNH
    + React sử dụng JSX cho phép trộn code JavaScript và HTML. Ta có thể đưa code HTML vào trong hàm render để mà nó chuyển đỗi các đoạn HTML trong đó thành đối tượng HTML, nói một cách cụ thể là ta có thể viết HTML trong JavaScript.
    + Có nhiều công cụ hổ trợ phát triển đặc biết là Chrome được tích hợp React để cho việc debug diễn ra dễ dàng hơn nhờ đó Virtual DOM có thể quan sát được một cách chi tiết hơn như là một Actual DOM.
    + Có thể render ở Server: Tối ưu hóa thời gian tải trang. Vì ReactJS là một thư viện component nên nó có thể render ở ngoài Browser sử dung DOM và cũng có thể render bằng các chuổi HTML mà server trả về.
    + Hiệu năng cao với các ứng dụng có dữ liệu thay đỗi liên tục.
    + Một lợi ích chính khác của ReactJS và hệ sinh thái của nó đó là: React Native - các product độc lập cho phép tạo giao diện người dùng đa nền tảng trên các ứng dụng di động đòi hỏi những thay đỗi phải ứng(react) để phù hợp với nền tảng đang chạy (tính Native).
+ ĐIỂM YẾU
    + ReactJS chỉ phục vụ cho tâng View vì nó chỉ là một View Library cho nên nó không có phần Model và Controller. Nên nó phải kết hợp với những Framework khác để xây dựng một ứng dụng hoàn chỉnh. Vì vậy phát triển một ứng dụng chỉ riêng ReactJS là rất khó.
    + ReactJS không có 2-way-binding.
    + Khi tích hợp ReactJS vào các Framework sử dụng MVC thì phải tái cấu trúc.
    + ReactJS nặng so với những Framework khác cụ thể là AngularJS.
    + Tài liệu hướng dẫn phức tạp và khó cho những người mới làm quen.

### b. Điểm mạnh và yếu của Vue.js
+ ĐIỂM MẠNH: 
    + Dễ dàng để phát triển.
    + Two-way communication tương tự với AngularJS. Trên Vue.js thì thuận lợi tăng tốc độ xử lý các block HTML. Kiến trúc của Vue.js làm nó có khả năng thao tác các luồng một chiều đây là điều quan trọng để xử lý các component.
    + Khả năng kiểm soát trạng thái. Cụ thể là Vue.js cho phép theo dõi sự thay đỗi của giao diện theo thời gian thực, Vue.js control thực hiện thông qua các phương thức props() và data() của class.
    + Vue.js có một quy trình xử lí tư duy theo tự nhiên. Nó được viết theo những nguyên lý tư duy theo kiểu con người. Không như những ngôn ngữ khác luôn bị theo khuôn khổ máy móc.
    + Vue.js nhẹ và có hiệu suất cao hơn ReactJS và AngularJS.
    + Vuex library giúp cho khả năng mở rộng ứng dụng tốt trên Vue.js. Tuy nhiên, yếu tố về khả năng mở rộng của một ứng dụng phụ thuộc nhiều vào xây dựng cấu trúc ứng dụng hơn là chỉ phụ thuộc vào những thư viện ở tầng View như là react hay vue.
    + Dễ dàng để sử dụng, thời gian để làm quen với Vue thì nhanh và dễ dàng hơn những Framework khác, điển hình như là AngularJS. 
+ ĐIỂM YẾU:
    + Cộng đống đang còn nhỏ, nhưng nó đang phát triển. Cho nên những tài nguyên được đóng góp vào đang còn ít so với những cộng đồng khác.
## 4. Cân nhắc lựa chọn giữa Vue.js và ReactJS
Với những điểm tương đồng của những tính năng và khả năng mà cả 2 đem lại. Tuy nhiên để có những khả năng đó thì chúng thực hiện với những cách khác nhau.

ReactJS so với Vue.js thì có độ phổ biến cao hơn, nhiều doanh nghiệp đã lựa chọn nó là giải pháp. Tuy nhiên hiện nay, nhiều lập trình viên đang cân nhắc việc sự dụng Vue.js thay cho ReactJS với AngularJS.

So với Vue.js thì React.js khó học hơn vì những thuật ngữ cho một số định nghĩa trong React.js còn gây khó khăn cho người học và điều này của React.js lại không thân thiện được như Vue.js.

Vue.js cũng có State Management là Vuex  tương tự như Redux (là một thư viện JavaScript được xây dựng trên ngôn ngữ Elm và kiến trúc Flux do Facebook giới thiệu) kết hợp với ReactJS.

Điểm mạnh khác của Vue.js so với ReactJS đó là tài liệu hướng dẫn chi tiết dễ hiểu hơn.





