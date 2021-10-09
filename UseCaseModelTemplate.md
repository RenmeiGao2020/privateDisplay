# Use Case Model

**Author**: <Team 047\>

## 1 Use Case Diagram

![Use Case Diagram](use_case_diagram.png)

## 2 Use Case Descriptions

### *Enter/ Edit Current Job*

- *Requirements: This use case allows a user to enter or edit the current job details. And after entering all information about the current job, the user can choose to save the information or cancel and exit the page.*

- *Pre-conditions: All the fields are entered successfully including the data type and the range of a number. Data type and value range are as follows:*
	1. String: Title
	2. String: Company
	3. String: Location (entered as city and state)
	4. int: Cost of living in the location (expressed as an index)
	5. double: Yearly salary
	6. double: Yearly bonus
	7. int: Allowed weekly telework days (expressed as the number of days per week allowed for remote work, inclusively between 0 and 5)
	8. int: Leave time (vacation days and holiday and/or sick leave, as a single overall number of days)
	9. double: Gym membership allowance ($0 to $500 annually)

- *Post-conditions:*

	1. If a user enters the ‘SAVE’ button and there are data type errors or out of range errors the screen will display an input error message
	2. If a user enters the ‘SAVE’ button, and there is no data type error or out of range error a new current job will be initialized or a current job will be updated
	3. If a user enters the “Cancel and Exit” button, the system will return to the main menu

- *Scenarios: Sequence of events that characterize the use case.*

    **Step 1:**
    	Click the button ‘Enter/ Edit Current Job’

    **Step 2:**
    	Enter the 9 fields of the current job offer
	* Scenario 1: A user enters a wrong input data type or data range, the screen displays an error message to the user.

    **Step3:**
    	Choose to save entered information of the current offer or cancel and exit the page
	* Scenario 1: A user ignores the error message when she/he enters and saves the wrong information, then the App refuses it and give an error message to tell what information should be re-entered
	* Scenario 2: A user decides not to save the information she/he entered, she/ he can enter the button ‘Cancel/ Exit’, the screen will switch to the main menu.
	* Scenario 3: When a user enters all the fields appropriately, and she/ he enters the button ‘SAVE’, her/ his current job offer will be saved into the system.

### *Enter Job Offer(s)*

- *Requirements:* 
    * This use case allows a user to enter a new job offer details. And after entering all information, the user can choose to save the information or cancel and exit the page or enter another offer or compare the offer with the current job details.*

- *Pre-conditions: For entering a new Job Offer: all the fields are entered successfully including the data type and the range of a number. Data type and value range are as follows:*
	1. String: Title
	2. String: Company
	3. String: Location (entered as city and state)
	4. int: Cost of living in the location (expressed as an index)
	5. double: Yearly salary
	6. double: Yearly bonus
	7. int: Allowed weekly telework days (expressed as the number of days per week allowed for remote work, inclusively between 0 and 5)
	8. int: Leave time (vacation days and holiday and/or sick leave, as a single overall number of days)
	9. double: Gym membership allowance ($0 to $500 annually)

    * For entering another Job Offer, the preconditions are the same as above.

    * For comparing the offer with the current job, the preconditions are as follows:
	    * There is a current job offer in the system
	    * The new job offer is saved successfully

- *Post-conditions:*
	1. If a user enters the ‘SAVE’ button and there are data type errors or out of range errors the screen will display an input error message
	2. If a user enters the ‘SAVE’ button, and there is no data type error or out of range error a new job offer will be initialized
	3. If a user enters the “Cancel and Exit” button, the system will return to the main menu
	4. If a user chooses to enter another offer, the page will go to ‘Enter Job Offer(s)’ again
	5. If a user chooses to compare the new entered offer with the current job offer, 
	1. If there is no current job offer in the system, the App will display a comparison error message to the user
	2. If there is a current job offer in the system, the App will compare these two jobs and display the comparison result on the screen

- *Scenarios: Sequence of events that characterize the use case.*
    
    **Step 1:**
    Click the button ‘Enter Job Offer(s)’

    **Step 2:**
    Enter the 9 fields of a new job offer
    	* Scenario 1: A user enters a wrong input data type or data range, and the screen  displays an error message to the user.

    **Step3:**
    Choose to save information of the new offer or cancel and exit the page
	* Scenario 1: A user ignores the error message when she/he enters and save the wrong information, and the App refuses it and gives an error message to tell what information should be re-entered
	* Scenario 2: A user decides not to save the information and she/ he enters the button ‘Cancel/ Exit’, the screen switches to the main menu.
	* Scenario 3: When a user enters all the fields appropriately, and she/ he enters the button ‘SAVE’, this new job offer will be saved into the system.

    **Step 4:**
    Choose to Enter Another Offer
	* Scenario 1: A user ignores this option or click the button accidentally and she/ he can cancel it and return to the main menu
	* Scenario 2: When a user chooses it and it will repeat Step 3

    **Step 5:**
    Compare with the Current Job
	* Scenario 1: A user ignores this option or click the button accidentally and she/ he can cancel it and return to the main menu
	* Scenario 2: When a user chooses to compare the new offer with the current job but there is no current job information in the system, the App will display an error message to let user enter a current job 
	* Scenario 3: When a user chooses to compare the new offer with the current job and there is a current job offer in the system, the App will compare these two jobs and display the comparison result on the screen *

