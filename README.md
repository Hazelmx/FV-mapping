# Recall the first round of FV_Dummy identification
In the first round of FV_indentification, we create FV_dummy=0 to FV_dummy=13 to classify all products appeared in the transaction file: TRANSACTION_DETAIL.xlsx (01/16)

<img width="615" height="292" alt="Screenshot 2025-09-18 at 23 29 56" src="https://github.com/user-attachments/assets/1f6939c3-01b1-4976-bfa4-1ede3b1fcd08" />

<img width="600" height="200" alt="image" src="https://github.com/user-attachments/assets/a7a64a66-d66e-4d7d-b30d-220f00f5cf51" />



# Workflow Overview
**Step 1: Automation**

Input files:

TRANSECTION_DETAIL.xlsx

(Latest transaction record file that requires FV_dummy mapping.)

FV_dummy_unit_updated.xlsx

(Previous transaction record file with FV_dummy variables already mapped.)

Process:
Run the code with the two input files in step 1.

Output files:

TRANSECTION_DETAIL_with_dummy_new.xlsx
(Latest transaction file with FV_dummy mapped automatically.
New/unseen products are temporarily assigned FV_dummy = 0.)

New_product.xlsx
(List of newly appeared products not mapped in the previous round.)

unique_products_all.xlsx
(Complete list of products by FV_dummy, saved in separate sheets.)

**Step 2: Human-in-the-Loop**

Open New_product.xlsx.

Manually map each new product to the correct FV_dummy.

Add these newly mapped products to the corresponding sheets in unique_products_all.xlsx and create a list of products of dummies saved in products of dummies.xlsx

**Step 3: Automation**

Input files:

products of dummies.xlsxl.xlsx
(Generated with newly mapped products from Step 2.)

TRANSECTION_DETAIL.xlsx

(Latest transaction record file that requires FV_dummy mapping.)

Process:
Run the code with the two input files in step 3.

Output file:

TRANSECTION DETAIL with dummy_new.xlsx
(Final file, with all products fully mapped to their FV_dummy categories.)

**Deliverables**

TRANSECTION DETAIL with dummy_new.xlsx → Final transaction dataset with completed dummy mapping.

unique_products_all.xlsx → Master reference list of products per dummy category.

New_product.xlsx → Newly appeared products requiring manual review and mapping.
