# Machine Unlearning Project

This project builds an end-to-end **user-level machine unlearning** pipeline that treats **data deletion** as a first-class operation. Given a user deletion request, the system deterministically constructs a **retain/forget split** and updates the model using either:

- **Full retraining** (gold standard for correctness), or
- **Efficient approximate unlearning** via **Fisher Scrubbing** (much lower deletion-time cost)

The goal is to reduce the cost of supporting deletion requests at scale—especially under **heavy-tailed workloads** where a small number of users contribute a disproportionate share of training data—while keeping model behavior close to what full retraining would produce.

---

## Key Ideas

- **User deletion as an operation:** A deletion request is expressed as `delete(user_id)`.
- **Retain/forget split contract:** For each request, we build:
  - **Forget set:** all records owned by the user
  - **Retain set:** all remaining permitted records
- **Two update modes:**
  - **Retraining:** trains a fresh model on the retain set
  - **Fisher Scrubbing:** approximates the retrained model update efficiently

---

## What’s in this repo

Typical contents may include:
- `notebooks/`: Deletion with Random User-Sample Pairing notebook
- `notebooks/`: K9db Integration  
- `notebooks/`: Deletion with Exclusive Classes
- `report/`: Final report

---

Team Member
- Jinghan/Tracy Cui
- Yuki Li
- Yang Lu
- Xin Wei
