# Payment API Study

Projeto base para estudos de APIs de pagamento usando Spring Boot e Java 21.

## Tecnologias

- Java 21
- Spring Boot 3.5
- Spring Web
- Bean Validation
- Spring Boot Actuator
- Maven

## Executar

```bash
mvn spring-boot:run
```

O projeto requer JDK 21 e Maven instalados.

Aplicação: `http://localhost:8080`

Health check: `GET http://localhost:8080/actuator/health`

## Estrutura inicial

```text
src/main/java/com/example/paymentapi
├── PaymentApiApplication.java
├── api
│   ├── PaymentController.java
│   └── dto
├── domain
│   ├── Payment.java
│   ├── PaymentMethod.java
│   └── PaymentStatus.java
└── service
    ├── PaymentService.java
    └── StudyPaymentService.java
```

Os endpoints de pagamento retornam `501 Not Implemented` de propósito. A ideia é oferecer contratos e pontos de extensão para você implementar persistência, idempotência, autorização, antifraude, webhooks, conciliação e integração com um provedor.

## Endpoints base

- `POST /api/v1/payments`
- `GET /api/v1/payments/{paymentId}`

O contrato HTTP usa `BigDecimal` para valores monetários e validações básicas. Não use dados reais de cartão neste projeto de estudo.
