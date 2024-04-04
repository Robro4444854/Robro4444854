import tkinter as tk

class PoussetteGUI:
    def __init__(self, master):
        self.master = master
        master.title("Sélection du mode de poussette")

        self.mode = tk.StringVar()
        self.mode.set("Eco")

        self.label = tk.Label(master, text="Sélectionnez le mode de poussette :")
        self.label.pack()

        self.eco_button = tk.Radiobutton(master, text="Eco", variable=self.mode, value="Eco")
        self.eco_button.pack()

        self.sport_button = tk.Radiobutton(master, text="Sport", variable=self.mode, value="Sport")
        self.sport_button.pack()

        self.sport_plus_button = tk.Radiobutton(master, text="Sport+", variable=self.mode, value="Sport+")
        self.sport_plus_button.pack()

        self.turbo_button = tk.Radiobutton(master, text="Turbo", variable=self.mode, value="Turbo")
        self.turbo_button.pack()

        self.submit_button = tk.Button(master, text="Valider", command=self.print_selection)
        self.submit_button.pack()

    def print_selection(self):
        selected_mode = self.mode.get()
        print("Mode sélectionné :", selected_mode)

def main():
    root = tk.Tk()
    poussette_gui = PoussetteGUI(root)
    root.mainloop()

if __name__ == "__main__":
    main()

