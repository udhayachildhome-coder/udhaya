udhayachildhome@gmail.com
Password: Stpaul@179


Supabase

Project Name : udhayachildhome
Udhaya@2026


GitHub Signup
udhayachildhome-coder



Below is a **complete first-cut scope document** you can give to Claude.

Save this as:

```txt
UDHAYA_APP_FULL_SCOPE_v0.1.md
```

---

# UDHAYA CHILDREN HOME ADMIN & FINANCIAL APP

## Full Scope Document v0.1

**Project Name:** Udhaya Children Home Admin Portal
**Version:** v0.1
**Purpose:** Build a secure, mobile-friendly, audit-ready financial and student management application for Udhaya Children Home.
**Frontend Stack:** React + HTML + CSS + JavaScript
**Hosting:** Vercel
**Backend/Data:** Supabase
**Storage:** Supabase Storage for active files
**Archive/Backup:** Google Drive for long-term archive copy
**Primary Users:** Super User, Admin, Limited User/Staff
**Public Website Relationship:** Selected approved data may later be shared to the public Udhaya website.

---

# 1. Project Objective

Build a professional web and mobile-compatible application for Udhaya Children Home to manage:

```txt
Student registration
Children profiles
Income/donations
Daily expenses
Administration expenses
Boys building expenses
Girls building expenses
Receipt uploads
Approval workflow
Clarification workflow
Reports
Balance sheet
Invoices
Audit records
File retention
Google Drive archive
Settings/configuration
Role-based access
```

The app should support real financial audit use. It should preserve transaction history, receipts, approval logs, currency conversions, and document references.

The app should be usable from:

```txt
Desktop browser
Tablet browser
Mobile browser
Vercel public URL
```

---

# 2. High-Level Architecture

```txt
Frontend:
React app hosted on Vercel

Authentication:
Supabase Auth

Database:
Supabase Postgres

Active File Storage:
Supabase Storage

Archive Storage:
Google Drive archive folder

Email Notifications:
Later phase using Supabase Edge Functions / EmailJS / SendGrid / Resend

Public Website Sharing:
Later phase with approved-safe data only
```

---

# 3. Important Security Principle

The app contains sensitive data:

```txt
Children details
Student profiles
Donor details
Financial transactions
Receipts
Invoices
Audit reports
Approval records
```

Therefore:

```txt
Do not expose private app data to the public website.
Do not hardcode production passwords.
Do not store real financial data during prototype.
Use Supabase Auth and role-based access for production.
Use Row Level Security in Supabase later.
Restrict receipt/document access by role.
Keep audit logs for all sensitive actions.
```

---

# 4. Prototype Admin Shortcut

For the first UI prototype only:

```txt
Ctrl + Shift + A opens Admin Mode password modal
Temporary password: admin2026
```

If correct:

```txt
Switch to Admin Mode
Show Admin badge
Reveal admin menu
```

Important:

```txt
This is prototype only.
Must be removed before production.
Production must use Supabase Auth and roles.
```

---

# 5. User Roles

## 5.1 Super User

Full access.

Can:

```txt
Manage all users
Manage settings
Approve high-value transactions
Change approval rules
View all financial reports
View all receipts/documents
Archive files
Approve Supabase cleanup
Manage audit exports
Lock/unlock periods
Configure retention policies
```

## 5.2 Admin

Operational access.

Can:

```txt
Create and edit students
Enter income
Enter expenses
Upload receipts
Review pending approvals if assigned
Generate reports
View balance sheet
Generate invoices
View audit logs
Manage basic settings
```

## 5.3 User / Staff

Limited access.

Can:

```txt
Submit expenses
Upload receipts
View own submissions
Respond to clarification requests
View limited student information
View limited dashboard
```

Cannot see:

```txt
Full balance sheet
Donor full details
Sensitive student documents
System settings
Audit logs
All receipts
User management
Archive cleanup
```

---

# 6. UI Design Direction

The design should feel:

```txt
Warm nonprofit style
Professional financial admin system
Clean and simple
Mobile-first for field data entry
Audit-friendly
Card-based
Easy to navigate
```

## Suggested Colors

```txt
Primary: Deep green or royal blue
Accent: Gold / saffron
Background: Soft cream / light gray
Cards: White
Success: Green
Warning: Amber
Error: Red
Info: Blue
```

## Layout

Desktop:

```txt
Left sidebar
Top header
Main content area
Cards, tables, forms
```

Mobile:

```txt
Top header
Bottom navigation
Stacked cards
Single-column forms
Large buttons
Camera receipt upload
Sticky submit button
```

---

# 7. Main Navigation

## Admin/Super User Menu

```txt
Dashboard

Student Management
- Student Registration
- Children Details
- Student Profiles

Finance
- Income Tracker
- Daily Expenses
- Administration Expenses
- Boys Building Expenses
- Girls Building Expenses

Audit & Control
- Approvals
- Receipts
- Invoices
- Reports
- Balance Sheet
- Audit Log
- Storage Cleanup & Archive Review

System
- Settings
```

## User Menu

```txt
Dashboard
Submit Expense
Upload Receipt
My Submissions
Student View
```

---

# 8. Main Modules

## Module 1: Login & App Shell

Build:

```txt
Login screen
App shell
Desktop sidebar
Mobile navigation
Top header
Role badge
Logout button
Admin/User mode
Ctrl+Shift+A admin shortcut for prototype
Protected page simulation
```

Login screen should include:

```txt
Udhaya logo placeholder
Title: Udhaya Children Home Admin Portal
Subtitle: Secure Financial & Student Management System
Username/email field
Password field
Login button
Forgot password placeholder
Mission quote
```

---

## Module 2: Dashboard

Admin dashboard should include cards:

```txt
Total Income This Month
Total Expenses This Month
Current Balance
Pending Approvals
Receipts Missing
Student Count
Boys Building Expense
Girls Building Expense
Administration Expenses
Storage Used
Files Eligible for Archive
```

Dashboard sections:

```txt
Monthly Income vs Expense chart placeholder
Recent Transactions table
Approval Queue table
Receipt Missing alert
Storage summary
```

