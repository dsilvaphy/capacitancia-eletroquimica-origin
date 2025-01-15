# 🔬 Cálculo de Capacitância Eletroquímica com Origin

Este repositório contém um script e um arquivo de projeto do Origin (`opj`) desenvolvido para análise de dados de experimentos eletroquímicos. O objetivo principal é processar dados de impedância, calcular propriedades físicas como a capacitância e organizar os resultados em planilhas automáticas.

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

1. **Configuração Inicial:**
   - Abra o Origin e selecione um novo projeto.
   - Navegue para `File > Open > Templates (*.otm)` e abra o arquivo `gpe_universal` (localizado no diretório do projeto).

2. **Importação de Dados:**
   - Importe os dados de impedância obtidos do Autolab. Certifique-se de que as medições estão ordenadas cronologicamente para manter a consistência.

3. **Plotagem Inicial:**
   - Gere um gráfico de Nyquist (log-log) para determinar os valores precisos de:
     - **Resistência do eletrólito (`Re`)**.
     - **Resistência de transferência de carga (`Rt`)**. Use a fórmula: `Rt = (1000 - Re) * 2` (dependendo do caso experimental).
    
<div align="center">
 <img src="https://github.com/dsilvaphy/capacitancia-eletroquimica-origin/blob/main/capturas/Imagem1.png" width="250" height="200">
</div>

4. **Carregue o Script no Origin:**
   - Abra o script `kapparho.txt` no editor de texto do Origin.
   - Copie o conteúdo e cole na janela de comandos do Origin.
  
<div align="center">
 <img src="https://github.com/dsilvaphy/capacitancia-eletroquimica-origin/blob/main/capturas/Imagem2.png" width="750" height="200">
</div>


5. **Atualize os Parâmetros no Script:**
   - Ajuste os seguintes valores de acordo com os dados experimentais:
     - `NScan`: Número de scans realizados.
     - `NFreq`: Número total de frequências.
     - `Vinicial` e `passoV` para representar os potenciais iniciais e incrementos.
   - Habilite a subrotina desejada (por exemplo, `area` ou `freq`) removendo os comentários (`//`).
  
<div align="center">
 <img src="https://github.com/dsilvaphy/capacitancia-eletroquimica-origin/blob/main/capturas/Imagem3.png" width="750" height="200">
</div>


6. **Atualização dos Valores na Subrotina `area`:**
   - Insira os valores de `Re`, `Rt` e área do eletrodo diretamente na subrotina `area`:
     ```
     col(A)[1] = 14.65; // Re: resistência do eletrólito
     col(A)[2] = 2000;  // Rt: resistência de transferência de carga
     col(A)[3] = 1.131; // Área do eletrodo em cm²
     ```

<div align="center">
 <img src="https://github.com/dsilvaphy/capacitancia-eletroquimica-origin/blob/main/capturas/Imagem4.png" width="750" height="250">
</div>


7. **Execução do Script:**
   - Salve o script como uma Custom Routine e clique no botão de execução no Origin.
   - Verifique se os dados nas colunas foram devidamente atualizados.
  
<div align="center">
 <img src="https://github.com/dsilvaphy/capacitancia-eletroquimica-origin/blob/main/buttom_custom.png" width="90" height="90">
</div>


8. **Extração por Frequências:**
   - Para extrair os dados relevantes de cada frequência:
     - Habilite a subrotina `freq` no script.
     - Verifique que ela calcula automaticamente `1/C_eff²` e `1/C_gpe²`, necessários para gráficos de Mott-Schottky.
    

<div align="center">
 <img src="https://github.com/dsilvaphy/capacitancia-eletroquimica-origin/blob/main/capturas/Imagem7.png" width="750" height="250">
</div>


9. **Renomeação de Planilhas:**
   - Habilite a subrotina `rename` para organizar e renomear as planilhas com base na frequência analisada.

<div align="center">
 <img src="https://github.com/dsilvaphy/capacitancia-eletroquimica-origin/blob/main/capturas/Imagem8.png" width="750" height="250">
</div>


10. **Verificação Final:**
    - Certifique-se de que as planilhas e gráficos estão atualizados e organizados corretamente.
   
<div align="center">
 <img src="https://github.com/dsilvaphy/capacitancia-eletroquimica-origin/blob/main/capturas/Imagem5.png" width="750" height="250">
</div>

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


