import pyttsx3
import time

def speak(text):
    try:
        engine = pyttsx3.init()
        engine.say(text)
        engine.runAndWait()
        engine.stop()
        time.sleep(0.3)  # تأخير بسيط لتجنب مشاكل الصوت
    except Exception as e:
        print(f"[Error in speak()] - {e}")

print("Welcome to your chatbot!")

while True:
    user_input = input("You: ").strip()

    if user_input.lower() in ["good luck", "goodbye", "exit", "quit"]:
        response = "Goodbye! Have a nice day."
        print("Chatbot:", response)
        speak(response)
        break

    elif "what is your name" in user_input.lower():
        response = "My name is Smart Methods bot."
        print("Chatbot:", response)
        speak(response)

    elif "how are you" in user_input.lower():
        response = "I am fine, thank you!"
        print("Chatbot:", response)
        speak(response)

    elif "thank you" in user_input.lower():
        response = "You're welcome!"
        print("Chatbot:", response)
        speak(response)

    else:
        response = "Sorry, I didn't understand that."
        print("Chatbot:", response)
        speak(response)
