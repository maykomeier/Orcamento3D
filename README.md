# Gestão de Orçamentos para Impressão 3D baseado em upload de G-code
Um sistema simples criado com o Trae em php+mysql para gerenciamento de orçamentos de impressão 3D.

O sistema é uma aplicação web simples, criada com IA do TRAE, mas muito funcional. É focada exclusivamente em gerar orçamentos automáticos de impressão 3D com base nos parâmetros cadastrados pelo operador e nas informações extraídas de um arquivo G-code enviado pelo usuário.
O objetivo é agilizar o cálculo do custo final da impressão, identificando automaticamente quantidade de material por cor/extrusor, tempo total de impressão e aplicando regras internas de precificação definidas previamente pelo operador.

Fluxo Geral

O usuário acessa a página e faz o upload do G-code.
O sistema interpreta o G-code e calcula:
Tempo estimado de impressão
Quantidade de material extrudado por filamento/cor (E total separado por extrusor: E0, E1, E2…)
O operador cadastra ou ajusta previamente os parâmetros:
Custo por grama para cada tipo/cor de filamento
Custo de energia (R$/kWh)
Margem de lucro (%)
Custo hora-máquina (opcional)
Valor fixo de preparação (opcional)
O sistema cruza dados do G-code com valores cadastrados, calcula o orçamento e exibe o total.
O usuário pode imprimir, baixar ou copiar o resumo do orçamento.
Possui também um pequeno fluxo de caixa para controle financeiro.

O operador define previamente:
Custo por grama (por material/cor) -	Base para cálculo do custo do filamento
Custo kWh - 	Usado para calcular o custo energético
Potência média da impressora (W) -	Para estimar consumo elétrico
Margem de lucro (%)	Aplicada sobre o subtotal
Taxas adicionais de serviços (opcional)

# Observação: Ao fazer o upload do GCODE, aguarde as informações serem carregadas.

# Instalação:
Instale o php8, apache e maysql/mariadb
Importe o schema.sql em uma base no mysql ou mariadb.
copie os arquivos para o diretório raiz do apache.

# Telas do sistema:

Parâmetros
<img width="1889" height="901" alt="image" src="https://github.com/user-attachments/assets/e8e38455-cd15-465f-a89a-e6d0270b7b80" />

Dashboard
<img width="1891" height="902" alt="image" src="https://github.com/user-attachments/assets/e611c3ad-9dc3-462a-91c7-938411660cbe" />

Itens do Orçamento
<img width="1879" height="906" alt="image" src="https://github.com/user-attachments/assets/bb4f384c-9587-4265-b1d9-804296c3e065" />

Impressão do orçamento
<img width="1132" height="882" alt="image" src="https://github.com/user-attachments/assets/9331ac46-9fc0-462f-acaf-75ec058e1158" />

Adição de Item (GCODE)
<img width="487" height="870" alt="image" src="https://github.com/user-attachments/assets/fa6ab1af-50ed-4e20-9828-5bd333da25cf" />

Financeiro (Fluxo de Caixa simples)
<img width="1884" height="883" alt="image" src="https://github.com/user-attachments/assets/3ccef4bd-f87e-459b-b82e-b02cd80c98f0" />


