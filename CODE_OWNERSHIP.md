# Code Ownership & Team Responsibility Structure

## 📋 Overview

This document clearly defines **who owns what** in the urbanladder BDD Cucumber automation framework. This ensures:
- ✅ Minimal merge conflicts
- ✅ Clear Git accountability
- ✅ Parallel development workflow
- ✅ Professional project structure

---

## 👥 Team Members & Responsibilities

| Team Member | GitHub Username | Primary Responsibility |
|-------------|-----------------|------------------------|
| **Sai Ganesh** | @saiganesh | **Lead** - Collections/Living Room + Common Components |
| **Ranjith Kumar** | @Ranjithkumar-4 | Bookshelves Feature |
| **Saran** | @saran-csk | Gift Card & Payment Feature |
| **Ramprasath** | *TBD* | *To be added in future* |

---

## 📁 Folder & File Ownership Structure

### 1️⃣ **BOOKSHELVES FEATURE** → Ranjith Kumar (@Ranjithkumar-4)

**What they own:**
- Features
  - `Features/Bookshelves.feature`
- Step Definitions
  - `src/test/java/stepDefinitions/BookshelvesSteps.java`
- Page Objects
  - `src/test/java/pageObjects/BookShelvesPage.java`

**Responsibilities:**
- Bookshelves → filter by price & storage → print first 3

**Git Blame Ownership:** Full responsibility for these files

---

### 2️⃣ **COLLECTIONS/LIVING ROOM FEATURE** → Sai Ganesh (@saiganesh)

**What they own:**
- Features
  - `Features/Collections.feature`
- Step Definitions
  - `src/test/java/stepDefinitions/CollectionsSteps.java`
- Page Objects
  - `src/test/java/pageObjects/livingroom.java`

**Responsibilities:**
- New Arrivals → Living Room → print Bestseller & New Arrivals

**Git Blame Ownership:** Full responsibility for these files

---

### 3️⃣ **GIFT CARD & PAYMENT FEATURE** → Saran (@saran-csk)

**What they own:**
- Features
  - `Features/GiftCards.feature`
- Step Definitions
  - `src/test/java/stepDefinitions/GiftCardSteps.java`
- Page Objects
  - `src/test/java/pageObjects/GiftCardPage.java`
  - `src/test/java/pageObjects/payment.java`

**Responsibilities:**
- Gift Card → fill details → **wrong email** → print error
- Gift Card → Pay Now → cancel payment → print cancellation error

**Git Blame Ownership:** Full responsibility for these files

---

### 4️⃣ **RAMPRASATH** (To be added in future)

*Reserved for future assignment*

---

## 🔒 SHARED/COMMON COMPONENTS → Sai Ganesh (@saiganesh) [READ-ONLY]

These files should **NOT** be modified by other team members without lead approval:

| File | Purpose | Owner |
|------|---------|-------|
| `src/test/java/factory/BaseClass.java` | Driver setup, waits, config | @saiganesh |
| `src/test/java/stepDefinitions/Hooks.java` | Before/After hooks | @saiganesh |
| `src/test/java/pageObjects/Homepage.java` | Homepage element locators | @saiganesh |
| `src/test/java/pageObjects/Basepage.java` | Base page class | @saiganesh |
| `pom.xml` | Dependencies & build config | @saiganesh |

---

## ❌ WHO SHOULD NOT TOUCH WHAT

| File/Folder | Ranjith | Sai | Saran | Notes |
|-------------|---------|-----|-------|-------|
| BaseClass.java | ❌ | ✅ | ❌ | Shared - Lead only |
| Hooks.java | ❌ | ✅ | ❌ | Shared - Lead only |
| Homepage.java | ❌ | ✅ | ❌ | Shared - Lead only |
| Basepage.java | ❌ | ✅ | ❌ | Shared - Lead only |
| BookshelvesSteps.java | ✅ | ❌ | ❌ | Ranjith's feature |
| CollectionsSteps.java | ❌ | ✅ | ❌ | Sai's feature |
| GiftCardSteps.java | ❌ | ❌ | ✅ | Saran's feature |
| BookShelvesPage.java | ✅ | ❌ | ❌ | Ranjith's page |
| livingroom.java | ❌ | ✅ | ❌ | Sai's page |
| GiftCardPage.java | ❌ | ❌ | ✅ | Saran's page |
| payment.java | ❌ | ❌ | ✅ | Saran's page |

---

## 🔄 Git Workflow (Practical)

### Step 1: Create Feature Branch
```bash
# Ranjith creates his branch
git checkout -b ranjith-bookshelves

# Sai creates his branch
git checkout -b sai-collections

# Saran creates his branch
git checkout -b saran-giftcard
```

### Step 2: Work on Your Feature
```bash
# Only modify files you own!
# Example for Ranjith:
# - Modify Bookshelves.feature
# - Modify BookshelvesSteps.java
# - Modify BookShelvesPage.java
```

### Step 3: Commit & Push
```bash
git add .
git commit -m "feat: Add bookshelves filter by price and storage"
git push origin ranjith-bookshelves
```

### Step 4: Create Pull Request
- PR title: Clear and descriptive
- PR description: What was tested
- Request review from @saiganesh (lead)

### Step 5: Lead Merges to Main
```bash
# After review approval
git checkout main
git pull origin main
git merge ranjith-bookshelves
git push origin main
```

---

## 📋 Code Review Policy

1. **Every PR requires review** from the team lead (@saiganesh)
2. **Modifications to shared components** require explicit approval
3. **No direct commits to main** - always use branches and PRs

---

## 🎯 How to Use CODEOWNERS File

The `.github/CODEOWNERS` file automatically:
- 📌 Assigns reviewers to PRs
- 🔔 Notifies owners when their code is modified
- 🛡️ Protects against unauthorized changes

---

## 💡 Best Practices

✅ **DO:**
- Work only on files you own
- Communicate with team before touching shared components
- Write clear commit messages
- Keep branches up-to-date with main

❌ **DON'T:**
- Modify shared components (BaseClass, Hooks, etc.)
- Work on other team member's features
- Push directly to main
- Ignore code review feedback

---

## 🔮 Future Additions

When **Ramprasath** joins:
1. Update this file with their username
2. Update `.github/CODEOWNERS` file
3. Create their feature branches
4. Divide Gift Card responsibilities if needed

---

## 📞 Questions?

Contact **Sai Ganesh** (@saiganesh) for:
- Clarifications on ownership
- Permissions to modify shared components
- Adding new team members
- Architecture changes

---

**Last Updated:** 2026-05-15
**Document Owner:** @saiganesh
