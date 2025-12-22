# Real-Time Notification & Event Management Platform
## Software Requirements Document (SRD) with Integrated Learning Roadmap

**Version:** 2.0  
**Date:** December 22, 2025  
**Status:** MVP Definition with Learning Path  
**Document Type:** Software Requirements, Technical Specification & Learning Roadmap

---

## Quick Overview

This is a **combined requirements + learning roadmap document**. Each phase includes:
- ✅ **What to build** (specific tasks and deliverables)
- 📚 **What to learn** (concepts, why they matter, resources)
- 🎯 **Learning checkpoints** (how to validate understanding)

**Total Timeline:** 5 weeks | **Total Learning:** 60-100 hours of hands-on development

---

## Phase 1: Project Setup & Infrastructure (Week 1)

### Learning Objectives
- Understand project structure and Git workflow
- Learn Docker fundamentals and Compose orchestration
- Master environment configuration patterns

### Key Concepts to Learn
- Git branching strategy (main, develop, feature branches)
- Docker container basics (images, containers, layers)
- Docker Compose service orchestration
- Environment variables and .env files
- Project folder structure best practices

### Resources to Study
- Docker Official Docs: https://docs.docker.com/get-started/
- Docker Compose Overview: https://docs.docker.com/compose/
- Git Branching Model: https://nvie.com/posts/a-successful-git-branching-model/

### Tasks

- [ ] **Initialize Git repository**
  - [ ] Create main branch, develop branch
  - [ ] Add .gitignore files
  - **What you learn:** Git workflow, branching strategy
  - **Why it matters:** Team coordination, version control

- [ ] **Create project structure**
  - [ ] `/api`, `/worker`, `/frontend`, `/infra`, `/docs` folders
  - **What you learn:** Multi-tier architecture, separation of concerns
  - **Why it matters:** Scalability, maintainability

- [ ] **Create `.env.example` and `.env.local`**
  - [ ] Document all environment variables
  - [ ] Add `.env` to `.gitignore`
  - **What you learn:** Secrets management, security
  - **Why it matters:** Never hardcode secrets, secure deployments

- [ ] **Write comprehensive README**
  - [ ] Overview, tech stack, quick start, architecture diagram
  - **What you learn:** Technical documentation, communication
  - **Why it matters:** Team collaboration, interview material

- [ ] **Create `docker-compose.yml` skeleton**
  - [ ] Define 8 services with ports and networks
  - **What you learn:** Docker Compose syntax, orchestration concepts
  - **Why it matters:** Reproducible local environments

### Deliverable
Git repo with structure, docker-compose skeleton, README

### Learning Checkpoint
- Can you explain Docker image vs container?
- Can you write basic docker-compose.yml?
- Why do you need .env files?

---

## Phase 2: Database Schema & Core API (Week 1-2)

### Learning Objectives
- Design relational databases and create schemas
- Build RESTful APIs with .NET
- Understand Entity Framework Core ORM
- Learn authentication with Keycloak and JWT

### Key Concepts to Learn
- Database normalization and schema design
- SQL basics (CREATE TABLE, relationships, indexes)
- ORM (Object-Relational Mapping) patterns
- RESTful API design principles
- JWT tokens and OAuth2 flow
- HTTP status codes and error handling

### Resources to Study
- PostgreSQL Documentation: https://www.postgresql.org/docs/
- Entity Framework Core: https://docs.microsoft.com/en-us/ef/core/
- JWT.io Introduction: https://jwt.io/introduction
- RESTful API Best Practices: https://restfulapi.net/

### Tasks

- [ ] **Design database schema**
  - [ ] Create `users`, `notification_templates`, `notification_history`, `user_preferences` tables
  - [ ] Research: Why use UUID? Why hash passwords?
  - [ ] Create indexes on frequently queried columns
  - **What you learn:** Database design, normalization, performance optimization
  - **Why it matters:** Query performance, data integrity

- [ ] **Set up .NET API project**
  - [ ] Create ASP.NET Core Web API project
  - [ ] Configure Entity Framework Core with PostgreSQL
  - [ ] Create Models and DbContext
  - [ ] Create health check endpoint: `GET /api/health`
  - **What you learn:** .NET project structure, ORM basics, dependency injection
  - **Why it matters:** Modern .NET development

