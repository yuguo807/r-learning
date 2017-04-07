# r-learning
R is case sensitive!

The modulo returns the remainder of the division of the number to the left by the number on its right, for example 5 modulo 3 or 5 %% 3 is 2.

What's that data type?
class()
create a vector with the combine function c()

give a name to the elements of a vector with the names() function. Have a look at this example:

some_vector <- c("John Doe", "poker player")
names(some_vector) <- c("Name", "Profession")

sum(). It calculates the sum of all elements of a vector.

# Poker and roulette winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Total winnings with poker
total_poker <- sum(poker_vector)

# Total winnings with roulette
total_roulette <-  sum(roulette_vector)

# Total winnings overall
total_week <- total_roulette + total_poker


# Print out total_week
  total_week


重复利用
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)

# Roulette winnings from Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)

# The variable days_vector
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
 
# Assign the names of the day to roulette_vector and poker_vector
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

逻辑判断
# Poker and roulette winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Calculate total gains for poker and roulette
total_poker <- sum(poker_vector)
total_roulette <- sum(roulette_vector)

# Check if you realized higher total gains in poker than in roulette 
total_poker > total_roulette
[1] TRUE

Vector selection:

Sample 1
> poker_vector <- c(140, -50, 20, -120, 240)
> roulette_vector <- c(-24, -50, 100, -350, 10)
> days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
> names(poker_vector) <- days_vector
> names(roulette_vector) <- days_vector
> 
> # Define a new variable based on a selection
> poker_wednesday <- poker_vector[3]
> poker_wednesday
Wednesday 
20
sample 2
poker_vector <- c(140, -50, 20, -120, 240)
> roulette_vector <- c(-24, -50, 100, -350, 10)
> days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
> names(poker_vector) <- days_vector
> names(roulette_vector) <- days_vector
> 
> # Define a new variable based on a selection
> poker_midweek <- poker_vector[c(2,3,4)]
> poker_midweek
  Tuesday Wednesday  Thursday 
      -50        20      -120

sample 3


> roulette_vector <- c(-24, -50, 100, -350, 10)
> days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
> names(poker_vector) <- days_vector
> names(roulette_vector) <- days_vector
> 
> # Select poker results for Monday, Tuesday and Wednesday
> poker_start <- poker_vector[c("Monday", "Tuesday", "Wednesday")]
> 
> # Calculate the average of the elements in poker_start
> mean(poker_start)
[1] 36.66667

•	< for less than
•	> for greater than
•	<= for less than or equal to
•	>= for greater than or equal to
•	== for equal to each other
•	!= not equal to each other
Selection by comparison


Sample1 
> # Poker and roulette winnings from Monday to Friday:
> poker_vector <- c(140, -50, 20, -120, 240)
> roulette_vector <- c(-24, -50, 100, -350, 10)
> days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
> names(poker_vector) <- days_vector
> names(roulette_vector) <- days_vector
> 
> # Which days did you make money on poker?
> selection_vector <- poker_vector>0
> 
> # Print out selection_vector
> selection_vector
   Monday   Tuesday Wednesday  Thursday    Friday 
TRUE     FALSE      TRUE     FALSE      TRUE
Sample 2
> names(poker_vector) <- days_vector
> names(roulette_vector) <- days_vector
> 
> # Which days did you make money on poker?
> selection_vector <- poker_vector > 0
> 
> # Select from poker_vector_ these days
> poker_winning_days <-poker_vector[selection_vector]
> poker_winning_days
   Monday Wednesday    Friday 
140        20       240
matrix()
matrix(1:9, byrow = TRUE, nrow = 3)
In the matrix() function:
The first argument is the collection of elements that R will arrange into the rows and columns of the matrix. Here, we use 1:9 which is a shortcut for c(1, 2, 3, 4, 5, 6, 7, 8, 9).
The argument byrow indicates that the matrix is filled by the rows. If we want the matrix to be filled by the columns, we just place byrow = FALSE. 
The third argument nrow indicates that the matrix should have three rows.






Sample

