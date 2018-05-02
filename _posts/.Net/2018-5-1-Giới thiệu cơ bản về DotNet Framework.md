---
layout: post
title: Giới thiệu cơ bản về .Net Framework
---
Sự ra đời của .Net  
.NET Framework của Microsoft là một nền tảng lập trình tập hợp các thư viện lập trình có thể được cài thêm hoặc đã có sẵn trong các hệ điều hành Windows. Nó cung cấp những giải pháp thiết yếu cho những yêu cầu thông thường của các chương trình điện toán như:
- Lập trình giao diện người dùng

- Truy cập dữ liệu, kết nối cơ sở dữ liệu

- Ứng dụng web, các giải thuật số học và giao tiếp mạng.
Ngoài ra, .NET Framework quản lý việc thực thi các chương trình được viết dựa trên .NET Framework do đó người dùng cần phải cài .NET Framework để có thể chạy các chương trình được viết trên nền .NET

Kiến trúc của .Net framework:


Các thành phần cơ bản của .Net framework
Về cơ bản .Net Framework được chia làm 2 phần là:

Common Language Runtime (CLR) : Bộ thực thi ngôn ngữ chung.
.Net Framework Class Library
Bộ biên dịch CLR : là 1 thành phần trung tâm của .Net framework với nhiệm vụ thực hiện biên dịch các chương trình. cái nào khủng hay nhanh hay không là đều dựa vào cái trình biên dịch của nó này — cái này bên Java là JVM ( Java Vitual Machine) nhé.



+ Các dịch vụ mà CLR cung cấp cho ta như sau:

– Nạp và thực thi chương trình
– Phân chia vùng nhớ của ứng dụng
– Xác minh tính an toàn của kiểu dữ liệu
– Dịch mã IL thành mà máy thực thi được
– Cung cấp metadata
– Quản lý bộ nhớ tự động (automatic garbage collection)
– Thực thi bảo mật
– Quản lý lỗi và ngoại lệ
– Hỗ trợ các công việc như debug hoặc profile ứng dụng
– Liên kết với các hệ thống khác



.NET Assemblies


Sau khi Project .NET được biên dịch, cho dù bạn dùng ngôn ngữ nào thì ngôn ngữ đó đều được đưa về ngôn ngữ CIL. CIL nằm trong khối Assembly, khối này bao gồm các thành phần sau:

A Windows file header
A CLR file header
CIL code
Type metadata
An assembly manifest
Optional embedded resources
Khái niệm thì phức tạp, để đơn giản có thể hiểu một ứng dụng .NET có thể có nhiều assembly và assembly có thể là  *.DLL hoặc *.EXE. Assembly có hai kiểu:

Private Assembly: DLL và EXE  chỉ được thực thi bởi một ứng dụng
Public/Shared Assembly: DLL có thể được sử dụng bởi nhiều ứng dụng cùng lúc. Loại này thường được lưu trữ tại "C:\Windows\Assembly"
Satellite Assembly: Chứa các đối tượng tĩnh và không thể thực thi  ví dụ như ảnh.


+ Cách hoạt động của bộ biên dịch: CLR cung cấp môi trường Run-Time, bạn có thể hiểu đó là một môi trường cung cấp các dịch vụ có sẵn để giúp chương trình .NET chạy được và dễ dàng.
Các đoạn mã được viết bằng .Net sẽ được biên dịch thành ra mã trung gian MSIL (Microsoft Intermediate Language). Khi thực thi chương trình 1 lần nữa CLR sẽ biên dịch các mã trung gian MSIL này thành mã máy để thực thi.

Nói một cách khác nó biên dịch assembly thành mã máy. 



Quá trình biên dịch và chạy chương trình trên nền .NET


















CLR là gần giống như 1 assemply nhưng không phải là assemply *