- [ ] **Implement authentication**
  - [ ] Set up Keycloak instance (Docker)
  - [ ] Create realm and client
  - [ ] Implement `/api/auth/register` endpoint (email/password)
  - [ ] Implement `/api/auth/login` endpoint (return JWT)
  - [ ] Add Bearer token validation middleware
  - **What you learn:** OAuth2/JWT flow, token validation, middleware patterns
  - **Why it matters:** Enterprise authentication, security

### Deliverable
Working API with auth, database connected, health check functional

### Learning Checkpoint
- Can you design a normalized database schema?
- Explain authentication vs authorization?
- Can you create and validate JWT tokens?

---

## Phase 3: User Management & Preferences API (Week 2)

### Learning Objectives
- Build complete CRUD endpoints
- Implement role-based authorization
- Document APIs with Swagger
- Write unit tests

### Key Concepts to Learn
- CRUD operations (Create, Read, Update, Delete)
- Role-based access control (RBAC)
- OpenAPI/Swagger documentation
- Unit testing (xUnit, Moq)
- Input validation and error handling

### Tasks

- [ ] **Implement preference endpoints**
  - [ ] `GET /api/preferences` (fetch user preferences)
  - [ ] `PUT /api/preferences` (update preferences)
  - [ ] `GET /api/user/profile` (fetch user profile)
  - **What you learn:** Protected endpoints, token claims extraction
  - **Why it matters:** User security, data isolation

- [ ] **Add role-based authorization**
  - [ ] Add `role` column to users table
  - [ ] Create `[Authorize(Roles = "Admin")]` attribute
  - [ ] Apply to admin-only endpoints
  - **What you learn:** Authorization patterns, permission models
  - **Why it matters:** Security, access control

- [ ] **Document with Swagger**
  - [ ] Install Swashbuckle.AspNetCore
  - [ ] Add XML comments to endpoints
  - [ ] Add example responses
  - [ ] Access Swagger UI at `/swagger/ui`
  - **What you learn:** API documentation standards, OpenAPI spec
  - **Why it matters:** Team collaboration, client integration

- [ ] **Write unit tests**
  - [ ] Test valid login (expect 200 + token)
  - [ ] Test invalid password (expect 401)
  - [ ] Test unauthorized access (expect 401)
  - [ ] Target > 70% code coverage
  - **What you learn:** Unit testing, mocking, test-driven development
  - **Why it matters:** Code quality, regression prevention

### Deliverable
User management API complete, documented, tested

### Learning Checkpoint
- Explain RBAC and how to implement it?
- Write complete unit test with Arrange-Act-Assert?
- Document API endpoint with Swagger?

---

## Phase 4: Notification Queuing with Redpanda (Week 2-3)

### Learning Objectives
- Understand message queue architecture
- Learn Kafka/Redpanda concepts
- Implement asynchronous notification queuing
- Handle rate limiting

### Key Concepts to Learn
- Event-driven architecture patterns
- Message queues vs synchronous calls
- Kafka/Redpanda: brokers, topics, partitions
- Producer and consumer patterns
- Message ordering and partitioning
- Rate limiting strategies
- Idempotence concepts

### Resources to Study
- Redpanda Documentation: https://docs.redpanda.com/
- Kafka Concepts: https://kafka.apache.org/intro
- Event-Driven Architecture: https://www.martinfowler.com/articles/201701-event-driven.html

### Tasks

- [ ] **Set up Redpanda**
  - [ ] Add Redpanda broker to docker-compose.yml
  - [ ] Create topics: `notifications`, `notifications-dlq`
  - [ ] Set partitions to 3 for parallelism
  - **What you learn:** Message broker architecture, topic design
  - **Why it matters:** Scalability, reliability

- [ ] **Implement notification API endpoint**
  - [ ] `POST /api/events/{eventType}` - accept event
  - [ ] Validate event (required fields, data types)
  - [ ] Check rate limiting (10 req/min per user)
  - [ ] Save to database with status `QUEUED`
  - [ ] Publish to Redpanda topic
  - [ ] Return 202 Accepted (async)
  - **What you learn:** Async patterns, rate limiting, status codes
  - **Why it matters:** API design, resource protection

