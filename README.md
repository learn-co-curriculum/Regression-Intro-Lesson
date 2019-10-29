
# Linear Relationships and Prediction

**Course**: Data Science   <br/>
**Mod**: 1 <br/>
**Topic**: Linear Relationships, Regression                <br/>
**Amount of time**: 1.5 hours <br/>
**Author**: Greg Damico  
Ported from the ds-lesson-starters-repo [here](https://github.com/learn-co-curriculum/ds-lessons-starter/tree/master/lesson-plans-by-mod/Module-1/simple_linear_regression/linear-reg-gd). 


***

## Lesson Summary:

#### Topic:
Correlation, covariance, linear regression

#### Learn.co material:
- https://learn.co/tracks/data-science-career-v1-1/section-01/section-10-introduction-to-linear-regression/introduction

This is a list of labs related to the topic that we’re teaching. These are the key labs that students should have completed before the lesson.
#### Prerequisite knowledge/ Prework:
Basic statistical notions like mean and variance. Recall: <br/>
$\mu = \frac{1}{n}\Sigma^n_{i = 1}x_i$ <br/> $\sigma^2 = \frac{\Sigma^n_{i = 1}(x_i - \mu)^2}{n}$

#### Learning goals for this lesson:
Students will be able to:
1. Calculate covariance and correlation of variables.
2. Construct a simple linear regression:

    a. state the assumptions for a linear regression;
    
    b. use statsmodels to construct an ordinary least-squares regression; and
    
    c. interpret significance and p-values
3. Explain the Coefficient of Determination.

#### Misconceptions:
Theoretical underpinnings of mathematical methods are not important to grasp for the practicing data scientist.

#### Materials

Anscombe's Quartet: https://www.desmos.com/calculator/paknt6oneh

Playing with the Regression Line: https://www.desmos.com/calculator/jwquvmikhr

Slides on Linear Regression: https://docs.google.com/presentation/d/1mC-049woTZ27HwcGaNLj0gHOVOid1q1LmVM6cU80iJs/edit?usp=sharing

Jupyter notebook: linear_relationships_and_prediction

Supplemental:
	* Dataset on buses and population?

***


## Lesson Outline:

**Step**: Problem <br/>
**Time**: [2] min

_Goal/Scenario:_<br/>
You suspect that one variable seems to be correlated with another. For example, cities with more buses have higher populations.

_Learning Goals in sequence:_<br/>
Students will be able to:
1. Calculate covariance and correlation of variables.
2. Construct a simple linear regression:

    a. state the assumptions for a linear regression;
    
    b. use statsmodels to construct an ordinary least-squares regression; and
    
    c. interpret significance and p-values
3. Explain the Coefficient of Determination.

**Step**: Activation <br/>
**Time**: [5] min

Solicit the class for more examples of correlated variables. Students already have the idea of a variable having a certain shape or distribution or spread. The new idea is that two variables may have shapes such that one is a function of the other. As X increases, so does Y, OR: As X increases, Y decreases.


**Step 1**: Learning Goal 1: Calculate covariance and correlation of variables. <br/>
**Time**: [20] min

_Demonstrate_: <br/>
### Definition of Covariance

For two random variables X and Y, each with n values:

$\sigma_{XY} = \frac{\Sigma^n_{i = 1}(x_i - \mu_x)(y_i - \mu_y)}{n}$


### Definition of Correlation

Pearson Correlation $r = \frac{\Sigma^n_{i = 1}(x_i - \mu_x)(y_i - \mu_y)}{\sqrt{\Sigma^n_{i = 1}(x_i - \mu_x)^2\Sigma^n_{i = 1}(y_i -\mu_y)^2}}$



**Refer to slides for examples.**

\[Time permitting: Correlation is not causation. (There's good material on learn.co about this.)\]

_Application_: <br/>
Ask students to perform simple calculations of covariance and correlation.

Use simple datasets like X = (1, 5, 6) and Y = (4, 7, 7). Here X could be number of buses (in hundreds, perhaps) and Y could be population (in tens of thousands, perhaps).

_Informal assessment_: <br/>
Poll the class: Thumbs up?

**Step 2**: Learning Goal 2: Construct a simple linear regression. <br/>
**Time**: [30] min

_Demonstrate_: <br/>

### Statistical Learning Theory

Important distinction between dependent and independent variables. Beware that an image on learn.co assimilates these to effect and cause, respectively!

A better explanation is that the independent variable is what can be directly manipulated and the dependent variable is what cannot be (but is nevertheless of great interest). But this is also problematic since we often take e.g. time as an independent variable.

Maybe best: The dependent variable is the one we want to think of as a function of the independent variable: "How does \[dep\] change as a function of \[indep\]?"

This is the proper interpretation of a statistical _model_.

Simple idea: Line as model!

This model has two _parameters_: _slope_ and _y-intercept_.

Model Validation?

Loss Functions? Quick version (more later): The loss function represents the _loss_ of accuracy that we get by assuming the truth of our model. We therefore want to _minimize_ that function.

### Simple Linear Regression

Finding the best-fit line y = mx + b. Note: The formal proof of this proceeds by setting the derivative of the loss function to zero.

slope: $m = r\frac{\sigma_y}{\sigma_x}$

y-intercept: $b = \mu_y - m\mu_x$

Assumptions:

1. The relationship between target and predictor(s) is linear.
2. The errors are mutually independent.
3. The errors are normally distributed.
4. The errors are homoskedastic.

_Application_: <br/>
Continue example from before! Now that we have the correlation for our two variables X and Y, we can calculate the slope of the best-fit line. And once we have that, we can calculate the y-intercept of that same line (which fully determines it).

_Informal assessment_: <br/>
Pair up and chat: See if you can explain LR to your neighbor!

**Step 3**: Learning Goal 3: Explain the Coefficient of Determination. <br/>
**Time**: [15] min

_Demonstrate_: <br/>
### Coefficient of Determination

Very often a data scientist will calculate $R^2$ as a measure of how well the model fits the data.

$R^2$ for a model is ultimately a _relational_ notion. It's a measure of goodness of fit _relative_ to a (bad) baseline model. This bad baseline model is simply the horizontal line $y = \mu_Y$, for dependent variable Y.

The actual calculation of $R^2$ is $\frac{\Sigma_i(y_i - \hat{y}_i)^2}{\Sigma_i(y_i - \bar{y})^2}$.

$R^2$ takes values between 0 and 1.

The picture on learn.co is helpful here.

Idea of $R^2$ as "explaining the variation in the dependent variable".

\[Time permitting:
### Hypothesis Testing and p-Values

Null and alternative hypotheses

Typically, the null hypothesis (NH) will state that there is no relationship between two variables. We'll _reject_ the NH when we have reason to believe that the two variables are correlated.

_How much_ correlated? _How much_ reason? This makes for another parameter, but often we'll be looking at _95\%_-confidence intervals.\]

_Application_: <br/>
Calculate $R^2$ for the sample problem.

_Informal assessment_: <br/>
"Does everyone understand the calculation?"

**Step 4**: Integration:  <br/>
**Time**: [5] min

_Synthesis_: <br/>
Review learning goal steps that led to this final step to confirm understanding of how the steps fit together.

_Application_: <br/>
Time permitting (this seems unlikely), have students calculate the coefficient of determination of the best-fit line for two _new_ datasets.


**Step 5**: Assessment:  <br/>
**Time**: [10] min

Review questions? (Chat with peers?)
- What would you look for in a problem if you wanted to apply linear regression?
- What do covariance and correlation have to do with linear regression?
- What does the coefficient of determination measure?

**Step 6**: Reflection:  <br/>
**Time**: [5] min

"Why is linear regression important?"




```python

```
