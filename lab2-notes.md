 Lab 2 – Manage Tenant Properties in Microsoft Entra ID

This lab covered viewing and configuring tenant-level settings: adding a custom domain, updating organization properties, and setting privacy contact information.

Exercise 1: Add a custom domain name

- Reviewed the tenant's existing default domain (`lodsm387934.onmicrosoft.com`) via the Microsoft 365 admin center Domains page.

![Domains page](lab2-01-domains.png)

Exercise 2: Update tenant properties

- Changed the tenant Name to "Contoso Marketing."
- Reviewed Tenant Country/Region,Data location, and Tenant ID.
- Confirmed the Technical contact and set the **Global privacy contact email.
- Saved the changes, confirmed with "Successfully updated tenant properties."

![Tenant properties updated](lab2-02-tenant-properties.png)

 Exercise 3: Set the privacy statement URL

- Added a **Privacy statement URL pointing to a SharePoint-hosted document.
 - Reviewed Country/Region and Data location alongside the new setting.

![Privacy statement URL set](lab2-03-privacy-url.png)

Key takeaways from this lab
- Tenant-level properties (name, contacts, privacy statement) are managed centrally in Entra ID and apply organization-wide.
- Custom domains must be added and verified through DNS before they can be used for user principal names.
- The privacy statement URL set here is surfaced to end users through  their My Account page.

  
 