- [ ] **Implement notification history endpoint**
  - [ ] `GET /api/notifications` - fetch user notifications
  - [ ] Support pagination, filtering, sorting
  - **What you learn:** Pagination, filtering, query optimization
  - **Why it matters:** Performance with large datasets

### Deliverable
Event ingestion API with queue integration

### Learning Checkpoint
- Benefits of async over synchronous?
- Design message format for notification event?
- What are Kafka partitions and why do they matter?

---

## Phase 5: Python Worker Service (Week 3)

### Learning Objectives
- Learn Python async programming
- Build Kafka consumer for message processing
- Implement template rendering and email sending
- Implement retry logic and error handling

### Key Concepts to Learn
- Python async programming (asyncio, threading)
- Consumer groups and offset management
- Template rendering (Jinja2)
- SMTP and email protocols
- Exponential backoff and retry strategies
- Dead-letter queue patterns
- Structured logging

### Tasks

- [ ] **Create Python worker**
  - [ ] Initialize venv and create requirements.txt
  - [ ] Create Redpanda consumer (consumer group: `notification-workers`)
  - **What you learn:** Python setup, dependency management
  - **Why it matters:** Environment isolation, reproducibility

- [ ] **Implement email processing**
  - [ ] Load templates from database
  - [ ] Render using Jinja2: `template.render(variables)`
  - [ ] Mock email sending (MVP) - later connect to SMTP
  - **What you learn:** Template engines, variable substitution
  - **Why it matters:** Flexibility, personalization

- [ ] **Implement status tracking and retries**
  - [ ] Update `notification_history` status to `SENT`/`FAILED`
  - [ ] Implement retry with exponential backoff (up to 3 times)
  - [ ] Move to DLQ after 3 failures
  - **What you learn:** Resilience patterns, failure handling
  - **Why it matters:** Reliability, recovery

- [ ] **Add monitoring**
  - [ ] Emit Prometheus metrics (counters for sent/failed)
  - [ ] Add structured JSON logging to stdout
  - **What you learn:** Metrics types, structured logging
  - **Why it matters:** Monitoring, debugging

### Deliverable
Working worker that consumes from queue and processes notifications

### Learning Checkpoint
- Explain consumer group pattern?
- Manual vs auto-commit in Kafka?
- Implement exponential backoff?

---

## Phase 6: React Frontend - User Dashboard (Week 3-4)

### Learning Objectives
- Build interactive React UIs with TypeScript
- Manage state and side effects with hooks
- Implement authentication and protected routes
- Make API calls with axios

### Key Concepts to Learn
- React hooks (useState, useEffect, useContext)
- React Router for navigation
- Authentication flow (JWT storage, redirects)
- Axios HTTP client
- Form handling and validation
- Component composition
- CSS frameworks (Tailwind, Material-UI)

### Resources to Study
- React Official Docs: https://react.dev/
- React Router: https://reactrouter.com/
- Axios Documentation: https://axios-http.com/

### Tasks

- [ ] **Set up React project**
  - [ ] Create with TypeScript template
  - [ ] Install: axios, react-router-dom, tailwindcss
  - [ ] Configure Tailwind CSS
  - **What you learn:** React project setup, TypeScript basics
  - **Why it matters:** Type safety, tooling

- [ ] **Implement authentication**
  - [ ] Create LoginPage and RegisterPage components
  - [ ] Store JWT in localStorage
  - [ ] Create AuthContext for global auth state
  - [ ] Create ProtectedRoute wrapper
  - **What you learn:** Forms, localStorage, Context API, routing
  - **Why it matters:** Authentication patterns, state management

- [ ] **Build user dashboard**
  - [ ] Notification history table (paginated, sortable)
  - [ ] Preferences toggle (enable/disable notifications)
  - [ ] Profile view/edit
  - [ ] Test notification button
  - **What you learn:** Tables, forms, API integration
  - **Why it matters:** User interface, data presentation

- [ ] **Implement polling and feedback**
  - [ ] Poll notifications every 5 seconds
  - [ ] Show loading and error states
  - [ ] Display success/error messages (toast)
  - **What you learn:** useEffect, intervals, UX patterns
  - **Why it matters:** Real-time updates, user experience

### Deliverable
Working React UI for users to manage notifications

### Learning Checkpoint
- Explain React hooks and when to use them?
- How to protect routes in React?
- Build form that makes API calls?

---

