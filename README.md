# Ham or Spam Call Detector

## Overview
The Ham or Spam Call Detector is a Python-based application designed to analyze and classify incoming phone calls in real-time as either legitimate ("Ham") or unwanted ("Spam"). The system employs Google Cloud's Speech-to-Text API for transcription and the VADER Sentiment Analysis tool, alongside keyword detection, to evaluate the content of the call.

## Features
- **Real-Time Analysis:** Analyzes incoming calls in real-time, processing audio data in 5-second intervals.
- **Sentiment Analysis:** Utilizes VADER Sentiment Analysis to gauge the sentiment of the call's transcript.
- **Keyword Detection:** Scans the transcription for specific keywords that are commonly found in spam calls.
- **Dynamic Classification:** Classifies calls as Ham or Spam based on the analysis, with the ability to end spam calls automatically.

## Prerequisites
- Python 3.x
- Google Cloud Speech-to-Text API credentials
- `google-cloud-speech` library
- `vaderSentiment` library

## Installation
1. Clone the repository or download the source code.
2. Install the required Python libraries:
   ```bash
   pip install google-cloud-speech vaderSentiment
   ```
3. Set up Google Cloud Speech-to-Text API credentials as per the [official documentation](https://cloud.google.com/speech-to-text/docs/quickstart-client-libraries).

## Usage
To use the Ham or Spam Call Detector, run the `process_call` function with a unique call identifier. Ensure your system is set up to capture and provide real-time audio data from incoming calls.

Example usage:
```python
incoming_call_id = "unique_call_id"
process_call(incoming_call_id)
```

## Functionality Overview
- `transcribe_call_google(audio_content)`: Transcribes audio content using Google Cloud Speech-to-Text.
- `analyze_sentiment(text)`: Analyzes the sentiment of the provided text using VADER Sentiment Analysis.
- `contains_spam_keywords(text)`: Checks if the transcription contains predefined spam keywords.
- `classify_call(transcription, sentiment, scores)`: Classifies the call as Ham or Spam based on sentiment and keyword analysis.
- `process_call(call_id)`: Main function to process the call in real-time and classify it.
- `receive_audio(call_id, duration)`: Simulates receiving audio data (to be replaced with actual audio capture logic).
- `end_call(call_id)`: Ends the call (to be integrated with the telephony system).

## Customization
- Modify the `spam_keywords` list to include phrases specific to the spam calls relevant to your context.
- Adjust sentiment analysis thresholds in the `classify_call` function to better suit your classification criteria.

## Note
This application is designed as a prototype and requires integration with telephony systems to function in a production environment. The `receive_audio` and `end_call` functions are placeholders and should be replaced with actual implementations.

## License
Released via an MIT license.
