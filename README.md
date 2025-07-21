# Dream Vacation Destinations

A production-grade application that helps users create and manage their dream vacation destinations list. This project demonstrates modern cloud architecture, DevOps practices, and infrastructure as code using AWS services.

## Architecture Overview

### Application Components

- **Frontend**: React-based SPA with modern UI/UX
- **Backend**: Node.js/Express RESTful API
- **Database**: PostgreSQL for data persistence
- **External API**: Integration with REST Countries API for country information

### Cloud Infrastructure (AWS)

- **Compute**: ECS (Elastic Container Service) with Fargate for serverless container orchestration
- **Database**: Amazon RDS for PostgreSQL with automated backups
- **Networking**: Custom VPC with public and private subnets across multiple AZs
- **Load Balancing**: Application Load Balancer (ALB) with WAF protection
- **Container Registry**: ECR for Docker image storage
- **Monitoring**: CloudWatch, X-Ray, and Grafana for observability
- **Security**: WAF, GuardDuty, and AWS Config for protection and compliance

## Features

### Application Features

- Add countries to your dream vacation list
- View detailed country information (capital, population, region)
- Remove countries from your list
- Responsive design for mobile and desktop

### Infrastructure Features

- **High Availability**: Multi-AZ deployment with auto-scaling
- **Security**:
  - WAF protection against common web exploits
  - GuardDuty for threat detection
  - AWS Config for security compliance
  - Encrypted data at rest and in transit
- **Monitoring & Alerting**:
  - CloudWatch metrics and logs
  - Custom Grafana dashboards
  - X-Ray for distributed tracing
  - SNS notifications for critical alerts
- **Cost Management**:
  - AWS Budgets with email alerts
  - Cost-optimized resource selection
  - Auto-scaling based on demand

## Local Development Setup

### Backend

1. Navigate to the `backend` directory
2. Install dependencies:
   ```bash
   npm install
   ```
3. Set up environment variables:
   ```bash
   cp .env.example .env
   # Edit .env with your database URL
   ```
4. Start the server:
   ```bash
   npm start
   ```

### Frontend

1. Navigate to the `frontend` directory
2. Install dependencies:
   ```bash
   npm install
   ```
3. Set up environment variables:
   ```bash
   cp .env.example .env
   # Edit .env with your API URL
   ```
4. Start the development server:
   ```bash
   npm start
   ```

## Infrastructure Setup

### Prerequisites

- AWS CLI configured with appropriate credentials
- Terraform installed (version >= 1.3.0)
- Docker installed for container builds

### Infrastructure Components

#### Networking

- Custom VPC with public and private subnets
- Internet Gateway for public access
- NAT Gateway for private subnet internet access
- Security groups for fine-grained access control

#### Compute & Containers

- ECS Fargate for serverless container orchestration
- ECR repositories for container images
- Application Load Balancer for traffic distribution
- Auto-scaling based on CPU/Memory metrics

#### Database

- RDS PostgreSQL in private subnets
- Automated backups and maintenance
- Encryption at rest
- Performance insights enabled

#### Monitoring & Observability

- CloudWatch Log Groups with 30-day retention
- Custom CloudWatch metrics and alarms
- Grafana dashboards for visualization
- X-Ray for request tracing
- SNS topics for alert notifications

#### Security

- WAF with rate limiting and AWS managed rules
- GuardDuty for threat detection
- AWS Config for compliance monitoring
- IAM roles with least privilege access
- Security groups for network isolation

#### Cost Management

- AWS Budgets with email alerts
- Resource tagging for cost allocation
- Cost-optimized instance selections

## CI/CD Pipeline

The project uses GitHub Actions for continuous integration and deployment:

- Automated testing for frontend and backend
- Docker image builds and ECR pushes
- Infrastructure validation with Terraform
- Automated deployments to different environments

## Environment Management

- **Development**: Local development environment
- **Staging**: AWS environment for testing
- **Production**: Production AWS environment
- Each environment has isolated resources and configurations

## Best Practices Implemented

- Infrastructure as Code with Terraform
- Container-based deployment
- Automated CI/CD pipeline
- Security-first approach with WAF, GuardDuty
- Comprehensive monitoring and alerting
- Cost optimization and budgeting
- State management with S3 and DynamoDB locking

## Future Enhancements

- [ ] Implement AWS Shield Advanced for DDoS protection
- [ ] Add AWS Certificate Manager for SSL/TLS
- [ ] Implement Route53 for DNS management
- [ ] Add ElastiCache for session management
- [ ] Implement blue-green deployments
- [ ] Add automated database migrations
