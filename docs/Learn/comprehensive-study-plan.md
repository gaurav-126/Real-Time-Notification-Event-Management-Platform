# Real-Time Notification Platform MVP - Comprehensive Study Plan

**Project Timeline:** 5 weeks | **Total Learning:** 60-100 hours  
**Document Updated:** December 22, 2025

---

## Overview

This study plan breaks down the 10-phase MVP project into daily learning and development activities. Each phase includes:
- **Learning Objectives** - What you'll understand
- **Key Concepts** - Core ideas to grasp
- **Best Resources** - Curated, high-quality sources with reviews
- **Hands-On Tasks** - Implementation work
- **Learning Checkpoints** - Validation of understanding

---

## PHASE 1: Project Setup & Infrastructure (Week 1)

**Duration:** 3-4 days | **Learning Time:** 8-12 hours

### Learning Objectives
- Understand Git workflows and branching strategies
- Master Docker fundamentals and containerization
- Learn Docker Compose for orchestrating multiple services
- Create reproducible local development environments

### Key Concepts to Master

| Concept | Why It Matters | Key Learning Points |
|---------|---|---|
| Git Branching | Team coordination & version control | main, develop, feature branches; merge strategy |
| Docker Images | Foundation of containerization | Layers, caching, efficiency |
| Docker Containers | Runtime execution units | Isolation, networking, resource limits |
| Docker Compose | Service orchestration | Multi-service coordination, networking, volumes |
| .env Files | Security & configuration | Never commit secrets, environment separation |

### Recommended Learning Resources

#### Git & Branching Strategy
**Resource:** *A Successful Git Branching Model (Git Flow)*  
- **URL:** https://nvie.com/posts/a-successful-git-branching-model/
- **Type:** Blog article
- **Duration:** 15-20 minutes read
- **Why This:** Gold standard for team Git workflows, directly applicable to this project
- **How to Use:** Read once, reference throughout project

**Resource:** Official GitHub Documentation  
- **URL:** https://github.github.com/training-kit/
- **Type:** Official documentation + cheat sheets
- **Duration:** 30 minutes
- **Why This:** Authoritative source for Git commands

#### Docker Fundamentals
**Resource:** *Docker for the Absolute Beginner — Hands-On — DevOps* (Udemy)  
- **URL:** https://udemy.com/course/docker-for-the-absolute-beginner-devops/
- **Cost:** $15-20 (on sale) or free trial
- **Duration:** 1 hour 26 minutes
- **Level:** Beginner
- **Why This:** Highly rated, no prerequisites assumed, hands-on demos
- **Topics Covered:** Docker basics, images, containers, Dockerfiles
- **Review Score:** 4.7/5 stars (100k+ reviews)

**Resource:** *Learn Docker in 2025 - Complete Roadmap Beginner to Pro* (YouTube)  
- **URL:** https://www.youtube.com/watch?v=zFa9_K8BS8I
- **Cost:** Free
- **Duration:** 30 minutes
- **Level:** Beginner to Intermediate
- **Why This:** Recent (2025), complete roadmap, visual learning, free
- **Topics Covered:** Docker Fundamentals → Commands → Images/Dockerfiles → Networking → Compose → Best Practices → CI/CD
- **How to Use:** Watch in sections, pause to practice commands

**Resource:** Official Docker Documentation  
- **URL:** https://docs.docker.com/get-started/
- **Cost:** Free
- **Duration:** 1-2 hours
- **Why This:** Authoritative, includes hands-on labs in Docker Playground
- **How to Use:** Reference while building Dockerfiles, supplement with videos

#### Docker Compose
**Resource:** Docker Compose Official Guide  
- **URL:** https://docs.docker.com/compose/
- **Cost:** Free
- **Duration:** 45 minutes
- **Why This:** Official source, practical examples, covers all needed syntax
- **Key Sections:** Getting started, compose file reference, networking

### Practical Tasks & Implementation

**Day 1: Git Setup (2-3 hours)**
```
Task 1.1: Initialize Git Repository
- [ ] Create GitHub repository
- [ ] Clone locally
- [ ] Create main branch (default)
- [ ] Create develop branch
- [ ] Set branch protection rules (no direct commits to main)
Learning: Understand branching strategy for team workflows

Task 1.2: Create Project Structure
- [ ] Create folders: /api, /worker, /frontend, /infra, /docs
- [ ] Create .gitignore file (for .NET, Python, Node.js)
- [ ] Create README.md (basic structure)
Learning: Project organization best practices
```

**Day 2: Docker Fundamentals (3-4 hours)**
```
Task 1.3: Install Docker & Docker Compose
- [ ] Install Docker Desktop (Mac/Windows) or Docker Engine (Linux)
- [ ] Verify installation: docker --version, docker run hello-world
- [ ] Install Docker Compose: docker-compose --version
Learning: Local development environment setup

Task 1.4: Docker Hands-On Practice
- [ ] Follow "Docker for Absolute Beginner" course (1h 26m)
- [ ] Create Dockerfile for a simple Node.js app
- [ ] Build image: docker build -t my-app:1.0 .
- [ ] Run container: docker run -p 3000:3000 my-app:1.0
- [ ] Practice docker commands: ps, logs, exec, stop, rm
Learning: Container lifecycle, image creation, port mapping
```

**Day 3-4: Docker Compose & Project Setup (4-5 hours)**
```
Task 1.5: Create Initial docker-compose.yml
- [ ] Define 8 services (stub versions):
    - api (port 5000)
    - worker (background service)
    - frontend (port 3000)
    - postgres (port 5432)
    - redis (port 6379)
    - redpanda (port 9092)
    - prometheus (port 9090)
    - grafana (port 3000 - change to 3001)
- [ ] Create docker-compose override file for local dev
- [ ] Test: docker-compose up (will fail on missing services, that's ok)
Learning: Service orchestration, networking, port management

Task 1.6: Create Environment Configuration
- [ ] Create .env.example with all required variables
- [ ] Create .env.local (add to .gitignore)
- [ ] Document each variable with explanation
Learning: Secrets management, environment separation

Task 1.7: Write Comprehensive README
- [ ] Project overview (what it does)
- [ ] Tech stack table
- [ ] Quick start guide
- [ ] Architecture diagram (text-based or image)
- [ ] Development guide (how to run locally)
- [ ] Troubleshooting section
Learning: Technical documentation, communication
```

### Learning Checkpoints (Self-Assessment)

Answer these questions to validate your understanding:

1. **Git Branching**: Explain Git Flow. When would you use feature branches vs hotfix branches?
2. **Docker Images**: What's the difference between a Docker image and a container? Why do layers matter?
3. **Dockerfiles**: What's a multi-stage build? Why would you use it?
4. **Docker Compose**: Write a basic docker-compose.yml with 2 services (postgres and api). Include networking and environment variables.
5. **Security**: Why should you never commit .env files to git? What's the alternative?

### Deliverables
- ✅ Git repo with develop/main branches, .gitignore configured
- ✅ docker-compose.yml skeleton with 8 services
- ✅ .env.example file with all needed variables
- ✅ README with overview, setup instructions, tech stack
- ✅ Project folder structure created

**Estimated Time:** 10-12 hours

---

## PHASE 2: Database Schema & Core API (Week 1-2)

**Duration:** 5-6 days | **Learning Time:** 15-20 hours

### Learning Objectives
- Design relational database schemas
- Learn PostgreSQL and SQL
- Build RESTful APIs with ASP.NET Core
- Understand Entity Framework Core ORM
- Implement JWT-based authentication
- Configure Keycloak for identity management

### Key Concepts to Master

| Concept | Why It Matters | Key Learning Points |
|---------|---|---|
| Database Normalization | Data integrity, query performance | 3NF, relationships, indexes |
| SQL & Queries | Data manipulation | CREATE TABLE, INSERT, SELECT, JOINs |
| ORMs (Entity Framework) | Reduce boilerplate, type-safe queries | DbContext, Models, Migrations |
| RESTful APIs | Standard web service design | HTTP verbs, status codes, idempotency |
| JWT Tokens | Stateless authentication | Token structure, expiration, validation |
| OAuth2 Flow | Enterprise authentication | Authorization grants, access tokens |

### Recommended Learning Resources

#### PostgreSQL Fundamentals
**Resource:** *PostgreSQL Tutorial (Neon)*  
- **URL:** https://neon.com/postgresql/tutorial
- **Cost:** Free
- **Duration:** 2-3 hours
- **Level:** Beginner
- **Why This:** Interactive, practical, modern approach, includes examples
- **Topics:** Getting started, basic queries, relationships, indexes
- **How to Use:** Follow tutorials, practice with your own sample data

