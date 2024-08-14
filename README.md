# AWS Lambda WeatherAlert

## Overview

In light of the significant impact Hurricane Ida had on the east coast of the United States, this project aims to provide daily weather alerts to ensure you're always prepared for changing weather conditions.

## Technology Stack

- **Python**
- **AWS Lambda**
- **AWS EventBridge**
- **AWS SES (Simple Email Service)**
- **OpenWeatherMap API**

## Setup

### AWS Setup

1. **Configure AWS CLI**: Ensure the AWS CLI is configured with your credentials.
2. **Email Verification**: Verify email addresses for sending and receiving emails while in sandbox mode.
3. **OpenWeatherMap API**: Sign up for an OpenWeatherMap API key and set it as an environment variable `OPEN_WEATHER_MAP_API`.
4. **Lambda Function**: Create a Lambda function named `weather-alert`. If you use a different name, ensure to update all references to `weather-alert` in the build and deployment scripts accordingly.
5. **Environment Variables**: Provide values for all environment variables as outlined in `.env.template` to your Lambda function.
6. **EventBridge Configuration**: Set up AWS EventBridge to trigger the Lambda function as per your schedule.

### Local Development

1. **Setup Virtual Environment**: Create a virtual environment with `python3 -m venv .venv`.
2. **Install Dependencies**: Run `pip install -r requirements.txt` to install the necessary libraries.
3. **Local Testing**: Test the function locally by running `python lambda_function.py`.
   - Note: Either create a `.env` file and load it for local development or manually replace environment variables in the code during testing.

## Deployment

1. **Build and Deploy**: Execute `./scripts/build-deploy.sh` to build and deploy the Lambda function to AWS.
2. **SES Template Creation**: Run `./aws/scripts/ses-create-weather-alert-template.sh` to create the email template in SES.
3. **SES Template Update**: Run `./aws/scripts/ses-update-template-weather-alert.sh` to update the email template in SES.