# Box office Star Wars (in millions!)
> new_hope <- c(460.998, 314.4)
> empire_strikes <- c(290.475, 247.900)
> return_jedi <- c(309.306, 165.8)
> 
> # Create box_office
> box_office <- c(new_hope, empire_strikes, return_jedi)
> 
> # Construct star_wars_matrix
> star_wars_matrix <- matrix(box_office, byrow = TRUE, nrow = 3)
> star_wars_matrix
        [,1]  [,2]
[1,] 460.998 314.4
[2,] 290.475 247.9
[3,] 309.306 165.8
>
Naming a matrix
# Box office Star Wars (in millions!)
> new_hope <- c(460.998, 314.4)
> empire_strikes <- c(290.475, 247.900)
> return_jedi <- c(309.306, 165.8)
> box_office <- c(new_hope, empire_strikes, return_jedi)
> # Construct matrix
> star_wars_matrix <- matrix(box_office, nrow = 3, byrow = TRUE)
> 
> # Vectors region and titles, used for naming
> region <- c("US", "non-US")
> titles <- c("A New Hope", "The Empire Strikes Back", "Return of the Jedi")
> 
> # Name the columns with region
> rownames(star_wars_matrix) <- titles
> 
> # Name the rows with titles
> colnames(star_wars_matrix) <- region
> 

or # Name the rows with titles, he columns with region

star_wars_matrix <- matrix(box_office, nrow = 3, byrow = TRUE,
                             dimnames = list(c("A New Hope", "The Empire Strikes Back", "Return of the Jedi"), 
                                             c("US", "non-US")))
# A dimnames attribute for the matrix: NULL or a list of length 2 giving the row and column names respectively. An empty list is treated as NULL, and a list of length one as row names. The list can be named, and the list names will be used as names for the dimensions.

> # Print out star_wars_matrix
> star_wars_matrix
                             US non-US
A New Hope              460.998  314.4
The Empire Strikes Back 290.475  247.9
Return of the Jedi      309.306  165.8




> # Calculate worldwide box office figures
> worldwide_vector <- rowSums(star_wars_matrix)
> worldwide_vector
        A New Hope The Empire Strikes Back      Return of the Jedi 
        775.398                 538.375                 475.106

> # Bind the new variable worldwide_vector as a column to star_wars_matrix
# cbind() function, which merges matrices and/or vectors together by column.
> # The worldwide box office figures
> worldwide_vector <- rowSums(star_wars_matrix)
all_wars_matr
ix <- cbind(star_wars_matrix, worldwide_vector)
> all_wars_matrix
                             US non-US worldwide_vector
A New Hope              460.998  314.4          775.398
The Empire Strikes Back 290.475  247.9          538.375
Return of the Jedi      309.306  165.8          475.106

rbind 
 sample 
# star_wars_matrix and star_wars_matrix2 are available in your workspace
> star_wars_matrix
                           US non-US
A New Hope              461.0  314.4
The Empire Strikes Back 290.5  247.9
Return of the Jedi      309.3  165.8
> star_wars_matrix2
                        US non-US
The Phantom Menace   474.5  552.5
Attack of the Clones 310.7  338.7
Revenge of the Sith  380.3  468.5
> 
> # Combine both Star Wars trilogies in one matrix
> all_wars_matrix <- rbind(star_wars_matrix, star_wars_matrix2)
> all_wars_matrix
                           US non-US
A New Hope              461.0  314.4
The Empire Strikes Back 290.5  247.9
Return of the Jedi      309.3  165.8
The Phantom Menace      474.5  552.5
Attack of the Clones    310.7  338.7
Revenge of the Sith     380.3  468.5

colSum()

sample 
# Total revenue for US and non-US
> total_revenue_vector <- colSums(all_wars_matrix)
> 
> # Print out total_revenue_vector
> total_revenue_vector
    US non-US 
2226.3 2087.8
Selection of matrix elements and  arithmetic with matrices
Similar to vectors, you can use the square brackets [ ] to select one or multiple elements from a matrix. Whereas vectors have one dimension, matrices have two dimensions. You should therefore use a comma to separate that what to select from the rows from that what you want to select from the columns. For example:
•	my_matrix[1,2] selects the element at the first row and second column.
•	my_matrix[1:3,2:4] results in a matrix with the data on the rows 1, 2, 3 and columns 2, 3, 4.
If you want to select all elements of a row or a column, no number is needed before or after the comma, respectively:
•	my_matrix[,1] selects all elements of the first column.
my_matrix[1,] selects all elements of the first row.



