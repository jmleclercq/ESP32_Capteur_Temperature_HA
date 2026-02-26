# Capteur Température et humidité pour Home-assistant à partir d'un ESP32 et avec ESPHome 🚀

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![ESPHome](https://img.shields.io/badge/ESPHome-Open%20Source-orange)](https://esphome.io/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

Créer un capteur de température et d'humidité pour HA à partir d'une carte ESP32

---

## 📖 Présentation

Utiliser un ESP32 ou ESP8266 comme capteur intelligent qui communique directement avec **Home Assistant**, sans aucun passage par le cloud.

### Pourquoi ESPHome ?

* Configuration simple via fichier YAML
* Flash en une commande
* Intégration native avec Home Assistant
* Mises à jour OTA (Over-The-Air)
* 100% local

ESPHome fait partie de l’Open Home Foundation.

---

## 🧰 Matériel requis

* ESP32 [Lien amazon](https://www.amazon.fr/dp/B071P98VTG)
* Capteur DHT22 (température et humidité) [AZDelivery Capteur DHT22 Température & Humidité](https://www.amazon.fr/dp/B074MZSZYF)
* Fils Dupont
* Un ordinateur avec Python installé


---

## ⚡ Branchement

Le DHT22 possède 3 broches utiles :

| Broche DHT22 | Connexion ESP32    |
| ------------ | ------------------ |
| VCC          | 3.3V               |
| GND          | GND                |
| DATA         | GPIO4 (modifiable) |


---

## 💻 Installation d’ESPHome

Installer ESPHome via pip :

```bash
pip install esphome
```

Vérifier l’installation :

```bash
esphome version
```

---

## 📝 Exemple de configuration YAML

Créer un fichier nommé :
[Configuration YAML](config.yaml)

Ce fichier configure :

* Le nom du device
* La carte ESP32 utilisée
* Le capteur DHT22
* Une mise à jour toutes les 60 secondes

* Il faut l'éditer afin d'adapter les identifiants wifi, l'OTA password et les données de configurationIP

---

## 🚀 Flash du capteur

Brancher l’ESP32 en USB puis lancer :

```bash
esphome run capteur_salon.yaml
```

Première exécution :

* Compilation du firmware
* Flash via USB

Ensuite :

* Mises à jour automatiques via WiFi (OTA)

---

## 🔌 Intégration avec Home Assistant

Une fois flashé :

1. Connecter l’ESP au WiFi
2. Activer l’intégration ESPHome dans Home Assistant
3. Le capteur est détecté automatiquement

Aucune dépendance cloud nécessaire.

---

## 🎉 Résultat

✔ Capteur 100% local
✔ Aucune donnée envoyée à l’extérieur
✔ Intégration native Home Assistant
✔ Maintenance simple

---

## 📚 Ressources

* Documentation officielle ESPHome : https://esphome.io/
* Open Home Foundation : https://www.openhomefoundation.org/

---

## 📜 Licence

MIT © jmleclercq

---
