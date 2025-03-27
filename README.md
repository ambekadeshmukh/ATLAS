# A.T.L.A.S

![ATLAS](https://github.com/user-attachments/assets/9913a6a9-7e50-4fb0-83bd-979156db7ef7)


# Automated Threat Learning and Analysis System

ATLAS is a comprehensive security monitoring and automated response platform that combines traditional security tools like Wazuh with advanced AI capabilities. This hybrid approach creates a powerful system that can automatically detect, analyze, and respond to security threats in real-time.

## Project Overview

In today's rapidly evolving threat landscape, organizations must proactively monitor, detect, and respond to security incidents to protect their critical assets and maintain business continuity. ATLAS addresses this need by providing:

1. **Comprehensive Monitoring**: Traditional security monitoring with Wazuh for complete visibility
2. **Intelligent Analysis**: ML-based analysis combined with LLM reasoning for deeper understanding
3. **Automated Response**: Action recommendations and automated remediation capabilities
4. **Scalable Architecture**: Cloud-native design that scales with your organization

## Architecture

ATLAS uses a hybrid architecture that combines proven security monitoring tools with cutting-edge AI technologies:

![ATLAS Design](https://github.com/user-attachments/assets/21371c75-4ced-4367-9fb6-299c8545c3bf)


## Key Components

### 1. Security Monitoring Infrastructure

- **Wazuh Server**: Core HIDS/SIEM component for security monitoring
- **Elasticsearch/Kibana**: Data storage and visualization platform
- **Agents**: Lightweight monitors deployed on systems to collect security data

### 2. AI Engine

- **Foundation Models**: Integration with LLMs (local or API-based)
- **Vector Database**: Semantic search for similar security incidents
- **ML Pipeline**: Traditional machine learning for threat classification
- **Agent Framework**: LangChain-based orchestration of intelligent agents

### 3. Response System

- **Automated Analysis**: Contextual understanding of security alerts
- **Remediation Actions**: Automatic or recommended response actions
- **Verification**: Confirmation of successful threat mitigation

### 4. DevOps Interface

- **Infrastructure as Code**: Terraform templates for AWS deployment
- **Dashboard**: Web interface for security monitoring and configuration
- **API**: RESTful API for integration with other systems
- **CLI Tools**: Command-line tools for automation and management

## Technical Implementation

ATLAS is implemented using:

- **AWS Cloud Infrastructure**: VPC, EC2, S3, IAM
- **Wazuh**: Open-source security monitoring platform
- **ELK Stack**: Elasticsearch, Logstash, Kibana for data analysis
- **LangChain & Semantic Kernel**: Framework for creating AI agents
- **Vector Database**: Chroma DB for similarity search
- **Terraform**: Infrastructure as Code for AWS provisioning
- **Python**: Core engine implementation

## Deployment Options

ATLAS can be deployed in two configurations:

### Free Tier Compatible
- Minimal setup suitable for AWS Free Tier
- Core security monitoring with Wazuh
- Limited AI capabilities
- Perfect for demonstration purposes

### Full Deployment
- Complete system with all AI components
- Vector database for similarity search
- LLM integration for enhanced analysis
- Automated response capabilities

## Getting Started

### Prerequisites

- AWS account
- Terraform installed
- AWS CLI configured
- Python 3.10+

### Deployment

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/ATLAS.git
   cd ATLAS
   ```

2. Make scripts executable:
   ```bash
   chmod +x scripts/*.sh
   ```

3. Deploy the system:
   
   For Free Tier compatible deployment:
   ```bash
   ./scripts/deploy.sh --free-tier
   ```
   
   For full deployment with AI capabilities:
   ```bash
   ./scripts/deploy.sh --full
   ```

4. Follow the instructions in the generated DEPLOYMENT_INFO.md file to access the system.

### Adding Agents

To monitor additional systems:

```bash
scp -i ~/.ssh/atlas-key.pem scripts/deploy-agent.sh user@target-system:~/
ssh -i ~/.ssh/atlas-key.pem user@target-system
sudo ./deploy-agent.sh <wazuh-server-ip>
```

### Cleanup

When you're done with your demo or testing:

```bash
./scripts/cleanup.sh
```

## Project Objectives

1. **Cloud Infrastructure**: Establish a secure and scalable cloud infrastructure to host security monitoring and analysis components.
2. **Security Monitoring**: Implement Wazuh to collect, analyze, and store security-related logs and events.
3. **Data Analysis**: Develop data pipelines and analytical tools to extract insights from security data.
4. **Automated Response**: Leverage machine learning and LLMs to suggest and apply appropriate solutions for detected security alerts.
5. **Documentation**: Thoroughly document the architecture and implementation for educational purposes.

## Repository Structure

```
atlas/
├── terraform/                  # Infrastructure as Code
│   ├── main.tf                 # Main AWS resources
│   ├── variables.tf            # Input variables
│   ├── outputs.tf              # Output values
│   └── modules/                # Modular components
├── scripts/                    # Installation and deployment scripts
│   ├── install-wazuh.sh        # Wazuh installation script
│   ├── install-ai-engine.sh    # AI engine installation script
│   ├── deploy.sh               # Master deployment script
│   └── cleanup.sh              # AWS cleanup script
├── src/                        # Source code
│   └── ai_engine/              # AI engine components
├── docs/                       # Documentation
└── README.md                   # Project overview
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Acknowledgments

- Wazuh open-source security platform
- LangChain framework for AI agent development
- AWS for cloud infrastructure services
