# PDF Info API

Small FastAPI application that accepts a PDF upload and returns basic information (page count, total characters, and extracted text).

Key file:
- Application entry: [main.py](main.py) (endpoint function: [`info_pdf`](main.py))

## Requirements

Install dependencies from the provided file:

```bash
pip install -r requirements.txt

Run (development)
Start the app with Uvicorn:

uvicorn main:app --reload -

By default the server is available at http://127.0.0.1:8000/.

API
POST /pdf-info

Form field: file (the uploaded PDF)
Response: JSON with filename, pages, characters, and text

#example curl
curl -X POST -F "file=@/path/to/file.pdf" http://127.0.0.1:8000/pdf-info

#Example response:

{
  "filename": "file.pdf",
  "pages": 3,
  "characters": 1024,
  "text": "Full extracted text ..."
}