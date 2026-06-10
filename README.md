# Bastion-Guacamole
Bastion d'administration web avec Apache Guacamole – accès RDP, SSH et VNC centralisés, HTTPS Nginx, gestion des droits par groupes et MFA TOTP.

Projet Bastion – Apache Guacamole
Centralisation et sécurisation des accès distants via un bastion d'administration web.


Description
Mise en place d'un bastion d'administration basé sur Apache Guacamole, permettant d'accéder à plusieurs machines virtuelles (Windows, Linux) depuis un navigateur web, sans client lourd à installer.

Le bastion centralise les connexions RDP, SSH et VNC, sécurise les accès via un reverse proxy HTTPS (Nginx), gère les droits par groupes d'utilisateurs et intègre une double authentification TOTP.


Stack technique
Apache Guacamole 1.5.5
Tomcat 9
Nginx (reverse proxy HTTPS)
MariaDB
OpenSSL
guacamole-auth-totp (MFA)


Architecture
Utilisateur (navigateur)

        |

        v  HTTPS :443

    Nginx (Reverse Proxy)

        |

        v  HTTP :8080 (localhost uniquement)

    Tomcat 9 + Guacamole

        |

        |-- RDP --> Windows 10   

        |-- VNC --> Debian GUI      

        |-- SSH --> Debian CLI      

Bastion : (NAT + Host-only)


Contenu du dépôt
README.md

Documentation_Bastion_Guacamole.docx

La documentation couvre l'ensemble du projet : préparation des VMs, installation et configuration de Guacamole, sécurisation HTTPS, gestion des groupes et utilisateurs, ségrégation réseau et mise en place du MFA.



Projet réalisé dans le cadre de la formation La Plateforme – 2026
