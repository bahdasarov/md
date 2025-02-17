```mermaid
graph TD
  %% Facade as the Core
  A[Facade: Core of the Application] -->|Delegates request| B[Chain of Responsibility]
  
  %% Chain of Responsibility handles step-by-step processing
  B -->|1. Validate Request| C[Filter Request]
  C -->|2. Search in Document Base| D[Search Documents]
  D -->|3. Generate LLM Response| E[Generate LLM Response]
  E -->|4. Format Citations & Charts| F[Format Citations & Charts]
  
  %% Observer collects results and streams them
  F -->|Sends output to| G[Observer: Stream Queue]
  G -->|Streams final response| H((User))

  %% Styling
  A -->|Grows with new features| B
  style A fill:#ffcc00,stroke:#333,stroke-width:2px
  style B fill:#ff9966,stroke:#333,stroke-width:2px
  style G fill:#66ccff,stroke:#333,stroke-width:2px


### **Explanation of Flow**
1️⃣ **Facade** receives the request and **delegates it** to Chain of Responsibility.  
2️⃣ **Chain of Responsibility** breaks the task into **sequential steps**:  
   ✅ **Filtering the request**  
   ✅ **Searching the document base**  
   ✅ **Generating an LLM-based response**  
   ✅ **Formatting citations & diagrams**  
3️⃣ **Observer** **listens** to these stages and **collects results**.  
4️⃣ **Observer streams** the final formatted Markdown back to the user.  

This architecture is highly **scalable** 🚀, **modular** 🔥, and **efficient for streaming responses** 📡.

Would you like me to enhance it with an example **Python implementation**? 😊
