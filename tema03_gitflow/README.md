# Gitflow
![](./slike/gitflow1.png)

## Šta je gitflow?

`Gitflow` je uspešan model za grananje. Autor je `Vincent Driessen`. Napravljen je takav da bude pogodan za saradnju i skalabilan.

## Teorija

### Grane

Postoje dve glavne glavne grane: 
- `master` grana na kojoj se nalazi produkcioni kod. Ovde se ne dešavaju promene dok neko ne pusti kod u produkciju.
- `develop` grana je za kod koji je trenutno u izradnji. Funkcionalnost i popravke grešaka se ovde spajaju. Na ovoj grani ima više gužve.
![](./slike/gitflow2.png)
- Pored ove dve grane postoje i pomoćne `feature`, `release` i `hotfix` grane.

### Feature grana

Grana `feature` služi za implementaciju nove funkcionalnosti. Na ovaj način se odvajamo od `develop` grane dok se vrši implementacija nove funkcionalnost i kasnije se vraćamo na `develop` granu kada se ta implementacija završi. Svi delovi koda koji su i dalje u izradnji se nalaze trenutno nalaze u nekoj `feature` grani. Ako je potrebno da se izvrši eksperiment, ovo je idealna grana za to, jer kasnije je možemo samo obrisati.
![](./slike/gitflow3.png)

### Release grana

Grana `release` služi za kod koji je dovoljno testiran da bude u produkcionom kodu. Ovde se ne vrše implementacije novih funkcionalnost, već se samo ispravljaju neke sitne greške u poslednjim trenutku ili slično. Grana `release` se pravi u okviru `develop` grane i spaja se sa `develop` i `master` granom. Razlog za ovu granu je mogućnost da se gleda kod za produkcioni, dok se na `develop` grani ne prestaje sa implementacijom novih funkcionalnosti. Kada se napravi `release` grana, onda dobije svoju verziju.
![](./slike/gitflow4.png)

### Hotfix grana

Grana `hotfix` služi za ispravke koda u trenutku kada je on već pušten u produkciju. Ova grana se pravi nad `master` granom, gde se vrše potrebne ispravke i onda se spaja sa `master` i `merge` granom. Grane `hotfix` dobijaju broj verzije kada se naprave (Primer. ako je release 1.2, onda je hotfix 1.2.1).
![](./slike/gitflow5.png)

### Bonus

Pogledati sledeći [video](https://www.youtube.com/watch?v=1SXpE08hvGs&ab_channel=Devchild) kao rezime.

## Praksa

### Instalacija alata

Instalacija alata na linux-u: `sudo apt install git-flow`.

### Rad sa gitflow alatom

Lista komandi:
- Inicijalizacija: `git flow init`.
- Inicijalizacija nove funkcionalnosti: `git flow feature create feature-name`.
- Završavanje nove funkcionalnosti: `git flow feature finish feature-name`.
- Inicijalizacija novog izdanja: `git flow release start version-number`
- Završavanje novog izdvanja: `git flow release finish version-number`
- Inicijalizacija nove hitne ispravke: `git flow hotfix start new-version-number`
- Završavanje nove hitne ispravke: `git flow hotfix finish new-version-number`

## Reference

[git-flow](https://www.codewall.co.uk/a-git-flow-explainer-how-to-tutorial/)