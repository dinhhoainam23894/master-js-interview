
[Source](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0 "Permalink to Master the JavaScript Interview: What is Functional Programming?")

# Bậc thầy về phỏng vấn Javascript : Lập trình chức năng là cái gì ?

![][1]

Cấu trúc Synth - Orihaus (CC BY 2.0)

> "Bậc thầy về phỏng vấn Javascript"" là  tuyển tập các bài đăng được thiết kế nên để dành cho các ứng cữ viên các câu hỏi thông thường mà họ sẽ gặp khi apply một vị trí ở trình độ từ cấp trung đến cấp cao về lĩnh vực Javascript. Đây là những câu hỏi mà tôi thường xuyên sử dụng trong phỏng vấn thực tế.

Lập trình chức năng đã trở thành chủ đề thực sự nóng trong thế giới Javascript. Ở thời điểm vài năm trước , một vài lập trình viên Javascript thậm chí còn không biết lập trình chức năng là gì , nhưng ở mức độ codebase ứng dụng lớn hơn tôi đã nhìn thấy 3 năm trước sự mạnh mẽ khi sử dụng các ý tưởng lập trình chức năng.

** Lập trình chức năng** (viết tắt là FP) là quá trình xây dựng phần mềm bởi composing is the process of building software by composing ** functions gốc**, Tránh **các trạng thái được chia sẻ,** **dữ liệu có thể thay đổi**  và **side-effects**.Lập trình chức năng là **declarative** thay vì **imperative**, và các trạng thái ứng dụng đi qua các hàm chính.Trái ngược với lập trình hướng đối tượng , nơi mà các trạng thái ứng dụng thường xuyên được chia sẻ và  sắp đặt với các method trong đối tượng.

Lập trình chức năng là một **mô hình lập trình**, có nghĩa nó là một cách suy nghĩ về xây dựng phần mềm dựa trên một số nguyên tắc cơ bản, xác định rõ (được liệt kê ở trên). Các ví dụ khác về mô hình lập trình bao gồm lập trình hướng đối tượng và lập trình thủ tục.

Code chức năng có xu hướng ngắn gọn hơn, dễ dự đoán hơn và dễ kiểm tra hơn code imperative hoặc đối tượng - nhưng nếu bạn không quen với nó và các mẫu phổ biến liên kết với nó, mcodechức năng cũng có thể dày đặc hơn và tài liệu liên quan có thể không thể hiểu được đối với người mới .

Nếu bạn bắt đầu tìm kiếm trên google các điều khoản lập trình chức năng, bạn sẽ nhanh chóng đâm đầu vào một bức tường có thể rất đáng sợ cho người mới bắt đầu. Để nói rằng nó có một cách học nhanh chóng thì đó là một lời nói dối. Nhưng nếu bạn đã lập trình JavaScript trong một thời gian, rất có thể bạn đã sử dụng rất nhiều khái niệm và tiện ích lập trình chức năng trong phần mềm thực tế của bạn.


> Đừng để tất cả những từ mới làm bạn sợ hãi. Nó dễ hơn so với vẻ bề ngoài.
os
Phần khó nhất là tất cả các từ vựng không quen thuộc. Có rất nhiều ý tưởng trong định nghĩa tìm kiếm vô nghĩa ở trên mà tất cả mọi thứ cần phải được hiểu trước khi bạn có thể bắt đầu nắm bắt ý nghĩa của lập trình chức năng:

* Pure functions
* Function composition
* Avoid shared state
* Avoid mutating state
* Avoid side effects

Nói cách khác, nếu bạn muốn biết những gì có nghĩa là lập trình chức năng trong thực tế, bạn phải bắt đầu với một sự hiểu biết về những khái niệm cốt lõi.

**pure function** là một hàm:
* Với cùng các yếu tố đầu vào, luôn trả về cùng một đầu ra, và
* Không có side-effects

Pure functions có nhiều thuộc tính quan trọng trong lập trình chức năng, bao gồm **referential transparency** (bạn có thể thay thế một cuộc gọi hàm với giá trị kết quả của nó mà không thay đổi ý nghĩa của chương trình). Đọc “Pure functions là gì?” Để biết thêm chi tiết.

** Function composition ** là quá trình kết hợp hai hoặc nhiều hàm để tạo ra một hàm mới hoặc thực hiện một số tính toán. Ví dụ, thành phần f. g (dấu chấm có nghĩa là "được tạo thành") tương đương với f (g (x)) trong JavaScript. Hiểu biết về thành phần hàm là một bước quan trọng hướng tới sự hiểu biết cách phần mềm được xây dựng bằng cách sử dụng lập trình chức năng. Đọc “Function composition là gì?” Để biết thêm.

