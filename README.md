**Overview**

This project focuses on performance testing of the Blazedemo flight booking website using Apache JMeter. 

The objective is to simulate real-world traffic,evaluate the website's performance,and assess its ability to handle varying loads.

Key actions like searching for flights, booking a flight, purchasing a flight, and entering details 

are tested to ensure stability and responsiveness under stress.

**Test Scenarios**

1.Search Flights: Simulate user search between departure and destination ports using parametrization.

2.Book Flight: Simulate the process of selecting and booking a flight.

3.Purchase Flight: Validate the purchase process and transaction completion.

4.Enter Details: Submit personal and payment details during booking.

**Key Features**

1.HTTP(s) Test Script Recorder: Used to capture the full end-to-end transaction flow.

2.Parametrization: Used for dynamic values like fromPort and toPort through CSV files.

3.Assertions: Ensures response correctness, including response code, size, and duration.

4.Listeners: Summary Reports, Aggregate Reports, and View Results Tree are used for test analysis.

5.Debug Sampler: Added to view variable values and debug scripts.

6.Load Simulation: Increased thread count and loop count to simulate concurrent users and repeated actions.


**Technologies Used**

Tool: Apache JMeter

Test Management: JMeter Test Plan with recording and scripting

Assertions: Response code, size, and duration assertions

Reporting: JMeter listeners (Summary, Aggregate, and View Results Tree) and HTML Report

Version Control: Git,Github


**Project Structure**

Blazedemo_Performance_Testing/

├── TestPlan/

│   ├── Blazedemo-Project.jmx           # JMeter Test Plan

│   ├── ThreadGroup/                    # Contains Thread Group and related requests

│   │   ├── RecordingController/        # Holds HTTP(s) Test Script Recorder

│   │   │   ├── HomePage/               # HomePage Request

             ├── ResponseCodeAssertion/ # Response Code Assertion

             ├── SizeAssertion/         # Size Assertion

             └── DurationAssertion/     # Duration Assertion

│   │   │   ├── SearchFlights/          # Search Flights Request

             ├── SearchFlight.csv        # CSV file for parametrization (e.g., fromPort, toPort)
            
             ├── ResponseCodeAssertion/  # Response Code Assertion

             ├── SizeAssertion/          # Size Assertion

             └── DurationAssertion/      # Duration Assertion

│   │   │   ├── BookFlight/             # Book Flight Request

             ├── ResponseCodeAssertion/ # Response Code Assertion

             ├── SizeAssertion/         # Size Assertion

             └── DurationAssertion/     # Duration Assertion

│   │   │   ├── PurchaseFlight/         # Purchase Flight Request

             ├── ResponseCodeAssertion/ # Response Code Assertion

             ├── SizeAssertion/         # Size Assertion

             └── DurationAssertion/     # Duration Assertion

│   │   │   └── EnterDetails/           # Enter Details Request

             ├── ResponseCodeAssertion/ # Response Code Assertion

             ├── SizeAssertion/         # Size Assertion

             └── DurationAssertion/     # Duration Assertion

│   ├── AggregateReport/            # Aggregate Report Listener

│   ├── SummaryReport/             # Summary Report Listener

│   └── ViewResultsTree/           # View Results Tree Listener

│   └── Debug Sampler/             # To Debug Scripts

├── HTTP(s) Test Script Recorder   #Recorder to capture the transactions     


**Report Screenshots**

**Report1**

![Blazedemo ss1](Blazedemo%20screenshots/Blazedemo%20ss1.PNG)

**Report2**

![Blazedemo ss2](Blazedemo%20screenshots/Blazedemo%20ss2.PNG)

**Report3**

![Blazedemo ss3](Blazedemo%20screenshots/Blazedemo%20ss3.PNG)

**Report4**

![Blazedemo ss4](Blazedemo%20screenshots/Blazedemo%20ss4.PNG)


**Prerequisites**

To run this performance testing project, ensure the following are set up:

Apache JMeter: Install the latest version of JMeter on your system.

Java Development Kit (JDK): Ensure JDK 8 or above is installed and configured in your system's environment variables.


**How to Use**

1.Clone this repository.

2.Open Blazedemo_Project.jmx in Apache JMeter.

3.Configure the SearchFlight.csv for flight search parameters (departure and destination ports).

4.Adjust thread count and loop count based on the desired load.

5.Run the tests in JMeter and analyze the results using the Listeners

6.Generate an HTML report for a visual representation of test results.

**Execution in Command Prompt**

To execute the test plan in command line:

     jmeter -n -t /path/to/Blazedemo_Project.jmx -l /path/to/Result.csv -e -o /path/to/HTML Report

This will run the test in non-GUI mode, generate results in Result.csv , and create HTML reports in the folder.

