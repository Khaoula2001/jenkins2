# TP 32 : Mise en place d’un pipeline CI/CD microservices avec Jenkins, GitHub, SonarQube, Docker Compose et Ngrok

---

## Architecture

![Structure du Projet](./screens/step01_intellij_project_structure.png)

### Services

| Service | Port | Technologie | Rôle |
|---------|------|-------------|------|
| **SERVICE-CAR** | 8089 | Spring Boot 3.2.0 (Java 21) | Gestion des voitures |
| **SERVICE-CLIENT** | 8088 | Spring Boot 3.2.0 (Java 17) | Gestion des clients |
| **Gateway** | 8888 | Spring Cloud Gateway | Routage API |
| **Eureka** | 8761 | Netflix Eureka | Service Discovery |
| **MySQL** | 3306 | MySQL | Base de données |
| **Consul** | 8500 | Consul 1.15.4 | Configuration |
| **phpMyAdmin** | 8081 | phpMyAdmin | Admin DB |

---

## 🚀 Pipeline Jenkins & SonarQube

### Configuration

![Scanner SonarQube](./screens/step02_jenkins_sonarqube_scanner_installation.png)

![Serveur SonarQube](./screens/step03_jenkins_sonarqube_server_configuration.png)

### Tokens par Service

![Token Car Service](./screens/step04_sonarqube_car_service_token.png)

![Token Client Service](./screens/step05_sonarqube_client_service_token.png)

### Dashboard Initial

![Dashboard SonarQube Initial](./screens/step06_sonarqube_initial_dashboard.png)

### Exécution Pipeline

![Pipeline Jenkins](./screens/step07_jenkins_pipeline_execution.png)

![Quality Gate](./screens/step09_sonarqube_quality_gate_passed.png)

**Stages :** Checkout → Build Maven → SonarQube Analysis → Quality Gate → Docker Build → Deploy

![Build Success](./screens/step08_jenkins_build_success_logs.png)

---

## Analyse Qualité

### Analyse Détaillée

![Analyse SonarQube](./screens/step10_sonarqube_detailed_analysis.png)

**Métriques validées :** Bugs ✅ | Vulnerabilities ✅ | Code Smells ✅ | Coverage ✅ | Duplications ✅

---

## Services en Production

![Eureka](./screens/step11_eureka_service_discovery.png)

**Services enregistrés :** GATEWAY-SERVICE ✅ | SERVICE-CLIENT ✅ | SERVICE-CAR ✅

![Routes Gateway](./screens/step12_gateway_routing_configuration.png)

### Health Checks

![Health Status](./screens/step13_services_health_status.png)

