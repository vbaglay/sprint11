### **Сводная таблица проблем, целей и решений**  

| №  | Проблема                          | Цель/План                                       | Решение (Архитектура 2.0)                                                                 | Приоритет  |  
|----|-----------------------------------|-------------------------------------------------|-------------------------------------------------------------------------------------------|------------|  
| 1  | Непродуктовый подход (узкое место)| Распределённая ответственность за данные        | Data Mesh: DDD-домены с ответственностью за Data Products                                  | **MUST**   |  
| 2  | Медленные изменения (Time-to-Market)| Снижение времени сбора до анализа              | Event-driven (Kafka) + Trino для real-time SQL                                             | **MUST**   |  
| 3  | Отсутствие сквозной аналитики     | Прозрачность происхождения данных              | DataHub: автоматический lineage и RBAC                                                    | **MUST**   |  
| 4  | Негибкие пайплайны                | Централизованная оркестрация                   | Airflow + dbt + интеграция с DataHub                                                      | **MUST**   |  
| 5  | Нет версионирования данных        | Rollback, time-travel, dev/prod среда          | Iceberg + Nessie (Git-like версионирование)                                               | **MUST**   |  
| 6  | Ограниченные возможности отчётов  | Self-service BI для аналитиков                 | Superset поверх Trino                                                                     | **SHOULD** |  
| 7  | Зависимость от Legacy DWH (MSSQL) | Миграция на современную платформу              | Поэтапный перенос в Iceberg через Airflow CDC                                             | **SHOULD** |  
| 8  | Отсутствие API         | Единая точка входа и аутентификация            | API Gateway (Kong) + Keycloak (OIDC/JWT)                                                  | **SHOULD** |  