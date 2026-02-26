# Capteur Température et humidité pour Home-assistant à partir d'un ESP32 et avec ESPHome 🚀

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![ESPHome](https://img.shields.io/badge/ESPHome-Open%20Source-orange)](https://esphome.io/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

Créer un capteur de température et d'humidité pour HA à partir d'une carte ESP32

---

## 📖 Présentation

Si, comme moi, vous en avez assez que vos objets connectés passent par des serveurs distants simplement pour afficher la température de votre salon, ce projet est pour vous.

Grâce à **ESPHome**, il est possible de transformer un ESP32 ou ESP8266 en capteur intelligent qui communique directement avec **Home Assistant**, sans aucun passage par le cloud.

### Pourquoi ESPHome ?

* Configuration simple via fichier YAML
* Flash en une commande
* Intégration native avec Home Assistant
* Mises à jour OTA (Over-The-Air)
* 100% local

ESPHome fait partie de l’Open Home Foundation.

---

## 🧰 Matériel requis

* ESP32 (ex : Wemos D1 Mini, NodeMCU, ESP32 DevKit)
* Capteur DHT22 (température et humidité)
* Fils Dupont
* Résistance 4.7kΩ (entre DATA et VCC, souvent déjà intégrée)
* Un ordinateur avec Python installé

Temps estimé : ~30 minutes

---

## ⚡ Branchement

Le DHT22 possède 3 broches utiles :

| Broche DHT22 | Connexion ESP32    |
| ------------ | ------------------ |
| VCC          | 3.3V               |
| GND          | GND                |
| DATA         | GPIO4 (modifiable) |

⚠️ Ajouter une résistance de 4.7kΩ entre DATA et VCC pour une meilleure stabilité si elle n’est pas intégrée au module.

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

```
capteur_salon.yaml
```

Contenu :

```yaml
esphome:
  name: capteur_salon

esp32:
  board: esp32dev

sensor:
  - platform: dht
    pin: GPIO4
    temperature:
      name: "Température Salon"
    humidity:
      name: "Humidité Salon"
    update_interval: 60s
```

Ce fichier configure :

* Le nom du device
* La carte ESP32 utilisée
* Le capteur DHT22
* Une mise à jour toutes les 60 secondes

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

## 🔧 Aller plus loin

* Ajouter des relais
* Contrôler des LEDs
* Utiliser d'autres capteurs (BME280, capteur de luminosité, etc.)
* Créer un réseau domotique entièrement local

---

## 🎉 Résultat

✔ Capteur 100% local
✔ Aucune donnée envoyée à l’extérieur
✔ Intégration native Home Assistant
✔ Maintenance simple

Avec un peu de curiosité et quelques euros de matériel, vous obtenez un capteur domotique fiable et respectueux de votre vie privée.

---

## 📚 Ressources

* Documentation officielle ESPHome : https://esphome.io/
* Open Home Foundation : https://www.openhomefoundation.org/

---

## 📜 Licence

MIT © VotreNom

---
