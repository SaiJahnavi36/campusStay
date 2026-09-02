CampusStay – Cloud-Based Student Accommodation & Hostel Booking Portal

A full-stack cloud-native web application showcasing enterprise-scale AWS architecture, scalability, and cloud resilience patterns.

📋 Project Overview

CampusStay is an intelligent student accommodation booking platform built to demonstrate real-world cloud engineering practices. The application enables students to search, filter, and book hostel/PG accommodations while showcasing enterprise cloud architecture principles aligned with industry standards.

Status: Frontend ✅ Complete | Backend Architecture 🏗️ Designed | Infrastructure 🌐 Production-Ready

🏗️ Architecture & Cloud Design
Multi-Tier AWS Architecture
┌─────────────────────────────────────────────────┐
│           CloudFront CDN (Global Edge)          │
├─────────────────────────────────────────────────┤
│  Elastic Load Balancer (ELB) - HA & Load Dist.  │
├─────────────────────────────────────────────────┤
│   EC2 Auto Scaling Group (Compute Layer)        │
│   • Apache Web Server                           │
│   • Application Logic                           │
│   • Horizontal Scaling (2-4 instances)          │
├─────────────────────────────────────────────────┤
│   VPC with Security Groups (Network Layer)      │
│   • Private Subnet (Databases)                  │
│   • Public Subnet (Web Servers)                 │
│   • NAT Gateway, Route Tables                   │
├─────────────────────────────────────────────────┤
│   RDS MySQL 8.0 (Data Layer)                    │
│   • Multi-AZ for failover protection            │
│   • Automated backups                           │
├─────────────────────────────────────────────────┤
│   S3 Bucket (Storage & Assets)                  │
│   • Static files, images, documents             │
│   • Versioning & backup strategy                │
├─────────────────────────────────────────────────┤
│   CloudWatch (Monitoring & Observability)       │
│   • Real-time performance metrics               │
│   • Custom alarms & auto-scaling triggers       │
└─────────────────────────────────────────────────┘
Key Architectural Concepts
1. High Availability (HA)
Multi-AZ RDS Deployment: Automatic failover between availability zones
Auto Scaling Group: Dynamically scales EC2 instances based on CPU/network metrics
Elastic Load Balancer: Distributes traffic across instances; health checks ensure only healthy servers receive requests
CloudFront CDN: Global edge locations reduce latency and provide DDoS protection
2. Scalability
Horizontal Scaling: Auto Scaling Group (ASG) automatically adds/removes EC2 instances based on demand (2-4 instance range)
Database Scaling: RDS read replicas for read-heavy workloads (future enhancement)
Asset Scaling: S3 + CloudFront handles unlimited concurrent file requests globally
CloudWatch Metrics: Tracks CPU utilization, network throughput, request counts to trigger scaling policies
3. Resilience & Disaster Recovery
VPC Segmentation: Public (web) and private (database) subnets isolate components
Security Groups: Acts as stateful firewalls controlling ingress/egress traffic
RDS Automated Backups: Point-in-time restore capability (7-day retention by default)
Multi-layer Redundancy: Load balancing + auto-scaling prevents single points of failure
CloudWatch Alarms: Proactive alerts on CPU, disk usage, and database connections
4. Security & Compliance
VPC Isolation: Databases run in private subnets—not directly accessible from internet
IAM Roles: EC2 instances assume least-privilege IAM roles
Security Groups: Whitelist-based access (port 80/443 for web, 3306 for database)
Encryption: S3 versioning, RDS encryption at rest, HTTPS/TLS in transit
Compliance Alignment: Architecture supports SOC 2 Type II, HIPAA, and GDPR compliance frameworks
🎨 Frontend Features
Responsive Design
HTML5 & CSS3 with modern techniques:
CSS Grid & Flexbox for responsive layouts
CSS Variables for dynamic theming
CSS Animations & transitions for smooth UX
Mobile-first design approach
Dynamic User Interactions
Vanilla JavaScript (ES6+) for client-side logic:
Real-time search & filtering (location, price, ratings)
Interactive booking workflow with form validation
State management for cart/favorites
Asynchronous API calls (ready for backend integration)
User Experience
Intuitive navigation and clear call-to-actions
Real-time availability updates (mock data currently)
Responsive accommodation cards with images & details
Seamless mobile experience across all screen sizes
Fast loading with optimized assets
🛠️ Tech Stack
Layer	Technology
Frontend	HTML5, CSS3 (Grid, Flexbox, Animations), JavaScript (ES6+)
Backend	Apache Web Server (configured), Node.js/Python ready
Database	MySQL 8.0 (RDS) with schema design documentation
Compute	EC2 (t2.micro/small instances) with Auto Scaling
Storage	S3 bucket for static assets, images, documents
Networking	VPC, Security Groups, Elastic Load Balancer, CloudFront CDN
Monitoring	CloudWatch (metrics, alarms, dashboards)
Infrastructure	AWS Academy Learner Lab (us-east-1, $100 credit)
DevOps Ready	Docker containerization ready, CI/CD pipeline architecture planned
📊 Database Schema
Core Tables
users: Student accounts, profile data
accommodations: Hostel/PG listings with details (capacity, amenities, pricing)
bookings: Reservation records (dates, status, payment)
reviews: Ratings and feedback from students
payments: Transaction records and invoice tracking

