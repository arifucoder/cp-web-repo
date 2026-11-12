# Connect Google Reviews to the website — simple guide

Nov 12, 2026 · @Md Arif Uddin

## Before you start

This takes about 15 minutes and costs nothing. Google does not charge for this.

- Sign in to Google with the account that **owns** the CornerStone Protection Business Profile.
- Use the Google Cloud project with number **738331935178**. Google already approved this project for reviews. Do not create a new project.
- Keep the website admin open in another browser tab.

## Part 1 — Turn on 3 Google switches

1. Go to Google Cloud: [console.cloud.google.com](https://console.cloud.google.com/)
2. At the top, click the project name (next to "Google Cloud") → click the **All** tab → pick the project whose number is **738331935178**.
   - To check: the home page (Dashboard) shows **Project number** in the "Project info" box.
   - Can't find it? Stop here and tell Arif.
3. Open each link below. Check the top still shows the same project, then click **Enable**:
   - [My Business Account Management API](https://console.cloud.google.com/apis/library/mybusinessaccountmanagement.googleapis.com)
   - [My Business Business Information API](https://console.cloud.google.com/apis/library/mybusinessbusinessinformation.googleapis.com)
   - [Google My Business API](https://console.cloud.google.com/apis/library/mybusiness.googleapis.com)

If a page already says **Manage** or **Disable API**, that switch is already on. Go to the next one.

## Part 2 — Name the app

1. Go to [Branding](https://console.cloud.google.com/auth/branding) (same project at the top).
2. If you see **Get started**, click it and fill in:
   - App name: **CornerStone Reviews**
   - Support email: your email
   - Audience: **External**
   - Contact email: your email → tick the agreement → **Create**
3. On the Branding page, fill in:
   - Application home page: `https://www.cornerstoneprotection.com`
   - Application privacy policy link: `https://www.cornerstoneprotection.com/privacy-policy/`
   - **Do not upload a logo.** A logo makes Google ask for a long review.
   - Click **Save**.
4. Go to [Audience](https://console.cloud.google.com/auth/audience) → click **Publish app** → **Confirm**. It should now say **In production**.

## Part 3 — Create the keys

1. Go to [Clients](https://console.cloud.google.com/auth/clients) → click **Create client**.
2. Application type: **Web application**. Name: **CornerStone Reviews**.
3. Under **Authorized redirect URIs**, click **Add URI** and paste exactly this: `https://www.cornerstoneprotection.com/wp-admin/admin-post.php?action=cp_rev_oauth`
4. Leave everything else empty → click **Create**.
5. A box shows a **Client ID** and a **Client secret**. Click **Download JSON** to keep them. Keep this box open for Part 4.

Do not email or share the Client secret. It is like a password.

## Part 4 — Connect the website

1. Open the website admin: [Settings → CP Reviews](https://www.cornerstoneprotection.com/wp-admin/options-general.php?page=cp-reviews)
2. On the **Connection** tab, paste the **Client ID** and **Client secret** → click **Save**.
3. Click **Connect with Google** → sign in with the owner account.
   - If Google says "Google hasn't verified this app": click **Advanced** → **Go to CornerStone Reviews** → **Continue / Allow**. This is normal: the app is only for our own website.
4. Status now shows **Connected**. Open the **Locations** tab.
5. Tick **Show on site** for each location → click **Save locations** → click **Sync now**.
6. Done. Tell Arif. From now on, new reviews come in by themselves once a day.

## If something goes wrong

| You see this | Do this |
| --- | --- |
| "has not been used … or it is disabled" | Do Part 1, step 3 again in the same project. Wait 5 minutes, then try again. |
| "Quota" or "limit: 0" | Wrong project. Use project number 738331935178 (Part 1, step 2). |
| "Access blocked" or "access\_denied" | Do Part 2, step 4 (Publish app). |
| "redirect\_uri\_mismatch" | In Part 3, step 3, paste the link again exactly as written. |
| A location is missing on the Locations tab | The account you signed in with is not Owner or Manager of that location in Google Business Profile. |
| Anything else | Take a screenshot and send it to Arif. |
