
#Server
1. Keeps listening on dedicated ip, port
2. Reads the request validates and logs it
3. Fetches relevant info from the transaction request or (Queries csv file) against the account number and checks for account number
5. If it finds the amount sufficient enough, approves the request and logs it
6. Sends the response to the client.


#Client
1. Sends transaction request.
2. Waits for response


#Assumptions
1. Request is coming from an already authorized client
2. In this context we are Authorising against account number and transaction amount so we are using '0200' as MTI
3. One sample request package is: '02005000000000000002191234567890123456789000000013990022' where account no is  1234567890123456789 and transaction amount = 139.90
4. Our server has a database (hashmap) of account numbers and account balance pre-populated

#Future enhancements
1. Make the server respond to previous incomplete request before responding to new one
2. Let the server keep a log of all the transaction it has approved or rejected, keep a log file and append to it.
3. Make it Available via REST api, where emulator will send HTTP request to Authengine and engine will respond as HTTP response (that would be really interesting and easy to deploy
4. optimize

#Requirments
1. python 2.7

#Installation
1. Clone the directory
2. cd and Run python authdriver.py

#Reference
Used iso8583 open source library
https://code.google.com/p/iso8583py/
