# Backend CRUD app built with Micronaut + Kotlin + MongoDB

Has 2 resources: Blogpost and Product.

## API endpoints for Blogpost:

### GET {URL}/blogpost -> returns list of ids

params:

- limit: Int?
- offset: Int?

### GET {URL}/blogpost/search -> returns list of blogposts

params:

- limit: Int?
- offset: Int?
- limit: Int?
- offset: Int?
- nameFilter: String?
- textFilter: String?
- categoryFilter: String?
- productFilter: String?

### GET {URL}/blogpost/{id} -> returns a blogpost

params:

- id: String

### POST {URL}/blogpost -> creates a blogpost and returns the created blogpost ID as string

params:

- blogpost: Blogpost

### PUT {URL}/blogpost -> returns the updated blogpost ID as string

params:

- id: String
- newName: String?
- newText: String?
- newCategory: Category?
- newProducts: List<Product>?

i broke them up so the user would be able to update with partial data,
also added in a comment an update function that expects an ID and a valid Blogpost type as params

### DELETE {URL}/blogpost/{id} -> deletes a blogpost

params:

- id: String

## API endpoints for Product are the same (at /product)

---

# Running

Use "./gradlew run" command to start server

I added the ${MONGODB_URI} param in the application.yml file for environment variables creation in piplines.

for simplicity i used this command to have it run locally:

./gradlew run --args="-mongodb.uri=mongodb://localhost:27017/"
