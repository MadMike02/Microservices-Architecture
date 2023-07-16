# Mircroservices architecture

## Introduction
### Agenda
- History of microservices
- Problem with Monolith & SOA
- Microservices Architecture
- Problems Solved by Microservices
- Designing Microservices Architecture
- Deploying Microservices
- Testing Mircroservices
- Service Mesh
- Loggin & Monitoring
- When not to use microservices
- Mircroservices and the organization
- Anti-patterns and common mistakes
- Breaking Monolith to Mircroservices
- Case study
- Conclusion

## History of microservices
- It is result of problems with Monolith & SOA architecture

### Monolith
- The original architecture
- All software components are executed in a single process.
- everything is using same thread same resources.
- No distribution of any kind
- strong coupling between all classes
- Usually implemented as silo i.e. no api no sharing of functionality to other apps.
- Monolith apps are running in their stand alone environment.
### Pros
- Easier to design
- Performance

### SOA (service oriented architecture)
- First coined in 1998
- Apps are services exposing functionality to the outside world.
- Services expose metadata to declare their functionality
- Usually implemented using SOAP & WSDL.
- Usually implemented with ESB(Enterprise service bus).
- ESB is a product that used to mediate between services and client by services itself. Use authentication, routing etc.
- example -- two apps using SOA architecture must have some API in both sides to communicate with each other. and the communication will happen through ESB that way the listener will not know all services in sender it will only know how to link with ESB and that one service needed.
### pros
- Sharing Data & Functionality
- Polygot Between Services. (allows to remove dependecy with platform i.e. one api can call another api even if there platform is different.)

### Problems in Monolith & SOA
- `Single Technology Platform`
    - With monolith, all the components must be developed using the same development platform.
    - Not always the best for the task
    - Can't use specific platform for specific features.
    - Future upgrade is a platform- need to upgrade the whole app
- `Inflexible Deployment`
    - With monolith, new deployment is always for the whole app.
    - No way to deply only part of the app
    - Even when updating only one component- the whole codebase is deployed.
    - Forces rigorous testing for the every deployment
    - Forces long development cycles.
- `Inefficient Compute Resources`
    - With monolith, Compute resources (CPU and RAM) are divided across all components.
    - If a specific component needs more resources - no way to do that
    - Very inefficient
- `Large and Complex`
    - with monolith, the codebase is large and complex
    - Every little change can affect other components.
    - Testing not always detects all the bugs
    - Very difficult to maintain
    - Might make the system obsolete.
- `Complicated and Expensive ESB`
    - With SOA, the ESB is one of the main components.
    - Can quickly become bloated and expensive.
    - Tries to do everything (routing, validation, authentication etc)
    - Very difficult to maintain
- `Lack of Tooling`
    - for SOA to be effective, short development cycles were needed
    - Allow for quick testing and deployment
    - No tooling existed to support this
    - No time saving was achieved - setup & maintaining is time consuming

### Microservices Architecutre