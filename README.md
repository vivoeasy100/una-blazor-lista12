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
<img width="1659" height="1528" alt="Captura de tela 2026-04-22 203858" src="https://github.com/user-attachments/assets/64b8a19e-6d93-4c5e-9db8-1df3fc730c52" />
<img width="1585" height="1493" alt="Captura de tela 2026-04-22 204013" src="https://github.com/user-attachments/assets/030dbd68-5005-4d07-9c18-f64bd4101c1e" />
<img width="1640" height="1453" alt="Captura de tela 2026-04-22 204003" src="https://github.com/user-attachments/assets/e981cd1a-45fb-4a80-bfd9-2b2e77d6b30e" />
<img width="1580" height="1513" alt="Captura de tela 2026-04-22 203955" src="https://github.com/user-attachments/assets/9737cfb5-ef51-4d28-9a10-cab5f1eed28b" />
<img width="1619" height="1493" alt="Captura de tela 2026-04-22 203943" src="https://github.com/user-attachments/assets/cc01c129-3c15-47bb-95a5-c8ebe3088475" />
