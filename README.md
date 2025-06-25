# Task-3
Built a chatbot using natural language processing libraries like NLTK or SPACY, capable of answering user queries.
<br>

pip install nltk spacy
<br>
     python -m spacy download en_core_web_sm 
# for SpaCy's English model
     
     import nltk
     <br>
   from nltk.chat.util import Chat, reflections

   # Define patterns and responses for the chatbot
   # Each tuple is (pattern_regex, [list_of_responses])
   pairs = [
       ['hi|hello|hey', ['Hello!', 'Hi there!', 'Greetings!']],
         <br>
       ['how are you', ["I'm a chatbot, so I don't have feelings, but I'm ready to help!", 'I am functioning correctly.']],
         <br>
       ['what is your name', ["I don't have a name.", "You can call me Chatbot."]],
         <br>
       ['quit|bye|exit', ['Goodbye!', 'See you later!', 'It was nice chatting with you.']],
   ]

   # Create a Chat object
   chatbot = Chat(pairs, reflections)
  <br>
   def simple_chatbot():
     <br>
       print("Hello! I'm a simple chatbot. Type 'quit' to exit.")
         <br>
       while True:
         <br>
           user_input = input("You: ")
             <br>
           if user_input.lower() in ['quit', 'bye', 'exit']:
             <br>
               print("Chatbot: Goodbye!")
                 <br>
               break
                 <br>
           response = chatbot.respond(user_input)
             <br>
           print(f"Chatbot: {response}")
             <br>

   if _name_ == "_main_":
       simple_chatbot()
       <br>
       import spacy

   # Load a pre-trained SpaCy model
   nlp = spacy.load("en_core_web_sm")

   def spacy_chatbot_response(text):
     <br>
       doc = nlp(text)
         
# Example: Identify entities and respond based on them
       if "weather" in text.lower():
         <br>
           return "I can't provide real-time weather information."
             <br>
       for ent in doc.ents:
         <br>
           if ent.label_ == "PERSON":

           
               return f"I don't know who {ent.text} is."

               
       return "I'm not sure how to respond to that."
  <br>
   def advanced_chatbot():
       print("Hello! I'm an advanced chatbot. Type 'quit' to exit.")  
         <br>
       while True:

       
           user_input = input("You: ")
             <br>
           if user_input.lower() in ['quit', 'bye', 'exit']:
             <br>
               print("Chatbot: Goodbye!")
                 <br>
               break
           response = spacy_chatbot_response(user_input)
             <br>
           print(f"Chatbot: {response}")

   # In a real application, you would integrate this with a more sophisticated
   # intent recognition and response generation system using techniques like
   # text classification, intent matching, and entity extraction.
     
