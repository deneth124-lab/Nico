# Nico
chatbox
import openai

# 🔑 Replace this with your actual OpenAI API key
openai.api_key = "your_openai_api_key"

def chat_with_nico(user_input):
    response = openai.ChatCompletion.create(
        model="gpt-4",  # Or "gpt-3.5-turbo" if you prefer
        messages=[
            {"role": "system", "content": "You are Nico, a friendly and helpful chatbot."},
            {"role": "user", "content": user_input},
        ]
    )
    return response['choices'][0]['message']['content'].strip()

def main():
    print("🤖 Nico: Hello! I'm Nico, your chatbot friend. Type 'exit' to leave.")
    while True:
        user_input = input("🧑 You: ")
        if user_input.lower() in ['exit', 'quit']:
            print("🤖 Nico: Bye! Have a great day!")
            break
        response = chat_with_nico(user_input)
        print("🤖 Nico:", response)

if __name__ == "__main__":
    main()
