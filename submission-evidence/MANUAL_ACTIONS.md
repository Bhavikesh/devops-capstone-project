# Guide: Remaining Screenshots & Lab Cluster Steps

This guide details the exact steps for capturing the remaining 16 board screenshots and executing the 2 cluster verification commands in your course lab environment.

---

## Part 1: GitHub Projects Board & Screenshot Captures (16 Screenshots)

All 10 required User Stories have already been created as GitHub Issues in your repository:
[https://github.com/Bhavikesh/customer-accounts-microservice/issues](https://github.com/Bhavikesh/customer-accounts-microservice/issues)

### Step 1: Set Up Your GitHub Projects Board
1. Navigate to: [https://github.com/Bhavikesh/customer-accounts-microservice](https://github.com/Bhavikesh/customer-accounts-microservice)
2. Click the **Projects** tab at the top.
3. Click **New project** (select the **Board** layout) and title it `Customer Accounts Kanban`.
4. Configure columns / statuses in this order:
   - `New Issues`
   - `Ice Box`
   - `Product Backlog`
   - `Sprint Backlog`
   - `In Progress`
   - `Done`
5. Click **+ Add item** and select all 10 issues (#1 through #10).

---

### Step 2: Capture Planning Phase Screenshots (Tasks 3–6)

#### Task 3: `submission-evidence/planning-userstories-done.png`
- **Board State:** Place all 10 user stories (#1 to #10) in the **New Issues** column.
- **Action:** Take a screenshot of the entire board and save as `submission-evidence/planning-userstories-done.png`.

#### Task 4: `submission-evidence/planning-productbacklog-done.png`
- **Board State:** Move all 10 user stories into the **Ice Box** column.
- **Action:** Take a screenshot of the board and save as `submission-evidence/planning-productbacklog-done.png`.

#### Task 5: `submission-evidence/planning-labels-done.png`
- **Board State:** Move all 10 user stories into the **Product Backlog** column. Make sure cards display their labels (`Technical Debt` on #1, `enhancement` on #2–#10).
- **Action:** Take a screenshot of the board and save as `submission-evidence/planning-labels-done.png`.

#### Task 6: `submission-evidence/planning-kanban-done.png`
- **Board State:** Move the Sprint 1 stories (#1, #2, #3, #4, #5) into the **Sprint Backlog** column. Add story point estimates (e.g. 1 to 3 points).
- **Action:** Take a screenshot of the board and save as `submission-evidence/planning-kanban-done.png`.

---

### Step 3: Capture Sprint 1 Implementation Screenshots (Tasks 8–12)

Move cards to **Done** one by one as they were implemented:

- **Task 8 (`submission-evidence/rest-techdebt-done.png`):**
  Move `#1: Setting up the development environment` to **Done**. Take screenshot.
- **Task 9 (`submission-evidence/read-accounts.png`):**
  Move `#2: Read an account from the service` to **Done**. Take screenshot.
- **Task 10 (`submission-evidence/list-accounts.png`):**
  Move `#3: List all accounts in the service` to **Done**. Take screenshot.
- **Task 11 (`submission-evidence/update-accounts.png`):**
  Move `#4: Update an account in the service` to **Done**. Take screenshot.
- **Task 12 (`submission-evidence/delete-accounts.png`):**
  Move `#5: Delete an account from the service` to **Done**. Take screenshot.

---

### Step 4: Capture Sprint 2 Screenshots (Tasks 18, 20, 24)

- **Task 18 (`submission-evidence/sprint2-plan.png`):**
  Move Sprint 2 stories (`#6: Need the ability to automate continuous integration checks` and `#7: Need to add security headers and CORS policies`) from Product Backlog into **Sprint Backlog**. Take screenshot.
- **Task 20 (`submission-evidence/ci-kanban-done.png`):**
  Move `#6` to **Done**. Take screenshot.
- **Task 24 (`submission-evidence/security-kanban-done.png`):**
  Move `#7` to **Done**. Take screenshot.

---

### Step 5: Capture Sprint 3 Screenshots (Tasks 25, 27, 28, 33)

- **Task 25 (`submission-evidence/sprint3-plan.png`):**
  Move Sprint 3 stories (`#8: Containerize your microservice using Docker`, `#9: Deploy your Docker image to Kubernetes`, and `#10: Create a CD pipeline to automate deployment to Kubernetes`) into **Sprint Backlog**. Take screenshot.
- **Task 27 (`submission-evidence/kube-docker-done.png`):**
  Move `#8` to **Done**. Take screenshot.
- **Task 28 (`submission-evidence/kube-kubernetes-done.png`):**
  Move `#9` to **Done**. Take screenshot.
- **Task 33 (`submission-evidence/cd-pipeline-done.png`):**
  Move `#10` to **Done**. Take screenshot.

---

## Part 2: Course Lab Cluster Execution (Tasks 31 & 32)

Open your assigned **IBM Cloud IDE with OpenShift / Kubernetes** from your Coursera lab session:

### 1. Clone Your Repository
```bash
git clone https://github.com/Bhavikesh/customer-accounts-microservice.git
cd customer-accounts-microservice
```

### 2. Task 31: Kubernetes Deployment Evidence
```bash
kubectl apply -f deploy/
kubectl get all -l app=accounts > submission-evidence/kube-deploy-accounts.txt
```

### 3. Task 32: Tekton Pipeline Execution Evidence
```bash
kubectl apply -f tekton/tasks.yaml
kubectl apply -f tekton/pipeline.yaml
kubectl apply -f tekton/pvc.yaml

tkn pipeline start cd-pipeline \
  -w name=pipeline-workspace,claimName=pipelinerun-pvc \
  -p repo-url="https://github.com/Bhavikesh/customer-accounts-microservice.git" \
  -p branch="main" \
  --showlog > submission-evidence/pipelinerun.txt
```

### 4. Push Final Deliverables
```bash
git add submission-evidence/
git commit -m "docs: add cluster deployment and pipeline execution evidence"
git push origin main
```