Sample 1
# all_wars_matrix is available in your workspace
> all_wars_matrix
                           US non-US
A New Hope              461.0  314.4
The Empire Strikes Back 290.5  247.9
Return of the Jedi      309.3  165.8
The Phantom Menace      474.5  552.5
Attack of the Clones    310.7  338.7
Revenge of the Sith     380.3  468.5
> 
> # Select the non-US revenue for all movies
> non_us_all <- all_wars_matrix[,2]
>   non_us_all
             A New Hope The Empire Strikes Back      Return of the Jedi 
                  314.4                   247.9                   165.8 
     The Phantom Menace    Attack of the Clones     Revenge of the Sith 
                  552.5                   338.7                   468.5
> # Average non-US revenue
> mean(non_us_all)
[1] 347.9667
> 
> # Select the non-US revenue for first two movies
> non_us_some <- all_wars_matrix[1:2,2]
> non_us_some
             A New Hope The Empire Strikes Back 
                  314.4                   247.9
> 
> # Average non-US revenue for first two movies
> mean(non_us_some)
[1] 281.15

sample 2

# all_wars_matrix and ticket_prices_matrix are available in your workspace
> all_wars_matrix
                           US non-US
A New Hope              461.0  314.4
The Empire Strikes Back 290.5  247.9
Return of the Jedi      309.3  165.8
The Phantom Menace      474.5  552.5
Attack of the Clones    310.7  338.7
Revenge of the Sith     380.3  468.5
> ticket_prices_matrix
                         US non-US
A New Hope              5.0    5.0
The Empire Strikes Back 6.0    6.0
Return of the Jedi      7.0    7.0
The Phantom Menace      4.0    4.0
Attack of the Clones    4.5    4.5
Revenge of the Sith     4.9    4.9
> 
> # Estimated number of visitors
> visitors <- all_wars_matrix / ticket_prices_matrix
> 
> # US visitors
> us_visitors <- visitors[,1]
> 
> # Average number of US visitors
> mean(us_visitors)
[1] 75.01401

sample 3
> # all_wars_matrix and ticket_prices_matrix are available in your workspace
> all_wars_matrix
                           US non-US
A New Hope              461.0  314.4
The Empire Strikes Back 290.5  247.9
Return of the Jedi      309.3  165.8
The Phantom Menace      474.5  552.5
Attack of the Clones    310.7  338.7
Revenge of the Sith     380.3  468.5
> ticket_prices_matrix
                         US non-US
A New Hope              5.0    5.0
The Empire Strikes Back 6.0    6.0
Return of the Jedi      7.0    7.0
The Phantom Menace      4.0    4.0
Attack of the Clones    4.5    4.5
Revenge of the Sith     4.9    4.9
> 
> # Estimated number of visitors
> visitors <- all_wars_matrix / ticket_prices_matrix
> visitors
                               US    non-US
A New Hope               92.20000  62.88000
The Empire Strikes Back  48.41667  41.31667
Return of the Jedi       44.18571  23.68571
The Phantom Menace      118.62500 138.12500
Attack of the Clones     69.04444  75.26667
Revenge of the Sith      77.61224  95.61224
> # US visitors
> us_visitors <- visitors[,1]
> 
> # Average number of US visitors
> mean(us_visitors)
[1] 75.01401
>
factor 
The term factor refers to a statistical data type used to store categorical variables.

Sample 1 

> # Gender vector
> gender_vector <- c("Male", "Female", "Female", "Male", "Male")
> 
> # Convert gender_vector to a factor
> factor_gender_vector <-factor(gender_vector)
> 
> # Print out factor_gender_vector
> factor_gender_vector
[1] Male   Female Female Male   Male  
Levels: Female Male

There are two types of categorical variables: a nominal categorical variable and an ordinal categorical variable.

