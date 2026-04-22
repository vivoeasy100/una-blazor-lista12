# EcoMonitor 🌱

Este projeto é uma prova de conceito (PoC) para o sistema de gamificação da ONG "ReCiclo", focado em registrar ações sustentáveis e acompanhar o impacto positivo gerado. A aplicação foi construída com **Blazor Interactive Server**.

O desenvolvimento focou na criação de componentes reutilizáveis (`EcoStatus.razor`), utilizando parâmetros (`[Parameter]`), gestão de estado dinâmico e funcionalidades de gamificação (barra de progresso e mensagens de conquista).

## Identificação
- **Nome:** [Seu Nome Completo Aqui]
- **Curso:** [Seu Curso Aqui]

## Heurísticas de Nielsen Aplicadas
1. **Visibilidade do Status do Sistema:** 
   O aplicativo mantém o usuário constantemente informado do seu progresso em tempo real. A cada clique no botão de ação, o contador de pontos  acumulados é imediatamente atualizado na tela, além de demonstrar o impacto por meio do crescimento e da mudança de cor da barra de progresso.
   
2. **Correspondência entre o Sistema e o Mundo Real:**
   As recompensas e termos utilizados no app refletem significados facilmente compreendidos pelo usuário e ligados à sua realidade. Por exemplo, a conquista "Você é um Herói do Planeta!" adota gatilhos emocionais da vida real que incentivam o usuário a continuar engajado, usando linguagem humanizada.

## Guia de Execução

Siga os passos abaixo para executar a aplicação no seu ambiente local:

1. Certifique-se de ter o [SDK do .NET (versão 8 ou mais recente)](https://dotnet.microsoft.com/download) instalado.
2. Abra o terminal na pasta raiz do repositório `EcoMonitor`.
3. Para garantir que todas as dependências estão corretas e compilar o projeto, execute:
   ```bash
   dotnet build
   ```
4. Para rodar a aplicação:
   ```bash
   dotnet run --launch-profile https
   ```
5. O console exibirá as URLs (ex: `https://localhost:XXXX`). Clique no link para abrir a aplicação no seu navegador.

## Explicação Técnica: Utilização do `[Parameter]`
O anotação `[Parameter]` (decorador) do Blazor é fundamental para a criação de componentes reutilizáveis. 

Em vez de criarmos vários arquivos diferentes para cada tipo de ação sustentável (um para reciclagem, um para plantio, etc), criamos um único componente genérico chamado `EcoStatus.razor`. Nele, definimos propriedades públicas decoradas com `[Parameter]`, como `Titulo` (texto que descreve a ação) e `Peso` (quantos pontos adiciona). 

Isso permite que o componente original "exponha" essas propriedades para onde ele for consumido. Na página principal (`Home.razor`), podemos criar múltiplas instâncias do mesmo componente passando valores distintos.

```razor
// Na Home.razor: 
<EcoStatus Titulo="Plantio de Árvores" Peso="10" />
```
O Blazor injeta esses valores diretamente no comportamento do componente, criando três instâncias funcionais mas com pesos e títulos independentes, otimizando muito o reaproveitamento de código.

## Desafios Extras Implementados ✨
- **Barra de Progresso:** Um indicador visual interativo que mostra a porcentagem rumo ao objetivo de ser um "Herói do Planeta", mudando de cor quando atinge a meta base de 50.
- **Mensagem de Conquista:** Uma mensagem de feedback motivacional, com animação fluída e identidade visual própria, revelada quando o usuário atinge o total de 100 pontos acumulados.
