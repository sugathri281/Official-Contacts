# Official Contacts

Collectors, Joint Collectors, SPs, ULB Commissioners, CRDA / AGICL / ADCL, the MA&UD HoDs and their regional offices,
and Nellore officials. Anyone with the link can view and call; only signed-in staff can add, edit, delete or upload.

This is a **separate app** from Political Contacts: its own web address, its own Firebase project, its own staff logins,
and a green icon so the two are easy to tell apart on a phone.

## One-time setup (about 15 minutes)

1. **New Firebase project** — console.firebase.google.com → Add project (e.g. `official-contacts`).
2. **Firestore** — Build → Firestore Database → Create database → *production mode* → region `asia-south1` (Mumbai).
3. **Authentication** — Build → Authentication → Get started → enable **Email/Password** → *Users* → add each staff member.
4. **Web app config** — Project settings (gear) → General → Your apps → `</>` Web → copy the `firebaseConfig` values into
   **`firebase-config.js`** (this separate file is the only place they go; future updates only replace `index.html`).
5. **Rules** — Firestore Database → Rules → paste the contents of `firestore.rules` → **Publish** (saving alone does not apply it).
6. **GitHub Pages** — new repository → upload *all* files in this folder → Settings → Pages → deploy from `main` / root.
   The address GitHub gives you is the Official Contacts link.
No Storage or billing plan is needed — photos are stored compressed inside each record.

## Bringing over Collectors, Joint Collectors and Commissioners

In the **Political Contacts** app (signed in) press **💾 Backup** and keep the file. In this app (signed in) press **♻ Restore**
and choose that file. Collector, Joint Collector and ULB Commissioner records arrive with their photos; the political records
in the same file are skipped automatically. Restore never deletes anything, and doing it twice is harmless.

## Tabs and fields

| Tab | Fields (besides name, mobile, alternate mobile, email, office address, **notes**, photo) | Filters (each narrows the next) |
|---|---|---|
| Collector | District, designation, cadre | District |
| Joint Collector | District, designation, charge | District |
| SP | District, designation | District |
| ULB Commissioner | ULB name, ULB type, district, cadre/grade | ULB |
| CRDA / AGICL / ADCL | **Organization** (CRDA, AGICL or ADCL), department/section, designation | Organization → Department → Designation |
| MA&UD | **HoD / Office**, regional office, wing/section, designation, district | HoD → Regional office → Designation |
| Nellore Officials | **Group** (Municipal Corporation, Revenue, Police, Education, Other District Officials), department, designation | Group → Department → Designation |

- **All tab:** global search plus one **Organization** filter listing each HoD, CRDA, AGICL, ADCL, Collector, Joint Collector, SP,
  ULB Commissioner and each Nellore group ("Nellore – Revenue", …).
- A filter appears only when there is something to choose, so, for example, *Department* shows up once departments have been entered.
- **Search** is live on every tab and matches any word in any field (name, designation, department, district, notes, mobile).

### Keeping names consistent
- **Organization** (CRDA/AGICL/ADCL) and **Group** (Nellore) are fixed lists — a bulk-upload row with anything else is skipped and reported.
- **HoD** starts with CDMA, EnCPH, DTCP, MEPMA, SAC, APUFIDC, TIDCO and MA&UD Secretariat. When entering a contact you can pick
  one or type a new HoD. In a bulk upload, an HoD that is not already known is **listed for your confirmation** before anything is saved.
- **Department, section, regional office and designation** suggest what is already used and reuse its spelling ("engineering" → "Engineering"),
  so filters never split into near-duplicates.
- Column headings in Excel/CSV files may leave out the bracketed words ("Department" works for "Department (optional)").

### Nellore duplicates
Nellore's Collector, Joint Collector and SP are entered under **Nellore Officials** as well as their own tabs. When the same mobile number
appears in two tabs: the **All** tab shows that person once (with "Also listed in: Nellore Officials"), the phone-contacts export
includes them once, and a photo file named for that number is attached to both records. Edit both records when an officer is transferred —
the "Updated" date on each card helps spot a stale one.

## Photo file names — one standard for every tab

**`CODE_MobileNumber.jpg`** — the contact's 10-digit mobile number (no spaces, no +91), e.g. `COLL_9876543210.jpg`.

| Tab | CODE | Example |
|---|---|---|
| Collector | `COLL` | `COLL_9876543210.jpg` |
| Joint Collector | `JC` | `JC_9876543210.jpg` |
| SP | `SP` | `SP_9876543210.jpg` |
| ULB Commissioner | `COMM` | `COMM_9876543210.jpg` |
| CRDA / AGICL / ADCL | `CRDA` | `CRDA_9876543210.jpg` |
| MA&UD | `MAUD` | `MAUD_9876543210.jpg` |
| Nellore Officials | `NLR` | `NLR_9876543210.jpg` |

- The number can be the contact's primary **or** alternate mobile. A bare `9876543210.jpg` (no code) also works.
- If several records share the number, the photo goes to all of them.
- Easiest: press **📋 Photo names** — it downloads the exact file name for every contact currently shown.
- `.jpg`, `.jpeg`, `.png` accepted. Photos that can't be matched are listed after the upload, with a dropdown to assign them by hand.

## Other features (same as Political Contacts)
Call / WhatsApp sheet · photo on every card · "Updated" date · bulk upload from **CSV or Excel (.xlsx)** with downloadable templates ·
Export to CSV · **📱 Phone contacts** export (names saved as "Name (Role)", photos included, Notes optional) ·
**💾 Backup / ♻ Restore** · installs on a phone from the browser (Android: Install app; iPhone: Safari → Share → Add to Home Screen).
