# Evaluation 


## System design

### Data Structure 

A pointer is used to curse over the text.

### Regular Expression

A mix of regular expression and simple string is used 

### Design Ideas

In order to solve the proglem gracefully, I coded the potential start and end of a datetime string; then use a moving pointer with a moving window length of 40 chars to search for the datetime strings. Then get rid of the corner cases. 

This way we solve the problem within O(n) time complexity, n being the length of the text input. Precision, recall and F1 score is reported in system-evaluation.md. 

The idea is to make the system as graceful as possible. So I tried to avoid hard coding and minimize the number of lines involved there; the key funtional lines are less than ten. 

## Running the tests

Use the code in jupyter notebook to run it. 

### Test results

#### Sample test 1
|       |   Parsed Datetime |   Not Parsed Datetime |
| ------------- | ------------- | ------------- |
|   True Datetime  |    10  |   0   |
|   False Datetime  |   1   |   0   |

F1-score = 0.96

#### Sample test 2

|       |   Parsed Datetime |   Not Parsed Datetime |
| ------------- | ------------- | ------------- |
|   True Datetime  |    17  |   4   |
|   False Datetime  |   2   |   0   |

F1-score = 0.85

## Analysis 

This function used another type of design different from most common ideas; it specifies the start and end of datetime strings instead of assemble them. 
It's good for its light-weight and little time complexity, but the accuracy and recall could be improved further. Corner cases couldn't be easily avoided and could be further discussed.