## Phase 7: Admin Dashboard & Metrics (Week 4)

### Learning Objectives
- Build admin-only dashboards
- Learn Prometheus metrics concepts
- Configure Grafana for monitoring
- Implement real-time system health monitoring

### Key Concepts to Learn
- Prometheus metrics types (counter, gauge, histogram)
- Time-series data concepts
- Grafana dashboard design
- PromQL (Prometheus Query Language)
- Data visualization best practices

### Tasks

- [ ] **Create admin dashboard (React)**
  - [ ] Admin-only route protection
  - [ ] Display key metrics (sent, failed, latency)
  - [ ] Recent failures table with search
  - [ ] Charts (line, pie) using Chart.js or Recharts
  - **What you learn:** Role-based routing, charts, data formatting
  - **Why it matters:** System visibility, troubleshooting

- [ ] **Add Prometheus metrics**
  - [ ] .NET API: Install `prometheus-net`
  - [ ] Create counters: `notifications_sent_total`, `notifications_failed_total`
  - [ ] Create gauge: `queue_depth`
  - [ ] Create histogram: `notification_processing_duration_ms`
  - [ ] Expose `/metrics` endpoint (public, no auth)
  - **What you learn:** Metrics instrumentation, naming conventions
  - **Why it matters:** Monitoring infrastructure

- [ ] **Set up Prometheus and Grafana**
  - [ ] Add to docker-compose.yml
  - [ ] Configure Prometheus scrape targets
  - [ ] Add Prometheus as Grafana data source
  - [ ] Create dashboard with 4 panels:
    - [ ] Notifications sent per minute (line)
    - [ ] Error rate (%) (gauge)
    - [ ] Queue depth (line)
    - [ ] API response time p95 (line)
  - **What you learn:** Prometheus config, PromQL queries, dashboard creation
  - **Why it matters:** System monitoring, alerting foundation

### Deliverable
Admin dashboard + monitoring stack working

### Learning Checkpoint
- Write PromQL query for 99th percentile?
- Difference between counter and gauge?
- Create Grafana dashboard from scratch?

---

## Phase 8: Docker & Docker Compose (Week 4)

### Learning Objectives
- Build Docker images for each service
- Master Docker Compose for local orchestration
- Understand multi-stage builds
- Learn container best practices

### Key Concepts to Learn
- Dockerfile syntax and best practices
- Image layers and caching
- Multi-stage builds for optimization
- Networks and environment variables
- Health checks and startup order

### Tasks

- [ ] **Create Dockerfiles**
  - [ ] .NET API: Multi-stage (build + runtime)
  - [ ] Python worker: Slim base image
  - [ ] React: Multi-stage (build + nginx)
  - **What you learn:** Multi-stage builds, image optimization
  - **Why it matters:** Image size, build speed

- [ ] **Create `.dockerignore` files**
  - [ ] Exclude: node_modules, __pycache__, bin/, obj/, .git
  - **What you learn:** Build context optimization
  - **Why it matters:** Build speed, image size

- [ ] **Complete docker-compose.yml**
  - [ ] 8 services: api, worker, frontend, postgres, redis, redpanda, prometheus, grafana
  - [ ] Networks for inter-service communication
  - [ ] Health checks on critical services
  - [ ] Volumes for persistence
  - [ ] Startup order (depends_on)
  - **What you learn:** Compose orchestration, networking, health checks
  - **Why it matters:** Reproducible local development

- [ ] **Test full stack**
  - [ ] Run: `docker-compose up`
  - [ ] Verify all services healthy
  - [ ] Check logs: `docker-compose logs -f`
  - [ ] Test APIs: `curl http://localhost:5000/api/health`
  - [ ] Access React: http://localhost:3000
  - [ ] Access Grafana: http://localhost:3001
  - **What you learn:** Docker debugging, service verification
  - **Why it matters:** Development workflow validation

### Deliverable
Full stack runs with one `docker-compose up` command

### Learning Checkpoint
- Explain multi-stage Docker builds?
- Write docker-compose.yml from scratch?
- What are Docker networks and how do services communicate?

---

## Phase 9: Integration Testing & Documentation (Week 4-5)

### Learning Objectives
- Write end-to-end integration tests
- Master technical documentation
- Learn API documentation standards
- Create comprehensive guides

### Tasks

