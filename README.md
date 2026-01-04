# API RIS

WolfReserve backend API

## Setup

### Prerequisites
- Node.js 18+
- MongoDB
- npm or yarn

### Installation

```bash
npm install
```

### Environment Variables

Create a `.env` file with:
```
PORT=5000
DB_URI=your_mongodb_connection_string
```

### Running the Application

Development mode:
```bash
npm run dev
```

Production mode:
```bash
npm start
```

## SonarQube Integration

This project includes automated code quality analysis with SonarQube via GitHub Actions.

### Setup SonarQube Secrets

To enable SonarQube analysis, add the following secrets to your GitHub repository:

1. `SONAR_TOKEN` - Your SonarQube authentication token
2. `SONAR_HOST_URL` - Your SonarQube server URL (e.g., https://sonarcloud.io)

### Configuration

The SonarQube configuration is defined in `sonar-project.properties`. Key settings:
- Project key: `janwolf9_api-ris`
- Source directories: `src`, `app.js`, `server.js`
- Exclusions: `node_modules`, `uploads`, test files

### Workflow

The SonarQube analysis workflow (`.github/workflows/sonarqube.yml`) runs on:
- Push to `main` or `develop` branches
- Pull requests (opened, synchronized, or reopened)

The workflow performs:
1. Code checkout
2. Node.js setup
3. Dependencies installation
4. SonarQube scan
5. Quality Gate check

