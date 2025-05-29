# 🎬 ScreenMatch - Sistema de Gerenciamento de Filmes e Séries

## 📖 Sobre o Projeto
Projeto desenvolvido durante o curso de Java da Alura, implementando conceitos avançados de programação orientada a objetos, consumo de APIs e manipulação de dados. O sistema integra-se à API OMDB para buscar informações sobre filmes e séries, oferecendo funcionalidades de avaliação, cálculo de tempo de conteúdo e recomendações personalizadas.

**Este projeto faz parte do curso da Alura, onde aprendemos:**
- ✅ Consumir uma API HTTP em Java
- ✅ Receber e converter informações de API para objetos Java
- ✅ Manipular dados no formato JSON
- ✅ Utilizar a biblioteca Gson para conversão de objetos
- ✅ Fazer uso das classes do pacote java.io para manipulação de arquivos

**Funcionalidades Principais:**
- Busca de filmes/séries na API OMDB
- Cálculo de tempo total de conteúdo
- Sistema de avaliação e recomendações
- Armazenamento de dados em arquivos
- Manipulação de listas e ordenação

---

## 🚀 Funcionalidades

| **Gestão de Conteúdo**       | **Integração com API**         |  
|------------------------------|--------------------------------|  
| ✅ Cadastro de filmes/séries | 🔍 Busca em tempo real (OMDB)  |  
| ✅ Sistema de avaliações     | 🎬 Conversão JSON → Objeto     |  
| ⏱ Cálculo de tempo total    | 💾 Armazenamento em arquivo    |  
| 🎭 Filtro de recomendações   | 🛡 Tratamento de exceções      |  

---

## 🛠️ Tecnologias Utilizadas  
<div align="center">  
  <img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java">  
  <img src="https://img.shields.io/badge/Gson-000000?style=for-the-badge&logo=google&logoColor=white" alt="Gson">  
  <img src="https://img.shields.io/badge/HTTP_Client-00599C?style=for-the-badge&logo=apache&logoColor=white" alt="HTTP Client">  
  <img src="https://img.shields.io/badge/JSON-000000?style=for-the-badge&logo=json&logoColor=white" alt="JSON">  
</div>  

---

## 📦 Estrutura do Projeto  
```
src/
├── main/
│ ├── java/
│ │ ├── br.com.alura.screenmatch/
│ │ │ ├── principal/
│ │ │ │ ├── Principal.java
│ │ │ │ ├── PrincipalComBusca.java
│ │ │ │ └── PrincipalComListas.java
│ │ │ ├── modelos/
│ │ │ │ ├── Episodio.java
│ │ │ │ ├── Filme.java
│ │ │ │ ├── Serie.java
│ │ │ │ ├── Titulo.java
│ │ │ │ └── TituloOmdb.java
│ │ │ ├── calculos/
│ │ │ │ ├── CalculadoraDeTempo.java
│ │ │ │ ├── Classificavel.java
│ │ │ │ └── FiltroRecomendacao.java
│ │ │ └── excecao/
│ │ │ └── ErroDeConversaoDeAnoException.java
```

---

## ⚙️ Como Executar

1. **Clone o repositório:**
```bash
git clone https://github.com/seu-usuario/screenmatch.git
```

2. **Importe no Eclipse/IntelliJ:**
   - Abra a IDE e importe como projeto Maven/Gradle
     
3. **Execute as classes principais:**
# Versão básica:
```
java br.com.alura.screenmatch.principal.Principal
```
# Busca na API OMDB:
```
java br.com.alura.screenmatch.principal.PrincipalComBusca
```
# Manipulação de listas:
```
java br.com.alura.screenmatch.principal.PrincipalComListas
```

---

## 🔍 Exemplo de Uso
```
// Consumindo API OMDB
String endereco = "https://www.omdbapi.com/?t=matrix&apikey=b6e53a2d";
HttpClient client = HttpClient.newHttpClient();
HttpRequest request = HttpRequest.newBuilder().uri(URI.create(endereco)).build();
HttpResponse<String> response = client.send(request, HttpResponse.BodyHandlers.ofString());

// Convertendo JSON para objeto Java
Gson gson = new GsonBuilder().create();
TituloOmdb tituloOmdb = gson.fromJson(response.body(), TituloOmdb.class);
Titulo meuTitulo = new Titulo(tituloOmdb);

// Salvando dados em arquivo
FileWriter escrita = new FileWriter("filmes.txt");
escrita.write(gson.toJson(meuTitulo));
escrita.close();
```
---

## 🔥 Destaques Técnicos
- Consumo de API HTTP: Uso de HttpClient para integração com OMDB
- Manipulação de JSON: Conversão de dados com biblioteca Gson
- Persistência em arquivos: Armazenamento com FileWriter
- Polimorfismo: Implementação com herança e interface Classificavel
- Tratamento de Exceções: ErroDeConversaoDeAnoException personalizada
- Collections Framework: Manipulação de listas e ordenação
- Sistema de Recomendações: Filtro baseado em classificações

---

Feito com ❤️ por [Guilherme Geisler](https://www.linkedin.com/in/guilhermegeisler/). como parte do curso de Java da Alura. 🎥
