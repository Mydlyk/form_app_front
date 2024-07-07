<h1>Form app front</h1>
<h2>Opis aplikacji</h2>
Form_app_front wykorzystuje vue 3. Dane w formularzach są walidowane za pomcą prostych instrukcji warunkowych i biblioteki vue validator. Aplikacja obsługuje i wyświetla błedy serwera oraz klienta.

<h2>Wykorzystane biblioteki Vue(npm):</h2>
Bootstrap- framework CSS wykorzystywane do do stylizowania komponentów
Validator- biblioteka JavaScript służąca do walidacji danych.
Axios- biblioteka służąca do wykonywania zapytań HTTP w aplikacjach JavaScript.

<h2>Implementcaja Vue:</h2>

Pliki aplikacji vue znajdują w folderze "assets". W pliku app.js zostały dodane biblioteki bootstrap.

![image](https://github.com/Mydlyk/form_app/assets/65900710/7e29d559-e238-4a1a-a3f1-6a509fe424aa)

W pliku App.vue został stworzony formularz. Została wyłączone walidacja poprzez przeglądarkę oraz dodane zostało wywołanie funkcji submitForm po wysłaniu formularza. Wszystkie pola formularza są wymagane oraz wartości pól zostały powiązane z obiektem formData poprzez "v-model".

![image](https://github.com/Mydlyk/form_app/assets/65900710/9e9af3a1-5cc2-4773-8d04-e4d1e45f89bc)

Funkcja submitForm wywołuje w instrukcji warunkowej funkcję validateForm która odpowiada za walidację danych z formularza. Gdy dane są nie poprawne zwraca fałsz.

![image](https://github.com/Mydlyk/form_app/assets/65900710/1a82fa22-a7b8-44d6-b492-bb7ce7deb6cd)

Funkcja validateForm sprawdza w instrukcjach warunkowych czy pola nie są puste,czy nie składją się z spacji (Trim()) i czy email jest poprawny za pomocą funkcji validator.isEmail(). Jeśli zostanie wykryty jakiś bład zostanie on przypisany do obiektu errors.

![image](https://github.com/Mydlyk/form_app/assets/65900710/2f36b49b-2d89-4f5d-8e1a-1a71382d1fdc)

Jeśli obiekt errors nie jest pusty zostanie wywołany Komponent FormErros i zostaną wyświetlone błedy.

![image](https://github.com/Mydlyk/form_app/assets/65900710/f07d219b-0ee4-4217-a392-ccac98de2ff2)

Jeśli nie będzie żadnych błędów w funkcji submitForm zostanie wywołana funkcja axios oraz zapytanie POST. Jeśli serwer zwróci jakieś błędy zostana one złapane w bloku try catch oraz podobnie jak błędy z formularza zostaną wyświetlone na stronie.

![image](https://github.com/Mydlyk/form_app/assets/65900710/246febaa-c355-4a1a-8464-1bc9f665f4f7)

Przez to że wyświetlanie błędów od strony klienta i serwera jest bardzo podobne został stworzony odzielny komponent FormErrors który może być wielokrotnie używany do wyświetlania błędów.

![image](https://github.com/Mydlyk/form_app/assets/65900710/3d3f1e25-f03e-4cd2-9c30-8cb7bfd6a8a7)

Jeśli serwer nie zwróci żadnych błędów funkcja submitForm odczyta dane i przypisze je do obiektu submittedData, a następnie na stronie zostaną one wypisane w postaci tabelki. 
![image](https://github.com/Mydlyk/form_app/assets/65900710/888b8087-7199-4a5d-be0e-9f7d11fc047d)

<h2>Działanie aplikacji:</h2>

![image](https://github.com/Mydlyk/form_app/assets/65900710/f0da9c74-31ac-41a0-a841-25b15e518815)

![image](https://github.com/Mydlyk/form_app/assets/65900710/1de8afdb-1240-4158-b8b1-a8f45fbe0e54)


![image](https://github.com/Mydlyk/form_app/assets/65900710/fe8227bd-fbe1-4944-a380-e2cf94503bdf)

W tym przykładzie zostało usunięte sprawdzanie po stronie klienty by przetestować czy poprawnie zostanie odczytany błąd od serwera.

![image](https://github.com/Mydlyk/form_app/assets/65900710/7e603391-8667-4d12-b7c7-87f731a4f07e)

![image](https://github.com/Mydlyk/form_app_front/assets/65900710/31f7ea75-cf92-4372-bd6e-c08596e73c32)

