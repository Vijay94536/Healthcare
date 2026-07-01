1. To record the patient statistics, the agency wants to find the age category of people who frequents
the hospital and has the maximum expenditure.
a. To find the category that has the highest frequency of hospital visit, we can use graphical analysis. A
histogram would display the number of occurrences of each age category. The as.factor() is called to
make sure that the categories are not treated as numbers. Outlier treatments: None
path&lt;-&quot;C:/Users/bijaykumar/Downloads/HospitalCosts.csv&quot;
data&lt;-read.csv(path)
head(data)
data_hist&lt;-hist(data$AGE,bin=10)
data_cat&lt;-as.factor(data$Age)
summary(data_cat)
Results:-
I have plotted histogram to check out occurrence of each category. From Histogram we see that the
tallest bar is between 0-3(X-axis  data$Age) which represents Infants.

b. To find the category with the maximum expenditure, we need to add the expenditure for each age,
and find the maximum value from the sum. We will use the aggregate function to add the values of total
charges according to the values of age.
p &lt;- aggregate(TOTCHG~AGE,FUN=sum,data=data)
max(p)
Results:-
I have used aggregate function to check relationship of expenditures with age. I have taken sum and
then max of results to get the maximum value with respect to expenditure. Age 0 has highest value of
6,78,118 and next age group is at Age 15 where 1,11,747
2. In order of severity of the diagnosis and treatments and to find out the expensive treatments, the
agency wants to find the diagnosis related group that has maximum hospitalization and expenditure.
x&lt;-as.factor(data$APRDRG)
y&lt;-which.max(summary(x))
df&lt;-aggregate(TOTCHG~APRDRG,FUN=sum,data=data)
Results:-
I have converted APDRG to factor and attached which max function to find the index of max value and
then sum of the aggregates of Total charges with respect to ARPDRG. The code as.factor treats the

column as numbers not as categories. So here we get max value as 640. Highest total hospitalization
cost is 4,37,978.

3. To make sure that there is no malpractice, the agency needs to analyze if the race of the patient is
related to the hospitalization costs.
e&lt;-colSums(is.na(data))
summary(as.factor(data$RACE))
data&lt;-na.omit(data)
model&lt;-aov(TOTCHG~RACE,data=data)
summary(model)
summary(data$RACE)
Results:-
I used is.na function to find missing data, found one missing. Used na.omit to omit missing values.
Converted column race to factor. Used ANOVA function to find variance across race and total charges.
The summary provides high p value which is 0.943 which is very high. That itself suggests that there is no
relation between race and total charges.

4. To properly utilize the costs, the agency has to analyze the severity of the hospital costs by age and
gender for proper allocation of resources.
CODE:-
str(data$FEMALE)
table(data$FEMALE)
model1&lt;-lm(data$TOTCHG~data$AGE+data$FEMALE, data = data)
summary(model1)
Results:-
-ve coefficient shows females bear less hospitalization costs.
5. Since the length of stay is the crucial factor for inpatients, the agency wants to find if the length of
stay can be predicted from age, gender, and race.
LOS - Dependent var.
AGE, GENDER AND RACE - Independent var.

Summary(lm(LOS~AGE+RACE+FEMALE,data = data))
Results:-
Used LOS as dependent var. to check whether it correlates with age ,race and gender. High p val ,all
greater than .05(p = .74), so no linear relationship with LOS not possible to predict.
6. To perform a complete analysis, the agency wants to find the variable that mainly affects the hospital
costs.
Code:-
Model&lt;-lm(TOTCHG~.,data=data)
Summary(Model)
Results:-
LOS has estimate value of 742.96 which cost per day. Residuals have no relationship
