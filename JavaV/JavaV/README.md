# Java V: Formulari i misionit sekret

Detyrë në lëndën Programimi në WWW. Projekt me HTML dhe CSS, pa biblioteka të jashtme dhe pa JavaScript.

## Hapja e projektit

1. Nxirre folderin `JavaV` nga ZIP-i.
2. Hap `JavaV/index.html` në një shfletues modern.
3. Plotëso formularin me të dhëna të sajuara dhe shtyp “Nis misionin”.

Nuk nevojitet instalim. Skedarët duhet të qëndrojnë bashkë në të njëjtin folder, që lidhjet relative të funksionojnë.

## Skedarët

* `index.html`: formulari, tabela me tri orare, rregullat dhe njoftimi për GET.
* `style.css`: stilet për të dyja faqet dhe përshtatja për telefon, tablet e kompjuter.
* `pranuar.html`: faqja e pranimit dhe shpjegimi i demonstrimit.
* `README.md`: udhëzimet, analiza e hyrjeve dhe daljeve, rastet e kontrollit dhe reflektimi individual.

## Analiza e hyrjeve dhe daljeve

**Hyrjet:** pseudonim me 3 deri në 20 karaktere; email në format të vlefshëm; numër i plotë i personave nga 1 deri në 5; një kategori mes Zbulim, Logjikë dhe Aventurë; pranim i detyrueshëm i rregullave.

**Daljet:** për të dhëna jo të vlefshme, shfletuesi e bllokon dërgimin dhe paraqet mesazhin e validimit pranë fushës. Për të dhëna të vlefshme, shfletuesi kalon përmes GET te `pranuar.html`, me vlerat e formularit në URL. Nuk ruhet regjistrim në server.

**Rast normal:** `Ekipi Orion`, `orion@example.com`, 3 persona, kategoria Zbulim dhe rregullat e pranuara. Pritet kalimi te faqja e pranimit.

**Rast kufitar 1:** pseudonimi `ABC`, `abc@example.com`, 1 person, kategori e zgjedhur dhe rregulla të pranuara. Vlerat në kufirin e poshtëm pranohen. Pseudonimi me 2 karaktere ose grupi me 0 persona bllokohen.

**Rast kufitar 2:** pseudonimi `12345678901234567890` (20 karaktere), `test@example.com`, 5 persona, kategori e zgjedhur dhe rregulla të pranuara. Vlerat në kufirin e sipërm pranohen. `maxlength` e kufizon shkrimin në 20 karaktere; grupi me 6 persona bllokohet.

## Përmbushja e kërkesave

* Çdo kontroll ka `label` të lidhur me `id`.
* Radio butonat janë të grupuar në `fieldset` me `legend` dhe kanë të njëjtin `name`.
* `required` përdoret për fushat e detyrueshme, kategorinë dhe pranimin e rregullave.
* Pseudonimi përdor `minlength="3"` dhe `maxlength="20"`.
* Email përdor `type="email"`.
* Numri i personave përdor `type="number"`, `min="1"`, `max="5"` dhe `step="1"`.
* Tabela ka tri rreshta të dhënash, `caption`, tituj kolonash me `th scope="col"` dhe tituj rreshtash me `th scope="row"`.
* Formulari përdor `action="pranuar.html"` dhe `method="get"`, pa çaktivizuar validimin vendas.
* Të dyja faqet shpjegojnë se të dhënat janë demonstrim, GET shfaq vlerat në URL dhe nuk ruhet regjistrim në server.

## Kontrolli i funksionimit

| Prova | Rezultati i pritur |
| :--- | :--- |
| Dërgimi i formularit bosh | Bllokohet nga shfletuesi. |
| Email `email-pa-format` | Bllokohet. |
| Numri i personave 0 ose 6 | Bllokohet. |
| Numri i personave 1.5 | Bllokohet sepse kërkohet numër i plotë. |
| Pseudonimi `AB` i shkruar në fushë | Bllokohet sepse ka vetëm 2 karaktere. |
| Shkrimi mbi 20 karaktere | Kufizohet nga `maxlength`. |
| Kategoria e pazgjedhur | Bllokohet. |
| Rregullat e papranuara | Bllokohet. |
| Të gjitha fushat të vlefshme | Kalon te `pranuar.html` me parametrat GET në URL. |

Shënim: pamja dhe gjuha e mesazheve të validimit varen nga shfletuesi dhe gjuha e tij.

## Reflektim individual

**Pse `required` në frontend nuk provon që të dhënat në një sistem real janë të sigurta?**

Atributi `required` kontrollon në shfletues nëse është plotësuar një fushë, por përdoruesi mund ta ndryshojë HTML-në ose të dërgojë kërkesë drejtpërdrejt, duke e anashkaluar formularin. Edhe një vlerë që e kalon këtë kontroll mund të jetë e pasaktë ose e dëmshme. Në një sistem real, serveri duhet t'i validojë përsëri të dhënat, të kontrollojë kufijtë dhe vlerat e lejuara, të përdorë pyetje të parametrizuara për bazën e të dhënave dhe të kodojë përmbajtjen kur e shfaq. `required` ndihmon përdoruesin gjatë plotësimit, por nuk e zëvendëson sigurinë në server.

## Dorëzimi në GitHub

Vendose folderin `JavaV` në rrënjën e repository-t individual. Mbaj strukturën:

* `JavaV/index.html`
* `JavaV/style.css`
* `JavaV/pranuar.html`
* `JavaV/README.md`

Shto skedarët në repository, bëj commit dhe push. Nëse Classroom kërkon linkun e repository-t, dorëzo linkun atje. ZIP-i përmban folderin e gatshëm; ngarkimi në repository bëhet me llogarinë tënde.