A nominal variable is a categorical variable without an implied order. This means that it is impossible to say that 'one is worth more than the other'. For example, think of the categorical variable animals_vector with the categories "Elephant", "Giraffe", "Donkey" and "Horse". Here, it is impossible to say that one stands above or below the other. (Note that some of you might disagree ;-) ).

In contrast, ordinal variables do have a natural ordering. Consider for example the categorical variable temperature_vector with the categories: "Low", "Medium" and "High". Here it is obvious that "Medium" stands above "Low", and "High" stands above "Medium".

Sample 2
> # Animals
> animals_vector <- c("Elephant", "Giraffe", "Donkey", "Horse")
> factor_animals_vector <- factor(animals_vector)
> factor_animals_vector
[1] Elephant Giraffe  Donkey   Horse   
Levels: Donkey Elephant Giraffe Horse
> 
> # Temperature
> temperature_vector <- c("High", "Low", "High","Low", "Medium")
> factor_temperature_vector <- factor(temperature_vector, order = TRUE, levels = c("Low", "Medium", "High"))
> factor_temperature_vector
[1] High   Low    High   Low    Medium
Levels: Low < Medium < High

levels():

levels(factor_vector) <- c("name1", "name2",...)
A good illustration is the raw data that is provided to you by a survey. A standard question for every questionnaire is the gender of the respondent. You remember from the previous question that this is a factor and when performing the questionnaire on the streets its levels are often coded as "M" and "F".

survey_vector <- c("M", "F", "F", "M", "M")
Next, when you want to start your data analysis, your main concern is to keep a nice overview of all the variables and what they mean. At that point, you will often want to change the factor levels to "Male" and "Female" instead of "M" and "F" to make your life easier.

Watch out: the order with which you assign the levels is important. If you type levels(factor_survey_vector), you'll see that it outputs [1] "F" "M". If you don't specify the levels of the factor when creating the vector, R will automatically assign them alphabetically. To correctly map "F" to "Female" and "M" to "Male", the levels should be set to c("Female", "Male"), in this order order.

Sample 
# Code to build factor_survey_vector
> survey_vector <- c("M", "F", "F", "M", "M")
> factor_survey_vector <- factor(survey_vector)
> 
> # Specify the levels of factor_survey_vector
>  levels(factor_survey_vector) <- c("Female" , "Male")
> 
> 
> factor_survey_vector
[1] Male   Female Female Male   Male  
Levels: Female Male

summary(). 
This will give you a quick overview of the contents of a variable
# Build factor_survey_vector with clean levels
> survey_vector <- c("M", "F", "F", "M", "M")
> factor_survey_vector <- factor(survey_vector)
> levels(factor_survey_vector) <- c("Female", "Male")
> factor_survey_vector
[1] Male   Female Female Male   Male  
Levels: Female Male
> 
> # Generate summary for survey_vector
> summary(survey_vector)
   Length     Class      Mode 
        5 character character
> 
> # Generate summary for factor_survey_vector
> summary(factor_survey_vector)
Female   Male 
     2      3
factor(some_vector,
       ordered = TRUE,
       levels = c("lev1", "lev2" ...))
By setting the argument ordered to TRUE in the function factor(), you indicate that the factor is ordered. With the argument levels you give the values of the factor in the correct order.

SAMPLE 
# Create speed_vector
> speed_vector <- c("fast", "slow", "slow", "fast", "insane")
> 
> # Convert speed_vector to ordered factor vector
> factor_speed_vector <-factor(speed_vector,
                        ordered= TRUE,
                        levels=c("slow", "fast", "insane"))
> 
> # Print factor_speed_vector
> factor_speed_vector
[1] fast   slow   slow   fast   insane
Levels: slow < fast < insane
> summary(factor_speed_vector)
  slow   fast insane 
     2      2      1
sample 2


# Create factor_speed_vector
> speed_vector <- c("fast", "slow", "slow", "fast", "insane")
> factor_speed_vector <- factor(speed_vector, ordered = TRUE, levels = c("slow", "fast", "insane"))
> 
> # Factor value for second data analyst
> da2 <-factor_speed_vector[2]
> da2
[1] slow
Levels: slow < fast < insane
> # Factor value for fifth data analyst
> da5 <-factor_speed_vector[5]
> da5
[1] insane
Levels: slow < fast < insane
> # Is data analyst 2 faster than data analyst 5?
> da2 > da5
[1] FALSE