User dashboard should include:

```txt
My Pending Submissions
My Approved Submissions
Clarification Needed
Quick Submit Expense
Upload Receipt
```

---

## Module 3: Settings

Settings is the central configuration area.

Settings sections:

```txt
User & Role Settings
Currency Settings
Expense Category Settings
Income Category Settings
Approval Workflow Settings
Receipt Upload Settings
Email Notification Settings
Invoice Settings
Student Profile Settings
Audit & Export Settings
Security Settings
Website Sharing Settings
File Retention & Archiving Settings
Archive & Backup Settings
```

Settings page layout:

```txt
Left settings menu
Right detail panel
Reusable settings tables
Add/edit/delete configuration UI
Sample data for prototype
```

---

# 9. Currency Requirements

The app must support:

```txt
USD
INR
NZD
```

Currency should be audit-ready.

Every transaction must store:

```txt
Original amount
Original currency
Exchange rate used
Base currency
Base amount
Exchange rate date
Manual override yes/no
Currency note
```

Recommended default base currency:

```txt
INR
```

But base currency should be configurable in Settings.

## Currency Settings Fields

```txt
Currency code
Currency name
Symbol
Country
Active status
Default exchange rate to base currency
Last updated date
Base currency flag
```

Example:

```txt
Donation received: 500 USD
Exchange rate: 1 USD = 83 INR
Base amount: 41,500 INR
```

---

# 10. Student Registration Module

Purpose:

```txt
Create and manage student records.
```

Fields:

```txt
Student ID
Badge number
Full name
Preferred name
Gender
Date of birth
Age
Photo
Admission date
Current status
Class/grade
School name
Academic year
Health notes
Education notes
Guardian name
Guardian relationship
Guardian contact
Sponsor linked yes/no
Sponsor name
Building
Room/dorm
Documents uploaded
Created by
Updated by
Created date
Updated date
```

Badge number format:

```txt
UDH-STU-2026-001
UDH-STU-2026-002
```

Badge should be auto-generated.

Student status values:

```txt
Active
Inactive
Graduated
Transferred
Alumni
Under Review
```

---

# 11. Student Profile Page

Each student should have a profile page.

Sections:

```txt
Basic Information
Photo
Badge Number
Education Details
Health Details
Guardian/Family Details
Sponsorship Details
Expense History
Documents
Notes
Audit History
```

Student profile tabs:

```txt
Basic Info
Education
Health
Sponsorship
Expenses
Documents
Notes
Audit
```

Sensitive child data should be visible only to Admin and Super User.

---

# 12. Children Details Module

Purpose:

```txt
Manage broader child care details beyond registration.
```

Track:

```txt
Dorm/building allocation
Daily needs
Medical notes
Education progress
Sponsor mapping
Document tracking
Special care notes
Status history
```

Do not expose this data publicly unless manually approved for website sharing.

---

# 13. Income Tracker Module

Purpose:

```txt
Track donations, sponsorships, grants, and other income.
```

Income types:

```txt
Donation
Monthly Sponsorship
One-time Sponsorship
Grant
Church Contribution
Event Collection
Bank Interest
Refund
Other Income
```

Fields:

```txt
Income ID
Date received
Donor name
Donor type
Country
Currency
Original amount
Exchange rate
Base amount
Payment method
Bank account
Reference number
Purpose
Restricted/unrestricted fund
Related student
Related building
Receipt generated yes/no
Invoice generated yes/no
Attachment
Approval status
Entered by
Approved by
Created date
Updated date
Audit notes
```

Filters:

```txt
Date range
Currency
Donor
Country
Income type
Purpose
Payment method
Approval status
Student-linked income
Building-linked income
```

---

# 14. Expense Modules

Expense modules should be separate for audit clarity:

```txt
Daily Expenses
Administration Expenses
Boys Building Expenses
Girls Building Expenses
```

Common expense fields:

```txt
Expense ID
Expense date
Expense type
Category
Subcategory
Vendor name
Description
Amount
Currency
Exchange rate
Base amount
Payment method
Paid by
Building allocation
Student allocation if any
Receipt uploaded yes/no
Receipt file link
Approval status
Clarification required yes/no
Clarification comments
Entered by
Approved by
Created date
Updated date
Audit note
```

## Daily Expense Examples

```txt
Food
Milk
Vegetables
Rice
Cooking gas
Cleaning items
School supplies
Transport
Small repairs
```

## Administration Expense Examples

```txt
Office expenses
Bank charges
Legal/documentation
Accounting fees
Software/subscription
Phone/internet
Printing/stationery
Staff admin expenses
```

## Boys Building Expense Examples

```txt
Maintenance
Utilities
Room repairs
Building supplies
Boys-specific welfare expenses
```

## Girls Building Expense Examples

```txt
Maintenance
Utilities
Room repairs
Building supplies
Girls-specific welfare expenses
```

---

# 15. Receipt & Document Management

Purpose:

```txt
Upload, compress, store, preview, and link receipts/documents to transactions.
```

Requirements:

```txt
Upload receipt from mobile camera
Upload receipt from desktop
Upload PDF bills
Compress images before upload
Link receipt to income/expense/student/invoice
Preview receipt on screen
Download receipt
Replace receipt with audit reason
Mark receipt as missing
Mark receipt as unreadable
Allow multiple receipts per transaction
Do not allow direct deletion without audit
```

Mobile camera input:

```html
<input type="file" accept="image/*" capture="environment" />
```

Compression rules:

```txt
Convert image to JPEG/WebP
Resize max width to 1200px or 1600px
Compress quality to 60–75%
Target file size: 300 KB to 700 KB where possible
Keep receipt readable
Do not upload original large phone photos unless required
```

Receipt status values:

```txt
Uploaded
Missing
Unreadable
Rejected
Re-upload Required
Approved
Archived
```

Receipt/document fields:

```txt
Receipt ID
Linked transaction ID
Linked transaction type
File name
File type
Original file size
Compressed file size
Upload date
Uploaded by
Storage path
Receipt status
OCR text future option
Audit note
```

