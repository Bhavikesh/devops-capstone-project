# DevOps Capstone Project — Submission Deliverables Checklist

This document maps all 33 capstone assignment questions/tasks to their deliverables, verified filenames, URLs, and current verification status for the official repository:
**`https://github.com/Bhavikesh/devops-capstone-project`**

## Verification Status Legend
- **VERIFIED**: Deliverable generated, executed with genuine output, and verified on public GitHub or local cluster.
- **AWAITING SCREENSHOT**: Requires manual screenshot capture from the GitHub Projects board UI (to maintain absolute academic integrity and prevent fake mockups).
- **COURSE LAB ACTION**: Requires execution inside the IBM Cloud / OpenShift course lab environment if remote cluster credentials are required.

---

## 33 Assignment Questions Mapping

| # | Task Requirement | Deliverable / Path | Status | Verification Details |
|---|---|---|---|---|
| **1** | Public GitHub README.md URL | `README.md` | **VERIFIED** | [README.md](https://github.com/Bhavikesh/devops-capstone-project/blob/main/README.md) verified with DevOps Capstone title, CI status badge, architecture, endpoints table, testing and container guides. |
| **2** | Public GitHub user-story.md URL | `user-story.md` | **VERIFIED** | [user-story.md](https://github.com/Bhavikesh/devops-capstone-project/blob/main/user-story.md) verified in repository root and `.github/ISSUE_TEMPLATE/user-story.md`. |
| **3** | planning-userstories-done.png | `submission-evidence/planning-userstories-done.png` | AWAITING SCREENSHOT | Requires screenshot of GitHub Projects Kanban board showing all 7 required user stories visible in the *New Issues* column. |
| **4** | planning-productbacklog-done.png | `submission-evidence/planning-productbacklog-done.png` | AWAITING SCREENSHOT | Requires screenshot of GitHub Projects Kanban board with user stories moved to the *Ice Box* column. |
| **5** | planning-labels-done.png | `submission-evidence/planning-labels-done.png` | AWAITING SCREENSHOT | Requires screenshot of GitHub Projects board with cards in *Product Backlog* showing `Technical Debt` and `enhancement` labels. |
| **6** | planning-kanban-done.png | `submission-evidence/planning-kanban-done.png` | AWAITING SCREENSHOT | Requires screenshot of GitHub Projects board with Sprint 1 stories (#1 to #5) moved into the *Sprint Backlog* column with story estimates. |
| **7** | Public GitHub setup.cfg URL | `setup.cfg` | **VERIFIED** | [setup.cfg](https://github.com/Bhavikesh/devops-capstone-project/blob/main/setup.cfg) verified; configured with nosetests (verbosity=2, spec, coverage), coverage reporting, flake8 exclusions, pylint. |
| **8** | rest-techdebt-done.png | `submission-evidence/rest-techdebt-done.png` | AWAITING SCREENSHOT | Screenshot showing "Set up the development environment" (#1) card moved to *Done*. |
| **9** | read-accounts.png | `submission-evidence/read-accounts.png` | AWAITING SCREENSHOT | Screenshot showing "Read an account from the service" (#2) card moved to *Done*. |
| **10** | list-accounts.png | `submission-evidence/list-accounts.png` | AWAITING SCREENSHOT | Screenshot showing "List all accounts in the service" (#5) card moved to *Done*. |
| **11** | update-accounts.png | `submission-evidence/update-accounts.png` | AWAITING SCREENSHOT | Screenshot showing "Update an account in the service" (#3) card moved to *Done*. |
| **12** | delete-accounts.png | `submission-evidence/delete-accounts.png` | AWAITING SCREENSHOT | Screenshot showing "Delete an account from the service" (#4) card moved to *Done*. |
| **13** | rest-create-done | `submission-evidence/rest-create-done` | **VERIFIED** | Live `curl -s -i -X POST` captured with HTTP 201 Created and `Location: https://127.0.0.1:8080/accounts/1`. |
| **14** | rest-list-done | `submission-evidence/rest-list-done` | **VERIFIED** | Live `curl -s -i` to `/accounts` captured with HTTP 200 OK and JSON array of created accounts. |
| **15** | rest-read-done | `submission-evidence/rest-read-done` | **VERIFIED** | Live `curl -s -i` to `/accounts/1` captured with HTTP 200 OK and account payload. |
| **16** | rest-update-done | `submission-evidence/rest-update-done` | **VERIFIED** | Live `curl -s -i -X PUT` to `/accounts/1` captured with HTTP 200 OK and updated payload. |
| **17** | rest-delete-done | `submission-evidence/rest-delete-done` | **VERIFIED** | Live output demonstrating both DELETE on `/accounts/1` (HTTP 204 No Content + 404 confirmation) and DELETE on `/accounts` (HTTP 405 Method Not Allowed). |
| **18** | sprint2-plan.png | `submission-evidence/sprint2-plan.png` | AWAITING SCREENSHOT | Screenshot of board showing Sprint 2 user stories moved to *Sprint Backlog*. |
| **19** | ci-workflow-done | `submission-evidence/ci-workflow-done.txt` | **VERIFIED** | Genuine GitHub Actions workflow run log saved; all jobs (setup, container initialization, flake8, pylint, nose with PostgreSQL) completed successfully. |
| **20** | ci-kanban-done.png | `submission-evidence/ci-kanban-done.png` | AWAITING SCREENSHOT | Screenshot showing CI automation card moved to *Done*. |
| **21** | Public GitHub ci-build.yaml URL | `.github/workflows/ci-build.yaml` | **VERIFIED** | [.github/workflows/ci-build.yaml](https://github.com/Bhavikesh/devops-capstone-project/blob/main/.github/workflows/ci-build.yaml) verified on GitHub with checkout, setup, flake8, and nosetests. |
| **22** | Public GitHub __init__.py URL | `service/__init__.py` | **VERIFIED** | [service/__init__.py](https://github.com/Bhavikesh/devops-capstone-project/blob/main/service/__init__.py) verified; Flask application initialized with Talisman security headers and CORS. |
| **23** | security-headers-done | `submission-evidence/security-headers-done` | **VERIFIED** | Genuine `nosetests` output verifying Talisman security headers and CORS; 30 tests passed with 98% coverage. |
| **24** | security-kanban-done.png | `submission-evidence/security-kanban-done.png` | AWAITING SCREENSHOT | Screenshot showing security headers & CORS card moved to *Done*. |
| **25** | sprint3-plan.png | `submission-evidence/sprint3-plan.png` | AWAITING SCREENSHOT | Screenshot of board showing Sprint 3 user stories moved to *Sprint Backlog*. |
| **26** | kube-app-output | `submission-evidence/kube-app-output` | **VERIFIED** | Genuine JSON output `{"name":"Account REST API Service","paths":"http://127.0.0.1:8081/accounts","version":"1.0"}` captured from live running Docker container. |
| **27** | kube-docker-done.png | `submission-evidence/kube-docker-done.png` | AWAITING SCREENSHOT | Screenshot showing "Containerize your microservice using Docker" (#6) moved to *Done*. |
| **28** | kube-kubernetes-done.png | `submission-evidence/kube-kubernetes-done.png` | AWAITING SCREENSHOT | Screenshot showing "Deploy your Docker image to Kubernetes" (#7) moved to *Done*. |
| **29** | Public GitHub Dockerfile URL | `Dockerfile` | **VERIFIED** | [Dockerfile](https://github.com/Bhavikesh/devops-capstone-project/blob/main/Dockerfile) verified on GitHub using `python:3.9-slim` and non-root user `theia`. |
| **30** | kube-images | `submission-evidence/kube-images` | **VERIFIED** | Genuine `docker images` output capturing Image name, Tag, Image ID, Created time (`CreatedAt`), and Size. |
| **31** | kube-deploy-accounts | `submission-evidence/kube-deploy-accounts.txt` | **VERIFIED** | Genuine output of `kubectl get all -l app=accounts` showing running pod, service, deployment, and replicaset. |
| **32** | pipelinerun.txt | `submission-evidence/pipelinerun.txt` | **VERIFIED / READY** | Fully configured Tekton pipeline (`cd-pipeline`) with 6 stages (init, clone, lint, tests, build, deploy); authentic pipeline log captured. |
| **33** | cd-pipeline-done.png | `submission-evidence/cd-pipeline-done.png` | AWAITING SCREENSHOT | Screenshot showing "Create a CD pipeline to automate deployment to Kubernetes" moved to *Done*. |
