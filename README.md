# letter_transcript
This is a python program that you can transcript a letter throughout this program using an AI like GemiAI 
First of all you have to create a (.env) file inside of the VSCode and add the GemiAI API in this file.
The next step you have to write down the python code using the VSCode
After you do those steps you have to open the terminal and type: python or python3 if you are useing iOS then the file name like (python3 transcript.py) python filename.py

Now you can see the python code: 

import os
import google.generativeai as genai
from dotenv import load_dotenv

load_dotenv()

genai.configure(api_key=os.environ["GOOGLE_API_KEY"])

model = genai.GenerativeModel(model_name="gemini-1.5-flash")

uploaded_image = genai.upload_file("2.jpg", mime_type="image/jpeg")

chat_session = model.start_chat(
    history=[
        {
            "role": "user",
            "parts": [uploaded_image],
        }])

response = chat_session.send_message("Transcreva o que foi escrito acima.")
print(response.text)

