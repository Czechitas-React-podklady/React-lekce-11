# Cvičení 1 - Stránky v Reac routeru

Příklad na procvičení, jak pomocí React routeru vytvořit v naší aplikaci jednoduchou navigaci a "stránky".

1. Vygenerujte si novou aplikaci pomocí příkazu `create-czechitas-app`, tak jak to děláme vždy, a vymaž z ní všechen nepotřebný vzorový kód. Obsah hlavní `App` nahraď za následující kód:
  ```jsx
  <header>
    zde bude později menu
  </header>
  <main>
    zde bude později hlavní obsah
  </main>
  ```

2. React Router v našem novém projektu není automaticky, knihovnu si musíš sama nainstalovat pomocí `npm`. Na příkazové řádce v terminálu spusť:
  ```
  npm install react-router-dom
  ```

3. Neboj se v následujících krocích používat [dokumentaci React Routeru](https://reactrouter.com/docs/en/v6/getting-started/overview). Najdeš v ní vše o tom, jak router funguje. Podrobný návod k jednotlivým komponentám routeru najdeš v dokumentaci v sekci [API Reference](https://reactrouter.com/docs/en/v6/api).

4. V aplikaci si vytvoř alespoň 3 komponenty, které budou představovat stránky naší aplikace. Na názvu nám teď příliš nezáleží, ale pojmenuj je třeba `Home`, `About` a `Detail`. Obsah stránek (komponent) může být třeba jen nadpis a jeden odstavec textu. Například takto:
  ```jsx
  const Home = () => {
    return (
      <>
        <h1>Home</h1>
        <p>Jsem domovská stránka</p>
      </>
    )
  }
  ```
  Podobně vytvoř i další dvě komponenty.

5. Všechny tři komponenty naimportuj do hlavního souboru.

6. V hlavním souboru (tam, kde je komponenta App) nezapomeň naimportovat všechny potřebné komponenty z `react-router-dom`. Budeš potřebovat komponenty `BrowserRouter`, `Routes`, `Route` a `Link`.

7. Podle dokumentace obal jsx celé aplikace do `<BrowserRouter>` komponenty. To tvojí aplikaci umožní uvnitř používat ostatní komponenty z `react-router-dom`.

8. V hlavní `App` do značky `<header>` přidáme jednoduché menu. Pomocí komponenty `<Link>` vlož do hlavičky odkazy na následující stránky:
  - **Home**, cesta `'/'`
  - **About**, cesta: `'/about'`
  - **Detail**, cesta: `'/detail'`
  V prohlížeči si rovnou můžeš vyzkoušet, že klikání na odkazy mění adresu za lomítkem v adresním řádku prohlížeče, i když se zatím neukazuje obsah našich stránek.

9. Podívej se v dokumentaci, jak se zapisuje struktura s React Router komponentami `<Routes>` a `<Route>`. Tuto strukturu vlož do kódu dovnitř sekce `<main>` a uvnitř použij svoje tři nové stránky (komponenty) Home, About a Detail, které sis naimportovala v kroku 5.

  Jednotlivé `<Route>` do sebe zatím nebudeme vnořovat (v dokumentaci je mají rovnou vnořené do sebe, ale my si to ukážeme si později).

  Náš kód tedy bude vypadat nějak takto:
  ```jsx
  <Routes>
    <Route ... />
    <Route ... />
    <Route ... />
  </Routes>
  ```
  Místo tří teček samozřejmě doplň správné parametry.

10. Vyzkoušej, že aplikace správně funguje - při klikání na odkazy by se měla měnit adresa v prohlížeči a obsah stránky.


## Bonus

11. Přidej zajímavější obsah dle libosti a nastyluj jednotlivé stránky a navigaci, ať vypadá jako skutečné menu.

12. Místo komponenty `Link` můžeš použít komponentu `NavLink`, která umí automaticky stylovat aktivní odkazy.

  Podívej se do [dokumentace](https://reactrouter.com/docs/en/v6/api#navlink). Dokumentace bohužel není moc výřečná, ale když budeš pozorná, tak se tam dočteš, že do atributu `className` komponenty `NavLink` jde napsat funkce, která automaticky jako parametr dostane hodnotu `true` nebo `false` podle toho, zda je odkaz zrovna aktivní (tj. uživatel je na stránce, na kterou odkaz vede). Podle hodnoty `true/false` můžeš z funkce vrátit název třídy, jakou chceš, aby odkaz dostal. Když si tuto třídu v CSS vhodně nastyluješ, budou se ti odkazy v menu automaticky obarvovat podle toho, na které stránce zrovna budeš.
