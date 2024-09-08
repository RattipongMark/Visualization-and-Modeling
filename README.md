![](media/image1.png){width="1.671875546806649in"
height="1.671875546806649in"} []{.mark}

**\
CPE 232 Data Models Final Project\
**

**จัดทำโดย**

> [**65070501048 รัฐธิพงษ์** **สกุลจีน**]{.mark}
>
> [**65070501072 ชนกันต์** **จิตรกสิกร**]{.mark}
>
> [**65070501074 ณภัทร** **สินจินดาวงศ์**]{.mark}
>
> [**65070501075 ณัฐชนน** **บุญยะโท**]{.mark}
>
> [**65070501084 ภูมิรพี** **เมืองน้อย**]{.mark}
>
> []{.mark}

**\
เสนอ**

**[ผศ.ดร.สันติธรรม พรหมอ่อน]{.mark}**

[]{.mark}

**[รายงานนี้เป็นส่วนหนึ่งของรายวิชา Data Models (CPE 232)]{.mark}**

**[ภาคเรียนที่ 2 ปีการศึกษา 2566]{.mark}**

**[มหาวิทยาลัยเทคโนโลยีพระจอมเกล้าธนบุรี]{.mark}**

**Introduction**

รายงานนี้เป็นส่วนหนึ่งของรายวิชา Data Models (CPE 232) โดยเป็นการจัดทำ EDA,
Visualization และ Modeling โดยใช้ชุดข้อมูล Ecommerce Customer Churn จำนวน
5639 แถว ในการทำงาน

**[Data explanation]{.mark}**

[ข้อมูลของบริษัท Online E-commerce เป็นข้อมูลที่บอกถึงพฤติกรรมการซื้อสินค้า\
ออนไลน์ของลูกค้า และประวัติการซื้อของเหล่านั้น โดยข้อมูลมีทั้งหมด 5,630 rows และ 20
columns ซึ่งได้แก่]{.mark}

-   [CustomerID : ID ของลูกค้าแต่ละคน]{.mark}

-   [Churn : เลขที่บอกถึงการ Churn ของลูกค้าโดย 0
    หมายถึงลูกค้ายังเป็นสมาชิกของบริษัทอยู่ และ 1
    หมายถึงลูกค้ายกเลิกการเป็นสมาชิกของบริษัทไปแล้ว]{.mark}

-   [Tenure : ระยะเวลาที่ลูกค้าอยู่กับองค์กรนี้]{.mark}

-   [PreferredLoginDevice : อุปกรณ์ที่ลูกค้าเลือกใช้ในการ Login]{.mark}

-   [CityTier : ระดับของพฤติกรรมในการบริโภคของประชากรในเมืองนั้น
    โดยจะมีตั้งแต่ระดับ 1 ไปจนถึง ระดับ 3]{.mark}

-   [WarehouseToHome : ระยะห่างระหว่างที่เก็บสินค้ากับบ้านลูกค้า]{.mark}

-   [PreferredPaymentMode : วิธีที่ลูกค้าเลือกใช้ในการชำระเงิน]{.mark}

-   [Gender : เพศของลูกค้า]{.mark}

-   [HourSpendOnApp : จำนวนชั่วโมงที่ลูกค้าใช้งานแอพบนโทรศัพท์หรือในเว็บไซต์]{.mark}

-   [NumberOfDeviceRegistered : จำนวนอุปกรณ์ทั้งหมดที่ลูกค้าลงทะเบียนไว้]{.mark}

-   [PreferedOrderCat : หมวดหมู่สินค้าที่ลูกค้าซื้อบ่อยในเดือนก่อนหน้า]{.mark}

-   [SatisfactionScore : ความพึงพอใจของลูกค้า]{.mark}

-   [MaritalStatus : สถานภาพการสมรสของลูกค้า]{.mark}

-   [NumberOfAddress : จำนวนที่รวมอยู่ของลูกค้า]{.mark}

