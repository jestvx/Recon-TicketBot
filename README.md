# 🎫 RECON Ticket-Bot – Setup & Konfiguration

Willkommen zur Installationsanleitung für den RECON Ticket-Bot.  
Diese Anleitung führt dich durch die Einrichtung und Konfiguration des Bots auf deinem Discord-Server.

---

## ⚙️ Voraussetzungen

- Node.js v18 oder höher
- Ein Discord-Bot-Token
- Lizenzschlüssel von RECON
- Bot-Dateien von uns (obfuskiert / kompiliert)

---

## 📁 1. Installation

1. **Dateien entpacken**  
   Die von uns bereitgestellte `.zip`-Datei entpacken.

2. **Abhängigkeiten installieren**  
   In das Bot-Verzeichnis wechseln und im Terminal ausführen:

   ```bash
   npm install
   ```

3. **Bot starten**  
   ```bash
   node index.js
   ```

---

## 🧩 2. Konfiguration (`config.json`)

Bearbeite die Datei `config.json` im Hauptverzeichnis:

### 🔐 Bot-Zugangsdaten

```json
"bot": {
  "token": "DEIN_DISCORD_TOKEN",
  "licensekey": "RECON-XXXXXX",
  "commandPrefix": "!ticketsetup"
}
```

> ⚠️ Ohne gültigen Lizenzschlüssel wird der Bot automatisch gestoppt.

---

### 📝 Grundeinstellungen

```json
"settings": {
  "channelNameFormat": "ticket-{user}",
  "logChannelId": "1234567890",
  "ticketPrefix": "ticket-",
  "successMessage": "✅ Dein Ticket wurde erstellt: <#{channelId}>",
  "alreadyExistsMessage": "❌ Du hast bereits ein Ticket: <#{channelId}>",
  ...
}
```

---

### 🧾 Interface (Texte & Embeds)

Hier kannst du Titel, Farben und Nachrichten anpassen:

```json
"interface": {
  "menu": {
    "placeholder": "📂 Ticketkategorie auswählen"
  },
  "embed": {
    "title": "🎫 Ticket System",
    "description": "Wähle eine Kategorie für dein Anliegen aus.",
    ...
  },
  "messages": {
    "closingMessage": "✅ Ticket wird geschlossen...",
    "transcriptMessage": "📄 Dein Ticket-Transkript:",
    ...
  }
}
```

---

### 🗂️ Ticket-Kategorien

Hier definierst du die Kategorien und wer Zugriff hat:

```json
"categories": [
  {
    "name": "Richterschaft",
    "allowedRoles": ["ROLE_ID"],
    "channelCategoryId": "CATEGORY_ID",
    "welcomeMessage": "<@{userId}> Willkommen bei {categoryName}!",
    "embed": {
      "title": "🎫 Richterschaft Ticket",
      "description": "Bitte schildere dein Anliegen...",
      "color": "#ffaa00"
    }
  }
]
```

---

## ✅ Hinweise

- Nur ein Ticket pro Nutzer gleichzeitig möglich
- Bei Klick auf "Ticket schließen" wird ein **HTML-Transkript** erstellt
- Die Lizenz wird automatisch regelmäßig geprüft (IP & Guild-ID)
- **Updates** erfolgen durch Austausch der Hauptdatei und `config.json` bei Bedarf

---

## 🧠 Support

Bei Fragen oder Lizenzproblemen melde dich bitte bei unserem RECON-Team.  
© RECON Development 2025