### *Adjust the Comparison Settings*

- *Requirements: This use case allows a user to select the integer weights of attributes of job offers and the system will use the weights to compare two job offers and calculate Job Score of each offer. If there are no user input weights the system will use the fault weights to compare job offers.*

- *Pre-conditions:*
There are drop down boxes of integers to assign to weights of the following attributes of job offers:
	1. Yearly salary
	2. Yearly bonus
	3. Allowed weekly telework days
	4. Leave time
	5. Gym membership allowance

- *Post-conditions:*
	1. If a user doesn’t choose to adjust the comparison weights or doesn’t save the new values, the system will set default value, same weight to the attributes to compare job offers
	2. If a user chooses wrong comparison weights, the App will display a comparison error on the screen
	3. If a user chooses to adjust comparison weights, the new chosen weights will pass into the comparator of the system.

- *Scenarios: Sequence of events that characterize the use case.*
    
    **Step 1:**
    Click the button ‘Adjust the Comparison Settings’
    
    **Step 2:**
    Choose values of drop down boxes to assign new comparison weights
	* Scenario 1: If a user enters wrong comparison weights, the App will display a comparison error on the screen

    **Step3:**
    Choose to save selected values of comparison weights or cancel and exit the page
	* Scenario 1: A user ignores the error message when she/he selects wrong values, and the App refuses it and gives an error message to tell what information should be re-selected
	* Scenario 2: When a user clicks the button ‘Cancel/ Exit’, the screen will switch to the main menu.
	* Scenario 3: When a user selects all the weights appropriately, and she/ he enters the button ‘SAVE’, these new comparison weights will be saved into the system and the comparator will use the new weights to compare job offers*

### *Compare Job Offers*

- *Requirements: This use case allows a user to compare Job Offers. It has 4 sub-menu to choose: (1)Display Offer Ranks (2)Compare Two Jobs (3)Display Jobs comparison details (4)Compare Another Two Jobs*

- *Pre-conditions: For ‘Compare Two Jobs’ and ‘Compare Another Two Jobs’, there must be at least two saved job offers in the system.*

- *Post-conditions:*
	1. If a user selects the ‘Display Offer Ranks’ button, but there is no offers in the system, the App will display an error message
	2. If a user selects the ‘Display Offer Ranks’ button, and there is at least one job offer in the system, the App will display all the job offer ranks on the screen. The ranks are according to the Job Score of each job. The Job Score is computed by the comparison weights of the system’s comparator.
	3. If a user selects the ‘Compare Two Jobs’ button, and there are fewer than two jobs in the system, the App will give the user an error message
	4. If a user selects the ‘Compare Two Jobs’ button, and there are more than two jobs in the system, the App will let the user choose two jobs from the system to compare. After the user choosing two jobs, the App will compare two jobs using the comparator in the system and display a general result
	5. If a user ‘Display Jobs comparison details’, the App will display the comparison details of two job offers
	6. If a user selects the ‘Compare Another Two Jobs’ button, and there are less than two jobs in the system, the App will give the user an error message
	7. If a user selects the ‘Compare Another Two Jobs’ button, and there are another two jobs in the system, the App will let the user choose two jobs from the system to compare. After the user choosing another two jobs, the App will compare two jobs using the comparator in the system and display a general result

- *Scenarios: Sequence of events that characterize the use case.*

    **Step 1:**
    Click the button ‘Compare Job Offers’

    **Step 2:**
    Click the button ‘Display Offer Ranks’
	* Scenario 1: A user clicks the button ‘Display Offer Ranks’ and if there are no offers in the system, the App displays an error message
	* Scenario 2: A user clicks the button ‘Display Offer Ranks’ and if there is at least one offer in the system, the App displays all the job offer ranks on the screen

    **Step3:**
    Click the button ‘Compare Two Jobs’
	* Scenario 1: A user selects the ‘Compare Two Jobs’ button, and there are less than two jobs in the system, the App gives the user an error message
	* Scenario 3: If a user selects the ‘Compare Two Jobs’ button, and there are more than two jobs in the system, the App will let the user choose two jobs from the system to compare. After the user choosing two jobs, the App compares two jobs using the comparator in the system and displays a general result

    **Step 4:**
    Click the button ‘Display Jobs comparison details’
	* Scenario 1: A user clicks ‘Display Jobs comparison details’ but she/he didn’t compare two jobs, the App displays an error message
	* Scenario 2: A user clicks ‘Display Jobs comparison details’,the App will display the comparison details of two job offers
    
    **Step 5:**
    Click the button ‘Compare Another Two Jobs’
	* Scenario 1: A user selects the ‘Compare Another Two Jobs’ button, and there are less than two jobs in the system, the App gives the user an error message
	* Scenario 2: A user selects the ‘Compare Another Two Jobs’ button, and there are another two jobs in the system, the App lets the user choose two jobs from the system to compare. After the user choosing another two jobs, the App compares two jobs using the comparator in the system and displays a general result