-   [Complain : ลูกค้าได้มีการ complain หรือไม่ในเดือนก่อนหน้าโดย 0 หมายถึง ไม่มีการ
    complain เลยในเดือนก่อนหน้า 1 หมายถึงมีการ complain ในเดือนก่อนหน้า]{.mark}

-   [OrderAmountHikeFromlastYear : จำนวน order
    รวมที่ลูกค้ารายนี้สั่งเพิ่มขึ้นจากปีที่แล้วคิดเป็นเปอร์เซ็นต์]{.mark}

-   [CouponUsed : จำนวนคูปองทั้งหมดที่ลูกค้ารายนี้ใช้ในเดือนก่อนหน้า]{.mark}

-   [OrderCount : จำนวน order ทั้งหมดที่ลูกค้าสั่งในเดือนก่อนหน้า]{.mark}

-   [DaySinceLastOrder : จำนวนวันที่ผ่านไปนับตั้งแต่ลูกค้าสั่งซื้อครั้งล่าสุด]{.mark}

-   [CashbackAmount : จำนวนเงินเฉลี่ยที่ลูกค้าได้รับคืนในเดือนที่แล้ว]{.mark}

**[Data preparation process and results]{.mark}**

[ในการเตรียมข้อมูล หรือการ clean data จะต้องมีการทำความเข้าใจข้อมูลก่อนว่ามี\
ความหมายว่าอย่างไร จากนั้นนำข้อมูลมาตรวจสอบแต่ละคอลัมน์เป็นข้อมูลประเภท
มีค่าว่างหรือไม่]{.mark}

![](media/image2.png){width="2.2587248468941383in"
height="2.5049365704286966in"}
[]{.mark}![](media/image3.png){width="2.3566786964129482in"
height="2.517361111111111in"}

[การ clean data มีขั้นตอนดังนี้]{.mark}

-   [ตรวจสอบคอลัมน์ที่ไม่มีค่า และวิเคราะห์ข้อมูล\
    \
    ]{.mark}![](media/image4.png){width="2.281324365704287in"
    height="2.6805555555555554in"}[\
    \
    จะเห็นได้ว่า มีคอลัมน์ที่มีค่าว่างซึ่งการจัดการค่าว่างนี้สามารถทำได้โดยการนำค่าเฉลี่ย หรือ
    ค่ามัธยฐานมาแทนที่ซึ่งเมื่อเปรียบเทียบค่าเฉลี่ยและค่ามัธยฐานของแต่ละคอลัมน์ที่ไม่มีค่าพบว่ามีค่าที่ใกล้เคียงกันในที่นี้จึงเลือกใช้ค่ามัธยฐานเนื่องจากโดยส่วนใหญ่มีค่าน้อยกว่า
    ค่าเฉลี่ย]{.mark}

![](media/image5.png){width="4.2809853455818025in"
height="1.5885422134733158in"}**[\
]{.mark}**

-   [เติมข้อมูลส่วนที่หายไป\
    \
    ]{.mark}![](media/image6.png){width="4.338542213473316in"
    height="0.8109426946631672in"}[\
    \
    จากขั้นตอนที่ผ่านมาได้มีการเลือกค่ามัธยฐานในการเติมในส่วนที่ข้อมูลขาดหายไป]{.mark}

**[Exploratory Data Analysis (EDA) and visualization of data]{.mark}**

[ในส่วนแรกจะเริ่มด้วยการปรับชนิดของข้อมูลแต่ละคอลัมน์ให้ถูกต้อง โดยมีการนำคอลัมน์
CustomerID ออก และแก้ไขคอลัมน์ Churn CityTier และ Complain ให้เป็น
object]{.mark}

![](media/image7.png){width="4.765625546806649in"
height="1.147866360454943in"} []{.mark}

[จากนั้นจะทำการแบ่งคอลัมน์เป็นสองประเภทคือ Categorical และ Numerical
โดยแยกจากชนิดข้อมูลที่เป็น object หรือไม่]{.mark}

![](media/image8.png){width="3.182292213473316in"
height="1.3737226596675416in"}

