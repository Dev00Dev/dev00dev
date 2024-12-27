import tkinter as tk
from tkinter import ttk

# Créer la fenêtre principale
root = tk.Tk()
root.title("Interface avec cases et widgets")

# Créer une bannière avec une image (via un lien ou fichier local)
banner_url = "https://via.placeholder.com/600x100.png?text=Bannière"  # Remplace par ton lien d'image
banner_image = tk.PhotoImage(data=banner_url)  # Si tu utilises un lien, tu dois télécharger l'image
banner_label = tk.Label(root, image=banner_image)
banner_label.pack()

# Créer un conteneur principal pour organiser les cases
main_frame = tk.Frame(root)
main_frame.pack(pady=10)

# Créer des petites cases avec des widgets à l'intérieur
for i in range(4):  # Change le nombre de cases selon besoin
    case_frame = tk.Frame(main_frame, width=100, height=100, borderwidth=2, relief="solid")
    case_frame.grid(row=i // 2, column=i % 2, padx=5, pady=5)  # Organiser les cases en 2x2

    label = tk.Label(case_frame, text=f"Case {i + 1}")
    label.pack(pady=10)
    
    # Ajouter un widget dans chaque case
    button = ttk.Button(case_frame, text="Widget")
    button.pack()

# Ajouter un bouton à la fin pour tester l'interface
test_button = ttk.Button(root, text="Test Bouton", command=lambda: print("Test bouton cliqué"))
test_button.pack(pady=20)

# Lancer l'interface
root.mainloop()
