#  data ScienceEESE 
> Author : Aaron Augustine

> Star the gist so that I can get a consensus on how many people are using this resource
> 
[Github Repo Link for all ESE Notes](https://github.com/ToothlessRider/Sem_3_Notes.git)

# Table of Contents
- [data ScienceEESE](#data-scienceeese)
- [Table of Contents](#table-of-contents)
  - [Previous Year Questions](#previous-year-questions)
    - [**Step 1: Formulate Hypotheses**](#step-1-formulate-hypotheses)
    - [**Step 2: Test Statistic**](#step-2-test-statistic)
    - [**Step 3: Critical Value and Significance Level**](#step-3-critical-value-and-significance-level)
    - [**Step 4: Decision Rule**](#step-4-decision-rule)
    - [**Step 5: Conclusion**](#step-5-conclusion)
    - [**Inference**](#inference)


## Previous Year Questions

Q1. a. **The mean of a manufacturing process is known to be 50 with a standard deviation of 2.5. The manufacturing manager may welcome any change is mean value towards higher side but would like to safeguard against decreasing values of mean. He takes a sample of 12 items that gives a mean value of 48.5. What inference should the manager take for the manufacturing process on the basis of sample results? Use 5% level of significance for the purpose.**

Ans. 
This is a one-tailed hypothesis test (left-tailed) for the population mean since the manufacturing manager is concerned about a **decrease** in the mean value. Here's how the analysis proceeds:

---

### **Step 1: Formulate Hypotheses**
- Null Hypothesis ($ H_0$ ): The population mean is $\mu_0 = 50$. (No decrease in mean)
- Alternative Hypothesis ( $H_1$ ): The population mean is $\mu < 50$ . (Mean has decreased)

---

### **Step 2: Test Statistic**
We use the $z$-test since the population standard deviation is known.

The $z$-test statistic is given by:
$z = \frac{\bar{x} - \mu_0}{\sigma / \sqrt{n}}$

Where:
- $\bar{x} = 48.5$ (Sample mean)
- $\mu_0 = 50$ (Population mean under $H_0$)
- $\sigma = 2.5$ (Standard deviation)
- $n = 12$ (Sample size)

Substitute the values:
$z = \frac{48.5 - 50}{2.5 / \sqrt{12}} = \frac{-1.5}{0.7217} \approx -2.08$

---

### **Step 3: Critical Value and Significance Level**
For a one-tailed test at $\alpha = 0.05$, the critical value of $z$ is:
$z_{\text{critical}} = -1.645 \quad (\text{from the standard normal table}).$

---

### **Step 4: Decision Rule**
- If $z \leq z_{\text{critical}}$, reject $H_0$ (mean has decreased).
- Otherwise, fail to reject $H_0$.

---

### **Step 5: Conclusion**
The calculated $z$-value is $-2.08$, which is **less than** the critical value $-1.645$. Thus, we reject the null hypothesis.

---

### **Inference**
The sample provides sufficient evidence to conclude that the mean of the manufacturing process has **decreased below 50**. The manager should investigate and take corrective action to safeguard the process.

--- 

Q1. b. **Sanju Hotel near the bus stop at Mumbai has been having average sales of 500 coffee cups per day. Because of the development of railway station nearby, it expects to increase its sales. During the first 12 days after the start of the railway station, the daily sales were as under: 550, 570, 490, 615, 505, 580, 570, 460, 600, 580, 530, 526 On the basis of this sample information, can one conclude that Sanju Hotel's sales have increased? Use 5% level of significance.**

Ans .

---

Q1. c. **A non-normal distribution representing the number of trips performed by lorries per week in a coal field has a mean of 100 trips and variance of 121 trips. A random sample of 36 lorries is taken from the non-normal population. What is the probability that the sample mean is**
i) greater than 105 trips
ii) less than 102 trips and
iii) between 101 trips and 103 trips?
(Use central limit theorem)

Ans. 


--- 

Q2. a. **The analyst of the study divided the entire population of the schools into schools in rural locations, semi-urban locations and urban locations. The analyst prefers to use proportionate stratified sampling in which the categories of location represent strata. The total number of schools in the state is 8000 which is divided into three strata of rural, semi-urban and urban locations. The number of schools in the rural, semi-urban and urban locations are 4000, 2400 and 1600, respectively. If the proportionate stratified sampling is to be used wih the sampling size of 30, determine the number of sampling units for each category of locations.**

Ans. 

---


Q2. b. **A sample of 11 circuits from a large normal population has a mean resistance of 2.20 ohms. Population standard deviation is not known. Sample standard deviation is 0.35 ohms. Determine a 95% confidence interval for the true mean resiatance of the population.**

Ans. 


---

Q2. c. **What are the different five questions related to the model (5) CO2 evaluation.**


Ans.


---


Q2. d. **Explain convenience samples and voluntary samples with (5) CO1 examples. (At least 2 examples for each).** 

Ans. 


---

Q3. a. **The education department of a state wants to study the standard of education in schools. The analyst of the study divided the entire population of the schools into schools in rural locations, semi-urban locations and urban locations. He found more variation between schools in rural locations because of varying infrastructure than the variation between schools in semi-urban locations. Same is the case between semi-urban locations an urban locations. The analyst prefers to use disproportionate stratified sampling in which the categories of location represent strata. The total number of schools in the state is 1200. The number of schools in the rural, semi-urban and urban locations 25 10 are 500, 400 and 300, respectively. The variance of educational standard of the schools in these locations are 49, 16 and 4, respectively. If the disproportionate stratified sampling is to be used wih the sampling size of 90, determine the number of sampling units for each category of locations.**


Ans. 


---


Q3. b. **A random sample of 100 people shows that 25 have opened IRA (individual retirement arrangement) this year. Construct a 95% confidence interval for true proportion of people who have opened IRA. (Use population proportion).**

Ans. 


---

Q3. c. **Suppose a certain hotel management is interested in determining the percentage of hotel's guests who stay for more than 3 days. The reservation manager wants to be 95% confident that the percentage has been estimated to be within +/- 3% of the true value. What is the most conservative sample size needed for this problem?**

Ans. 


---


Q3. d. **Which are five different questions for data understanding? Discuss in detail.**

Ans. 


--- 

Q4. a. **Two researchers adopted different sampling techniques while investigating the same group of customers to find the number of customers falling in different buying-intelligence levels. Test if "Researcher" is independent of "No. of customers in each level" using chi-square distribution. (use alpha=0.05)**
![alt text](image-14.png)

Ans. 

---


Q4. b. **Out of hundreds of people. You randomly chose 46 men with a mean of 86 inches (height) with a standard deviation of 6.2 inches. Determine that the selected men are tall enough. Take the confidence level as 95%.**

Ans. 


--- 

Q4. c. **Why is data science popular today? Explain in detail.**

Ans. 


---

Q4. d. **Explain Central Limit Theorem and alternative version of Central Limit Theorem in detail.**

Ans. 


--- 

Q5. a. **Explain point and interval estimators in detail with proper example.**

Ans. 


---


Q5. b. **You are teaching an online course and based on your internal surveys claim that 60% of your students like your course. A course review committee is skeptical about your claims and wants to test them. How would they go about this. Out of 100 students 62 students said yes. The confidence level is 90%**

Ans. 

---

Q5. c. **Explain statistical modelling of data in detail with an appropriate example**

Ans. 


--- 

Q5. c. **What are the different five questions for data preparation? Explain in detail with proper example.**

Ans. 


---