---

# 16. Approval Workflow

Purpose:

```txt
Control when income and expense records become official for reporting.
```

Workflow statuses:

```txt
Draft
Submitted
Pending Review
Clarification Required
Resubmitted
Approved
Rejected
Posted to Reports
Locked for Audit
```

Approval rules should be configurable.

Example rules:

```txt
Expense below ₹1,000: one-level approval
Expense ₹1,000 to ₹10,000: Admin approval
Expense above ₹10,000: Super User approval
Missing receipt: cannot approve unless exception reason is entered
Foreign currency entry: requires exchange rate validation
```

Clarification loop:

```txt
Approver requests clarification
Approver enters comment/question
Submitter receives notification
Submitter adds details or receipt
Submitter resubmits
Approval continues
```

Approval fields:

```txt
Approval ID
Transaction ID
Transaction type
Current status
Submitted by
Submitted date
Reviewer
Reviewer role
Review date
Decision
Clarification comments
Resubmission comments
Final approved by
Final approved date
Audit lock status
```

---

# 17. Email Notification Workflow

For prototype, email can be simulated in UI.

Later production email triggers:

```txt
New expense submitted
New income submitted
Approval required
Clarification requested
Clarification response submitted
Transaction approved
Transaction rejected
Receipt missing
Invoice generated
Monthly report ready
Archive cleanup approval required
```

Possible email tools later:

```txt
Supabase Edge Functions
EmailJS
SendGrid
Resend
SMTP service
```

---

# 18. Invoice & Document Generation

Purpose:

```txt
Generate and store official donation receipts, vouchers, invoices, and PDFs.
```

Use cases:

```txt
Donation receipt
Sponsor contribution receipt
Expense reimbursement document
Vendor payment invoice record
Internal voucher
```

Invoice fields:

```txt
Invoice ID
Invoice number
Invoice type
Linked transaction
Donor/vendor name
Date
Currency
Amount
Tax or registration details if applicable
Purpose
Prepared by
Approved by
PDF link
Status
```

Invoice number examples:

```txt
UDH-INV-2026-0001
UDH-DON-2026-0001
UDH-VCH-2026-0001
```

Invoice status:

```txt
Draft
Generated
Sent
Paid
Cancelled
Archived
```

---

# 19. Reports Module

Reports should be filterable and exportable.

## Weekly Reports

```txt
Weekly income summary
Weekly expense summary
Weekly pending approvals
Weekly receipt missing report
Weekly building-wise expenses
```

## Monthly Reports

```txt
Monthly income vs expense
Monthly category-wise expense
Monthly donor contribution
Monthly student sponsorship
Monthly boys building expense
Monthly girls building expense
Monthly admin expense
Monthly receipt audit
Monthly cash/bank balance
```

## Yearly Reports

```txt
Yearly income statement
Yearly expense statement
Yearly balance sheet
Yearly donor report
Yearly student expense report
Yearly building expense report
Yearly audit packet
```

## Audit Reports

```txt
All transactions with receipts
Transactions without receipts
Approved transactions
Rejected transactions
Clarification history
Currency conversion report
Modified transaction report
Deleted/voided transaction report
User activity report
Approval aging report
Archive cleanup report
```

Report filters:

```txt
Date range
Financial year
Currency
Base currency
Donor
Vendor
Expense category
Income category
Building
Student
Payment method
Approval status
Receipt status
Fund type
```

Export options:

```txt
PDF
Excel
CSV
```

---

# 20. Balance Sheet Module

Purpose:

```txt
Show financial position summary for audit and management.
```

Balance sheet sections:

```txt
Opening Balance
Total Income
Total Expenses
Current Balance
Cash in Hand
Bank Balance
Receivables
Payables
Restricted Funds
Unrestricted Funds
Building-specific balances
Student-specific sponsorship balances
```

Important rule:

```txt
Only approved and posted transactions should be counted in official audit reports.
Draft, pending, and clarification transactions should appear separately.
```

Filters:

```txt
Date range
Financial year
Currency
Base currency
Building
Fund type
Approval status
```

---

# 21. Audit Log Module

Every important action should be logged.

Audit log should capture:

```txt
User
Action
Module
Record ID
Old value
New value
Timestamp
Reason for change
Approval impact
Device/IP later
```

Example actions:

```txt
Created expense
Updated amount
Uploaded receipt
Replaced receipt
Submitted for approval
Requested clarification
Approved transaction
Rejected transaction
Generated invoice
Exported report
Changed setting
Activated admin mode
Archived file
Deleted Supabase file after archive
Placed legal hold
```

---

# 22. Donor Management

Add donor management to avoid future redesign.

Fields:

```txt
Donor ID
Donor name
Donor type
Country
Email
Phone
Preferred currency
Donation history
Sponsorship commitment
Tax receipt required yes/no
Communication notes
Active status
```

Donor types:

```txt
Individual
Church
Organization
Corporate
Family
Other
```

---

# 23. Sponsor Management

Fields:

```txt
Sponsor ID
Sponsor name
Linked student
Monthly amount
Currency
Payment frequency
Start date
End date
Status
Notes
```

Sponsor status:

```txt
Active
Paused
Completed
Cancelled
Under Review
```

---

# 24. Vendor Management

Fields:

```txt
Vendor ID
Vendor name
Vendor type
Contact person
Phone
Email
Address
Tax/GST number if applicable
Payment history
Active status
```

---

# 25. Bank / Cash Account Tracking

Track:

```txt
Cash in hand
Bank account
Digital wallet
Payment method
Transfer records
Bank reference number
```

Payment methods:

```txt
Cash
Bank Transfer
Check
Card
Online Payment
Digital Wallet
Other
```

---

# 26. Budget Module

Add budget support for planning.

Track:

```txt
Monthly budget
Category budget
Building budget
Student budget
Actual vs budget
Variance
Budget alerts
```

Budget comparison:

```txt
Budget Amount
Actual Amount
Variance Amount
Variance Percentage
Status
```

---

# 27. Opening Balance & Period Locking

