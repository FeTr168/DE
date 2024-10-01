import json
import os

# Step 1: Generate 100 empty result files
def initialize_empty_files(n=1):
    # Base case: Stop at 100 files
    if n > 100:
        return

    file_name = f'result_{n}.json'
    
    # Write an empty dictionary to the file
    with open(file_name, 'w') as json_file:
        json.dump({}, json_file, indent=4)
    
    # Recursive call to initialize the next file
    initialize_empty_files(n + 1)

# Initialize the first file to start updating
ready_to_input = 1

# Step 2: Process word count and update files sequentially
def def_word_cnt():
    global ready_to_input
    
    if ready_to_input > 100:
        print("No more processing can be handled due to the limit of 100 results files.")
        return

    # Get input from the user
    input_string = input("Please enter a string: ")
    words = input_string.split()

    # Process each word
    for word in words:
        if ready_to_input > 100:
            print("No more processing can be handled due to the limit of 100 results files.")
            break
        
        update_word_count(word)

def update_word_count(word):
    global ready_to_input
    
    # Get the current file name based on ready_to_input
    file_name = f'result_{ready_to_input}.json'
    
    # Read the existing file
    if os.path.exists(file_name):
        with open(file_name, 'r') as json_file:
            data = json.load(json_file)

        # If the file is empty or contains words, update/add the word count
        if word in data:
            data[word] += 1
        else:
            data[word] = 1

        # Write the updated word count back to the file
        with open(file_name, 'w') as json_file:
            json.dump(data, json_file, indent=4)

        # Increment ready_to_input for the next file
        ready_to_input += 1

# Step 1: Initialize 100 empty result files
initialize_empty_files()

# Step 2 and 3: Take input from the user and update the word counts
def_word_cnt()
