# Powerlearnproject-python-week-4-assignment
Week 4 assignment
def modify_content(content):
    """Modify the content by converting it to uppercase."""
    return content.upper()

def read_and_write_file():
    """Reads a file and writes a modified version to a new file with error handling."""
    try:
        filename = input("Enter the filename to read: ")

        # Attempt to open and read the file
        with open(filename, "r") as file:
            content = file.read()

        # Modify the content
        modified_content = modify_content(content)

        # Define the new filename
        new_filename = "modified_" + filename

        # Write the modified content to a new file
        with open(new_filename, "w") as file:
            file.write(modified_content)

        print(f"Modified content saved to {new_filename}")

    except FileNotFoundError:
        print("Error: The file does not exist. Please check the filename and try again.")
    except PermissionError:
        print("Error: Permission denied. You don’t have access to this file.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

# Run the function
read_and_write_file()

