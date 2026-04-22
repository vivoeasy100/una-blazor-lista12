# EcoMonitor 🌱

Este projeto é uma prova de conceito (PoC) para o sistema de gamificação da ONG "ReCiclo", com o objetivo de registrar ações sustentáveis e acompanhar o impacto positivo gerado em tempo real. A aplicação foi desenvolvida utilizando **Blazor Interactive Server**.

O foco principal do desenvolvimento foi a criação de componentes reutilizáveis (`EcoStatus.razor`), utilizando parâmetros (`[Parameter]`), gerenciamento de estado dinâmico e elementos de gamificação, como barra de progresso e mensagens de conquista.

---

## 🧠 Heurísticas de Nielsen Aplicadas

### 1. Visibilidade do Status do Sistema

O sistema mantém o usuário constantemente informado sobre seu progresso. A cada interação (clique no botão), o valor dos pontos é atualizado imediatamente na interface, proporcionando feedback em tempo real. Além disso, a barra de progresso evolui visualmente, reforçando a percepção de avanço.

### 2. Correspondência entre o Sistema e o Mundo Real

A linguagem utilizada no sistema é simples, intuitiva e próxima da realidade do usuário. Termos como "Plantio de Árvores" e a conquista "Você é um Herói do Planeta!" tornam a experiência mais envolvente e significativa, estimulando o engajamento por meio de elementos emocionais.

---

## ▶️ Guia de Execução

Para executar o projeto localmente, siga os passos:

1. Instale o [.NET SDK (versão 8 ou superior)](https://dotnet.microsoft.com/download)
2. Abra o terminal na pasta do projeto `EcoMonitor`
3. Execute o comando:

   ```bash
   dotnet build
   ```
4. Em seguida, rode a aplicação:

   ```bash
   dotnet run --launch-profile https
   ```
5. Acesse a URL exibida no terminal (ex: `https://localhost:XXXX`)

---

## ⚙️ Explicação Técnica: Uso do `[Parameter]`

O atributo `[Parameter]` é utilizado no Blazor para permitir que um componente receba valores externos, tornando-o reutilizável e dinâmico.

No componente `EcoStatus.razor`, foram definidos parâmetros como:

* `Titulo`: responsável pelo nome da ação sustentável
* `Peso`: define quantos pontos são adicionados a cada interação
* `Meta`: define o limite de pontos para atingir um objetivo

Esses parâmetros permitem que o mesmo componente seja reutilizado várias vezes com comportamentos diferentes.

Exemplo de uso na `Home.razor`:

```razor
<EcoStatus Titulo="Reciclagem de Plástico" Peso="1" Meta="10" />
<EcoStatus Titulo="Plantio de Árvores" Peso="10" Meta="100" />
<EcoStatus Titulo="Descarte de Eletrônicos" Peso="5" Meta="50" />
```

Cada instância do componente mantém seu próprio estado (`Total`), garantindo independência entre os elementos da interface.

---

## 🚀 Desafios Extras Implementados

* **Barra de Progresso:** Representação visual do progresso do usuário em relação à meta definida, atualizada dinamicamente conforme as interações.
* **Mensagem de Conquista:** Exibição de uma mensagem motivacional ("🎉 Você é um Herói do Planeta!") ao atingir a meta de pontos, incentivando o engajamento do usuário.
* **Desativação do Botão:** O botão de ação é automaticamente desabilitado ao atingir a meta, evitando interações desnecessárias e reforçando o estado do sistema.
