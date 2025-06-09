**AI News Aggregation Prompt**  
*Date Range:* [Specify: Today/Yesterday/Last 7 Days]  
*Source Credibility Threshold:* [Minimum 3 independent reputable outlets]  
*Regional Focus:* [Global/North America/Europe/Asia-Pacific]  

**Core Instructions:**  
1. **News Collection Phase**  
   - Scrape all AI-related articles from:  
     - Technical journals (ArXiv, IEEE, Nature Machine Intelligence)  
     - Financial reports (Bloomberg, Reuters, Crunchbase)  
     - General media (Associated Press, BBC, The Verge)  
   - Apply real-time fact-checking via cross-referencing using:  
     - **Claim Verification Matrix:**  
       ```
       if (source_count ≥ 5): Reliability = High  
       elif (3 ≤ source_count <5): Reliability = Medium  
       else: Flag for manual review  
       ```  
   - Exclude rumors lacking named sources or peer-reviewed citations  

2. **Multi-Dimensional Classification System**  
   - **Technical Developments** (60% weight):  
     - Subcategories:  
       - NLP breakthroughs (transformer architectures >1B params)  
       - Computer vision (SOTA on ImageNet/COCO)  
       - Reinforcement learning (novel environments)  
   - **Financial Impact** (30% weight):  
     - Funding rounds >$10M  
     - IPO filings  
     - Market analysis (Gartner/IDC forecasts)  
   - **Societal Discourse** (10% weight):  
     - Policy changes (EU AI Act updates)  
     - Ethical debates (AI alignment papers)  
     - Cultural impacts (AI in art/music)  

3. **Research Integration Protocol**  
   - Harvest preprints from arXiv/PubMed with:  
     - `cv.CL` (Computation and Language)  
     - `cs.AI` (Artificial Intelligence)  
     - `cs.LG` (Machine Learning)  
   - Apply novelty scoring:  
     $$ \text{Novelty} = \frac{\text{New citations}}{\text{Days since publication}} $$  

**Output Structure:**  
### Technical Developments  
- [Reliability Score] [Headline]  
  - Key innovation: [Architecture/method]  
  - Benchmark improvement: [% vs previous SOTA]  
  - Research team: [Institution/collaborators]  

### Financial Pulse  
- [Sector] [Company] raised $[Amount] at [Valuation]  
  - Lead investors: [VC firms]  
  - Use of funds: [R&D/% breakdown]  

### Societal Impact  
- [Country/Region] proposed [Policy Name]  
  - Key provisions: [Testing requirements]  
  - Industry response: [Company statements]  

### Emerging Research (Last 24h)  
1. [Paper Title]  
   - Authors: [University]  
   - Contribution: [New technique]  
   - Early citations: [Number]  
