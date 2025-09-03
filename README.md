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
#Assignment on Analyzing Data with Pandas and Visualizing Results with Matplotlib 
‎‎#source code:
‎#Task1
‎#loading the dataset. The Iris dataset is loaded from a CSV file using pd.read_csv().
‎
‎    import pandas as pd
‎    import matplotlib.pyplot as plt
‎    import seaborn as sns
‎
‎    # Load the Iris dataset from a URL
‎    url = "https://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data"
‎    column_names = ["sepal_length", "sepal_width", "petal_length", "petal_width", "species"]
‎    df = pd.read_csv(url, names=column_names)
‎
‎#display first row
‎    print("First 5 rows of the dataset:")
‎    print(df.head())
‎
‎#Explore the structure (data types and missing values)
‎#Clean the dataset: For the Iris dataset, there are typically no missing values. If missing values were present, they could be handled by df.dropna() to drop rows with missing values or df.fillna(value) to fill them.
‎
‎    print("\nDataset Information:")
‎    print(df.info())
‎    print("\nMissing values per column:")
‎    print(df.isnull().sum())
‎
‎
‎#Task2
‎#Basic Data Analysis
‎#Compute basic statistics
‎#Identify patterns: The analysis of the Iris dataset reveals that different species of Iris flowers have distinct average sepal and petal measurements. For example, Iris-setosa generally has shorter petal lengths compared to Iris-versicolor and Iris-virginica.
‎
‎    print("\nBasic statistics of numerical columns:")
‎    print(df.describe())
‎
‎#Performing grouping and mean
‎    print("\nAverage petal length per species:")
‎    print(df.groupby('species')['petal_length'].mean())
‎
‎#Task3
‎#Data visualization
‎    # This is an illustrative example as Iris data is not time-series.
‎    # For actual time-series, ensure a datetime column exists.
‎#Line chart (Illustrative, as Iris data is not time-series):
‎
‎    plt.figure(figsize=(8, 5))
‎    df['sepal_length'].plot(kind='line')
‎    plt.title('Sepal Length Trend (Illustrative)')
‎    plt.xlabel('Index')
‎    plt.ylabel('Sepal Length (cm)')
‎    plt.grid(True)
‎    plt.show()
‎
‎#Bar Chart
‎    plt.figure(figsize=(8, 5))
‎    sns.barplot(x='species', y='petal_length', data=df, errorbar=None)
‎    plt.title('Average Petal Length per Species')
‎    plt.xlabel('Species')
‎    plt.ylabel('Average Petal Length (cm)')
‎    plt.show()
‎
‎#Histogram
‎    plt.figure(figsize=(8, 5))
‎    sns.histplot(df['sepal_length'], kde=True)
‎    plt.title('Distribution of Sepal Length')
‎    plt.xlabel('Sepal Length (cm)')
‎    plt.ylabel('Frequency')
‎    plt.show()
‎
‎#Scatter plot
‎    plt.figure(figsize=(8, 5))
‎    sns.scatterplot(x='sepal_length', y='petal_length', hue='species', data=df)
‎    plt.title('Sepal Length vs. Petal Length by Species')
‎    plt.xlabel('Sepal Length (cm)')
‎    plt.ylabel('Petal Length (cm)')
‎    plt.legend(title='Species')
‎    plt.show()
‎
‎
‎