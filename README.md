# api-rest-contactos-1

@app.get("/")
async def root():
    return {"message": "Hello word"}

@app.get("/v1/contactos")
async def contactos():
    contactos = []

    try:
        with open("contactos.csv", newline="", encoding="utf-8") as csvfile:
            reader = csv.DictReader(csvfile)
            for row in reader:
                contactos.append({"nombre": row["nombre"], "email": row["email"]})
    except FileNotFoundError:
        return {"error": "No conozco ese archivo "}

    response = { "contactos": contactos}
    return response



    @app.get("/")
    def root()
    """"
  
