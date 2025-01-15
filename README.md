# 🔬 Cálculo de Propriedades Eletroquímicas com Origin

Este repositório contém um script e um arquivo de projeto do Origin (`opj`) desenvolvido para análise de dados de experimentos eletroquímicos. O objetivo principal é processar dados de impedância, calcular propriedades físicas e organizar os resultados em planilhas automáticas.

---

## 📂 Estrutura do Repositório

### **Arquivos Disponíveis:**
- `kapparho.txt`: O script para automação e processamento de dados no Origin.
- `gpe_universal.opj`: Arquivo do Origin com as planilhas e configurações para executar o script.
- Pasta `capturas`: Contém imagens demonstrativas do uso do script e do projeto no Origin.

---

## 🚀 Funcionalidades do Script

### 🔧 **Configurações Gerais:**
O script permite configurar os seguintes parâmetros principais:
- **Número de Scans de Impedância (`NScan`)**: Define o número de medições realizadas.
- **Número de Frequências (`NFreq`)**: Indica quantas frequências estão disponíveis nos dados experimentais.
- **Frequências a serem Puladas (`pulaFreq`)**: Determina a frequência de amostragem dos dados.
- **Parâmetros de Voltagem:** Inclui o potencial inicial (`Vinicial`) e o passo de potencial (`passoV`).

### 📊 **Subrotinas Disponíveis:**
O script inclui subrotinas para diferentes tipos de processamento e análise:

1. **Subrotina `area`:**
   - Adiciona informações de resistência do eletrólito (`Re`), resistência de transferência de carga (`Rct`) e área do eletrodo nas planilhas KR.

2. **Subrotina `freq`:**
   - Extrai dados relacionados às frequências, como:
     - Capacitância efetiva (`C_eff`)
     - Capacitância de GPE (`C_gpe`)
     - Resolução de impedâncias reais e imaginárias (`Zr`, `-Zi`)
     - Propriedades como Kappa, Rho e Omega.
   - Cria novas planilhas organizadas para cada frequência analisada.

3. **Subrotina `mott`:**
   - Calcula propriedades derivadas:
     - `1/C_eff²`
     - `1/C_gpe²`
   - Insere os valores nas colunas das planilhas apropriadas.

4. **Subrotina `rename`:**
   - Renomeia automaticamente os nomes das planilhas de acordo com a frequência associada, formatando os nomes para facilitar a navegação.

---

## 📖 Como Utilizar

1. **Abra o Arquivo de Projeto no Origin:**
   - Carregue o arquivo `gpe_universal.opj` no Origin.

2. **Carregue os Dados:**
   - Insira seus dados experimentais nas planilhas correspondentes do projeto.

3. **Configure o Script:**
   - Abra o script `kapparho.txt`.
   - Atualize os parâmetros iniciais, como `NScan`, `NFreq`, `Vinicial`, e selecione a subrotina desejada.

4. **Execute o Script:**
   - No Origin, cole o script na janela de comandos e pressione **Enter** para executá-lo.

5. **Visualize os Resultados:**
   - Verifique as planilhas geradas e utilize os dados organizados para análises ou exportações.

---

## 📷 Exemplos e Demonstrações

A pasta `capturas` contém imagens que demonstram:
- Configuração do script no Origin.
- Resultados organizados nas planilhas.
- Processamento de propriedades eletroquímicas, como gráficos de Kappa e Rho.

---

## 🛠️ Tecnologias e Requisitos

- **OriginLab:** Software para processamento e análise de dados científicos.
- **Linguagem de Script do Origin:** Utilizada para automação das tarefas e cálculos.

---

## 📝 Contribuição em Publicação Científica
Este script foi essencial no suporte aos cálculos apresentados no artigo publicado na revista **Electrochimica Acta**:

[Electrochemical impedance spectroscopy study of mixed ionic–electronic conducting membranes: Method for accurate determination of bulk and grain boundary resistances](https://www.sciencedirect.com/science/article/pii/S0013468621010860).

Seus cálculos foram utilizados para determinar propriedades eletroquímicas e gerar os dados analisados no estudo.

---

## 💡 Aplicações
Este script é ideal para pesquisadores e estudantes que trabalham com experimentos eletroquímicos e precisam automatizar cálculos como:
- Capacitância.
- Resistência de transferência de carga.
- Impedância complexa.
- Propriedades dielétricas.

---

## 📄 Licença

Este projeto está licenciado sob a **Creative Commons Attribution-NonCommercial 4.0 International License**. Não é permitido usar o código para fins comerciais.

Veja a licença completa [CC BY-NC 4.0](/creativecommons.org/licenses/by-nc/4.0/deed.pt-br).