Each financial year should start with:

```txt
Opening cash balance
Opening bank balance
Opening restricted fund balance
Opening unrestricted fund balance
```

After audit/month close:

```txt
Lock period
Prevent direct edits
Allow correction only through adjustment entry
```

Adjustment types:

```txt
Correction entry
Reversal entry
Currency adjustment
Receipt correction
Opening balance correction
```

---

# 28. File Retention & Archiving Settings

Add this under Settings:

```txt
File Retention & Archiving Settings
```

Purpose:

```txt
Control how long files remain active before archive/review/delete.
```

Default recommended policy:

```txt
Receipts: 5 years
Income documents: 5 years
Expense documents: 5 years
Invoices: 5 years
Audit reports: 7 years
Student documents: Active status + 5 years, review only
Temporary uploads: 30 days
Duplicate/rejected files: 90 days
System logs: 3 years
```

Allowed retention options:

```txt
30 days
90 days
1 year
3 years
5 years
7 years
Custom
Never auto-delete
```

File lifecycle:

```txt
Active
Archived
Marked for Review
Approved for Deletion
Deleted
Legal Hold
Permanent Record
```

Important deletion rules:

```txt
Do not delete files linked to open approvals
Do not delete files linked to active audit period
Do not delete files under legal hold
Do not delete student documents without Super User approval
Do not delete financial receipts without export/backup first
Do not physically delete approved financial records without audit log
```

---

# 29. Archive & Backup to Google Drive

Purpose:

```txt
Move/copy older files from Supabase Storage to Google Drive archive before cleanup.
```

Architecture:

```txt
Supabase Storage = active app files
Google Drive = long-term archive copy
Supabase Database = permanent metadata and audit trail
```

File lifecycle:

```txt
Active File
Archive Eligible
Archive Review
Export to Google Drive
Archive Verified
Supabase Cleanup Pending Approval
Supabase File Deleted
Audit Log Created
```

Do not delete from Supabase unless:

```txt
Google Drive archive copy exists
Google Drive file ID is saved in Supabase
Archive verification passed
Archive index was generated
Super User approved cleanup
File is not under legal hold
Linked transaction is not under open audit
Audit log entry was created
```

Google Drive folder structure:

```txt
Udhaya-App-Archive/
│
├── 2026/
│   ├── Receipts/
│   │   ├── Income/
│   │   ├── Expenses/
│   │   ├── Daily/
│   │   ├── Admin/
│   │   ├── Boys-Building/
│   │   └── Girls-Building/
│   ├── Invoices/
│   ├── Student-Documents/
│   ├── Audit-Reports/
│   └── Monthly-Exports/
│
├── 2027/
├── 2028/
└── Archive-Index/
```

Archive statuses:

```txt
Active
Eligible for Archive
Archive Pending
Archived to Google Drive
Archive Verified
Cleanup Pending Approval
Supabase File Deleted
Legal Hold
Archive Failed
```

Archive settings fields:

```txt
Archive destination: Google Drive
Google Drive root folder ID
Archive by year yes/no
Archive by module yes/no
Archive file naming rule
Generate archive index yes/no
Require verification before cleanup yes/no
Require Super User approval before Supabase deletion yes/no
Keep metadata in Supabase permanently yes/no
```

---

# 30. File Naming Convention

Receipt:

```txt
UDH_EXP_2026_000123_Food_Grocery_4500INR_2026-06-26.pdf
```

Income document:

```txt
UDH_INC_2026_000045_Donation_500USD_2026-06-26.pdf
```

Student document:

```txt
UDH_STU_2026_001_BirthCertificate_2026-06-26.pdf
```

Invoice:

```txt
UDH_INV_2026_000078_DonationReceipt_JohnD_500USD.pdf
```

---

# 31. Storage Cleanup & Archive Review Page

Add page under Audit & Control:

```txt
Storage Cleanup & Archive Review
```

Cards:

```txt
Supabase Storage Used
Files Eligible for Archive
Files Already Archived
Files Pending Verification
Estimated Supabase Space Savings
Legal Hold Files
```

Filters:

```txt
Year
File Type
Module
Status
Retention Expiry Date
Linked Record
File Size
```

Table columns:

```txt
File Name
Module
Linked Record
Size
Uploaded Date
Retention Expiry
Archive Status
Action
```

Actions:

```txt
View File
View Linked Record
Archive to Google Drive
Verify Archive
Export Index
Request Cleanup Approval
Place Legal Hold
```

---

# 32. Website Sharing Layer

Later phase.

Purpose:

```txt
Share only approved safe data from app to public Udhaya website.
```

Shareable examples:

```txt
General donation summary
Approved public reports
Non-sensitive mission content
Approved student story without private details
Program impact numbers
```

Never share:

```txt
Full student profiles
Child health notes
Guardian details
Receipts
Financial internal notes
Donor private details
Approval workflow
Audit logs
```

Website sharing fields:

```txt
Approved for website yes/no
Approved by
Approval date
Public title
Public summary
Public image
Private data removed yes/no
```

---

# 33. Suggested Database Tables

First-cut tables:

```txt
users
roles
user_roles
settings
currencies
exchange_rates
students
children_profiles
student_documents
income_transactions
expense_transactions
expense_categories
income_categories
receipts
documents
approvals
approval_comments
invoices
donors
sponsors
vendors
buildings
payment_methods
bank_accounts
budgets
opening_balances
adjustment_entries
audit_logs
notifications
report_exports
retention_policies
archive_jobs
archive_files
website_share_items
```

---

# 34. Key Table Fields

## users

```txt
user_id
full_name
email
role
status
last_login
created_at
updated_at
```

## students

```txt
student_id
badge_number
full_name
preferred_name
gender
date_of_birth
admission_date
status
school_name
grade
building_id
sponsor_id
photo_path
created_by
created_at
updated_by
updated_at
```

## income_transactions

```txt
income_id
income_date
donor_id
income_type
original_amount
original_currency
exchange_rate
base_currency
base_amount
payment_method
reference_number
purpose
restricted_flag
student_id
building_id
approval_status
receipt_status
created_by
approved_by
created_at
updated_at
```