[สำหรับการ visualization แบ่งเป็น 2 แบบดังนี้]{.mark}

[\
]{.mark}

1.  *[Univariate Analysis]{.mark}*

    1.  [Categorical Data]{.mark}

        1.  [Churn : กราฟแสดงสัดส่วนของสถานะการ Churn ของลูกค้า]{.mark}

> ![](media/image9.png){width="3.2802230971128608in"
> height="2.7725699912510935in"}

2.  [Preferred Login Device : กราฟแสดงสัดส่วนของเครื่องมือต่างๆ ที่ลูกค้าใช้ในการ
    login\
    \
    ]{.mark}![](media/image10.png){width="3.276042213473316in"
    height="2.7968339895013123in"}

3.  [City Tier : กราฟแสดงระดับของเมืองที่ลูกค้าอยู่\
    \
    ]{.mark}![](media/image11.png){width="3.25in"
    height="2.6805555555555554in"}

4.  [Preferred Payment Mode : กราฟแสดงวิธีที่ลูกค้าเลือกใช้ใน\
    การชำระเงิน\
    \
    ]{.mark}![](media/image12.png){width="3.059620516185477in"
    height="2.6093755468066493in"}

5.  [Gender : กราฟแสดงสัดส่วนเพศของลูกค้าที่ใช้บริการ\
    \
    ]{.mark}![](media/image13.png){width="3.0199650043744533in"
    height="2.588542213473316in"}

6.  [Prefered Order Cat : กราฟแสดงหมวดหมู่ของสินค้าที่ลูกค้าซื้อบ่อย\
    \
    ]{.mark}![](media/image14.png){width="3.026042213473316in"
    height="2.525041557305337in"}

7.  [Marital Status : กราฟแสดงสัดส่วนสถานภาพสมรสของลูกค้า\
    \
    ]{.mark}![](media/image15.png){width="3.276042213473316in"
    height="2.7555489938757654in"}

8.  [Complain : กราฟแสดงสัดส่วนของสถานะการ Complain ของลูกค้าในช่วง 1
    เดือนก่อนหน้า\
    \
    ]{.mark}![](media/image16.png){width="3.2239588801399823in"
    height="2.786639326334208in"}

<!-- -->

2.  [Numerical Data]{.mark}

    1.  [Tenure : กราฟแสดงสัดส่วนของระยะเวลาในการใช้บริการแพลตฟอร์ม\
        \
        ]{.mark}![](media/image17.png){width="3.1718755468066493in"
        height="2.646596675415573in"}

    2.  [Warehouse To Home : กราฟแสดงข้อมูลระยะห่างระหว่างที่เก็บสินค้ากับบ้าน\
        ของลูกค้า\
        \
        ]{.mark}![](media/image18.png){width="3.0781255468066493in"
        height="2.6045669291338585in"}

    3.  [Hour Spend On App : กราฟแสดงสัดส่วนเวลาที่ลูกค้าใช้แอพ\
        ]{.mark}![](media/image19.png){width="3.02373687664042in"
        height="2.5468755468066493in"}

    4.  [Number Of Device Registered : กราฟแสดงสัดส่วนจำนวนอุปกรณ์ที่ลูกค้าลง\
        ทะเบียนไว้\
        \
        ]{.mark}![](media/image20.png){width="3.088542213473316in"
        height="2.650234033245844in"}

    5.  [Satisfaction Score : กราฟแสดงคะแนนความพึงพอใจของลูกค้า\
        \
        ]{.mark}![](media/image21.png){width="3.088542213473316in"
        height="2.6601312335958007in"}

    6.  [Number Of Address : กราฟแสดงข้อมูลจำนวนที่อยู่ทั้งหมดของลูกค้า\
        \
        ]{.mark}![](media/image22.png){width="3.0657272528433945in"
        height="2.592014435695538in"}

[\
]{.mark}

