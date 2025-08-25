# Python-assignment-4
File handling and exception handling
def modify_file_content(text):
    # Example modification: convert to uppercase
    return text.upper()

def main():
    filename = input("Enter the name of the file to read: ")

    try:
        with open(filename, 'r') as file:
            content = file.read()

        modified_content = modify_file_content(content)

        new_filename = "modified_" + filename
        with open(new_filename, 'w') as new_file:
            new_file.write(modified_content)

        print(f"\n✅ File successfully modified and saved as '{new_filename}'.")

    except FileNotFoundError:
        print("❌ Error: File not found. Please check the filename and try again.")
    except IOError:
        print("❌ Error: Could not read or write to the file.")
    except Exception as e:
        print(f"❌ An unexpected error occurred: {e}")

if __name__ == "__main__":
    main()
