# SMS Assistant for Real Estate

This Python Flask application serves as an SMS assistant for real estate tasks. It integrates with OpenAI for natural language processing and Twilio for SMS communication. The assistant handles incoming SMS messages, processes them using AI, and responds accordingly.

## Requirements

- Python 3.x
- Flask
- OpenAI
- Twilio
- pydantic
- sqlite3

## Installation

1. Clone or download the repository to your local machine.
2. Install the required dependencies using pip:

    ```
    pip install Flask openai twilio pydantic
    ```

3. Set up a Twilio account and obtain the necessary credentials (account SID, auth token, and phone number).
4. Set up an OpenAI account and obtain the API key.
5. Create a `.env` file in the project directory and add the following environment variables:

    ```
    OPENAI_API_KEY=<your_openai_api_key>
    TWILIO_ACCOUNT_SID=<your_twilio_account_sid>
    TWILIO_AUTH_TOKEN=<your_twilio_auth_token>
    TWILIO_PHONE_NUMBER=<your_twilio_phone_number>
    ```

## Usage

1. Run the Flask application:

    ```
    python app.py
    ```

2. The application will start, and you can send SMS messages to the specified phone number.
3. The SMS assistant will process the incoming messages, perform the required actions (such as querying real estate data or contacting a realtor), and respond via SMS.

## Functionality

- **Create Assistant**: The `/create_assistant` endpoint allows you to create a new AI assistant using OpenAI.
- **Chat**: The `/chat` endpoint handles incoming messages from a web interface and interacts with the AI assistant.
- **SMS**: The `/SMS` endpoint handles incoming SMS messages, interacts with the AI assistant, and sends responses via SMS.

## File Structure

- `app.py`: The main Flask application file containing route definitions and logic for handling SMS messages.
- `tools_list.py`: List of tools used by the AI assistant.
- `functions.py`: Helper functions for querying real estate data and contacting realtors.
- `sms_assistant.db`: SQLite database file for storing SMS thread information.

## Security Considerations

- Ensure that sensitive credentials (API keys, tokens) are kept secure and not exposed in the source code or version control.
- Implement proper error handling and input validation to prevent security vulnerabilities such as SQL injection or XSS attacks.
- Follow best practices for data storage and transmission to protect user privacy and sensitive information.
