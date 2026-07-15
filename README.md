<img width="1763" height="1007" alt="Screenshot 2026-07-15 130034" src="https://github.com/user-attachments/assets/22562738-b3c6-4f57-bf6d-b5c2e4310bc6" />
<img width="1838" height="953" alt="Screenshot 2026-07-15 130717" src="https://github.com/user-attachments/assets/dafcefe9-7232-41ef-8951-9cc21b2ef075" />


Link: 
http://lina-potty-hero-2025.s3-website.us-east-2.amazonaws.com/



# Potty Training Rewards 🦖

A serverless web app that turns potty training into a reward-based experience for kids — built to get hands-on practice with core AWS services.

## Why
As a parent, I've seen reward-based encouragement work well during potty training. I built this both as a useful tool and as a way to practice serverless architecture end to end.

## How it works
A child enters their name and taps "I went potty!" — triggering a celebration animation and updating their reward count, stored in the cloud.
Browser → S3 (static site) → API Gateway → Lambda → DynamoDB

## Stack
- **Frontend:** HTML/CSS/JS, hosted on S3 static website hosting
- **Backend:** API Gateway (HTTP API) → Lambda (Python 3.12)
- **Database:** DynamoDB, on-demand capacity

## Why these choices
- S3 static hosting — no server to manage, near-zero cost
- HTTP API over REST API — cheaper and lower latency for this simple request pattern
- DynamoDB on-demand — avoids paying for idle capacity on low, unpredictable traffic

## Deploy
```bash
sam build && sam deploy --guided
aws s3 sync frontend/ s3://your-bucket-name --acl public-read
```

## Future improvements
Cognito login for parents, progress dashboard, multiple reward types, CI/CD via CodePipeline.
