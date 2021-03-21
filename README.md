# Next Level Week 3 Backend

## migrations

creating migrations
```
yarn typeorm migration:create -n create_table
```

running migrations
```
yarn typeorm migration:run
```

reverting migrations
```
yarn typeorm migration:revert
```

## Requests

### Orphanages

<details>
  <summary>Index</summary>

  curl
  ```
  curl -H 'content-type: application/json' -X "GET" 'http://localhost:3333/orphanages' | jq
  ```

  status `200 OK`

  response
  ```
  [
    {
      "id": 1,
      "name": "Lar das meninas",
      "latitude": -27.2104,
      "longitude": -49.6291,    "about": "Sobre o orfanato",
      "instructions": "Venha visitar",
      "opening_hours": "Das 8h ate 18h",
      "open_on_weekends": true
    },
    {
      "id": 2,
      "name": "Lar das meninas",
      "latitude": -27.2104,
      "longitude": -49.6291,
      "about": "Sobre o orfanato",
      "instructions": "Venha visitar",
      "opening_hours": "Das 8h ate 18h",
      "open_on_weekends": true
    }
  ]
  ```
</details>

<details>
  <summary>Create</summary>

  curl
  ```
  curl -H 'content-type: application/json' -d '{ "name": "Lar das meninas", "latitude": -27.2104, "longitude": -49.6291, "about": "Sobre o orfanato", "instructions": "Venha visitar", "opening_hours": "Das 8h ate 18h", "open_on_weekends": true }'  -X "POST" 'http://
localhost:3333/orphanages' | jq
```

  status `201 Created`

  reponse
  ```
  {
    "name": "Lar das meninas",
    "latitude": -27.2104,
    "longitude": -49.6291,
    "about": "Sobre o orfanato",
    "instructions": "Venha visitar",
    "opening_hours": "Das 8h ate 18h",
    "open_on_weekends": true,
    "id": 2
  }
  ```
</details>

<details>
  <summary>Show</summary>

  curl
  ```
   curl -H 'content-type: application/json' -X "GET" 'http://localhost:3333/orphanages/1' | jq
  ```

  status `200 OK`

  response
  ```
  {
    "id": 1,
    "name": "Lar das meninas",
    "latitude": -27.2104,
    "longitude": -49.6291,
    "about": "Sobre o orfanato",
    "instructions": "Venha visitar",
    "opening_hours": "Das 8h ate 18h",
    "open_on_weekends": true
  }
  ```
</details>
