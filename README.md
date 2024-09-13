# Saudi_Stock_Market_Prediction
# This project is made for Tuwaiq Data Scince Bootcamp 
# the data is collected from sa.investing.com
# the summary model is from https://huggingface.co/malmarjeh/mbert2mbert-arabic-text-summarization
# hugging face space of the project https://huggingface.co/spaces/Faisal-Data/Saudi_Stock_Market_Prediction

Saudi stock market prediction with simple summarized info about the chosen company

For the prediction, I have used scikit-learn’s linear regression. The prediction is quite basic and should not be taken seriously, as I do not have enough data to build a robust prediction engine.

For the summary, I initially used a library to fetch information from Wikipedia pages and processed the text using a pipeline created by malmarjeh on Hugging Face, specifically the model “malmarjeh/mbert2mbert-arabic-text-summarization.” I also tried using “aubmindlab/aragpt2-large,” a GPT-2 based text generation model, but the outputs were not reliable.

The first thing to discuss is the data. Free data for the Saudi stock market is not easy to obtain. Therefore, I used the list from sa.investing.com, which shows daily market prices. I collected data from two different days: Day 1 for the main data and Day 2 for the price, to perform the regression. 
I used pandas to manipulate the sheets and scikit-learn for the prediction. Then, I initiated the model for the summary. After that, I created a simple function to plot the price difference, with a rule to make the plot clearer if the difference is small.

The main function starts by getting the name of the company and follows these steps to complete the task: first, fetch the Wikipedia text, then retrieve the necessary data from the Excel sheet, and put it into the pipeline for prediction. Finally, the information and the Wikipedia text are used to generate the summary and data prediction.

finally I used gradio to make the interface.

To run the code, you need to install all the libraries listed in the requirements.txt file and ensure that the stock_data.xlsx file is in the correct directory. Alternatively, you can try it on the Hugging Face space: https://huggingface.co/spaces/Faisal-Data/Saudi_Stock_Market_Prediction.

Example input:
name	final price today	highest price today	lowest price today	change today	percentage of change today	size	last update time	future_price
التعاونية	155.4	156.6	154.2	0.4	0.26%	181.41K	15:15:59	152.6
![image](https://github.com/user-attachments/assets/d46ec294-25a9-493e-915c-b1d54a30ebc5)

Example output:
{
"اخر قيمة لليوم"
:
155.4
,
"اعلى قيمة لليوم"
:
156.6
,
"اقل قيمة لليوم"
:
154.2
,
"التغير"
:
0.4
,
"نسبة التغير"
:
0.0026
,
"الحجم"
:
"181.41K"
,
"اخر تحديث (بالساعة)"
:
"15:15:59"
,
"السعر المتوقع"
:
153.72336756333198
,
"التوقع والملخص"
:
"سهم شركة التعاونية سعره الحالي155.4 اليوم مع تغيير قدره 0.4. ويتوقع ان يصبح سعره 153.72336756333198 والجدير بالذكر ان شركة " التعاونية للتأمين " تدعم خدماتها ب نصف مليار ريال"
,
"مقال ويكيبيديا الكامل"
:
"شركة التعاونية للتأمين هي شركة مساهمة سعودية، تأسست في التاسع من يناير عام 1986، برأس مال نصف مليار ريال سعودي، وتعد المؤسسة العامة للتقاعد أحد المساهمين الرئيسيين للشركة إذ تبلغ نسبة تملكها 23.70%، أما المؤسسة العامة للتأمينات الاجتماعية فتملك 22.80%، ويتركز نشاط الشركة في مزوالة أعمال التأمين التعاوني وكل ما يتعلق بهذه الأعمال من توكيلات وإعادة التأمين، ويتمثل النشاط الرئيس للشركة في تقديم خدمات تأمين السيارات، التأمين البحري، تأمين الحريق، التأمين الطبي، التأمين الهندسي، تأمين الطيران، وتأمين التكافل والحوادث المتنوعة. تتبع للشركة التعاونية للتأمين 3 شركات هي: شركة المتحدة للتأمين. شركة وصيل. شركة التعاونية للاستثمار العقارية."
}

Finally there is a file called "Video explanation of the code.mkv" which is a video explanation of how the code works and a fast example of the output. you need to install the video and play it in any available video player in your device

