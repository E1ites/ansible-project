# Ansible Docker Deployment Project

Этот проект автоматически устанавливает Docker, скачивает приложение с GitHub и запускает его через `docker compose` на локальной машине с помощью Ansible.

---

## 📦 Требования

Перед началом убедитесь, что на вашей машине установлены:
- Ansible
---

## ⚙️ Установка Ansible

```bash
sudo apt update
sudo apt install -y ansible
````

Проверьте, что Ansible установлен:

```bash
ansible --version
```

---

## 🚀 Как запустить проект

1. Клонируйте этот репозиторий:

```bash
git clone https://github.com/E1ites/ansible-project
cd ansible-project
```

Убедитесь, что есть папки `roles`, файл `playbook.yml` и `inventory`.

2. Запустите плейбук:

```bash
ansible-playbook -i inventory/hosts playbook.yaml

```
3. Проверьте, запустились ли контейнеры: 

docker ps

Порты:
Приложение: http://ваш ip-aдрес:8000
Prometheus: http://ваш ip-aдрес:9090
Grafana: http://ваш ip-aдрес:3000
Nginx Exporter: http://ваш ip-aдрес:9113/metrics
Node Exporter: http://localhost:9100/metrics
cAdvisor: http://localhost:8080/metrics
---

## 🛠 Что делает плейбук

* Устанавливает Docker
* Устанавливает Git
* Клонирует проект из GitHub
* Запускает проект через `docker compose up -d --build`
---

