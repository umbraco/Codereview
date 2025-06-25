# 🧰 Umbraco Project Code Review

Welcome to our Umbraco code review submission template. This repository is designed to streamline how you send us your project and highlight the issues you're facing.

## 📦 Steps to Submit

1. Click the **"Use this template"** button at the top of this repository.
2. Select **Create a new repository**
3. Replace the contents of the `umbraco-project/` folder with your `.sln` and full site structure (App_Plugins, Views, Controllers, etc.)
4. Edit the `ISSUE.md` file in the root describing your issue.
5. Push your changes.
6. Share the repo URL with us.

If your repository is private, please add our GitHub team as a collaborator:
**teamcomingsoon**

---

## ✅ What to Include

- Your full `.sln` file and project folders (`Views`, `App_Plugins`, etc.)
- Any relevant custom code you're using
- A clear `ISSUE.md` that specifies where and what the problem is
- Any specific steps needed to run your project (if applicable)
  
---

## 🛠 ISSUE.md Format (Example)

```markdown
### Environment Information:
**Umbraco:** 12.2.0  
**Forms:** 12.1.1  
**Deploy:** 4.6.2  
**Installed Packages:**  
- SEO Toolkit 1.5.3  
- uSync 9.6.0  
- Contentment 4.7.0  

---

### Code For Review (Files & Lines Involved)
- `Controllers/ContactFormController.cs:88–102`  
- `Views/Partials/Forms/ContactForm.cshtml:22–40`  
- `App_Plugins/CustomValidation/validation.js:14–22`

---

### Summary
We're encountering a validation issue with the contact form on our website. 
When users submit the form without filling all required fields, the form still appears to submit successfully, and the success message is shown—despite no data being saved to the database.

---

### Expected Behavior
If required fields (like Name and Email) are left blank, the form should display inline error messages and **not** submit until all fields are valid.

---

### Steps to Reproduce
1. Navigate to `/contact-us`
2. Leave all fields empty
3. Click the "Submit" button
4. Observe that the form reloads with a success message, even though the required data is missing

---

### Additional Notes
- This issue started after upgrading from Umbraco Forms 11.x to 12.1.1.
- Client-side validation appears to be firing correctly (fields turn red), but server-side logic seems to be bypassed.
- We are using a custom controller for form submissions (`ContactFormController.cs`).
