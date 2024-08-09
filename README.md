# CrewAI
Blood Test Analysis Automation: Technical Workflow

This Jupyter Notebook is designed to automate the process of analyzing blood test reports and
generating personalized health recommendations based on the extracted data. The workflow
integrates CrewAI, a sophisticated task automation and delegation library, with PyPDF2 for
extracting text from PDF documents. Additional utilities are employed for web-based research
and data retrieval, ensuring a comprehensive analysis.

**Workflow Approach:**

**1. PDF Blood Test Report Text Extraction:**
- The notebook leverages PyPDF2 to read and extract text from specific pages of a PDF blood
test report. This is particularly useful when dealing with large documents where only certain
pages contain relevant medical data. The extracted text is parsed and pre-processed for
downstream tasks.

**2. Agent and Task Orchestration:**
- Three distinct agents are defined within the CrewAI framework, each serving a specialized
role in the analysis pipeline:
- Blood Test Analyst: Responsible for interpreting the extracted test results and identifying
key health indicators.
- Article Researcher: This agent conducts targeted web searches to gather additional
information related to the identified health indicators.
- Health Advisor: Based on the findings of the previous agents, this agent formulates health
recommendations tailored to the patient’s needs.
- Tasks are meticulously crafted and assigned to these agents, ensuring a logical flow of
information and task dependencies.

**3. Task Execution and Contextual Data Flow:**
- The task execution is managed by forming a Crew composed of the defined agents. Each
task is executed in sequence, with the output of one task providing necessary context for the
subsequent tasks. This sequential execution ensures that each agent operates with the most
relevant and up-to-date information.

**Detailed Execution Steps:**

**1. Package Installation:**
- Ensure that Python is correctly installed on your system. The notebook relies on several
external packages, which must be installed via pip. Execute the following command to install the
required dependencies:

**pip install crewai PyPDF2**

**2. API Key Configuration:**
- Prior to running the notebook, configure the necessary API keys for external services.
Replace the placeholders in the notebook with your actual API keys. The relevant lines to
update are:
**os.environ["SERPER_API_KEY"] = "<your_serper_api_key>"**
**os.environ["OPENAI_API_KEY"] = "<your_openai_api_key>"**
  
**3. PDF Blood Test Report Preparation:**
- Download the blood test report you wish to analyze. Update the `pdf` variable in the
notebook to reflect the correct file path. This file path directs the PyPDF2 tool to the correct
document for text extraction.

**4. Notebook Execution:**
- Execute the notebook cells sequentially or all at once. Each cell represents a discrete step in
the analysis pipeline. The notebook is designed to handle errors gracefully, ensuring a smooth
execution process.

**5. Reviewing and Interpreting Results:**
- Upon successful execution, the notebook will generate a summary of the blood test results
along with health recommendations based on external articles. The results will be displayed in a
structured format, allowing for easy interpretation and further analysis.
Note: Due to token limitations, the notebook is configured to analyze specific pages (e.g., pages
1 and 3) of the blood test report. These pages typically contain the majority of the relevant test
data, ensuring a focused and efficient analysis
