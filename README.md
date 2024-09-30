# GenAI-based RAG Application
- Develop a real-time or static RAG-based LLM application completely using Pathway LLM App templates or Pathway with Llamaindex / Pathway with Langchain
- This demo shows how to create a RAG application using Pathway that provides always up-to-date knowledge to your LLM without the need for a separate ETL
  
- ![Pathway_01](https://github.com/user-attachments/assets/b1c0291f-5662-4601-a421-5bd499ce11ee)

- This demo allows you to:
- 📂 **Set up a vector store** for real-time indexing of documents from Google Drive, Microsoft 365 SharePoint, or local directories.
- 🤖 **Integrate an OpenAI LLM** with your knowledge base for seamless access to intelligent responses.
- 🎯 **Receive accurate and precise answers** to your queries with high-quality information.
- 🗂️ **Easily ask questions** about specific folders, files, or all documents using powerful filtering options.
- ✍️ **Use LLMs via API** to automatically summarize large texts.
- 👁️‍🗨️ **Get an executive summary** from multiple files, giving you a quick overview of all relevant knowledge.

  # How it works (Understanding the RAG pipeline)
  Here’s the bullet-point list with emojis:

- 📄 **app.py**: The main application code, written in Python, using Pathway.
  
  ![llm_01_new](https://github.com/user-attachments/assets/74c7d887-e46f-4cec-994a-4d61747987bc)

  ![llm_02_new](https://github.com/user-attachments/assets/88bbb203-b5a8-425b-ad26-5377bac35e82)

  ![llm_03_new](https://github.com/user-attachments/assets/ecd0222a-d32b-400d-922a-6b78834675ab)

- 🛠️ **config.yaml**: Configuration file for data sources, OpenAI LLM model, and the web server. Customize this to modify the LLM model, use Google Drive data, or adjust filesystem directories for indexing.

  ![llm_04_new](https://github.com/user-attachments/assets/162faea6-9311-4039-b96b-9aa8515a14f1)

  ![google_drive_key](https://github.com/user-attachments/assets/32183136-08da-4fd3-8a51-0dfce9e87b92)

  **Google Drive Data Source**
  - The section config must contain two main parameters:
- **object_id**, containing the ID of the folder that needs to be indexed. It can be found from the URL in the web interface, where it's the last part of the address. For example, the publicly available demo folder in Google Drive has the URL https://drive.google.com/drive/folders/1cULDv2OaViJBmOfG5WB0oWcgayNrGtVs. Consequently, the last part of this address is 1cULDv2OaViJBmOfG5WB0oWcgayNrGtVs, hence this is the object_id you would need to specify.
  - **service_user_credentials_file**, containing the path to the credentials files for the Google service account. To get more details on setting up the service account and getting credentials, you can also refer to this tutorial.
 
- 📋 **requirements.txt**: Contains dependencies for the pipeline. Use with `pip install -r` to set up the environment locally.
- 🗝️ **.env**: Environment variables configuration file where the **OpenAI key** is stored.
- 📁 **data/**: A folder with example files for running test cases. 
- 🐋 **Dockerfile**: Docker configuration for running the pipeline inside a container.
- docker build -t rag .
- docker run -v `pwd`\C\Users\sanja\llm-app\examples\pipelines\demo-question-answering:\appC\Users\sanja\llm-app\examples\pipelines\demo-question-answering -p 8000:8000 rag
- **Listing & Run the RAG pipeline**
- Invoke-WebRequest -Uri 'http://localhost:8000/v1/pw_list_documents' `
                  -Method POST `
                  -Headers @{ "accept"="/"; "Content-Type"="application/json" } `
                  -Body '{}'
  
- Invoke-RestMethod -Method POST `
  -Uri 'http://localhost:8000/v1/pw_ai_answer' `
  -Headers @{ "accept"="/"; "Content-Type"="application/json" } `
  -Body '{"prompt": "What is Sanjay Singh CPI?"}'
  
  **Answer** 🤖: 7.92
  
  ![Final_llm_output](https://github.com/user-attachments/assets/953f0c57-f1a1-4d91-a92e-a73e1ee1ba03)


  # Insight Deep Dive
  

https://github.com/user-attachments/assets/45877b11-3551-4b90-9f34-a2a5d7d02737

1. **Flexibility & Versatility**:
Solution is flexible and can cater to different user needs, such as those requiring real-time updates or those prioritizing performance stability

2. **Ease of Use & Efficiency**:
The use of templates and terms like seamless integration reflects a strong focus on developer efficiency. These phrases indicate that users can quickly build or deploy LLM applications without needing extensive setup or customization, which is a significant selling point for time-conscious developers or businesses.

3. **Enhancement & Capabilities**:
Words like enhance and capabilities reflect the potential for growth and improvement when using these tools. Pairing Pathway with powerful frameworks like Langchain and Llamaindex underscores the ability to unlock more advanced functionalities, appealing to those seeking more than just basic LLM operations.

4. **Performance & Precision**:
Phrases like fast and accurate responses highlight the importance of performance and precision in LLM-based applications. In the context of RAG systems, fast retrieval and the ability to generate correct and relevant answers are key to user satisfaction.

6. **Real-Time Functionality**:
The consistent mention of real-time processing (both in the context of RAG-based apps and document indexing) shows that the solution is built with a strong focus on speed and immediate availability of information, which is crucial for use cases requiring instant feedback.

**Conclusion**:
The overall messaging in these sentences reflects a developer-friendly, performance-oriented, and highly flexible solution. The focus on real-time capabilities, efficiency through templates, and advanced integrations with tools like Llamaindex and Langchain positions this system as both cutting-edge and accessible to a wide range of developers or businesses looking to create powerful LLM-based applications.

# Thank You

  