### Tránh trạng thái chia sẻ

**Tránh trạng thái chia sẻ** là các biến, đối tượng hoặc không gian bộ nhớ nào tồn tại trong một scope chia sẻ hoặc là thuộc tính của một đối tượng được truyền giữa các scope. Một scope chia sẻ có thể bao gồm pope toàn cục hoặc phạm vi closure. Thông thường, trong lập trình hướng đối tượng, các đối tượng được chia sẻ giữa các scope bằng cách thêm các thuộc tính cho các đối tượng khác.

Ví dụ, một trò chơi máy tính có thể có một đối tượng trò chơi chính, với các nhân vật và các mục trò chơi được lưu trữ dưới dạng các thuộc tính thuộc sở hữu của đối tượng đó. Lập trình chức năng tránh trạng thái chia sẻ - thay vào đó dựa vào cấu trúc dữ liệu không thay đổi và tính toán thuần túy để lấy dữ liệu mới từ dữ liệu hiện có. Để biết thêm chi tiết về cách phần mềm chức năng có thể xử lý trạng thái ứng dụng, hãy xem “10 mẹo cho kiến ​​trúc Redux tốt hơn”.

Vấn đề với shared state là để hiểu được tác động của một hàm, bạn phải biết toàn bộ lịch sử của mọi biến chia sẻ mà hàm sử dụng hoặc tác động.

Hãy tưởng tượng bạn có một đối tượng người dùng cần lưu. Hàm saveUser () của bạn tạo một yêu cầu tới một API trên máy chủ. Trong khi điều đó đang xảy ra, người dùng thay đổi ảnh tiểu sử của họ bằng updateAvatar () và kích hoạt một yêu cầu saveUser () khác. Khi lưu, máy chủ sẽ gửi lại một đối tượng người dùng chuẩn để thay thế bất kỳ thứ gì trong bộ nhớ để đồng bộ hóa với các thay đổi xảy ra trên máy chủ hoặc để đáp ứng các cuộc gọi API khác.

Thật không may, phản hồi thứ hai nhận được trước phản hồi đầu tiên, vì vậy khi phản hồi đầu tiên (hiện đã hết hạn) được trả về, ảnh hồ sơ mới bị xóa sổ trong bộ nhớ và được thay thế bằng ảnh cũ. Đây là một ví dụ về race condition - một lỗi rất phổ biến liên quan đến trạng thái được chia sẻ.

Một vấn đề phổ biến khác liên quan đến share state là việc thay đổi thứ tự mà các hàm được gọi có thể gây ra một loạt các lỗi vì các hàm hoạt động trên trạng thái chia sẻ phụ thuộc vào thời gian:

Ví dụ về thời gian phụ thuộc

Khi bạn tránh shared state , thời gian và thứ tự của các cuộc gọi hàm không thay đổi kết quả của việc gọi hàm. Với các pure functions,được cung cấp cùng một đầu vào, bạn sẽ luôn nhận được cùng một đầu ra. Điều này làm cho các cuộc gọi hàm hoàn toàn độc lập với các cuộc gọi hàm khác, có thể đơn giản hóa triệt để các thay đổi và tái cấu trúc. Thay đổi trong một chức năng hoặc thời gian của cuộc gọi chức năng sẽ không gợn sóng và phá vỡ các phần khác của chương trình.

Trong ví dụ trên, chúng ta sử dụng Object.assign () và truyền vào một đối tượng rỗng làm tham số đầu tiên để sao chép các thuộc tính của x thay vì thay đổi nó tại chỗ. Trong trường hợp này, nó sẽ tương đương với việc tạo một đối tượng mới ngay từ đầu, không có Object.assign (), nhưng đây là một mẫu phổ biến trong JavaScript để tạo ra các bản sao của trạng thái hiện tại thay vì sử dụng các đột biến.Ví dụ.

Nếu bạn nhìn kỹ vào các câu lệnh console.log () trong ví dụ này, bạn sẽ thấy một điều tôi đã đề cập: hàm hợp.Nhắc lại phần trước , hàm hợp trông giống như sau: f (g (x)). Trong trường hợp này, chúng ta thay thế f () và g () bằng x1 () và x2 () cho thành phần: x1. x2.

