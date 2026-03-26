# Fayette County Farm Bureau — Farm Equipment Consignment Auction

Website + Mobile App for the annual Fayette County Farm Bureau Farm Equipment Consignment Auction.

**Live site:** `https://YOUR-USERNAME.github.io/fayette-auction/`

---

## Repo structure

```
/
├── index.html          ← Main website (Home, Map, FAQ/Terms tabs)
├── assets/
│   └── logo.png        ← Farm Bureau logo
└── README.md
```

The mobile app code lives in a separate folder. See the app repo for React Native / Expo files.

---

## Step 1 — Publish the website to GitHub Pages

1. Create a new GitHub repository (e.g. `fayette-auction`)
2. Upload all files from this folder to the repo root
3. Go to **Settings → Pages**
4. Under **Source**, choose `Deploy from a branch`
5. Select `main` branch and `/ (root)` folder
6. Click **Save**

Your site will be live at `https://YOUR-USERNAME.github.io/fayette-auction/` within a minute or two.

---

## Step 2 — Publish the Expo app and connect it to the website

### Publish the app

1. Create a free account at [expo.dev](https://expo.dev)
2. Install EAS CLI:
   ```
   npm install -g eas-cli
   ```
3. Log in:
   ```
   eas login
   ```
4. In the `fayette-auction-app` folder, run:
   ```
   eas update --channel production --message "Initial release"
   ```
5. Your app will be published and accessible via a URL like:
   ```
   https://expo.dev/@YOUR-USERNAME/fayette-auction-app
   ```

### Add the Expo link to the website

Once published, open `index.html` and find this section (around line 200):

```html
<a href="#" id="expo-link" class="app-link-btn">
```

Replace `href="#"` with your Expo URL:
```html
<a href="https://expo.dev/@YOUR-USERNAME/fayette-auction-app" target="_blank" id="expo-link" class="app-link-btn">
```

### Add the QR code

The website has a QR code placeholder in the sidebar. To add the real QR code:

1. Go to your published app URL on expo.dev
2. A QR code is displayed on the page — right-click and save it as `assets/expo-qr.png`
3. In `index.html`, find:
   ```html
   <div class="qr-box" id="qr-box">
     <p class="qr-placeholder">QR code appears here after publishing to Expo</p>
   </div>
   ```
4. Replace with:
   ```html
   <div class="qr-box" id="qr-box">
     <img src="assets/expo-qr.png" alt="Scan to open in Expo Go" style="width:100%;height:100%;object-fit:contain">
   </div>
   ```

### Add the GitHub repo link

Find the GitHub button in `index.html`:
```html
<a href="https://github.com" target="_blank" class="app-link-btn" id="github-link">
```
Replace `href="https://github.com"` with your actual repo URL:
```html
<a href="https://github.com/YOUR-USERNAME/fayette-auction" target="_blank" ...>
```

---

## Updating content each year

All event data in the website (`index.html`) is written directly in the HTML and JavaScript near the bottom of the file. Search for these sections to update:

- **Dates** — search `MARCH 14, 2026` and `March 14`
- **Schedule** — search `Consignment Check-In` section
- **Fees** — search `Key Fees at a Glance` section
- **FAQs** — find the `const FAQS = [` array in the `<script>` block
- **Terms** — find `const AUCTION_TERMS` and `const SELLER_TERMS` arrays

For the mobile app, all content is in `src/constants/data.js`.

---

## Contacts

- Office: (859) 880-2766
- Todd Clark: (859) 621-6471
- Auctioneer: Taylor Auction Company — Gary Allen Taylor, Principal Auctioneer #256494
- Online bidding: Equipmentfacts.com
