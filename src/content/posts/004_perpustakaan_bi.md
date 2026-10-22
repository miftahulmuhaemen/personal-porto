---
title: 'Bank Indonesia Regional Library Management System'
pubDate: '2020-03-01'
techStack: ['PHP', 'CodeIgniter 3', 'MySQL', 'Bootstrap 4', 'DataTables']
category: 'product'
---

- [x] Contract Delivery for Bank Indonesia Regional Office (Banjarmasin)
- [x] Institutional On-Premises Server Decommissioned

## Overview

The Bank Indonesia Regional Office in Banjarmasin maintains a specialized public and staff reference library. Prior to digitization, circulation workflows, book inventories, and loan returns were recorded in paper logs or manual spreadsheets, making inventory audits and overdue tracking inefficient.

This web application provided a centralized library information and circulation management system. It enabled public visitors to browse and search available collections while providing librarians with automated borrowing lifecycle tracking and inventory management.

## Architecture and Technical Implementation

### 1. MVC Application Architecture

Developed with CodeIgniter 3 following the classic Model-View-Controller (MVC) pattern:

- **Modular Separation**: Controller endpoints (`Admin.php`, `User.php`, `Welcome.php`) isolate public catalog routes from restricted administrative actions.
- **Relational Data Modeling**: MySQL schema design implemented via Active Record models (`M_buku.php`, `M_user.php`, `M_pages.php`), establishing foreign key constraints across book entities, categories, membership tiers, and circulation transaction tables.
- **Client Interface**: Responsive UI utilizing Bootstrap 4 paired with DataTables for client-side sorting, pagination, and multi-attribute catalog search.

### 2. Core Functional Modules

- **Public Book Catalog & Classification**: Searchable inventory categorized by subject (economics, central banking, monetary policy, jurisprudence), showing real-time rack location and availability status.
- **Circulation Lifecycle Tracking**: Automated logging of loan transactions, scheduled return deadlines, and overdue calculation.
- **Librarian Administrative Suite**: Back-office dashboard for registering new acquisitions, assigning ISBNs and physical rack numbers, and auditing member loan histories.

## Repository

::github{repo="miftahulmuhaemen/Web-Perpustakaan-BI"}
