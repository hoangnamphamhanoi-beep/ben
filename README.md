#1
numbers = []

while True:
    user_input = input("Enter a number (or press Enter to quit): ")
    if user_input == "":
        break
    try:
        numbers.append(float(user_input))
    except ValueError:
        print("That's not a valid number. Try again!")

numbers.sort(reverse=True)

print("\nThe five greatest numbers are:")
print(numbers[:5])


#2
seasons = ("Winter", "Spring", "Summer", "Autumn")

month = int(input("Enter the number of the month (1-12): "))

season_index = (month % 12) // 3
print(f"The season is {seasons[season_index]}.")


#3
names = set()

while True:
    name = input("Enter a name (or press Enter to quit): ").strip()
    if name == "":
        break
    
    if name in names:
        print("Existing name")
    else:
        print("New name")
        names.add(name)

print("\nList of entered names:")
for n in names:
    print(n)


#4
def analyze_word_frequency(text):
    words = text.lower().split()
    total_count = len(words)
    
    frequency_dict = {}
    for word in words:
        word = word.strip(".,!?\"")
        frequency_dict[word] = frequency_dict.get(word, 0) + 1
    
    sorted_words = sorted(frequency_dict.items(), key=lambda item: item[1], reverse=True)
    top_5 = dict(sorted_words[:5])
    
    top_5_sum = sum(top_5.values())
    proportion = (top_5_sum / total_count) * 100
    
    print(f"Top 5: {top_5}")
    print(f"Total number of words: {total_count}")
    print(f"Proportion of 5 most common words: {top_5_sum} / {total_count} = {proportion:.2f}%")

sample_text = "The world is a big place and the world is mine and the world is out there."
analyze_word_frequency(sample_text)


#5
def remove_odds(numbers):
    return [num for num in numbers if num % 2 == 0]

def main():
    original_list = [12, 7, 44, 19, 2, 33, 8, 101, 4]
    filtered_list = remove_odds(original_list)
    
    print(f"Original list: {original_list}")
    print(f"Cut-down list (evens only): {filtered_list}")

if __name__ == "__main__":
    main()