7.  [OrderAmountHike From Last year : กราฟแสดงสัดส่วนของจำนวนออร์เดอร์\
    ที่เพิ่มขึ้นของลูกค้าแต่ละคนเมื่อเทียบกับปีที่แล้ว\
    \
    \
    ]{.mark}![](media/image23.png){width="2.869792213473316in"
    height="2.4680205599300087in"}

8.  [CouponUsed : กราฟแสดงสัดส่วนของจำนวนการใช้คูปองของลูกค้า\
    แต่ละคนในช่วง 1 เดือนก่อนหน้านี้\
    \
    ]{.mark}![](media/image24.png){width="2.884301181102362in"
    height="2.480902230971129in"}

9.  

10. [OrderCount : กราฟแสดงสัดส่วนของจำนวนออร์เดอร์รวมทั้งหมดในช่วง 1 เดือน\
    ที่ผ่านมา\
    \
    ]{.mark}![](media/image25.png){width="2.9615660542432196in"
    height="2.526042213473316in"}

11. [DaySinceLastOrder : กราฟแสดงสัดส่วนระยะเวลาตั้งแต่การซื้อครั้งล่าสุด\
    \
    ]{.mark}![](media/image26.png){width="3.3229166666666665in"
    height="2.7916666666666665in"}

12. [CashBackAmount : กราฟแสดงสัดส่วนของจำนวนเงินที่ลูกค้าได้รับคืน\
    \
    ]{.mark}![](media/image27.png){width="3.496032370953631in"
    height="2.810764435695538in"}

<!-- -->

2.  

