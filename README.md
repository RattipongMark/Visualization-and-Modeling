# Introduction

รายงานนี้เป็นส่วนหนึ่งของรายวิชา Data Models (CPE 232) โดยเป็นการจัดทำ EDA, Visualization และ Modeling โดยใช้ชุดข้อมูล Ecommerce Customer Churn จำนวน 5639 แถว ในการทำงาน

# Data Explanation

ข้อมูลของบริษัท Online E-commerce เป็นข้อมูลที่บอกถึงพฤติกรรมการซื้อสินค้าออนไลน์ของลูกค้า และประวัติการซื้อของเหล่านั้น โดยข้อมูลมีทั้งหมด 5,630 rows และ 20 columns ดังนี้:

- **CustomerID**: ID ของลูกค้าแต่ละคน
- **Churn**: เลขที่บอกถึงการ Churn ของลูกค้าโดย 0 หมายถึงลูกค้ายังเป็นสมาชิกของบริษัทอยู่ และ 1 หมายถึงลูกค้ายกเลิกการเป็นสมาชิกของบริษัทไปแล้ว
- **Tenure**: ระยะเวลาที่ลูกค้าอยู่กับองค์กรนี้
- **PreferredLoginDevice**: อุปกรณ์ที่ลูกค้าเลือกใช้ในการ Login
- **CityTier**: ระดับของพฤติกรรมในการบริโภคของประชากรในเมืองนั้น โดยจะมีตั้งแต่ระดับ 1 ไปจนถึง ระดับ 3
- **WarehouseToHome**: ระยะห่างระหว่างที่เก็บสินค้ากับบ้านลูกค้า
- **PreferredPaymentMode**: วิธีที่ลูกค้าเลือกใช้ในการชำระเงิน
- **Gender**: เพศของลูกค้า
- **HourSpendOnApp**: จำนวนชั่วโมงที่ลูกค้าใช้งานแอพบนโทรศัพท์หรือในเว็บไซต์
- **NumberOfDeviceRegistered**: จำนวนอุปกรณ์ทั้งหมดที่ลูกค้าลงทะเบียนไว้
- **PreferedOrderCat**: หมวดหมู่สินค้าที่ลูกค้าซื้อบ่อยในเดือนก่อนหน้า
- **SatisfactionScore**: ความพึงพอใจของลูกค้า
- **MaritalStatus**: สถานภาพการสมรสของลูกค้า
- **NumberOfAddress**: จำนวนที่อยู่ทั้งหมดของลูกค้า
- **Complain**: ลูกค้าได้มีการ complain หรือไม่ในเดือนก่อนหน้าโดย 0 หมายถึง ไม่มีการ complain เลยในเดือนก่อนหน้า 1 หมายถึงมีการ complain ในเดือนก่อนหน้า
- **OrderAmountHikeFromLastYear**: จำนวน order รวมที่ลูกค้ารายนี้สั่งเพิ่มขึ้นจากปีที่แล้วคิดเป็นเปอร์เซ็นต์
- **CouponUsed**: จำนวนคูปองทั้งหมดที่ลูกค้ารายนี้ใช้ในเดือนก่อนหน้า
- **OrderCount**: จำนวน order ทั้งหมดที่ลูกค้าสั่งในเดือนก่อนหน้า
- **DaySinceLastOrder**: จำนวนวันที่ผ่านไปนับตั้งแต่ลูกค้าสั่งซื้อครั้งล่าสุด
- **CashbackAmount**: จำนวนเงินเฉลี่ยที่ลูกค้าได้รับคืนในเดือนที่แล้ว

# Data Preparation Process and Results

## การ Clean Data

- ตรวจสอบคอลัมน์ที่ไม่มีค่าและวิเคราะห์ข้อมูล
- ค่ามัธยฐานถูกใช้ในการเติมค่าว่าง เนื่องจากใกล้เคียงกับค่าเฉลี่ยในหลายคอลัมน์

## การเติมข้อมูลส่วนที่หายไป

- ใช้ค่ามัธยฐานในการเติมข้อมูลที่ขาดหายไป

# Exploratory Data Analysis (EDA) and Visualization

## Univariate Analysis

### Categorical Data
- Churn
- Preferred Login Device
- City Tier
- Preferred Payment Mode
- Gender
- Prefered Order Cat
- Marital Status
- Complain

### Numerical Data
- Tenure
- Warehouse To Home
- Hour Spend On App
- Number Of Device Registered
- Satisfaction Score
- Number Of Address
- OrderAmountHike From Last Year
- CouponUsed
- OrderCount
- DaySinceLastOrder
- CashBackAmount

## Churn Analysis

### Categorical Data
- Preferred Login Device
- City Tier
- Preferred Payment Mode
- Gender
- Prefered Order Cat
- Marital Status
- Complain

### Numerical Data
- Tenure
- WarehouseToHome
- HourSpendOnApp
- NumberOfDeviceRegistered
- SatisfactionScore
- NumberOfAddress
- OrderAmountHikeFromLastYear
- CouponUsed
- OrderCount
- DaySinceLastOrder
- CashbackAmount

# Modeling Method

- แยกข้อมูลเป็นสองประเภท: num (int, float) และ object
- ข้อมูลที่มี data type เป็น num ตัด CustomerID ออกไป
- ข้อมูลที่มี data type เป็น object ใช้ get_dummies เพื่อแยกเป็น column ที่มีแค่เลข 0 กับ 1

## Decision Tree

- ใช้ library sklearn เพื่อแบ่งข้อมูลสำหรับการ train และ test โดยกำหนดอัตราส่วนเป็น 70:30
- Plot decision tree
- Feature importance: Tenure

## Logistic Regression

- Import Logistic Regression model กำหนด max_iter ที่ 10,000
- Classification report ให้ค่า accuracy อยู่ที่ 0.90

## K-neighbors Classifier

- Classification report ให้ค่า accuracy อยู่ที่ 0.87

## Random Forest Classifier

- Import RandomForestClassifier และตั้งค่า n_estimators = 100, random_state = 1, bootstrap = True
- Classification report ให้ค่า accuracy อยู่ที่ 0.96
- สร้าง confusion matrix

# Modeling Results and Discussion

จากการทำ decision tree พบว่า Tenure มีอิทธิพลต่อการ churn มากที่สุด รองลงมาเป็น Complain, NumberOfAddress, CashbackAmount, DaySinceLastOrder, NumberOfDeviceRegistered, SatisfactionScore, CouponUsed และ PreferredPaymentMode_UPI

ลูกค้าที่ใช้บริการมาไม่นานมักจะมีแนวโน้มที่จะเลิกใช้บริการ