data frame
A data frame has the variables of a data set as columns and the observations as rows
head() enables you to show the first observations of a data frame. Similarly, the function tail() prints out the last observations in your data set.

Both head() and tail() print a top line called the 'header', which contains the names of the different variables in your data set.
Sample 
head(mtcars)
                   mpg cyl disp  hp drat    wt  qsec vs am gear carb
Mazda RX4         21.0   6  160 110 3.90 2.620 16.46  0  1    4    4
Mazda RX4 Wag     21.0   6  160 110 3.90 2.875 17.02  0  1    4    4
Datsun 710        22.8   4  108  93 3.85 2.320 18.61  1  1    4    1
Hornet 4 Drive    21.4   6  258 110 3.08 3.215 19.44  1  0    3    1
Hornet Sportabout 18.7   8  360 175 3.15 3.440 17.02  0  0    3    2
Valiant           18.1   6  225 105 2.76 3.460 20.22  1  0    3    1

The function str() shows you the structure of your data set.
str(mtcars)
'data.frame':	32 obs. of  11 variables:
 $ mpg : num  21 21 22.8 21.4 18.7 18.1 14.3 24.4 22.8 19.2 ...
 $ cyl : num  6 6 4 6 8 6 8 4 4 6 ...
 $ disp: num  160 160 108 258 360 ...
 $ hp  : num  110 110 93 110 175 105 245 62 95 123 ...
 $ drat: num  3.9 3.9 3.85 3.08 3.15 2.76 3.21 3.69 3.92 3.92 ...
 $ wt  : num  2.62 2.88 2.32 3.21 3.44 ...
 $ qsec: num  16.5 17 18.6 19.4 17 ...
 $ vs  : num  0 0 1 1 0 1 0 1 1 1 ...
 $ am  : num  1 1 1 0 0 0 0 0 0 0 ...
 $ gear: num  4 4 4 3 3 3 3 4 4 4 ...
 $ carb: num  4 4 1 1 2 1 4 2 2 4 ..

Creating a data frame
data.frame() function. As arguments, you pass the vectors from before: they will become the different columns of your data frame. Because every column has the same length, the vectors you pass should also have the same length. But don't forget that it is possible (and likely) that they contain different types of data.
Sample
# Definition of vectors
> name <- c("Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn", "Uranus", "Neptune")
> type <- c("Terrestrial planet", "Terrestrial planet", "Terrestrial planet", 
            "Terrestrial planet", "Gas giant", "Gas giant", "Gas giant", "Gas giant")
> diameter <- c(0.382, 0.949, 1, 0.532, 11.209, 9.449, 4.007, 3.883)
> rotation <- c(58.64, -243.02, 1, 1.03, 0.41, 0.43, -0.72, 0.67)
> rings <- c(FALSE, FALSE, FALSE, FALSE, TRUE, TRUE, TRUE, TRUE)
> 
> # Create a data frame from the vectors
> planets_df <-data.frame(name,type,diameter,rotation,rings)
> planets_df
     name               type diameter rotation rings
1 Mercury Terrestrial planet    0.382    58.64 FALSE
2   Venus Terrestrial planet    0.949  -243.02 FALSE
3   Earth Terrestrial planet    1.000     1.00 FALSE
4    Mars Terrestrial planet    0.532     1.03 FALSE
5 Jupiter          Gas giant   11.209     0.41  TRUE
6  Saturn          Gas giant    9.449     0.43  TRUE
7  Uranus          Gas giant    4.007    -0.72  TRUE
8 Neptune          Gas giant    3.883     0.67  TRUE
Selection of data frame elements
Sample 1
# The planets_df data frame from the previous exercise is pre-loaded
> 
> # Print out diameter of Mercury (row 1, column 3)
> planets_df[1,3]
[1] 0.382
> 
> # Print out data for Mars (entire fourth row)
> planets_df[4, ]
  name               type diameter rotation rings