3.  *[Churn Analysis]{.mark}*

    1.  [Categorical Data]{.mark}

        1.  [Preferred Login Device : ในกลุ่มลูกค้าที่ใช้ Mobile phone
            มีจำนวนคนที่ Churn ทั้งหมด 348 คน และคนที่ยังไม่ Churn ทั้งหมด 2417 คน\
            กลุ่มลูกค้าที่ใช้ Computer มีจำนวนคนที่ Churn ทั้งหมด 324 คน และคนที่ยังไม่
            Churn ทั้งหมด 1310 คน\
            กลุ่มลูกค้าที่ใช้ Phone มีจำนวนคนที่ Churn ทั้งหมด 276คน และคนที่ยังไม่
            Churn ทั้งหมด 955คน\
            \
            \
            ]{.mark}![](media/image28.png){width="3.3988003062117236in"
            height="2.887152230971129in"}

        2.  [City Tier :\
            ในกลุ่มลูกค้าที่อาศัยอยู่ในเมืองระดับ 1 มีคนที่ Churn ทั้งหมด 532 คน
            และมีคนที่ยังไม่ Churn ทั้งหมด 3134 คน\
            ในกลุ่มลูกค้าที่อาศัยอยู่ในเมืองระดับ 2 มีคนที่ Churn ทั้งหมด 48คน
            และมีคนที่ยังไม่ Churn ทั้งหมด 194 คน\
            ในกลุ่มลูกค้าที่อาศัยอยู่ในเมืองระดับ 3 มีคนที่ Churn ทั้งหมด 368 คน
            และมีคนที่ยังไม่ Churn ทั้งหมด 1354 คน\
            \
            ]{.mark}![](media/image29.png){width="3.3802088801399823in"
            height="2.8532939632545933in"}

        3.  [PreferredPaymentMode :\
            ในกลุ่มลูกค้าที่ชำระค่าสินค้าด้วยวิธี CC มีคน Churn ทั้งหมด 59 คน
            และมีคนที่ยังไม่ Churn 214 คน\
            ในกลุ่มลูกค้าที่ชำระค่าสินค้าด้วยวิธี COD มีคน Churn ทั้งหมด 105 คน
            และมีคนที่ยังไม่ Churn 260 คน\
            ในกลุ่มลูกค้าที่ชำระค่าสินค้าด้วยวิธี Cash on Delivery มีคน Churn ทั้งหมด
            23 คน และมีคนที่ยังไม่ Churn 126 คน\
            ในกลุ่มลูกค้าที่ชำระค่าสินค้าด้วยวิธี Credit Card มีคน Churn ทั้งหมด 193 คน
            และมีคนที่ยังไม่ Churn 1308 คน\
            ในกลุ่มลูกค้าที่ชำระค่าสินค้าด้วยวิธี Debit Card มีคน Churn ทั้งหมด 356 คน
            และมีคนที่ยังไม่ Churn 1958 คน\
            \
            ในกลุ่มลูกค้าที่ชำระค่าสินค้าด้วยวิธี E-wallet มีคน Churn ทั้งหมด 140 คน
            และมีคนที่ยังไม่ Churn 474 คน\
            ในกลุ่มลูกค้าที่ชำระค่าสินค้าด้วยวิธี UPI มีคน Churn ทั้งหมด 72 คน
            และมีคนที่ยังไม่ Churn 342 คน\
            \
            ]{.mark}![](media/image30.png){width="3.4739588801399823in"
            height="2.8987248468941385in"}

        4.  [Gender : ในกลุ่มผู้ใช้งานที่เป็นผู้หญิงมีคนที่ Churn ทั้งหมด 348 คนและไม่
            Churn 1898 คน และในกลุ่มลูกค้าที่เป็นผู้ชายมีคนที่ Churn ทั้งหมด 600
            คนและไม่ Churn 2784 คน\
            \
            ]{.mark}![](media/image31.png){width="3.390577427821522in"
            height="2.8836811023622047in"}

        5.  

        6.  [Preferred Order Cat :\
            ในกลุ่มลูกค้าที่ต้องการซื้อสินค้าประเภท Fashion มีคน Churn ทั้งหมด 128 คน
            และมีคนยังไม่ 698 คน\
            ในกลุ่มลูกค้าที่ต้องการซื้อสินค้าประเภท Grocery มีคน Churn ทั้งหมด 20 คน
            และมีคนยังไม่ 390 คน\
            ในกลุ่มลูกค้าที่ต้องการซื้อสินค้าประเภท Laptop & Accessory มีคน Churn
            ทั้งหมด 210 คน และมีคนยังไม่ 1840 คน\
            ในกลุ่มลูกค้าที่ต้องการซื้อสินค้าประเภท Mobile มีคน Churn ทั้งหมด 220 คน
            และมีคนยังไม่ 589 คน\
            ในกลุ่มลูกค้าที่ต้องการซื้อสินค้าประเภท Mobile Phone มีคน Churn ทั้งหมด
            350 คน และมีคนยังไม่ 921 คน\
            ในกลุ่มลูกค้าที่ต้องการซื้อสินค้าประเภท Others มีคน Churn ทั้งหมด 20 คน
            และมีคนยังไม่ 244 คน\
            \
            ]{.mark}![](media/image32.png){width="3.3199726596675414in"
            height="2.8281255468066493in"}

        7.  

        8.  [Martial Status :\
            ในกลุ่มลูกค้าที่สถานะโสดมีคนที่ Churn ทั้งหมด 480 คนและไม่ Churn 1316 คน
            ในกลุ่มลูกค้าที่หย่ากันแล้วมีคนที่ Churn 124 คนและไม่ Churn 724
            และในกลุ่มลูกค้าที่แต่งงานแล้วมีคนที่ Churn 344 คนและไม่ Churn 2642 คน\
            \
            ]{.mark}![](media/image33.png){width="3.3209022309711287in"
            height="2.810764435695538in"}

        9.  [Complain : ในกลุ่มลูกค้าที่ไม่ได้ Complain มีคนที่ Churn ทั้งหมด 440 คน
            และไม่ Churn 3586 คน และ ในกลุ่มลูกค้าที่ Complain มีคนที่ Churn ทั้งหมด
            508 คน และไม่ Churn 1096 คน\
            \
            ]{.mark}![](media/image34.png){width="3.276042213473316in"
            height="2.7541940069991253in"}

    2.  

    3.  [Numerical Data]{.mark}

        1.  [Tenure : ยิ่งระยะเวลาการในการใช้บริการนานขึ้น โอกาสการ Churn
            จะมีแนวโน้มที่จะลดลงเรื่อยๆ\
            \
            ]{.mark}![](media/image35.png){width="3.0296587926509186in"
            height="2.5364588801399823in"}

        2.  [WarehouseToHome : โอกาสการ Churn จะมีแนวโน้มลดลงเมื่อระยะห่าง\
            มากขึ้น\
            \
            ]{.mark}![](media/image36.png){width="2.994792213473316in"
            height="2.5134853455818025in"}

