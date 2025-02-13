#!/bin/bash


if ! command -v git &> /dev/null; then
    echo "🔄 Installation de Git..."
    sudo apt update && sudo apt install git -y
else
    echo "✅ Git est déjà installé."
fi


read -p "📝 Entrez votre nom GitHub : " username
read -p "📧 Entrez votre email GitHub : " email


git config --global user.name "$username"
git config --global user.email "$email"
echo "✅ Configuration de Git enregistrée."


if [ -f ~/.ssh/id_rsa ]; then
    echo "🔑 Une clé SSH existe déjà."
else
    
    echo "🛠 Génération d'une nouvelle clé SSH..."
    ssh-keygen -t rsa -b 4096 -C "$email" -f ~/.ssh/id_rsa -N ""

   
    eval "$(ssh-agent -s)"
    ssh-add ~/.ssh/id_rsa
    echo "✅ Clé SSH générée et ajoutée à l'agent SSH."
fi


echo "🚀 Copiez cette clé et ajoutez-la à GitHub : https://github.com/settings/keys"
echo "-----------------------------------------"
cat ~/.ssh/id_rsa.pub
echo "-----------------------------------------"

read -p "⏳ Appuyez sur [Entrée] après avoir ajouté la clé à GitHub..."


echo "🛠 Test de connexion à GitHub..."
ssh -T git@github.com

echo "✅ Configuration terminée ! Vous pouvez utiliser GitHub avec SSH."