4 Mars Terrestrial planet    0.532     1.03 FALSE



sample 2
# The planets_df data frame from the previous exercise is pre-loaded
> 
> # Select first 5 values of diameter column
> planets_df[5,"diameter"]
[1] 11.209

sample3
# planets_df is pre-loaded in your workspace
> 
> # Select the rings variable from planets_df
# planet_df$diameter==planets_df[,"diameter"]
> rings_vector <- planets_df$diameter
> 
> # Print out rings_vector
> rings_vector
[1]  0.382  0.949  1.000  0.532 11.209  9.449  4.007  3.883

sample 4
# planets_df and rings_vector are pre-loaded in your workspace
> 
> # Adapt the code to select all columns for planets with rings
> planets_df[rings_vector, ]
     name      type diameter rotation rings
5 Jupiter Gas giant   11.209     0.41  TRUE
6  Saturn Gas giant    9.449     0.43  TRUE
7  Uranus Gas giant    4.007    -0.72  TRUE
8 Neptune Gas giant    3.883     0.67  TRUE

sample 5
# planets_df is pre-loaded in your workspace
> 
> # Select planets with diameter < 1
# subset(my_df, subset = some_condition)
# The first argument of subset() specifies the data set for which you want a subset. # By adding the second argument, you give R the necessary information and # # # conditions to select the correct subset.

> subset(planets_df, subset = diameter < 1)
     name               type diameter rotation rings
1 Mercury Terrestrial planet    0.382    58.64 FALSE
2   Venus Terrestrial planet    0.949  -243.02 FALSE
4    Mars Terrestrial planet    0.532     1.03 FALSE

order() is a function that gives you the ranked position of each element when it is applied on a variable
> a <- c(100, 10, 1000)
> order(a)
[1] 2 1 3
we can use the output of order(a) to reshuffle a:

> a[order(a)]
[1]   10  100 1000

sample
# planets_df is pre-loaded in your workspace
> 
> # Use order() to create positions
> positions <- order(planets_df$diameter)
> 
> # Use positions to sort planets_df
# reshuffle planets_df with the positions vector as row indexes inside square brackets. Keep all columns.
> planets_df[positions, ]
     name               type diameter rotation rings
1 Mercury Terrestrial planet    0.382    58.64 FALSE
4    Mars Terrestrial planet    0.532     1.03 FALSE
2   Venus Terrestrial planet    0.949  -243.02 FALSE
3   Earth Terrestrial planet    1.000     1.00 FALSE
8 Neptune          Gas giant    3.883     0.67  TRUE
7  Uranus          Gas giant    4.007    -0.72  TRUE
6  Saturn          Gas giant    9.449     0.43  TRUE
5 Jupiter          Gas giant   11.209     0.41  TRUE

A list in R allows you to gather a variety of objects under one name (that is, the name of the list) in an ordered way. These objects can be matrices, vectors, data frames, even other lists, etc.
Sample 
# Vector with numerics from 1 up to 10
> my_vector <- 1:10
> 
> # Matrix with numerics from 1 up to 9
> my_matrix <- matrix(1:9, ncol = 3)
> 
> # First 10 elements of the built-in data frame mtcars
> my_df <- mtcars[1:10,]
> 
> # Construct list with these different elements:
> my_list <- list(my_vector, my_matrix, my_df)
> # Print out my_list

# my_list <- list(your_comp1, your_comp2)
# names(my_list) <- c("name1", "name2") 
# The above commands are fully equivalent to the assignment
# my_list <- list(name1 = your_comp1, name2 = your_comp2)

> names(my_list) <- c("vec", "mat", "df")
> my_list
$vec
 [1]  1  2  3  4  5  6  7  8  9 10

$mat
     [,1] [,2] [,3]
[1,]    1    4    7
[2,]    2    5    8
[3,]    3    6    9

$df
                   mpg cyl  disp  hp drat    wt  qsec vs am gear carb
