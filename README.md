

📌 **GitHub SSH Setup Script**
-----------------------------------
Automatise la configuration de Git et l'ajout de la clé SSH pour se connecter à GitHub depuis un serveur Ubuntu.

🚀 **Fonctionnalités**
-----------------------------------
✅ Vérifie et installe Git si nécessaire
✅ Configure votre nom et email Git
✅ Génère une clé SSH si inexistante
✅ Ajoute la clé SSH à l'agent SSH
✅ Affiche la clé publique pour l'ajouter à GitHub
✅ Teste la connexion avec GitHub

🛠 **Installation & Exécution**
-----------------------------------
1️⃣ **Téléchargez le script**
```bash
wget https://raw.githubusercontent.com/MedusaSH/setup-github/main/setup-github.sh
```

2️⃣ **Donnez-lui les permissions d'exécution**
```bash
chmod +x setup-github.sh
```

3️⃣ **Lancez le script**
```bash
./setup-github.sh
```

🔑 **Ajout de la clé SSH sur GitHub**
-----------------------------------
Rendez-vous sur [GitHub SSH Keys](https://github.com/settings/keys) et collez la clé affichée par le script.

📡 **Test de connexion**
-----------------------------------
Après avoir ajouté la clé sur GitHub, testez votre connexion avec :
```bash
ssh -T git@github.com
```
Vous devriez voir :
```
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

📜 **Licence**
-----------------------------------
🔓 Ce projet est open-source et sous licence MIT. Vous pouvez l'utiliser librement !

💬 **Contact & Contributions**
-----------------------------------
📩 Vous avez une suggestion ou une amélioration ? Ouvrez une issue ou envoyez un pull request sur GitHub !

🌟 **Si ce projet vous aide, laissez une étoile ⭐ sur GitHub !**
