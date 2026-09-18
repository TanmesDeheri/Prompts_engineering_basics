# Prompt Engineering Summary Report

This report compares the **initial/naive prompts** used in this chat with the **later optimized prompts**. Scores reflect how well each response met the stated task requirements across **Relevance, Tone, Formatting, and Length**.

## 1. Evaluation Summary

| Content Task               | Prompt Version    | Relevance (1-5) | Tone (1-5) | Formatting (1-5) | Length (1-5) | Total Score /20 |
| -------------------------- | ----------------- | --------------: | ---------: | ---------------: | -----------: | --------------: |
| **1. Blog Post**           | Before (Naive)    |               4 |          3 |                3 |            4 |       **14/20** |
|                            | After (Optimized) |               5 |          5 |                5 |            5 |       **20/20** |
| **2. LinkedIn Post**       | Before (Naive)    |               4 |          4 |                4 |            4 |       **16/20** |
|                            | After (Optimized) |               5 |          5 |                5 |            5 |       **20/20** |
| **3. Email Campaign**      | Before (Naive)    |               3 |          3 |                3 |            4 |       **13/20** |
|                            | After (Optimized) |               5 |          5 |                5 |            5 |       **20/20** |
| **4. Instagram Caption**   | Before (Naive)    |               4 |          4 |                3 |            5 |       **16/20** |
|                            | After (Optimized) |               5 |          5 |                5 |            5 |       **20/20** |
| **5. YouTube Script**      | Before (Naive)    |               4 |          3 |                3 |            4 |       **14/20** |
|                            | After (Optimized) |               5 |          5 |                5 |            5 |       **20/20** |
| **6. Product Description** | Before (Naive)    |               4 |          4 |                3 |            4 |       **15/20** |
|                            | After (Optimized) |               5 |          5 |                5 |            5 |       **20/20** |

### Overall Score

| Version               |          Total |     Average |
| --------------------- | -------------: | ----------: |
| **Before — Naive**    |     **88/120** | **14.7/20** |
| **After — Optimized** |    **120/120** |   **20/20** |
| **Improvement**       | **+32 points** | **+5.3/20** |

---

# 1. Blog Post

## Before — Naive

**Prompt:**

> Write a blog post about why remote work is good.

**Response:**
The response produced a general article explaining benefits such as work-life balance, reduced commuting, flexibility, comfortable working environments, wider talent pools, learning opportunities, and environmental benefits.

### Objective

Create a general blog post explaining why remote work is beneficial.

### The Issue with 'Before' Prompt

The prompt provided almost no instructions about:

* Target audience
* Writing style
* Structure
* Paragraph length
* Formatting
* Specific perspective
* Tone

As a result, the response was useful but generic. It read more like a conventional informational article than a deliberately designed piece of content.

### The 'After' Strategy

The optimized prompt added:

* **Role prompting:** “Expert Blog Writer for a B2B Company”
* **Target audience:** B2B managers
* **Tone constraints:** no corporate fluff, active voice
* **Formatting constraints:** H1, H2 sections, bullet takeaways
* **Style transfer:** reference text supplied
* **Topic narrowing:** remote work specifically for B2B managers

### Quality Comparison Summary

The optimized version scored higher because it converted a broad writing request into a constrained editorial assignment. The output became more targeted, structured, concise, and closer to the requested reference style.

**Score:** `14/20 → 20/20`

---

# 2. LinkedIn Post

## Before — Naive

**Prompt:**

> Write a LinkedIn post about learning prompt engineering.

**Response:**
The response created a professional LinkedIn post discussing learning prompt engineering, including structured instructions, context, examples, constraints, iteration, coding, research, documentation, and productivity.

### Objective

Create a professional LinkedIn post about learning prompt engineering.

### The Issue with 'Before' Prompt

The prompt did not specify:

* Maximum word count
* Number of emojis
* Hook structure
* Audience
* Exact LinkedIn formatting
* Hashtag requirements
* Desired personal tone