Tất nhiên, nếu bạn thay đổi thứ tự của bố cục, đầu ra sẽ thay đổi. Thứ tự của các hoạt động vẫn còn quan trọng. f (g (x)) không phải lúc nào cũng bằng g (f (x)), nhưng những gì không quan trọng nữa là những gì xảy ra với các biến bên ngoài hàm - và đó là một vấn đề lớn. Với hàm số không chuẩn chỉnh, bạn không thể hiểu đầy đủ chức năng của một hàm trừ khi bạn biết toàn bộ lịch sử của mọi biến mà hàm sử dụng hoặc ảnh hưởng.

Xóa phụ thuộc thời gian cuộc gọi chức năng và bạn loại bỏ toàn bộ lớp lỗi tiềm ẩn.

### Tính bất biến

Đối tượng bất biến là đối tượng không thể sửa đổi sau khi được tạo. Ngược lại, đối tượng khả biếnlà bất kỳ đối tượng nào có thể được sửa đổi sau khi được tạo.

Tính bất biến là một khái niệm trung tâm về lập trình chức năng bởi vì không có nó, luồng dữ liệu trong chương trình của bạn bị mất. Lịch sử tiểu bang bị bỏ rơi và các lỗi lạ có thể xâm nhập vào phần mềm của bạn. Để biết thêm về tầm quan trọng của bất biến, hãy xem "Đạo của bất biến."

Trong JavaScript, điều quan trọng là không nhầm lẫn const, với bất biến. const tạo ra một ràng buộc tên biến mà không thể được gán lại sau khi tạo. const không tạo ra các đối tượng bất biến. Bạn không thể thay đổi đối tượng mà ràng buộc đề cập đến, nhưng bạn vẫn có thể thay đổi các thuộc tính của đối tượng, điều đó có nghĩa là các ràng buộc được tạo bằng const là có thể thay đổi,không phải là bất biến.

Đối tượng bất biến không thể thay đổi được. Bạn có thể làm cho một giá trị thực sự bất biến bằng cách đóng băng đối tượng. JavaScript có một phương thức đóng băng chiều sâu đối tượng:

Nhưng các đối tượng đóng băng chỉ là không thay đổi bề ngoài. Ví dụ, đối tượng sau đây có thể thay đổi:

Như bạn có thể thấy, các thuộc tính nguyên thủy cấp cao nhất của một đối tượng đóng băng không thể thay đổi, nhưng bất kỳ thuộc tính nào cũng là một đối tượng (bao gồm mảng, vv…) vẫn có thể bị biến đổi , vì vậy ngay cả đối tượng đđóng băng cũng không thay đổi trừ khi bạn duyệt toàn bộ cây đối tượng và đóng băng mọi thuộc tính đối tượng.

Trong nhiều ngôn ngữ lập trình chức năng, có cấu trúc dữ liệu bất biến đặc biệt gọi là cấu trúc dữ liệu trie (được phát âm là “cây”) được đóng băng sâu - nghĩa là không có thuộc tính nào có thể thay đổi, bất kể mức độ của thuộc tính trong hệ thống phân cấp đối tượng.

Các phép thử sử dụng **structural sharing** để chia sẻ các vị trí bộ nhớ tham chiếu cho tất cả các phần của đối tượng không thay đổi sau khi một đối tượng được sao chép bởi một toán tử, sử dụng ít bộ nhớ hơn và cho phép cải thiện hiệu suất đáng kể cho một số loại hoạt động.

Ví dụ, bạn có thể sử dụng so sánh nhận dạng tại gốc của cây đối tượng để so sánh. Nếu danh tính giống nhau, bạn không phải duyệt cả cây để kiểm tra sự khác biệt.

Có một số thư viện trong JavaScript tận dụng các cries , bao gồm Immutable.js và Mori.

Tôi đã thử nghiệm cả hai, và có xu hướng sử dụng Immutable.js trong các dự án lớn đòi hỏi một lượng đáng kể trạng thái bất biến. Để biết thêm về điều đó, hãy xem “10 mẹo cho kiến ​​trúc Redux tốt hơn”.


### Side Effects

Một side effect là bất kỳ thay đổi trạng thái ứng dụng nào có thể quan sát được bên ngoài hàm được gọi ngoài giá trị trả về của nó. Các tác dụng phụ bao gồm:

* Sửa đổi bất kỳ biến bên ngoài hoặc thuộc tính đối tượng nào (ví dụ: biến toàn cục hoặc biến trong chuỗi phạm vi hàm chính)
* Đăng nhập vào bảng điều khiển
* Ghi ra màn hình
* Ghi vào một file
* Ghi vào mạng
* Kích hoạt bất kỳ quá trình bên ngoài nào
* Gọi bất kỳ chức năng nào khác có side-effects

