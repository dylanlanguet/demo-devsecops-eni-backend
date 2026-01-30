# Task Manager

## Installation & usage

### Backend

```bash
cd backend
python3 -m venv .venv
source .venv/bin/activate

pip install -r requirements.txt
uvicorn app.main:app --host 127.0.0.1 --port 8000
```

## Quelques commandes `curl`

### Créer une tâche
```bash
curl -s -X POST http://127.0.0.1:8000/tasks \
  -H "Content-Type: application/json" \
  -d '{"title":"Écrire tests API","description":"Ajouter des assertions sur /tasks"}' | jq
```

### Lister les tâches
```bash
curl -s http://127.0.0.1:8000/tasks | jq
```

### Mettre à jour une tâche
```bash
curl -s -X PUT http://127.0.0.1:8000/tasks/1 \
  -H "Content-Type: application/json" \
  -d '{"status":"DONE"}' | jq
```

### Supprimer une tâche
```bash
curl -i -X DELETE http://127.0.0.1:8000/tasks/1
```
