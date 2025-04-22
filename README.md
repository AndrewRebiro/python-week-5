# python-week-5
def modify_content(content):
    # Example modification: Convert content to uppercase
    return content.upper()

def main():
    try:
        # Ask user for the input filename
        input_filename = input("Enter the name of the file to read from: ")

        # Try opening and reading the file
        with open(input_filename, "r") as infile:
            original_content = infile.read()

        # Modify the content (you can change this function to do other modifications)
        modified_content = modify_content(original_content)

        # Ask for output filename
        output_filename = input("Enter the name of the file to write the modified content to: ")

        # Write the modified content to the new file
        with open(output_filename, "w") as outfile:
            outfile.write(modified_content)

        print(f"File has been modified and saved as '{output_filename}'.")

    except FileNotFoundError:
        print("❌ Error: The file you entered was not found.")
    except IOError:
        print("❌ Error: There was a problem reading or writing the file.")
    except Exception as e:
        print(f"❌ An unexpected error occurred: {e}")

# Run the program
main()