Side effects phần lớn được tránh trong lập trình hàm, điều này làm cho các hiệu ứng của một chương trình dễ hiểu hơn nhiều và dễ dàng hơn nhiều để kiểm tra.

Haskell và các ngôn ngữ chức năng khác thường xuyên cô lập và đóng gói các side-effect từ các pure functions bằng cách sử dụng monads. Chủ đề của các monads đủ sâu để viết một cuốn sách, vì vậy chúng tôi sẽ lưu lại cuốn sách đó sau này.

Những gì bạn cần biết ngay bây giờ là các tside-effect cần phải được tách biệt với phần còn lại của phần mềm của bạn. Nếu bạn giữ các side-effect tách biệt với phần còn lại của logic chương trình, phần mềm của bạn sẽ dễ dàng hơn để mở rộng, tái cấu trúc, gỡ lỗi, kiểm tra và bảo trì.

Đây là lý do mà hầu hết các frameworks front-end khuyến khích người dùng quản lý hiển thị trạng thái và thành phần trong các mô đun riêng lẻ, tách biệt nhau.

### Khả năng sử dụng lại thông qua các chức năng bậc cao

Lập trình chức năng có xu hướng sử dụng lại một tập hợp các tiện ích chức năng phổ biến để xử lý dữ liệu. Lập trình hướng đối tượng có xu hướng colocate phương pháp và dữ liệu trong các đối tượng. Những phương pháp colocated chỉ có thể hoạt động trên loại dữ liệu mà chúng được thiết kế để hoạt động và thường chỉ có dữ liệu chứa trong cá thể đối tượng cụ thể đó.

Trong lập trình chức năng, bất kỳ loại dữ liệu nào là fair game. Cùng một tiện ích map () có thể ánh xạ đối tượng, chuỗi, số hoặc bất kỳ kiểu dữ liệu nào khác vì nó lấy một hàm làm đối số xử lý thích hợp kiểu dữ liệu đã cho. FP rút ra thủ thuật tiện ích chung của nó bằng cách sử dụng các hàm bậc cao hơn.

JavaScript có các hàm ở lớp đầu tiên, cho phép chúng ta xử lý các hàm như dữ liệu - gán chúng cho các biến, chuyển chúng đến các hàm khác, trả về chúng từ các hàm, v.v ...

Hàm bậc cao hơn là bất kỳ hàm nào nhận hàm làm đối số, trả về hàm hoặc cả hai. Các hàm bậc cao thường được sử dụng để:

* Abstract hoặc cô lập hành động, hiệu ứng hoặc điều khiển luồng không đồng bộ bằng cách sử dụng chức năng gọi lại, promise , monads, v.v.
* Tạo các tiện ích có thể hoạt động trên nhiều loại dữ liệu khác nhau
* Áp dụng một phần chức năng cho các đối số của nó hoặc tạo một hàm được kết hợp với mục đích sử dụng lại hoặc thành phần hàm
* Lấy danh sách các hàm và trả về một số thành phần của các hàm đầu vào đó

#### Containers, Functors, Lists, and Streams

Một functor là cái gì đó có thể được ánh xạ . Nói cách khác, nó là một container có một giao diện có thể được sử dụng để áp dụng một hàm cho các giá trị bên trong nó. Khi bạn thấy từ functor, bạn nên suy nghĩ "có thể điều chỉnh được".

Trước đó chúng ta đã học được rằng cùng một tiện ích map () có thể hoạt động trên nhiều kiểu dữ liệu khác nhau. Nó làm điều đó bằng cách nâng hoạt động ánh xạ để làm việc với một API functor. Các hoạt động kiểm soát lưu lượng quan trọng được sử dụng bởi map () tận dụng giao diện đó. Trong trường hợp của Array.prototype.map (), vùng chứa là một mảng, nhưng các cấu trúc dữ liệu khác cũng có thể là các hàm functors - miễn là chúng cung cấp API ánh xạ.

Hãy xem Array.prototype.map () cho phép bạn trừu tượng kiểu dữ liệu từ tiện ích ánh xạ để làm cho map () có thể sử dụng được với bất kỳ kiểu dữ liệu nào. Chúng ta sẽ tạo một ánh xạ đơn giản () đơn giản để nhân các giá trị được truyền cho 2:

Điều gì sẽ xảy ra nếu chúng ta muốn hoạt động trên các mục tiêu trong một trò chơi để tăng gấp đôi số điểm mà họ giành được? Tất cả những gì chúng ta phải làm là tạo một thay đổi tinh tế cho hàm double () mà chúng ta truyền vào map (), và mọi thứ vẫn hoạt động:

