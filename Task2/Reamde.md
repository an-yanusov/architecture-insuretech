Как запускать:
1. Применяем deplpoyment: kubectl apply -f deployment.yaml
2. Применяем service: kubectl apply -f service.yaml
3. Применяем Horizontal Pod Autoscaler (HPA): kubectl apply -f hpa.yaml
4. Запускаем kubectl get pods, чтобы убедиться, что все контейнеры запущены.
5. Проверяем, что запущены deplpoyment, service и HPA.
- kubectl get deployment
- kubectl get service
- kubectl get hpa
6. Проверяем, что сервис доступен:
- minikube service scaletestapp-service --url 
Переходим по появившейся ссылке и проверяем, что сервис работает.
7. Открываем туннель: minikube tunnel и смотрим, что сервис доступен по внешнему IP-адресу c помощью команды kubectl get svc scaletestapp-service. Нагрузку будем проводить на EXTERNAL-IP по порту 8080
8. Запускаем приложение для создания нагрузки: 
- python3.12 -m venv venv
- source venv/bin/activate
- pip install locust
- locust 
- Выбираем настройки для теста и запускаем
9. Открываем minikube dashboard и проверяем, что все контейнеры работают, запускаются новые поды под нагрузкой и не падают