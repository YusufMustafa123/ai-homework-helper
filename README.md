# ai-homework-helper
AI homework helper that uses study notes and the SPUR API to explain school topics in simple language.
# AI Homework Helper

## Project Overview

AI Homework Helper is a simple AI-powered study assistant designed to help students understand their study notes. It uses retrieval-augmented generation (RAG) to find relevant information in notes and sends that information to an AI model to generate simple answers.

## Problem It Solves

Students sometimes struggle to find answers in long study notes. This project helps students ask questions in everyday language and receive short, easy-to-understand answers based on their notes.

## How It Works

1. **Load notes:** The project reads study notes from a text file.
2. **Split and index:** The notes are divided into smaller chunks and stored in a searchable index.
3. **Retrieve information:** A keyword-based search finds relevant note sections for a question.
4. **Generate an answer:** The retrieved notes are sent to an AI model through the SPUR inference API.
5. **Handle missing information:** The improved prompt instructs the AI to say when the answer cannot be found in the supplied notes.

## Technologies Used

- Python
- Google Colab
- SPUR inference API
- OpenAI-compatible Python client
- JSON and text files
- Retrieval-augmented generation (RAG)

## Evaluation

The project was tested using 20 questions: 10 answerable from the notes and 10 that should be rejected because the notes do not contain the answers.

The preliminary behaviour check produced these results:

| Version | Questions passed | Behaviour score |
|---|---:|---:|
| Baseline | 11/20 | 55% |
| Improved | 20/20 | 100% |

These are preliminary behaviour scores, not complete factual-accuracy scores. Further testing is needed to verify that every answer is correct and that unsupported answers are consistently rejected.

## Limitations

- The project currently uses a small science notes file.
- Keyword-based retrieval may miss relevant information when questions use different wording.
- AI-generated answers can still be incorrect.
- The preliminary evaluation does not fully measure factual accuracy.
- The project should be tested with more subjects and a wider range of questions.

## How to Run

1. Open the project's Google Colab notebook.
2. Configure the `SPUR_API_KEY` secret in Colab.
3. Run the notebook cells in order.
4. Load the study notes and create the index.
5. Ask questions using the homework helper function.
6. Run the evaluation cells to test the project.

Never publish your API key in this repository.

## Future Improvements

- Improve retrieval accuracy.
- Expand the evaluation dataset.
- Measure factual accuracy as well as refusal behaviour.
- Add structured request logging and a quality alert.
- Test with notes from additional subjects.
