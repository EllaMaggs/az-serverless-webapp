# Azure Serverless Static Web App with Visitor Counter and Analytics
This is my website! It's a static website hosted on Azure Storage with a visitor counter powered by .NET and Azure Functions. Developed with HTML, CSS, and JavaScript; it features CI/CD workflows managed via GitHub Actions and integrates Azure services like Blob Storage and CosmosDB for a serverless web app with a dynamic database. 

## Demo
[View it live here](https://www.ellamaggs.com/)

## Structure
- 'frontend/': Folder contains HTML for website. 
    - 'main.js': Folder contains visitor counter JavaScript. 
- 'backend/': Folder defines Azure Function for storage in CosmosDB.
    - 'api/': Folder Contains the dontnet API deployed on Azure Functions.
    - 'Counter.cs': Contains the visitor counter code. 
- 'github/workflows/': Folder contains CI/CD workflow configurations. 

## Architecture
![Architecture Diagram](EMWebAppArchitectureDiagram4.drawio.png)

Azure CDN delivers static web content (HTML, CSS, JavaScript from the frontend/ directory in Blob Storage) with low latency, HTTPS support, and custom domains. Static website hosting provides high availability, global caching, and scalability. Azure Functions handles HTTP GET requests and uses Cosmos DB bindings to read the visitor counter, increment it, and return the updated value. GitHub Actions provides automated CI/CD, enabling continuous integration and deployment with minimal downtime. Azure Monitor tracks service performance and collects application logs.

## Troubleshooting

- **Website not loading:** Check Azure Storage static website settings and CDN configuration.
- **Visitor counter not updating:** Review Azure Functions logs, verify CosmosDB connection, and ensure CORS is set up.
- **CI/CD pipeline fails:** Inspect GitHub Actions logs and confirm Azure credentials/secrets are correct.

## Roadmap

- **Improve CI/CD Pipelines** Add end-to-end tests with automated security scanning and performance testing.
- **Rate Limiting:** Add API authentication, rate limiting, and replace wildcard CORS with specific domains.
- **Automated Testing:** Configure Azure Monitor alerts for error rates, response times, function failures, and cost thresholds.
