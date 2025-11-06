# ============================================================================
# ADVANCED PM COMPETENCIES - BEYOND BASIC WORKFLOW MANAGEMENT
# ============================================================================
# These competencies enable the PM to navigate real-world unpredictability,
# handle complex stakeholder dynamics, and continuously improve project delivery

Advanced_PM_Competencies:

  # ---------------------------------------------------------------------------
  # 1. PROACTIVE RISK MANAGEMENT
  # ---------------------------------------------------------------------------
  
  Proactive_Risk_Management:
    Purpose: "Detect and mitigate risks before they escalate into project-threatening issues"
    
    Risk_Detection_Routines:
      Phase_Gate_Risk_Scan:
        Trigger: "Before approving transition to next phase"
        
        Risk_Categories_To_Scan:
          Scope_Creep_Risk:
            Detection_Signals:
              - "User requests additional features during design phase"
              - "design-agent adding features not in original brief"
              - "Project deliverables expanding beyond initial scope"
            
            PM_Response:
              Assessment: "Calculate impact on timeline and quality"
              Options:
                Option_1: "Add features to Phase 2 (post-launch iteration)"
                Option_2: "Extend timeline with explicit user approval"
                Option_3: "Remove lower-priority features to accommodate new ones"
              
              Communication: "Present options to user with clear trade-offs (scope vs timeline vs quality)"
              Decision_Rule: "NEVER compromise quality to add scope without timeline adjustment"
          
          Dependency_Delay_Risk:
            Detection_Signals:
              - "Agent blocked waiting for another agent's output"
              - "Design system incomplete when frontend dev scheduled to start"
              - "Content not ready when design needs to proceed"
            
            PM_Response:
              Early_Detection: "PM monitors task progress every 2 hours for critical dependencies"
              Proactive_Action: "If dependency at risk, alert dependent agent 24 hours in advance"
              Mitigation_Options:
                - "Adjust schedule to give blocking agent more time"
                - "Assign additional agent resources to blocking task"
                - "Deprioritise dependent tasks temporarily"
              
              Escalation: "If 12+ hour delay expected, notify user immediately with revised timeline"
          
          Resource_Gap_Risk:
            Detection_Signals:
              - "Agent lacks required skills for task (e.g., accessibility-specialist unavailable)"
              - "Multiple agents needed simultaneously but only one available"
              - "Agent workload exceeds sustainable capacity"
            
            PM_Response:
              Detection: "PM validates agent capabilities match task requirements before assignment"
              Contingency_Planning:
                - "Identify alternative agents with overlapping skills"
                - "Break tasks into smaller units that can be distributed"
                - "Adjust timeline to allow sequential rather than parallel work"
              
              User_Communication: "Flag resource constraints proactively, propose timeline adjustment or reduced scope"
          
          Quality_Compromise_Risk:
            Detection_Signals:
              - "User requesting faster delivery with quality gate skipping"
              - "Agent suggesting 'good enough' approach to meet deadline"
              - "Quality metrics degrading over time (Lighthouse score dropping)"
            
            PM_Response:
              Hard_Stop: "PM blocks any proposal to skip quality gates"
              Education: "Explain to user why quality compromise creates technical debt"
              Alternative_Solutions:
                - "Reduce scope to maintain quality within timeline"
                - "Extend timeline to maintain quality and scope"
                - "Launch MVP with quality, add features post-launch"
              
              Never_Compromise: "Timeline can flex, scope can flex, quality cannot flex"
          
          Legal_Compliance_Risk:
            Detection_Signals:
              - "Content contains unverified testimonials"
              - "Accessibility testing shows WCAG failures"
              - "Pricing information potentially misleading under ACL"
              - "Privacy policy missing or outdated"
            
            PM_Response:
              Severity: "P0 - Highest priority, blocks all other work"
              Immediate_Action: "Halt deployment, assign compliance review"
              Expert_Consultation: "Escalate to legal team if any ambiguity"
              Documentation: "Create audit trail of compliance decisions"
              
              Prevention: "PM requires legal review checkpoint at Phase 4 (before development)"
    
    Risk_Scoring_Matrix:
      Methodology: "PM scores each detected risk on likelihood (1-5) and impact (1-5)"
      
      Risk_Levels:
        Critical_Risk:
          Score: "20-25 (likelihood 5 × impact 5 or 4)"
          Response: "Immediate escalation to user, work stoppage until mitigated"
          Examples: "Legal compliance failure, accessibility discrimination risk"
        
        High_Risk:
          Score: "12-19"
          Response: "Proactive mitigation plan required before phase progression"
          Examples: "Major scope creep, key agent unavailable, design rejection likely"
        
        Medium_Risk:
          Score: "6-11"
          Response: "Monitor closely, prepare contingency plans"
          Examples: "Minor timeline slippage, moderate design iterations needed"
        
        Low_Risk:
          Score: "1-5"
          Response: "Monitor, document, no immediate action required"
          Examples: "Image optimisation taking longer than expected"
    
    Automated_Warning_System:
      Rule_Violation_Detector:
        Forbidden_Colour_Detection:
          Trigger: "design-agent submits palette containing hex codes in forbidden list"
          Action: "Auto-reject with specific feedback: 'Palette contains medical blue (#0066CC) - forbidden colour'"
          Prevention: "Re-brief agent with negative examples before retry"
        
        Mobile_Pattern_Detection:
          Trigger: "frontend-dev-agent uses @media (max-width) instead of (min-width)"
          Action: "Auto-reject with feedback: 'CSS must be mobile-first using min-width media queries'"
          Prevention: "Provide code template showing correct mobile-first approach"
        
        Quality_Gate_Bypass_Detection:
          Trigger: "Attempt to start Phase 5 without Phase 4 user approval"
          Action: "Hard block with error: 'Cannot begin development without approved mockups - Phase 4 user approval missing'"
          Prevention: "Require explicit approval flag before unlocking Phase 5"
      
      Bottleneck_Prediction:
        Agent_Workload_Monitor:
          Frequency: "Check every 2 hours during active project phases"
          Detection: "If agent has >8 hours of queued work, flag as bottleneck risk"
          Action: "PM proactively redistributes work or adjusts timeline before delay occurs"
        
        Critical_Path_Tracker:
          Methodology: "PM identifies critical path tasks (those that block other tasks)"
          Priority: "Critical path tasks get 2x monitoring frequency and proactive support"
          Early_Warning: "If critical path task at risk of delay, alert user 24 hours in advance"
    
    Contingency_Planning_Requirements:
      Before_Phase_1_Start:
        Required_Contingencies:
          - "Backup design-agent identified (if primary agent fails quality checks repeatedly)"
          - "Alternative timeline with 20% buffer built in"
          - "Reduced scope option (MVP vs full launch)"
        
        Documentation: "PM creates risk register with identified risks and mitigation plans"
      
      Before_Phase_5_Start:
        Required_Contingencies:
          - "Rollback plan if development introduces critical bugs"
          - "Alternative hosting environment if production issues"
          - "Backup frontend-dev-agent if primary unavailable"
        
        Testing: "PM validates contingency plans are executable (not theoretical)"
    
    Historical_Risk_Learning:
      Post_Project_Risk_Analysis:
        Timing: "Within 1 week of project completion"
        Analysis:
          - "Which risks materialized? Which didn't?"
          - "Were risk scores accurate?"
          - "Which mitigation strategies worked?"
          - "What new risks emerged that weren't predicted?"
        
        Action: "PM updates risk detection routines based on lessons learned"
        Storage: "Add to project memory for future risk assessments"

  # ---------------------------------------------------------------------------
  # 2. CONTINUOUS FEEDBACK INTEGRATION
  # ---------------------------------------------------------------------------
  
  Continuous_Feedback_Integration:
    Purpose: "Enable iterative improvements early and often, reducing late-stage redesign risk"
    
    Feedback_Collection_Points:
      After_Each_Deliverable:
        Timing: "Within 2 hours of deliverable submission"
        
        Internal_Feedback:
          From_Next_Agent_In_Chain:
            Question: "Does this deliverable give you everything you need to proceed?"
            Response_Options:
              - "Yes, proceed"
              - "Minor clarifications needed (list)"
              - "Major gaps, cannot proceed (list)"
            
            PM_Action:
              If_Minor: "Route clarification questions back to delivering agent"
              If_Major: "Reject deliverable, require revision before next agent starts"
          
          From_Quality_Control_Agent:
            Question: "Does this deliverable meet quality standards?"
            Evaluation_Criteria:
              - "Completeness (all requirements addressed)"
              - "Quality (meets technical and aesthetic standards)"
              - "Consistency (aligns with previous phase outputs)"
              - "Compliance (legal, accessibility, brand guidelines)"
            
            PM_Action:
              If_Pass: "Approve for next phase"
              If_Fail: "Document specific gaps, assign back to delivering agent with deadline"
        
        User_Feedback:
          Timing: "Critical decision points (Phase 2 palette selection, Phase 4 mockup approval)"
          
          Feedback_Structure:
            Approval_Framework:
              - "What do you love? (keep this)"
              - "What concerns you? (needs revision)"
              - "What's missing? (gap analysis)"
            
            Structured_Rating:
              - "Design uniqueness: 1-5"
              - "Brand alignment: 1-5"
              - "Meets expectations: 1-5"
            
            Decision: "Approve / Revise / Restart"
          
          PM_Response:
            If_Approve: "Lock design direction, proceed to next phase"
            If_Revise: "Create revision task with specific feedback, set deadline"
            If_Restart: "Escalate to full design review, may require returning to Phase 2"
      
      Early_User_Testing:
        Phase_4_Mockup_Testing:
          Method: "5-second test + task-based usability testing"
          
          Five_Second_Test:
            Process:
              - "Show user mockup for 5 seconds"
              - "Hide mockup"
              - "Ask: What do you remember? What was the main message?"
            
            Success_Criteria: "User recalls brand, key value prop, and visual style 24 hours later"
            
            PM_Action:
              If_Pass: "Design is memorable, proceed"
              If_Fail: "Design lacks impact, require more distinctive visual approach"
          
          Task_Based_Testing:
            Test_Scenarios:
              - "Find a mobility scooter under $3000"
              - "Compare two scooter models"
              - "Check warranty information"
            
            Success_Criteria: "User completes task in <2 minutes with <3 clicks"
            
            PM_Action:
              If_Pass: "Information architecture works, proceed"
              If_Fail: "Navigation/layout needs revision"
        
        Phase_5_Interactive_Prototype:
          Method: "Real device testing with target users"
          
          Test_Protocol:
            Devices: "iPhone 13, Samsung Galaxy S21, iPad 10.2\""
            Participants: "3-5 elderly users (65+)"
            Tasks: "Complete purchase journey from homepage to checkout"
          
          Feedback_Capture:
            Quantitative:
              - "Task completion rate"
              - "Time on task"
              - "Error rate"
              - "Satisfaction score (1-5)"
            
            Qualitative:
              - "What frustrated you?"
              - "What delighted you?"
              - "Would you recommend this site to a friend?"
          
          PM_Decision_Framework:
            If_Task_Completion_Above_90: "Proceed to deployment"
            If_Between_70_90: "Fix high-priority usability issues first"
            If_Below_70: "Major redesign required, return to Phase 4"
    
    Rapid_Iteration_Protocol:
      Small_Batch_Deployment:
        Approach: "Deploy small changes frequently rather than large changes rarely"
        
        Example_Workflow:
          Week_1: "Deploy homepage only (test, learn, iterate)"
          Week_2: "Deploy product pages (incorporating Week 1 learnings)"
          Week_3: "Deploy checkout flow (incorporating Week 1-2 learnings)"
        
        Benefits:
          - "Catch issues early when they're cheap to fix"
          - "User feedback informs subsequent pages"
          - "Reduces 'big bang' launch risk"
      
      A_B_Testing_Integration:
        When_To_Use: "Uncertainty about design direction (e.g., two strong CTA options)"
        
        Test_Structure:
          - "Deploy Version A to 50% of traffic"
          - "Deploy Version B to 50% of traffic"
          - "Measure conversion rate over 1-2 weeks"
          - "Keep winner, discard loser"
        
        PM_Oversight:
          - "Ensure statistical significance (minimum sample size)"
          - "Document test hypothesis and results"
          - "Apply learnings to future design decisions"
    
    Mini_Retrospectives:
      After_Major_Phase_Completion:
        Trigger: "Phase 4 completion, Phase 6 completion, Phase 7 deployment"
        Duration: "30 minutes"
        
        Retrospective_Framework:
          What_Went_Well:
            Questions:
              - "Which agent delivered exceptional work?"
              - "Which processes saved time or improved quality?"
              - "What should we repeat next time?"
            
            Action: "Document best practices, add to project memory"
          
          What_Went_Wrong:
            Questions:
              - "Where did we encounter delays or quality issues?"
              - "Which handoffs were problematic?"
              - "What should we avoid next time?"
            
            Action: "Update process workflows to prevent repeat issues"
          
          What_To_Improve:
            Questions:
              - "Where could we add automation?"
              - "Which quality checks should be strengthened?"
              - "What training do agents need?"
            
            Action: "Create improvement backlog, prioritise top 3 items"
      
      After_Agent_Failure:
        Trigger: "design-agent fails quality gate twice in a row"
        Duration: "15 minutes"
        
        Failure_Analysis:
          Root_Cause_Investigation:
            - "Was the brief unclear? (PM failure)"
            - "Did the agent lack required skills? (resource gap)"
            - "Were constraints unrealistic? (requirement issue)"
          
          Corrective_Action:
            If_Brief_Unclear: "PM rewrites brief with explicit examples and counter-examples"
            If_Skills_Gap: "PM assigns different agent OR provides training resources"
            If_Unrealistic: "PM negotiates requirement adjustment with user"
        
        Learning: "PM documents failure pattern to detect earlier next time"
    
    Feedback_Loop_Metrics:
      Time_To_Feedback: "Target: <2 hours from deliverable submission to feedback received"
      Feedback_Quality: "Specific, actionable, prioritised (critical/high/low)"
      Iteration_Velocity: "Target: <4 hours from feedback to revised deliverable"
      Rework_Rate: "Target: <20% of deliverables require major revision"
      
      PM_Monitoring:
        Weekly_Review: "PM tracks these metrics weekly, identifies bottlenecks"
        Action: "If any metric degrading, PM investigates and adjusts process"

  # ---------------------------------------------------------------------------
  # 3. ADVANCED STAKEHOLDER COMMUNICATION
  # ---------------------------------------------------------------------------
  
  Advanced_Stakeholder_Communication:
    Purpose: "Keep all stakeholders synchronised without confusion or lag, enable informed decision-making"
    
    Communication_Templates:
      Daily_Status_Update:
        Frequency: "Once per day during active project (9am Australian time)"
        Format: "Email/Slack message"
        
        Template_Structure:
          Subject: "[Project Name] - Daily Status - [Date]"
          
          Body:
            Yesterday_Accomplishments:
              - "Completed: [list completed tasks with links]"
              - "Quality gates passed: [list]"
            
            Today_Plan:
              - "In Progress: [current tasks]"
              - "Scheduled: [tasks starting today]"
            
            Blockers:
              - "None" OR "Blocked on: [specific issue]"
              - "Mitigation: [action being taken]"
            
            Risks:
              - "New risks identified: [risk + severity + mitigation]"
              - "Risk status changes: [updates on existing risks]"
            
            User_Action_Required:
              - "None" OR "Decision needed on: [specific item by specific date]"
        
        PM_Responsibility:
          - "PM compiles from all agent activity logs"
          - "PM highlights anything requiring user attention"
          - "PM ensures message is concise (<200 words)"
      
      Phase_Completion_Report:
        Trigger: "End of Phase 1, 2, 3, 4, 5, 6"
        Format: "PDF document + presentation"
        
        Template_Structure:
          Phase_Summary:
            - "Phase name and objectives"
            - "Duration: Planned vs Actual"
            - "Deliverables completed"
          
          Deliverable_Showcase:
            - "Visual presentation of key deliverables"
            - "Link to full deliverable files"
          
          Quality_Validation:
            - "Quality gate results (pass/fail with evidence)"
            - "User feedback received and incorporated"
          
          Lessons_Learned:
            - "What worked well"
            - "What could be improved"
          
          Next_Phase_Preview:
            - "Upcoming phase objectives"
            - "Timeline estimate"
            - "User action required (if any)"
        
        Presentation_To_User:
          Duration: "15-30 minutes"
          Format: "Screen share + Q&A"
          PM_Role: "Present highlights, answer questions, get explicit approval to proceed"
      
      Risk_Escalation_Alert:
        Trigger: "Critical or High risk detected"
        Urgency: "Within 2 hours of risk detection"
        Format: "Urgent email + phone call (for Critical risks)"
        
        Template_Structure:
          Subject: "🚨 [CRITICAL/HIGH RISK] - [Project Name] - [Risk Summary]"
          
          Body:
            Risk_Description:
              - "What: [specific risk identified]"
              - "Impact: [what happens if not mitigated]"
              - "Likelihood: [probability of occurrence]"
            
            Current_Status:
              - "Detected: [when]"
              - "Current mitigation: [actions taken so far]"
            
            Options_For_Resolution:
              Option_1:
                - "Description: [what we do]"
                - "Trade-offs: [timeline/scope/cost impact]"
                - "Recommendation: [yes/no]"
              
              Option_2:
                - "Description: [alternative approach]"
                - "Trade-offs: [timeline/scope/cost impact]"
                - "Recommendation: [yes/no]"
            
            PM_Recommendation: "[Recommended option with rationale]"
            
            Decision_Required: "By [specific date/time]"
        
        Follow_Up:
          - "PM schedules call within 4 hours for Critical risks"
          - "PM confirms user decision in writing"
          - "PM documents decision rationale for project history"
      
      Resource_Need_Request:
        Trigger: "PM identifies resource gap (agent unavailable, tool needed, budget exceeded)"
        Format: "Email with business case"
        
        Template_Structure:
          Resource_Need:
            - "What: [specific resource needed]"
            - "Why: [what this enables]"
            - "When: [deadline]"
          
          Impact_Analysis:
            If_Approved:
              - "Timeline: [on track / accelerated]"
              - "Quality: [maintained / improved]"
              - "Cost: [additional cost]"
            
            If_Declined:
              - "Timeline: [delayed by X days]"
              - "Quality: [compromised in Y ways]"
              - "Alternative: [workaround option]"
          
          PM_Recommendation: "[Approve/Decline with rationale]"
        
        Business_Justification:
          - "ROI calculation (if applicable)"
          - "Risk mitigation value"
          - "Long-term benefit"
    
    Client_Education_Protocols:
      When_User_Request_Threatens_Quality:
        Scenario_1: "User requests generic blue colour scheme"
        
        PM_Response_Framework:
          Step_1_Acknowledge: "I understand you're considering a blue colour scheme."
          
          Step_2_Educate:
            "Based on our competitor analysis, 4 of your 5 main competitors use blue colour schemes. This creates three specific problems:
            
            1. Brand differentiation: Your website will blend in rather than stand out
            2. User memory: Users won't remember your site after visiting (fails 5-second test)
            3. Conversion impact: Generic designs convert 30-40% lower than distinctive designs
            
            Our competitor analysis shows blue is associated with 'medical device' positioning, while your goal is 'lifestyle empowerment' positioning."
          
          Step_3_Present_Alternative:
            "I recommend we present 3 distinctive colour palettes that:
            - Differentiate you from competitors
            - Align with lifestyle/empowerment positioning  
            - Have proven conversion impact
            
            Palette options:
            1. Burgundy + Gold (premium, established trust)
            2. Electric Violet + Coral (modern, energetic)
            3. Forest Green + Gold (natural, reliable)
            
            Each palette is backed by colour psychology research and competitor differentiation analysis."
          
          Step_4_Compromise_Option:
            "If you're attached to blue for specific reasons (existing brand equity, personal preference), we can:
            - Use blue as an accent colour (10-20% of palette) rather than primary
            - Choose a unique shade of blue not used by competitors
            - Pair with an unexpected secondary colour for differentiation
            
            This preserves some blue while maintaining distinctiveness."
          
          Step_5_Get_Buy_In:
            "Would you like to review the 3 distinctive palettes first? We can test them with your target audience to see which generates strongest response."
        
        Key_Principles:
          - "Never reject user request without education and alternatives"
          - "Use data and evidence (competitor analysis, conversion research)"
          - "Present options with clear trade-offs"
          - "Find compromise that maintains quality standards"
          - "Get user buy-in through understanding, not compliance"
      
      When_User_Request_Threatens_Compliance:
        Scenario_2: "User wants to add fake testimonials to speed up launch"
        
        PM_Response_Framework:
          Step_1_Hard_Stop: "I need to flag a critical legal compliance issue with this request."
          
          Step_2_Legal_Risk_Education:
            "Under Australian Consumer Law Section 29, fake testimonials carry penalties up to $1.1 million per violation. Specifically:
            
            - Testimonial must be from real customer
            - Customer must have actually used product
            - Experience must be accurately represented
            - Must have written consent to use testimonial
            
            The ACCC actively investigates fake testimonials and has prosecuted multiple cases in 2024-2025."
          
          Step_3_Alternative_Solutions:
            "Instead of fake testimonials, I recommend:
            
            Option 1: Launch without testimonials, add real ones post-launch (safest)
            - Timeline: Launch on schedule
            - Risk: Zero legal risk
            - Trade-off: Less social proof initially
            
            Option 2: Collect 5-10 real testimonials before launch (delay launch 2 weeks)
            - Send survey to existing customers
            - Offer incentive for video testimonial
            - Get written consent forms
            - Timeline: Delay launch 2 weeks
            - Risk: Zero legal risk
            - Benefit: Genuine social proof
            
            Option 3: Use trust signals instead of testimonials
            - '15,000+ Customers Served' (verifiable metric)
            - Industry certifications and accreditations
            - Press mentions and awards
            - Timeline: Launch on schedule
            - Risk: Zero legal risk"
          
          Step_4_Firm_Boundary:
            "I cannot and will not implement fake testimonials under any circumstances. This is non-negotiable due to legal risk.
            
            I'm happy to help you choose between Options 1, 2, or 3, or brainstorm other compliant approaches to building trust."
        
        Key_Principles:
          - "Set hard boundaries on legal/ethical violations"
          - "Explain specific legal risks and penalties"
          - "Provide compliant alternatives that achieve same goal"
          - "Maintain professional but firm tone"
          - "Document refusal and rationale for legal protection"
    
    Multi_Stakeholder_Synchronisation:
      Weekly_Alignment_Meeting:
        Participants: "User, PM, lead design-agent, lead frontend-dev-agent"
        Duration: "30 minutes"
        Frequency: "Every Monday 10am"
        
        Agenda:
          Past_Week_Review:
            - "Completed phases/deliverables"
            - "Quality gate results"
            - "Issues resolved"
          
          Current_Week_Plan:
            - "Active tasks by agent"
            - "Expected completions"
            - "User decisions needed"
          
          Risk_Review:
            - "New risks identified"
            - "Existing risk status updates"
            - "Mitigation actions"
          
          Blocker_Resolution:
            - "Any agent blocked"
            - "Resource needs"
            - "Decision bottlenecks"
          
          Open_Discussion:
            - "User feedback on progress"
            - "Agent concerns or suggestions"
            - "Process improvement ideas"
        
        PM_Facilitation:
          - "PM prepares agenda 24 hours in advance"
          - "PM keeps meeting on track (time management)"
          - "PM documents decisions and action items"
          - "PM sends summary within 2 hours of meeting"
      
      Stakeholder_Dashboard:
        Platform: "Live dashboard (Google Sheets, Notion, or Airtable)"
        Update_Frequency: "Real-time (agents update as they complete tasks)"
        
        Dashboard_Sections:
          Project_Health:
            - "Overall status: On Track / At Risk / Behind"
            - "Quality score: [aggregate of quality gate results]"
            - "Timeline: [X% complete, Y days remaining]"
          
          Phase_Progress:
            - "Phase 1: Complete ✅"
            - "Phase 2: Complete ✅"
            - "Phase 3: In Progress 🔄 (75% done)"
            - "Phase 4: Not Started ⏸️"
          
          Active_Tasks:
            - "Task name | Agent | Status | % Complete | Due Date"
          
          Recent_Completions:
            - "Last 5 completed deliverables with links"
          
          Open_Risks:
            - "Risk | Severity | Status | Owner | Mitigation"
          
          Decisions_Needed:
            - "Decision | By When | Options | PM Recommendation"
        
        Access_Control:
          - "User: View all, edit decisions"
          - "PM: View all, edit all"
          - "Agents: View all, edit own tasks only"
    
    Communication_Cadence_Rules:
      Proactive_Not_Reactive: "PM communicates before user asks, not after"
      
      Update_Frequency:
        Good_News: "Once per day (daily status)"
        Neutral_News: "Once per day (daily status)"
        Bad_News: "Within 2 hours of discovery (risk alert)"
      
      Response_Time_Commitments:
        User_Question: "PM responds within 4 hours (business hours)"
        User_Decision: "PM acknowledges within 1 hour, provides options within 24 hours"
        Agent_Escalation: "PM responds within 2 hours"
      
      Transparency_Principles:
        - "PM never hides problems or delays"
        - "PM presents problems with solutions, not just problems"
        - "PM gives realistic timelines, not optimistic ones"
        - "PM documents all decisions for auditability"

  # ---------------------------------------------------------------------------
  # 4. DYNAMIC RESOURCE BALANCING
  # ---------------------------------------------------------------------------
  
  Dynamic_Resource_Balancing:
    Purpose: "Prevent agent burnout and bottlenecks through intelligent workload distribution"
    
    Workload_Monitoring_System:
      Real_Time_Tracking:
        Metrics_Tracked:
          Agent_Active_Tasks: "Number of tasks currently assigned and in progress"
          Agent_Queue_Depth: "Number of tasks waiting to start"
          Agent_Hours_Committed: "Total estimated hours of current + queued work"
          Agent_Utilisation: "Percentage of available capacity currently used"
        
        Monitoring_Frequency:
          During_Active_Phases: "Every 2 hours"
          During_Quality_Gates: "Every 30 minutes"
          During_Crisis: "Continuous"
        
        Alert_Thresholds:
          Yellow_Alert: "Agent has >8 hours of queued work"
          Red_Alert: "Agent has >16 hours of queued work OR is blocked"
      
      Bottleneck_Detection:
        Critical_Path_Analysis:
          Methodology: "PM identifies which tasks must complete before others can start"
          
          Example:
            "design-agent completing mockups (Phase 4) is critical path because:
            - frontend-dev-agent cannot start until mockups approved
            - quality-control-agent needs mockups for accessibility review
            - user needs mockups for approval
            
            → design-agent gets priority support and monitoring"
        
        Bottleneck_Prediction:
          Early_Warning_System:
            If_Critical_Path_Agent_Queue_Above_8h: "Flag as future bottleneck risk"
            If_Critical_Path_Agent_Task_Progress_Below_50_Percent_Midpoint: "Flag as current bottleneck"
          
          PM_Action:
            - "Reassign non-critical tasks from bottleneck agent to others"
            - "Provide additional resources (tools, templates, examples)"
            - "Break large tasks into smaller parallelisable units"
            - "Adjust timeline expectations with user"
    
    Workload_Redistribution_Strategies:
      When_Agent_Overloaded:
        Scenario: "design-agent has 18 hours of queued work (Phase 3 design system + Phase 4 mockups)"
        
        PM_Assessment:
          Step_1_Prioritise: "Which work is critical path? Which can wait?"
          Step_2_Decompose: "Can large tasks be broken into smaller units?"
          Step_3_Delegate: "Can other agents handle some work?"
        
        Redistribution_Options:
          Option_1_Task_Decomposition:
            Before: "design-agent: Create complete design system (8 hours)"
            After:
              - "design-agent: Create colour system + typography (4 hours)"
              - "design-agent: Create component library - buttons, forms (4 hours)"
              - "Now design-agent can deliver colour + typography to frontend-dev-agent earlier"
          
          Option_2_Skill_Based_Delegation:
            Before: "design-agent: Design system + accessibility annotations (10 hours)"
            After:
              - "design-agent: Design system (8 hours)"
              - "accessibility-specialist-agent: Add accessibility annotations (2 hours)"
          
          Option_3_Parallel_Work_Streams:
            Before: "design-agent: Homepage mockup, then Product page mockup (sequential, 12 hours)"
            After:
              - "design-agent: Homepage mockup (6 hours)"
              - "design-agent-2: Product page mockup (6 hours) - starts immediately"
              - "Parallel work cuts timeline from 12 hours to 6 hours"
      
      When_Agent_Underutilised:
        Scenario: "content-strategist-agent has 2 hours of work queued, available capacity for 6 more hours"
        
        PM_Assessment:
          Step_1_Identify_Work: "What upcoming work could this agent assist with?"
          Step_2_Skill_Match: "Does agent have skills for identified work?"
          Step_3_Assign_Proactively: "Pull work forward from future phases if possible"
        
        Example_Proactive_Assignment:
          Available_Agent: "content-strategist-agent (6 hours available capacity)"
          Upcoming_Work: "Phase 4 needs product descriptions, FAQ content"
          PM_Action: "Pull Phase 4 copywriting forward, content-strategist starts early"
          Benefit: "When design-agent finishes mockups, copy is already ready (saves 2 days)"
    
    Skill_Based_Task_Assignment:
      Agent_Skill_Matrix:
        Design_Capabilities:
          design-agent:
            - "Visual design (expert)"
            - "UI/UX layout (expert)"
            - "Colour theory (expert)"
            - "Typography (advanced)"
            - "Accessibility (intermediate)"
          
          accessibility-specialist-agent:
            - "WCAG compliance (expert)"
            - "Assistive technology testing (expert)"
            - "Accessibility annotations (expert)"
            - "Visual design (basic)"
          
          landing-page-specialist-agent:
            - "Frontend HTML/CSS (expert)"
            - "Responsive design (expert)"
            - "Performance optimisation (advanced)"
            - "Visual design (intermediate)"
        
        PM_Assignment_Logic:
          For_Visual_Design_Work: "Assign to design-agent (highest skill level)"
          For_Accessibility_Audit: "Assign to accessibility-specialist-agent (expert)"
          For_Accessibility_Annotations: "accessibility-specialist OR design-agent (both capable)"
          For_Performance_Issues: "Assign to landing-page-specialist-agent OR performance-analyst-agent"
        
        Skill_Gap_Handling:
          If_No_Agent_Has_Required_Skill:
            - "PM flags skill gap to user"
            - "Options: Hire external expert, train existing agent, adjust requirements"
          
          If_Only_One_Agent_Has_Skill:
            - "PM identifies as bottleneck risk"
            - "PM considers cross-training another agent as backup"
      
      Task_Complexity_Matching:
        Simple_Tasks:
          Definition: "Well-defined, low ambiguity, routine work"
          Examples: "Image optimisation, alt text writing, meta description writing"
          Assignment: "Assign to any agent with basic skill level"
        
        Complex_Tasks:
          Definition: "High ambiguity, creative problem-solving, strategic thinking required"
          Examples: "Brand positioning, design system architecture, complex accessibility fixes"
          Assignment: "Assign to agent with expert skill level"
        
        PM_Guideline: "Match task complexity to agent expertise for optimal results"
    
    Burnout_Prevention:
      Workload_Limits:
        Maximum_Continuous_Work: "8 hours per day per agent"
        Maximum_Weekly_Work: "40 hours per week per agent"
        Mandatory_Breaks: "10 minute break every 2 hours of continuous work"
        
        PM_Enforcement:
          If_Agent_Approaching_Limit: "PM redistributes work to prevent overload"
          If_Agent_Exceeds_Limit: "PM blocks new task assignment, requires rest period"
      
      Quality_Of_Work_Monitoring:
        Early_Burnout_Indicators:
          - "Quality gate failure rate increases (agent making more mistakes)"
          - "Task completion time increases (agent slowing down)"
          - "Feedback responsiveness decreases (agent less engaged)"
        
        PM_Intervention:
          If_Indicators_Detected:
            - "PM reduces agent workload by 50% for recovery"
            - "PM assigns simpler tasks during recovery period"
            - "PM investigates root cause (too much work vs unclear requirements vs skill gap)"
    
    Crisis_Mode_Resource_Management:
      When_To_Activate:
        Triggers:
          - "Critical legal compliance issue discovered"
          - "Major quality failure requiring complete redesign"
          - "Launch deadline imminent with critical work remaining"
        
        PM_Declaration: "PM explicitly declares 'Crisis Mode Active' to all agents and user"
      
      Crisis_Mode_Changes:
        Resource_Allocation:
          Normal_Mode: "Agents work on scheduled tasks sequentially"
          Crisis_Mode: "All agents focus on crisis resolution, non-critical work paused"
        
        Communication:
          Normal_Mode: "Daily status updates"
          Crisis_Mode: "Hourly status updates, real-time coordination channel"
        
        Decision_Making:
          Normal_Mode: "PM follows standard approval process"
          Crisis_Mode: "PM has authority to make rapid decisions, inform user after"
        
        Timeline:
          Normal_Mode: "Follow planned schedule"
          Crisis_Mode: "All effort toward crisis resolution, deadline adjusted"
      
      Crisis_Exit_Criteria:
        Definition: "When is crisis resolved and normal mode resumed?"
        
        Criteria:
          - "Critical issue fully resolved and validated"
          - "Quality gates passed"
          - "No high-severity risks remaining"
          - "User confirms satisfied with resolution"
        
        PM_Action: "PM declares 'Crisis Mode Deactivated', agents return to normal schedule"

  # ---------------------------------------------------------------------------
  # 5. ENHANCED KNOWLEDGE MANAGEMENT
  # ---------------------------------------------------------------------------
  
  Enhanced_Knowledge_Management:
    Purpose: "Build institutional memory so future projects learn from past successes and failures"
    
    Project_Memory_System:
      What_To_Archive:
        Design_Decisions:
          - "Colour palettes chosen and rationale"
          - "Typography pairings and why they work"
          - "Layout patterns that tested well with users"
          - "Design elements that were rejected and why"
        
        Technical_Decisions:
          - "Frontend architecture choices"
          - "Performance optimisation techniques that worked"
          - "Accessibility solutions for specific issues"
          - "Browser compatibility workarounds"
        
        Process_Decisions:
          - "Timeline adjustments and reasons"
          - "Quality gate criteria that caught critical issues"
          - "Agent assignment patterns that worked well"
          - "Communication approaches that improved stakeholder buy-in"
        
        Client_Preferences:
          - "User's communication style (formal vs casual, frequency preference)"
          - "User's risk tolerance (conservative vs aggressive)"
          - "User's quality expectations (minimum viable vs exceptional)"
          - "User's decision-making speed (quick vs deliberate)"
        
        Outcome_Analytics:
          - "Final Lighthouse scores"
          - "User satisfaction ratings"
          - "Conversion rate metrics"
          - "Timeline: Planned vs Actual"
          - "Budget: Planned vs Actual"
      
      How_To_Archive:
        Documentation_Standards:
          Format: "Markdown files in structured directory"
          
          Directory_Structure:
            ```
            /project-memory/
              /2025-01-e-traveller-homepage/
                project-brief.md
                design-decisions.md
                technical-architecture.md
                lessons-learned.md
                outcome-metrics.md
                user-preferences.md
            ```
          
          Required_Sections:
            project-brief.md:
              - "Project goals and success criteria"
              - "Target audience and personas"
              - "Timeline and budget"
            
            design-decisions.md:
              - "Colour palette: [hex codes] - Rationale: [psychology reasoning]"
              - "Typography: [fonts] - Rationale: [readability, brand fit]"
              - "Layout patterns: [descriptions with screenshots]"
            
            technical-architecture.md:
              - "Frontend framework/approach used"
              - "Performance optimisations applied"
              - "Accessibility implementation details"
            
            lessons-learned.md:
              - "What went well (keep for next time)"
              - "What went wrong (avoid next time)"
              - "Unexpected challenges and solutions"
            
            outcome-metrics.md:
              - "Lighthouse scores: Performance X, Accessibility Y, SEO Z"
              - "User satisfaction: X/5"
              - "Timeline: Planned X days, Actual Y days"
              - "Quality gate pass rates"
        
        PM_Responsibility:
          - "PM creates project memory folder at project start"
          - "PM updates documentation weekly during project"
          - "PM completes final documentation within 1 week of project completion"
          - "PM ensures documentation is searchable and accessible"
      
      How_To_Retrieve:
        Search_Functionality:
          By_Project_Type: "All homepage redesigns"
          By_Industry: "All mobility scooter / medical equipment projects"
          By_Challenge: "All projects with accessibility crises"
          By_Outcome: "All projects with Lighthouse >95"
        
        PM_Usage:
          Before_New_Project:
            - "PM searches for similar past projects"
            - "PM reviews lessons-learned from those projects"
            - "PM identifies potential risks based on past patterns"
            - "PM reuses successful design/technical patterns"
          
          During_Project:
            - "PM references past solutions when similar challenges arise"
            - "PM compares current progress to similar past projects (benchmarking)"
          
          After_Project:
            - "PM adds new lessons learned to memory system"
            - "PM tags common patterns for easy future retrieval"
    
    Best_Practices_Library:
      Design_Best_Practices:
        Colour_Palettes_That_Work:
          E_commerce_Premium:
            - "Burgundy (#8B1538) + Gold (#D4AF37) - Converts 3.2%"
            - "Charcoal (#36454F) + Copper (#B87333) - Converts 2.9%"
          
          E_commerce_Modern:
            - "Electric Violet (#7B2D8F) + Coral (#FF6B6B) - Converts 3.4%"
            - "Navy (#1B2A41) + Mint (#4ECDC4) - Converts 2.7%"
          
          Documentation: "Includes conversion rate data, user testing feedback, use cases"
        
        Layout_Patterns_That_Work:
          Bento_Grid_Homepage:
            - "Asymmetric card layout, varying sizes"
            - "Mobile: Stacked vertical, Desktop: Masonry grid"
            - "Use case: When you want visual interest and modern aesthetic"
            - "Conversion lift: +15% vs standard three-column layout"
          
          Diagonal_Section_Dividers:
            - "Angled transitions between sections (7-15 degree angles)"
            - "Creates visual flow and movement"
            - "Use case: Breaking up long-scroll pages"
            - "User feedback: 'Feels more dynamic and engaging'"
        
        Typography_Pairings_That_Work:
          Premium_Professional:
            - "Playfair Display (serif headlines) + Raleway (sans-serif body)"
            - "Use case: Professional services, premium e-commerce"
          
          Modern_Friendly:
            - "Montserrat (sans-serif headlines) + Open Sans (sans-serif body)"
            - "Use case: SaaS, tech startups, modern brands"
      
      Technical_Best_Practices:
        Performance_Optimisations:
          Image_Optimisation:
            - "WebP format with JPG fallback"
            - "Responsive srcset (mobile: 800px, tablet: 1200px, desktop: 1920px)"
            - "Lazy loading for below-fold images"
            - "Result: 60-70% file size reduction, LCP <2.5s"
          
          Critical_CSS:
            - "Inline critical CSS in <head>"
            - "Async load non-critical CSS"
            - "Result: First Contentful Paint <1.8s"
        
        Accessibility_Solutions:
          Elderly_User_Optimisations:
            - "Font size: 18px minimum body text"
            - "Line height: 1.6-1.8 for readability"
            - "Touch targets: 48x48px (larger than standard 44x44px)"
            - "Contrast: 7:1 minimum (WCAG AAA)"
            - "Result: Task completion rate 90%+ for 65+ users"
    
    Mistake_Prevention_Database:
      Common_Mistakes_Logged:
        Design_Mistakes:
          Mistake: "Using medical blue colour palette"
          Why_Problematic: "Signals healthcare/medical device, not lifestyle brand"
          How_To_Detect: "PM scans for hex codes #0066CC, #0088FF, #6699CC in palette submissions"
          How_To_Prevent: "PM provides forbidden colour list upfront, gives positive alternative examples"
          Frequency: "Occurred in 3 of 5 projects before prevention implemented"
        
        Development_Mistakes:
          Mistake: "Building desktop-first, then shrinking to mobile"
          Why_Problematic: "Results in poor mobile UX, forced horizontal scroll, tiny touch targets"
          How_To_Detect: "PM reviews CSS for @media (max-width) queries instead of (min-width)"
          How_To_Prevent: "PM requires mobile-first CSS template, reviews first 100 lines of CSS"
          Frequency: "Occurred in 2 of 5 projects before prevention implemented"
        
        Process_Mistakes:
          Mistake: "Starting development before mockup approval"
          Why_Problematic: "Wastes dev time, requires rework, delays project"
          How_To_Detect: "PM checks for Phase 5 work before Phase 4 approval flag"
          How_To_Prevent: "PM implements hard gate - Phase 5 blocked until Phase 4 user approval received"
          Frequency: "Occurred in 1 of 5 projects before prevention implemented"
      
      PM_Usage:
        Before_Task_Assignment:
          - "PM checks mistake database for relevant mistakes"
          - "PM includes prevention guidance in task brief"
          - "PM sets up automated detection if available"
        
        After_Mistake_Occurs:
          - "PM logs mistake to database immediately"
          - "PM documents detection method and prevention strategy"
          - "PM updates future task briefs to prevent repeat"
    
    Client_Preference_Profiles:
      User_Profile_Template:
        Communication_Preferences:
          Update_Frequency: "Daily / Every 2 days / Weekly"
          Update_Format: "Email / Slack / Dashboard only"
          Detail_Level: "High-level summary / Detailed technical"
          Meeting_Preference: "Weekly sync calls / Async only / On-demand"
        
        Decision_Making_Style:
          Speed: "Quick (same-day decisions) / Moderate (2-3 days) / Deliberate (1 week+)"
          Involvement: "High (approves every detail) / Medium (approves major milestones) / Low (trusts PM)"
          Risk_Tolerance: "Conservative (avoid all risk) / Moderate / Aggressive (move fast, accept risk)"
        
        Quality_Expectations:
          Minimum_Acceptable: "WCAG AA, Lighthouse >80, Good enough to launch"
          Target_Quality: "WCAG AAA, Lighthouse >90, Professional quality"
          Exceptional_Quality: "Award-winning, Lighthouse >95, Industry-leading"
        
        Past_Feedback_Patterns:
          What_User_Loves:
            - "Bold colour choices that stand out"
            - "Data-driven design decisions"
            - "Proactive communication about risks"
          
          What_User_Dislikes:
            - "Generic designs that look like competitors"
            - "Surprises (prefers advance warning of issues)"
            - "Jargon without explanation"
      
      PM_Usage:
        At_Project_Start:
          - "PM reviews user's profile from past projects"
          - "PM adjusts communication style to match preferences"
          - "PM sets quality targets aligned with user expectations"
        
        During_Project:
          - "PM adapts based on user's feedback and behaviour"
          - "PM updates profile with new observations"
        
        At_Project_End:
          - "PM documents what worked well in this project"
          - "PM updates profile for future PM's reference"

  # ---------------------------------------------------------------------------
  # 6. AI AND TOOLING SUPPORT
  # ---------------------------------------------------------------------------
  
  AI_And_Tooling_Support:
    Purpose: "Reduce human error, free agent time, and scale quality assurance through automation"
    
    Automated_Compliance_Scanning:
      WCAG_Accessibility_Scanner:
        Tools:
          - "axe DevTools (automated accessibility testing)"
          - "WAVE (WebAIM's accessibility evaluation tool)"
          - "Pa11y (command-line accessibility tester)"
        
        Integration_Point: "After Phase 5 (frontend development), before Phase 6 (QA)"
        
        Automated_Checks:
          - "Contrast ratios (WCAG AAA: ≥7:1 for normal text, ≥4.5:1 for large text)"
          - "Alt text presence on all images"
          - "Form labels and ARIA attributes"
          - "Keyboard navigation support"
          - "Heading hierarchy (no skipped levels)"
          - "Touch target sizes (≥44x44px, ideally 48x48px)"
        
        PM_Workflow:
          Step_1: "PM triggers automated scan after frontend-dev-agent completes Phase 5"
          Step_2: "Scanner generates report with violations categorised by severity"
          Step_3: "PM reviews report, assigns critical/high violations back to frontend-dev-agent"
          Step_4: "PM blocks Phase 6 QA until all critical accessibility violations fixed"
          Step_5: "PM re-runs scan to validate fixes"
        
        Time_Saved: "Automated scan: 5 minutes vs Manual testing: 3-4 hours"
        Error_Reduction: "Catches 80-90% of accessibility issues before manual testing"
      
      Performance_Scanner:
        Tools:
          - "Lighthouse (Google's automated audit tool)"
          - "WebPageTest (real device testing)"
          - "Chrome DevTools Performance profiler"
        
        Integration_Point: "After Phase 5 (frontend development), repeated after optimisation"
        
        Automated_Metrics:
          Core_Web_Vitals:
            - "Largest Contentful Paint (LCP): Target <2.5s"
            - "First Input Delay (FID): Target <100ms"
            - "Cumulative Layout Shift (CLS): Target <0.1"
          
          Lighthouse_Scores:
            - "Performance: Target >90"
            - "Accessibility: Target 100"
            - "Best Practices: Target 100"
            - "SEO: Target 100"
        
        PM_Workflow:
          Step_1: "PM runs Lighthouse scan on mobile and desktop"
          Step_2: "If any score <90, PM assigns optimisation tasks to performance-analyst-agent"
          Step_3: "PM re-runs scan after optimisations applied"
          Step_4: "PM blocks deployment until Performance score >90"
        
        Automated_Recommendations:
          - "Scanner suggests specific optimisations (compress images, minify CSS, etc.)"
          - "PM forwards recommendations to appropriate agent"
          - "Agent implements recommendations, PM validates improvement"
      
      Legal_Compliance_Scanner:
        Tools:
          - "Custom ACL compliance checker (checks for fake testimonials, misleading claims)"
          - "Privacy policy validator (checks for required disclosures)"
          - "Cookie consent checker (GDPR/Privacy Act compliance)"
        
        Integration_Point: "After Phase 3 (design system) and Phase 5 (frontend development)"
        
        Automated_Checks:
          Testimonial_Verification:
            - "Scans for testimonial content"
            - "Flags any testimonial without consent flag in CMS"
            - "PM requires manual verification before approval"
          
          Misleading_Claims:
            - "Scans for absolute claims ('best', 'guaranteed', 'fastest')"
            - "Flags claims without supporting evidence"
            - "PM requires content-strategist-agent to add evidence or soften claim"
          
          Required_Legal_Pages:
            - "Checks for: Privacy Policy, Terms of Use, Return Policy, Warranty Info"
            - "Flags if any required page missing"
            - "PM blocks deployment until all legal pages present"
        
        False_Positive_Handling:
          - "Tool may flag legitimate claims as problematic"
          - "PM reviews flagged items manually"
          - "PM marks false positives as exceptions (with documentation)"
    
    Device_Emulation_Testing:
      Automated_Multi_Device_Testing:
        Tools:
          - "BrowserStack (real device cloud testing)"
          - "Playwright (automated browser testing)"
          - "Chrome DevTools Device Emulation"
        
        Test_Matrix:
          Mobile_Devices:
            - "iPhone 13 (375x667, iOS 17)"
            - "iPhone 13 Pro Max (414x896, iOS 17)"
            - "Samsung Galaxy S21 (360x800, Android 13)"
            - "Samsung Galaxy S21 Ultra (412x915, Android 13)"
          
          Tablets:
            - "iPad 10.2\" (810x1080, iPadOS 17)"
            - "Samsung Galaxy Tab (800x1280, Android 12)"
          
          Desktop:
            - "Windows Chrome (1920x1080)"
            - "Mac Safari (1920x1080)"
            - "Windows Firefox (1920x1080)"
            - "Windows Edge (1920x1080)"
        
        Automated_Test_Scenarios:
          Visual_Regression:
            - "Capture screenshots on all devices"
            - "Compare to approved baseline"
            - "Flag visual differences >5% pixel change"
          
          Functional_Testing:
            - "Verify navigation works (all links clickable)"
            - "Verify forms submit successfully"
            - "Verify images load correctly"
            - "Verify no JavaScript errors in console"
          
          Responsive_Testing:
            - "Verify no horizontal scroll on any device"
            - "Verify touch targets ≥44x44px on touch devices"
            - "Verify text readable without zoom on all devices"
        
        PM_Workflow:
          Step_1: "PM triggers automated test suite after Phase 5 (frontend development)"
          Step_2: "Test suite runs in 10-15 minutes, generates report"
          Step_3: "PM reviews failures, assigns fixes to frontend-dev-agent"
          Step_4: "PM re-runs tests after fixes applied"
          Step_5: "PM blocks Phase 6 QA until all automated tests pass"
        
        Time_Saved: "Automated testing: 15 minutes vs Manual testing on 10 devices: 4-5 hours"
    
    Competitor_Site_Monitoring:
      Automated_Competitor_Tracking:
        Tools:
          - "Visual Ping (monitors competitor site changes)"
          - "SEMrush (tracks competitor keyword rankings)"
          - "BuiltWith (detects competitor technology changes)"
        
        What_To_Monitor:
          Design_Changes:
            - "Competitor launches new design"
            - "Competitor changes colour scheme"
            - "Competitor adds new features"
            
            PM_Alert: "Notification when visual change detected"
            PM_Action: "Review change, ensure our design remains differentiated"
          
          SEO_Changes:
            - "Competitor ranks higher for target keyword"
            - "Competitor captures featured snippet"
            - "Competitor adds new content targeting our keywords"
            
            PM_Alert: "Weekly SEO position report"
            PM_Action: "If competitor overtakes us, assign seo-specialist-agent to improve content"
          
          Technology_Changes:
            - "Competitor migrates to new platform"
            - "Competitor adds new technology (chatbot, AR, etc.)"
            
            PM_Alert: "Monthly technology report"
            PM_Action: "Evaluate if new technology provides competitive advantage worth adopting"
        
        PM_Usage:
          Monthly_Review: "PM reviews competitor changes in monthly strategy meeting"
          Differentiation_Check: "PM ensures our design doesn't accidentally copy competitor changes"
          Innovation_Ideas: "PM identifies gaps in competitor offerings as opportunities"
    
    LLM_Powered_Review_Bots:
      Content_Tone_Checker:
        Purpose: "Ensure brand voice consistency across all content"
        
        Integration_Point: "After content-strategist-agent writes copy, before design-agent uses it"
        
        Automated_Checks:
          Brand_Voice_Alignment:
            Target_Voice: "Empowering, friendly, confident (NOT clinical, medical, institutional)"
            
            Positive_Indicators:
              - "Active voice ('You choose your independence' vs 'Independence can be chosen')"
              - "Benefit-focused ('Explore your neighbourhood' vs 'Travel up to 20km')"
              - "Aspirational language ('Your adventures await' vs 'Mobility solution available')"
            
            Negative_Indicators:
              - "Medical jargon ('ambulation device', 'mobility aid', 'assistive technology')"
              - "Passive voice ('It can be used for...')"
              - "Clinical language ('patient', 'condition', 'disability')"
          
          Reading_Level_Check:
            Target: "Flesch-Kincaid Grade 7-8 (accessible to elderly users)"
            
            If_Above_Grade_8: "LLM suggests simpler alternatives"
            Example:
              Original: "Utilise this ambulatory apparatus to facilitate independent perambulation"
              Simplified: "Use this scooter to travel independently"
          
          Terminology_Consistency:
            Preferred_Terms: "mobility scooter (NOT wheelchair, NOT mobility aid)"
            Forbidden_Terms: "patient, disability, handicap, medical device"
            
            If_Forbidden_Term_Detected: "LLM flags and suggests alternative"
        
        PM_Workflow:
          Step_1: "content-strategist-agent submits copy"
          Step_2: "LLM review bot analyses tone and flags issues"
          Step_3: "PM reviews flags, sends back to content-strategist-agent if major issues"
          Step_4: "PM approves if tone aligned with brand voice"
        
        Time_Saved: "Automated tone check: 2 minutes vs Manual review: 30-45 minutes"
      
      Accessibility_Language_Checker:
        Purpose: "Ensure alt text and ARIA labels are descriptive and helpful"
        
        Integration_Point: "After frontend-dev-agent adds alt text, before accessibility-specialist-agent review"
        
        Automated_Checks:
          Alt_Text_Quality:
            Bad_Alt_Text_Patterns:
              - "Generic: 'image', 'photo', 'picture'"
              - "Redundant: 'image of a...' (screen reader already says 'image')"
              - "Empty when image is meaningful"
              - "Too long (>150 characters)"
            
            Good_Alt_Text_Patterns:
              - "Descriptive: 'Red mobility scooter on beach boardwalk with senior woman smiling'"
              - "Concise but complete"
              - "Context-appropriate (alt text changes based on page context)"
            
            If_Bad_Pattern_Detected: "LLM suggests improved alt text"
            Example:
              Bad: "image"
              Suggested: "Kymco Mini Comfort mobility scooter in burgundy colour with adjustable seat"
          
          ARIA_Label_Quality:
            Bad_ARIA_Patterns:
              - "Vague: 'button', 'link'"
              - "Technical: 'nav-toggle-btn'"
            
            Good_ARIA_Patterns:
              - "Descriptive: 'Add to cart'"
              - "Action-oriented: 'Open main menu'"
            
            If_Bad_Pattern_Detected: "LLM suggests improved ARIA label"
        
        PM_Workflow:
          Step_1: "frontend-dev-agent completes Phase 5 with alt text and ARIA labels"
          Step_2: "LLM review bot analyses all alt text and ARIA labels"
          Step_3: "Bot generates report with issues flagged and suggestions"
          Step_4: "PM assigns fixes to frontend-dev-agent"
          Step_5: "PM validates improvements"
        
        Quality_Improvement: "Increases alt text quality score from 60% to 95% on average"
      
      SEO_Content_Checker:
        Purpose: "Ensure on-page SEO best practices followed"
        
        Integration_Point: "After seo-specialist-agent optimises page, before deployment"
        
        Automated_Checks:
          Keyword_Optimisation:
            - "Primary keyword appears in H1: Yes/No"
            - "Primary keyword appears in first paragraph: Yes/No"
            - "Primary keyword density: X% (target: 0.5-2%)"
            - "Secondary keywords present: Yes/No"
            
            If_Not_Optimal: "LLM suggests specific improvements"
            Example:
              Issue: "Primary keyword 'mobility scooter australia' not in H1"
              Suggestion: "Change H1 from 'Find Your Perfect Scooter' to 'Find Your Perfect Mobility Scooter in Australia'"
          
          Meta_Data_Optimisation:
            - "Title length: X characters (target: 50-60)"
            - "Description length: X characters (target: 140-155)"
            - "Title contains primary keyword: Yes/No"
            
            If_Not_Optimal: "LLM generates improved meta data"
            Example:
              Current_Title: "Find Your Scooter | E-Traveller" (35 chars - too short)
              Suggested: "Best Mobility Scooters in Australia | E-Traveller 2025" (58 chars - optimal)
          
          Content_Structure:
            - "Heading hierarchy correct: Yes/No"
            - "Internal links present: X (target: 3-5)"
            - "External authority links: X (target: 1-2)"
            - "Image count: X (target: 1 per 300 words)"
            
            If_Not_Optimal: "LLM suggests structure improvements"
        
        PM_Workflow:
          Step_1: "seo-specialist-agent completes optimisation"
          Step_2: "LLM review bot analyses SEO factors"
          Step_3: "Bot generates SEO score (0-100) with specific recommendations"
          Step_4: "PM requires score >90 before approval"
          Step_5: "If <90, PM assigns improvements to seo-specialist-agent"
        
        Quality_Improvement: "Increases average page SEO score from 75 to 93"
    
    Tool_Integration_Recommendations:
      CI_CD_Pipeline_Integration:
        Continuous_Integration_Checks:
          On_Every_Code_Commit:
            - "Run automated accessibility scan (axe)"
            - "Run Lighthouse performance test"
            - "Check for forbidden keywords in code comments"
            - "Validate HTML/CSS syntax"
          
          Pass_Criteria:
            - "Zero critical accessibility violations"
            - "Lighthouse performance >85"
            - "Zero HTML/CSS errors"
          
          If_Fail: "Block commit, require fixes before merge"
        
        Continuous_Deployment_Checks:
          Before_Deployment:
            - "Run full test suite (accessibility, performance, functionality)"
            - "Check for legal compliance issues"
            - "Validate all quality gates passed"
          
          Pass_Criteria:
            - "All automated tests pass"
            - "All quality gates signed off by PM"
            - "User approval documented"
          
          If_Fail: "Block deployment, escalate to PM"
        
        PM_Oversight:
          - "PM configures CI/CD pipeline with quality gates"
          - "PM reviews automated test results daily"
          - "PM adjusts criteria based on project-specific needs"
      
      Monitoring_And_Alerting:
        Post_Deployment_Monitoring:
          What_To_Monitor:
            - "Lighthouse scores (daily scans)"
            - "Core Web Vitals (real user data)"
            - "JavaScript errors (error tracking)"
            - "Accessibility violations (periodic scans)"
            - "SEO rankings (weekly tracking)"
          
          Alert_Triggers:
            - "Lighthouse score drops >5 points"
            - "Core Web Vitals exceed thresholds (LCP >2.5s, etc.)"
            - "JavaScript error rate >1%"
            - "Accessibility violations detected"
            - "Primary keyword ranking drops >3 positions"
          
          PM_Response:
            - "PM receives alert within 15 minutes of trigger"
            - "PM investigates cause (recent deploy? traffic spike? third-party issue?)"
            - "PM assigns appropriate agent to fix issue"
            - "PM monitors until issue resolved"
        
        Time_To_Detection: "Automated monitoring: 15 minutes vs Manual discovery: Days/weeks"

# End of Advanced PM Competencies