## expense_transactions

```txt
expense_id
expense_date
expense_type
category_id
subcategory
vendor_id
description
original_amount
original_currency
exchange_rate
base_currency
base_amount
payment_method
paid_by
building_id
student_id
approval_status
receipt_status
created_by
approved_by
created_at
updated_at
```

## documents / receipts

```txt
file_id
file_name
file_type
file_category
linked_record_type
linked_record_id
storage_provider
storage_path
file_size_original
file_size_compressed
uploaded_by
uploaded_at
retention_policy_id
retention_start_date
retention_expiry_date
file_status
archive_status
google_drive_file_id
google_drive_link
archived_at
archived_by
deletion_eligible_date
deletion_approved_by
deletion_approved_at
deleted_at
delete_reason
legal_hold_flag
permanent_record_flag
audit_note
```

## retention_policies

```txt
retention_policy_id
policy_name
file_category
retention_period_value
retention_period_unit
action_after_retention
requires_admin_review
requires_superuser_approval
requires_export_before_delete
auto_delete_allowed
active_status
created_by
created_at
updated_by
updated_at
```

## audit_logs

```txt
audit_id
user_id
action
module
record_id
old_value
new_value
reason
timestamp
device_info
ip_address
```

---

# 35. UI Component List

Claude should create reusable components:

```txt
AppLayout
TopHeader
Sidebar
MobileBottomNav
DashboardCard
StatCard
DataTable
FilterBar
FormSection
CurrencyInput
ReceiptUploader
StatusBadge
ApprovalStatusBadge
RoleBadge
SettingsPanel
Modal
ConfirmDialog
StudentProfileCard
ReportFilterPanel
ReceiptPreview
InvoicePreview
AuditTimeline
ArchiveStatusBadge
StorageSummaryCard
```

---

# 36. Development Phases

## Phase 0: Project Setup

Build:

```txt
React app
Folder structure
Routing
Theme
Sample data
Vercel-ready build
GitHub repo
```

Deliverable:

```txt
App runs locally and can deploy to Vercel.
```

---

## Phase 1: UI Foundation

Build:

```txt
Login screen
App shell
Sidebar
Mobile navigation
Admin/User mode
Dashboard
Placeholder pages
Settings layout
Reusable cards/tables/forms
```

Deliverable:

```txt
Clickable UI prototype using sample data.
```

---

## Phase 2: Settings Module

Build detailed settings UI for:

```txt
Currency
Categories
Approval rules
Payment methods
Buildings
Student settings
Receipt upload rules
Retention policies
Archive settings
```

Deliverable:

```txt
Settings center ready with sample data.
```

---

## Phase 3: Student Module

Build:

```txt
Student registration
Badge generator
Student list
Student profile page
Student documents placeholder
Student reports placeholder
```

Deliverable:

```txt
Full student UI lifecycle with sample data.
```

---

## Phase 4: Income Tracker

Build:

```txt
Income form
Income list
Income detail
Currency calculation
Donor fields
Approval status
Receipt/document link
```

Deliverable:

```txt
Income entry flow ready with sample data.
```

---

## Phase 5: Expense Tracker

Build:

```txt
Daily expense form
Admin expense form
Boys building expense form
Girls building expense form
Expense list
Expense detail
Receipt requirement indicator
Currency calculation
```

Deliverable:

```txt
Expense entry flow ready with sample data.
```

---

## Phase 6: Receipt Upload & Compression

Build:

```txt
Mobile camera upload
Desktop file upload
PDF upload
Image compression
Receipt preview
Multiple receipts per transaction
Receipt status
Replacement with audit note
```

Deliverable:

```txt
Receipt upload UI and client-side compression ready.
```

---

## Phase 7: Approval Workflow

Build:

```txt
Approval queue
Approval detail page
Approve
Reject
Need clarification
Resubmit
Approval comments
Approval history
Status tracking
```

Deliverable:

```txt
Approval lifecycle using sample data.
```

---

## Phase 8: Reports

Build:

```txt
Weekly reports
Monthly reports
Yearly reports
Audit reports
Filters
Export buttons
Sample output tables
```

Deliverable:

```txt
Report UI ready.
```

---

## Phase 9: Balance Sheet

Build:

```txt
Opening balance
Income total
Expense total
Current balance
Cash/bank split
Restricted/unrestricted funds
Building-wise summary
Student sponsorship summary
```

Deliverable:

```txt
Balance sheet UI using sample data.
```

---

## Phase 10: Invoice Generation

Build:

```txt
Donation receipt
Voucher
Invoice list
Invoice preview
PDF placeholder
Invoice status
```

Deliverable:

```txt
Invoice/receipt generation UI ready.
```

---

## Phase 11: Audit Log

Build:

```txt
Audit log table
Filters
Audit timeline
Record change view
Export placeholder
```

Deliverable:

```txt
Audit log UI ready.
```

---

## Phase 12: Supabase Integration

Build:

```txt
Supabase project connection
Database tables
CRUD operations
Auth
Role-based access
Storage buckets
```

Deliverable:

```txt
Real data persistence.
```

---

## Phase 13: Supabase Storage

Build:

```txt
Upload receipts/documents to Supabase Storage
Secure file paths
File metadata in database
Receipt preview from storage
Download access by role
```

Deliverable:

```txt
Active file storage working.
```

---

## Phase 14: Archive & Backup

Build:

```txt
Retention rules
Eligible file detection
Archive review screen
Google Drive integration later
Archive status tracking
Archive index export
Cleanup approval
```

Deliverable:

```txt
Archive lifecycle ready.
```

---

## Phase 15: Production Security

Build:

```txt
Remove hardcoded admin password
Supabase Auth
Role-based views
RLS policies
Storage access rules
Audit logging
Session timeout
Secure environment variables
```

Deliverable:

```txt
Production-safe version.
```

---

## Phase 16: Website Sharing

Build:

```txt
Approved-for-website flag
Public-safe content review
Website data API or export
Public report publishing
```

