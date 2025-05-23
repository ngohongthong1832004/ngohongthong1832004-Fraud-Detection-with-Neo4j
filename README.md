# Fraud-Detection---Insurance-Claims
## AIM : 

**Fraud Detection Using Graphs – Neo4j**. Trong dự án này, chúng ta phải phát hiện gian lận trong môi trường thực tế, sử dụng thuật toán ML và cơ sở dữ liệu đồ thị Neo4j. Tôi đang tạo một sổ tay python giúp dự đoán gian lận và biểu diễn gian lận bằng cơ sở dữ liệu Neo4j.

## What is a Fraud Detection Model? 

Mô hình phát hiện gian lận là mô hình ML giúp phát hiện gian lận theo thời gian thực. Học máy (ML) là một tập hợp các phương pháp và kỹ thuật cho phép máy tính nhận dạng các mẫu và xu hướng và tạo ra các dự đoán dựa trên những mẫu và xu hướng đó. Cùng với ML, chúng tôi cũng sẽ sử dụng cơ sở dữ liệu đồ thị neo4j để biểu diễn trực quan mô hình..

## Why is Machine Learning suited for Fraud Detection?

Với sự sẵn có của rất nhiều phương pháp và công nghệ trên thị trường, tại sao ML lại phù hợp để phát hiện gian lận? Hãy cùng xem:

**• It is Super-Fast:** Trong Phát hiện gian lận, chúng ta cần kết quả cực nhanh để kẻ gian không trốn thoát. ML phù hợp nhất cho mục đích này.

**• Efficient and Cheap:** Việc thực hiện hàng trăm nghìn phép tính thanh toán mỗi giây không phải là nhiệm vụ dễ dàng, tốn kém về mặt thời gian và chi phí, nhưng ML có thể thực hiện điều đó chỉ trong vài giây.

**• More Accurate:** Các mô hình học máy có thể học từ các mô hình hành vi bình thường rất khó phát hiện bằng cách khác. Nó nhanh chóng thích ứng với những thay đổi và xác định các mô hình gian lận.

**• Scalable:** Trong trường hợp cần tài nguyên đột ngột, chúng ta có thể mở rộng mô hình ML để có ranh giới mới và áp dụng lại thuật toán tương tự một cách hiệu quả.

## Insurance Fraud, what is it?

Gian lận bảo hiểm là hành vi bất hợp pháp của bên mua hoặc bên bán hợp đồng bảo hiểm. Gian lận bảo hiểm từ bên phát hành bao gồm bán hợp đồng bảo hiểm từ các công ty không tồn tại, không nộp phí bảo hiểm và đảo ngược hợp đồng bảo hiểm để tạo ra nhiều hoa hồng hơn. Trong khi đó, gian lận của bên mua có thể bao gồm các khiếu nại phóng đại, làm giả tiền sử bệnh án, hợp đồng bảo hiểm ghi ngày sau, gian lận viatical, giả chết hoặc bắt cóc, và giết người.

## Insurance Claims dataset

Chúng tôi sử dụng một tập dữ liệu (insurance_claims.csv) gồm 1000 hàng và 36 cột theo định dạng csv (các giá trị được phân cách bằng dấu phẩy). Sau đó, chúng tôi xử lý dữ liệu và dự đoán các mô hình gian lận bằng ML.
 
