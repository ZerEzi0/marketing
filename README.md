# Прогнозирование покупок в интернет-магазине  
**Цель проекта:** предсказать вероятность покупки клиентом в течение **90 дней**  
**Метрика:** `roc_auc` → **0.6568** (CatBoost)  

---

## Задача  
Оптимизировать маркетинговые рассылки: выделить пользователей, **готовых купить** в ближайшее время.  

---

## Данные  
Файл | Описание

- `apparel-purchases.csv` - История покупок: `client_id`, `quantity`, `price`, `category_ids`, `date`, `message_id` 
- `apparel-messages.csv` - Рассылки: `bulk_campaign_id`, `event` (send, open, click, purchase), `channel` (email/sms), `created_at` |
- `apparel-target_binary.csv` - Целевой признак: `target` — покупка в следующие 90 дней |

> **Важно:** `category_ids` — вложенные категории в виде строки `['4', '28', '57']`. Нумерация **сквозная** по всем уровням.

---

## Технологии  
- **Python 3.12**  
- **pandas, numpy**  
- **phik, seaborn, matplotlib**  
- **scikit-learn** (Pipeline, GridSearchCV)  
- **LightGBM + CatBoost**  

---

## Запуск

```bash
# 1. Клонировать репозиторий
git clone https://github.com/ZerEzi0/marketing
cd marketing

# 2. Создать окружение
python -m venv venv
source venv/bin/activate  # Linux/Mac
# venv\Scripts\activate   # Windows

# 3. Установить зависимости
pip install -r requirements.txt

# 4. Запустить ноутбук
jupyter notebook marketing.ipynb