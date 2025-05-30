| Категория          | Технология       | Статус   | Обоснование                                                                 |
|--------------------|------------------|----------|-----------------------------------------------------------------------------|
| **Методологии**    | Data Mesh        | ADOPT    | Решает проблему монолитного DWH через продуктовый подход                    |
|                    | Event-Driven     | ADOPT    | Основа интеграции между доменами (Kafka)                                    |
|                    | GitOps           | TRIAL    | Для управления конфигурациями платформы (Kubernetes + ArgoCD)               |
| **Инструменты**    | Apache Kafka     | ADOPT    | Центральная шина событий вместо Camel                                       |
|                    | Apache Iceberg   | ADOPT    | ACID-хранилище для аналитики                                               |
|                    | Trino            | ADOPT    | SQL-движок для кросс-доменных запросов                                      |
|                    | Nessie            | ASSESS    | Версионирование таблиц                                      |
|                    | DataHub          | TRIAL    | Каталог метаданных                                                          |
| **Платформы**      | AWS S3           | ADOPT    | Основное хранилище для Iceberg                                              |
|                    | Kubernetes       | TRIAL    | Оркестрация микросервисов (для доменных API)                                |
|                    | Snowflake        | ASSESS   | Альтернатива Iceberg                                                        |
| **Языки/Фреймворки** | Python (Airflow) | ADOPT    | Основной язык для ETL и ML                                                  |
|                    | Java/Golang      | ADOPT    | Для высоконагруженных сервисов (финтех, API)                                |
| **Инфраструктура** | Keycloak         | ADOPT    | Единая аутентификация/авторизация                                           |
|                    | Kong API Gateway | TRIAL    | Единая точка входа для доменных API                                         |
|                    | Power BI         | HOLD     | Постепенная миграция на Superset                                            |
|                    | MSSQL 2008       | HOLD     | Замена на Iceberg для аналитики |

**Роадмап**
Квартал 1:
ADOPT: Kafka, Iceberg, Trino, Data Mesh.
HOLD: Постепенная миграция с Power BI на Superset.

Квартал 2:
TRIAL: DataHub, Kong, Kubernetes.
ASSESS: Snowflake для нереляционных сценариев. Nessie - для Git-like Versioning данных.

Квартал 3-4:
Полный переход на Superset.
Вывод MSSQL, Power BI из аналитики.