- [ ] **Write e2e test script**
  - [ ] Register user → Login → Send notification → Verify in history
  - [ ] Use curl or Postman Collection
  - [ ] Assert each step succeeds
  - **What you learn:** E2E testing, scenario validation
  - **Why it matters:** Quality assurance

- [ ] **Update README**
  - [ ] Overview, architecture diagram, quick start
  - [ ] Tech stack table, project structure
  - [ ] Development guide, deployment guide
  - [ ] Contributing guidelines
  - **What you learn:** Technical writing, documentation
  - **Why it matters:** Onboarding, knowledge transfer

- [ ] **Create API documentation**
  - [ ] Document each endpoint (method, path, auth, example request/response)
  - [ ] Include error responses (400, 401, 403, 404, 500)
  - [ ] Export Swagger/OpenAPI spec
  - **What you learn:** API documentation standards
  - **Why it matters:** Client integration, API usability

- [ ] **Create database schema documentation**
  - [ ] Include ERD diagram
  - [ ] Document each table (purpose, columns, relationships)
  - [ ] Explain migrations
  - **What you learn:** Database documentation, ERD creation
  - **Why it matters:** Understanding data model

- [ ] **Write deployment guide**
  - [ ] Local development setup
  - [ ] Cloud deployment (GCP, AWS, or Azure)
  - [ ] Environment variables for production
  - [ ] Monitoring setup in cloud
  - **What you learn:** Cloud deployment, infrastructure
  - **Why it matters:** Production readiness

- [ ] **Write developer guide**
  - [ ] How to add new notification type
  - [ ] How to extend worker
  - [ ] How to add new API endpoints
  - [ ] Code style, testing, debugging
  - **What you learn:** Knowledge transfer, best practices
  - **Why it matters:** Team productivity

- [ ] **Achieve > 70% test coverage**
  - [ ] .NET: Run with coverage reporting
  - [ ] Python: pytest --cov
  - [ ] Add tests for critical logic
  - **What you learn:** Test coverage measurement
  - **Why it matters:** Code quality

### Deliverable
Complete, tested, documented MVP

### Learning Checkpoint
- Write integration test that validates system?
- Document API endpoint completely?
- Difference between unit and integration tests?

---

## Phase 10: Final Testing & Demo Preparation (Week 5)

### Learning Objectives
- Validate entire system end-to-end
- Prepare demonstration
- Perform load testing basics
- Create deployment-ready code

### Tasks

- [ ] **Full e2e test on fresh docker-compose**
  - [ ] Remove all containers/volumes
  - [ ] Fresh start: `docker-compose up`
  - [ ] Run e2e test script
  - [ ] Verify all steps pass
  - [ ] Check Grafana metrics
  - **What you learn:** System validation, reproducibility
  - **Why it matters:** Confidence in system

- [ ] **Verify APIs via Postman**
  - [ ] Import Postman collection
  - [ ] Test each endpoint
  - [ ] Test error cases (401, 404, 429)
  - [ ] Export test results
  - **What you learn:** API testing
  - **Why it matters:** Quality assurance

- [ ] **Create demo script**
  - [ ] Architecture overview (2 min)
  - [ ] Docker Compose explanation (2 min)
  - [ ] User registration & login (1 min)
  - [ ] Send notification via Postman (1 min)
  - [ ] View in history (1 min)
  - [ ] Admin dashboard & metrics (2 min)
  - [ ] Grafana monitoring (2 min)
  - [ ] Code walkthrough (3 min)
  - **What you learn:** Presentation skills, system knowledge
  - **Why it matters:** Communication

- [ ] **Load test**
  - [ ] Send 100 concurrent notifications
  - [ ] Measure throughput, latency (p95, p99)
  - [ ] Verify no message loss
  - [ ] All end up in database
  - **What you learn:** Performance testing, bottleneck identification
  - **Why it matters:** Scalability validation

- [ ] **Test error scenarios**
  - [ ] Database down → system recovers
  - [ ] Email provider fails → worker retries
  - [ ] Rate limit exceeded → 429 response
  - [ ] Malformed event → 400 response
  - [ ] Missing auth → 401 response
  - [ ] Verify resilience
  - **What you learn:** Resilience testing, failure modes
  - **Why it matters:** Production reliability

