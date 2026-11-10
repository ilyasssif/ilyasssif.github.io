# Wikidata Creation Guide for Ilyass Sif

Wikidata is the primary structured database crawled by Google's Knowledge Graph algorithm. Having an item here makes it significantly easier for Google to identify you as an entity.

---

### Step 1: Create an Account
1. Go to [https://www.wikidata.org/](https://www.wikidata.org/).
2. Click **Create account** (top right) or log in with your Wikimedia / Wikipedia account if you have one.

---

### Step 2: Create a New Item
1. In the left sidebar, click **"Create a new Item"** (or visit [https://www.wikidata.org/wiki/Special:NewItem](https://www.wikidata.org/wiki/Special:NewItem)).
2. Fill in the initial fields:
   * **Language:** English (`en`)
   * **Label:** `Ilyass Sif`
   * **Description:** `Moroccan computer scientist and software developer`
   * **Aliases:** `re3gi`, `ilyass-sif`
3. Click **Create**.

---

### Step 3: Add Statements
Once the item is created, click **"+ add statement"** for each of the following:

| Property (Search this in property box) | Value |
| :--- | :--- |
| **instance of** (`P31`) | `human` (`Q5`) |
| **sex or gender** (`P21`) | `male` (`Q6581097`) |
| **country of citizenship** (`P27`) | `Morocco` (`Q1028`) |
| **occupation** (`P106`) | `programmer` (`Q5482740`) |
| **field of work** (`P101`) | `machine learning` (`Q2539`) |
| **official website** (`P856`) | `https://re3gi.github.io/` |
| **GitHub username** (`P2037`) | `re3gi` |

---

### Step 4: Add References to Statements
For each statement (especially `occupation`, `GitHub username`, and `official website`), click **"+ add reference"**:
* **stated in / reference URL:** `https://github.com/re3gi`
* **retrieval date:** Today's date

---

*Note: Once submitted, Wikidata assigns an Item ID (e.g. `Q123456789`). You can then add this Wikidata ID to your website's JSON-LD `sameAs` array!*
