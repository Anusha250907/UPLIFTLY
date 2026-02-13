# UPLIFTLY

> AI-Powered Video Content Optimization Platform

UPLIFTLY is an intelligent platform that empowers video content creators to analyze and optimize their content before publishing. Using advanced AI capabilities, the platform delivers actionable insights, engagement recommendations, and improvement suggestions to help creators maximize their content's impact.

## 🎯 Overview

Content creators often publish videos without understanding their potential performance. UPLIFTLY bridges this gap by providing pre-publication AI analysis, helping creators make data-driven decisions to improve engagement, quality, and audience reach.

## ✨ Features

- **Secure Authentication**: User registration and login powered by Amazon Cognito
- **Creator Dashboard**: Personalized dashboard with video analytics and insights
- **Video Upload System**: Seamless drag-and-drop video upload with progress tracking
- **AI Content Analysis**: Automated video analysis using Amazon Bedrock
- **Smart Recommendations**: AI-generated suggestions for content optimization
- **Real-time Insights**: Instant feedback on content quality and engagement potential

## 🛠️ Technology Stack

### Frontend
- **Next.js** - React framework for production
- **React** - UI component library
- **Amazon S3** - Static website hosting
- **Amazon CloudFront** - Global CDN for fast content delivery

### Backend
- **Node.js** - JavaScript runtime
- **Express.js** - Web application framework
- **AWS Lambda** - Serverless compute
- **Amazon API Gateway** - RESTful API management

### Data & Storage
- **Amazon DynamoDB** - NoSQL database for user data and analysis results
- **Amazon S3** - Object storage for video files

### AI & Machine Learning
- **Amazon Bedrock** - Foundation models for content analysis and recommendations

### Authentication & Security
- **Amazon Cognito** - User authentication and authorization

### Monitoring
- **Amazon CloudWatch** - Application monitoring and logging

## 📁 Project Structure

```
upliftly/
├── frontend/               # Next.js frontend application
│   ├── components/         # React components
│   ├── pages/              # Next.js pages
│   ├── public/             # Static assets
│   ├── styles/             # CSS/styling files
│   └── utils/              # Utility functions
│
├── backend/               # Node.js backend services
│   ├── functions/         # Lambda function handlers
│   │   ├── auth/          # Authentication logic
│   │   ├── upload/        # Video upload handling
│   │   ├── analysis/      # AI analysis orchestration
│   │   └── dashboard/     # Dashboard data aggregation
│   ├── services/          # Business logic services
│   └── utils/             # Helper functions
│
├── infrastructure/        # Infrastructure as Code
│   ├── cloudformation/    # AWS CloudFormation templates
│   └── scripts/           # Deployment scripts
│
├── docs/                  # Documentation
│   ├── design.md          # System design document
│   └── requirements.md    # Requirements specification
│
└── README.md              # This file
```

## 🚀 Deployment Overview

UPLIFTLY uses a serverless architecture deployed on AWS:

1. **Frontend**: Built with Next.js, exported as static files, hosted on S3, and distributed via CloudFront
2. **Backend**: Serverless functions deployed to AWS Lambda, exposed through API Gateway
3. **Database**: DynamoDB tables for users, videos, and analysis data
4. **Storage**: S3 buckets for video files with lifecycle policies
5. **AI Processing**: Amazon Bedrock integration for content analysis

## 🔐 Environment Variables

### Frontend (.env.local)
```
NEXT_PUBLIC_API_URL=<API_Gateway_URL>
NEXT_PUBLIC_COGNITO_USER_POOL_ID=<Cognito_User_Pool_ID>
NEXT_PUBLIC_COGNITO_CLIENT_ID=<Cognito_Client_ID>
NEXT_PUBLIC_AWS_REGION=<AWS_Region>
```

### Backend (Lambda Environment Variables)
```
DYNAMODB_USERS_TABLE=<Users_Table_Name>
DYNAMODB_VIDEOS_TABLE=<Videos_Table_Name>
DYNAMODB_ANALYSIS_TABLE=<Analysis_Table_Name>
S3_VIDEO_BUCKET=<Video_Bucket_Name>
BEDROCK_MODEL_ID=<Bedrock_Model_ID>
AWS_REGION=<AWS_Region>
```

## 🏁 Getting Started

### Prerequisites
- Node.js (v18 or higher)
- npm or yarn
- AWS Account with appropriate permissions
- AWS CLI configured

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/upliftly.git
   cd upliftly
   ```

2. **Install frontend dependencies**
   ```bash
   cd frontend
   npm install
   ```

3. **Install backend dependencies**
   ```bash
   cd ../backend
   npm install
   ```

4. **Configure environment variables**
   - Copy `.env.example` to `.env.local` in frontend directory
   - Update with your AWS resource values

5. **Run frontend locally**
   ```bash
   cd frontend
   npm run dev
   ```
   Frontend will be available at `http://localhost:3000`

6. **Test Lambda functions locally** (optional)
   ```bash
   cd backend
   npm run test
   ```

### Deployment

1. **Deploy infrastructure**
   ```bash
   cd infrastructure
   aws cloudformation deploy --template-file template.yaml --stack-name upliftly-stack
   ```

2. **Deploy backend functions**
   ```bash
   cd backend
   npm run deploy
   ```

3. **Build and deploy frontend**
   ```bash
   cd frontend
   npm run build
   aws s3 sync out/ s3://your-bucket-name
   aws cloudfront create-invalidation --distribution-id YOUR_DIST_ID --paths "/*"
   ```

## 📊 Usage

1. **Sign Up**: Create an account using email and password
2. **Login**: Access your personalized dashboard
3. **Upload Video**: Drag and drop your video file or click to browse
4. **Analyze**: Wait for AI analysis to complete (typically 30-60 seconds)
5. **Review Insights**: View AI-generated recommendations and insights
6. **Optimize**: Apply suggestions to improve your content before publishing

## 🎓 Architecture Highlights

- **Serverless**: Zero server management, automatic scaling
- **Cost-Effective**: Pay only for what you use
- **Scalable**: Handles traffic spikes automatically
- **Secure**: AWS-managed security with Cognito and IAM
- **Fast**: Global CDN delivery with CloudFront
- **AI-Powered**: Leverages Amazon Bedrock foundation models

## 🔮 Future Enhancements

- Thumbnail optimization with A/B testing
- Engagement prediction models
- SEO improvement suggestions
- Advanced analytics dashboard
- Multi-platform integration
- Team collaboration features

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🏆 Hackathon Submission

This project was developed for AI FOR BHARAT with the goal of empowering content creators through AI-driven insights. The MVP demonstrates core functionality including authentication, video upload, AI analysis, and recommendation generation using AWS serverless technologies.

**Team Members**: [CONTENT CATLAYST/SOUMY SAWANT,VISHESH GUPTA, ANUSHA BHALLA AND YASH KOTHARI]

**Submission Date**: [15/02/2026]


## 🤝 Contributing

This is a hackathon project, but contributions are welcome! Please feel free to submit issues or pull requests.

## 📧 Contact

For questions or feedback, please reach out to  [soumy0802@gmail.com]
---

Built with ❤️ using AWS and AI