**Resource:** *PostgreSQL Official Documentation*  
- **URL:** https://www.postgresql.org/docs/
- **Cost:** Free
- **Duration:** Reference as needed
- **Why This:** Authoritative, includes examples for all features
- **When to Use:** For specific query syntax, functions, advanced features

**Resource:** *W3Schools PostgreSQL Tutorial*  
- **URL:** https://www.w3schools.com/postgresql/
- **Cost:** Free
- **Duration:** 1-2 hours
- **Level:** Beginner
- **Why This:** Interactive exercises, step-by-step learning, no setup required

#### ASP.NET Core & C#
**Resource:** *Learn ASP.NET Core 8.0 - Full Course for Beginners* (YouTube)  
- **URL:** https://www.youtube.com/watch?v=f63mo1ZRobM
- **Cost:** Free
- **Duration:** 3 hours 14 minutes
- **Level:** Beginner
- **Why This:** Free, comprehensive, covers API + EF Core + CRUD, hands-on project
- **Topics Covered:** 
  - Project creation & setup
  - Database design with EF Core (Code First)
  - RESTful API design
  - CRUD endpoints
  - Frontend integration (bonus)
- **Review Score:** Highly rated on YouTube
- **How to Use:** Watch in sections, pause to code alongside, GitHub repos available

**Resource:** *Microsoft ASP.NET Core Documentation*  
- **URL:** https://learn.microsoft.com/en-us/aspnet/core/
- **Cost:** Free
- **Duration:** Reference as needed
- **Why This:** Official, authoritative, includes official tutorials
- **Key Sections:** Getting started, API design, Entity Framework

#### Entity Framework Core
**Resource:** *Getting Started with Entity Framework Core* (Educative)  
- **URL:** https://www.educative.io/blog/getting-started-with-ef-core
- **Cost:** Free
- **Duration:** 2-3 hours
- **Level:** Beginner
- **Why This:** Beginner-friendly, covers core concepts, practical examples
- **Topics:** DbContext, Models, Queries, Relationships, Change Tracking

**Resource:** *Entity Framework Core Documentation*  
- **URL:** https://docs.microsoft.com/en-us/ef/core/
- **Cost:** Free
- **Duration:** 3-4 hours
- **Why This:** Official, comprehensive, includes migration examples
- **Key Sections:** Getting started, creating models, querying, saving data

**Resource:** *Learn Entity Framework Core* (Website)  
- **URL:** https://www.learnentityframeworkcore.com/
- **Cost:** Free
- **Duration:** 2-3 hours
- **Level:** Beginner to Intermediate
- **Why This:** Focused tutorials, practical examples, good explanations

#### JWT & OAuth2 Authentication
**Resource:** *OAuth2 with Password & JWT* (FastAPI - Language Agnostic Concepts)  
- **URL:** https://fastapi.tiangolo.com/tutorial/security/oauth2-jwt/
- **Cost:** Free
- **Duration:** 1-2 hours
- **Level:** Intermediate
- **Why This:** Language-agnostic concepts apply to ASP.NET, clear flow diagrams
- **Topics:** JWT structure, token generation, validation, refresh tokens
- **How to Use:** Understand concepts, then apply to ASP.NET implementation

**Resource:** *Introduction to JWT and OAuth 2.0* (Dev.to)  
- **URL:** https://dev.to/gervaisamoah/introduction-to-jwt-and-oauth-20-4bin
- **Cost:** Free
- **Duration:** 30-45 minutes
- **Level:** Beginner
- **Why This:** Clear, concise explanation of both technologies, practical use cases

**Resource:** *JWT.io Introduction*  
- **URL:** https://jwt.io/introduction
- **Cost:** Free
- **Duration:** 15-20 minutes
- **Level:** Beginner
- **Why This:** Official JWT site, explains structure, shows examples
- **Interactive:** Token debugger to examine JWT structure

#### Keycloak Setup
**Resource:** *Keycloak Official Documentation*  
- **URL:** https://www.keycloak.org/documentation
- **Cost:** Free
- **Duration:** 1-2 hours (for basic setup)
- **Level:** Intermediate
- **Why This:** Official, comprehensive, Docker setup included
- **Key Sections:** Getting started, running in Docker, realm creation, client configuration

### Practical Tasks & Implementation

**Day 1-2: PostgreSQL Setup (4-5 hours)**
```
Task 2.1: Learn PostgreSQL Basics
- [ ] Follow Neon PostgreSQL Tutorial (2-3 hours)
- [ ] Learn: CREATE TABLE, INSERT, SELECT, WHERE, ORDER BY, JOINS
- [ ] Practice: Write 10 different queries
Learning: SQL fundamentals, query syntax

Task 2.2: Design Database Schema
- [ ] Create schema diagram for 4 tables:
    1. users (id, email, password_hash, created_at, updated_at, is_active)
    2. notification_templates (id, name, subject, body, variables, created_by, created_at)
    3. notification_history (id, user_id, template_id, status, sent_at, created_at, error_message)
    4. user_preferences (id, user_id, email_enabled, created_at, updated_at)
- [ ] Identify primary keys, foreign keys, and relationships
- [ ] Determine indexes needed for query performance
- [ ] Create ERD diagram (use Lucidchart or draw.io)
Learning: Database design principles, normalization, relationships
```

**Day 3: ASP.NET Core API Setup (3-4 hours)**
```
Task 2.3: Create ASP.NET Core Project
- [ ] Watch "Learn ASP.NET Core 8.0" video sections 1-2 (30 min)
- [ ] Create new ASP.NET Core Web API project
  Command: dotnet new webapi -n NotificationAPI
- [ ] Explore project structure
- [ ] Run locally: dotnet run
Learning: .NET project structure, MVC/REST basics

Task 2.4: Set Up Entity Framework Core
- [ ] Add NuGet packages:
    - Microsoft.EntityFrameworkCore
    - Microsoft.EntityFrameworkCore.PostgreSQL
    - Microsoft.EntityFrameworkCore.Tools
- [ ] Create Models based on schema:
    - User.cs
    - NotificationTemplate.cs
    - NotificationHistory.cs
    - UserPreference.cs
- [ ] Create AppDbContext class inheriting from DbContext
- [ ] Configure PostgreSQL connection string
Learning: ERM patterns, DbContext configuration

Task 2.5: Create Health Check Endpoint
- [ ] Create GET /api/health endpoint
- [ ] Return JSON: { "status": "ok", "timestamp": "2025-12-22T10:00:00Z" }
- [ ] Test with curl or Postman
Learning: Basic API endpoint creation, HTTP responses
```

**Day 4-5: Authentication & Authorization (4-5 hours)**
```
Task 2.6: Set Up Keycloak (Docker)
- [ ] Add Keycloak to docker-compose.yml
- [ ] Run: docker-compose up keycloak
- [ ] Access Keycloak admin console (http://localhost:8080)
- [ ] Create realm: "notification-platform"
- [ ] Create client: "notification-api"
- [ ] Generate client credentials (client_id, client_secret)
- [ ] Copy to .env.local
Learning: Identity management, OAuth2 setup

Task 2.7: Implement JWT Authentication in ASP.NET
- [ ] Add NuGet packages:
    - System.IdentityModel.Tokens.Jwt
    - Microsoft.AspNetCore.Authentication.JwtBearer
- [ ] Configure JWT middleware in Startup.cs
- [ ] Create UserController with:
    - POST /api/auth/register (email, password)
    - POST /api/auth/login (email, password) → returns JWT
- [ ] Hash passwords using bcrypt (BCrypt.Net-Next NuGet)
- [ ] Validate JWT tokens on protected endpoints
Learning: Token generation, validation, middleware

Task 2.8: Add Authorization Attributes
- [ ] Add [Authorize] attribute to protected endpoints
- [ ] Test: Access endpoint without token → 401 Unauthorized
- [ ] Test: Access endpoint with token → 200 OK
Learning: Authorization patterns, claim extraction
```

**Day 6: Testing & Documentation (2-3 hours)**
```
Task 2.9: Write Unit Tests
- [ ] Create test project: xUnit
- [ ] Test valid login → expect JWT token
- [ ] Test invalid password → expect 401
- [ ] Test unauthorized access → expect 401
- [ ] Use Moq for mocking dependencies
Learning: Unit testing patterns, mocking

Task 2.10: Document API with Swagger
- [ ] Add Swashbuckle.AspNetCore NuGet
- [ ] Configure Swagger/OpenAPI in Startup.cs
- [ ] Add XML comments to endpoints:
    /// <summary>Register a new user</summary>
    /// <param name="email">User email address</param>
- [ ] Add example request/response bodies
- [ ] Access Swagger UI at /swagger/ui
Learning: API documentation standards, OpenAPI spec
```