Deliverable:

```txt
Controlled sharing from app to website.
```

---

# 37. Recommended Git Branches

```txt
main
dev
feature/ui-shell
feature/settings-module
feature/student-profile
feature/income-tracker
feature/expense-tracker
feature/receipt-upload
feature/approval-workflow
feature/reports
feature/balance-sheet
feature/invoice-generation
feature/audit-log
feature/supabase-integration
feature/storage
feature/archive-backup
feature/security-hardening
feature/website-sharing
```

---

# 38. Documentation Files to Maintain

```txt
UDHAYA_APP_FULL_SCOPE_v0.1.md
UDHAYA_DATABASE_SCHEMA_v0.1.md
UDHAYA_UI_SCREEN_MAP_v0.1.md
UDHAYA_APPROVAL_WORKFLOW_v0.1.md
UDHAYA_REPORTING_REQUIREMENTS_v0.1.md
UDHAYA_RETENTION_ARCHIVE_POLICY_v0.1.md
UDHAYA_SUPABASE_SECURITY_PLAN_v0.1.md
UDHAYA_CLAUDE_PROMPTS_v0.1.md
```

---

# 39. First Claude Prompt: Build UI Foundation

Use this first.

```txt
I am building a React-based web and mobile-compatible admin/financial app for Udhaya Children Home.

The app will manage children home operations, student profiles, income, expenses, receipts, approvals, reports, balance sheet, invoices, audit logs, file retention, and archive management.

Technology:
- React
- HTML
- CSS
- JavaScript
- Later Supabase for auth, database, and active file storage
- Later Google Drive for archive backup
- Hosted later on Vercel

For now, build only the frontend prototype using sample data. Do not connect to a database yet.

Design style:
- Beautiful, clean, warm nonprofit style
- Professional financial admin dashboard
- Mobile responsive
- Card-based layout
- Soft cream/white background
- Deep green or blue primary color
- Gold/saffron accent
- Rounded cards
- Clear audit-friendly tables
- Large mobile-friendly buttons

Build these screens:

1. Login Screen
- Udhaya logo placeholder
- Title: Udhaya Children Home Admin Portal
- Subtitle: Secure Financial & Student Management System
- Username field
- Password field
- Login button
- Mission quote at bottom

2. App Shell
- Desktop sidebar
- Mobile bottom navigation
- Top header
- Role badge
- Logout button
- Main content area

3. Admin/User Mode
- Default login opens User Mode
- Ctrl + Shift + A opens admin password modal
- Temporary password: admin2026
- If correct, switch to Admin Mode
- Show visible Admin Mode badge
- Add note in code that this is prototype only and must be replaced by secure auth later

4. Admin Sidebar Menu
- Dashboard
- Student Registration
- Children Details
- Student Profiles
- Income Tracker
- Daily Expenses
- Administration Expenses
- Boys Building Expenses
- Girls Building Expenses
- Approvals
- Receipts
- Invoices
- Reports
- Balance Sheet
- Audit Log
- Storage Cleanup & Archive Review
- Settings

5. User Sidebar Menu
- Dashboard
- Submit Expense
- Upload Receipt
- My Submissions
- Student View

6. Dashboard
Create stat cards:
- Total Income This Month
- Total Expenses This Month
- Current Balance
- Pending Approvals
- Receipts Missing
- Student Count
- Boys Building Expense
- Girls Building Expense
- Admin Expenses
- Storage Used
- Files Eligible for Archive

Add sections:
- Recent Transactions table
- Approval Queue table
- Monthly Summary placeholder chart area
- Storage summary card

7. Settings Page
Create a settings layout with left settings menu and right detail area.

Settings sections:
- User & Role Settings
- Currency Settings
- Expense Category Settings
- Income Category Settings
- Approval Workflow Settings
- Receipt Upload Settings
- Email Notification Settings
- Invoice Settings
- Student Profile Settings
- Audit & Export Settings
- Security Settings
- Website Sharing Settings
- File Retention & Archiving Settings
- Archive & Backup Settings

8. Placeholder Pages
For every menu item, create a placeholder page with:
- Page title
- Short description
- Sample card/table/form layout

9. Reusable Components
Create:
- AppLayout
- TopHeader
- Sidebar
- MobileBottomNav
- DashboardCard
- DataTable
- StatusBadge
- RoleBadge
- Modal
- SettingsPanel
- PlaceholderPage
- StorageSummaryCard
- ArchiveStatusBadge

10. Responsive Requirements
- Desktop: sidebar + main content
- Tablet: collapsible sidebar
- Mobile: bottom navigation and stacked cards
- Forms should be single-column on mobile

Output:
- Complete React project code
- File structure
- CSS files
- How to run locally
- Keep code clean and modular

Important:
Do not build database yet.
Do not build Supabase yet.
Do not build real Google Drive integration yet.
Do not build real deletion logic yet.
This first session is only the UI foundation.
```

---

# 40. Second Claude Prompt: Build Settings Module

Use after the UI foundation works.

