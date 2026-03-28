## Real-Time Voice Sales Assistant

### Overview

The Real-Time Voice Sales Assistant is an AI-powered conversational sales agent that simulates an expert seller. It listens to customer questions, retrieves relevant product information, and responds with natural speech in near real time. The system was built for a Flipkart hackathon and is designed to deliver an engaging, informative shopping experience.

This solution combines retrieval-augmented generation (RAG), speech-to-text (STT), text-to-speech (TTS), and large language models (LLMs) to generate accurate, personalized responses from product and policy documents.

### Features

- **Fast Voice Interaction**: Handles customer questions with low latency for smooth conversational flow.
- **Context-Aware Dialogue**: Keeps track of the conversation and responds consistently across multiple turns.
- **Natural Speech Output**: Provides audio responses that feel more human than robotic.
- **Personalized Recommendations**: Suggests products and options tailored to the user’s needs.
- **Multiple Seller Styles**: Can adapt its tone to different seller personas, such as tech expert or fashion consultant.
- **Data-Driven Answers**: Uses product details, pricing, and policy documents to support responses.
- **Support for Offers**: Can discuss deals, bundles, and customer concerns in a sales-focused way.

### Architecture

The system is built from several core components:

1. **Speech-to-Text (STT)**: Captures customer audio and converts it into text using Google Cloud Speech-to-Text.
2. **Retrieval-Augmented Generation (RAG)**: Searches the indexed document store and provides relevant context to the language model.
3. **Text-to-Speech (TTS)**: Converts generated responses into clear, natural audio using Google Cloud Text-to-Speech.
4. **Product Data Integration**: Ingests product, privacy, and return policy documents to support accurate answer generation.

### Technology Stack

- **LangChain**: For document processing, chunking, and retrieval orchestration.
- **Google Cloud Speech-to-Text**: For converting live voice input into text.
- **Google Cloud Text-to-Speech**: For generating spoken responses.
- **Hugging Face Models**: For generating conversational text output.
- **Vector Database**: For efficient semantic retrieval of product documents.
- **BeautifulSoup**: For scraping and parsing HTML source documents.

### How It Works

1. **Data Processing**: Product and policy content is collected, cleaned, chunked, and indexed into a vector database.
2. **Speech Capture**: Customer voice input is recorded and transcribed into text.
3. **Response Generation**: The system retrieves relevant context, passes it to the model, and creates a coherent answer.
4. **Speech Playback**: The generated response is converted into speech and played back to the customer.

### Key Components

- **`document_search.ipynb`**: Prepares product and policy data, splits text into chunks, and builds the retrieval index.
- **`first.py`**: Handles speech capture, transcription, and initial query processing.
- **`reader.py`**: Retrieves relevant documents and generates the AI response.
- **`Frontend/main.py`**: Provides the interface for voice interaction and user experience.

### Evaluation Criteria

1. **Naturalness and Fluency**: Responses should sound smooth and conversational.
2. **Accuracy and Product Knowledge**: Output should be factually correct and informative.
3. **Responsiveness**: The system should reply quickly to maintain engagement.
4. **Context Awareness**: The assistant should follow the conversation and preserve the seller persona.
5. **Problem Solving**: Customer questions and objections must be addressed clearly and helpfully.
6. **Personalization**: Recommendations should reflect the customer’s intent and context.
7. **Seller Realism**: The assistant should behave like a confident, knowledgeable salesperson.
