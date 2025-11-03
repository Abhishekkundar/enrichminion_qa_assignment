# 🐞 Bug Report – EnrichMinion QA Assignment

## 1️⃣ Bug ID: B001 – Signup accepts invalid email format
**Severity:** High  
**Module:** Signup  
**Steps to Reproduce:**
1. Go to Signup page.
2. Enter `test@` in email field and a valid password.
3. Click Signup.
**Expected Result:** Validation error should appear “Invalid email format.”  
**Actual Result:** Signup request proceeds to API call.  
**Root Cause:** Frontend (Email validation regex missing or incorrect).

---

## 2️⃣ Bug ID: B002 – Login button disabled after failed attempt
**Severity:** Medium  
**Module:** Login  
**Steps to Reproduce:**
1. Enter wrong credentials.
2. Try to log in again after error message.
**Expected Result:** User can retry login.  
**Actual Result:** Login button stays disabled until page refresh.  
**Root Cause:** Frontend (state not reset after error).

---

## 3️⃣ Bug ID: B003 – Enrichment results mismatch with uploaded data
**Severity:** High  
**Module:** Enrichment  
**Steps to Reproduce:**
1. Upload `Test_File.csv`.
2. Observe enriched results.
**Expected Result:** Each row should map to correct enriched record.  
**Actual Result:** Some records mismatch or duplicate.  
**Root Cause:** Backend (Data mapping or response indexing issue).

---

## 4️⃣ Bug ID: B004 – Verification API returns 200 for invalid email
**Severity:** Critical  
**Module:** Verification  
**Steps to Reproduce:**
1. Send `verifyEmail` request via Network tab for an invalid email.  
**Expected Result:** API should return 400 or 422.  
**Actual Result:** API returns 200 with “Invalid email” message in body.  
**Root Cause:** Backend (Improper status code handling).

---

## 5️⃣ Bug ID: B005 – Logout does not clear session token
**Severity:** High  
**Module:** Authentication  
**Steps to Reproduce:**
1. Login and logout.
2. Check LocalStorage for token.
**Expected Result:** Token should be removed.  
**Actual Result:** Token remains stored.  
**Root Cause:** Frontend (Logout function missing clearStorage).

---

## 6️⃣ Bug ID: B006 – File upload accepts non-CSV files
**Severity:** Medium  
**Module:** Enrichment Upload  
**Steps to Reproduce:**
1. Upload `.txt` or `.png` file.  
**Expected Result:** Validation error.  
**Actual Result:** File accepted.  
**Root Cause:** Frontend (missing file extension validation).

---

## 7️⃣ Bug ID: B007 – Incorrect API error message for token expiry
**Severity:** High  
**Module:** Authentication  
**Steps to Reproduce:**
1. Login.
2. Wait for token to expire.
3. Make any authenticated request.
**Expected Result:** 401 “Token expired.”  
**Actual Result:** 500 “Server error.”  
**Root Cause:** Backend (Improper error handling for expired token).

---

## 8️⃣ Bug ID: B008 – Dashboard UI misaligned on mobile view
**Severity:** Low  
**Module:** Dashboard UI  
**Steps to Reproduce:**
1. Open on a mobile device.
**Expected Result:** Responsive layout.  
**Actual Result:** Buttons overlap.  
**Root Cause:** Frontend (CSS responsiveness issue).