=> Vậy vấn đề là tại sao lại cần phải dịch qua ngôn ngữ trung gian: Như ta đã biến thì .Net framework là 1 nền tảng và nó cho phép các ứng dụng họ nhà .Net phát triển các ứng dụng trên nó… Điều này sẽ là mất tri chi phí nếu như 1 chức năng được xây dựng trên ngôn ngữ này khi sang ngôn ngữ khác cũng thuộc họ .Net lại phải phát triển lại… Chẳng hạn viết 1 bộ thư viện xử lý chuỗi trên Visual Basic sang C# lại phải viết lại => .Net framework cung cấp 1 giải pháp biên dịch qua mã trung gian MSIL và Các bộ mã này biên dịch các các mã trung gian này thành các thư viện liên kết động Dynamic Language Linked (DLL) để hỗ trợ cho việc tái sử dụng ..
VD: xây dựng 1 bộ xử lý chuỗi trên C# có thể sử dụng lại trên Visual Basic hay J#, F#, các họ ngôn ngữ nhà .Net mà ko cần xây dựng lại.
Common Type System (CTS)
.NET framework hỗ trợ nhiều ngôn ngữ và đều dùng một thành phần gọi là hệ thống kiểu chung CTS trong CLR. CTS hỗ trợ một loạt kiểu và toán tử có thể thấy trong hầu hết các ngôn ngữ lập trình nên gọi một ngôn ngữ từ một ngôn ngữ khác sẽ không yêu cầu chuyển kiểu. Dẫn đến chúng ta có thể xây dựng các ứng dụng .NET sử dụng cả ngôn ngữ VB.NET lẫn C#, C++…



Một số kiểu dữ liệu CTS cơ bản

CLS-Compliant Primitive Types
Type	C#	VB	C++/CLI	F#
System.Byte	byte	Byte	unsigned char	byte
System.Int16	short	Short	short	int16
System.Int32	int	Integer	int/long	int/int32
System.Int64	long	Long	__int64	int64
System.Single	float	Single	Float	single/float32
System.Double	double	Double	Double	double/float
System.Boolean	bool	Boolean	Bool	bool
System.Char	char	Char	wchar_t	char
System.Decimal	decimal	Decimal	Decimal	decimal
System.String	string	String	String^	string


Common Language Specification (CLS)
Đặc tả ngôn ngữ chung CLS là một tập con của CTS, nó định nghĩa một tập các quy tắc cho phép liên kết hoạt động trên nền tảng .NET. Các quy tắc này sẽ trợ giúp và chỉ dẫn cho các nhà thiết kế compiler của hãng thứ 3 hoặc những người muốn xây dựng thư viện dùng chung.



Microsoft Intermediate Language (MSIL)
MSIL hay còn gọi IL là một tập lệnh mà tất cả các chương trình .NET được biên dịch thành. Nó trông hơi giống ngôn ngữ assembly và nó chứa các lệnh để nạp, lưu trữ, khởi tạo, gọi các phương thức trong chương trình. Khi chúng ta biên dịch một chương trình C# hoặc bất kỳ chương trình nào được viết bởi ngôn ngữ tuân theo CLS thì mã của nó sẽ là IL.

IL: Intermediate Language

CIL: Common Intermediate Language

Các Project .NET không trực tiếp biên dịch trực tiếp về mã nhị phân mà được chuyển đổi sang một ngôn ngữ trung gian cấp thấp gọi là MSIL (hay còn được gọi là CIL).

Mã CIL có dạng như sau. Để xem mã này trên Visual Studio bạn có thể dùng.NET Reflector (fee) hoặc các công cụ tương tự khác.

.method public hidebysig instance int32 Add(int32 x,
int32 y) cil managed
{
// Code size 9 (0x9)
.maxstack 2
.locals init (int32 V_0)
IL_0000: nop
IL_0001: ldarg.1
IL_0002: ldarg.2
IL_0003: add
IL_0004: stloc.0
IL_0005: br.s IL_0007
IL_0007: ldloc.0
IL_0008: ret
} // end of method Calc::Add