- [ ] **Clean repository**
  - [ ] Remove build artifacts
  - [ ] Remove test data
  - [ ] Verify .gitignore complete
  - [ ] Remove hardcoded secrets
  - [ ] No large files in git
  - **What you learn:** Repository hygiene, security
  - **Why it matters:** Code quality

- [ ] **Create summary document**
  - [ ] What was built
  - [ ] Learning outcomes per phase
  - [ ] Technologies learned
  - [ ] Architecture decisions
  - [ ] Future enhancements
  - [ ] Challenges & solutions
  - [ ] Key insights
  - **What you learn:** Reflection, documentation
  - **Why it matters:** Portfolio material, interview talking points

### Deliverable
Production-ready MVP, ready for demo/interview

### Learning Checkpoint
- Explain every component and why it exists?
- Troubleshoot issues under pressure?
- Demo system and explain architectural decisions?

---

## Summary: Learning by Week

| Week | Phases | Focus Area | Key Skills |
|------|--------|-----------|-----------|
| Week 1 | 1-2 | Foundation | Git, Docker, Databases, APIs, Auth |
| Week 2 | 3-4 | Backend | CRUD, Testing, Queues, Event-Driven |
| Week 3 | 5-6 | Full-Stack | Python Workers, React, Frontend |
| Week 4 | 7-8 | DevOps & Monitoring | Prometheus, Grafana, Containerization |
| Week 5 | 9-10 | Quality & Demo | Testing, Documentation, Presentation |

---

## Technology Learning Roadmap

| Technology | Key Concepts | Time | Resources |
|------------|--------------|------|-----------|
| Git | Branching, workflows, merging | 2-3h | GitHub Docs |
| Docker | Images, containers, layers | 4-6h | Docker Docs, TechWorldWithNana |
| .NET Core | C#, ASP.NET, DI, EF Core | 10-15h | Microsoft Docs |
| PostgreSQL | SQL, schema design, normalization | 5-8h | PostgreSQL Docs |
| REST APIs | HTTP, status codes, design | 3-5h | RESTful API Docs |
| JWT/OAuth2 | Token auth, flows, security | 3-4h | JWT.io, Auth0 |
| React | Components, hooks, routing | 8-12h | React Docs |
| TypeScript | Type safety, interfaces | 4-6h | TypeScript Handbook |
| Kafka/Redpanda | Topics, partitions, consumers | 6-8h | Confluent Kafka, Redpanda Docs |
| Python | Async, decorators, packages | 5-7h | Real Python |
| Prometheus | Metrics, PromQL, instrumentation | 4-5h | Prometheus Docs |
| Grafana | Dashboards, queries, visualization | 3-4h | Grafana Docs |
| **Total** | | **60-100h** | |

---

## Success Criteria

Your MVP is complete when you can:

✅ Register a user and receive a welcome email notification  
✅ Log in and send a custom notification via the UI  
✅ See the notification appear in history within 5 seconds  
✅ Toggle preferences and verify notifications respect the setting  
✅ View metrics in Grafana showing successful delivery  
✅ Restart all services with one Docker command  
✅ Explain every component of the architecture  
✅ Troubleshoot and fix issues under time pressure  
✅ Demo the system to a team or interviewer  

---

## Next Steps After MVP (Phase 2+)

1. **Multiple Channels**: SMS, Push, In-App, Slack, Teams
2. **MongoDB Analytics**: Large-scale analytics data storage
3. **ELK Stack**: Elasticsearch, Logstash, Kibana for centralized logging
4. **Kubernetes**: Production deployment, auto-scaling, self-healing
5. **CI/CD Pipeline**: Concourse or GitHub Actions for automated deployment
6. **GraphQL API**: Add GraphQL alongside REST
7. **gRPC**: Inter-service communication
8. **AI Features**: Send-time optimization, content personalization
9. **Advanced Monitoring**: Distributed tracing, custom alerts
10. **Multi-tenancy**: Support multiple organizations

---

## Document History

| Version | Date | Changes |
|---------|------|---------|
| 2.0 | 2025-12-22 | Added integrated learning objectives, resources, and concepts to each phase |
| 1.0 | 2025-12-22 | Initial MVP requirements document |

---

**Status:** Ready to Use  
**Last Updated:** December 22, 2025  
**Next Review:** After Phase 5 completion
