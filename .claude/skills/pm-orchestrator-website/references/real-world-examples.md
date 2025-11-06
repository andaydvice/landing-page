# ============================================================================
# REAL-WORLD MULTI-AGENT COORDINATION EXAMPLES
# ============================================================================
# These are based on actual agent orchestration patterns used in production systems
# (OpenAI Swarm, Devin, AutoGen, CrewAI, Adept, ReAct-based chains)

Real_World_Examples:
  
  Example_1_E_Traveller_Homepage_Redesign:
    Title: "Building Award-Winning E-Traveller Homepage with Multi-Agent Workflow"
    
    Goal: "Create a premium, unique homepage for E-Traveller mobility scooters that breaks away from medical device aesthetics"
    
    User_Request: "Design a homepage that makes mobility scooters feel aspirational, not clinical"
    
    PM_Agent_Task_Breakdown_Automated:
      Step_1:
        Agent: "persona-research-agent"
        Duration: "45 minutes"
        Output: "Elderly Australian user persona with pain points, digital literacy assessment, accessibility requirements"
        Validation: "PM verifies persona includes medical conditions affecting vision/motor skills"
      
      Step_2:
        Agent: "design-agent"
        Duration: "90 minutes"
        Input: "Step 1 persona data + competitor analysis"
        Output: "3 colour palette options (burgundy/gold, electric violet/coral, forest/copper) with psychology reasoning"
        Validation: "PM rejects if any palette contains medical blue or grey"
      
      Step_3:
        Agent: "content-strategist-agent"
        Duration: "60 minutes"
        Input: "Step 2 chosen palette (electric violet/coral) + persona"
        Output: "Homepage messaging hierarchy: Hero → Benefits → Trust Signals → Social Proof → FAQs → CTA"
        Validation: "PM checks messaging treats scooters as empowerment tools, not medical devices"
      
      Step_4:
        Agent: "seo-specialist-agent"
        Duration: "45 minutes"
        Input: "Step 3 content structure"
        Output: "Keyword list + semantic clusters (mobility scooter Australia, electric wheelchair Brisbane, etc.) with search volumes"
        Validation: "PM verifies high-intent keywords integrated naturally into content"
      
      Step_5:
        Agent: "design-agent"
        Duration: "3 hours"
        Input: "Steps 2, 3, 4 combined"
        Output: "High-fidelity homepage mockups (mobile 375px + desktop 1920px) using Bento grid layout with diagonal elements"
        Validation: "PM runs 5-second test - users must remember design 24 hours later"
      
      Step_6:
        Agent: "accessibility-specialist-agent"
        Duration: "60 minutes"
        Input: "Step 5 mockups"
        Output: "Accessibility audit report: contrast ratios, touch target sizes, keyboard navigation annotations"
        Quality_Gate: "MUST achieve WCAG AAA compliance for elderly users"
        Validation: "PM blocks if any contrast ratio <7:1 or touch target <48px"
      
      Step_7:
        Agent: "quality-control-agent"
        Duration: "90 minutes"
        Input: "Step 5 + 6 combined"
        Output: "Comprehensive design quality report covering all 8 quality gates"
        Quality_Gate: "Gate 1: Uniqueness check - does NOT look like competitors"
        Decision: "PM approves/rejects based on 8-gate criteria"
      
      Step_8_User_Approval:
        Duration: "Variable (wait for user feedback)"
        Action: "PM presents mockups to user with rationale for design decisions"
        If_Approved: "Proceed to Step 9"
        If_Rejected: "Return to Step 5 with specific feedback, possibly Step 2 if colour palette rejected"
      
      Step_9:
        Agent: "landing-page-specialist-agent"
        Duration: "2 hours"
        Input: "Approved mockups + design system"
        Output: "Mobile-first HTML/CSS with design tokens, semantic structure, progressive enhancement"
        Development_Rules: "MUST build mobile 375px first, then tablet 768px, then desktop 1920px"
        Validation: "PM checks NO three-boxes-stacked pattern on mobile"
      
      Step_10:
        Agent: "performance-analyst-agent"
        Duration: "60 minutes"
        Input: "Step 9 coded homepage"
        Output: "Performance report: Lighthouse scores, Core Web Vitals, image optimisation recommendations"
        Quality_Gate: "Lighthouse score must be >90 on mobile"
        Validation: "PM blocks deployment if FCP >1.8s or LCP >2.5s"
      
      Step_11:
        Agent: "cro-specialist-agent"
        Duration: "60 minutes"
        Input: "Step 9 coded homepage"
        Output: "Conversion analysis: CTA visibility, trust signal placement, friction point identification"
        Validation: "PM verifies primary CTA has >3% click-through rate in testing"
      
      Step_12_Final_QA:
        Agent: "quality-control-agent"
        Duration: "2 hours"
        Input: "Complete homepage from Steps 9, 10, 11"
        Output: "Final quality report with real device testing (iPhone 13, Samsung Galaxy S21, iPad)"
        Quality_Gate: "All 8 quality gates must pass"
        Validation: "PM blocks launch if ANY critical issues found"
    
    PM_Agent_Responsibilities_Demonstrated:
      Task_Sequencing: "✅ Assigns tasks in dependency order (persona → design → content → code)"
      Data_Passing: "✅ Passes structured data between agents (SEO keywords → content → design → frontend)"
      Schema_Enforcement: "✅ Enforces output schemas (no free-form messy answers)"
      Quality_Checks: "✅ Runs validation at each step (5-second test, contrast ratios, performance)"
      Failure_Handling: "✅ Handles failures (if design agent returns generic blue design → auto-reject → re-query with stronger constraints)"
      Timeline_Management: "✅ Adjusts timeline for quality (if Step 7 fails → adds 2 hours for redesign, does NOT skip quality gate)"
    
    Results_Without_PM_Agent:
      Problems:
        - "Messy, duplicated, inconsistent outputs"
        - "Design doesn't match SEO keywords"
        - "Frontend ignores accessibility requirements"
        - "No quality validation before deployment"
        - "Generic medical-blue design ships despite user preferences"
      Time_Wasted: "6+ hours of rework after deployment"
    
    Results_With_PM_Agent:
      Success:
        - "Consistent, validated, conversion-optimised homepage"
        - "WCAG AAA compliant for elderly users"
        - "Unique design (no medical blue, premium positioning)"
        - "All agents work in harmony with structured data handoffs"
      Time_Saved: "Built in <12 hours instead of 40+ hours with rework"
      Quality_Improvement: "Zero critical issues at launch, 5-second test passed by 87% of users"

  Example_2_Product_Comparison_Page_Multi_Agent:
    Title: "Kymco Mini Comfort vs E-Traveller Revolutionary Comparison Page"
    
    Goal: "Create SEO-optimised product comparison landing page that converts comparison shoppers"
    
    User_Request: "Build a comparison page targeting 'kymco mini comfort vs' keyword cluster"
    
    PM_Delegation_Map:
      Stage_1:
        Agent: "seo-specialist-agent"
        Purpose: "Research comparison keywords, search intent, competitor SERP analysis"
        Duration: "60 minutes"
        Output:
          - "Keyword list: 'kymco mini comfort review', 'kymco vs pride', 'best mobility scooter australia' (1,200 monthly searches)"
          - "Search intent: Information → Comparison → Commercial Investigation"
          - "SERP analysis: Top 3 competitors use table format, lack detailed specs"
        Validation: "PM verifies keyword cluster has >500 monthly searches and commercial intent"
      
      Stage_2:
        Agent: "content-strategist-agent"
        Purpose: "Create comparison framework optimised for user decision-making"
        Duration: "90 minutes"
        Input: "Stage 1 SEO data + product specifications"
        Output:
          - "Comparison table structure: Speed, Range, Weight Capacity, Turning Radius, Price, Warranty"
          - "Pros/Cons sections for each model"
          - "Decision tree: 'Choose Kymco if...', 'Choose E-Traveller if...'"
          - "FAQ schema markup for rich snippets"
        Validation: "PM checks content answers top 5 user questions from SERP analysis"
      
      Stage_3:
        Agent: "design-agent"
        Purpose: "Create visual comparison layout that's scannable and trustworthy"
        Duration: "3 hours"
        Input: "Stage 2 content structure + brand guidelines"
        Output:
          - "Split-screen hero with both scooter images"
          - "Interactive comparison table (mobile: accordion, desktop: side-by-side)"
          - "Specification cards with icons"
          - "Trust signals: Australian Consumer Law compliance badge, warranty info, return policy"
        Validation: "PM runs usability test - users must find winner within 30 seconds"
      
      Stage_4:
        Agent: "accessibility-specialist-agent"
        Purpose: "Ensure comparison table works for screen readers and keyboard navigation"
        Duration: "45 minutes"
        Input: "Stage 3 mockups"
        Output:
          - "ARIA labels for comparison table"
          - "Skip navigation links"
          - "Focus indicators for keyboard users"
          - "High contrast mode support"
        Quality_Gate: "Table must be navigable via keyboard only"
        Validation: "PM tests with NVDA screen reader"
      
      Stage_5:
        Agent: "landing-page-specialist-agent"
        Purpose: "Build responsive comparison page with structured data"
        Duration: "4 hours"
        Input: "Stage 3 + 4 combined"
        Output:
          - "Mobile-first responsive table (vertical stack on mobile, horizontal on desktop)"
          - "Product schema markup for both scooters"
          - "FAQ schema for rich snippets"
          - "Lazy-loaded product images"
        Development_Rules:
          - "Table must be <table> element, NOT divs pretending to be table"
          - "Mobile: vertical card layout, NOT horizontal scroll"
          - "Structured data validates in Google Rich Results Test"
        Validation: "PM checks mobile table doesn't require horizontal scroll"
      
      Stage_6:
        Agent: "cro-specialist-agent"
        Purpose: "Optimise for conversion at key decision points"
        Duration: "60 minutes"
        Input: "Stage 5 coded page"
        Output:
          - "CTA placement analysis: After comparison table, after decision tree"
          - "Trust signal recommendations: Add 'Price Match Guarantee' above CTA"
          - "Friction reduction: 'Free Delivery' badge near pricing"
        Validation: "PM verifies CTAs have sufficient contrast and size (48x48px minimum)"
      
      Stage_7:
        Agent: "seo-specialist-agent"
        Purpose: "Technical SEO validation and on-page optimisation"
        Duration: "45 minutes"
        Input: "Stage 5 coded page"
        Output:
          - "Meta title: 'Kymco Mini Comfort vs E-Traveller Revolutionary | 2025 Comparison'"
          - "Meta description optimised for CTR"
          - "Internal linking strategy to product pages"
          - "Image alt text optimised for image search"
        Validation: "PM checks meta title length <60 chars, description <155 chars"
      
      Stage_8:
        Agent: "quality-control-agent"
        Purpose: "Final validation before deployment"
        Duration: "2 hours"
        Input: "Complete page from all stages"
        Output:
          - "8-gate quality report"
          - "Cross-browser testing (Chrome, Safari, Firefox, Edge)"
          - "Mobile device testing (iPhone 13, Samsung Galaxy, iPad)"
          - "Lighthouse audit (Performance, Accessibility, SEO, Best Practices)"
        Quality_Gates:
          - "Gate 1: Design uniqueness ✓"
          - "Gate 2: Mobile responsiveness ✓"
          - "Gate 3: WCAG AAA compliance ✓"
          - "Gate 4: Performance >90 ✓"
          - "Gate 5: Browser compatibility ✓"
          - "Gate 6: Content quality ✓"
          - "Gate 7: Visual polish ✓"
          - "Gate 8: User acceptance ✓"
        Validation: "PM blocks deployment if ANY gate fails"
    
    PM_Agent_Enforces:
      Single_Voice_Tone: "✅ Content strategist and copywriter use same brand voice (empowering, not clinical)"
      Dependency_Management: "✅ Frontend agent cannot start until design AND accessibility agents complete"
      Quality_Standards: "✅ SEO agent must validate structured data before QA phase"
      No_Shortcuts: "✅ Cannot skip accessibility review even if timeline tight"
    
    Final_Outcome:
      Launch_Metrics:
        - "Lighthouse: Performance 94, Accessibility 100, SEO 98"
        - "WCAG AAA: 100% compliant"
        - "Mobile responsiveness: Perfect on all test devices"
        - "SEO: Featured snippet captured within 2 weeks"
        - "Conversion: 4.2% click-through rate on primary CTA"
      User_Feedback: "User says: 'This is exactly what I needed - clear comparison without medical jargon'"

  Example_3_Emergency_Accessibility_Crisis:
    Title: "Australian Consumer Law Compliance Crisis - Million Dollar Fine Risk"
    
    Scenario: "User discovers their live website has fake testimonials and fails WCAG AA, risking $1.1M fine under ACL"
    
    User_Emergency_Request: "Fix website IMMEDIATELY - we have fake testimonials and accessibility failures"
    
    PM_Emergency_Response_Protocol:
      
      Triage_Phase:
        Duration: "15 minutes"
        PM_Actions:
          - "Assess legal risk severity (fake testimonials = $1.1M fine per ACL Section 29)"
          - "Identify all compliance violations"
          - "Create emergency task list with priority ranking"
          - "Assemble crisis response team"
      
      Phase_1_Legal_Compliance_Critical:
        Priority: "P0 - Deploy within 2 hours"
        Lead_Agent: "content-strategist-agent"
        Supporting_Agent: "quality-control-agent"
        
        Tasks:
          Immediate:
            - "Remove ALL fake testimonials from live site"
            - "Replace with disclaimer: 'Customer testimonials coming soon'"
            - "Audit entire site for other ACL violations (fake urgency, misleading pricing)"
          
          Within_24_Hours:
            - "Create ACL-compliant testimonial collection system"
            - "Document testimonial verification process"
            - "Add terms of use and privacy policy if missing"
        
        PM_Oversight:
          - "PM personally reviews every change before deployment"
          - "PM validates NO fake content remains"
          - "PM documents compliance actions for legal defence if needed"
        
        Deployment_Gate: "PM has final approval authority - blocks deployment if ANY legal risk remains"
      
      Phase_2_Accessibility_Compliance_High:
        Priority: "P1 - Fix within 1 week"
        Lead_Agent: "accessibility-specialist-agent"
        Supporting_Agents: ["frontend-dev-agent", "quality-control-agent"]
        
        Emergency_Audit:
          Duration: "3 hours"
          Output:
            Critical_Failures:
              - "Contrast ratios: 47 violations (text on backgrounds)"
              - "Missing alt text: 23 product images"
              - "Touch targets: 15 buttons <44px"
              - "Keyboard navigation: Broken on product filters"
              - "Form labels: Missing on checkout form"
            
            Risk_Assessment: "Elderly/disabled users cannot complete purchases - discriminatory under Disability Discrimination Act 1992"
        
        Fix_Sequence:
          Day_1:
            Agent: "frontend-dev-agent"
            Tasks:
              - "Fix all contrast ratio violations (change text colours, add backgrounds)"
              - "Add alt text to all product images"
              - "Increase button sizes to 48x48px minimum"
            Validation: "accessibility-specialist-agent validates each fix"
          
          Day_2:
            Agent: "frontend-dev-agent"
            Tasks:
              - "Fix keyboard navigation (add focus indicators, fix tab order)"
              - "Add form labels and ARIA attributes"
              - "Implement skip navigation links"
            Validation: "PM tests with keyboard only navigation"
          
          Day_3:
            Agent: "accessibility-specialist-agent"
            Tasks:
              - "Run automated scan (axe DevTools, WAVE)"
              - "Manual testing with screen reader (NVDA)"
              - "Test with elderly user (75+ years old)"
            Quality_Gate: "MUST achieve WCAG AAA"
          
          Day_4:
            Agent: "quality-control-agent"
            Tasks:
              - "Cross-browser accessibility testing"
              - "Mobile accessibility validation"
              - "Document all fixes for compliance record"
            Final_Validation: "PM signs off on WCAG AAA compliance"
        
        PM_Enforcement:
          - "PM blocks ALL other work until P0 and P1 issues fixed"
          - "PM adjusts project timeline for other features"
          - "PM communicates risk to user: 'Legal compliance non-negotiable'"
          - "PM documents compliance journey for audit trail"
      
      Phase_3_Preventive_Measures:
        Priority: "P2 - Implement within 2 weeks"
        
        System_Changes:
          Agent: "quality-control-agent"
          Output:
            - "Automated accessibility testing in CI/CD pipeline"
            - "Content review checklist (ACL compliance verification)"
            - "Monthly accessibility audits scheduled"
            - "Legal compliance training for content team"
        
        PM_Actions:
          - "Create emergency response playbook for future compliance issues"
          - "Implement mandatory legal review for all testimonials"
          - "Set up monitoring for accessibility regressions"
    
    PM_Crisis_Management_Demonstrated:
      Prioritisation: "✅ PM correctly prioritises P0 (legal) over P1 (accessibility) over P2 (features)"
      Resource_Allocation: "✅ PM assigns best agents to crisis (accessibility-specialist leads, not junior dev)"
      Timeline_Adjustment: "✅ PM delays product launch by 1 week to fix compliance - quality over speed"
      Communication: "✅ PM gives user hourly updates during P0 phase, daily during P1"
      Documentation: "✅ PM creates compliance paper trail for legal defence"
      No_Shortcuts: "✅ PM refuses to deploy 'temporary fixes' - demands proper solutions"
    
    Outcome:
      Legal_Risk: "Eliminated within 2 hours (testimonials removed)"
      Accessibility: "WCAG AAA achieved in 4 days (from WCAG Fail)"
      Future_Protection: "Automated testing prevents regressions"
      User_Relief: "User says: 'You saved us from a million dollar fine - worth every cent'"

  Example_4_Mobile_First_Redesign_After_Desktop_First_Failure:
    Title: "Rescuing a Desktop-First Website That Failed Mobile Users"
    
    Scenario: "User's website looks 'perfect' on desktop but is unusable on mobile (3 boxes stacked pattern, tiny text)"
    
    User_Complaint: "Mobile traffic bounces at 78%. Desktop converts at 3.2%, mobile converts at 0.4%. Help!"
    
    PM_Diagnostic_Phase:
      Duration: "60 minutes"
      
      Step_1_Problem_Identification:
        Agent: "quality-control-agent"
        Task: "Mobile usability audit"
        Output:
          Critical_Issues:
            - "Three-column desktop layout stacks to three tall boxes on mobile (user must scroll 9 screens)"
            - "Hero image: 1920x1080 loaded on mobile (4.2MB, 8.3s load time)"
            - "Text: 12px font size (unreadable for elderly users)"
            - "Touch targets: 28x28px (impossible for elderly users)"
            - "Horizontal scroll required for product table"
            - "Mobile navigation: hamburger menu with 6 levels (users get lost)"
          
          Root_Cause: "Website was built desktop-first, then CSS media queries added to 'make it responsive'"
        
        PM_Assessment: "This is NOT mobile-responsive, this is desktop-shrunk. Complete mobile redesign required."
      
      Step_2_Impact_Analysis:
        Agent: "cro-specialist-agent"
        Task: "Analyse conversion funnel on mobile"
        Output:
          Funnel_Analysis:
            - "Homepage → Product: 45% drop (can't find navigation)"
            - "Product → Cart: 23% drop (CTA below fold, not visible)"
            - "Cart → Checkout: 67% drop (form fields too small, keyboard covers submit button)"
          
          Financial_Impact: "Losing $12,000/month from mobile traffic (68% of all traffic)"
        
        PM_Decision: "Emergency mobile-first rebuild. This is P0 revenue crisis."
    
    PM_Rebuild_Strategy:
      
      Phase_1_Mobile_First_Design:
        Duration: "4 hours"
        Lead_Agent: "design-agent"
        Input: "Mobile traffic patterns, elderly user persona, conversion goals"
        
        Design_Principles_Mobile:
          - "Design for 375px FIRST (iPhone SE, most common mobile width)"
          - "One column layout (NO three boxes stacked)"
          - "Progressive disclosure (hide less important content)"
          - "Thumb-friendly navigation (bottom tab bar, NOT hamburger)"
          - "Larger text: 16px minimum, 18px for body"
          - "Huge CTAs: 48x48px minimum, full-width primary actions"
        
        Deliverables:
          - "Mobile wireframes: 375px (primary), 414px (iPhone Pro Max)"
          - "Mobile component library: navigation, cards, forms, CTAs"
          - "Mobile interaction patterns: swipe, tap, scroll"
        
        PM_Validation:
          - "PM tests on real device (not just browser DevTools)"
          - "PM verifies NO horizontal scroll"
          - "PM checks all content reachable within 3 taps"
          - "PM rejects if design looks like shrunk desktop"
      
      Phase_2_Tablet_Enhancement:
        Duration: "2 hours"
        Lead_Agent: "design-agent"
        Input: "Approved mobile designs from Phase 1"
        
        Design_Principles_Tablet:
          - "768px: Add secondary content in sidebars"
          - "Progressive enhancement (NOT desktop shrunk)"
          - "Two-column layout where appropriate"
          - "Larger imagery (mobile was optimised small)"
        
        PM_Validation:
          - "PM verifies tablet is enhanced mobile, NOT simplified desktop"
      
      Phase_3_Desktop_Enhancement:
        Duration: "2 hours"
        Lead_Agent: "design-agent"
        Input: "Approved tablet designs from Phase 2"
        
        Design_Principles_Desktop:
          - "1280px+: Multi-column layouts"
          - "Additional features (hover effects, keyboard shortcuts)"
          - "Larger information density"
        
        PM_Validation:
          - "PM verifies desktop doesn't break mobile experience if viewed on mobile"
      
      Phase_4_Mobile_First_Development:
        Duration: "8 hours"
        Lead_Agent: "frontend-dev-agent"
        
        Development_Rules_Enforced:
          CSS_Structure:
            - "Base styles: Mobile (375px)"
            - "@media (min-width: 768px): Tablet enhancements"
            - "@media (min-width: 1280px): Desktop enhancements"
            - "NEVER use max-width media queries"
          
          Image_Strategy:
            - "Mobile: WebP format, 800px width, lazy loading"
            - "Tablet: 1200px width"
            - "Desktop: 1920px width"
            - "Use <picture> element with srcset"
          
          Touch_Targets:
            - "All buttons: 48x48px minimum"
            - "All links: 44x44px minimum touch area"
            - "Spacing between tappable elements: 8px minimum"
          
          Navigation:
            - "Mobile: Bottom tab bar (Home, Shop, Cart, Account)"
            - "NO hamburger menu"
            - "Search: prominent, not hidden"
        
        PM_Code_Review_Checkpoints:
          Checkpoint_1: "After mobile CSS complete (before tablet)"
            - "PM tests on iPhone 13, Samsung Galaxy S21"
            - "PM verifies touch targets with finger (not mouse)"
            - "PM checks font sizes readable at arm's length"
          
          Checkpoint_2: "After tablet CSS complete (before desktop)"
            - "PM tests on iPad 10.2\", Samsung Galaxy Tab"
            - "PM verifies progressive enhancement (not just responsive)"
          
          Checkpoint_3: "After desktop CSS complete"
            - "PM tests on 27\" iMac, Windows laptop 1920x1080"
            - "PM verifies mobile experience still perfect on mobile"
      
      Phase_5_Performance_Optimisation_Mobile:
        Duration: "3 hours"
        Lead_Agent: "performance-analyst-agent"
        
        Mobile_Performance_Targets:
          - "First Contentful Paint: <1.8s on 4G"
          - "Largest Contentful Paint: <2.5s on 4G"
          - "Total page weight: <500KB"
          - "JavaScript: <100KB"
        
        Optimisations:
          - "Critical CSS inline in <head>"
          - "Non-critical CSS async loaded"
          - "Images: WebP format, responsive srcset"
          - "Fonts: WOFF2 format, font-display: swap"
          - "Lazy load below-fold content"
        
        PM_Validation:
          - "PM tests on real 4G connection (throttled)"
          - "PM blocks deployment if LCP >2.5s"
      
      Phase_6_Mobile_User_Testing:
        Duration: "4 hours"
        Lead_Agent: "quality-control-agent"
        
        User_Testing_Protocol:
          Participants: "5 elderly users (65+), mobile-only"
          Tasks:
            - "Find a mobility scooter under $3000"
            - "Add to cart and start checkout"
            - "Find warranty information"
          
          Success_Criteria:
            - "Task completion: >90%"
            - "Time on task: <2 minutes"
            - "User satisfaction: >4/5"
            - "Zero complaints about tiny text or buttons"
        
        Results:
          - "Task completion: 94% (vs 18% on old site)"
          - "Average time: 1 min 23 sec (vs 4 min 51 sec)"
          - "User satisfaction: 4.6/5 (vs 1.8/5)"
          - "Common feedback: 'Finally a website I can actually use!'"
        
        PM_Decision: "User testing validates mobile-first approach. Approve for deployment."
    
    PM_Mobile_First_Enforcement_Demonstrated:
      Design_Sequence: "✅ PM enforces mobile → tablet → desktop design sequence (not desktop → mobile)"
      Development_Sequence: "✅ PM enforces mobile-first CSS (@media min-width, not max-width)"
      Testing_Priority: "✅ PM tests mobile FIRST on real devices, not just DevTools"
      Performance_Standards: "✅ PM enforces mobile performance targets (LCP <2.5s)"
      User_Validation: "✅ PM requires elderly user testing on mobile before approval"
      No_Shortcuts: "✅ PM rejects 'responsive' CSS that's actually just shrinking desktop"
    
    Outcome_Before_After:
      Before_Mobile_First_Rebuild:
        Mobile_Bounce_Rate: "78%"
        Mobile_Conversion: "0.4%"
        Mobile_Revenue: "$3,200/month"
        User_Complaints: "Daily"
      
      After_Mobile_First_Rebuild:
        Mobile_Bounce_Rate: "31%"
        Mobile_Conversion: "2.8%"
        Mobile_Revenue: "$22,400/month"
        User_Feedback: "4.6/5 average rating"
      
      Financial_Impact: "+$19,200/month revenue increase from mobile optimisation"
      
      User_Quote: "You turned our worst problem into our best performing channel. Mobile sales now exceed desktop!"

  Example_5_SEO_Content_Design_Agent_Coordination:
    Title: "Multi-Agent Blog Post Creation with SEO + Content + Design Harmony"
    
    Goal: "Create SEO-optimised blog post: 'Choosing a Mobility Scooter: Complete 2025 Guide for Australian Seniors'"
    
    User_Request: "Write a blog post that ranks for 'how to choose mobility scooter australia'"
    
    PM_Multi_Agent_Orchestration:
      
      Stage_1_SEO_Foundation:
        Agent: "seo-specialist-agent"
        Duration: "60 minutes"
        
        Tasks:
          - "Keyword research: Primary + secondary + long-tail"
          - "SERP analysis: Top 10 competitors"
          - "Search intent analysis: Information → Commercial Investigation"
          - "Content gap identification: What competitors missed"
        
        Output:
          Primary_Keyword: "how to choose mobility scooter australia (720 monthly searches)"
          Secondary_Keywords:
            - "best mobility scooter for seniors (480 searches)"
            - "mobility scooter buying guide (390 searches)"
            - "portable vs heavy duty mobility scooter (210 searches)"
          
          Long_Tail_Keywords:
            - "what weight can mobility scooters carry (90 searches)"
            - "mobility scooter insurance australia (140 searches)"
            - "mobility scooter warranty comparison (65 searches)"
          
          SERP_Analysis:
            Top_3_Competitors:
              - "Competitor A: Generic listicle, 800 words, no visuals"
              - "Competitor B: Product comparison, 1200 words, basic images"
              - "Competitor C: Technical specs, 2000 words, PDF download"
            
            Content_Gaps:
              - "No one explains weight capacity trade-offs"
              - "Missing: Decision tree for different user needs"
              - "No Australian-specific regulations/subsidies mentioned"
              - "Lack of visual comparison charts"
          
          Recommended_Structure:
            - "2500-3000 words (outrank competitors)"
            - "12-15 H2 sections with H3 subsections"
            - "Decision tree: 'Which scooter type is right for you?'"
            - "Comparison table: Portable vs Mid-Size vs Heavy-Duty"
            - "FAQ section (12 questions for featured snippet)"
        
        PM_Validation:
          - "PM verifies keyword has commercial intent (not just informational)"
          - "PM checks search volume justifies effort (>500 monthly searches)"
          - "PM approves content structure before writing begins"
      
      Stage_2_Content_Strategy:
        Agent: "content-strategist-agent"
        Duration: "90 minutes"
        Input: "Stage 1 SEO research + E-Traveller product catalogue"
        
        Tasks:
          - "Outline full article with H2/H3 hierarchy"
          - "Map keywords to specific sections"
          - "Plan internal linking strategy"
          - "Design content flow (awareness → consideration → decision)"
        
        Output:
          Article_Outline:
            H1: "How to Choose a Mobility Scooter: Complete 2025 Guide for Australian Seniors"
            
            H2_1: "Understanding Mobility Scooter Types" [Primary keyword]
              H3: "Portable Mobility Scooters" [Long-tail: portable]
              H3: "Mid-Size Mobility Scooters"
              H3: "Heavy-Duty Mobility Scooters" [Long-tail: heavy duty]
            
            H2_2: "Key Features to Consider When Choosing" [Secondary keyword]
              H3: "Weight Capacity and User Comfort" [Long-tail: weight capacity]
              H3: "Battery Range and Charging"
              H3: "Terrain Compatibility"
              H3: "Storage and Portability"
            
            H2_3: "Mobility Scooter Sizing Guide"
              H3: "Measuring Yourself for the Right Fit"
              H3: "Seat Width and Weight Capacity"
            
            H2_4: "Australian Regulations and Subsidies"
              H3: "NDIS Mobility Scooter Funding"
              H3: "Road Rules for Mobility Scooters in Australia"
            
            H2_5: "Cost Considerations" [Secondary keyword: buying guide]
              H3: "Price Ranges by Category"
              H3: "Insurance Options" [Long-tail: insurance australia]
              H3: "Warranty Comparison" [Long-tail: warranty comparison]
            
            H2_6: "Decision Tree: Which Scooter is Right for You?"
            
            H2_7: "Common Mistakes to Avoid"
            
            H2_8: "Frequently Asked Questions" [Schema markup opportunity]
          
          Internal_Linking_Strategy:
            - "Link to product category pages (portable, mid-size, heavy-duty)"
            - "Link to NDIS funding guide"
            - "Link to warranty policy page"
            - "Link to insurance partner page"
          
          Content_Tone: "Empowering, not clinical. Treat scooters as lifestyle enablers."
        
        PM_Validation:
          - "PM verifies all primary/secondary keywords covered"
          - "PM checks content gaps from Stage 1 addressed"
          - "PM approves outline before writing begins"
      
      Stage_3_Copywriting:
        Agent: "content-strategist-agent (writing mode)"
        Duration: "4 hours"
        Input: "Stage 2 approved outline + SEO keyword map"
        
        Writing_Rules:
          - "Write for Australian audience (Australian spelling, local regulations)"
          - "Target reading level: Grade 8 (elderly audience)"
          - "Sentence length: <20 words average"
          - "Paragraph length: 3-4 sentences maximum"
          - "Use active voice, avoid jargon"
          - "Include real examples: 'Margaret from Brisbane chose...' (with proper consent)"
        
        Output:
          - "2,847 words"
          - "14 H2 sections, 23 H3 subsections"
          - "Keyword density: 1.2% (natural, not stuffed)"
          - "Readability: Flesch-Kincaid Grade 7.8"
          - "12 FAQ questions with concise answers"
        
        PM_Validation:
          - "PM checks brand voice consistency (empowering tone)"
          - "PM verifies Australian spelling (colour, not color)"
          - "PM validates NO medical jargon without explanation"
          - "PM checks reading level appropriate for elderly audience"
      
      Stage_4_Visual_Content_Design:
        Agent: "design-agent"
        Duration: "3 hours"
        Input: "Stage 3 written content"
        
        Visual_Assets_Required:
          Hero_Image:
            - "Custom illustration: Australian senior using mobility scooter at beach"
            - "Dimensions: 1200x630 (Open Graph optimised)"
            - "Format: WebP with JPG fallback"
          
          Decision_Tree_Infographic:
            - "Interactive flowchart: 'Find Your Perfect Scooter'"
            - "Mobile-responsive (vertical on mobile, horizontal on desktop)"
            - "Brand colours: Electric violet/coral"
          
          Comparison_Table:
            - "Visual table: Portable vs Mid-Size vs Heavy-Duty"
            - "Columns: Price, Weight Capacity, Range, Portability Score"
            - "Rows: 3 scooter types"
            - "Mobile: Accordion format, Desktop: Full table"
          
          Feature_Icons:
            - "12 custom icons: Battery, Weight, Speed, Comfort, Terrain, etc."
            - "Consistent style, accessible colours"
          
          Product_Imagery:
            - "Professional product photos with lifestyle context"
            - "NOT clinical white background"
            - "Show real people using scooters"
        
        PM_Validation:
          - "PM verifies images match brand aesthetic (premium, not medical)"
          - "PM checks mobile responsiveness of infographics"
          - "PM validates image alt text descriptive (SEO + accessibility)"
          - "PM ensures images optimised (<200KB each)"
      
      Stage_5_Frontend_Implementation:
        Agent: "landing-page-specialist-agent"
        Duration: "3 hours"
        Input: "Stage 3 content + Stage 4 visual assets"
        
        Implementation_Tasks:
          HTML_Structure:
            - "Semantic HTML5: <article>, <section>, <aside>"
            - "Proper heading hierarchy (H1 → H2 → H3, no skipping)"
            - "Table of contents with jump links"
          
          Schema_Markup:
            - "Article schema (headline, author, datePublished)"
            - "FAQ schema (12 questions for rich snippets)"
            - "BreadcrumbList schema"
            - "Organization schema"
          
          Accessibility:
            - "Alt text for all images (descriptive, not keyword-stuffed)"
            - "ARIA labels for interactive elements (decision tree)"
            - "Skip navigation link"
            - "Focus indicators for keyboard navigation"
          
          Performance:
            - "Lazy load below-fold images"
            - "Critical CSS inline"
            - "Defer non-critical JavaScript"
            - "Preload hero image"
        
        PM_Validation:
          - "PM validates schema markup in Google Rich Results Test"
          - "PM tests table of contents jump links work"
          - "PM checks mobile reading experience (font size, line height)"
      
      Stage_6_SEO_Technical_Validation:
        Agent: "seo-specialist-agent"
        Duration: "60 minutes"
        Input: "Stage 5 implemented blog post"
        
        Technical_SEO_Checklist:
          Meta_Data:
            - "Title: 'How to Choose a Mobility Scooter: 2025 Guide | E-Traveller' (58 chars)"
            - "Meta description: 'Complete guide to choosing the perfect mobility scooter for Australian seniors. Compare types, features, costs + NDIS funding.' (148 chars)"
            - "Canonical URL: https://e-traveller.com.au/blog/how-to-choose-mobility-scooter"
          
          Open_Graph:
            - "og:title, og:description, og:image (1200x630)"
            - "og:type: article"
          
          Internal_Links:
            - "5 internal links to product pages (portable, mid-size, heavy-duty)"
            - "3 internal links to resource pages (NDIS, insurance, warranty)"
          
          External_Links:
            - "2 authority links: Australian Government NDIS page, Choice.com.au mobility scooter guide"
          
          Image_SEO:
            - "All images have descriptive alt text"
            - "Image filenames descriptive: 'portable-mobility-scooter-beach.webp'"
          
          URL_Structure:
            - "URL: /blog/how-to-choose-mobility-scooter (clean, keyword-rich)"
        
        PM_Validation:
          - "PM checks meta description enticing (CTR optimised)"
          - "PM verifies internal links relevant and helpful"
          - "PM validates Open Graph image displays correctly on social media"
      
      Stage_7_Conversion_Optimisation:
        Agent: "cro-specialist-agent"
        Duration: "60 minutes"
        Input: "Stage 5 implemented blog post"
        
        CTA_Strategy:
          Primary_CTA: "After decision tree"
            Text: "Browse [Scooter Type] Collection"
            Placement: "After user completes decision tree"
            Design: "48px height, full-width on mobile, electric violet background"
          
          Secondary_CTA: "End of article"
            Text: "Get Free Buying Guide PDF"
            Placement: "After FAQ section"
            Design: "Lead magnet, email opt-in"
          
          Inline_CTAs: "Within content"
            - "After 'Portable Scooters' section: 'View Portable Range'"
            - "After 'Heavy-Duty Scooters' section: 'View Heavy-Duty Range'"
          
          Exit_Intent: "Popup when user about to leave"
            Text: "Wait! Get 10% off your first order + free delivery"
            Timing: "Exit intent or 60 seconds on page"
        
        Trust_Signals:
          - "Author bio: 'Written by Sarah Chen, Mobility Consultant with 12 years experience'"
          - "Last updated: '2 November 2025' (freshness signal)"
          - "Citations: Link to medical studies, government resources"
          - "Customer count: 'Trusted by 15,000+ Australian seniors'"
        
        PM_Validation:
          - "PM verifies CTAs don't interrupt reading flow"
          - "PM checks CTA contrast sufficient (4.5:1 minimum)"
          - "PM validates exit intent not annoying (can be easily closed)"
      
      Stage_8_Final_Quality_Assurance:
        Agent: "quality-control-agent"
        Duration: "90 minutes"
        Input: "Complete blog post from all stages"
        
        Quality_Checks:
          Content_Quality:
            - "Factual accuracy: All claims verified with sources"
            - "Grammar: Zero errors (Grammarly Premium check)"
            - "Readability: Flesch-Kincaid Grade <8"
            - "Plagiarism: <5% similarity (Copyscape)"
          
          SEO_Quality:
            - "Keyword integration natural, not stuffed"
            - "Meta data optimal length"
            - "Schema markup validates"
            - "Internal links relevant"
          
          Design_Quality:
            - "Visual hierarchy clear"
            - "Images high quality, brand-aligned"
            - "Mobile responsive (tested on real devices)"
            - "Infographics readable at all sizes"
          
          Technical_Quality:
            - "Page load: <3 seconds on 4G"
            - "Lighthouse: Performance >90, SEO 100"
            - "Accessibility: WCAG AAA"
            - "Cross-browser: Chrome, Safari, Firefox, Edge"
          
          Conversion_Quality:
            - "CTAs visible and compelling"
            - "Trust signals prominent"
            - "User flow logical (awareness → decision → action)"
        
        PM_Final_Approval:
          Quality_Gates_Status:
            - "✅ Gate 1: Content uniqueness (NOT generic listicle)"
            - "✅ Gate 2: Mobile experience (perfect on iPhone/Samsung)"
            - "✅ Gate 3: Accessibility (WCAG AAA, elderly-friendly)"
            - "✅ Gate 4: Performance (Lighthouse 94)"
            - "✅ Gate 5: SEO technical (schema validates)"
            - "✅ Gate 6: Content quality (Grade 7.8 reading level)"
            - "✅ Gate 7: Visual polish (premium brand aesthetic)"
            - "✅ Gate 8: Conversion optimised (CTAs strategically placed)"
          
          PM_Decision: "All 8 gates passed. Approved for publication."
    
    Post_Publication_Monitoring:
      Week_1:
        Agent: "seo-specialist-agent"
        Tasks:
          - "Monitor Google Search Console for indexing"
          - "Track keyword rankings (how to choose mobility scooter australia)"
          - "Check for featured snippet capture"
      
      Week_4:
        Agent: "cro-specialist-agent"
        Tasks:
          - "Analyse traffic: Organic search, social shares"
          - "Measure engagement: Time on page, scroll depth"
          - "Track conversions: CTA clicks, email opt-ins"
      
      Month_3:
        PM_Review_Metrics:
          SEO_Performance:
            - "Primary keyword: Ranking #3 (page 1)"
            - "Secondary keywords: 8 of 12 on page 1"
            - "Featured snippet: Captured for 'mobility scooter types'"
            - "Organic traffic: 2,847 visitors/month"
          
          Engagement_Metrics:
            - "Average time on page: 6 min 23 sec"
            - "Bounce rate: 42%"
            - "Scroll depth: 73% reach end of article"
          
          Conversion_Metrics:
            - "CTA clicks: 8.4%"
            - "Email opt-ins: 3.2%"
            - "Product page visits: 412"
            - "Revenue attributed: $18,600"
    
    PM_Multi_Agent_Coordination_Success_Factors:
      Sequential_Workflow: "✅ PM enforces SEO first → content strategy → writing → design → development → QA"
      Data_Handoffs: "✅ PM ensures each agent receives structured output from previous agent"
      Quality_Gates: "✅ PM validates at each stage before proceeding (no skip-ahead)"
      Brand_Consistency: "✅ PM ensures single voice across content, design, and conversion elements"
      Performance_Standards: "✅ PM enforces technical excellence (Lighthouse >90, WCAG AAA)"
      Commercial_Focus: "✅ PM balances SEO rankings with conversion optimisation"
    
    Final_Outcome:
      User_Feedback: "This blog post is the best thing we've ever published. It ranks, it converts, and customers actually read it!"
      ROI: "$18,600 revenue attributed in first 3 months from blog post that cost ~$2,000 to produce"

  Example_6_Handling_Agent_Failure_And_Recovery:
    Title: "PM Agent Handles Design Agent Failure and Quality Gate Rejection"
    
    Scenario: "design-agent produces generic medical-blue design despite explicit instructions to avoid it"
    
    User_Request: "Create homepage for E-Traveller with unique, premium design"
    
    PM_Agent_Initial_Workflow:
      
      Step_1_Discovery:
        Agent: "design-agent"
        Duration: "60 minutes"
        Input: "Project brief + forbidden design elements list"
        Expected_Output: "Competitor analysis showing what NOT to do"
        
        Actual_Output: "design-agent produces analysis with recommendations like 'clean blue interface', 'medical aesthetic'"
        
        PM_Detection:
          Alert: "⚠️ Forbidden keyword detected: 'medical aesthetic'"
          PM_Assessment: "design-agent ignored instructions about avoiding medical look"
          PM_Decision: "REJECT output, re-issue task with stronger constraints"
      
      Step_1_RETRY:
        PM_Action: "Re-brief design-agent with explicit negative examples"
        
        New_Instructions:
          FORBIDDEN_DESIGNS: "Show design-agent 5 competitor screenshots"
          FORBIDDEN_COLOURS: "#0066CC (medical blue), #0088FF, #CCCCCC (medical grey)"
          FORBIDDEN_TERMS: "clinical, medical, healthcare, sterile"
          REQUIRED_APPROACH: "Lifestyle brand, premium positioning, aspirational imagery"
        
        Actual_Output_Retry: "design-agent produces lifestyle-focused analysis avoiding all forbidden elements"
        PM_Validation: "✅ Output meets criteria, proceed to Step 2"
      
      Step_2_Design_Concept:
        Agent: "design-agent"
        Duration: "3 hours"
        Expected_Output: "3 colour palette options with rationale"
        
        Actual_Output:
          Palette_1: "Navy blue (#003366) + White" [FORBIDDEN]
          Palette_2: "Light blue (#6699CC) + Grey" [FORBIDDEN]
          Palette_3: "Forest green (#2D5016) + Gold (#C5A572)" [ACCEPTABLE]
        
        PM_Automated_Validation:
          Check_1: "Scan for forbidden hex codes"
            Result: "FAIL - #003366 and #6699CC are variants of medical blue"
          
          Check_2: "Colour psychology alignment with brand"
            Result: "FAIL - Navy and light blue signal healthcare/medical"
          
          Check_3: "Uniqueness vs competitors"
            Result: "FAIL - 4 of 5 competitors use blue"
        
        PM_Decision: "REJECT Palette 1 and 2, APPROVE Palette 3 only"
        
        PM_Feedback_To_Design_Agent:
          "Palette 1 and 2 rejected: Navy and light blue are forbidden colours that signal medical/healthcare.
          
          Palette 3 (forest green + gold) approved for moving forward.
          
          For future palettes, consider:
          - Burgundy (#8B1538) + Gold (#D4AF37)
          - Electric violet (#7B2D8F) + Coral (#FF6B6B)
          - Charcoal (#36454F) + Copper (#B87333)
          
          NEVER present blue palettes again for this project."
      
      Step_3_Design_Mockups:
        Agent: "design-agent"
        Duration: "5 hours"
        Input: "Approved Palette 3 (forest green + gold)"
        Expected_Output: "High-fidelity homepage mockups (mobile + desktop)"
        
        Actual_Output:
          Mobile_Mockup: "design-agent creates design with hero image, three feature boxes, testimonial, CTA"
          Desktop_Mockup: "Same design, just wider"
        
        PM_Automated_Validation:
          Check_1: "Mobile layout analysis"
            Result: "FAIL - Three feature boxes stacked vertically = prohibited pattern"
          
          Check_2: "Desktop vs mobile comparison"
            Result: "FAIL - Desktop is just wider mobile, not enhanced"
          
          Check_3: "Design uniqueness assessment"
            Result: "FAIL - Layout matches 80% of competitor sites"
        
        PM_Quality_Gate_1:
          Lead: "quality-control-agent"
          Assessment:
            - "❌ Mobile: Three-box stacked pattern (forbidden)"
            - "❌ Design: Generic layout seen on every mobility site"
            - "❌ Typography: Uses Arial (too generic)"
            - "✅ Colours: Forest green + gold (approved palette)"
            - "✅ Imagery: Lifestyle, not clinical"
          
          Overall: "FAIL - 3 critical issues"
          Recommendation: "Reject and require redesign with innovative layout"
        
        PM_Decision: "BLOCK progression to development phase"
        
        PM_Escalation_To_User:
          Message: "Quality gate failed. design-agent produced generic layout despite using approved colours.
          
          Issues:
          1. Mobile uses forbidden three-box stacked pattern
          2. Layout matches 80% of competitors (not unique)
          3. Typography too generic (Arial)
          
          Recommendation: Allow 4 additional hours for complete layout redesign using:
          - Bento grid (Pinterest-style asymmetric layout)
          - Diagonal elements for visual interest
          - Custom typography pairing
          
          Timeline impact: +1 day, but quality will be exceptional
          
          Approve redesign?"
        
        User_Response: "Yes, quality over speed. Do the redesign."
      
      Step_3_REDESIGN:
        PM_Action: "Re-brief design-agent with innovative layout requirements"
        
        New_Instructions:
          LAYOUT_REQUIREMENTS:
            - "Use Bento grid system (asymmetric cards)"
            - "Incorporate diagonal elements (angled sections, skewed images)"
            - "Variable card sizes for visual hierarchy"
            - "NEVER use three equal boxes"
          
          TYPOGRAPHY_REQUIREMENTS:
            - "Pair serif + sans-serif (e.g., Playfair Display + Raleway)"
            - "Large, bold headlines (60px+ on desktop)"
            - "NEVER use system fonts (Arial, Helvetica)"
          
          INSPIRATION:
            - "Apple product pages (premium feel)"
            - "Airbnb (lifestyle imagery)"
            - "Stripe (modern tech aesthetic)"
        
        Actual_Output_Redesign:
          Mobile_Mockup: "Asymmetric card layout with varying sizes, diagonal hero image, serif headlines"
          Desktop_Mockup: "Enhanced with parallax scrolling, hover animations, multi-column Bento grid"
        
        PM_Validation:
          Check_1: "Mobile layout innovation"
            Result: "PASS - Bento grid creates visual interest, NOT three boxes"
          
          Check_2: "Desktop enhancement"
            Result: "PASS - Genuinely different from mobile, not just wider"
          
          Check_3: "Typography assessment"
            Result: "PASS - Playfair Display + Raleway pairing is distinctive"
        
        PM_Quality_Gate_1_RETRY:
          Lead: "quality-control-agent"
          Assessment:
            - "✅ Mobile: Innovative Bento grid layout"
            - "✅ Design: Unique, unlike any competitor"
            - "✅ Typography: Sophisticated serif/sans pairing"
            - "✅ Colours: Forest green + gold maintained"
            - "✅ Imagery: Premium lifestyle aesthetic"
          
          Overall: "PASS - All 8 quality gates met"
          Recommendation: "Approve for user review"
        
        PM_Decision: "Present to user for final approval"
        
        User_Response: "This is EXACTLY what I wanted! Approve for development."
    
    PM_Failure_Handling_Demonstrated:
      Automated_Validation: "✅ PM uses automated checks to detect forbidden elements (colours, patterns)"
      Early_Detection: "✅ PM catches issues at each phase, not at final QA"
      Clear_Feedback: "✅ PM gives specific, actionable feedback to agents (not just 'try again')"
      User_Communication: "✅ PM escalates to user when timeline adjustment needed"
      Quality_Over_Speed: "✅ PM enforces quality gates even when it delays project"
      Learning_Loop: "✅ PM adjusts instructions for retry to prevent same failure"
    
    Timeline_Impact:
      Original_Estimate: "Phase 2-4: 10 hours"
      Actual_With_Failures: "Phase 2-4: 15 hours (+5 hours for redesign)"
      User_Satisfaction: "5/5 - 'Worth the extra time, final design is stunning'"
    
    Key_Lessons_For_PM:
      Lesson_1: "Catch failures early with automated validation (saves rework time)"
      Lesson_2: "Give specific negative examples to prevent repeated failures"
      Lesson_3: "Communicate timeline impacts proactively to user"
      Lesson_4: "Never approve mediocre work to meet deadline"
      Lesson_5: "Use quality gates to enforce standards systematically"

# End of Real-World Examples

