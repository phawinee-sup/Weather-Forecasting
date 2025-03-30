# Weather-Forecasting
## Overview ##
1. ในการสอบครั้งนี้ท้าทาย ให้ผู้เข้าสอบ AI4BA รุ่น 4 ร่วมพัฒนาแบบจำลองการพยากรณ์อุณหภูมิ temp ที่แม่นยำสำหรับสถานีอากาศท้องถิ่นในประเทศไทย โดยใช้ข้อมูลสภาพอากาศในอดีตจากสถานีต่างๆ ทั่วประเทศหลายจังหวัด โดยอาศัยปัจจัยทางอุตุนิยมวิทยาและภูมิศาสตร์ที่หลากหลาย ผู้เข้าสอบจะต้องทำนายอุณหภูมิ (temp) ในอนาคต ใน file test.csv โดยอาศัยข้อมูลทดลอ (train dataset) จาก train.csv
2. กำหนดให้ Model ที่ใช้ในการสอบได้ จำนวน 6 โมเดลตามตาราง โดยให้ใช้แค่ Library sklearn เท่านั้น

| Algorithm               | How to Call
| ----------------------- | ------------------------------------------- |
| Linear Regression        | `from sklearn.linear_model import LinearRegression`<br> `model = LinearRegression()` |
| Ridge Regression         | `from sklearn.linear_model import Ridge`<br>`model = Ridge()`            |
| Lasso Regression         | `from sklearn.linear_model import Lasso`<br>`model = Lasso()`            |
| Elastic Net              | `from sklearn.linear_model import ElasticNet`<br>`model = ElasticNet()`  |
| Polynomial Regression    | `from sklearn.preprocessing import PolynomialFeatures`<br>`from sklearn.linear_model import LinearRegression`<br>`poly = PolynomialFeatures(degree=20)`<br>`model = LinearRegression()` |
| Random Forest Regressor  | `from sklearn.ensemble import RandomForestRegressor`<br>`model = RandomForestRegressor()` |

## Description ##
จุดมุ่งหมายการทดสอบนี้เน้นการพัฒนาโมเดลเพื่อพยากรณ์อุณหภูมิ temp สำหรับสถานีตรวจวัดอากาศท้องถิ่นในประเทศไทย โดยใช้ชุดข้อมูลที่ประกอบด้วยข้อมูลจากสถานีตรวจวัดอากาศทั่วประเทศ
- ผู้เข้าแข่งขันจะต้องพัฒนาโมเดลที่สามารถทำนายอุณหภูมิได้อย่างแม่นยำโดยโดยใช้ข้อมูลจาก train.csv ที่มีให้ ความท้าทายนี้จะช่วยปรับปรุงความเข้าใจเกี่ยวกับปัจจัยที่ส่งผลต่อสภาพอากาศท้องถิ่นและเพิ่มประสิทธิภาพในการพยากรณ์อากาศระดับตำบลต่อไป

## Evaluation ##
การประเมินผลโมเดลจะใช้ค่า Root Mean Squared Error (RMSE) ระหว่างค่าอุณหภูมิที่ทำนายได้และค่าจริง โดยคำนวณดังนี้:

`RMSE = sqrt(1/n * Σ(y_pred - y_true)^2)`

โดยที่:
n คือจำนวนการทำนายทั้งหมด
y_pred คือค่าอุณหภูมิที่ทำนายได้
y_true คือค่าอุณหภูมิจริง