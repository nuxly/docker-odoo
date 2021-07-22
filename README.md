# docker-odoo
PostgreSQL container with Odoo demo databases.

#  **To use it:**
`docker run -p 5433:5432 -d -e POSTGRES_USER=odoo -e POSTGRES_PASSWORD=odoo -e POSTGRES_DB=postgres --volume=<PATH_TO_DIRECTORY>/data:/var/lib/postgresql/data --name bdd_demo postgres:9`

#  **Trouble you might face:**
- You may need to re-generate some filestore files if Odoo logs show “No such file or directory: u'/var/lib/odoo/filestore/odoo_demo/cd/cd8f9...”:
    1. Access to the database (for example with pgAdmin)
    2. Run this SQL query : `DELETE FROM ir_attachment WHERE url LIKE '/web/content/%';`
    3. Refresh the page