Mazda RX4         21.0   6 160.0 110 3.90 2.620 16.46  0  1    4    4
Mazda RX4 Wag     21.0   6 160.0 110 3.90 2.875 17.02  0  1    4    4
Datsun 710        22.8   4 108.0  93 3.85 2.320 18.61  1  1    4    1
Hornet 4 Drive    21.4   6 258.0 110 3.08 3.215 19.44  1  0    3    1
Hornet Sportabout 18.7   8 360.0 175 3.15 3.440 17.02  0  0    3    2
Valiant           18.1   6 225.0 105 2.76 3.460 20.22  1  0    3    1
Duster 360        14.3   8 360.0 245 3.21 3.570 15.84  0  0    3    4
Merc 240D         24.4   4 146.7  62 3.69 3.190 20.00  1  0    4    2
Merc 230          22.8   4 140.8  95 3.92 3.150 22.90  1  0    4    2
Merc 280          19.2   6 167.6 123 3.92 3.440 18.30  1  0    4    4

to create shining_list; it contains three elements:

moviename: a character string with the movie title (stored in mov)
actors: a vector with the main actors' names (stored in act)
reviews: a data frame that contains some reviews (stored in rev)
# The variables mov, act and rev are available
> 
> # Finish the code to build shining_list
> shining_list <- list(moviename = mov, actors=act, reviews=rev)
> shining_list
$moviename
[1] "The Shining"

$actors
[1] "Jack Nicholson"   "Shelley Duvall"   "Danny Lloyd"      "Scatman Crothers"
[5] "Barry Nelson"    

$reviews
  scoressources                                              comments
1    4.5   IMDb1                     Best Horror Film I Have Ever Seen
2    4.0   IMDb2 A truly brilliant and scary film from Stanley Kubrick
3    5.0   IMDb3                 A masterpiece of psychological horror
>
One way to select a component is using the numbered position of that component. For example, to "grab" the first component of shining_list you type

shining_list[[1]]
You can also refer to the names of the components, with [[ ]] or with the $ sign. Both will select the data frame representing the reviews:

shining_list[["reviews"]]
shining_list$reviews
to select elements from vectors, you use single square brackets: [ ]
For example, with shining_list[[2]][1] you select from the second component,  (shining_list[[2]]), the first element ([1]).

Sample 
# shining_list is already pre-loaded in the workspace
> 
> # Print out the vector representing the actors
> shining_list[["actors"]]
[1] "Jack Nicholson"   "Shelley Duvall"   "Danny Lloyd"      "Scatman Crothers"
[5] "Barry Nelson"
> 
> # Print the second element of the vector representing the actors
> shining_list[[2]][2]
[1] "Shelley Duvall"

To conveniently add elements to lists you can use the c() function, that you also used to build vectors:

ext_list <- c(my_list , my_val)
This will simply extend the original list, my_list, with the component my_val. This component gets appended to the end of the list. If you want to give the new list item a name, you just add the name as you did before:

ext_list <- c(my_list, my_name = my_val)

sample
# shining_list, the list containing movie name, actors and reviews, is pre-loaded in the workspace
> 
> # We forgot something; add the year to shining_list
> shining_list_full <- c(shining_list, year=1980)
> 
> # Have a look at shining_list_full
> str(shining_list_full)
List of 4
 $ moviename: chr "The Shining"
 $ actors   : chr [1:5] "Jack Nicholson" "Shelley Duvall" "Danny Lloyd" "Scatman Crothers" ...
 $ reviews  :'data.frame':	3 obs. of  3 variables:
  ..$ scores  : num [1:3] 4.5 4 5
  ..$ sources : Factor w/ 3 levels "IMDb1","IMDb2",..: 1 2 3
  ..$ comments: Factor w/ 3 levels "A masterpiece of psychological horror",..: 3 2 1
 $ year     : num 1980
> shining_list_full
$moviename
[1] "The Shining"

$actors
[1] "Jack Nicholson"   "Shelley Duvall"   "Danny Lloyd"      "Scatman Crothers"
[5] "Barry Nelson"    

$reviews
  scoressources                                              comments
1    4.5   IMDb1                     Best Horror Film I Have Ever Seen
2    4.0   IMDb2 A truly brilliant and scary film from Stanley Kubrick
3    5.0   IMDb3                 A masterpiece of psychological horror

