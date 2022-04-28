# Servian Technical Challenge

This is the Servian Tech challenge. We use this challenge to help measure a candidate's technical capabilities and fit for working at Servian.

The scope of this challenge is to deploy a simple GTD application backed by a PostgreSQL database into a cloud environment of your choice (AWS, Azure, or GCP).

## Assessment Requirements

The solution you come up with should be able to be deployed into an empty cloud environment with no existing infrastructure in place.

There _should not_ be a requirement for Servian to access your cloud environment to deploy this solution.

Candidates should demonstrate good git practices and work flows i.e. Regular commits.

There is no time limit on the solution, however we recommend you spend no more than 2 hours.

Documentation should be included in an README.md file as part of the solution, which highlights the following:

- How to provision the solution and deploy the application.
- High level architecture (This can be a diagram or a simple description of the architecture, be ready to talk about it in your interview).
- High level description of improvements (if any).

## Submission

To submit your solution, please provide the URL to your repo with all of your supporting artefacts to the Servian Talent Aquision team member who you have been engaged with. You can simply reply to the email that they sent you with initial instructions and links to this repo.

## Assessment Grading Criteria

### Key Criteria

Candidates should take care to ensure that their submission meets the following criteria:

- Must be able to start from a cloned git repo.
- Must document any prerequisites clearly.
- Must be contained within a GitHub repository.
- Must deploy via an automated process.
- Must deploy infrastructure using code.

### Things are we looking for

We will be looking at the following areas for your solution:

#### Coding Style

- Readability & Clarity of code
- Comments (Where relevant)
- Consistency of Coding

#### Security

- Network segmentation (Default VPC/VNETs are acceptable however be prepared to dive into how you would segment your network should you have created a VPC).
- Secret management.
- Platform security features.

#### Simplicity

- No superfluous dependencies.
- Do not overengineer the solution (If you have additional ideas beyond the minimum required to satisfy the key requirements, document them down in your README.md and they can be discussed in the technical interview).

#### Resiliency

- Highly available frontend
- Auto Scaling solution is desired (If you do not implement auto scaling, be prepared to talk about how you would architect this).
- Highly available Database.

#### CICD

You can either code or explain how the following could be accomplished:

- CI/CD pipeline for deployment
- Any tests to check for success or failure of the pipeline.

## Application Details

The [TechChallengeApp](https://github.com/servian/TechChallengeApp) is a single page application designed to be run inside a container with a PostgreSQL database to store data.

It is completely self contained, and should not require any additional dependencies to run.

`docker pull servian/techchallengeapp:latest`

## Configuration

The [application can be configured](https://github.com/servian/TechChallengeApp/blob/master/doc/config.md) with a file `conf.toml` or environment variables.

## Start server

`./TechChallengeApp updatedb` to create a database and seed it with test data

`./TechChallengeApp serve` will start serving requests

## Endpoints

`/` - root endpoint that will load the SPA

`/api/tasks/` - api endpoint to create, read, update, and delete tasks

`/healthcheck/` - Used to validate the health of the application
