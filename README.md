# Aula 07 - Rotas no React
📄 Link de acesso aos <a href="https://cord-delivery-7eb.notion.site/React-Avan-ado-0dd7bebfaf364c1f8544098923b060e5">resumos</a>. 

🖼 Link de <a href="https://jonathanBenedito.github.io/rotas-no-react">demonstração</a>.

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
