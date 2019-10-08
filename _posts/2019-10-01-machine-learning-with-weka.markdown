---
layout: post
title: Tự học Machine Learning với Weka
date: 2019-10-01 17:25:00 +0700
description: Tự học Machine Learning cho người mới bắt đầu với Weka. Nhập môn máy học Machine Learning
img: machine-learning-weka.jpg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Machine Learning, Weka]
---

### 0. Giới thiệu

* Ngày nay, Machine Learning (ML) đã được phổ biến và áp dụng trong nhiều lĩnh vực khác nhau như xe tự lái, đánh cờ, dự đoán, thống kê ... Trong bài viết này, chúng ta sẽ thực hành ML bằng phần mềm Weka mà không cần phần code bất cứ dòng code nào.

* Sau khi đọc xong và làm theo bài viết này, bạn sẽ có thể: 

  * Hiểu được cách làm việc với Dataset trong ML

  * Khám phá các thuật toán thường dùng trong ML và thông qua phần mềm Weka

  * Đánh giá, thống kê các thuật toán áp dụng, từ đó chọn ra mô hình tốt nhất cho vấn đề của mình

* Bài viết này dành cho các bạn hiện tại là lập trình viên (Developer) muốn tìm hiểu về ML, cách làm việc của ML trước khi bước vào một thế giới đầy thú vị với Machine Learning.

### 1. Download và cài đặt Weka

* Weka là một phần mềm miễn phí mã nguồn mở, được viết bằng Java. Vì vậy, Weka có thể chạy trên tất cả các nền tảng có thể chạy được Java (Windows, MacOS, Linux). Bạn có thể download tại đây: [https://www.cs.waikato.ac.nz/ml/weka/downloading.html?__s=dkozbixc2aspc1dkmsty](https://www.cs.waikato.ac.nz/ml/weka/downloading.html?__s=dkozbixc2aspc1dkmsty)

* Vì được chạy trên Java, nên đầu tiên bạn cần cài đặt Java trước nhé. Bạn có thể tham khảo cách cài đặt Java ở đây: [https://java.com/en/download/help/download_options.xml](https://java.com/en/download/help/download_options.xml)

### 2. Cách load Dataset cho Machine Learning

* Weka được thiết kế để load data với định dạng ARFF. Nó tương tự như CSV nhưng thêm thuộc tính (attribute) của mỗi đối tượng (tương đương với CSV là cột)

* Sau khi bạn cài đặt, thì Weka đã để sẵn một số file data mẫu theo định dạng ARFF trong thư mục `data`.

* Weka cũng hỗ trợ load data theo định dạng CSV và convert sang định dạng ARFF khi cần thiết. Bạn có thể tìm thêm data theo định dạng CSV tại đây: [http://archive.ics.uci.edu/ml/index.php](http://archive.ics.uci.edu/ml/index.php)

* Cách load Dataset trên Weka:

  * Đầu tiên, mở ứng dụng Weka

  * Click button `Explorer`

  * Click `Open file...` và tìm đến file data bạn muốn load lên. như vậy là xong rồi nhé.

### 3. Trực quan hoá dữ liệu

* Weka giúp bạn có cái nhìn tổng quan về data mà bạn load lên. Ngoài ra, nó cũng có nhiều công cụ để bạn có thể xem trực quan về data của bạn.

* Ở đây, bạn có thể download data `smsSpamCollection.arff` [Tại đây](http://www.dt.fee.unicamp.br/~tiago/smsspamcollection/smsSpamCollection.arff) để mình thử nghiệm nhé

* Sau khi download về, bạn load dataset như bước 2 nha. Bạn sẽ thấy các thông tin cơ bản của data như sau:

  ![](/assets/img/weka-1.png)

  * Thống kê của dataset (Current relation) gồm: Tên của relation, số lượng data (Intances), số lượng thuộc tính (attributes)

  * Tiếp theo là tên của Attributes: như ví dụ trong hình, dataset này gồm 2 attribute là `Text` và `class-att`

  * Khi click vào attribute `class-att`, bạn sẽ thấy data này được đánh 2 nhãn (label) là 0 và 1. Với số lượng data tương ứng với nhãn đó

  * Cuối cùng, bạn sẽ thấy mô phỏng data được vẽ thành biểu đồ cột

* Ngoài ra, đối với mỗi loại data khác nhau, trên Weka sẽ hiển thị khác nhau một cách trực quan, dễ nhìn hơn.

