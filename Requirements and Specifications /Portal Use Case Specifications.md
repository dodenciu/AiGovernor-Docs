# Use Case Document: AiGovernor Portal Application

**Version: 1.0**
**Date: 13.11.2023**

## 1. Introduction

The Use Case Document provides an overview of the main use cases for the "AiGovernor Portal" application, designed for administrators to manage tenants, features, and licenses for the AiGovernor product.

## 2. Use Cases

### 2.1 Use Case 1: Create a New Tenant

**Description:** The Administrators can create new tenants in the system.

**Main Actor:** Administrator

**Preconditions:**
- The Administrator is logged in.
- The system is in an operational state.

**Basic Flow:**
1. The Administrator accesses the "Create New Tenant" function.
2. The system displays a form for entering tenant information.
3. The Administrator fills in the required tenant details.
4. Administrator submits the form.
5. The system adds the new tenant with a default "Free" license to the system.
6. The tenant is created as inactive.

**Postconditions:**
- A new tenant is created and added to the system.

**Notes:**
- The tenant is created as inactive and will remain so until a license is assigned. Activation will occur only after a license is assigned to the tenant.

### 2.2 Use Case 2: Create a New Feature

**Description:** Administrators can add new features to the system.

**Main Actor:** Administrator

**Preconditions:**
- The administrator is logged in.
- The system is in an operational state.

**Basic Flow:**
1. The administrator accesses the "Create New Feature" function.
2. The system displays a form for entering feature details.
3. The administrator fills in the required feature information, including the name and description.
4. Administrator submits the form.
5. The system creates a new feature with the provided details and assigns a unique feature ID.
6. The system records the current date and time in the "created_at" and "updated_at" fields.

**Postconditions:**
- A new feature is created and added to the system.
- The feature is assigned a unique feature ID.
- The "created_at" and "updated_at" timestamps are updated to reflect the creation time.

**Notes:**
- Features are created and managed by administrators.
- The "created_at" and "updated_at" timestamps are used for tracking feature creation and modification times.


### 2.3 Use Case 3: Create a License

**Description:** Administrators can create licenses for tenants. A tenant is required to create a license. The license is based on a template that defines available features and maximum duration.

**Main Actor:** Administrator

**Preconditions:**
The administrator is logged in.
- A tenant has been created.
- The system is in an operational state.

**Basic Flow:**
1. The administrator accesses the "Create New License" function.
2. The administrator selects a license template and a tenant to create a license.
3. The administrator selects the features available for the license.
4. The administrator specifies the license duration (maximum time).
5. The administrator confirms the creation of the license.
6. The system creates a new license based on the template for the selected tenant with the specified duration.

**Postconditions:**
- A new license is created for the tenant based on the selected template, features, and duration.

**Notes:**
- License creation is contingent on the existence of a tenant.
- The license template defines available features and maximum duration.

### 2.4 Use Case 4: Assign License to Tenant

**Description:** Administrators can assign licenses to tenants. License assignment triggers infrastructure creation, which is an asynchronous operation.

**Main Actor:** Administrator

**Preconditions:**
The administrator is logged in.
- A tenant has been created.
- A license has been created for the tenant.
- The system is in an operational state.

**Basic Flow:**
1. The Administrator selects a tenant to assign a license.
2. The system displays the list of available licenses.
3. The Administrator selects a license to assign to the tenant.
4. The Administrator confirms the license assignment.
5. The system initiates infrastructure creation for the tenant asynchronously.
6. The tenant's status is changed to "Scheduled".

**Postconditions:**
- The selected license is assigned to the tenant.
- Infrastructure creation is initiated asynchronously.
- The tenant's status is changed to "Active" upon successful infrastructure creation or "Unsuccessful" after a 1-hour timeout.

**Notes:**
- License assignment triggers infrastructure creation, which is an asynchronous operation.
- The tenant remains inactive until infrastructure creation is successfully completed or a 1-hour timeout elapses.

### 2.5 Use Case 5: View Tenant Details

**Description:** Administrators can view a tenant's details.

**Main Actor:** Administrator

**Preconditions:**
- The Administrator is logged in.
- A tenant has been created.

**Basic Flow:**
1. The Administrator selects a tenant to view.
2. The system displays detailed information about the selected tenant: name, status, description, creation and last update dates, contact, features, license name, etc.

**Postconditions:**
- The administrator can view the tenant's details.

## 3. Alternative Flows

Include any alternative or exceptional flows for each use case.

## 4. Extensions

Describe any extensions or additional features related to each use case.

## 5. User Acceptance Criteria

- Each use case must be testable and fulfill its described purpose.
- All use cases must be implemented and function as specified.

## 6. Document Revision History

| Version | Date       | Author               |  Description of Changes   |
|---------|------------|----------------------|---------------------------|
| 1.0     | 13.11.2023 | Vlad Daniel Dodenciu | Initial Draft             |