Database Features:

Normalized schema (3NF) for data integrity
Indexed columns for fast query performance
Foreign key constraints for referential integrity
Automated backup strategy with RDS snapshots
🚀 Deployment & Monitoring
Current Deployment
Frontend: GitHub Pages (deployed at: username.github.io/campusstay)
AWS Resources: Deployed in AWS Academy Learner Lab (us-east-1 region)
CloudFront: Global distribution via CDN endpoint
Monitoring & Observability
CloudWatch Dashboard displays:
├── EC2 CPU Utilization (triggers Auto Scaling)
├── Network In/Out (bandwidth tracking)
├── RDS Connections (database health)
├── ELB Request Count (traffic volume)
├── CloudFront Hit Ratio (cache efficiency)
└── Custom Alarms (alerts on threshold breach)
📈 Learning Outcomes & Skills Demonstrated

This project showcases proficiency in:

✅ Cloud Architecture Design

Multi-tier application architecture
Enterprise scalability patterns
High availability and disaster recovery
Compliance-aligned security design

✅ AWS Services

EC2 (compute), RDS (database), S3 (storage)
VPC (networking), ELB (load balancing)
Auto Scaling, CloudFront, CloudWatch
IAM (identity & access management)

✅ Frontend Development

Responsive web design (mobile-first)
Modern CSS (Grid, Flexbox, animations)
Vanilla JavaScript with ES6+ features
UX best practices

✅ DevOps & Infrastructure

Infrastructure as Code concepts
Monitoring and alerting
Scalability testing and optimization
Security & compliance frameworks
🔄 Future Enhancements
Phase 2: Backend Implementation
 Build REST API (Node.js/Python)
 Connect to RDS database
 Implement user authentication (JWT/OAuth)
 Payment gateway integration (Razorpay/Stripe)
 Email notifications (SES)
Phase 3: DevOps & CI/CD
 Containerize application (Docker)
 Set up CI/CD pipeline (GitHub Actions)
 Automated testing (unit & integration tests)
 Container orchestration (Kubernetes-ready)
Phase 4: Advanced Features
 Machine Learning recommendations (user preferences)
 Real-time availability updates (WebSockets)
 Analytics dashboard (AWS QuickSight)
 Mobile app (React Native)
📚 Resources & Documentation
AWS Architecture: AWS Well-Architected Framework
Security: AWS Security Best Practices
Scalability: AWS Auto Scaling Documentation
Monitoring: CloudWatch User Guide
🎓 Academic Context

Course: Managing Cloud Solutions (INT 330)
Assignment: CA2 - Cloud Project
Institution: Lovely Professional University
Minor: Cloud Computing
Framework: AWS Academy Learner Lab

🤝 Contributing

This is a portfolio/academic project. For suggestions or improvements:

Fork the repository
Create a feature branch (git checkout -b feature/enhancement)
Commit changes (git commit -m 'Add feature')
Push to branch (git push origin feature/enhancement)
Open a Pull Request
📄 License

This project is open source and available under the MIT License. See LICENSE file for details.

👤 Author

Sai Jahnavi

🎓 B.Tech Computer Science Engineering (Minor: Cloud Computing)
🏢 Lovely Professional University
🔗 LinkedIn: www.linkedin.com/in/jahnavi-sai/
💻 GitHub: github.com/SaiJahnavi36
📧 Email: saijaahnavi999@gmail.com
📸 Screenshots & Demo

Frontend Demo: Live on GitHub Pages
Architecture Diagram: See above multi-tier architecture section
Database Schema: Included in /docs/schema.sql

❓ FAQ

Q: Why is only frontend deployed on GitHub?
A: The backend requires a live server and database connection. AWS Academy account has limited credits. Frontend showcases UI/UX and responsive design. Full stack will be deployed once backend API is implemented and can use free-tier alternatives (MongoDB Atlas, Vercel, etc.).

Q: What's the AWS infrastructure cost?
A: This project uses AWS Academy Learner Lab—free for students. Production deployment would use AWS Free Tier (12 months) with estimated cost: ~$15-30/month for small-scale (after free tier expires).

Q: Is this production-ready?
A: The architecture is production-ready, but the backend implementation is pending. Frontend is fully functional. Security is designed per AWS best practices and compliance frameworks.

Q: How is this project evaluated?
A: This is an academic project (INT 330, CA2) demonstrating cloud architecture design, AWS service integration, and enterprise scalability patterns. Graded on architecture design, implementation, documentation, and understanding of cloud concepts.

📞 Support

For questions or issues:

📧 Email: saijaahnavi999@gmail.com
💬 LinkedIn: Direct message
🐛 GitHub Issues: Create an issue in this repository

Last Updated: September 2026
Status: Active Development
Version: 1.0 (Frontend Complete)

Built with ☁️ Cloud Engineering passion | Showcasing AWS expertise | Demonstrating scalability & resilience
