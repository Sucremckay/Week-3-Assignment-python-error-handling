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
‎