### Learning Checkpoints

1. **Database Design**: Explain your schema. What are the relationships? Why did you choose those indexes?
2. **Entity Framework**: Write code to query all notifications for a user using EF Core LINQ
3. **JWT**: Explain JWT structure (header.payload.signature). What's inside the payload?
4. **Authentication**: Create a login endpoint from scratch. What checks do you perform?
5. **Keycloak**: How would you configure OpenID Connect in your API?

### Deliverables
- ✅ PostgreSQL schema with 4 tables created
- ✅ ASP.NET Core project with EF Core configured
- ✅ Health check endpoint working
- ✅ /api/auth/register and /api/auth/login endpoints
- ✅ JWT token generation and validation working
- ✅ Unit tests (>70% coverage on auth)
- ✅ Swagger documentation for all endpoints

**Estimated Time:** 18-22 hours

---

## PHASE 3: User Management & Preferences API (Week 2)

**Duration:** 3-4 days | **Learning Time:** 8-10 hours

### Learning Objectives
- Implement complete CRUD operations
- Master role-based access control (RBAC)
- Document APIs with Swagger
- Write comprehensive unit tests
- Handle validation and error responses

### Key Concepts

| Concept | Why It Matters | Key Learning Points |
|---------|---|---|
| CRUD Operations | Core data management | Create, Read, Update, Delete patterns |
| RBAC | Fine-grained access control | Roles, claims, authorization policies |
| Input Validation | Data integrity & security | Model validation, custom validators |
| Error Handling | User experience | Proper HTTP status codes, error messages |
| Unit Testing | Code quality & confidence | Arrange-Act-Assert pattern, mocking |

### Recommended Learning Resources

**Resource:** *ASP.NET Core Tutorials* (Microsoft Learn)  
- **URL:** https://learn.microsoft.com/en-us/training/modules/build-web-api-aspnet-core/
- **Topics:** Building APIs, handling requests, returning responses
- **Duration:** 2-3 hours

**Resource:** *xUnit Documentation*  
- **URL:** https://xunit.net/docs/getting-started/netfx
- **Topics:** Writing tests, assertions, setup/teardown
- **Duration:** 1-2 hours

### Practical Tasks

**Day 1: CRUD Endpoints (3-4 hours)**
```
Task 3.1: Implement User Preferences Endpoints
- [ ] GET /api/preferences (fetch user preferences, requires auth)
- [ ] PUT /api/preferences (update preferences, requires auth)
- [ ] GET /api/user/profile (fetch user profile, requires auth)

Implementation:
- Extract user ID from JWT claims
- Query database for user preferences
- Validate input data
- Return proper HTTP status codes
Learning: Protected endpoints, token claims extraction

Task 3.2: Add Role-Based Authorization
- [ ] Add role column to users table
- [ ] Create migration: AddRoleToUsers
- [ ] Implement [Authorize(Roles = "Admin")] on admin endpoints
- [ ] Create GET /admin/system-config endpoint (Admin only)
- [ ] Test: Regular user accessing admin endpoint → 403 Forbidden
Learning: RBAC patterns, policy-based authorization
```

**Day 2: Testing & Validation (3-4 hours)**
```
Task 3.3: Write Unit Tests
- [ ] Test POST /api/auth/login with valid credentials → 200 + JWT
- [ ] Test POST /api/auth/login with invalid password → 401
- [ ] Test GET /api/preferences without token → 401
- [ ] Test GET /api/preferences with token → 200 + data
- [ ] Test PUT /api/preferences with invalid data → 400
- [ ] Test admin endpoint as regular user → 403
- [ ] Target > 70% code coverage

Use Moq for database mocking:
  var mockDb = new Mock<IUserRepository>();
  mockDb.Setup(x => x.GetUser(It.IsAny<int>()))
    .Returns(new User { ... });
Learning: AAA pattern, mocking frameworks

Task 3.4: Add Input Validation
- [ ] Use DataAnnotations for model validation:
    [Required]
    [EmailAddress]
    public string Email { get; set; }
- [ ] Create custom validators for business logic
- [ ] Return 400 with validation errors on invalid input
Learning: Model validation, error details
```

**Day 3: Documentation & Polish (2-3 hours)**
```
Task 3.5: Swagger Documentation
- [ ] Add XML comments to all endpoints
- [ ] Add [ProducesResponseType()] attributes:
    [ProducesResponseType(StatusCodes.Status200OK)]
    [ProducesResponseType(StatusCodes.Status401Unauthorized)]
- [ ] Include example request/response bodies
- [ ] Document error responses (400, 401, 403, 404)
Learning: API documentation standards

Task 3.6: Error Handling
- [ ] Create custom exception classes
- [ ] Add global exception middleware
- [ ] Return consistent error response format:
    {
      "error": "...",
      "statusCode": 400,
      "timestamp": "...",
      "traceId": "..."
    }
Learning: Middleware patterns, error consistency
```

### Learning Checkpoints

1. **CRUD**: Write endpoints for creating and updating a notification template
2. **RBAC**: How would you implement different permission levels (viewer, editor, admin)?
3. **Testing**: Write a test that verifies a user can't access another user's preferences
4. **Validation**: What validations should you apply to user email addresses?

### Deliverables
- ✅ GET /api/preferences endpoint with auth
- ✅ PUT /api/preferences endpoint
- ✅ GET /api/user/profile endpoint
- ✅ Role-based authorization configured
- ✅ Swagger documentation complete
- ✅ Unit tests (>70% coverage)
- ✅ Input validation on all endpoints

**Estimated Time:** 10-12 hours

---

## PHASE 4: Notification Queuing with Redpanda (Week 2-3)

**Duration:** 4-5 days | **Learning Time:** 12-15 hours

### Learning Objectives
- Understand event-driven architecture
- Learn Kafka/Redpanda message broker concepts
- Implement asynchronous notification queuing
- Design message formats and partitioning strategies
- Implement rate limiting

### Key Concepts

| Concept | Why It Matters | Key Learning Points |
|---------|---|---|
| Event-Driven Architecture | Scalability, decoupling | Producers, consumers, async patterns |
| Message Queues | Reliability, ordering | Topics, partitions, consumer groups |
| Kafka Concepts | Performance, distribution | Brokers, replication, offset management |
| Rate Limiting | Resource protection | Token bucket, sliding window algorithms |
| Message Formats | Reliability, schema evolution | JSON, Avro, schema validation |

### Recommended Learning Resources

**Resource:** *Kafka Architecture & Concepts*  
- **URL:** https://kafka.apache.org/intro
- **Cost:** Free
- **Duration:** 1-2 hours
- **Level:** Beginner
- **Why This:** Official explanation of Kafka architecture
- **Topics:** Brokers, topics, partitions, producers, consumers, consumer groups

**Resource:** *Redpanda Documentation*  
- **URL:** https://docs.redpanda.com/
- **Cost:** Free
- **Duration:** 2-3 hours
- **Level:** Intermediate
- **Why This:** Official Redpanda docs, compatible with Kafka APIs
- **Key Sections:** Getting started, topics, consumers, error handling

**Resource:** *Reliable Message Processing with Dead Letter Queues* (Redpanda Blog)  
- **URL:** https://www.redpanda.com/blog/reliable-message-processing-with-dead-letter-queue
- **Cost:** Free
- **Duration:** 30-45 minutes
- **Level:** Intermediate
- **Why This:** Best practices for error handling, retry patterns
- **Topics:** DLQ patterns, exponential backoff, non-blocking retries

**Resource:** *Event-Driven Architecture* (Martin Fowler)  
- **URL:** https://www.martinfowler.com/articles/201701-event-driven.html
- **Cost:** Free
- **Duration:** 45-60 minutes
- **Level:** Intermediate
- **Why This:** Architectural patterns, mental models, design thinking
- **Topics:** Event streaming, event sourcing, CQRS patterns

### Practical Tasks

