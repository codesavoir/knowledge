# Jenkins Pipelines

> When and how to use Jenkins effectively in modern ecosystems.

## When Jenkins Still Fits
- Heavy custom agents / specialized build tools
- Self-hosted compliance constraints
- Complex legacy job orchestration

## Modern Pipeline (Declarative)
```groovy
pipeline {
  agent any
  options { timestamps(); ansiColor('xterm') }
  environment { APP_ENV = 'ci' }
  stages {
    stage('Checkout') { steps { checkout scm }}
    stage('Build') { steps { sh 'make build' }}
    stage('Test') { steps { sh 'make test' }}
    stage('Package') { steps { sh 'make package' }}
  }
  post {
    always { archiveArtifacts artifacts: 'dist/**'; cleanWs() }
    failure { mail to: 'dev-team@example.com', subject: 'Build Failed', body: env.BUILD_URL }
  }
}
```

## Hardening
- Run controllers & agents with least privilege
- Lock down script approval (avoid arbitrary Groovy)
- Use folder-level RBAC
- Regularly rotate credentials and API tokens

## Migration Pattern
1. Inventory jobs (export config.xml)
2. Classify: retire / migrate / keep
3. Create GitHub Actions equivalents
4. Parallel-run for confidence
5. Decommission plugins gradually

## Observability
- Pipeline stage timing
- Queue length / executor utilization
- Failure cause categorization

---
**Next:** Testing strategy alignment → [Testing Strategy](testing-strategy.md)