[\
]{.mark}

3.  [HourSpendOnApp : โอกาสการ Churn จะสูงที่สุด เมื่อชั่วโมงในการใช้แอปเท่ากับ 3
    ชั่วโมง\
    \
    ]{.mark}![](media/image37.png){width="2.957680446194226in"
    height="2.4392366579177605in"}

4.  [NumberOfDeviceRegistered : จำนวนอุปกรณ์ ในช่วง 3 - 5 อุปกรณ์ มีโอกาสการ
    Churn ใกล้เคียงกัน\
    \
    ]{.mark}![](media/image38.png){width="2.901042213473316in"
    height="2.44242125984252in"}

[\
]{.mark}

5.  [SatisfactionScore : จากกราฟจะเห็นได้ว่าโอกาสการ Churn จะมีมากที่สุดเมื่อ
    คะแนนมีค่าเท่ากับ 3\
    \
    ]{.mark}![](media/image39.png){width="2.9393208661417325in"
    height="2.512153324584427in"}

6.  [NumberOfAddress : โอกาสการ Churn มีมากเมื่อจำนวนที่อยู่น้อย
    และเมื่อจำนวนที่อยู่มากขึ้น แนวโน้มของการ Churn ลดลง\
    \
    ]{.mark}![](media/image40.png){width="2.9346423884514437in"
    height="2.4982633420822395in"}

[\
]{.mark}

7.  [OrderAmountHikeFromLastYear : ​\
    จะเห็นได้ว่าเมื่อเปอร์เซนต์จำนวนออเดอร์ที่เพิ่มขึ้น อาจจะส่งผลให้ โอกาสการ Churn
    ลดลง\
    \
    ]{.mark}![](media/image41.png){width="3.037141294838145in"
    height="2.6093755468066493in"} []{.mark}

8.  [CouponUsed : เมื่อจำนวนคูปองที่ใช้มากขึ้น โอกาสการ Churn มีแนวโน้มที่ลดลง
    แต่เป็นแนวโน้มที่ไม่ชัดเจนมากนัก กล่าวคือจำนวนคูปองอาจไม่ได้ส่งผลต่อการ Churn มาก\
    \
    ]{.mark}![A graph of a graph Description automatically
    generated](media/image42.png){width="3.0677088801399823in"
    height="2.608759842519685in"}

9.  [OrderCount : ในช่วงที่มีจำนวน order น้อย โอกาสการ Churn จะมากว่า ช่วงที่
    order เยอะ\
    \
    ]{.mark}![](media/image43.png){width="3.0729166666666665in"
    height="2.6354166666666665in"}

10. [DaySinceLastOrder : เมื่อจำนวนวันมากขึ้น แนวโน้มการ Churn จะลดลง\
    \
    ]{.mark}![](media/image44.png){width="3.2968755468066493in"
    height="2.751435914260717in"}

11. 

12. [CashbackAmount : เมื่อจำนวนเงินที่ลูกค้าได้รับ การ Churn
    มีแนวโน้มที่จะลดลงตามลำดับ\
    \
    ]{.mark}![](media/image45.png){width="3.2864588801399823in"
    height="2.719465223097113in"}

**[Modeling method]{.mark}**

-   [ทำการเตรียมข้อมูลโดยการแยก ข้อมูลออกเป็นตารางที่มี data type เป็น num (int,
    float) และที่มี data type เป็น object]{.mark}![A screenshot of a
    computer Description automatically
    generated](media/image46.png){width="6.267716535433071in"
    height="2.4722222222222223in"}