**Day 1: Redpanda Setup (2-3 hours)**
```
Task 4.1: Add Redpanda to Docker Compose
- [ ] Add Redpanda service to docker-compose.yml:
    redpanda:
      image: docker.redpanda.com/redpanda/redpanda
      ports:
        - "9092:9092"
      environment:
        - REDPANDA_ADVERTISED_KAFKA_API_ADDRESSES=redpanda:9092
- [ ] Add rpk CLI tool for topic management
- [ ] Run: docker-compose up redpanda
- [ ] Wait for broker to be ready
Learning: Redpanda configuration, broker setup

Task 4.2: Create Kafka Topics
Using rpk (Redpanda CLI):
- [ ] Create topic "notifications":
    rpk topic create notifications --partitions 3 --replication-factor 1
- [ ] Create topic "notifications-dlq" (dead letter queue)
- [ ] Create topic "events" (for system events)
- [ ] List topics: rpk topic list
- [ ] Inspect topic: rpk topic describe notifications
Learning: Topic design, partitioning strategy
```

**Day 2: .NET Kafka Producer (3-4 hours)**
```
Task 4.3: Implement Event Ingestion Endpoint
- [ ] Add Confluent.Kafka NuGet package
- [ ] Create KafkaProducerService class:
    public async Task PublishAsync(string topic, string message)
- [ ] Implement POST /api/events/{eventType} endpoint:
    - Validate event payload
    - Check rate limiting (10 req/min per user)
    - Save to notification_history with status QUEUED
    - Publish to Redpanda topic
    - Return 202 Accepted (async acknowledgment)
Learning: Kafka producer patterns, async APIs

Task 4.4: Implement Rate Limiting
- [ ] Create RateLimitingMiddleware or use NuGet package
- [ ] Store request counts in memory (for MVP)
- [ ] Check: requests per minute per user
- [ ] Return 429 Too Many Requests if exceeded
- [ ] Example: Limit to 10 requests/minute
Learning: Rate limiting algorithms, middleware
```

**Day 3: Message Design & History (2-3 hours)**
```
Task 4.5: Design Notification Message Format
Define JSON schema:
{
  "notificationId": "uuid",
  "eventType": "order-placed",
  "userId": "uuid",
  "templateId": "uuid",
  "variables": { "orderId": "123", "total": "99.99" },
  "timestamp": "2025-12-22T10:00:00Z",
  "retryCount": 0
}

Learning: Message design, schema thinking

Task 4.6: Implement GET /api/notifications Endpoint
- [ ] Query notification_history for current user
- [ ] Support pagination: ?page=1&limit=20
- [ ] Support filtering: ?status=SENT&type=email
- [ ] Support sorting: ?sortBy=sentAt&order=desc
- [ ] Return paginated results
Learning: Pagination, filtering, sorting patterns
```

**Day 4-5: Testing & Documentation (2-3 hours)**
```
Task 4.7: Test Event Publishing
- [ ] Create test that publishes event and verifies:
    1. Event saved to notification_history
    2. Event published to Kafka topic
    3. Endpoint returns 202 Accepted
- [ ] Test rate limiting:
    1. Send 10 requests → success
    2. Send 11th request → 429 Too Many Requests
Learning: Integration testing, async patterns

Task 4.8: Document Event Format
- [ ] Document /api/events/{eventType} endpoint
- [ ] Include example events:
    - order-placed
    - password-reset
    - meeting-reminder
- [ ] Document response codes (202, 400, 401, 429)
- [ ] Update README with event architecture diagram
Learning: API documentation
```

### Learning Checkpoints

1. **Kafka Concepts**: Explain brokers, topics, and partitions. How do partitions enable parallelism?
2. **Message Design**: Design message format for a "user-signup" event
3. **Rate Limiting**: Write pseudocode for a token bucket rate limiter
4. **Error Handling**: How would you handle a case where Kafka is down but API is running?

### Deliverables
- ✅ Redpanda running in Docker Compose
- ✅ Topics created: notifications, notifications-dlq
- ✅ POST /api/events/{eventType} endpoint
- ✅ Rate limiting implemented (10 req/min per user)
- ✅ GET /api/notifications endpoint with pagination
- ✅ Notification history properly saved
- ✅ Event format documented

**Estimated Time:** 12-15 hours

---

## PHASE 5: Python Worker Service (Week 3)

**Duration:** 4-5 days | **Learning Time:** 12-15 hours

### Learning Objectives
- Learn Python async programming (asyncio)
- Build Kafka consumer for message processing
- Implement template rendering with Jinja2
- Build retry logic and error handling
- Emit Prometheus metrics

### Key Concepts

| Concept | Why It Matters | Key Learning Points |
|---------|---|---|
| Python Async | Non-blocking I/O, concurrency | asyncio, await, coroutines |
| Kafka Consumers | Event consumption, ordering | Consumer groups, offset management |
| Template Rendering | Personalization, flexibility | Jinja2, variable substitution |
| Retry Patterns | Reliability, recovery | Exponential backoff, DLQ routing |
| Metrics Emission | Observability, alerting | Prometheus counters, gauges |

### Recommended Learning Resources

**Resource:** *aiokafka Documentation*  
- **URL:** https://aiokafka.readthedocs.io/
- **Cost:** Free
- **Duration:** 1-2 hours
- **Level:** Intermediate
- **Why This:** Async Kafka consumer, designed for asyncio
- **Topics:** Consumer setup, message consumption, commit handling

**Resource:** *Building Real-Time Data Streaming with Kafka and Asyncio* (Earthly Dev)  
- **URL:** https://earthly.dev/blog/datastreaming-kafka-asyncio/
- **Cost:** Free
- **Duration:** 1-2 hours
- **Level:** Intermediate
- **Why This:** Practical tutorial, real-world patterns
- **Topics:** Async producer/consumer, error handling, example project

**Resource:** *Real Python - asyncio*  
- **URL:** https://realpython.com/async-io-python/
- **Cost:** Free
- **Duration:** 2-3 hours
- **Level:** Beginner to Intermediate
- **Why This:** Comprehensive asyncio guide, clear explanations
- **Topics:** Coroutines, tasks, event loops, async patterns

**Resource:** *Jinja2 Documentation*  
- **URL:** https://jinja.palletsprojects.com/
- **Cost:** Free
- **Duration:** 1-2 hours
- **Level:** Beginner
- **Why This:** Official Jinja2 docs, template syntax, best practices
- **Topics:** Template syntax, filters, inheritance

### Practical Tasks

**Day 1: Python Project Setup (2-3 hours)**
```
Task 5.1: Create Python Worker Project
- [ ] Create /worker folder
- [ ] Create requirements.txt with dependencies:
    aiokafka==0.10.0
    psycopg2-binary==2.9.x
    redis==5.x
    jinja2==3.x
    python-dotenv==1.x
    prometheus_client==0.x
    pydantic==2.x
- [ ] Create virtual environment: python -m venv venv
- [ ] Activate venv: source venv/bin/activate (or .\venv\Scripts\activate on Windows)
- [ ] Install dependencies: pip install -r requirements.txt
Learning: Python dependency management

Task 5.2: Understand asyncio Basics
- [ ] Read Real Python asyncio guide (30-45 min)
- [ ] Understand:
    - Coroutines vs functions
    - async/await syntax
    - Event loop
    - asyncio.run()
    - asyncio.gather() for concurrency
- [ ] Practice: Write 3 simple async functions
Learning: Async programming fundamentals
```

**Day 2: Kafka Consumer (3-4 hours)**
```
Task 5.3: Create Redpanda Consumer
- [ ] Create consumer.py with AIOKafkaConsumer:
    async def start_consumer():
        consumer = AIOKafkaConsumer(
            'notifications',
            bootstrap_servers='redpanda:9092',
            group_id='notification-workers',
            auto_offset_reset='earliest'
        )
        await consumer.start()
        try:
            async for msg in consumer:
                await process_message(msg)
        finally:
            await consumer.stop()

- [ ] Test consumer:
    1. Run docker-compose up redpanda
    2. Run worker: python -m worker.consumer
    3. Publish test message from API
    4. Verify consumer receives message
Learning: Kafka consumer patterns, consumer groups

Task 5.4: Implement Message Processing
- [ ] Create process_message() function:
    async def process_message(msg):
        try:
            data = json.loads(msg.value)
            template = await fetch_template(data['templateId'])
            rendered = render_template(template, data['variables'])
            await send_email(data['userId'], rendered)
            await update_status(data['notificationId'], 'SENT')
        except Exception as e:
            await handle_error(data, e)
Learning: Message deserialization, error handling
```

