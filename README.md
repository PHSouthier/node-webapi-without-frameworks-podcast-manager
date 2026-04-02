# Podcast Manager API

API REST para gerenciamento e listagem de episódios de podcasts, construída com Node.js puro e TypeScript — sem frameworks externos.

## Tecnologias

- **Node.js** — servidor HTTP nativo (`http` module)
- **TypeScript** — tipagem estática
- **tsx** — execução de TypeScript em desenvolvimento
- **tsup** — build para produção

## Instalação

```bash
npm install
```

Configure um arquivo `.env` na raiz do projeto:

```env
PORT=3333
```

## Scripts

| Comando | Descrição |
|---|---|
| `npm run start:dev` | Inicia em modo desenvolvimento |
| `npm run start:watch` | Inicia com hot reload |
| `npm run dist` | Gera build de produção |
| `npm run start:dist` | Gera build e inicia em produção |

## Endpoints

### `GET /api/list`

Retorna todos os episódios cadastrados.

**Resposta:**
```json
[
  {
    "podcastName": "flow",
    "episode": "CBUM - Flow #319",
    "videoId": "pQSuQmUfS30",
    "categories": ["saúde", "esporte", "bodybuilder"]
  }
]
```

---

### `GET /api/podcasts?podcastName={nome}`

Filtra episódios pelo nome do podcast.

**Exemplo:**
```
GET /api/podcasts?podcastName=flow
```

**Resposta:**
```json
[
  {
    "podcastName": "flow",
    "episode": "CBUM - Flow #319",
    "videoId": "pQSuQmUfS30",
    "categories": ["saúde", "esporte", "bodybuilder"]
  },
  {
    "podcastName": "flow",
    "episode": "RUBENS BARRICHELLO - Flow #339",
    "videoId": "4KDGTdiOV4I",
    "categories": ["esporte", "corrida"]
  }
]
```
