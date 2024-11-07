# Installation de Linux (Ubuntu) en Dual Boot avec Windows

## Tables des matières

  1. Introduction
  2. Vérification de la version de Windows
  3. Transfert des fichiers sur un serveur distant
  4. Préparation du disque (partitionnement)
  5. Téléchargement de l'image ISO d'Ubuntu
  6. Création de la clé USB bootable
  7. Installation d'Ubuntu
  8. Gestion des problèmes courants

## Introduction

Le dual boot est une configuration qui permet à un ordinateur de démarrer sur deux systèmes d'exploitation différents. Cela offre la flexibilité de basculer entre Windows et Linux en fonction des besoins spécifiques, tels que l'utilisation de logiciels spécifiques à un système ou l'expérimentation de Linux pour des raisons de développement ou de cybersécurité.

## Vérification de la version de Windows

Avant de commencer, il est important de vérifier la version de Windows installée. Pour ce faire :

  1. Appuyez sur Windows + R pour ouvrir la boîte de dialogue Exécuter.

  2. Tapez winver et appuyez sur Entrée.
    
  3. Une fenêtre s'ouvrira, affichant la version de Windows et d'autres détails. Cette information est essentielle pour s'assurer que le système est compatible avec l'installation d'un second système d'exploitation.
  
## Transfert des fichiers avec SSH

Il est conseillé de sauvegarder vos fichiers importants avant toute manipulation de partitions. Vous pouvez utiliser la commande scp pour transférer des fichiers vers un serveur distant sécurisé :

  1. Connexion à un serveur distant via SSH : `ssh mounir@192.67.197.121`
    mot de passe : *******

  
  2. Vérification de l'espace disponible : `df -h`
    

  3. Création d'un dossier sauvegardes : `mkdir /root/sauvegardes`
    

  4. Transfert des fichiers : `scp C:\Users\Asus\Desktop\Sauvegardes_pc root@192.67.197.121`
    

  5. Vérification du transfert : `ls /root/sauvegardes/sauvegardes_pc`
    

## Préparation du disque (partitionnement) :

Avant l'installation, il faut libérer de l'espace pour Linux :

  1. Appuyez sur Win + X et sélectionnez Gestion des disques.

  2. Identifiez la partition Windows principale (souvent appelée "C:").

  3. Faites un clic droit et sélectionnez Réduire le volume pour libérer de l'espace non alloué.

  4. Réduisez la partition selon l'espace que vous souhaitez allouer à Linux (généralement 20 Go minimum pour Ubuntu).
    
## Téléchargement de l'image ISO d'Ubuntu

Téléchargez la dernière version d'Ubuntu depuis le site officiel https://ubuntu.com/download et choisissez la version LTS (Long Term Support) pour une stabilité accrue.

## Création de la clé USB bootable

Pour créer une clé USB bootable :

  1. Téléchargez Rufus : https://rufus.ie/fr/

  2. Branchez une clé USB (4 Go minimum).

  3. Ouvrez l'outil, sélectionnez l'image ISO d'Ubuntu et la clé USB.

  4. Configurez le schéma de partition (MBR pour les BIOS/UEFI) et cliquez sur Démarrer.

## Installation d'Ubuntu :

   1. Redémarrez l'ordinateur et accédez au BIOS/UEFI en appuyant sur F2, F10, DEL ou une autre touche spécifique selon le fabricant.

   2. Changez l'ordre de démarrage pour que la clé USB soit prioritaire.

   3. Démarrez l'installation d'Ubuntu et sélectionnez Installer Ubuntu à côté de Windows.

## Gestion des Problèmes courants :

   1. Désactivez la gestion automatique de l'espace disque si nécessaire pour réduire manuellement la partition Windows.

   2. Assurez-vous de désactiver le démarrage rapide de Windows (dans Options d'alimentation > Choisir l'action des boutons d'alimentation > décocher Activer le démarrage rapide).

   3. Si GRUB (le gestionnaire de démarrage) ne s'affiche pas après l'installation, redémarrez et accédez au BIOS pour vérifier que le disque contenant Linux est bien prioritaire, ou utilisez un outil comme Boot Repair pour configurer GRUB.

**Ces étapes garantissent un dual boot fonctionnel, vous permettant de passer aisément entre Windows et Ubuntu.**
