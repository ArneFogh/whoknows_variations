# Prioriteret Liste over Problemer i Kodebasen

1. **SQL-injektionssårbarheder (Kritisk)**
   - Flere tilfælde af usaniteret brugerinput, der indsættes direkte i SQL-forespørgsler.
   - Eksempel: 
     ```python
     query_db("SELECT * FROM users WHERE username = '%s'" % request.form['username'])
     ```

2. **Svag adgangskodehashing (Kritisk)**
   - Brug af MD5 til adgangskodehashing, hvilket anses for at være kryptografisk usikkert.

3. **Forældede afhængigheder (Høj)**
   - Brug af meget gamle versioner af Python (2.7) og Flask (0.5), som ikke længere understøttes og kan have kendte sårbarheder.
   - Berørte filer: requirements.txt, Makefile

4. **Cross-Site Scripting (XSS) sårbarheder (Høj)**
   - Potentiale for XSS-angreb på grund af uescapet brugerinput, der gengives i skabeloner.
   - Berørte filer: search.html, about.html

5. **Usikker sessionshåndtering (Høj)**
   - Brug af en hardcodet hemmelig nøgle til sessionshåndtering.
   - Eksempel:
     ```python
     SECRET_KEY = 'development key'
     ```

6. **Mangel på inputvalidering (Medium)**
   - Utilstrækkelig inputvalidering for brugerregistrering og login.
