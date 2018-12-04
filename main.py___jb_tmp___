from tkinter import *
import requests

#root = Tk()
#root.mainloop()

class Api:
    def __init__(self):
        self.viacep = requests
        self.cep = None
        self.logradouro = None
        self.bairro = None
        self.localidade = None




    def getCep(self,cep=""):

        buscar = self.viacep.get("http://viacep.com.br/ws/"+cep+"/json/")
        b = buscar.json()
        self.cep = b["cep"]
        self.logradouro = b["logradouro"]
        self.bairro = b["bairro"]
        self.localidade = b["localidade"]



class App:
    def __init__(self, master):
        self.api = Api()

        self.entry = Entry(master, width =27)
        self.entry.grid(columnspan=4,row=0,column=0)

        self.button = Button(master)
        self.button["text"] = "Procurar"
        self.button["command"] = lambda:self.Buscar()
        self.button.grid(row=0, column=3)

        self.label = Label(master,width=10)
        self.label["text"] = "CEP:"
        self.label["anchor"] = E
        self.label.grid(row=1, column=0)

        self.resp = Label(master,width =30)
        self.resp.grid(row=1, column=2)

        self.label1 = Label(master,width =10,anchor=E)
        self.label1["text"] = "Logradouro:"
        self.label1.grid(row=2, column=0)

        self.resp2 = Label(master, width=30)
        self.resp2.grid(row=2, column=2)

        self.label2 = Label(master,width =10,anchor=E)
        self.label2["text"] = "Bairro:"
        self.label2.grid(row=3, column=0)

        self.resp3 = Label(master, width=30)
        self.resp3.grid(row=3, column=2)

        self.label3 = Label(master)
        self.label3["text"] = "Localidade:"
        self.label3.grid(row=4, column=0,stick=E)

        self.resp4 = Label(master, width=30)
        self.resp4.grid(row=4, column=2)


    def debug(self):
        print(self.entry.get())

    def Buscar(self):
        cep = self.entry.get()
        self.api.getCep(cep)
        self.resp["text"] = self.api.cep
        self.resp2["text"] = self.api.logradouro
        self.resp4["text"] = self.api.localidade
        self.resp3["text"] = self.api.bairro




b = Tk()
App(b)
b.mainloop()