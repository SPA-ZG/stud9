Aplikacija: https://sixlab.onrender.com/

Pokretanje:
- npm install
- npm run build
- npm run serve (ili npm run dev za development mode)

1. interpolation/one-way binding - NIJE IMPLEMENTIRANO
2. two-way binding - komponenta ContactForm, svako input polje forme ima v-model
3. methods - komponenta Main ima methods na liniji 50, kao i primjerice ContactForm na liniji 42
4. computed properties - komponenta ContactForm, linija 37
5. scoped style - komponenta ProductCard, linija 26
6. lifecycle hook - komponenta Main na liniji 47 koristi beforeMount hook
7. routing - u router/index.js se mogu vidjeti rute (home, about i contact), a u komponenti Navbar se može kliknuti na link koji vodi na pojedinu stranicu
8. Dvije komponente: 
	komponenta bez stanja, koristiti properties - komponenta ProductCard ima properties (linija 23), komponenta About je bez stanja i bez propertisa
	komponenta sa stanjem - komponenta Main ima stanje, linija 37, kao i komponenta ContactForm na liniji 30
9. emitiranje eventa - komponenta SubmitButon emitira event na liniji 9
10. store (Pinia) - NIJE IMPLEMENTIRANO
11. asinkroni dohvat podataka - komponenta Main dohvaća podatke na liniji 51, s time da su oni mockani u data/data.json 
