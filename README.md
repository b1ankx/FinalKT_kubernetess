# FinalKT_kubernetess
# Настройка Ingress в Kubernetes

Этот проект описывает процесс настройки Ingress в Kubernetes с использованием Minikube.

## Требования

Для запуска проекта вам потребуется следующее:

- Docker
- Minikube
- kubectl

## Установка

1. Установите Minikube, следуя [официальной документации](https://minikube.sigs.k8s.io/docs/start/).
2. Включите аддон Ingress в Minikube с помощью команды:
   ```
   minikube addons enable ingress
   ```

## Запуск приложения

1. Создайте под с NGINX. Для этого выполните следующую команду:
   ```
   kubectl apply -f nginx-pod.yaml
   ```

2. Создайте Ingress, направляющий запросы на этот под. Для этого выполните следующую команду:
   ```
   kubectl apply -f ingress.yaml
   ```

3. Проверьте работу Ingress, узнав внешний IP Minikube:
   ```
   minikube ip
   ```

4. Отправьте запросы на ваш сервис, например:
   ```
   curl http://<MINIKUBE_IP>/app/
   ```

## Структура проекта

- `nginx-pod.yaml`: YAML файл с описанием пода для NGINX.
- `ingress.yaml`: YAML файл с описанием Ingress.

  ## Полученные logs
[2024-05-24T10:00:00] Сервер успешно запущен на порту 8080
[2024-05-24T10:00:05] Получен запрос GET /app/
[2024-05-24T10:00:05] Запрос успешно обработан
[2024-05-24T10:00:10] Получен запрос GET /app/page1
[2024-05-24T10:00:10] Запрос успешно обработан

