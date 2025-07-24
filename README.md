# MindForgeAgent

## 1. Overview

**MindForge** is a multi-agent collaborative system specifically designed for emotion analysis and journal processing. The system is managed by a central coordinator (Supervisor Agent) that orchestrates multiple specialized agents to perform tasks such as:

- Emotional diary analysis  
- Mood tracking  
- Theme extraction  
- Report generation  

By decomposing complex tasks into smaller, specialized components, MindForge efficiently processes user requests and provides deep emotional insights and personalized analysis.

---

## 2. System Architecture

MindForge employs a **centralized coordination with distributed execution** architecture:



                 +-------------------+
                 | supervisor_agent  |
                 | (Task Coordinator)|
                 +-------------------+
                          |
          +---------------+---------------+
          |               |               |
+-----------------+ +------------+ +---------------+
| summarize_agent | | emotion_   | | topic_agent   |
| (diary        | | agent      | | (Theme        |
|  Summary)       | | (Emotion   | |  Analysis)    |
+-----------------+ |  Analysis) | +---------------+
                    +------------+         |
                          |                |
                    +------------------+
                    | report_agent     |
                    | (Report          |
                    |  Generation)     |
                    +------------------+


---

## 3. Agents Introduction

### 3.1 Supervisor Agent

The **Supervisor Agent** serves as the central coordinator of the system and is responsible for:

1. Analyzing the user's original request  
2. Determining which specialized agents are needed  
3. Coordinating workflows between agents  
4. Integrating outputs and returning final results  

---

### 3.2 Emotion Agent

The **Emotion Agent** conducts emotional analysis based on **Plutchik's Wheel of Emotions**. It is capable of:

1. Providing quantitative scores for 8 basic emotion dimensions  
2. Detecting complex emotion combinations and intensity levels  
3. Tracking emotional trends over time  
4. Offering detailed emotional explanations  

---

### 3.3 Topic Agent

The **Topic Agent** specializes in theme and keyword extraction. It performs:

1. Theme analysis across documents  
2. Keyword and concept extraction  
3. Topic clustering and classification  
4. Foundation building for word clouds or knowledge graphs  

---

### 3.4 Report Agent

The **Report Agent** synthesizes all analysis results and generates comprehensive reports by:

1. Transforming raw data into structured formats  
2. Generating data visualizations (charts, graphs, etc.)  
3. Providing insights and recommendations  
4. Supporting various report formats  

---

## 4. Workflow Example

**User Request:**

> _"I need to write an emotional journal about how meditation helps reduce anxiety, and analyze my emotional state from the past week."_

**Step-by-step Process:**

1. **Supervisor Agent** analyzes the request and delegates tasks to:
   - `summarize_agent` → process the journal
   - `emotion_agent` → analyze emotional states
   - `topic_agent` → extract themes
   - `report_agent` → generate the report  

2. **User writes the journal**

3. Agents execute:
   - `summarize_agent` → creates journal summary  
   - `emotion_agent` → evaluates emotions in the entry  
   - `topic_agent` → extracts terms like _“meditation”_, _“anxiety”_

4. For past emotional records:
   - `emotion_agent` → analyzes logs from the past week  
   - `topic_agent` → identifies weekly recurring themes  

5. Final stage:
   - `report_agent` integrates all findings into a polished report  
   - `supervisor_agent` returns the final report to the user  

---

## 5. Technical Implementation Notes

The codebase includes **JSON-based functional definitions** for each agent, which contain:

1. Agent name and unique identifier  
2. Function descriptions  
3. Expected input parameters  
4. Usage examples  

These agent definition files enable the `supervisor_agent` to:

- Discover available agents  
- Understand their capabilities  
- Properly invoke them with structured input  

