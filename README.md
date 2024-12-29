# **Rapport : Installation de PfSense sur VirtualBox**

---

**Introduction**

Dans le cadre de ce TP, nous allons apprendre à installer et configurer le pare-feu PfSense sur Oracle VirtualBox. PfSense est une solution logicielle de pare-feu open source qui offre une protection réseau avancée. La topologie du projet comprend un pare-feu PfSense configuré avec des interfaces WAN et LAN, ainsi que deux machines clientes (Linux Mint et Ubuntu) connectées à l’interface LAN pour tester la connectivité et les fonctionnalités réseau.

---

**1. Prérequis**

Avant de commencer l’installation, anous devons se disposer des éléments suivants :

- **Oracle VirtualBox** : Téléchargez et installez la dernière version d’Oracle VirtualBox à partir du site officiel.
- **Image PfSense** : Téléchargez l’image ISO de PfSense à partir de [ce lien](https://getlabsdone.com/how-to-install-pfsense-on-virtualbox/). Il faut choisir le programme d’installation d’images DVD (ISO) et le miroir le plus proche de votre emplacement.
- voilà l'image que j'ai utilisée:


![image](https://github.com/user-attachments/assets/ce30cf65-a6fc-4953-a15d-7f1f4e31413f)


---

**2. Création d’une machine virtuelle pour PfSense**

1. **Ouvrez VirtualBox** et cliquez sur **Nouvelle** pour créer une nouvelle machine virtuelle.
2. Donnez un nom à la VM, par exemple « PfSense », et choisissez « BSD » comme type et « FreeBSD (64 bits) » comme version.
3. Attribuez au moins **1024 Mo de RAM** à la machine virtuelle.
4. Créez un disque dur virtuel de type **VDI** avec une taille d’environ **10 Go**.


![Screenshot 2024-12-27 111325](https://github.com/user-attachments/assets/50559f09-83f7-4669-b715-ee6aa9a513c4)


---

**3. Configuration des interfaces réseau**

1. Dans les paramètres de la VM PfSense, accédez à la section **Réseau**.
2. Configurez deux adaptateurs réseau :
   - **Adaptateur 1** : Sélectionnez « NAT » pour permettre à PfSense de se connecter à Internet.
   - **Adaptateur 2** : Sélectionnez « Réseau interne » (Internal Network) pour la connexion LAN.


![Screenshot 2024-12-27 111401](https://github.com/user-attachments/assets/c4297794-7d96-4e16-aee1-378ecc71d11f)

---

**4. Installation de PfSense**

1. Démarrez la VM PfSense et sélectionnez l’image ISO de PfSense comme source de démarrage.
2. Suivez les étapes de l’installation :
   - Sélectionnez « Install » dans le menu de démarrage.
   - Choisissez les paramètres de clavier appropriés.
   - Acceptez les paramètres par défaut pour la disposition des disques.
   - Une fois l'installation terminée, redémarrez la VM.

![image](https://github.com/user-attachments/assets/e85e5eaa-07ae-40ae-b279-4e407188c318)

![image](https://github.com/user-attachments/assets/989285a4-0b03-48e8-b6ab-9847d6c1669d)

![image-86](https://github.com/user-attachments/assets/80d0c2da-f91f-4df6-95c8-aa42f84e4cf4)

![Screenshot 2024-12-27 111443](https://github.com/user-attachments/assets/8f0a76d8-3160-4925-bed0-002197965f17)

---

**5. Configuration initiale de PfSense**

1. Une fois PfSense démarré, configurez les interfaces :
   - **WAN** : Assurez-vous qu’il est connecté à l’adaptateur NAT.
   - **LAN** : Assurez-vous qu’il est connecté à l’adaptateur interne.
2. Notez les adresses IP attribuées à chaque interface.
3. Connectez-vous à l’interface Web de PfSense en utilisant l’adresse IP LAN depuis un navigateur (dans mon cas, http://192.168.1.1).
4. Suivez l’assistant de configuration pour configurer des paramètres tels que le mot de passe administrateur et les options de réseau.

![image](https://github.com/user-attachments/assets/48688a75-7287-4a6c-aca0-6ad2e796be61)

![image](https://github.com/user-attachments/assets/17b4db11-016c-4935-910e-90188d56beb6)

---

**6. Simulation de l’environnement utilisateur**

1. Créez deux nouvelles machines virtuelles dans VirtualBox :
   - Une VM avec Linux Mint.
   - Une VM avec Ubuntu.
2. Connectez les deux machines à l’adaptateur interne (Internal Network) configuré précédemment.
3. Vérifiez que chaque machine peut communiquer avec PfSense et accéder à Internet via l’interface LAN.
![image](https://github.com/user-attachments/assets/3b36099f-bca5-4d3c-8b71-49a61ad19852)


---

**Conclusion**

Ce TP vous a guidé à travers les étapes essentielles pour installer et configurer PfSense sur VirtualBox. En configurant les interfaces WAN et LAN, puis en simulant des machines clientes, nous avons créé un environnement réaliste pour tester les fonctionnalités réseau et la connectivité. PfSense s’est avéré être une solution fiable pour gérer et protéger un réseau virtuel. Vous pouvez maintenant ajouter des captures d’écran des résultats obtenus pour documenter chaque étape.




Réalisé par : Ilham OULAKBIR