The resulting post was appropriate for LinkedIn but could have been more tightly controlled.

### The 'After' Strategy

The optimized prompt introduced explicit constraints:

* **Role:** Social Media Copywriter specializing in tech careers
* **Platform:** LinkedIn
* **Topic:** Learning Prompt Engineering
* **Length:** under 150 words
* **Emoji limit:** maximum 2
* **Hook:** exactly one sentence

This demonstrates **constraint-based prompting**.

### Quality Comparison Summary

The optimized output was shorter, more focused, and more suitable for LinkedIn. The explicit word and emoji limits also prevented unnecessary expansion.

**Score:** `16/20 → 20/20`

---

# 3. Email Campaign

## Before — Naive

**Prompt:**

> Write a B2B sales email promoting our new Water Bottle.

**Response:**
The email introduced the Bileri Water Bottle and highlighted durability, leak resistance, portability, reusable construction, and custom branding.

### Objective

Create a B2B sales email promoting a Water Bottle from Bileri.

### The Issue with 'Before' Prompt

The basic request did not specify:

* Subject-line format
* Email structure
* CTA placement
* Feature formatting
* Sales tone
* Company positioning
* Required template

The response therefore produced a reasonable sales email but without the precise structure required for a conversion-focused campaign.

### The 'After' Strategy

The optimized prompt used:

* **Role prompting:** B2B sales copywriter
* **Reference structure:** high-converting email template
* **Product variable:** Water Bottle
* **Company variable:** Bileri
* **Formatting constraint:** features as bullets
* **Subject constraint:** bold + Pascal Case
* **CTA placement:** explicit reply-based CTA

This is an example of **template-guided prompting + explicit output constraints**.

### Quality Comparison Summary

The optimized email better matched a professional B2B sales workflow. It contained a clear introduction, feature section, and action-oriented closing rather than simply describing the product.

**Score:** `13/20 → 20/20`

---

# 4. Instagram Caption

## Before — Naive

**Prompt:**

> Write an Instagram caption for a picture of a coffee cup.

**Response:**
The response created a short caption around coffee, peace, and slowing down, followed by hashtags.

### Objective

Create a short Instagram caption for a coffee picture.

### The Issue with 'Before' Prompt

The prompt gave no specific:

* Emotional tone
* Emoji limit
* Hashtag limit
* Hashtag grouping requirement
* Creative direction

The output was suitable, but the creative requirements were largely left to the model.

### The 'After' Strategy

The optimized prompt specified:

* **Role:** Content creator
* **Platform:** Instagram
* **Tone:** warm and joyful
* **Emoji constraint:** maximum 2
* **Hashtag constraint:** maximum 3 grouped hashtags
* **Creative references:** examples such as “but first: coffee”

This is **example-based prompting + constraint prompting**.

### Quality Comparison Summary

The optimized version followed the requested social-media style more precisely. The tone, emoji usage, and hashtag structure were explicitly controlled.

**Score:** `16/20 → 20/20`

---

# 5. YouTube Script

## Before — Naive

**Prompt:**

> Write a YouTube video script about how to start a business.

**Response:**
The response created a 5–7 minute script covering finding a problem, understanding customers, researching competitors, starting small, creating a business plan, finding customers, and improving the business.

### Objective

Create a YouTube script explaining how beginners can start a business.

### The Issue with 'Before' Prompt

The prompt did not specify:

* Audience retention strategy
* Opening hook
* Visual instructions
* Camera directions
* CTA
* Voice style
* Output structure
* Length

The resulting script was informative but followed a fairly conventional educational-video structure.

### The 'After' Strategy

The optimized prompt introduced multiple control mechanisms:

* **Expert role:** professional YouTube creator
* **Retention requirement:** hook within the first 5 seconds
* **Visual grounding:** visual suggestions in brackets
* **Interactive CTA:** like/subscribe and comment engagement
* **Human-like language:** no generic keywords
* **Strict output structure:** two-column Markdown
* **Left column:** visual/camera cue
* **Right column:** spoken voiceover

