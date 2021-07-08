# python14
EXCEPTIONS


1.Write a program to generate Arithmetic Exception without exception handling

a = int(input("Enter a:"))    
b = int(input("Enter b:"))    
c = a/b  
print("a/b = %d" %c)    
    
#other code:    
print("Hi I am other part of the program")  


2.Handle the Arithmetic exception using try-catch block

try:  
    a = int(input("Enter a:"))    
    b = int(input("Enter b:"))    
    c = a/b  
except:  
    print("Can't divide with zero")  
    
    

3.Write a method which throws exception, Call that method in main class without try block

class UnAcceptedValueError(Exception):   
    def __init__(self, data):    
        self.data = data
    def __str__(self):
        return repr(self.data)

Total_Marks = int(input("Enter Total Marks Scored: "))
try:
    Num_of_Sections = int(input("Enter Num of Sections: "))
    if(Num_of_Sections < 1):
        raise UnAcceptedValueError("Number of Sections can't be less than 1")
except UnAcceptedValueError as e:
    print ("Received error:", e.data)
    
    
4.Write a program with multiple catch blocks

import math
def square(x):
    if int(x) is 0:
        raise ValueError('Input argument cannot be zero')
    if int(x) < 0:
        raise TypeError('Input argument must be positive integer')
    return math.pow(int(x), 2)
    
while True:
    try:
        y = square(input('Please enter a number\n'))
        print(y)
    except ValueError as ve:
        print(type(ve), '::', ve)
    except TypeError as te:
        print(type(te), '::', te)   
  
  
  
5.Write a program to throw exception with your own message

class YourException(Exception):
  def __init__(self, message):
    self.message = message
 
try:
  raise YourException("Something is fishy")
 
except YourException as err:
 
  print("Message:", err.message)
  
  
  
6.Write a program to create your own exception

class YourException(Exception):
  def __init__(self, message):
    self.message = message
 
try:
  raise YourException("Something is fishy")
 
except YourException as err:
 
  print("Message:", err.message)
  
  
  
7.Write a program with finally block

def divide(x, y):
    try:
        # Floor Division : Gives only Fractional
        # Part as Answer
        result = x // y
    except ZeroDivisionError:
        print("Sorry ! You are dividing by zero ")
    else:
        print("Yeah ! Your answer is :", result)
    finally: 
        # this block is always executed  
        # regardless of exception generation. 
        print('This is always executed')  
divide(3, 2)
divide(3, 0)


8.Write a program to generate Arithmetic Exception

import sys
try:
7/0
except ArithmeticError as e:
print e
print sys.exc_type
print 'This is an example of catching ArithmeticError'


9.Write a program to generate ArrayIndexOutOfBoundException


10. Write a program to generate ClassNotFoundException


def bulk_load(rdd):
    conf = {#removed for brevity}
    keyConv = "org.apache.spark.examples.pythonconverters.StringToImmutableBytesWritableConverter"
    valueConv = "org.apache.spark.examples.pythonconverters.StringListToPutConverter"
    load_rdd = rdd.flatMap(lambda line: line.split("\n"))\
                  .flatMap(csv_to_key_value)
    load_rdd.saveAsNewAPIHadoopDataset(conf=conf,keyConverter=keyConv,valueConverter=valueConv)
    

11.Write a program to generate FileNotFoundException

# trying to open a file, which does not exist
try:
    #trying to open a file in read mode
    fo = open("myfile.txt","rt")
    print("File opened")
except FileNotFoundError:
    print("File does not exist")
except:
    print("Other error")



12.Write a program to generate IOException


import sys
def whatever():
try:
f = open ( "foo.txt", 'r' )
except IOError, e:
print e
print sys.exc_type
whatever()


13.Write a program to generate NoSuchFieldException

elt = driver.find_element_by_css_selector('.information')
try:
    dat1 = elt.find_element_by_css_selector('#one').text
    dat2 = elt.find_elements_by_css_selector('#two')[1].text
    text = dat1 + dat2
except NoSuchElementException:
    text = elt.find_element_by_css_selector('#all').text
    item.set_description(text)
    
    