**Day 3: Template Rendering & Email (3-4 hours)**
```
Task 5.5: Implement Jinja2 Template Rendering
- [ ] Create template_renderer.py
- [ ] Load template from database:
    template_text = await fetch_template(template_id)

- [ ] Render with Jinja2:
    from jinja2 import Template
    template = Template(template_text)
    rendered = template.render(
        userName=data['userName'],
        orderId=data['orderId'],
        orderTotal=data['orderTotal']
    )

- [ ] Test with sample templates:
    "Hello {{userName}}, your order #{{orderId}} for ${{orderTotal}} is confirmed"
Learning: Template engines, variable substitution

Task 5.6: Implement Email Sending (Mock for MVP)
- [ ] For MVP, log to console instead of sending real emails
- [ ] Later: Integrate with SMTP, SendGrid, or AWS SES
- [ ] Create send_email_mock():
    async def send_email(user_id, subject, body):
        logger.info(f"Email to {user_id}: {subject}")
        logger.info(f"Body: {body}")

Learning: Email provider integration patterns
```

**Day 4: Retry Logic & Error Handling (3-4 hours)**
```
Task 5.7: Implement Retry Logic with Exponential Backoff
- [ ] Create retry handler:
    async def process_with_retry(msg, max_retries=3):
        for attempt in range(max_retries):
            try:
                await process_message(msg)
                return
            except Exception as e:
                if attempt < max_retries - 1:
                    wait_time = 2 ** attempt  # 1s, 2s, 4s
                    await asyncio.sleep(wait_time)
                    logger.warning(f"Retry {attempt+1}/{max_retries}")
                else:
                    await move_to_dlq(msg, str(e))

Learning: Exponential backoff pattern, failure recovery

Task 5.8: Dead Letter Queue (DLQ) Handling
- [ ] After 3 failed retries, publish to DLQ topic
- [ ] Create dlq_publisher:
    async def move_to_dlq(message, error):
        dlq_msg = {
            'original_message': message,
            'error': error,
            'timestamp': datetime.now().isoformat(),
            'retry_count': 3
        }
        await producer.send('notifications-dlq', dlq_msg)

Learning: DLQ patterns, failure tracking
```

**Day 5: Metrics & Monitoring (2-3 hours)**
```
Task 5.9: Add Prometheus Metrics
- [ ] Create metrics using prometheus_client:
    from prometheus_client import Counter, Gauge, Histogram

    notifications_sent = Counter(
        'notifications_sent_total',
        'Total notifications sent successfully'
    )
    notifications_failed = Counter(
        'notifications_failed_total',
        'Total notifications failed'
    )
    queue_depth = Gauge(
        'queue_depth',
        'Current messages in queue'
    )
    processing_duration = Histogram(
        'notification_processing_duration_seconds',
        'Time to process notification'
    )

- [ ] Emit metrics:
    notifications_sent.inc()
    notifications_failed.inc()
    with processing_duration.time():
        await process_message(msg)

Learning: Prometheus metrics instrumentation

Task 5.10: Add Structured Logging
- [ ] Use JSON logging for easy parsing:
    import logging
    logging.basicConfig(
        level=logging.INFO,
        format='%(message)s'
    )
    
    logger.info(json.dumps({
        'event': 'notification_sent',
        'notification_id': '123',
        'user_id': '456',
        'duration_ms': 234
    }))

Learning: Structured logging patterns
```

### Learning Checkpoints

1. **asyncio**: Write an async function that waits for 2 seconds, then prints "Done"
2. **Kafka Consumer**: Create a consumer group and explain how offsets work
3. **Templates**: Write a Jinja2 template for a password reset email
4. **Retry Logic**: What's the delay sequence for 3 retries with exponential backoff?

### Deliverables
- ✅ Python worker project created with requirements.txt
- ✅ Kafka consumer implemented with consumer groups
- ✅ Message processing pipeline
- ✅ Jinja2 template rendering
- ✅ Email sending (mock for MVP)
- ✅ Retry logic with exponential backoff (max 3 retries)
- ✅ Dead letter queue routing
- ✅ Prometheus metrics emitted
- ✅ Structured JSON logging

**Estimated Time:** 14-16 hours

---

## PHASE 6: React Frontend - User Dashboard (Week 3-4)

**Duration:** 4-5 days | **Learning Time:** 15-18 hours

### Learning Objectives
- Build interactive React UIs with TypeScript
- Manage state and side effects with hooks
- Implement authentication and protected routes
- Make HTTP calls with axios
- Handle loading and error states

### Key Concepts

| Concept | Why It Matters | Key Learning Points |
|---------|---|---|
| React Hooks | State management, side effects | useState, useEffect, useContext, useReducer |
| TypeScript | Type safety, error prevention | Interfaces, generics, types for props |
| React Router | Navigation, protected routes | Routes, Link, useNavigate, route guards |
| HTTP Client | API communication | axios, interceptors, error handling |
| State Management | Component communication | Context API, custom hooks, lifting state |

### Recommended Learning Resources

**Resource:** *React Official Documentation*  
- **URL:** https://react.dev
- **Cost:** Free
- **Duration:** 3-4 hours
- **Level:** Beginner
- **Why This:** Official, modern, comprehensive
- **Topics:** Components, hooks, state, effects, context

**Resource:** *React + TypeScript: Best Practices Tutorial* (YouTube - Kodaps)  
- **URL:** https://www.youtube.com/watch?v=FknaQpe9Y5s
- **Cost:** Free
- **Duration:** 30-45 minutes
- **Level:** Beginner to Intermediate
- **Why This:** Recent, practical examples, TypeScript focus
- **Topics:** Functional components, props typing, hooks with types

**Resource:** *Context API & Generics* (Frontend Masters)  
- **URL:** https://frontendmasters.com/courses/react-typescript-v3/
- **Cost:** $39/month subscription or $299/year
- **Duration:** 3-4 hours
- **Level:** Intermediate
- **Why This:** Expert instruction, advanced patterns, real-world examples
- **Topics:** useState type safety, form handling, state management, generics

**Resource:** *React Router Documentation*  
- **URL:** https://reactrouter.com/
- **Cost:** Free
- **Duration:** 1-2 hours
- **Level:** Beginner to Intermediate
- **Why This:** Official documentation, modern features
- **Topics:** Routes, navigation, protected routes, params

**Resource:** *Axios Documentation*  
- **URL:** https://axios-http.com/
- **Cost:** Free
- **Duration:** 45-60 minutes
- **Level:** Beginner
- **Why This:** Clear examples, interceptors, error handling
- **Topics:** HTTP verbs, headers, interceptors, timeouts

### Practical Tasks

**Day 1: React Project Setup (3-4 hours)**
```
Task 6.1: Create React Project
- [ ] Create with TypeScript:
    npx create-react-app frontend --template typescript
- [ ] Install dependencies:
    npm install axios react-router-dom tailwindcss zustand
- [ ] Configure Tailwind CSS:
    npm install -D tailwindcss postcss autoprefixer
    npx tailwindcss init -p
- [ ] Update tailwind.config.js with template paths
- [ ] Test: npm start (should open http://localhost:3000)
Learning: React project structure, TypeScript setup

Task 6.2: Set Up Basic Project Structure
- [ ] Create folders:
    /src
      /components (reusable UI)
      /pages (full pages)
      /services (API calls)
      /context (state management)
      /types (TypeScript interfaces)
      /hooks (custom hooks)
- [ ] Create App.tsx with basic routing
Learning: Project organization, module separation
```

**Day 2: Authentication Flow (3-4 hours)**
```
Task 6.3: Create Authentication Context
- [ ] Create src/context/AuthContext.tsx:
    interface AuthContextType {
      user: User | null;
      token: string | null;
      login: (email, password) => Promise<void>;
      register: (email, password) => Promise<void>;
      logout: () => void;
      isLoading: boolean;
    }

- [ ] Implement with useReducer for complex state
- [ ] Store JWT in localStorage (with warnings about security)
Learning: Context API, custom hooks, state management

Task 6.4: Create Login & Register Pages
- [ ] Create pages/LoginPage.tsx:
    - Email input
    - Password input
    - Login button
    - Link to register
    - Error message display
    - Loading state

- [ ] Create pages/RegisterPage.tsx:
    - Email input
    - Password input (with strength indicator)
    - Confirm password
    - Register button
    - Link to login
    - Terms checkbox

- [ ] Handle form submission:
    const { login } = useContext(AuthContext);
    await login(email, password);

Learning: Form handling, context integration
```

