Importare il DB allegato tramite phpMyAdmin ed eseguire le seguenti queries:

- Selezionare tutti gli uffici, ordinati per nazione
SELECT *
FROM offices
ORDER BY country;

- Selezionare tutti gli uffici, ordinati per nazione e per città
SELECT *
FROM offices
ORDER BY country, city;

- Selezionare tutti gli impiegati, ordinati per titolo e per nome
SELECT *
FROM employees
ORDER BY title, name;

- Contare quanti impiegati condividono lo stesso ufficio
SELECT office_id, COUNT(*) as number_employees
FROM employees
GROUP BY office_id
ORDER BY number_employees DESC;

- Contare quanti impiegati condividono la stessa estensione
SELECT extension, COUNT(*) as number_employees
FROM employees
GROUP BY extension
ORDER BY number_employees DESC;


- Selezionare tutti i prodotti con quantità inferiore a 500 pezzi
SELECT *
FROM products
WHERE qty < 500;

- Selezionare tutti i prodotti Ford
SELECT *
FROM products
WHERE name = 'Ford';


- Contare quanti prodotti Ford hanno quantità inferiore a 500 pezzi
SELECT COUNT(*) as numbers_products_ford
FROM products
WHERE name = 'Ford' AND qty < 500;

- Per ogni impiegato mostrare il suo diretto superiore (tip: usa un alias quando fai la join)


- Per ogni impiegato mostrare il numero di telefono completo (numero ufficio + estensione)
SELECT 
    CONCAT(name, ' ', lastname) AS name_lastname,
    CONCAT(office_id, ' ', extension) AS phone_number_complete
FROM employees;


- Selezionare i 10 ordini più recenti
SELECT *
FROM orders
ORDER BY date DESC
LIMIT 10;

- Per ogni cliente mostrare il numero di ordini che ha fatto (tip: attenzione al tipo di JOIN e al campo usato per il COUNT)


- Per ogni cliente mostrare la quantità di prodotti acquistati in ogni ordine, mostrando anche il nome del prodotto (tip: attenzione al tipo di JOIN)
    - Ordinare per quantità
    - Ordinare per nome o ID cliente


    
- Per ogni cliente mostrare il totale speso sulla piattaforma, il costo sostenuto per ogni prodotto ed il guadagno netto per la piattaforma (tip: la colonna MSRP indica il prezzo a cui è stato venduto il singolo prodotto)