$year
[1] 1980

Equality
# Comparison of logicals. In the editor on the right, write R code to see if TRUE equals FALSE
> TRUE == FALSE
[1] FALSE
> 
> # Comparison of numerics. Likewise, check if -6 * 14 is not equal to 17 - 101
> 
> -6 * 14 != 17-101
[1] FALSE
> # Comparison of character strings. Notice from the last expression that R is case sensitive: "R" is not equal to "r"
> "useR" == "user"
[1] FALSE
> 
> # Compare a logical with a numeric. find out what happens if you compare logicals to numerics: are TRUE and 1 equal?
> TRUE == 1
[1] TRUE

Greater and less than
# Comparison of numerics
> -6*5+2 >= -10+1
[1] FALSE
> 
> # Comparison of character strings
#for string comparison, R determines the greater than relationship based on alphabetical order
> "raining" <= "raining dogs"
[1] TRUE
> 
> # Comparison of logicals
# TRUE corresponds to 1 in R, and FALSE coerces to 0 behind the scenes.
> TRUE > FALSE
[1] TRUE

Compare vectors

# The linkedin and facebook vectors have already been created for you
linkedin <- c(16, 9, 13, 5, 2, 17, 14)
facebook <- c(17, 7, 5, 16, 8, 13, 14)

# Popular days
#On which days did the number of LinkedIn profile views exceed 15?
linkedin > 15
[1]  TRUE FALSE FALSE FALSE FALSE  TRUE FALSE
# Quiet days
#When was your LinkedIn profile viewed only 5 times or fewer?
linkedin <= 5
[1] FALSE FALSE FALSE  TRUE  TRUE FALSE FALSE

# LinkedIn more popular than Facebook
When was your LinkedIn profile visited more often than your #Facebook profile?
linkedin > facebook
[1] FALSE  TRUE  TRUE FALSE FALSE  TRUE FALSE

Compare matrices
> # The social data has been created for you
> linkedin <- c(16, 9, 13, 5, 2, 17, 14)
> facebook <- c(17, 7, 5, 16, 8, 13, 14)
> views <- matrix(c(linkedin, facebook), nrow = 2, byrow = TRUE)
> 
> # When does views equal 13?
> views == 13
      [,1]  [,2]  [,3]  [,4]  [,5]  [,6]  [,7]
[1,] FALSE FALSE  TRUE FALSE FALSE FALSE FALSE
[2,] FALSE FALSE FALSE FALSE FALSE  TRUE FALSE
> 
> # When is views less than or equal to 14?
> views <= 14
      [,1] [,2] [,3]  [,4] [,5]  [,6] [,7]
[1,] FALSE TRUE TRUE  TRUE TRUE FALSE TRUE
[2,] FALSE TRUE TRUE FALSE TRUE  TRUE TRUE


& and |
& means and, | means or 
sample 1
> # The linkedin and last variable are already defined for you
> linkedin <- c(16, 9, 13, 5, 2, 17, 14)
> last <- tail(linkedin, 1)
> 
> # Is last under 5 or above 10?
> last<5 | last >10
[1] TRUE
> 
> # Is last between 15 (exclusive) and 20 (inclusive)?
> last>15 & last <=20
[1] FALSE

sample 2 
# The social data (linkedin, facebook, views) has been created for you
> 
> # linkedin exceeds 10 but facebook below 10
> linkedin >10 & facebook <10
[1] FALSE FALSE  TRUE FALSE FALSE FALSE FALSE
> 
> # When were one or both visited at least 12 times?
> linkedin >=12 | facebook >=12
[1]  TRUE FALSE  TRUE  TRUE FALSE  TRUE  TRUE
> 
> # When is views between 11 (exclusive) and 14 (inclusive)?
> views >11 & views <= 14
      [,1]  [,2]  [,3]  [,4]  [,5]  [,6] [,7]
[1,] FALSE FALSE  TRUE FALSE FALSE FALSE TRUE
[2,] FALSE FALSE FALSE FALSE FALSE  TRUE TRUE

Reverse the result: !
! operator, which negates a logical value.
