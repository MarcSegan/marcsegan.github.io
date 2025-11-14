# marcsegan.github.io
Segan.com website


# Connecting **segan.com** to GitHub Pages

**GitHub Pages site:** https://marcsegan.github.io  
**GitHub repo:** https://github.com/MarcSegan/marcsegan.github.io  
**Domain registrar:** Network Solutions  
**Hosting:** GitHub Pages (User Site)

---

## 1. Update DNS at Network Solutions

Log into:  
https://www.networksolutions.com/manage-account

Navigation:

**My Products & Services → Domain Names → segan.com → Manage → Advanced Tools → Advanced DNS Records**

You will update:

- A Records (for `segan.com`)
- CNAME Records (for `www.segan.com`)

---

## A. A Records (root domain)

Delete these if they exist:

- `@` → 208.91.197.27  
- `www` → 208.91.197.27  
- `*` (wildcard) → 208.91.197.27  

Add all four GitHub Pages A records:

@ A 185.199.108.153 TTL 2h
@ A 185.199.109.153 TTL 2h
@ A 185.199.110.153 TTL 2h
@ A 185.199.111.153 TTL 2h



These point **segan.com** to GitHub Pages.

---

## B. CNAME Record (www)

Delete any A record for `www`.

Add this CNAME:
www CNAME marcsegan.github.io TTL 2h


Notes:

- No `https://`
- No trailing slash
- Must be lowercase

---

## 2. Configure GitHub Pages

Go to:  
https://github.com/MarcSegan/marcsegan.github.io

Navigation:

**Settings → Pages**

Under “Custom domain,” enter:
segan.com

Click **Save**, then enable:
[✓] Enforce HTTPS

GitHub will issue an SSL certificate.

---

## 3. Verify DNS Propagation

Use DNS checker:

https://dnschecker.org/#A/segan.com

Expected A records:

- 185.199.108.153  
- 185.199.109.153  
- 185.199.110.153  
- 185.199.111.153  

Once these appear globally, your domain is fully connected.

---

## 4. Expected Result

- **https://segan.com** → loads GitHub Pages  
- **https://www.segan.com** → loads GitHub Pages  
- HTTPS is active  
- Future updates: commit to your GitHub repo

---

## 5. Location recap

### At Network Solutions
- **Advanced Tools → Advanced DNS Records**
  - Update A Records (root `@`)
  - Update CNAME Records (`www`)

### At GitHub
- **Repo → Settings → Pages → Custom Domain**

---



