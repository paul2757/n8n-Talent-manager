*Mi a dat Gemini ceva si l am modificat*

Conceptual ar arata asa:

    Modulul 1: Receptie Cerere

        Trigger: Un email nou este primit.
        Proces: Un LLM analizeaza textul, extrage datele structurate (artist, data, cerere) si interogheaza Google Calendar pentru a verifica disponibilitatea.

        Output: Se genereaza o notificare interna cu rezumatul si statusul disponibilitatii (Liber/Ocupat).

    Modulul 2: Ofertare

        Trigger: Manual (declansat de un agent dupa negociere).

        Proces: Sistemul preia un ID de artist si un email de client. Cauta tarifele artistului  intr o baza de date (ex: Google Sheets) si le compileaza.

        Output: Un email standardizat cu oferta este trimis clientului.

    Modulul 3: Validare

        Trigger: Detectarea unui email de confirmare de la client.

        Proces: Fluxul marcheaza oferta ca "Confirmata de Client".

        Output: Un email este trimis automat catre artist cu detaliile evenimentului, solicitând confirmarea (Accept/Refuz) si un posibil eveniment este creat google calendar.

    Modulul 4: Finalizare

        Trigger: Detectarea email ului de raspuns al artistului.

        Proces:

            Daca raspunsul e "Accept", sistemul se conecteaza la Google Calendar pentru a marca evenimentul(de la posibil la are loc).

            Simultan, se conecteaza la API ul unui serviciu de facturare pentru a emite eFactura cu datele clientului si tariful.

        Output: Clientul este notificat, iar statusul ofertei este marcat ca "Finalizat".

Asta e schita generala. Este doar o mapare a pasilor si a modului  in care s ar putea conecta sistemele.