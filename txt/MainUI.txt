# from chatbot import chatbot
from chatgpt import *
from conversationalbot import *
from flask import Flask, render_template, request


app = Flask(__name__)
app.static_folder = 'static'

@app.route("/")
def home():
    return render_template("index.html")

@app.route("/get")
def get_bot_response():
    userText = request.args.get('msg')
    # resp = str(converse(Conversation(userText))).split("bot >>",1)[1]
    # resp = str(response(userText)).split("bot >>",1)[1]
    resp = str(response(userText))
    print(resp)
    return resp
    

if __name__ == "__main__":
    app.run() 