**Day 3: Protected Routes & API Integration (3-4 hours)**
```
Task 6.5: Create Protected Route Component
- [ ] Create components/ProtectedRoute.tsx:
    <ProtectedRoute>
      <DashboardPage />
    </ProtectedRoute>

- [ ] Implementation:
    - Check if user is authenticated
    - If not, redirect to login
    - If yes, render component

Learning: Route guards, redirect patterns

Task 6.6: Create API Service with Axios
- [ ] Create src/services/api.ts:
    import axios from 'axios';
    
    const api = axios.create({
      baseURL: 'http://localhost:5000/api'
    });
    
    // Add Bearer token to all requests
    api.interceptors.request.use((config) => {
      const token = localStorage.getItem('token');
      if (token) {
        config.headers.Authorization = `Bearer ${token}`;
      }
      return config;
    });
    
    export const userService = {
      getPreferences: () => api.get('/preferences'),
      updatePreferences: (data) => api.put('/preferences', data),
      getProfile: () => api.get('/user/profile'),
      getNotifications: (page: number) => 
        api.get(`/notifications?page=${page}&limit=20`)
    };

Learning: Axios setup, interceptors, HTTP patterns
```

**Day 4: User Dashboard (3-4 hours)**
```
Task 6.7: Build Dashboard Layout
- [ ] Create pages/DashboardPage.tsx:
    - Header with user name and logout button
    - Navigation tabs (Notifications, Preferences, Profile)
    - Main content area

Learning: Component composition, layout patterns

Task 6.8: Implement Notification History Table
- [ ] Create components/NotificationTable.tsx:
    - Fetch notifications with useEffect
    - Display as table with columns:
      - Date
      - Type
      - Subject
      - Status (SENT, FAILED, QUEUED)
    - Pagination controls
    - Sort functionality
    - Loading spinner while fetching
    - Error message on failure

- [ ] Handle loading state:
    const [loading, setLoading] = useState(false);
    const [error, setError] = useState<string | null>(null);
    
    useEffect(() => {
      setLoading(true);
      userService.getNotifications(page)
        .then(res => setNotifications(res.data))
        .catch(err => setError(err.message))
        .finally(() => setLoading(false));
    }, [page]);

Learning: Data fetching, pagination, error handling
```

**Day 5: Preferences & Polish (2-3 hours)**
```
Task 6.9: Implement Preferences Toggle
- [ ] Create components/PreferencesPanel.tsx:
    - Fetch user preferences on load
    - Toggle: "Enable email notifications"
    - Save button
    - Success/error message on save
    - Loading state while saving

- [ ] Implementation:
    const [preferences, setPreferences] = useState(null);
    
    useEffect(() => {
      userService.getPreferences()
        .then(res => setPreferences(res.data));
    }, []);
    
    const handleToggle = async () => {
      await userService.updatePreferences({
        emailEnabled: !preferences.emailEnabled
      });
    };

Learning: Two-way data binding, form updates

Task 6.10: Add Test Notification Button
- [ ] Create button to send test notification via API
- [ ] POST /api/events/test-notification
- [ ] Show "notification sent" message on success
- [ ] Use for quick testing during development

Learning: API integration, user feedback
```

### Learning Checkpoints

1. **React Hooks**: Explain useState and useEffect. When do you use each?
2. **TypeScript Props**: Create a button component with typed props
3. **Protected Routes**: How do you prevent unauthenticated users from accessing the dashboard?
4. **API Integration**: Write code to fetch notifications and display them with loading state
5. **State Management**: When would you use Context API vs local component state?

### Deliverables
- ✅ React project created with TypeScript
- ✅ Login and register pages
- ✅ AuthContext for state management
- ✅ Protected routes implemented
- ✅ API service with axios and interceptors
- ✅ Dashboard page with tabs
- ✅ Notification history table with pagination
- ✅ Preferences toggle
- ✅ Loading and error states
- ✅ Test notification button

**Estimated Time:** 16-18 hours

---

## PHASE 7: Admin Dashboard & Metrics (Week 4)

**Duration:** 3-4 days | **Learning Time:** 10-12 hours

### Learning Objectives
- Build admin-only dashboards
- Learn Prometheus metrics concepts
- Configure Grafana for monitoring
- Create PromQL queries
- Design monitoring dashboards

### Key Concepts

| Concept | Why It Matters | Key Learning Points |
|---------|---|---|
| Metrics Types | Observability | Counters, gauges, histograms, summaries |
| Prometheus | Monitoring system | Scrape configs, targets, data storage |
| PromQL | Query language | Selectors, operators, functions |
| Grafana | Visualization | Dashboards, panels, data sources, variables |
| Alerting | Incident response | Alert rules, thresholds, notifications |

### Recommended Learning Resources

**Resource:** *Prometheus Monitoring: Configure & Visualize Systems* (Coursera)  
- **URL:** https://www.coursera.org/learn/prometheus-monitoring-configure-visualize-systems
- **Cost:** Free to audit
- **Duration:** 3-4 hours
- **Level:** Beginner
- **Why This:** Official Prometheus content, comprehensive, hands-on labs
- **Topics:** Installation, scraping, PromQL, Grafana integration

**Resource:** *Monitoring Made EASY with Grafana and Prometheus!* (YouTube)  
- **URL:** https://www.youtube.com/watch?v=pGSkPutCKtQ
- **Cost:** Free
- **Duration:** 10 minutes
- **Level:** Beginner
- **Why This:** Quick visual introduction, docker-compose setup, dashboard creation
- **Topics:** Setup, configuration, dashboard creation

**Resource:** *Prometheus Official Documentation*  
- **URL:** https://prometheus.io/docs/
- **Cost:** Free
- **Duration:** 2-3 hours (reference)
- **Level:** Intermediate
- **Why This:** Complete reference, all features, best practices

**Resource:** *Grafana Official Documentation*  
- **URL:** https://grafana.com/docs/
- **Cost:** Free
- **Duration:** 2-3 hours (reference)
- **Level:** Intermediate
- **Why This:** Complete reference, dashboard creation, alerting

### Practical Tasks

**Day 1: Prometheus Integration (2-3 hours)**
```
Task 7.1: Add Prometheus to .NET API
- [ ] Install NuGet package: prometheus-net
- [ ] Create MetricsService.cs:
    using Prometheus;
    
    public class MetricsService
    {
        private static readonly Counter NotificationsSent = 
            Counter.Create("notifications_sent_total",
                "Total notifications sent");
        
        private static readonly Counter NotificationsFailed = 
            Counter.Create("notifications_failed_total",
                "Total notifications failed");
        
        private static readonly Gauge QueueDepth = 
            Gauge.Create("queue_depth",
                "Current queue depth");
        
        public void RecordSent() => NotificationsSent.Inc();
        public void RecordFailed() => NotificationsFailed.Inc();
        public void SetQueueDepth(int count) => QueueDepth.Set(count);
    }

- [ ] Add metrics endpoint to Startup.cs:
    app.UseMetricServer("/metrics");

- [ ] Test: http://localhost:5000/metrics (should return Prometheus format)
Learning: Metrics instrumentation, counter/gauge types

Task 7.2: Emit Metrics from API
- [ ] Inject MetricsService into controllers
- [ ] Record metrics on events:
    [HttpPost("/events/{eventType}")]
    public async Task Post(string eventType, [FromBody] EventDto evt)
    {
        // ... process event ...
        _metrics.RecordSent();
        return Accepted();
    }

- [ ] Update queue depth metric periodically
Learning: Metric emission, controller integration
```

**Day 2: Prometheus & Grafana Setup (2-3 hours)**
```
Task 7.3: Configure Prometheus
- [ ] Create prometheus.yml in /infra folder:
    global:
      scrape_interval: 15s
      evaluation_interval: 15s
    
    scrape_configs:
      - job_name: 'notification-api'
        static_configs:
          - targets: ['api:5000']
      
      - job_name: 'notification-worker'
        static_configs:
          - targets: ['worker:8000']

- [ ] Add Prometheus to docker-compose.yml:
    prometheus:
      image: prom/prometheus
      ports:
        - "9090:9090"
      volumes:
        - ./infra/prometheus.yml:/etc/prometheus/prometheus.yml

- [ ] Test: http://localhost:9090 (Prometheus UI)
Learning: Prometheus configuration, scrape targets

Task 7.4: Set Up Grafana
- [ ] Add to docker-compose.yml:
    grafana:
      image: grafana/grafana
      ports:
        - "3001:3000"
      environment:
        - GF_SECURITY_ADMIN_PASSWORD=admin

- [ ] Run: docker-compose up grafana
- [ ] Access: http://localhost:3001 (username: admin, password: admin)
- [ ] Add Prometheus as data source:
    1. Data Sources → Add Prometheus
    2. URL: http://prometheus:9090
    3. Save & Test

Learning: Grafana configuration, data sources
```

