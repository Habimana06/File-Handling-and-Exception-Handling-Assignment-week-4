# File-Handling-and-Exception-Handling-Assignment-week-4

def modify_content(text):
    # Example modification: Convert to uppercase
    return text.upper()

try:
    # 🧪 Ask the user for the input file name
    input_filename = input("Enter the name of the file to read from: ")

    with open(input_filename, "r") as infile:
        content = infile.read()

    # ✏️ Modify the content
    modified_content = modify_content(content)

    # 📝 Ask for the output file name
    output_filename = input("Enter the name of the file to write to: ")

    with open(output_filename, "w") as outfile:
        outfile.write(modified_content)

    print(f"🎉 Successfully read from '{input_filename}' and wrote modified content to '{output_filename}'!")

except FileNotFoundError:
    print(f"❌ Error: The file '{input_filename}' was not found.")
except IOError:
    print("❌ Error: Could not read/write the file. Check permissions or file path.")
except Exception as e:
    print(f"⚠️ An unexpected error occurred: {e}")
