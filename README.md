# Pipeline de Último Preço de Compras

Este projeto processa dados históricos de pedidos de compra da **Fundação Butantan** e gera um relatório consolidado com o **último preço de compra de cada material**, incluindo conversão para **BRL (Real)** quando necessário.

Além disso, o relatório em Excel é entregue pronto para análise

---

## 🔎 O que o projeto faz

1. Lê os dados de pedidos fornecidos em CSV (cabeçalho e itens).
2. Identifica a **última compra de cada material**, considerando a data do pedido.
3. Para compras em moedas estrangeiras, consulta a **API do Banco Central** para obter a cotação e converter para BRL.
4. Gera um relatório final em **CSV e Excel** contendo:
    - Código do material
    - Último preço de compra em BRL
    - Último preço sem conversão
    - Moeda original do pedido
    - Data da última compra
    - Código do pedido de referência
    - Data da cotação utilizada (quando aplicável)
5. O relatório Excel inclui:
    - **Filtros automáticos**
    - **Cabeçalho congelado**
    - **Valores formatados como moeda (BRL)**

---

## ⚙️ Como rodar

1. Clonar o repositório:

```bash
git clone <https://github.com/Leticia0587/pipeline-relatorio-compras.git>
cd pipeline_ult_precos

```

1. Instalar dependências:

```bash
pip install -r requirements.txt

```

1. Executar o pipeline:

```bash
python src/pipeline_ult_precos.py

```

1. O relatório final será gerado em:
- `relatorios/relatorio_final.csv`
- `relatorios/relatorio_final.xlsx`

---

## 🛠️ Decisões técnicas

- Implementação em **um único script** organizado em funções para clareza e fácil execução.
- Uso de bibliotecas amplamente utilizadas:
    - `pandas` → manipulação de dados
    - `requests` → integração com API do Banco Central
    - `openpyxl` → geração do Excel com gráfico e formatação
- Consulta à API do Banco Central feita **apenas quando necessário**, evitando chamadas repetidas.
- Relatório final pensado para ser **apresentável, direto e de fácil análise**.

---

## 📂 Estrutura do projeto

```
pipeline_ult_precos/
│── src/
│   └── pipeline_ult_precos.py   # Script principal
│── relatorios/                  # Saída dos relatórios
│── requirements.txt             # Dependências
│── README.md                    # Documentação

```

---

## ✅ Observações finais

- Compras realizadas em **BRL** mantêm o valor original.
- Datas das cotações são registradas no relatório para rastreabilidade.
- O pipeline foi desenvolvido para ser **funcional, legível e apresentável**, permitindo que o avaliador veja o resultado imediatamente.