**Day 3: Dashboards & Queries (2-3 hours)**
```
Task 7.5: Create PromQL Queries
Learn basic PromQL:
- [ ] Query: notifications_sent_total (raw counter)
- [ ] Query: rate(notifications_sent_total[1m]) (per second)
- [ ] Query: 
    (rate(notifications_failed_total[1m]) / 
     rate(notifications_sent_total[1m])) * 100
    (failure rate percentage)

- [ ] Test queries in Prometheus UI
Learning: PromQL syntax, functions, rates

Task 7.6: Build Grafana Dashboard
- [ ] Create new dashboard
- [ ] Add 4 panels:

Panel 1: Notifications Sent per Minute
  - Type: Line chart
  - Query: rate(notifications_sent_total[1m])
  - Y-axis label: "Notifications/min"

Panel 2: Error Rate %
  - Type: Gauge
  - Query: (rate(notifications_failed_total[1m]) / 
           rate(notifications_sent_total[1m])) * 100
  - Units: percent
  - Thresholds: 0-5 (green), 5-10 (yellow), 10+ (red)

Panel 3: Queue Depth
  - Type: Line chart
  - Query: queue_depth
  - Y-axis label: "Messages in Queue"

Panel 4: API Response Time (p95)
  - Type: Line chart
  - Query: histogram_quantile(0.95, 
           rate(http_request_duration_seconds[5m]))
  - Y-axis label: "Duration (seconds)"

- [ ] Save dashboard
Learning: Dashboard creation, panel types, thresholds
```

### Learning Checkpoints

1. **Metrics Types**: Explain when to use counter vs gauge vs histogram
2. **PromQL**: Write query to calculate error rate percentage
3. **Prometheus**: How does scraping work? What's a job vs a target?
4. **Grafana**: Create a gauge panel that shows a percentage

### Deliverables
- ✅ prometheus-net integrated into .NET API
- ✅ /metrics endpoint exposed
- ✅ Counters and gauges emitted
- ✅ prometheus.yml configured
- ✅ Prometheus running in Docker Compose
- ✅ Grafana configured with Prometheus data source
- ✅ Grafana dashboard with 4 panels
- ✅ PromQL queries for key metrics

**Estimated Time:** 10-12 hours

---

## PHASE 8: Docker & Docker Compose (Week 4)

**Duration:** 2-3 days | **Learning Time:** 6-8 hours

### Learning Objectives
- Build production-grade Docker images
- Master multi-stage builds
- Optimize image sizes
- Configure Docker Compose for local dev

### Key Concepts

| Concept | Why It Matters | Key Learning Points |
|---------|---|---|
| Multi-stage Builds | Image optimization | Build stage vs runtime stage |
| Image Optimization | Performance, storage | Layer caching, .dockerignore |
| Networking | Service communication | Custom networks, DNS resolution |
| Health Checks | Reliability | Liveness, readiness probes |

### Practical Tasks

**Day 1-2: Create Dockerfiles (3-4 hours)**
```
Task 8.1: .NET API Dockerfile
- [ ] Create api/Dockerfile:
    FROM mcr.microsoft.com/dotnet/sdk:8.0 AS builder
    WORKDIR /src
    COPY . .
    RUN dotnet publish -c Release -o /app
    
    FROM mcr.microsoft.com/dotnet/aspnet:8.0
    WORKDIR /app
    COPY --from=builder /app .
    ENV ASPNETCORE_URLS=http://+:5000
    EXPOSE 5000
    CMD ["dotnet", "NotificationAPI.dll"]

- [ ] Create .dockerignore:
    bin/
    obj/
    .git/
    .vs/

Learning: Multi-stage builds, layers optimization

Task 8.2: Python Worker Dockerfile
- [ ] Create worker/Dockerfile:
    FROM python:3.11-slim
    WORKDIR /app
    COPY requirements.txt .
    RUN pip install --no-cache-dir -r requirements.txt
    COPY . .
    CMD ["python", "-m", "worker.main"]

- [ ] Create .dockerignore:
    __pycache__/
    .pytest_cache/
    venv/
    *.pyc

Learning: Python image optimization

Task 8.3: React Frontend Dockerfile
- [ ] Create frontend/Dockerfile:
    # Build stage
    FROM node:20-alpine AS builder
    WORKDIR /app
    COPY package*.json .
    RUN npm ci
    COPY . .
    RUN npm run build
    
    # Runtime stage
    FROM nginx:alpine
    COPY --from=builder /app/build /usr/share/nginx/html
    COPY nginx.conf /etc/nginx/nginx.conf
    EXPOSE 3000
    CMD ["nginx", "-g", "daemon off;"]

- [ ] Create frontend/nginx.conf for SPA routing

Learning: Frontend image optimization, multi-stage for Node
```

**Day 3: Complete docker-compose.yml (2-3 hours)**
```
Task 8.4: Full Docker Compose Setup
- [ ] Update docker-compose.yml with all services
- [ ] Configure networks: create custom network
- [ ] Add health checks to critical services
- [ ] Add volume mounts for persistence
- [ ] Add environment variables from .env

Example structure:
version: '3.8'

networks:
  notification-network:
    driver: bridge

services:
  postgres:
    image: postgres:15
    environment:
      POSTGRES_USER: ${POSTGRES_USER}
      POSTGRES_PASSWORD: ${POSTGRES_PASSWORD}
      POSTGRES_DB: ${POSTGRES_DB}
    ports:
      - "5432:5432"
    volumes:
      - postgres_data:/var/lib/postgresql/data
    networks:
      - notification-network
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U ${POSTGRES_USER}"]
      interval: 10s
      timeout: 5s
      retries: 5

  api:
    build: ./api
    ports:
      - "5000:5000"
    depends_on:
      postgres:
        condition: service_healthy
    environment:
      DATABASE_URL: postgresql://...
      KAFKA_BROKERS: redpanda:9092
    networks:
      - notification-network
    healthcheck:
      test: ["CMD", "curl", "-f", "http://localhost:5000/api/health"]
      interval: 10s
      timeout: 5s
      retries: 3

  # ... (redis, redpanda, prometheus, grafana, keycloak)

volumes:
  postgres_data:
  redis_data:

Learning: docker-compose configuration, networking, health checks
```

**Task 8.5: Test Full Stack**
```
- [ ] Build all images: docker-compose build
- [ ] Start all services: docker-compose up
- [ ] Wait for all services to be healthy
- [ ] Test connectivity:
    - API health: curl http://localhost:5000/api/health
    - Frontend: http://localhost:3000
    - Grafana: http://localhost:3001
    - Prometheus: http://localhost:9090
- [ ] Check logs: docker-compose logs -f service_name
- [ ] Verify network communication between services
Learning: Multi-service debugging, network verification
```

### Deliverables
- ✅ Dockerfile for each service (API, Worker, Frontend)
- ✅ Multi-stage builds for optimization
- ✅ .dockerignore files
- ✅ Complete docker-compose.yml
- ✅ Health checks configured
- ✅ All services running together
- ✅ Single command startup: docker-compose up

**Estimated Time:** 6-8 hours

---

## PHASE 9: Integration Testing & Documentation (Week 4-5)

**Duration:** 3-4 days | **Learning Time:** 8-10 hours

### Learning Objectives
- Write end-to-end integration tests
- Create comprehensive documentation
- Achieve >70% code coverage
- Document APIs and deployment

### Key Resources

**Resource:** *xUnit Testing Best Practices*  
- **URL:** https://xunit.net/docs/getting-started/netfx

**Resource:** *Postman Documentation*  
- **URL:** https://learning.postman.com/

### Practical Tasks

**Day 1-2: E2E Testing (2-3 hours)**
```
Task 9.1: Write End-to-End Test Script
- [ ] Create test.sh or PowerShell script:
    #!/bin/bash
    
    API="http://localhost:5000/api"
    FRONTEND="http://localhost:3000"
    
    # 1. Register user
    curl -X POST $API/auth/register \
      -H "Content-Type: application/json" \
      -d '{"email":"test@example.com","password":"TestPass123"}'
    
    # 2. Login and get token
    TOKEN=$(curl -s -X POST $API/auth/login \
      -H "Content-Type: application/json" \
      -d '{"email":"test@example.com","password":"TestPass123"}' \
      | jq -r '.token')
    
    # 3. Send test notification
    curl -X POST $API/events/test-notification \
      -H "Authorization: Bearer $TOKEN" \
      -H "Content-Type: application/json" \
      -d '{}'
    
    # 4. Wait and verify
    sleep 5
    curl -s http://localhost:3000 | grep -q "Notification sent"
    
    echo "✅ E2E test passed!"

Learning: Bash scripting, API testing, wait strategies

Task 9.2: Unit Test Coverage
- [ ] Ensure >70% code coverage:
    - .NET: dotnet test /p:CollectCoverage=true
    - Python: pytest --cov=worker
    - React: npm test -- --coverage
- [ ] Add tests for critical paths:
    - User authentication
    - Notification queueing
    - Worker processing
    - API error handling
Learning: Coverage measurement, test prioritization
```