![image](https://user-images.githubusercontent.com/95923021/179353860-a4e54459-7c77-4a42-99ee-e637fcf9c2ec.png)

## What is Neo4j? 

 ![image](https://user-images.githubusercontent.com/95923021/179353891-ac4eb871-78c4-4ed3-84bc-e1af2782387f.png)

Trước khi tìm hiểu Neo4j, chúng ta hãy xem cơ sở dữ liệu đồ thị là gì. Cơ sở dữ liệu đồ thị lưu trữ các nút và mối quan hệ thay vì các bảng hoặc tài liệu. Dữ liệu được lưu trữ giống như bạn có thể phác thảo ý tưởng trên bảng trắng. Dữ liệu của bạn được lưu trữ mà không giới hạn nó trong một mô hình được xác định trước, cho phép một cách rất linh hoạt để suy nghĩ về và sử dụng nó.
Neo4j là một phương tiện để sử dụng cơ sở dữ liệu đồ thị và áp dụng nó vào các ứng dụng trong thế giới thực. Hãy nghĩ về nó như một phần mềm giúp chúng ta sử dụng cơ sở dữ liệu đồ thị một cách chính xác và hiệu quả. Neo4j sử dụng ngôn ngữ mã hóa để giao tiếp với dữ liệu, bất kể ở định dạng nào (tức là .csv, .dump, v.v.)

## Tools Used :

Sau đây là các công cụ được sử dụng để hoàn thành dự án này:

**•	Google Colab:** Đây là sản phẩm của Google Research. Colab cho phép bất kỳ ai viết và thực thi mã python thông qua trình duyệt mà không cần cài đặt bất kỳ phần mềm hoặc plugin nào. Dễ sử dụng, hiệu quả và mạnh mẽ.

**•	Neo4j:** Đây là cơ sở dữ liệu đồ thị NoSQL mã nguồn mở cho phép người dùng lưu trữ, liên hệ và hiển thị dữ liệu dưới dạng đồ thị để trực quan hóa và hiểu rõ hơn. Nó sử dụng ngôn ngữ cypher.


## How to predict fraud using ML : 

Học máy cung cấp cho chúng ta nhiều mô hình/thuật toán mà chúng ta có thể sử dụng để giải quyết các vấn đề như vậy. Các bước theo thứ tự sau:

•	 Nhập thư viện và tập dữ liệu: Đầu tiên chúng ta nhập các thư viện cần thiết và tập dữ liệu sẽ được yêu cầu. Trong trường hợp này, chúng ta sử dụng pandas, numpy và seaborn. Sau đó, chúng ta nhập tập dữ liệu của mình – ‘insurance_claims.csv’ bằng cách sử dụng

 df = pd.read_csv('/content/insurance_claims.csv')
 
**• Tiền xử lý dữ liệu:** Sau khi nhập tập dữ liệu, chúng tôi tiền xử lý dữ liệu để tìm kiếm các giá trị bị thiếu, giá trị NaN và để kiểm tra các kiểu dữ liệu được sử dụng trong tập dữ liệu.

**• Trực quan hóa các giá trị bị thiếu:** Sau khi tiền xử lý, chúng tôi xem dữ liệu dưới dạng đồ thị và xem các giá trị bị thiếu để hiểu rõ hơn về tập dữ liệu của mình.

**• Xử lý các giá trị bị thiếu:** Sau đó, chúng tôi xử lý các giá trị bị thiếu bằng cách thay thế chúng bằng 0. Sau đó, chúng tôi loại bỏ các nhãn không cần thiết khỏi tập dữ liệu của mình.

**• Phát hiện giá trị ngoại lai:** Sau đó, chúng tôi phát hiện các giá trị ngoại lai và đào tạo các biến phân loại của mình cho thuật toán phân loại.

**• Sử dụng thuật toán ML:** Sau khi mọi thứ đã hoàn tất, chúng tôi áp dụng thuật toán phân loại ML để kiểm tra mô hình của mình.


## Random Forest Classification Model :

Random Forest là một bộ phân loại chứa một số cây quyết định trên nhiều tập con khác nhau của tập dữ liệu đã cho và lấy giá trị trung bình để cải thiện độ chính xác dự đoán của tập dữ liệu đó. Thay vì dựa vào một cây quyết định, random forest lấy dự đoán từ mỗi cây và dựa trên số phiếu bầu đa số của các dự đoán, và dự đoán đầu ra cuối cùng.

![image](https://user-images.githubusercontent.com/95923021/179419556-addc864d-1d04-47a0-97fa-9061afb28ef3.png)


## Neo4j Representation : 

Sau đó, chúng tôi tải tập dữ liệu lên trình duyệt neo4j. Chúng tôi tạo nhãn và đánh dấu mối quan hệ giữa các nhãn khác nhau trong tập dữ liệu để có thể hiển thị dưới dạng biểu đồ được liên kết.
 
```
LOAD CSV WITH HEADERS FROM 'file:///refined_dataset.csv' AS line
WITH line
MERGE (fraud: Fraud {id: line.fraud_reported})
MERGE (incident_t: Incident_T {id: line.incident_type})
CREATE (customer: Customer {
  Occupation: line.insured_occupation,
  sex: line.insured_sex,
  incident: line.incident_type
})-[:WITH]->(incident_t)
CREATE (customer)-[:MAKE]->(fraud);
```

**Thực hiện truy vấn :**
Kiểm tra dữ liệu đã tạo:
```
MATCH (n) RETURN n LIMIT 50
```
Xem quan hệ;

```
MATCH (c:Customer)-[:WITH]->(i:Incident_T)
RETURN c, i
```
Xem mối quan hệ giữa Customer và Incident_T
```
MATCH (c:Customer)-[:WITH]->(i:Incident_T)
RETURN c, i LIMIT 50
```


Xem mối quan hệ giữa Customer và Fraud
```
MATCH (c:Customer)-[:MAKE]->(f:Fraud)
RETURN c, f LIMIT 50
```

Đếm số lượng khách hàng theo loại sự cố
```
MATCH (c:Customer)-[:WITH]->(i:Incident_T)
RETURN i.id AS incident_type, COUNT(*) AS total_customers
ORDER BY total_customers DESC
```

Thống kê theo giới tính
```
MATCH (c:Customer)
RETURN c.sex AS gender, COUNT(*) AS total
```

PHÂN TÍCH DỮ LIỆU GIAN LẬN
Tìm tất cả khách hàng đã báo cáo gian lận
```
MATCH (c:Customer)-[:MAKE]->(f:Fraud {id: 'Y'})
RETURN c
```
Tỷ lệ gian lận theo giới tính
```
MATCH (c:Customer)-[:MAKE]->(f:Fraud)
RETURN c.sex AS gender, COUNT(*) AS total
```
Loại sự cố nào có gian lận cao nhất?
```
MATCH (c:Customer)-[:WITH]->(i:Incident_T), (c)-[:MAKE]->(f:Fraud {id: 'Y'})
RETURN i.id AS incident_type, COUNT(*) AS fraud_count
ORDER BY fraud_count DESC
```


## PHÂN TÍCH DỮ LIỆU KHÁCH HÀNG
Thống kê số lượng khách hàng theo nghề nghiệp
```
MATCH (c:Customer)
RETURN c.Occupation AS occupation, COUNT(*) AS total
ORDER BY total DESC
```
Sự phân bố khách hàng theo giới tính và loại sự cố
```
MATCH (c:Customer)-[:WITH]->(i:Incident_T)
RETURN c.sex AS gender, i.id AS incident_type, COUNT(*) AS total
ORDER BY total DESC
```


Tìm các khách hàng nữ đã gặp tai nạn Multi-vehicle Collision và có gian lận
```
MATCH (c:Customer {sex: 'FEMALE'})-[:WITH]->(i:Incident_T {id: 'Multi-vehicle Collision'}), 
      (c)-[:MAKE]->(f:Fraud {id: 'Y'})
RETURN c
```