```txt
Continue the Udhaya Children Home Admin Portal React app.

Build the Settings module in detail.

Do not connect to Supabase yet. Use local React state and sample data.

The Settings page should have these configurable sections:

1. Currency Settings
- Currency code
- Currency name
- Symbol
- Active/inactive
- Default exchange rate to base currency
- Base currency selector
- Last updated date

2. Expense Category Settings
- Category name
- Subcategory
- Applies to Daily/Admin/Boys Building/Girls Building
- Receipt required yes/no
- Approval required yes/no
- Active/inactive

3. Income Category Settings
- Donation
- Monthly Sponsorship
- One-time Sponsorship
- Grant
- Church Contribution
- Event Collection
- Bank Interest
- Refund
- Other

4. Approval Workflow Settings
- Amount threshold
- Required approver role
- Receipt required rule
- Foreign currency review rule
- Clarification allowed yes/no
- Final lock after approval yes/no

5. Payment Method Settings
- Cash
- Bank Transfer
- Check
- Card
- Online Payment
- Digital Wallet
- Other

6. Building Settings
- Boys Building
- Girls Building
- Admin Office
- Common Area

7. Student Profile Settings
- Student status
- Gender
- Grade/class
- Document type
- Sponsorship status

8. Receipt Upload Settings
- Max file size
- Allowed file types
- Image compression quality
- Required receipt categories

9. File Retention & Archiving Settings
- File category
- Retention period
- Retention unit: days, months, years
- Action after retention: archive, mark for review, delete, never delete
- Require admin approval before delete
- Require super user approval before delete
- Require export before delete
- Legal hold option
- Permanent record option
- Active/inactive policy status

Sample retention policies:
- Receipts: 5 years, archive, admin approval required
- Income documents: 5 years, archive, admin approval required
- Expense documents: 5 years, archive, admin approval required
- Invoices: 5 years, archive, admin approval required
- Audit reports: 7 years, never delete
- Student documents: active status + 5 years, review only
- Temporary uploads: 30 days, delete
- Duplicate/rejected files: 90 days, review

10. Archive & Backup Settings
- Archive destination: Google Drive
- Google Drive root folder ID
- Archive by year yes/no
- Archive by module yes/no
- Require archive verification before cleanup yes/no
- Require Super User approval before Supabase deletion yes/no
- Generate archive index yes/no
- Keep metadata permanently yes/no

Build:
- Tabs or section cards
- Add/edit/delete UI for each configuration
- Modal forms or inline forms
- Sample data
- Clean validation messages
- Responsive design
- Reusable configuration table component

Important:
Do not implement real deletion.
Do not implement real Google Drive API.
Do not implement backend.
This is UI and sample data only.
```

---

# 41. Third Claude Prompt: Build Student Module

```txt
Continue the Udhaya Children Home Admin Portal.

Build the Student Registration, Children Details, and Student Profile modules using React and sample data only.

Create:

1. Student Registration Form
Fields:
- Student ID
- Auto-generated badge number
- Full name
- Preferred name
- Gender
- Date of birth
- Age
- Photo upload placeholder
- Admission date
- Current status
- Class/grade
- School name
- Academic year
- Health notes
- Education notes
- Guardian name
- Guardian relationship
- Guardian contact
- Sponsor linked yes/no
- Sponsor name
- Building
- Room/dorm
- Documents uploaded

Badge format:
UDH-STU-2026-001

2. Student List
- Search
- Filter by status, gender, building, grade, sponsor status
- Table/grid view
- Click student to open profile

3. Student Profile Page
Sections/tabs:
- Basic Info
- Education
- Health
- Sponsorship
- Expenses
- Documents
- Notes
- Audit

4. Children Details Page
Track:
- Dorm/building allocation
- Daily needs
- Medical notes
- Education progress
- Sponsor mapping
- Document tracking

Use reusable components and sample data.
Make mobile layout clean and easy.
Do not connect to database yet.
```

---

# 42. Fourth Claude Prompt: Build Income & Expense Modules

```txt
Continue the Udhaya Children Home Admin Portal.

Build Income Tracker and Expense Tracker modules using sample data only.

Income Tracker:
Fields:
- Income ID
- Date received
- Donor name
- Donor type
- Country
- Income type
- Original amount
- Original currency
- Exchange rate
- Base currency
- Base amount auto-calculated
- Payment method
- Bank account
- Reference number
- Purpose
- Restricted/unrestricted fund
- Related student
- Related building
- Attachment placeholder
- Approval status
- Entered by
- Approved by

Income types:
- Donation
- Monthly Sponsorship
- One-time Sponsorship
- Grant
- Church Contribution
- Event Collection
- Bank Interest
- Refund
- Other Income

Expense Modules:
- Daily Expenses
- Administration Expenses
- Boys Building Expenses
- Girls Building Expenses

Expense fields:
- Expense ID
- Expense date
- Expense type
- Category
- Subcategory
- Vendor name
- Description
- Original amount
- Original currency
- Exchange rate
- Base currency
- Base amount auto-calculated
- Payment method
- Paid by
- Building allocation
- Student allocation if any
- Receipt uploaded yes/no
- Receipt status
- Approval status
- Clarification required yes/no
- Clarification comments

Build:
- Add Income form
- Income list
- Income detail page
- Add Expense form
- Expense list
- Expense detail page
- Filters
- Currency formatting for USD, INR, NZD
- Sample transactions

Do not connect to database yet.
```

---

# 43. Fifth Claude Prompt: Build Receipt Upload UI

```txt
Continue the Udhaya Children Home Admin Portal.

Build the Receipt and Document Management UI using React and sample data only.

Requirements:
- Upload receipt from mobile camera
- Upload receipt from desktop
- Upload PDF bill
- Image compression placeholder
- Receipt preview panel
- Link receipt to transaction
- Mark receipt as missing
- Mark receipt as unreadable
- Replace receipt with audit reason
- Multiple receipts per transaction

Use this mobile camera input:
<input type="file" accept="image/*" capture="environment" />

Receipt statuses:
- Uploaded
- Missing
- Unreadable
- Rejected
- Re-upload Required
- Approved
- Archived

Build:
- Receipt Center page
- Receipt upload component
- Receipt preview component
- Receipt list table
- Receipt status badges
- Replacement modal
- Missing receipt report placeholder

Compression rule display:
- Resize max width to 1200px or 1600px
- Compress quality 60–75%
- Target file size 300 KB to 700 KB
- Keep readable quality

Do not upload to Supabase yet.
Do not store real files yet.
Use sample data and local preview only.
```

---

# 44. Sixth Claude Prompt: Build Approval Workflow

```txt
Continue the Udhaya Children Home Admin Portal.

Build the Approval Workflow module using React and sample data only.

Workflow statuses:
- Draft
- Submitted
- Pending Review
- Clarification Required
- Resubmitted
- Approved
- Rejected
- Posted to Reports
- Locked for Audit

Build:
1. Approval Queue
- Pending approvals table
- Filters by type, date, amount, status, submitted by, building

2. Approval Detail Screen
- Transaction details
- Receipt preview
- Approval history
- Comments
- Action buttons

Actions:
- Approve
- Need Clarification
- Reject

3. Clarification Loop
- Approver enters clarification question
- Submitter response section
- Resubmit button
- Status changes to Resubmitted

4. Approval History Timeline
Show:
- Submitted by
- Reviewed by
- Comments
- Decision
- Date/time

Important:
Only approved and posted transactions should appear in final reports later.
Do not connect to backend yet.
Use sample data only.
```

