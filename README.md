# Aula 07 & 08 - Rotas no React & Styled Components
📄 Link de acesso aos <a href="https://cord-delivery-7eb.notion.site/React-Avan-ado-0dd7bebfaf364c1f8544098923b060e5">resumos</a>. 

## Rotas (Routes)

São caminhos específicos que levam para determinadas páginas, como se fossem links.

```jsx
const AppRoutes = () => (
    <BrowserRouter>
        <Routes>
            <Route exact path='/' element={<Posts />} />
            <Route exact path='/post/:id' element={<Post />} />
        </Routes>
    </BrowserRouter>
)
```
Página padrão para definir as rotas do projeto
```jsx
<Link to='/'>Voltar para os posts</Link>
```
Link simples para acessar o caminho da rota.
```jsx
<Link to={`/post/${post.id}`}>
    <img src={post.image} alt="" />
    <h2>{post.title}</h2>
</Link>

// ----------------------------------------------

// Lembre-se de usar useParams na página onde vai receber os parâmetros

const { id } = useParams()
```
Link para acessar o caminho da rota com parâmetros.

## Styled Components
É uma biblioteca que possibilita estilizar páginas de forma individual, evitando bugs de estilos e deixando nosso projeto mais dinâmico.

> Estilizando um componente individual
> 

```jsx
const Button = styled.button`
  background: transparent;
  border-radius: 3px;
  border: 2px solid palevioletred;
  color: palevioletred;
  margin: 0 1em;
  padding: 0.25em 1em;
`
```

> Estilizando de forma global
> 

```jsx
import { createGlobalStyle } from 'styled-components'

function App() {
	return (
		<div>
			<GlobalStyle />
			<AppRoutes />
		</div>
	);
}
```

```jsx
const GlobalStyle = createGlobalStyle`
	* {
		margin: 0;
		padding: 0;
	}
`
```

> Estilizando componente de acordo com uma prop.
> 

```jsx
const Section = styled.section`
    background-color: blue;
    ${props => props.red && css `
        background-color: red;
    `}
    padding: 50px;
`
```

```jsx
<Section red>
    <Link to='/'>Voltar para os posts</Link>
    <div>
        <Img src={post.image} alt={post.title} />
        <h2>{post.title}</h2>
        <p>{post.text}</p>
    </div>
</Section>
```

Ao colocar a prop `red`, automaticamente o componente terá fundo vermelho.