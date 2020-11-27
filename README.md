# carfac
Slides and example code on the training React Fundamentals, Carfac, November 2020

## Links - Day #1
- Repository with example code: https://github.com/PeterKassenaar/react-fundamentals
- Puntkomma's in JavaScript zijn OPTIONEEL. Dit heet `Automatic Semicolon Insertion (ASI)`. Lees er eventueel meer over op 
https://stackoverflow.com/questions/2846283/what-are-the-rules-for-javascripts-automatic-semicolon-insertion-asi en/of https://flaviocopes.com/javascript-automatic-semicolon-insertion/
- Over inheritance bij componenten: https://reactjs.org/docs/composition-vs-inheritance.html en/of https://thoughtspile.github.io/2018/11/05/react-extend-justified/

## Day #2
- React Developer Tools voor Chrome: https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en
- React Bootstrap, Bootstrap as optimized React Components: https://react-bootstrap.github.io/
- React: Composition vs. Inheritance: https://reactjs.org/docs/composition-vs-inheritance.html
- Adding `TypeScript` via Create-React-App: https://create-react-app.dev/docs/adding-typescript/
- Simple Solution: `PropTypes` : https://reactjs.org/docs/typechecking-with-proptypes.html
- "Gebruik liever geen `index` als key": https://reactjs.org/docs/lists-and-keys.html
- Vraag van Jan: "LESS gebruiken in React?": https://jasonwatmore.com/post/2020/02/10/react-how-to-add-global-css-less-styles-to-react-with-webpack
- Algemeen architectuur: How to organize a Large Scale Web application: https://www.sitepoint.com/organize-large-react-application/
- Enkel gebruikte CSS meebundelen en de rest verwijderen: `PurgeCSS` : https://purgecss.com/

## Day #3
Voorbeeld van een generieke service die de calls naar de API afhandelt (pseudo code):

```javascript
import axios from 'axios'

// the API-URLs to get the data from
const url = 'https://restcountries.eu/rest/v2/all';
const detail_url = 'https://restcountries.eu/rest/v2/name';

export default new class CountryService{
	// 'lokale API' vor deze service
	getCountries(){
		return axios.get(url);

	}
	deleteCountry(country){
		//....
	}
	getSingleCountry(id){
		//....
	}
}
``` 

En in de component waar je dan de service wilt gebruiken, wordt deze geimporteerd:

```javascript
import countryService from './services/CountryService'
...
componentDidMount(){
    countryService.getCountries()
        .then(response => {
            this.setState({
                isLoaded: true,
                countries: response.data
            })
        })
}
```

- Lijst met veel beschikbare Public API's: https://github.com/public-apis/public-apis
- Opinie(s) over het navigeren vanuit code met de router.Via componenten of via `history.push()`? - https://ui.dev/react-router-v4-programmatically-navigate/


Bedankt voor jullie aanwezigheid en vragen tijdens de opleiding.

Veel succes met React in uw werk!

Peter.



