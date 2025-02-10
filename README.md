# FII_2A1_ReteleDeCalculatoare
QuizGame
În acest proiect am creat un server care poate gestiona un număr nelimitat de clienți, fiecare conectându-se pentru a răspunde la diverse întrebări. Practic, fiecare client se autentifică trimițându-și numele și parola, iar serverul verifică aceste date înainte de a le permite accesul. După ce se conectează, utilizatorul primește un meniu simplu din care poate alege fie să înceapă jocul, fie să se deconecteze.

Pentru a asigura conexiuni stabile și secvențiale, am folosit protocolul TCP/IP, atribuindu-i fiecărui client un thread dedicat. Proiectul a fost realizat în C/C++, iar pentru gestionarea datelor legate de utilizatori și întrebări am optat pentru baza de date SQLite (versiunea 3).

Din punct de vedere tehnic, serverul începe prin inițializarea socket-ului, se leagă de acesta și apoi ascultă conexiunile venite. După autentificare, serverul așteaptă ca toți clienții conectați să fie pregătiți pentru a porni jocul. Odată ce jocul începe, serverul trimite aleatoriu 10 întrebări, fiecare însoțită de variante de răspuns, iar clienții au la dispoziție 10 secunde pentru a răspunde. Fiecare client își calculează propriul scor și îl transmite serverului, care ulterior determină câștigătorul.

Un aspect important este și modul în care se gestionează oprirea aplicației: atunci când se apasă CTRL + C, serverul solicită o confirmare înainte de a se închide, pentru a preveni opririle accidentale.

În concluzie, proiectul asigură o separare clară între partea de prelucrare a datelor (server) și interfața de comunicare cu utilizatorul (client). Pentru dezvoltările viitoare, se prevede adăugarea unor funcționalități suplimentare, precum posibilitatea de a introduce întrebări noi dinamic și opțiunea de înregistrare a utilizatorilor noi.
