🧮 Calculadora de IR 2026 - Simulador da Lei nº 15.270/2025

Este projeto é uma aplicação web de arquivo único (Single File Application) desenvolvida para simular o cálculo do Imposto de Renda Pessoa Física (IRPF) com base nas novas regras sancionadas em novembro de 2025, especificamente focando na isenção para quem ganha até R$ 5.000,00.

🚀 Funcionalidades

Cálculo em Tempo Real: Atualiza os valores automaticamente enquanto o usuário digita.

Cálculo Progressivo do INSS: Deduz a contribuição previdenciária (baseada nas faixas de 2024/2025) para encontrar a base de cálculo real do IR.

Lógica da Nova Isenção: Aplica isenção total para bases de cálculo até R$ 5.000,00.

Fórmula de Transição: Implementa a lógica matemática de redução para salários na faixa de transição (até R$ 7.350,00):

D = 978,62 - 0,133145 * R

Detalhamento Visual: Exibe o passo a passo da conta (Bruto → INSS → Base → Desconto → Líquido).

🛠️ Tecnologias Utilizadas

HTML5: Estrutura semântica.

JavaScript (Vanilla): Lógica de cálculo e manipulação do DOM. Não requer frameworks JS pesados (como React ou Vue).

Tailwind CSS (via CDN): Estilização moderna e responsiva.

FontAwesome: Ícones para melhor experiência visual.

🧠 Lógica de Negócios (Como o cálculo funciona)

O código segue um fluxo lógico financeiro estrito dentro da função calculateTax():

Entrada: Recebe o Salário Bruto.

Dedução do INSS: Calcula o INSS de forma progressiva (7.5% a 14%) respeitando o teto do RGPS.

Resultado: Base de Cálculo = Salário Bruto - INSS.

Cálculo do IR (Nova Regra):

Cenário A (Isento): Se Base <= 5.000, o imposto é R$ 0,00.

Cenário B (Transição): Se 5.000 < Base <= 7.350, calcula-se o imposto padrão e subtrai-se um desconto variável calculado pela fórmula da lei.

Cenário C (Padrão): Se Base > 7.350, aplica-se a tabela progressiva padrão vigente.

Saída: Exibe o Salário Líquido e a Alíquota Efetiva.

📂 Estrutura do Código

O arquivo index.html contém tudo o que é necessário para rodar:

<head>: Importação de fontes e bibliotecas de estilo.

<body>: Estrutura da interface do usuário (Inputs e Cards de Resultado).

<script>:

calculateINSS(salary): Função isolada para tratar a progressividade da previdência.

calculateStandardIRPF(base): Função auxiliar com a tabela tradicional do IR.

calculateTax(): Função principal que orquestra a lógica e atualiza o HTML.

📦 Como Executar

Não é necessário instalação de dependências (npm, node, etc).

Baixe o arquivo index.html.

Abra-o em qualquer navegador moderno (Chrome, Firefox, Edge, Safari).

Requisito: É necessário conexão com a internet para carregar o Tailwind CSS e o FontAwesome (CDN).

🌐 Acesso Online: https://capx8.github.io/calculadora_IRPF/

⚠️ Aviso Legal

Esta calculadora é uma simulação baseada nos textos divulgados sobre a Lei nº 15.270/2025. O cálculo do INSS é uma estimativa baseada nas tabelas vigentes e pode sofrer reajustes anuais oficiais. Não substitui o cálculo oficial da Receita Federal.