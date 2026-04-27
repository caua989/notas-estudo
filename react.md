Criando repositorio para react

Na area "add git.ignore" deixe "node"

Configurando react no repositorio

Começe clicando em "Ctrl+aspas" para criar um terminal, nele abra um novo terminal do tipo "Git bash" e nele coloque 
"npm create vite@latest ."

na proxima apenas de "Enter"



Pastas

No "src" crie "components" e "pages"


Em "components" tenha "Footer","Header" e "List"

em "pages" tenha "About", "Home", "SingUp" e "exercicioX"


em todos tenha "index.jsx" e "style.css"

nos "index.jsx" tenha em todos " import './style.css' " no inicio, em baixo tenha " function ///nome da pagina/// () { ///outra linha/// return ( ///outra linha/// ///assuntos/// ///outra linha///) ///outra linha///} " e no fim "export default ///nome da pagina///"


exemplo pagina Home
=================================================================================
import { Link } from 'react-router-dom';
import './style.css';

function Home() {
    return (
        <>
        <h2>Bem-Vindo(a) ao meu sistema</h2>
        <Link to="/about" >
        <button>navegar para About</button>
        </Link>
        </>
    )
}

export default Home
===================================================================================

exemplo pagina Header
===================================================================================
import './style.css'

function Header () {
    return (
    <header>
        <h1>Exemplo de React</h1>
    </header>
    )
}

export default Header
=================================================================================

exemplo pagina SingUp/exercicios
=================================================================================
import { useState } from 'react';
import './style.css';

function SingUp() {
    const [ nome,setNome ] = useState("sla")
    const [ email,setEmail ] = useState("sla@sla")
    const [ senha,setSenha ] = useState("slasla")

    const [ resultado,setResultado ] = useState("")

    function handleSubmit(event) {
        event.preventDefault();
        console.log(nome, email, senha)
        setResultado(1+1)
    }

    return (
        <>
        <h2>Criar Conta</h2>

        <form onSubmit={handleSubmit}>
            <label>Nome</label>
             <input 
               type="text"
               value={nome}
               onChange={ (event) => setNome(event.target.value) }
               />

            <label>Email</label>
             <input 
               type="email"
               value={email}
               onChange={ (event) => setEmail(event.target.value) }
               />

             <label>Senha</label>
             <input 
               type="password"
               value={senha}
               onChange={ (event) => setSenha(event.target.value) }
               />

               <p>{resultado}</p>

               <button type="submit">Cadastrar</button>
        </form>
        </>
    )
}

export default SingUp
=================================================================================

Exemplo App.jsx
=================================================================================
import './App.css'
import Header from './components/Header'
import Footer from './components/Footer'
import List from './components/List'
import { Route, Routes } from 'react-router-dom'
import Home from './pages/Home'
import About from './pages/About'
import SingUp from './pages/SingUp'

function App() {

 return (
  <>
  
  <Header />

  <Routes>
    <Route path="/" element={<Home />} />
    <Route path="/about" element={<About />} />
    <Route path="/signup" element={<SingUp />} />
  </Routes>

  <Footer />
  </>
 )

}

export default App
=================================================================================