---

# 45. Seventh Claude Prompt: Build Reports, Balance Sheet & Invoices

```txt
Continue the Udhaya Children Home Admin Portal.

Build Reports, Balance Sheet, and Invoice modules using React and sample data only.

Reports:
- Weekly income summary
- Weekly expense summary
- Monthly income vs expense
- Monthly category-wise expense
- Monthly donor contribution
- Monthly student sponsorship
- Boys building expense report
- Girls building expense report
- Admin expense report
- Receipt missing report
- Currency conversion report
- Approval aging report
- Audit packet placeholder

Report filters:
- Date range
- Financial year
- Currency
- Base currency
- Donor
- Vendor
- Category
- Building
- Student
- Payment method
- Approval status
- Receipt status
- Fund type

Export buttons:
- PDF
- Excel
- CSV

Balance Sheet:
Show:
- Opening Balance
- Total Income
- Total Expenses
- Current Balance
- Cash in Hand
- Bank Balance
- Restricted Funds
- Unrestricted Funds
- Building-specific balances
- Student sponsorship balances

Important:
Only approved and posted transactions should count in official report totals.

Invoices:
Build:
- Invoice list
- Donation receipt preview
- Voucher preview
- Invoice number generator placeholder

Invoice number formats:
- UDH-INV-2026-0001
- UDH-DON-2026-0001
- UDH-VCH-2026-0001

Invoice statuses:
- Draft
- Generated
- Sent
- Paid
- Cancelled
- Archived

Use sample data only.
Do not generate real PDFs yet.
```

---

# 46. Eighth Claude Prompt: Build Archive & Cleanup UI

```txt
Continue the Udhaya Children Home Admin Portal.

Build the Storage Cleanup & Archive Review page using React and sample data only.

Purpose:
Older files in Supabase Storage should be archived to Google Drive before Supabase cleanup.

File lifecycle:
Active → Eligible for Archive → Archive Pending → Archived to Google Drive → Archive Verified → Cleanup Pending Approval → Supabase File Deleted

Archive statuses:
- Active
- Eligible for Archive
- Archive Pending
- Archived to Google Drive
- Archive Verified
- Cleanup Pending Approval
- Supabase File Deleted
- Legal Hold
- Archive Failed

Build:
1. Storage Summary Cards
- Supabase Storage Used
- Files Eligible for Archive
- Files Already Archived
- Files Pending Verification
- Estimated Supabase Space Savings
- Legal Hold Files

2. Filters
- Year
- File Type
- Module
- Status
- Retention Expiry Date
- Linked Record
- File Size

3. Eligible Files Table
Columns:
- File Name
- Module
- Linked Record
- Size
- Uploaded Date
- Retention Expiry
- Archive Status
- Action

4. Actions
- View File
- View Linked Record
- Archive to Google Drive
- Verify Archive
- Export Index
- Request Cleanup Approval
- Place Legal Hold

5. Safety Rules Display
Show that Supabase file cannot be deleted unless:
- Google Drive archive copy exists
- Google Drive file ID is saved
- Archive verification passed
- Archive index was generated
- Super User approved cleanup
- File is not under legal hold
- Linked transaction is not under open audit
- Audit log entry was created

Important:
Do not implement real Google Drive API yet.
Do not implement physical deletion.
This is UI and sample data only.
```

---

# 47. Ninth Claude Prompt: Supabase Integration

Use this only after UI is approved.

```txt
Now integrate Supabase into the Udhaya Children Home Admin Portal.

Use Supabase for:
- Auth
- Database
- Active file storage

Create database tables for:
- users
- roles
- user_roles
- settings
- currencies
- exchange_rates
- students
- children_profiles
- student_documents
- income_transactions
- expense_transactions
- expense_categories
- income_categories
- receipts
- documents
- approvals
- approval_comments
- invoices
- donors
- sponsors
- vendors
- buildings
- payment_methods
- bank_accounts
- budgets
- opening_balances
- adjustment_entries
- audit_logs
- notifications
- report_exports
- retention_policies
- archive_jobs
- archive_files
- website_share_items

Implement:
- Supabase client setup using environment variables
- Auth login/logout
- Role-based access
- CRUD for students
- CRUD for income
- CRUD for expenses
- CRUD for receipts metadata
- CRUD for settings
- Audit log inserts for create/update/delete-sensitive actions
- Storage bucket setup for active receipts/documents

Security:
- Do not hardcode Supabase keys except public anon key through env variable
- Remove prototype admin2026 shortcut from production mode
- Prepare for Row Level Security
- Do not expose private files publicly
```

---

# 48. Immediate Build Recommendation

Start exactly in this order:

```txt
1. UI foundation
2. Settings module
3. Student module
4. Income/expense modules
5. Receipt upload UI
6. Approval workflow
7. Reports/balance sheet/invoices
8. Archive cleanup UI
9. Supabase database
10. Supabase storage
11. Supabase Auth and security
12. Google Drive archive integration
13. Website sharing layer
```

Do not start with database first. First get the UI flow clean.

---

# 49. Final First-Cut Scope Summary

The Udhaya app should become:

```txt
A secure financial admin portal
A student profile system
A receipt/document management system
An approval workflow tool
An audit reporting system
A balance sheet generator
An invoice/donation receipt system
A file retention and archive manager
A controlled data source for the public website
```

The safest long-term setup:

```txt
Vercel = React frontend hosting
Supabase Auth = login and roles
Supabase Database = structured records
Supabase Storage = active receipts/documents
Google Drive = archive/backup copy
```

The first Claude build should only create the **frontend UI prototype**.
After you approve the UI, then move to Supabase and real storage.
