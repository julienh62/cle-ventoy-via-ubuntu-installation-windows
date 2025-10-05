# Création d’une clé USB d’installation de Windows 11 avec Ventoy (Ubuntu)

## 🧰 Prérequis
- Une clé USB (≥ 8 Go)
- Ubuntu ou une distribution Linux
- Un fichier ISO de **Windows 11**
- Droits administrateur (`sudo`)
- Une connexion Internet

---

## ⚙️ Étapes effectuées

### 1. Vérifier la clé USB
Lister les disques connectés pour repérer le nom de la clé :
```bash
lsblk -o NAME,SIZE,FSTYPE,LABEL,MOUNTPOINT

➡️ Exemple de sortie :

sdb          14,4G
└─sdb1       14,4G vfat WINUSB

Ici, la clé est /dev/sdb.
2. Formater la clé USB

(Ventoy va de toute façon reformater la clé, mais on s’assure qu’elle est propre.)

sudo mkfs.vfat -F 32 -n "WINUSB" /dev/sdb1

3. Télécharger et installer Ventoy

Aller dans le dossier Téléchargements :

cd ~/Téléchargements

Extraire l’archive :

tar -zxvf ventoy-1.1.07-linux.tar.gz
cd ventoy-1.1.07

Installer Ventoy sur la clé en mode GPT (recommandé pour Windows 11 / UEFI) :

sudo ./Ventoy2Disk.sh -i -g /dev/sdb

    ⚠️ Attention : Toutes les données sur /dev/sdb seront effacées.

4. Vérifier la création

Ventoy crée deux partitions :

sdb          14,4G
├─sdb1       14,4G exfat    Ventoy
└─sdb2         32M vfat     VTOYEFI

✅ Cela signifie que Ventoy est correctement installé.
5. Télécharger l’image ISO de Windows 11

Aller sur le site officiel de Microsoft :
👉 https://www.microsoft.com/software-download/windows11

Sélectionner :

    Windows 11 (version 25H2 ou plus récente)

    Français

    64 bits (x64)

Télécharger le fichier .iso.
6. Copier l’ISO sur la clé Ventoy

Une fois le fichier téléchargé, le copier simplement sur la partition Ventoy :

cp ~/Téléchargements/Win11_French_x64.iso /media/$USER/Ventoy/

    Aucun outil spécial requis : Ventoy détectera automatiquement les ISO.

7. Démarrer sur la clé

    Brancher la clé USB sur le portable (ex : HP Pavilion).

    Démarrer l’ordinateur et ouvrir le menu de démarrage (souvent Échap, F9, ou F12).

    Choisir la clé Ventoy.

    Dans le menu Ventoy, sélectionner le fichier Windows 11.iso.

💡 Notes techniques

    MBR vs GPT :

        MBR = format ancien, compatible BIOS.

        GPT (GUID Partition Table) = format moderne, requis pour Windows 11 et UEFI.

    L’option -g de Ventoy crée automatiquement une table GPT.

    Ventoy permet d’avoir plusieurs ISO sur la même clé.

✅ Résultat attendu

Votre clé USB est maintenant bootable avec Ventoy, prête à installer Windows 11 en mode UEFI.

Ventoy installé avec succès
Fichier ISO copié
Clé prête pour installation Windows 11

© 2025 — Créé sur Ubuntu avec ❤️ et Ventoy
COINDUFEU20

Entrer dans le BIOS / UEFI du HP Pavilion.

Vérifier l’ordre de démarrage :

USB Hard Disk ou USB Key en premier.

Secure Boot peut rester activé si Ventoy est compatible (Ventoy 1.1.07 supporte Secure Boot).
Laisse Secure Boot désactivé pour vaentoy si soucis  
reactivé secure boot une fois l'installation ok
Brancher la clé Ventoy avec l’ISO de Windows 11.

5. Installation de Windows 11

Démarrer depuis la clé Ventoy.

Dans le menu Ventoy, sélectionner l’ISO de Windows 11.

Choisir Normal Boot (ou WinBoot si nécessaire).

Supprimer les partitions du disque contenant l’ancien Windows (disque cible pour la nouvelle installation) :

Supprimer toutes les partitions existantes sur ce disque (y compris la partition de récupération).

Sélectionner l’espace non alloué pour installer Windows 11.

Windows créera automatiquement les partitions nécessaires (EFI, MSR, partition principale).

⚠️ Important : Toutes les données sur le disque cible seront définitivement effacées.

6. Après installation

Retirer la clé Ventoy.

Le HP Pavilion devrait démarrer sur le nouvel Windows 11 fraîchement installé.

Reconfigurer éventuellement les disques secondaires si tu souhaites conserver des données.

Résumé :
Nous avons préparé une clé USB bootable avec Ventoy, copié l’ISO Windows 11, nettoyé l’ancien disque Windows et configuré le BIOS pour un démarrage UEFI sécurisé. L’installation peut maintenant se dérouler proprement.




