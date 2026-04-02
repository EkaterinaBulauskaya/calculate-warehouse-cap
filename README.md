# Example of warehouse optimization

[![CI (tests)](https://github.com/EkaterinaBulauskaya/warehouse-optimization/actions/workflows/warehouse-optimization-ci.yml/badge.svg)](https://github.com/EkaterinaBulauskaya/warehouse-optimization/actions/workflows/warehouse-optimization-ci.yml)

Репозиторий с двумя независимыми Python-проектами (данные и скрипты лежат в своих папках).

| Проект | Описание | Документация |
|--------|----------|--------------|
| [warehouse_cap](projects/warehouse_cap/) | Прогноз и расчёт **свободного места на складе** по дням (продажи, остатки, PO). | [README](projects/warehouse_cap/README.md) |
| [abc_xyz](projects/abc_xyz/) | **ABC/XYZ-анализ** ассортимента по SKU. | [README](projects/abc_xyz/README.md) |

## Общие зависимости

Оба проекта используют `pandas` и `scikit-learn`. Минимально для запуска скриптов:

```bash
python -m pip install pandas scikit-learn
```

Для запуска **тестов** из корня репозитория удобнее одна команда — в [`requirements-dev.txt`](requirements-dev.txt) перечислены `pytest`, `pandas` и `scikit-learn`:

```bash
python -m pip install -r requirements-dev.txt
```

## Структура репозитория

```text
projects/
  warehouse_cap/     # README, скрипт, notebook, in_*.csv, out_*.csv
  abc_xyz/           # README, скрипт, notebook, in_*.csv, out_*.csv
```

Подробности по входным/выходным файлам и командам запуска — в README соответствующей папки.

## Тесты

В корне репозитория заданы [`pytest.ini`](pytest.ini) (в т.ч. `pythonpath`) и [`requirements-dev.txt`](requirements-dev.txt). Установите зависимости для тестов ([Общие зависимости](#общие-зависимости)), затем из **корня** репозитория — запуск **всех** тестов:

```bash
python -m pytest -v
```

Только один проект:

```bash
python -m pytest projects/warehouse_cap/tests -v
python -m pytest projects/abc_xyz/tests -v
```