This combines **role prompting, structural prompting, constraint prompting, and audience-retention prompting**.

### Quality Comparison Summary

The optimized script was significantly more production-ready because it separated the visual direction from the spoken script. It also gave the opening and CTA explicit jobs rather than leaving them implicit.

**Score:** `14/20 → 20/20`

---

# 6. Product Description

## Before — Naive

**Prompt:**

> Write a product description for a wireless mouse.

**Response:**
The response produced a general description covering wireless connectivity, precise tracking, ergonomic design, power efficiency, compatibility, and portability.

### Objective

Create a product description for a wireless mouse.

### The Issue with 'Before' Prompt

The prompt did not identify:

* Brand
* Exact product
* Technical specifications
* Target customer
* Required formatting
* Product-specific differentiators
* Number or structure of features

The response consequently relied on generic wireless-mouse characteristics.

### The 'After' Strategy

The optimized prompt provided detailed product information:

* **Brand:** Wolf
* **Product:** Wolf Pureview Transparent Mouse
* **Technical specifications:** battery, DPI, connectivity, dimensions, weight, compatibility, etc.
* **Required feature format:** bullets
* **Maximum emoji limit:** 3
* **Reference writing style:** supplied sample
* **Output format:** requested Markdown format

This is **data-grounded prompting + style transfer + structured output constraints**.

### Quality Comparison Summary

This produced the largest improvement in product specificity. Instead of generic mouse benefits, the optimized version incorporated the actual product's technical specifications and differentiators.

**Score:** `15/20 → 20/20`

---

# Prompt Engineering Techniques Used Across the Six Tasks

| Technique                    | How It Was Used                                                                                                   |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| **Role Prompting**           | Defined the model as a blog writer, social media copywriter, B2B copywriter, content creator, or YouTube creator. |
| **Audience Targeting**       | Narrowed broad topics toward B2B managers, tech-career audiences, or B2B buyers.                                  |
| **Constraint Prompting**     | Added word counts, emoji limits, hashtag limits, formatting rules, and structural requirements.                   |
| **Style Transfer**           | Supplied reference text to guide vocabulary, rhythm, tone, and sentence structure.                                |
| **Example-Based Prompting**  | Provided sample captions, email structures, and product descriptions.                                             |
| **Template Prompting**       | Used a predefined sales-email structure instead of asking for an unconstrained email.                             |
| **Structured Output**        | Required H1/H2 sections, bullet points, Markdown tables, and split-column layouts.                                |
| **Variable-Based Prompting** | Used variables such as `[topic]`, `[product]`, `[features]`, and `[Company]`.                                     |
| **Platform Optimization**    | Tailored content specifically for LinkedIn, Instagram, YouTube, blogs, and B2B email.                             |
| **Audience Retention**       | Added a 5-second hook and interactive CTA to the YouTube prompt.                                                  |
| **Technical Grounding**      | Supplied exact product specifications rather than relying on generic product assumptions.                         |

---

# Final Assessment

The comparison shows a clear progression:

**Naive Prompt → General Instruction → Optimized Prompt → Controlled Output**

The biggest improvement came from replacing simple commands such as:

> “Write a blog post.”

with instructions that define **who is writing, who is reading, what should be said, how it should sound, how long it should be, and exactly how it should be formatted.**

The optimized prompts therefore produced outputs that were more **specific, predictable, platform-appropriate, and ready to use**.

### Overall Result

* **Before:** 88/120 — **73.3%**
* **After:** 120/120 — **100%**
* **Overall improvement:** **32 points / 26.7 percentage points**

The main lesson is that **prompt engineering is not simply about making prompts longer**. The strongest improvement came from adding the *right constraints*: role, audience, context, examples, style, structure, and measurable output requirements.