Khái niệm sử dụng các phép trừu tượng như hàm functors và các hàm bậc cao hơn để sử dụng các hàm tiện ích chung để thao tác với bất kỳ số lượng các kiểu dữ liệu khác nhau nào là quan trọng trong lập trình hàm. Bạn sẽ thấy một khái niệm tương tự được áp dụng theo tất cả các cách khác nhau.

> “Danh sách được thể hiện theo thời gian là một luồng.”

Tất cả những gì bạn cần hiểu bây giờ là mảng và functors không phải là cách duy nhất khái niệm container và giá trị trong các container được áp dụng. Ví dụ, một mảng chỉ là một danh sách mọi thứ. Danh sách được thể hiện theo thời gian là luồng - vì vậy bạn có thể áp dụng cùng một loại tiện ích để xử lý luồng sự kiện đến - thứ mà bạn sẽ thấy rất nhiều khi bạn bắt đầu xây dựng phần mềm thực với FP.

### Declarative vs Imperative

Lập trình chức năng là một mô hình khai báo, có nghĩa là logic chương trình được thể hiện mà không mô tả rõ ràng việc kiểm soát luồng.

**Imperative** chương trình dùng các dòng mã mô tả các bước cụ thể được sử dụng để đạt được kết quả mong muốn - **flow control:How** để làm việc .

**Declarative** chương trình trừu tượng quá trình kiểm soát luồng, và thay vào đó dùng dòng mã mô tả **data flow: What**. _how_ được trừu tượng đi

Ví dụ, **imperative** ánh xạ lấy một mảng các số và trả về một mảng mới với mỗi số nhân với 2:

Ánh xạ dữ liệu bắt buộc

**declarative**  thực hiện tương tự, nhưng rút gọn điều khiển luồng bằng cách sử dụng tiện ích Array.prototype.map () chức năng, cho phép bạn thể hiện rõ ràng luồng dữ liệu:

**Imperative** code thường xuyên sử dụng các câu lệnh. Một câu lệnh là một đoạn code thực hiện một số hành động. Ví dụ về các câu lệnh thường được sử dụng bao gồm, nếu, chuyển đổi, ném, v.v ...

**Declarative** code dựa nhiều hơn vào expressions. **expression** là một đoạn mã đánh giá một số giá trị.Expressions thường là một số kết hợp của các cuộc gọi hàm, giá trị và toán tử được đánh giá để tạo ra giá trị kết quả. 

Đây là tất cả các ví dụ về các expressions:
    
    
    2 * 2  
    doubleMap([2, 3, 4])  
    Math.max(4, 3, 2)

Thông thường trong code, bạn sẽ thấy các expression được gán cho một số nhận dạng, được trả về từ các hàm hoặc được chuyển vào một hàm. Trước khi được chỉ định, trả về, hoặc được thông qua,expression được đánh giá đầu tiên và giá trị kết quả được sử dụng.

### Phần kết luận

 Lập trình chức năng favors:

* Pure functions thay vì shared state và side effects
* Tính bất trên dữ liệu có thể thay đổi
* Thành phần chức năng  điều khiển lưu lượng bmperativeF
* Rất nhiều tiện ích chung, có thể tái sử dụng sử dụng các hàm bậc cao hơn để hành động trên nhiều loại dữ liệu thay vì các phương thức chỉ hoạt động trên dữ liệu được phân bổ của chúng
* Declarative rather than imperative code (what to do, rather than how to do it)
* Expressions over statements
* Containers & higher order functions over ad-hoc polymorphism



![][11]

[1]: https://cdn-images-1.medium.com/max/1600/1*1OxglOpkZHLITbIKEVCy2g.jpeg
[2]: https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-pure-function-d1c076bec976
[3]: https://medium.com/javascript-scene/master-the-javascript-interview-what-is-function-composition-20dfb109a1a0
[4]: https://medium.com/javascript-scene/10-tips-for-better-redux-architecture-69250425af44
[5]: https://medium.com/javascript-scene/the-dao-of-immutability-9f91a70c88cd
[6]: https://github.com/facebook/immutable-js
[7]: https://github.com/swannodette/mori
[8]: https://en.wikipedia.org/wiki/Monad_%28functional_programming%29
[9]: https://github.com/fantasyland/fantasy-land
[10]: http://ericelliottjs.com/product/lifetime-access-pass/
[11]: https://cdn-images-1.medium.com/max/1600/1*3njisYUeHOdyLCGZ8czt_w.jpeg

  
