 ["Wat zijn de twee lagen van het 3-lagen model?",
             "Wat is de functie van de presentatielaag in het 3-lagen model?",
             "Welke laag is verantwoordelijk voor de verwerking van zakelijke logica in het 3-lagen model??",
             "Wat is de belangrijkste taak van de gegevenslaag in het 3-lagen model?",
             "Welke laag zorgt voor de communicatie tussen verschillende applicaties en systemen in het 3-lagen model??"]
answer_choices_b = ["a)presentatie laag\n)toepassinglaag\nc)netwerklaag\nd)A en B\n:",
                  "a)verbinding maken met het netwerk\nb)interactie met de gebruiker\nc)beheer van gegevensstromen\nd)verwerking van zakelijke logica\n:",
                  "a)toepassinglaag\nb)presentatielaag\nc)gegevenslaag\nd)beveiligingslaag\n:",
                  "a)Presentatie van informatie aan de gebruiker\nb)Verwerking van gebruikersinvoer\nc)Beheer van gegevensopslag en -opvraging\nd)Communicatie met andere systemen\n:",
                  "a)Toepassingslaag\n)Netwerklaag\nc)Gegevenslaag\nd)Beveiligingslaag\n:",]
correct_choices_b = [{"D", "A en B"},
                   {"B", "interactie met de gebruiker"},
                   {"A", "toepassinglaag"},
                   {"C", "Beheer van gegevensopslag en -opvraging"},
                   {"B", "Netwerklaag"}]
answers_b = ["D",
           "B",
           "A",
           "C",
           "B"]
run = "y"
def quiz_b():
    score = 0
    for question, choices, correct_choice, answer in zip(questions_b, answer_choices_b, correct_choices_b, answers_b):
        print(question)
        user_answer = input(choices).lower()
        if user_answer in correct_choice:
            print("goed")
            score += 1
        else:
            print("Goed", answer)
    print(score, "out of", len(questions), "that is", float(score / len(questions)) * 100, "%")


#start of program
#Quiz B is people age 16 to 99
#Quiz A is people less than 16 
age = int(input("Hoe oud ben je?: "))
while run == "y":
    if age <= 5:
        leave = input("Je bent te jong. wil je nog steeds spelen? y/n: ")
        if leave == "n":
            print("Doei!")
            break
        elif leave == "y":
            print("nu ga je quiz a doen")
            quiz_a()
        else:
            break
    elif age > 99:
        leave = input("je bent te oud, wil je nog steeds spelen? y/n: ")
        if leave == "n":
            print("Doei!")
            break
        elif leave == "y":
            print("Nu ga je de 3 lagen model quiz doen")
            quiz_b()
            play_again = input("wil je de andere quiz doen? y/n: ")
            if play_again.lower() == "y":
                print("Okay, nu ga je quiz a doen")
                quiz_a()
                print("Bedankt voor het spelen, Doei!")
                break
            else:
                print("Doei!")
                break
        else:
            break
    elif age <= 1 and age < 99:
        print("nu ga je quiz A doen")
        quiz_a()
    else:
        if age <= 99:
            print("Nu ga je de 3 lagen model quiz doen")
            quiz_b()
