# Week-3-Assignment-python-error-handling

‎#Source Code:
‎
‎import re
‎
‎try:
‎    # Read the contents of input.txt
‎
‎with open('input.txt', 'r') as file:
‎        data = file.read( )
‎
‎    # Count the number of words
‎
‎    words = re.findall(r'\b\w+\b', data.lower( ) ) 
‎
‎#Using regex to find words
‎
‎    word_count = len(words)
‎
‎    # Convert all text to uppercase
‎
‎    uppercase_data = data.upper( )
‎
‎    # Write the processed text and word count to output.txt
‎
‎    with open('output.txt', 'w') as output_file:
‎        output_file.write("Processed Text (Uppercase):\n")
‎        output_file.write(uppercase_data)
‎        output_file.write(f"\n\nTotal Word Count: {word_count}\n")
‎
‎    print("Success: output.txt created with processed text and word count.")
‎
‎except FileNotFoundError:
‎    print("Error: input.txt not found. Please ensure it's in the directory.")
‎except Exception as e:
‎    print(f"An error occurred: {e}")


#Week 3 Assignment/Object Oriented Programming 
#‎Create a class representing anything you like (a Smartphone, Book, or even a Superhero!).
‎
#‎Add attributes and methods to bring the class to life!
‎
#‎Use constructors to initialize each object with unique values.
‎
#‎Add an inheritance layer to explore polymorphism or encapsulation.


Answer:
‎#source code
‎class Lion:
‎    def speak(self):
‎        return "Roar!"
‎
‎class Cow:
‎    def speak(self):
‎        return "Moow!"
‎
‎# Polymorphism in action
‎for animal in [Lion( ), Cow( )]:
‎    print(animal.speak( ) )
‎
‎output:
‎Roar!
‎Moow!
‎
‎#Answer
‎class SecretBook:
‎    def __init__(self):
‎        self.__books = 10  
‎# Private attribute
‎
‎    def take_books(self):
‎        if self.__books > 0:
‎            self.__books -= 2
‎            print("Two books taken!")
‎        else:
‎            print("No book left!")
‎
‎Book = SecretBook( )
‎book.take_book( )
‎
‎output:
‎Two books taken!
‎
‎
‎
‎