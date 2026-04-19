# SAP ERP Implementation Project Report

## Fictitious Company Blueprint and Customization Guide

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Company Profile](#company-profile)
3. [Organizational Structure](#organizational-structure)
4. [Functional Areas Implementation](#functional-areas-implementation)
   - [Financial Accounting (FI)](#financial-accounting-fi)
   - [Materials Management (MM)](#materials-management-mm)
   - [Sales and Distribution (SD)](#sales-and-distribution-sd)
5. [Customization Steps](#customization-steps)
6. [Configuration Details](#configuration-details)
7. [Test Scenarios](#test-scenarios)
8. [Conclusion](#conclusion)

---

## 1. Project Overview

This project document outlines the complete implementation blueprint for deploying SAP ERP within a fictitious manufacturing company. The document covers the organizational structure, functional area configurations, and step-by-step customization procedures for FI (Financial Accounting), MM (Materials Management), and SD (Sales and Distribution) modules.

**Project Objective:** To establish a fully functional SAP ERP system with all major sub-organizations properly configured to support business operations across finance, procurement, and sales domains.

**Scope:**
- Company Code configuration
- Chart of Accounts setup
- Credit Management
- Asset Accounting
- Material Master setup
- Purchasing Organization structure
- Sales Organization setup
- Distribution Channel configuration

---

## 2. Company Profile

### Company Information

| Field | Details |
|-------|---------|
| Company Name | **Apex Manufacturing Solutions Ltd.** |
| Industry | Engineering & Manufacturing |
| Headquarter | Mumbai, Maharashtra, India |
| Regional Offices | Delhi, Bangalore, Chennai, Kolkata |
| Annual Revenue | ₹500 Crores (INR) |
| Employee Count | 2,500+ |
| Fiscal Year | April 1 - March 31 |

### Business Overview

Apex Manufacturing Solutions Ltd. is a mid-sized engineering and manufacturing company specializing in industrial machinery components, automotive parts, and custom-engineered solutions. The company operates multiple production facilities across India and exports to Southeast Asian markets.

**Key Business Processes:**
- Procurement of raw materials and components
- Production planning and manufacturing
- Quality assurance and testing
- Storage and warehouse management
- Domestic and international sales
- Financial accounting and reporting

---

## 3. Organizational Structure

### Enterprise Structure Hierarchy

```
Apex Manufacturing Solutions Ltd. (Client 100)
├── Corporate Level
│   └── Group Management
├── Finance Domain (FI)
│   ├── Finance & Accounting
│   ├── Treasury Management
│   ├── Controlling
│   └── Asset Management
├── Procurement Domain (MM)
│   ├── Central Purchasing
│   ├── Strategic Sourcing
│   ├── Inventory Management
│   └── Warehouse Operations
└── Sales Domain (SD)
    ├── Domestic Sales
    ├── Export Sales
    ├── Customer Service
    └── Distribution & Logistics
```

### Organizational Units Configuration

| Organizational Level | ID | Description |
|---------------------|-----|-------------|
| Client | 100 | Apex Manufacturing Solutions Ltd. |
| Company Code | 1000 | Apex Manufacturing HQ |
| Company Code | 1001 | Apex Manufacturing Delhi Unit |
| Company Code | 1002 | Apex Manufacturing Bangalore Unit |
| Company Code | 1003 | Apex Manufacturing Chennai Unit |
| Company Code | 1004 | Apex Manufacturing Kolkata Unit |
| Credit Control Area | CCA1 | Apex Credit Control |
| Business Area | BA01 | Mumbai Operations |
| Business Area | BA02 | Delhi Operations |
| Business Area | BA03 | Bangalore Operations |
| Business Area | BA04 | Chennai Operations |
| Business Area | BA05 | Kolkata Operations |
| Sales Organization | SO01 | Domestic Sales Org |
| Sales Organization | SO02 | Export Sales Org |
| Distribution Channel | DC01 | Wholesale |
| Distribution Channel | DC02 | Retail |
| Distribution Channel | DC03 | Direct Sales |
| Plant | PL01 | Mumbai Plant |
| Plant | PL02 | Delhi Plant |
| Plant | PL03 | Bangalore Plant |
| Plant | PL04 | Chennai Plant |
| Plant | PL05 | Kolkata Plant |
| Purchasing Organization | PO01 | Central Purchasing |
| Purchasing Organization | PO02 | Regional Purchasing |

---

## 4. Functional Areas Implementation

### 4.1 Financial Accounting (FI)

#### Overview

The Financial Accounting (FI) module forms the core of the accounting system, providing integrated financial transactions across all business processes.

#### Sub-Organizations in FI

| Sub-Organization | Component | Purpose |
|-----------------|-----------|---------|
| General Ledger Accounting | FI-GL | Core GL posting and reporting |
| Accounts Payable | FI-AP | Vendor invoice processing |
| Accounts Receivable | FI-AR | Customer invoice processing |
| Asset Accounting | FI-AA | Fixed asset management |
| Bank Accounting | FI-BK | Cash and bank management |
| Travel Expense Management | FI-TV | Employee travel claims |

#### FI Configuration Settings

**Company Code: 1000 (Apex Mumbai)**

| Parameter | Value |
|-----------|-------|
| Name | Apex Manufacturing HQ |
| City | Mumbai |
| Country | India (IN) |
| Currency | INR |
| Language | English |
| Fiscal Year Variant | 4C (April - March) |
| Periods | 12 |
| Posting Period | Open |
| Chart of Accounts | CA-IN (Indian Chart) |
| Credit Control Area | CCA1 |
| Bank Secret | ********* |

**Chart of Accounts: CA-IN**

| Account Group | Field | Configuration |
|--------------|-------|---------------|
| Primary Accounts | 10xx - 19xx | Balance Sheet Accounts |
| Income Accounts | 30xx - 39xx | P&L - Revenue |
| Expense Accounts | 40xx - 49xx | P&L - Direct Costs |
| Cost Accounts | 50xx - 59xx | P&L - Indirect Costs |

#### FI Customization Steps

1. **Define Company Code**
   - Transaction: OX02
   - Configure company code details
   - Set fiscal year variant
   - Define posting periods

2. **Define Credit Control Area**
   - Transaction: VKOA
   - Create credit control area
   - Assign company codes
   - Set credit limits

3. **Define Business Area**
   - Transaction: OBR6
   - Create business areas for each plant
   - Assign to company code

4. **Maintain Chart of Accounts**
   - Transaction: OB13
   - Create account groups
   - Define field status groups

5. **Maintain Field Status Variant**
   - Transaction: OBC4
   - Define posting keys
   - Configure required fields

6. **Define Tax Configuration**
   - Transaction: FTXP
   - Configure GST rates
   - Set tax codes for intra/inter-state

---

### 4.2 Materials Management (MM)

#### Overview

The Materials Management (MM) module handles all procurement and material-related activities, from purchasing to inventory management.

#### Sub-Organizations in MM

| Sub-Organization | Component | Purpose |
|-----------------|-----------|---------|
| Purchasing | MM-PR | Purchase requisitions |
| Purchasing Info Records | MM-PIR | Vendor material data |
| Vendor Master | MM-VM | Vendor management |
| Material Master | MM-MM | Material data management |
| Inventory Management | MM-IM | Stock management |
| Warehouse Management | MM-WM | Physical warehouse ops |
| Quality Management | MM-QM | Incoming inspection |
| Procurement | MM-PC | Contract management |

#### MM Configuration Settings

**Plant: PL01 (Mumbai Plant)**

| Parameter | Value |
|-----------|-------|
| Name | Mumbai Manufacturing Plant |
| City | Mumbai |
| Region | Maharashtra |
| Country | India |
| Language | English |
| Currency | INR |
| Time Zone | IST (UTC+5:30) |

**Purchasing Organization: PO01 (Central Purchasing)**

| Parameter | Value |
|-----------|-------|
| Name | Central Purchasing Org |
| City | Mumbai |
| Country | India |
| Currency | INR |

#### Store Locations

| Store Location | Plant | Description |
|---------------|-------|-------------|
| SL01 | PL01 | Raw Material Store |
| SL02 | PL01 | Finished Goods Store |
| SL03 | PL01 | Spare Parts Store |
| SL04 | PL02 | Raw Material Store |
| SL05 | PL02 | Finished Goods Store |
| SL06 | PL03 | Raw Material Store |
| SL07 | PL03 | Finished Goods Store |
| SL08 | PL04 | Raw Material Store |
| SL09 | PL04 | Finished Goods Store |
| SL10 | PL05 | Raw Material Store |
| SL11 | PL05 | Finished Goods Store |

#### MM Customization Steps

1. **Define Plant**
   - Transaction: OX10
   - Create plants for each location
   - Configure address details

2. **Define Storage Location**
   - Transaction: OX09
   - Create storage locations per plant
   - Define for raw materials, finished goods

3. **Define Purchasing Organization**
   - Transaction: OX09
   - Create purchasing organizations
   - Assign to company code

4. **Assign Organization Units**
   - Transaction: OX18
   - Link plant to company code
   - Link purchasing org to company code
   - Assign purchasing org to plant

5. **Define Material Types**
   - Transaction: OMS2
   - Configure material types
   - Set valuation and inventory management

6. **Define Movement Types**
   - Transaction: OMJJ
   - Configure goods movement types
   - Set auto GR/goods issue posting

7. **Configure Valuation Classes**
   - Transaction: OMW3
   - Define valuation classes
   - Link to material types

8. **Define MRP Groups**
   - Transaction: OMD6
   - Create MRP groups
   - Set parameters for MRP

9. **Configure Purchasing Info Records**
   - Transaction: ME11
   - Create info records
   - Define vendor master data

---

### 4.3 Sales and Distribution (SD)

#### Overview

The Sales and Distribution (SD) module handles all customer-facing activities from inquiry to invoicing and delivery.

#### Sub-Organizations in SD

| Sub-Organization | Component | Purpose |
|-----------------|-----------|---------|
| Sales Order Management | SD-SO | Order processing |
| Pricing & Conditions | SD-PC | Price determination |
| Billing & Invoicing | SD-BI | Invoice generation |
| Delivery Processing | SD-DL | Outbound delivery |
| Credit Management | SD-CM | Sales credit control |
| Partner Functions | SD-PF | Partner relationships |
| Text Determination | SD-TX | Sales texts |
| Output Determination | SD-OP | Output processing |

#### SD Configuration Settings

**Sales Organization: SO01 (Domestic Sales)**

| Parameter | Value |
|-----------|-------|
| Name | Domestic Sales Organization |
| City | Mumbai |
| Country | India |
| Currency | INR |
| Language | English |

**Sales Organization: SO02 (Export Sales)**

| Parameter | Value |
|-----------|-------|
| Name | Export Sales Organization |
| City | Mumbai |
| Country | India |
| Currency | USD, EUR |
| Language | English |

**Distribution Channels**

| Channel | Code | Description |
|---------|-----|-------------|
| Wholesale | DC01 | Wholesale customers |
| Retail | DC02 | Retail customers |
| Direct Sales | DC03 | Direct corporate sales |

#### Shipping Points

| Shipping Point | Plant | Description |
|----------------|-------|-------------|
| SP01 | PL01 | Mumbai Main Dock |
| SP02 | PL02 | Delhi Main Dock |
| SP03 | PL03 | Bangalore Main Dock |
| SP04 | PL04 | Chennai Main Dock |
| SP05 | PL05 | Kolkata Main Dock |

#### SD Customization Steps

1. **Define Sales Organization**
   - Transaction: OV10
   - Create sales organizations
   - Configure address details

2. **Define Distribution Channel**
   - Transaction: OV11
   - Create distribution channels

3. **Assign Sales Org to Company Code**
   - Transaction: OV14
   - Link sales org to company code

4. **Assign Distribution Channel to Sales Org**
   - Transaction: OV15
   - Link distribution channels

5. **Define Division**
   - Transaction: OV12
   - Create divisions for product lines

6. **Assign Sales Organization to Plant**
   - Transaction: OV16
   - Link sales org to plants

7. **Define Shipping Point**
   - Transaction: OV21
   - Create shipping points per plant

8. **Configure Credit Management**
   - Transaction: OVA8
   - Set credit limit procedures
   - Define credit groups

9. **Define Sales Document Types**
   - Transaction: OVA1
   - Configure OR (Standard Order)
   - Configure CR (Credit Memo Request)
   - Configure DR (Debit Memo Request)

10. **Define Item Categories**
    - Transaction: OVA2
    - Configure TAP (Standard Item)
    - Configure TANN (Free Goods)

11. **Define Schedule Line Categories**
    - Transaction: OVA3
    - Configure CN (Credit Memo)
    - Configure IP (Incomplete)

12. **Configure Pricing Procedure**
    - Transaction: V/06
    - Create condition tables
    - Define access sequences
    - Set pricing procedures

13. **Configure Output Determination**
    - Transaction: NACE
    - Define output types
    - Configure partner functions

14. **Define Copying Control**
    - Transaction: VOV2
    - Configure document copying

---

## 5. Customization Steps

### Phase 1: Enterprise Structure Setup

| Step | Transaction | Description | Status |
|------|-------------|-------------|--------|
| 1.1 | SCC4 | Create Client 100 | ✓ Complete |
| 1.2 | OX02 | Define Company Codes | ✓ Complete |
| 1.3 | OX10 | Define Plants | ✓ Complete |
| 1.4 | OX09 | Define Storage Locations | ✓ Complete |
| 1.5 | OV10 | Define Sales Organizations | ✓ Complete |
| 1.6 | OV11 | Define Distribution Channels | ✓ Complete |
| 1.7 | OV12 | Define Divisions | ✓ Complete |
| 1.8 | OX09 | Define Purchasing Orgs | ✓ Complete |

### Phase 2: FI Configuration

| Step | Transaction | Description | Status |
|------|-------------|-------------|--------|
| 2.1 | OB13 | Define Chart of Accounts | ✓ Complete |
| 2.2 | OB15 | Assign CoA to Company Code | ✓ Complete |
| 2.3 | OBC4 | Define Field Status Variants | ✓ Complete |
| 2.4 | OBC5 | Assign Field Status to CoCode | ✓ Complete |
| 2.5 | F110 | Define Posting Periods | ✓ Complete |
| 2.6 | OB8G | Define Tolerance Groups | ✓ Complete |
| 2.7 | OBB8G | Define Tax Codes (GST) | ✓ Complete |
| 2.8 | OA75 | Define Asset Classes | ✓ Complete |
| 2.9 | AW01N | Asset Configuration | ✓ Complete |

### Phase 3: MM Configuration

| Step | Transaction | Description | Status |
|------|-------------|-------------|--------|
| 3.1 | OMS2 | Define Material Types | ✓ Complete |
| 3.2 | OMSE | Assign Number Ranges | ✓ Complete |
| 3.3 | OMWD | Define Valuation Classes | ✓ Complete |
| 3.4 | OMW3 | Define Valuation Areas | ✓ Complete |
| 3.5 | OMW9 | Activate MRP | ✓ Complete |
| 3.6 | OMJJ | Define Movement Types | ✓ Complete |
| 3.7 | OME9 | Define Purchase Req Types | ✓ Complete |
| 3.8 | OME6 | Define PO Document Types | ✓ Complete |
| 3.9 | OME2 | Define Info Categories | ✓ Complete |

### Phase 4: SD Configuration

| Step | Transaction | Description | Status |
|------|-------------|-------------|--------|
| 4.1 | OVA1 | Define Sales Doc Types | ✓ Complete |
| 4.2 | OVA2 | Define Item Categories | ✓ Complete |
| 4.3 | OVA3 | Define Schedule Line Categories | ✓ Complete |
| 4.4 | V/06 | Define Pricing Procedures | ✓ Complete |
| 4.5 | V/08 | Create Condition Tables | ✓ Complete |
| 4.6 | V/09 | Define Access Sequences | ✓ Complete |
| 4.7 | V/04 | Define Condition Types | ✓ Complete |
| 4.8 | V/03 | Maintain Pricing Procedures | ✓ Complete |
| 4.9 | NACE | Output Determination | ✓ Complete |
| 4.10 | OV21 | Define Shipping Points | ✓ Complete |
| 4.11 | OVA8 | Credit Management Setup | ✓ Complete |

### Phase 5: Integration & Testing

| Step | Transaction | Description | Status |
|------|-------------|-------------|--------|
| 5.1 | SPRO | Configure Integration Points | ✓ Complete |
| 5.2 | MIGO | Test Goods Movement | ✓ Complete |
| 5.3 | VA01 | Test Sales Order | ✓ Complete |
| 5.4 | ME21N | Test Purchase Requisition | ✓ Complete |
| 5.5 | FB01 | Test GL Posting | ✓ Complete |
| 5.6 | F-02 | Test AP/AR Posting | ✓ Complete |
| 5.7 | MIRO | Test Invoice Verification | ✓ Complete |
| 5.8 | VF01 | Test Billing | ✓ Complete |

---

## 6. Configuration Details

### 6.1 Master Data Configuration

#### Material Master Views

| View | Description | Required Fields |
|------|-------------|----------------|
| Basic Data | Material description | Material, Description, Base Unit |
| Sales Org | Sales data | Sales Org, Distribution Channel |
| Purchasing | Purchasing data | Purchasing Org, Plant |
| Plant/Storage | Plant data | Plant, Storage Location |
| Accounting | Valuation data | Valuation Class, Moving Price |
| MRP | MRP parameters | MRP Type, Lot Size |
| Work Schedule | Production scheduling | Production Scheduler |

#### Vendor Master Configuration

| Segment | Field | Required |
|---------|-------|----------|
| General Data | Name, Search Term | Yes |
| Address | City, Country | Yes |
| Payment Terms | Payment Terms | Yes |
| Company Code | Reconciliation Account | Yes |
| Purchasing | PO Currency | Yes |
| Withholding Tax | Tax Categories | Yes |

#### Customer Master Configuration

| Segment | Field | Required |
|---------|-------|----------|
| General Data | Name, Search Term | Yes |
| Address | City, Country | Yes |
| Sales Area | Sales Org, Dist Channel | Yes |
| Company Code | Payment Terms | Yes |
| Credit Management | Credit Limit | Yes |
| Partner Functions | Sold-to, Ship-to | Yes |

### 6.2 Integration Configuration

#### FI-MM Integration

| Process | Configuration |
|---------|---------------|
| Material Valuation | Automatic G/L posting |
| Goods Movement | Real-time inventory update |
| Invoice Verification | Automatic PO matching |
| Automatic Payment | Vendor payment processing |

#### FI-SD Integration

| Process | Configuration |
|---------|---------------|
| Billing | Revenue recognition |
| Credit Management | Credit limit check |
| Customer Payment | Dunning procedure |
| Sales Analytics | Profit center assignment |

#### MM-SD Integration

| Process | Configuration |
|---------|---------------|
| Availability Check | ATP checking |
| Delivery Scheduling | Shipping point determination |
| Pricing | Customer-specific pricing |
| Customer Material | Material determination |

---

## 7. Test Scenarios

### Test Case 1: Purchase Requisition to PO

| Step | Description | Expected Result |
|------|-------------|-----------------|
| 1 | Create PR via ME51N | PR created with number |
| 2 | Convert PR to PO via ME57N | PO generated |
| 3 | Goods Receipt via MIGO | GR posted, inventory updated |
| 4 | Invoice Receipt via MIRO | Invoice parked/posted |

**Test Case 2: Sales Order to Billing**

| Step | Description | Expected Result |
|------|-------------|-----------------|
| 1 | Create Sales Order VA01 | Order created with number |
| 2 | Create Delivery VL01N | Delivery document created |
| 3 | Post Goods Issue VL02N | Quantity updated |
| 4 | Create Invoice VF01 | Invoice generated |
| 5 | Post Invoice VF02 | Revenue recognized in FI |

**Test Case 3: GL Posting**

| Step | Description | Expected Result |
|------|-------------|-----------------|
| 1 | Post manual journal FB01 | Document posted |
| 2 | Check balance in F.03 | GL balances updated |
| 3 | Run trial balance F.01 | Balance sheet report |

---

## 8. Conclusion

### Project Summary

This project successfully established a comprehensive SAP ERP blueprint for Apex Manufacturing Solutions Ltd. covering all three major functional areas:

- **Financial Accounting (FI):** Complete company code setup, chart of accounts configuration, GST tax handling, and asset accounting
- **Materials Management (MM):** Full plant and storage location setup, purchasing organization structure, and inventory management
- **Sales and Distribution (SD):** Sales organization configuration, distribution channels, pricing procedures, and delivery processing

### Key Deliverables

1. Complete organizational structure defined and configured
2. All master data templates prepared
3. Integration points configured between FI, MM, and SD
4. Test scenarios documented and executed
5. User procedures documented

### Recommendations

1. Regular master data reviews should be conducted quarterly
2. Integration testing should be performed after any configuration change
3. Credit limit reviews should be conducted monthly
4. Periodic inventory counts should be performed as per policy

---

## Document Information

| Field | Details |
|-------|---------|
| Project Title | SAP ERP Implementation - Company Blueprint |
| Course | SAP ERP Training Project |
| Submission Date | April 2026 |

---

**Made by:** Sourish Dey  
**Enrollment Number:** 23051223  
**Email:** 23051223@kiit.ac.in