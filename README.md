# HubSpot Deal → Airtable (Companies, Contacts, Orders)

🔹 Scenario: HubSpot Deal → Airtable (Companies, Contacts, Orders)
📌 Scenario overview

This Make.com scenario processes a HubSpot Deal and distributes all related data into separate Airtable tables.

The automation takes a deal as the entry point, then:

extracts and stores company data in one table,

extracts and stores associated contacts in a second table,

extracts and stores deal-related orders / offers in a third table.

Each entity is handled independently to keep Airtable data normalized, structured, and reusable.

⚙️ Scenario logic (clear flow)

Watch updated Deals in HubSpot
The scenario is triggered when a deal is updated in HubSpot.

Filter by Deal Stage
Only deals in a specific pipeline stage are processed (e.g. onboarding / qualified).

Load Deal details
Core deal information (deal name, amount, internal IDs) is retrieved.

🏢 Company processing

Get Company associated with the Deal
The scenario retrieves the company linked to the deal.

Load full Company data
Company details such as:

legal name

communication name

address

VAT ID

country, city, ZIP
are fetched from HubSpot.

Create / update Company record in Airtable

Company data is stored in the Companies (Customer Data) table

Duplicate prevention is handled via a unique Company ID

👤 Contact processing

Get Contacts associated with the Deal
All contacts linked to the deal are retrieved.

Iterate through Contacts
Each contact is processed individually.

Create / update Contact records in Airtable

Contacts are saved in a Contacts table

Each contact is linked to the corresponding Company and Deal

📦 Order / Offer processing

Extract deal-related orders / offers
Order or offer information stored on the deal is retrieved.

Create Order / Offer records in Airtable

Orders / offers are saved in a Deals / Orders table

Each record is linked back to:

the Deal

the Company

related Contacts (if needed)

🧩 Resulting Airtable structure

Companies table
One record per company (no duplicates)

Contacts table
All contacts linked to companies and deals

Orders / Deals table
Commercial data connected to both companies and contacts

This structure allows Airtable to function as a relational database, not just a flat CRM copy.

🛠 Platform & tools

Make.com (Integromat)

HubSpot CRM

Airtable

Relational data logic (Deal → Company → Contacts → Orders)

🔒 Notes

Demo / template scenario

No real client data included

Field names and IDs must be adapted to your Airtable schema