<!-- -->

-   [ข้อมูลที่มี data type เป็น num จะทำการตัด customer ID ออกไป]{.mark}

-   [ข้อมูลที่มี data type เป็น object จะใช้ฟังก์ชัน get_dummies เพื่อทำการแยกเป็น
    column ที่มีแค่เลข 0 กับ 1 จากนั้น drop column ที่ไม่ได้ใช้ออก
    แล้วรวมเข้าด้วยกัน]{.mark}![A screenshot of a computer Description
    automatically
    generated](media/image47.png){width="6.267716535433071in"
    height="2.4166666666666665in"}![A screenshot of a computer
    Description automatically
    generated](media/image48.png){width="6.267716535433071in"
    height="2.263888888888889in"}

**[Decision tree]{.mark}**

-   [ใช้ library sklearn เพื่อแบ่งข้อมูลสำหรับการ train และ test โดยกำหนดให้
    มีอัตราส่วนเป็น 70:30]{.mark}

<!-- -->

-   [จากนั้นทำการ plot decision tree]{.mark}![A screenshot of a computer
    Description automatically
    generated](media/image49.png){width="6.267716535433071in"
    height="1.1111111111111112in"}

-   [ทำการหาค่า feature important พบว่าข้อมูลจาก column "Tenure"
    มีอิทธิพลต่อการตัดสินใจมากที่สุด]{.mark}![A screenshot of a computer
    Description automatically
    generated](media/image50.png){width="6.267716535433071in"
    height="1.8194444444444444in"}

-   [Classification report ให้ค่า accuracy อยู่ที่ 0.89]{.mark}![A screenshot
    of a computer Description automatically
    generated](media/image51.png){width="6.267716535433071in"
    height="2.263888888888889in"}

**[Logistic Regression]{.mark}**

-   [ทำการ import Logistic Regression model กำหนดค่า max_iter ไว้ที่ 10,000
    เพื่อให้ algorithm ของ model มีเวลาคำนวณมากขึ้น]{.mark}![A computer screen
    with text and numbers Description automatically
    generated](media/image52.png){width="6.267716535433071in"
    height="1.6944444444444444in"}

-   [Classification report ให้ค่า accuracy อยู่ที่ 0.90]{.mark}![A screenshot
    of a computer program Description automatically
    generated](media/image53.png){width="6.267716535433071in"
    height="1.8333333333333333in"}

**[K-neighbors Classifier]{.mark}**

-   [Classification report ให้ค่า accuracy อยู่ที่ 0.87]{.mark}![A screenshot
    of a computer program Description automatically
    generated](media/image54.png){width="6.267716535433071in"
    height="3.5277777777777777in"}

**[Random Forest Classifier]{.mark}**

-   [ทำการ import RandomForestClassifier เพื่อเรียกใช้ model จากนั้นเลือกใช้เกณฑ์
    gini พร้อมกับกำหนดให้ค่า n_estimators = 100, random_state = 1 และ
    bootstrap = True]{.mark}![A screen shot of a computer Description
    automatically
    generated](media/image55.png){width="6.267716535433071in"
    height="2.388888888888889in"}

-   [Classification report ให้ค่า accuracy อยู่ที่ 0.96]{.mark}![A screenshot
    of a computer Description automatically
    generated](media/image56.png){width="6.267716535433071in"
    height="1.7777777777777777in"}

-   [ทำการสร้าง confusion matrix เพื่อดูผลการ predict]{.mark}![A screenshot
    of a computer program Description automatically
    generated](media/image57.png){width="6.267716535433071in"
    height="1.4305555555555556in"}

**[Modeling results and discussion]{.mark}**

