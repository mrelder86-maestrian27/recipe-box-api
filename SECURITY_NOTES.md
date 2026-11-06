# Security baseline – open recipe API

Date: 2026-11-06

- Anonymous `GET /recipes` returns `200 OK` and the recipe list.
- Anonymous `POST /recipes` with JSON body returns `201 Created` and stores the new recipe.
- Anonymous `DELETE /recipes/<id>` returns `204 No Content`; the recipe is gone on the next `GET`.

Notes:
- The API never asks for identity (no login, no token, no session).
- Success status codes show that the operation worked, **not** that it was authorized.
- Any requester who can reach the server can read, create, or delete recipes.