Tham khảo thêm: Understanding Common Intermediate Language (CIL)





JIT - Just-In-Time
CLR chuyển mã IL thành mã máy (Native Code) trong lúc runtime. Quá trình này được gọi là JIT Compiling

Managed Code
CLR chịu trách nhiệm quản lý việc thực thi mã được biên dịch trên nền tảng .NET. Mã chạy được trên môi trường thực thi CLR được gọi là managed code. Trình biên dịch tương thích với nền tảng .NET sẽ tạo ra managed code. Managed code được tạo bởi C# chính là IL code.

Garbage Collection (GC): Bộ phận thu gom rác.
CLR tự động quản lí kí ức, nhằm làm giảm sự rò rỉ kí ức. Một lúc nào đó (do CLR tự chọn), GC sẽ nhảy vào giải phóng các vùng kí ức không còn được cái gì trỏ đến (không dùng nữa); lập trình viên không phải làm việc này (trừ lúc cố tình).
 
.Net FrameWork Class Library
BCL: Basic Class Library là 1 bộ thư viện liên kết động , cung cấp 1 thư viện lập trình cho ứng dụng CSDL . Web ..vv
Ado.Net và XML:
Asp.Net
Web Service
Windows Form
Lịch sử của .Net Framwork





.NET LÀM ĐƯỢC NHỮNG GÌ?

 Web Application (Webforms & MVC): Ứng dụng chạy trên nền WEB được triển khai tại máy chủ IIS của Microsoft.
Web Application (Webforms)
Web Application (ASP.NET MVC)
Windows Workflow Foundation (WF): Xây dựng các thành phần, thư viện phục vụ các hệ thống có chức năng XỬ LÝ CÔNG VIỆC THEO QUY TRÌNH (WORKFLOW)
Windows Communication Foundation (WCF): Xây
dựng hệ thống có các thành phần hướng dịch vụ. Thường áp dụng trong các loại:
+) Các giao dịch xử lý cần bảo mật cao.
+) Trao đổi dữ liệu giữa các hệ thống, các nền tảng khác
nhau.
+) Các hệ thống có nhiều giao diện đầu cuối nhưng sử dụng
chung các nghiệp vụ xử lý.
Lập trình Game:
+) Unity3D: Sử dụng C# là ngôn ngữ lập trình
+) XNA, OpenGL, DirectX: Lập trình game cho hệ máy
console XBOX.
Lập trình di động:
+) Windows Store (Windows 8.1)
+) Windows Phone (Nokia Lumia)
CHỌN .NET THÌ NÊN HỌC CÁI GÌ?

Ngôn ngữ lập trình C#
+) Làm chủ ngôn ngữ lập trình.
+) Sử dụng thành thạo các thư viện phổ biến của .NET Framework
Cơ sở dữ liệu:
+) Hiểu rõ về lý thuyết của CSDL quan hệ.
+) Thiết kế cơ sở dữ liệu trên Microsoft Sql Server
+) Lập trình cơ sở dữ liệu với T-SQL trên Microsoft Sql
Server.
Phát triển ứng dụng DESKTOP
Phát triển ứng dụng trên WEB
Sử dụng thành thạo ADO.NET để truy cập CSDL từ
môi trường lập trình.
Sử dụng ADO.NET Entity Framework (ORM) và
LINQ.
Biết và vận dụng WebService, WCF để phát triển
các ứng dụng hướng dịch vụ.
Lập trình di động: Windows Phone
Học nâng cao để làm việc:

Web (Front-End):
+) Html5, Jquery, AngularJS, KnockoutJS, …
Database:
+) Advanced SQL Server: Report Service, Analysis Service,
Integration Service, Service Broker.
+) SQL Azure (Database Cloud Computing)
Programming: Design Pattern
NoSql:
+) MongoDB, RavenDb, CouchDB, Cassandra DB, …
+) Real-time: SignalR