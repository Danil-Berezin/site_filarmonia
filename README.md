# 🎵 Event Booking System (Система бронирования билетов)

<p align="left">
  <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" />
  <img src="https://img.shields.io/badge/Vite-B73BFE?style=for-the-badge&logo=vite&logoColor=FFD62E" />
  <img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white" />
  <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" />
</p>

Полноценное веб-приложение для управления мероприятиями (на примере филармонии). Проект демонстрирует реализацию клиентской части на **React** с ролевой моделью доступа (RBAC), корзиной бронирования и панелью администратора.

В качестве бэкенда используется легковесный Node.js Mock-сервер для эмуляции реального API.

## ✨ Ключевые возможности

👤 **Для пользователей (User):**
- Просмотр актуальной афиши мероприятий.
- Система бронирования и покупки билетов (с сохранением состояния).
- Чтение новостной ленты.

🛡 **Для администраторов (Admin Dashboard):**
- Управление контентом (добавление/редактирование афиши и новостей).
- Просмотр статистики и отчетов по продажам.
- Ролевая модель авторизации (JWT-подобная логика через Mock API).

---

## 🛠 Архитектура проекта
- **Frontend:** React + Vite + Tailwind CSS.
- **Backend (Mock):** Node.js + Express (in-memory база данных, сброс при перезагрузке).
- **Email-эмуляция:** Логирование исходящих писем (покупки билетов) в локальный файл `sent_emails.log`.

---

## 🚀 Инструкция по локальному запуску

Для работы приложения необходимо запустить оба сервиса (Frontend и Mock Server) в разных терминалах.

### Требования
* Node.js (v16 или выше)
* npm

### 1. Запуск Backend (Mock Server)
В первом терминале перейдите в папку сервера, установите зависимости и запустите его:

cd frontend/mock-server
npm install
node server.js

Сервер API запустится по адресу: http://localhost:8080
2. Запуск Frontend (React)
Во втором терминале перейдите в папку фронтенда, установите зависимости и запустите сборку:
cd frontend
npm install
npm run dev
Приложение будет доступно по адресу: http://localhost:5173

🔐 Тестовые доступы
Для проверки ролевой модели используйте следующие учетные данные:
Роль	Логин	Пароль	Доступ
Администратор	admin	admin	Полный доступ (CMS, отчеты)
Пользователь	user	user	Бронирование, просмотр афиши
