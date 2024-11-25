**Overview**

This project focuses on performance testing of the Blazedemo flight booking website using Apache JMeter. The objective is to simulate real-world traffic,evaluate the website's performance,

and assess its ability to handle varying loads. Key actions like searching for flights, booking a flight, purchasing a flight, and entering details 

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

├── HTTP(s) Test Script Recorder   #Recorder to capture the transactions     



**Technologies Used**

Tool: Apache JMeter

Test Management: JMeter Test Plan with recording and scripting

Assertions: Response code, size, and duration assertions

Reporting: JMeter listeners (Summary, Aggregate, and View Results Tree) and HTML Report

Version Control: Git,Github

**How to Use**

Clone this repository.

Open Blazedemo_Project.jmx in Apache JMeter.

Configure the SerachFlight.csv for flight search parameters (departure and destination ports).

Adjust thread count and loop count based on the desired load.

Run the tests in JMeter and analyze the results using the Listeners

Generate an HTML report for a visual representation of test results.

**Execution in Command Prompt**

To execute the test plan in command line:

jmeter -n -t /path/to/Blazedemo_Project.jmx -l /path/to/Result.csv -e -o /path/to/HTML Report

This will run the test in non-GUI mode, generate results in Result.csv , and create HTML reports in the folder.

