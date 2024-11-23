# FastAPI Report Generator

The **FastAPI Report Generator** is a modern web application that uses Google’s Gemini 1.5 AI model to generate detailed reports on various topics. This application allows users to easily request reports, which include detailed historical information, and receive AI-generated content via a simple REST API built with **FastAPI**.

## Features:
- **AI-Powered Reports**: Automatically generates in-depth reports on any given topic using the powerful Google Gemini 1.5 model.
- **FastAPI Framework**: A fast, easy-to-use framework that powers the backend of the application.
- **Customizable Input**: Supports any topic of your choice; just provide the topic, and the AI handles the rest.
- **Robust Error Handling**: Proper error responses with status codes and messages to ensure smooth usage.
- **Scalable**: Designed to handle high traffic and can be easily deployed in production environments.

## Setup Instructions:

### 1. Clone the Repository
Start by cloning the repository to your local machine:
```bash
git clone https://github.com/your-username/fastapi-report-generator.git
cd fastapi-report-generator
```

### 2. Install Dependencies
Install all the required Python dependencies by running:
```bash
pip install -r requirements.txt
```

### 3. Environment Configuration
- **Gemini API Key**: To use the Google Gemini AI service, you need an API key.
  1. Go to your [Google Cloud Console](https://console.cloud.google.com/).
  2. Create a new project or use an existing one.
  3. Enable the Gemini API and generate an API key.
  4. Add the key to your environment variables as follows:
     ```bash
     export GEMINI_API_KEY="your_api_key_here"
     ```
     Alternatively, you can set it directly in your `.env` file or any other secure way of storing environment variables.

### 4. Run the FastAPI Application
With everything set up, you can now start the FastAPI app by running:
```bash
uvicorn main:app --reload
```
This will launch the server locally. By default, the app will be accessible at `http://127.0.0.1:8000`.

### 5. Testing the API
You can test the API directly via tools like **Postman** or **curl**, or use the interactive API docs provided by FastAPI at `http://127.0.0.1:8000/docs`.

---

## API Usage

Once the server is running, you can interact with the API to generate reports by sending a POST request to the `/generatereport/` endpoint.

### Endpoint: `/generatereport/`
**Method**: `POST`

### Request Format
The request should contain a JSON body with the `topic` key, which specifies the subject of the report.

#### Example Request:
```json
{
  "topic": "Artificial Intelligence"
}
```

- **`topic`**: A string representing the topic you want a report on.

### Response Format
The API will return a JSON response containing the `topic` and the generated `report`.

#### Example Response:
```json
{
  "topic": "Artificial Intelligence",
  "report": "The history of Artificial Intelligence dates back to the early 1950s..."
}
```

- **`topic`**: The topic that was requested.
- **`report`**: The generated detailed report text.

### Error Handling
The API will return meaningful error responses if something goes wrong. For example, if there’s an issue with the request or an error generating the report, the server will respond with a `500` status code and a descriptive error message.

#### Example Error Response:
```json
{
  "detail": "Error while generating report: [error message here]"
}
```

---

## Customizing the Report
The AI-generated reports include historical context, but you can expand or modify the prompt generation logic by altering the `generate_report` function in the backend code. This way, you can tailor the reports to be more specific, creative, or detailed.

---

## Development and Contributions
We welcome contributions! If you want to improve this project, fix bugs, or add new features, feel free to fork the repository and open a pull request. Here’s how you can contribute:
1. Fork the repository.
2. Create a new branch for your changes.
3. Make your changes and test them thoroughly.
4. Open a pull request with a description of your changes.

---

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---

## Contact
For questions or feedback, please open an issue on GitHub or contact the maintainer at `your-email@example.com`.

---

### Notes:
- **Gemini AI API**: This project uses the **Gemini AI** model from Google, and the application relies on a valid API key. Be sure to secure your API key appropriately, and never expose it in public repositories.