[จากการทำ decision tree ทำให้เห็นว่า Tenure เป็นตัวแปรที่มีค่า feature importance
สูงที่สุด กล่าวคือมีอิทธิพลต่อการ churn มากที่สุด รองลงมาเป็น Complain,
NumberOfAddress, CashbackAmount, DaySinceLastOrder,
NumberOfDeviceRegistered, SatisfactionScore, CouponUsed และ
PreferredPaymentMode_UPI ส่วน column อื่น ๆ จะไม่มีอิทธิพลต่อการ churn\
และจากการทำ visualization ทำให้ทราบว่า
ลูกค้าที่ใช้บริการมาไม่นานมักจะมีแนวโน้มจะเลิกใช้\
บริการ]{.mark}

> ![A diagram of a data flow Description automatically
> generated](media/image58.png){width="4.390625546806649in"
> height="5.014429133858267in"}

[ผลลัพธ์ที่ได้จากการทำ model พบว่าค่า accuracy ที่ได้จากการทำ decision tree
มีค่าน้อยกว่า logistic regression เป็นเพราะความสัมพันธ์ของ column churn กับ
column อื่น ๆ เป็นไปในทางเชิงเส้น\
มากกว่า ทำให้การทำ model แบบ linear สามารถ predict ได้แม่นยำมากกว่าการทำ
decision tree ที่จะถนัดกับความสัมพันธ์แบบ non-linear มากกว่า]{.mark}

[ส่วน model แบบ K-Nearest Neighbor จะให้ค่า accuracy ที่ต่ำที่สุด
แม้ในกรณีที่มีการปรับค่า n_neighbors หรือการใช้วิธีแบบ euclidean\
ในขณะที่ model แบบ Random Forest จะให้ค่า accuracy ที่สูงที่สุด
สามารถประเมินผลได้จาก\
การดู confusion matrix ซึ่งจะเห็นว่าถ้าค่าจริงเป็น 1 จะสามารถ predict ได้ว่าเป็น 1
จริง ๆ อยู่ที่ 245 samples จากทั้งหมด 298 samples คิดเป็น 82.21% ในขณะที่
ถ้าค่าจริงเป็น 0 จะสามารถ predict ได้ว่าเป็น 0 จริง ๆ อยู่ที่ 1378 samples จากทั้งหมด
1391 samples คิดเป็น 99.06% อัตราส่วนนี้แสดงให้ถึงค่า recall หรือค่า true positive
rate]{.mark}

![A chart of a blue yellow and purple box Description automatically
generated with medium
confidence](media/image59.png){width="4.776042213473316in"
height="4.006310148731409in"}

**[Conclusion]{.mark}**

[ในการทำงานสามารถแบ่งขั้นตอนได้เป็นสองส่วนหลัก ๆ
ส่วนแรกคือการเตรียมข้อมูลและวิเคราะห์\
ข้อมูล และส่วนที่สองคือการทำ model สำหรับทำนาย\
​ส่วนแรกเริ่มจากการเตรียมข้อมูล โดยได้พบข้อมูลที่หายไปซึ่งแก้ไขด้วยการใช้ค่ามัธยฐาน จากนั้น\
ทำการแสดงข้อมูลโดยวิเคราะห์สัดส่วนข้อมูลแต่ละคอลัมน์ก่อนจากนั้นนำแต่ละคอลัมน์มาวิเคราะห์กับค่า
churn]{.mark}

[ส่วนที่สองเป็นการทำ modeling โดยมีการทำทั้งหมด 4 แบบ คือ Decision tree,
Logistic Regression, K-neighbors Classifier และ Random Forest Classifier
ซึ่งจากการทำ decision tree ทำให้เห็นว่า Tenure เป็นตัวแปรที่มีค่า feature
importance สูงที่สุด กล่าวคือมีอิทธิพลต่อการ churn มากที่สุด และเมื่อเปรียบเทียบ model
ทั้งหมด จะพบว่า model แบบ Random Forest จะให้ค่า accuracy ที่สูงที่สุด]{.mark}

[สุดท้ายในการทำ model สามารถพัฒนาเพิ่มด้วยการใช้วิธีการทำนายอื่น ๆ เพื่อเปรียบเทียบ\
วิธีที่มีประสิทธิภาพที่สุด]{.mark}
