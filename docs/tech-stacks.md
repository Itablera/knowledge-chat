# docs/tech-stacks

## Background
My experience in this area mainly comes from working with ready-made solutions such as OpenAI API and PaaS services like Azure AI Services. These services are great for getting started quickly, but they can be expensive and obscuring how the underlying technology works.

Ambition is that this project should be modular and make it easy to use different hosting options, including local hosting. 

## Tech reviewed
- Ollama - Run AI models locally
- Ollama NodeJS package - Convenient package for running Ollama operations
- Qdrant - Vector search engine
- Frontmatter - Markdown metadata parser
- llama-index - Python (and node) package for indexing data into Qdrant
- transformers.js - Hugging Face's transformers in JavaScript
- langChain.js - LLM processing in JavaScript
- Tessaract - OCR engine
- OpenAI Clip - Vision model, used for image to text
- FastAPI - Python web framework
- Redis + FastAPI-limiter - Rate limiting
- NextJS - React framework

## Process

I started out with a Next.JS app and Ollama installed on local host and then started to play with various methods and packages to parse markdown and index data into Qdrant.

Quite soon I realized that a Python runtime would be better suited as backend for LLM processing and Qdrant indexing due to more extensive community and better performance. However, as I'm far from fluent in Python I needed some ready-made frameworks such as FastAPI.

With a separate backend I took the chance to minimize the frontend by using Vite + React instead of Next.JS. This also made it easier to use the same backend for other projects.

In the end it was apparent that this is not a single capability project but a stack of different services. Considerations around hosting, scaling and maintainability is needed.

## Resulting stack

- Frontend
  - React
  - Vite
  - TypeScript
- Backend
  - FastAPI
  - Redis + FastAPI-limiter
- Vector search
  - Qdrant
- LLM engine
  - Ollama
- Model processing
  - llama-index - index documents
  - langChain - LLM processing
- Image processing
  - Tessaract
  - OpenAI Clip