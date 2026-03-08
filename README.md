# 🎰 Lucky777 — Lottery Platform

A complete, professional lottery website built for GitHub Pages hosting.

## 📁 File Structure

```
lucky777/
├── index.html          ← Homepage (hero, games, stats, testimonials)
├── play.html           ← Main play page (all 3 games + payment)
├── games.html          ← Games overview with full prize tables
├── results.html        ← Draw results + ticket checker
├── how-to-play.html    ← Complete guide + FAQ
├── css/
│   ├── main.css        ← Shared styles (nav, buttons, animations)
│   └── play.css        ← Play page specific styles
├── js/
│   ├── main.js         ← Shared JS (nav, particles, toast, utils)
│   ├── play.js         ← Game logic (Jackpot, Predict, Spin + payment)
│   └── results.js      ← Results rendering + ticket checker
└── assets/
    ├── qr.png          ← YOUR UPI QR code (add this!)
    └── og-image.png    ← Social share image (optional)
```

---

## ⚙️ SETUP — Edit These Before Going Live

### 1. Update your details in `js/main.js`

Open `js/main.js` and find the `CONFIG` block at the top:

```javascript
const CONFIG = {
  siteName:      'Lucky777',
  whatsappNum:   '919876543210',   // ← YOUR WhatsApp number (country code + number, no +)
  upiId:         'lucky777@upi',   // ← YOUR UPI ID
  upiName:       'Lucky777 Games', // ← Name on UPI
  accountName:   'Lucky777 Games',
  accountNumber: 'XXXX XXXX XXXX XXXX', // ← YOUR bank account number
  ifsc:          'SBIN0XXXXXXX',   // ← YOUR IFSC code
  bankName:      'State Bank of India',  // ← YOUR bank name
  drawTimeIST:   '8:00 PM',        // ← Your daily draw time
};
```

### 2. Add your UPI QR Code

- Generate your UPI QR from GPay/PhonePe/Paytm/bank app
- Save it as `assets/qr.png`
- In `play.html`, find the `qr-placeholder` div and replace with:
```html
<img src="assets/qr.png" alt="UPI QR Code">
```

### 3. Update WhatsApp link in footer

In all HTML files, find `wa.me/919876543210` and replace with your number.

---

## 🚀 Deploy to GitHub Pages

1. Create a GitHub account at github.com
2. Click **New Repository** → name it `lucky777` (or any name)
3. Upload all files (keep the folder structure)
4. Go to **Settings → Pages → Source → main branch → / (root)**
5. Your site will be live at: `https://yourusername.github.io/lucky777/`

---

## 🎮 Games & Pricing

| Game | Min Entry | Max Entry | Prize |
|------|-----------|-----------|-------|
| 💰 Jackpot Lottery | ₹5 | ₹50 | ₹1,77,777 |
| 🔮 Number Prediction | ₹5 | ₹50 | 35× entry |
| 🎡 Spin the Wheel | ₹10 | ₹50 | Up to 5× entry |

---

## 📱 How the WhatsApp Flow Works

1. Player fills form on `play.html`
2. Player pays via UPI / Bank Transfer  
3. Player enters their UTR/Transaction ID
4. Player clicks "Confirm My Entry"
5. A success modal shows their Ticket ID
6. "Get Ticket on WhatsApp" button opens WhatsApp with pre-filled message
7. Player sends the message to YOUR WhatsApp number
8. YOU manually send them their official ticket confirmation
9. After draw, you WhatsApp results to all players

---

## 🛠️ Customization Tips

### Change prices
In `js/play.js`, find the `PRICING` object:
```javascript
const PRICING = {
  INR: {
    jackpot: [5, 10, 20, 50],   // ← change these
    predict: [5, 10, 20, 50],
    spin:    [10, 20, 30, 50],
    max: 50,                     // ← max per ticket
  },
```

### Change jackpot amount
In `js/main.js`, find `initJackpotCounter` and change `startVal`:
```javascript
function initJackpotCounter(elId, startVal = 177777) {
```

### Change draw time
In `js/main.js`, find `initCountdown` — change `targetHour = 20` (20 = 8 PM).

### Add your winners to the ticker
In `js/main.js`, find `WINNERS_DATA` array and add/edit entries.

### Add real results
In `js/results.js`, find `DRAW_RESULTS` object and update with real draw data daily.

---

## 📞 Support

Built with ❤️ using vanilla HTML, CSS, JavaScript — no frameworks, no dependencies.
Works on iPhone, Android, all browsers. No app download required.
