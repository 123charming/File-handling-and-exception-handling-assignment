# File-handling-and-exception-handling-assignment
File Read & Write Challenge 🖋️: Create a program that reads a file and writes a modified version to a new file.
Error Handling Lab 🧪: Ask the user for a filename and handle errors if it doesn’t exist or can’t be read.
Outcomes 🎉

By the end of this module, you’ll be skilled in managing files efficiently in Python, ensuring error-free code that gracefully handles unexpected issues. Mastering files and exception handling will allow you to build strong, robust applications!
def process_file():
    """Reads a file, modifies its content, and writes to a new file with error handling."""

    input_filename = input("Enter the name of the file you want to read: ")
    output_filename = input("Enter the name for the new file to write to: ")

    try:
        with open(input_filename, 'r') as infile:
            content = infile.read()
            # Modify the content (example: convert to uppercase)
            modified_content = content.upper()

        with open(output_filename, 'w') as outfile:
            outfile.write(modified_content)

        print(f"\n🎉 Successfully read '{input_filename}', modified it, and wrote the result to '{output_filename}'!")

    except FileNotFoundError:
        print(f"\n🧪 Error: The file '{input_filename}' was not found. Please make sure the filename is correct and the file exists.")
    except IOError:
        print(f"\n🧪 Error: Could not read or write to the file(s). Please check file permissions.")
    except Exception as e:
        print(f"\n🧪 An unexpected error occurred: {e}")

if __name__ == "__main__":
    process_file()