**Day 3: Documentation (2-3 hours)**
```
Task 9.3: Update README
- [ ] Sections:
    1. Overview (what it does, why)
    2. Architecture diagram
    3. Tech stack table
    4. Quick start (git clone, docker-compose up)
    5. Development guide
    6. API documentation
    7. Contributing guidelines
    8. Troubleshooting
    9. Next steps

Learning: Technical writing

Task 9.4: API Documentation
- [ ] Document each endpoint:
    Method: POST
    Path: /api/events/{eventType}
    Auth: Bearer token
    Request:
      {
        "userId": "string",
        "templateId": "string",
        "variables": {}
      }
    Response: 202 Accepted
    Errors: 400, 401, 429

- [ ] Export Swagger/OpenAPI spec:
    http://localhost:5000/swagger/v1/swagger.json

Learning: API documentation standards

Task 9.5: Database Schema Documentation
- [ ] Create ERD diagram with tool like draw.io
- [ ] Document each table:
    Table: users
    Purpose: Store user accounts
    Columns:
      - id (UUID, PK)
      - email (VARCHAR, unique)
      - password_hash (VARCHAR)
      - created_at (TIMESTAMP)
    Relationships:
      - notifications_history.user_id → users.id

Learning: Schema documentation
```

### Deliverables
- ✅ End-to-end test script
- ✅ >70% code coverage
- ✅ Updated README with full documentation
- ✅ API documentation for all endpoints
- ✅ Database schema documentation
- ✅ Deployment guide

**Estimated Time:** 8-10 hours

---

## PHASE 10: Final Testing & Demo Preparation (Week 5)

**Duration:** 3-4 days | **Learning Time:** 6-8 hours

### Practical Tasks

**Day 1-2: System Validation (2-3 hours)**
```
Task 10.1: Fresh Environment Test
- [ ] Clean Docker environment:
    docker-compose down -v
    docker system prune
- [ ] Fresh start: docker-compose up
- [ ] Run E2E test script
- [ ] Verify all services healthy
- [ ] Check Grafana metrics updated

Task 10.2: Load Testing
- [ ] Simple stress test (100 concurrent notifications):
    for i in {1..100}; do
      curl -X POST http://localhost:5000/api/events/test \
        -H "Authorization: Bearer $TOKEN" &
    done
- [ ] Monitor in Grafana
- [ ] Check for message loss
- [ ] Verify retries work for failures
Learning: Performance testing basics
```

**Day 3: Demo Preparation (2-3 hours)**
```
Task 10.3: Create Demo Script
Prepare to demonstrate:
1. **Architecture Overview (2 min)**
   - Show architecture diagram
   - Explain flow

2. **User Registration (1 min)**
   - Open web UI
   - Register new user
   - Show redirect to dashboard

3. **Send Notification (1 min)**
   - Click "Send Test Notification"
   - Show request in Postman
   - Show notification queued

4. **View History (1 min)**
   - Navigate to notification history
   - Show notifications with status
   - Explain pagination

5. **Admin Dashboard (1 min)**
   - Navigate to admin panel
   - Show system metrics
   - Explain each metric

6. **Grafana Monitoring (1 min)**
   - Show real-time metrics
   - Explain dashboard panels
   - Show error alerts

7. **Code Walkthrough (3 min)**
   - Show key components
   - Explain architecture decisions
   - Highlight interesting code

Learning: Presentation skills, system knowledge
```

### Deliverables
- ✅ Clean fresh deployment working
- ✅ All E2E tests passing
- ✅ Demo script prepared
- ✅ Performance tested
- ✅ System documentation complete
- ✅ Code ready for review

**Estimated Time:** 6-8 hours

---

## Summary Schedule

| Week | Phases | Duration | Learning Hours | Focus |
|------|--------|----------|-----------------|-------|
| Week 1 | 1-2 | 6-7 days | 20-24 hours | Git, Docker, PostgreSQL, .NET setup |
| Week 2 | 3-4 | 7-8 days | 20-24 hours | CRUD, Auth, RBAC, Queuing |
| Week 3 | 5-6 | 8-9 days | 25-30 hours | Python Worker, React Frontend |
| Week 4 | 7-8-9 | 8-10 days | 24-30 hours | Monitoring, Docker, Documentation |
| Week 5 | 10 | 3-4 days | 6-8 hours | Final testing, Demo prep |
| **Total** | **1-10** | **35-38 days** | **95-120 hours** | **Full MVP** |

---

## Daily Learning Tips

### Morning (30 minutes)
- Review yesterday's concepts
- Read documentation for today's phase
- Watch 1-2 YouTube videos on key topics

### Hands-On (3-4 hours)
- Implement tasks from phase checklist
- Use IDE/editor with autocomplete
- Reference documentation as needed
- Test code locally

### Evening (1 hour)
- Review what was learned
- Update learning checkpoint notes
- Plan next day's tasks
- Document any challenges

### Weekly Review
- Go through learning checkpoints
- Review deliverables
- Check if code is production-ready
- Plan next week

---

## Learning Checkpoint Assessment Template

After each phase, assess yourself:

```
PHASE X: [Phase Name]

Knowledge Check:
- [ ] Can explain core concept 1?
- [ ] Can explain core concept 2?
- [ ] Can code core feature 1 from memory?
- [ ] Can code core feature 2 from memory?

Code Quality:
- [ ] Code follows best practices?
- [ ] >70% test coverage achieved?
- [ ] All error cases handled?
- [ ] Documentation complete?

Deliverables:
- [ ] Feature working end-to-end?
- [ ] Code pushed to Git?
- [ ] Reviewed and ready for production?

Time Tracking:
- Estimated: X hours
- Actual: X hours
- +/- Variance: X hours
- Notes: ...
```

---

## Resource Summary Table

| Technology | Best Resource | Duration | Type | Cost | Link |
|------------|---------------|----------|------|------|------|
| Git | Git Flow Article | 20 min | Blog | Free | nvie.com/posts/a-successful-git-branching-model/ |
| Docker | Docker Absolute Beginner | 1.5h | Video | $15 | udemy.com/course/docker-for-the-absolute-beginner |
| Docker Compose | Official Docs | 45 min | Docs | Free | docker.com/compose |
| PostgreSQL | Neon Tutorial | 2-3h | Tutorial | Free | neon.com/postgresql/tutorial |
| ASP.NET Core | YouTube Course | 3.5h | Video | Free | youtube.com/@YouTubeChannel |
| Entity Framework | EF Docs | 2-3h | Docs | Free | docs.microsoft.com/en-us/ef/core/ |
| React + TS | Frontend Masters | 3-4h | Video | $39/mo | frontendmasters.com/courses/react-typescript-v3/ |
| JWT/OAuth2 | FastAPI Guide | 1-2h | Docs | Free | fastapi.tiangolo.com/tutorial/security/oauth2-jwt/ |
| Kafka/Redpanda | Redpanda Docs | 2-3h | Docs | Free | docs.redpanda.com |
| Python Async | Real Python | 2-3h | Guide | Free | realpython.com/async-io-python/ |
| Prometheus | Coursera | 3-4h | Course | Free | coursera.org/learn/prometheus-monitoring |
| Grafana | YouTube | 10 min | Video | Free | youtube.com (Monitoring Made Easy) |

---

## Success Criteria Checklist

By the end of 5 weeks, you should be able to:

- ✅ Explain the complete architecture and why each component exists
- ✅ Set up entire system with single `docker-compose up` command
- ✅ Register user, send notification, view in history (end-to-end)
- ✅ Monitor system health via Grafana dashboard
- ✅ Write and run unit tests with >70% coverage
- ✅ Document APIs using Swagger/OpenAPI
- ✅ Implement retry logic and error handling
- ✅ Perform basic load testing and optimization
- ✅ Deploy to cloud (GCP/AWS in future phases)
- ✅ Explain architectural decisions confidently

---

**Document Version:** 1.0  
**Last Updated:** December 22, 2025  
**Total Learning Resources:** 30+ curated sources  
**Estimated Completion:** 5-6 weeks with full commitment