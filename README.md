# Frontline
code challenge
I chose to do this in Python because it is very prevalent. This exercise seemed to be about parsing strings, and that what I did, however; a real world case, I suspect this would be a CSV output and have many rows of data.  The "strings" listed would be the headers.  In that case, an import into a relational database would be more effective and allow SQL reporting,  Data types could also be manipulated to account for dates, unique id's, etc.  I suspect the "created" string would actually be a datetime.  



Here are my assumptions:



1) the id string is different for each node: first is the row ID (probably generated serial), the second is the employee ID (could be from multiple HR systems and may need to be made unique) and third, the employeeType-ID.  I assumed each was separate and unique.



2) The output requested, line by line, was what was delivered.  Not a full thousand row CSV file to be processed



3) Keep It Simple Stupid - I did not over think this



Challenges:

the multiple ID field, had to make unique
there was an added space in the last name
I did not have time to complete the Bonus, but the idea would be a If then loop against each of the variables, sort the list and sub-sort the list within EMPLOYEE and produce the output


Here is the Python source code:



# Frontline coding exercise - Bob Hercer - 3/24/2019

# Input string
mystring ="(id,created,employee(id,firstname,employeeType(id), lastname),location)"

# id - this is the record ID for the row
ID1 = mystring.split(",")[0].replace("(","")

# created
CREATED = mystring.split(",")[1]

# employee
EMPLOYEE = mystring.split(",")[2].split("(")[0]

# employee id - this id is the unique employee id
ID2 = "- " + mystring.split(",")[2].split("(")[1]

# firstname
FIRSTNAME = "- " + mystring.split(",")[3]

# employeeType
EMPLOYEETYPE = "- " + mystring.split(",")[4].split("(")[0]

# employeeType(ID) - this is the id of the employeeType
ID3 = "-- " + mystring.split(",")[4].split("(")[1].replace(")","")

# lastname
LASTNAME = "- " + mystring.split(",")[5].replace(")","").replace(" ","")

# location
LOCATION = mystring.split(",")[6].replace(")","")

# Print first output
print(ID1)
print(CREATED)
print(EMPLOYEE)
print(ID2)
print(FIRSTNAME)
print(EMPLOYEETYPE)
print(ID3)
print(LASTNAME)
print(LOCATION)

# Bonus (output in alphabetical order)
varlist=dir()  #strip out the UPPERCASE, sort and sub-sort on employee
