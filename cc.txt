class SymptomChecker:
    def __init__(self):
        self.selected_symptoms = []

    def select_symptoms(self):
        print("Welcome to the Symptom Checker!")
        print("Select symptoms from the list (type 'done' when finished):")
        
        symptoms_list = [
            "Runny or Stuffy Nose",
            "Sore Throat",
            "Cough",
            "Sneezing",
            "Watery Eyes",
            "Headache",
            "Fatigue",
            "Body Aches",
            "Low-Grade Fever",
        ]

        while True:
            print("\nSymptoms:")
            for i, symptom in enumerate(symptoms_list, start=1):
                print(f"{i}. {symptom}")

            user_input = input("Enter the number of the symptom or 'done': ")

            if user_input.lower() == 'done':
                break

            try:
                index = int(user_input)
                if 1 <= index <= len(symptoms_list):
                    selected_symptom = symptoms_list[index - 1]
                    if selected_symptom not in self.selected_symptoms:
                        self.selected_symptoms.append(selected_symptom)
                        print(f"Selected: {selected_symptom}")
                    else:
                        print("Symptom already selected. Choose a different one.")
                else:
                    print("Invalid input. Please enter a valid number.")
            except ValueError:
                print("Invalid input. Please enter a valid number.")

    def get_treatment_recommendation(self):
        print("\nBased on your selected symptoms, here are general treatment recommendations:")
        if "Runny or Stuffy Nose" in self.selected_symptoms:
            print("- Decongestants (e.g., pseudoephedrine)")

        if "Sore Throat" in self.selected_symptoms:
            print("- Throat lozenges or sprays")

        if "Cough" in self.selected_symptoms:
            print("- Cough suppressants (e.g., dextromethorphan)")

        if "Headache" in self.selected_symptoms or "Body Aches" in self.selected_symptoms:
            print("- Pain relievers and fever reducers (e.g., acetaminophen, ibuprofen)")

        print("\nRemember to stay hydrated and get plenty of rest.")

if __name__ == "__main__":
    symptom_checker = SymptomChecker()
    symptom_checker.select_symptoms()
    symptom_checker.get_treatment_recommendation()
