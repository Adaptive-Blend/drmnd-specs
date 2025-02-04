<h1 style="text-align:left; font-weight: bold;   font-family: 'Cormorant Garamond Regular', Times, serif;">DRMND PROTOCOL SPECIFICATIONS</h1>


<!-- markdownlint-disable-next-line MD036 #667994-->
<!-- **DRMND: 1st-Principles Skincare Engine, simple, adaptive, effective.** -->

This book specifies the DRMND protocol, a first-principles framework for gamified, real-time, user-centric, data-driven skincare.


Turn the DRMND protocol into a GDB (Game Development Bible) from 1st principles intentionally optimized clear
and each part functional and as a whole unit from 1st principles


<!-- # **DRMND Protocol**: Skincare Systemized from 1st Principles   -->

<!-- **Mission**: Simplify skincare by combining core priorities and profiles with essential care functionalities.   -->



---

## **SkinCare101: Skin + Care**

### **0.0. [Skin] Priorities**

Every routine begins with **Priorities**:
- **Concerns** = current state.
- **Results** = desired state.
- **Actions** = bridge between them.

<br>

#### **Concern →  Result Mapping**

| **Concern**               | **Optimized Essential Actions**         | **Result**               |
|----------------------------|--------------------------------------|----------------------------:|
| **Dryness**               | `Hydrate (H)`                          | **Deep Hydration**               |
| **Dullness**              | `Clean (C)`, `Hydrate (H)`               | **Brightening**              |
| **Wrinkles / Fine Lines** | `Treat (T)`, `Hydrate (H)`               | **Anti / Graceful Aging** |
| **Acne**                  | `Treat (T)`, `Clean (C)`                 | **Clear Breakouts**                  |
| **Pore Visibility**       | `Treat (T)`, `Clean (C)`                 | **Pore Refinement**       |
| **Redness**               | `Treat (T)`, `Protect (P)`               | **Soothing Irritation**|
| **Hyperpigmentation**     | `Treat (T)`, `Protect (P)`               | **Even SkinTone**     |


<br>

---

### **Selection Framework**
- **Primary Concern** (*Current State*): *"What skincare issue demands immediate attention right now?"*
- **Secondary Choice** (*Priority Shift*): *“Next priority: unresolved issue or desired outcome?”*
- **Tertiary Choice** (*Optimization*): *"Final priority to refine your regimen."*
<br>

**1. Primary Concern** (*Current State*): *"What skincare issue demands immediate attention right now?"*
- **Rule:** Must select a **Concern** (e.g., Dryness, Acne).
- **Function:** Anchors regimen in *current need* → triggers **Essential Actions** (e.g., `Hydrate`) + auto-adds **Result** (e.g., Deep Hydration).

**2. Secondary Choice** (*Priority Shift*): *“Next priority: unresolved issue or desired outcome?”*
- **Flexibility:** Choose **Concern** (adds Actions + Result) **or Result** (e.g., Brightening).

**3. Tertiary Choice** (*Optimization*): *"Final priority to refine your regimen."*
- **Constraint:** No duplicates; lower priority than Primary/Secondary.

---

#### **Rules**
- **Max 3 total** (1 Primary + 1 Secondary + 1 Tertiary).
- **Actions deduplicated** (e.g., `Hydrate` selected twice → retained once).
- **Primary locked to Concern** → ensures regimen starts from *`current reality`*.

---
#### **Priority Matrix**
- **3x2(6) Matrix** : 2 Actions per Concern/Result, Default
- **3x3(9) Matrix** : 3 Actions per Concern/Result, Used if Primary Concern not addressed / Extreme cases.

|  | P¹ | S² | T³ |
|--|---|---|---|
| P¹ |`H` ¹|`C` ²|`T` ³|
| S² |`C` ²|`H` ⁴|`T` ⁶|
| T³ |`T` ³|`C` ⁶|`H` ⁹|


|   | ¹ | ² | ³ |
|---|---|---|---|
| ¹ | ¹ | ² | ³ |
| ² | ² | ⁴ | ⁶ |
| ³ | ³ | ⁶ | ⁹ |


|   | P | S | T |
|---|---|---|---|
| P |`H`|`C`|`T`|
| S |`C`|`H`|`T`|
| T |`T`|`C`|`H`|


#### **Priority Rules**
- **Concern/Result Priority**
- **Action/Function Priority** : Takes precidence if Concern/Result  Priority Match

|`H`|`C`|`C`|`T`|`T`|`H`|`C`|`T`|`H`|
|---|---|---|---|---|---|---|---|---|
| P | S | P | T | P | S | T | S | T |

