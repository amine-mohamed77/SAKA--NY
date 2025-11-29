# 📧 EmailJS Setup Guide for Contact Form

## ✅ What's Already Done
Your contact form is now fully integrated with EmailJS! Here's what was added:
- ✅ EmailJS CDN script
- ✅ Form fields with proper IDs (name, email, message)
- ✅ JavaScript code to send emails
- ✅ Success/Error alerts
- ✅ Loading state on submit button
- ✅ Form validation

## 🚀 Setup Steps (Follow These Exactly)

### Step 1: Create EmailJS Account
1. Go to: https://www.emailjs.com/
2. Click **"Sign Up"** (top right)
3. Create account with your email
4. Verify your email address

### Step 2: Add Email Service
1. After login, go to: https://dashboard.emailjs.com/admin
2. Click **"Email Services"** in the left sidebar
3. Click **"Add New Service"**
4. Choose **Gmail** (recommended) or any other provider
5. Click **"Connect Account"**
6. Sign in with your Gmail: **mohammedattiaofficial@gmail.com**
7. Allow EmailJS to access your account
8. Click **"Create Service"**
9. **COPY the Service ID** (looks like: service_xxxxxxx)
   - You'll need this later!

### Step 3: Create Email Template
1. Go to: https://dashboard.emailjs.com/admin/templates
2. Click **"Create New Template"**
3. Replace the default template with this:

```
Subject: New Contact Form Message from {{from_name}}

---

You have received a new message from your website contact form:

From: {{from_name}}
Email: {{from_email}}

Message:
{{message}}

---

This message was sent from your SAKA website contact form.
Reply to: {{from_email}}
```

4. In the **Template Settings** (right side):
   - Set **"To Email"** to: `mohammedattiaofficial@gmail.com`
   - Set **"From Name"** to: `SAKA Contact Form`
   - Set **"Reply To"** to: `{{from_email}}`

5. Click **"Save"**
6. **COPY the Template ID** (looks like: template_xxxxxxx)
   - You'll need this later!

### Step 4: Get Your Public Key
1. Go to: https://dashboard.emailjs.com/admin/account
2. Scroll down to **"API Keys"** section
3. You'll see your **Public Key** (looks like: a long string of letters/numbers)
4. **COPY this Public Key**
   - You'll need this later!

### Step 5: Update Your HTML File
Open your `index.html` file and find these 3 lines (around line 1400 and 1416):

**Line 1400:**
```javascript
emailjs.init("YOUR_PUBLIC_KEY"); // ⚠️ REPLACE WITH YOUR PUBLIC KEY
```
Replace `YOUR_PUBLIC_KEY` with your actual Public Key from Step 4.

**Line 1416:**
```javascript
const serviceID = 'YOUR_SERVICE_ID';      // ⚠️ Replace this
```
Replace `YOUR_SERVICE_ID` with your Service ID from Step 2.

**Line 1417:**
```javascript
const templateID = 'YOUR_TEMPLATE_ID';    // ⚠️ Replace this
```
Replace `YOUR_TEMPLATE_ID` with your Template ID from Step 3.

### Example (After Replacement):
```javascript
// Before:
emailjs.init("YOUR_PUBLIC_KEY");
const serviceID = 'YOUR_SERVICE_ID';
const templateID = 'YOUR_TEMPLATE_ID';

// After (with your actual values):
emailjs.init("a1b2c3d4e5f6g7h8i9j0");
const serviceID = 'service_abc123';
const templateID = 'template_xyz789';
```

### Step 6: Test Your Form
1. Open your `index.html` in a browser
2. Scroll to the "Get In Touch" section
3. Fill in the form with test data
4. Click **"Send Message"**
5. You should see a success alert
6. Check your email: **mohammedattiaofficial@gmail.com**
7. You should receive the message within seconds!

## 🔥 Important Notes

### ✅ Advantages of EmailJS
- ✅ **No backend needed** - works with just HTML/JavaScript
- ✅ **Free plan** - 200 emails/month (upgrade for more)
- ✅ **Secure** - your email password is never exposed
- ✅ **Easy setup** - 10 minutes to complete
- ✅ **Works everywhere** - any hosting (GitHub Pages, Netlify, etc.)

### ⚠️ Security
- Your Public Key is safe to expose (it's meant to be public)
- Service ID and Template ID are also safe to expose
- Never share your EmailJS account password

### 📊 Free Tier Limits
- **200 emails per month**
- If you need more, upgrade to a paid plan ($7/month for 1000 emails)

### 🐛 Troubleshooting

**Problem: "emailjs is not defined" error**
- Solution: Make sure the EmailJS CDN script is loaded (line 1293 in your HTML)

**Problem: Emails not arriving**
- Check spam folder
- Verify your Service ID and Template ID are correct
- Check EmailJS dashboard for error logs

**Problem: "Invalid template" error**
- Make sure you used the exact template variable names: `from_name`, `from_email`, `message`
- Check your Template ID is correct

**Problem: Form doesn't submit**
- Open browser console (F12) to see errors
- Make sure all 3 IDs are replaced (PUBLIC_KEY, SERVICE_ID, TEMPLATE_ID)

## 📧 Email Template Variables

The form sends these variables to your email:
- `{{from_name}}` - Sender's name
- `{{from_email}}` - Sender's email address
- `{{message}}` - The message content

You can customize the email template in EmailJS dashboard anytime!

## 🎨 Customize Success/Error Messages

To change the alert messages, edit lines 1433 and 1445 in your HTML:

```javascript
// Success message (line 1433)
alert('✅ Success! Your message has been sent successfully. We will get back to you soon!');

// Error message (line 1445)
alert('❌ Oops! Something went wrong. Please try again later or email us directly at mohammedattiaofficial@gmail.com');
```

## 📞 Support

If you have any issues:
1. Check EmailJS documentation: https://www.emailjs.com/docs/
2. EmailJS support: https://www.emailjs.com/support/
3. Check your browser console (F12) for errors

---

## ✅ Final Checklist

Before going live, make sure:
- [ ] EmailJS account created
- [ ] Gmail service connected
- [ ] Email template created
- [ ] Public Key copied and replaced in code
- [ ] Service ID copied and replaced in code
- [ ] Template ID copied and replaced in code
- [ ] Form tested and working
- [ ] Email received successfully

---

**Your contact form is ready to use!** 🎉

Recipients will receive emails at: **mohammedattiaofficial@gmail.com**