**Priority Decoding (OOP)**
- `Hydrate Primary`
- `Clean Secondary`
- `Clean Primary`
- `Treat Tertiary`
- `Treat Primary`
- `Hydrate Secondary`
- `Clean Tertiary`
- `Treat Secondary`
- `Hydrate Tertiary`


---
#### **Example**
**Selections**:
1. **Primary**: Dryness → `H` → Deep Hydration
2. **Secondary**: Dullness → `C, H` → Brightening
3. **Tertiary**: Even SkinTone (Result) → `T, P`

**Priority Matrix**
|  | P | S | T |
|--|---|---|---|
| P |`H` ¹|`C` ²|`T` ³|
| S |`C` ²|`H` ⁴|`T` ⁶|
| T |`T` ³|`C` ⁶|`H` ⁹|

<br>

**Priority Rules**
|`H`|`C`|`C`|`T`|`T`|`H`|`C`|`T`|`H`|
|---|---|---|---|---|---|---|---|---|
| P | S | P | T | P | S | T | S | T |


**Output**:
- **Results**: Deep Hydration, Brightening, Even SkinTone
- **Actions**: `H, C, T, P`
- **Function**: `H, C, C, T, T, H, C, T, H`

```JSON
//Skin Priority
{
  "primary": ["dryness"],
  "secondary": ["dullness"],
  "tertiary": ["even-skin-tone"]
}

```
---


### **0.1. [Skin] Profile**
Refine routines based on individual **Skin Profiles**:
- **Skin Type**: Dry ↔ Oily
- **Sensitivity**: High ↔ Low
- **Allergies**: Avoid specific triggers
- **Environment**: Adapt to weather, age, and lifestyle.

```JSON
//Skin Profile
{
  "skin_type": "oily",
  "sensitivity": "high",
  "allergies": ["fragrance"]
}

```
---

## **1. Care**

#### **4 Core Functionalities** :  `🫧 Clean` , `🎯 Treat` ,`💧 Hydrate` , `🔆 Protect`


<br>


| **Fx**       | **Purpose**                                 |
|--------------|---------------------------------------------|
| 🫧 **Clean**  | Remove `dirt/impurities`, `dead-skin(exfoliate)`. |
| 🎯 **Treat**  | `target`,`alleviate` specific concerns.     |
| 💧 **Hydrate**|`lock in moisture`.                          |
| 🔆 **Protect**| `shield` skin from environmental stressors.   |




<br>

```JSON
//Function of Skin[Care]

{
  "Clean": ["dirt/impurities", "dead-skin"],
  "Treat": ["target", "alleviate"],
  "Hydrate": ["lock in moisture"],
  "Protect": ["shield"]
}

```

---

## **Protocol Overview**

**Formula**: **Skin Priorities × Skin Profile × Core Functionalities**

1. **Define Priorities**: Focus on up to **3 concerns** (Primary, Secondary, Tertiary).
2. **Map Core Functionalities**: Address concerns using **C (Clean)**, **T (Treat)**, **H (Hydrate)**, and **P (Protect)**.
3. **Adapt via Profile**: Refine products and routines to match individual needs.
4. **Apply in Order**: Execute routines systematically for maximum efficacy.

---

### **Example Routine**

**Case**:
- **Primary Concern**: Acne → Treat (T), Clean (C)
- **Secondary Concern**: Dullness → Clean (C), Hydrate (H)
- **Intended Result**: Brightening → Clean (C), Hydrate (H)
- **Profile**: Sensitive, Oily

**Routine**:
1. **Step 1**: Gentle cleanser (Clean 🫧)
2. **Step 2**: Acne serum (Treat 🎯)
3. **Step 3**: Lightweight moisturizer (Hydrate 💧)
4. **Step 4**: Sunscreen (Protect 🔆)


```JSON
{
  "priorities": {
    "primary": ["acne"],
    "secondary": ["dullness"],
    "tertiary": ["brightening"]
  },
  "profile": {
    "skin_type": "oily",
    "sensitivity": "high",
    "allergies": ["fragrance"]
  }
}

{
  "Clean": ["remove impurities"],
  "Treat": ["target acne"],
  "Hydrate": ["lock in moisture"],
  "Protect": ["shield from UV"]
}

{
  "routine": [
    { "step": 1, "action": "clean", "product": "gentle cleanser" },
    { "step": 2, "action": "treat", "product": "acne serum" },
    { "step": 3, "action": "hydrate", "product": "lightweight moisturizer" },
    { "step": 4, "action": "protect", "product": "sunscreen" }
  ]
}

```

---

## **Why DRMND?**
- **Minimalist Design**: Only the essentials, no unnecessary steps.
- **Adaptable**: Dynamic solutions tailored to every user’s skin.
- **Efficacy-First**: Address core needs directly, without compromise.

The DRMND Protocol is the foundation for precise, effective skincare.
