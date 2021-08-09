Neste artigo, vamos fazer uma exploração dos dados do hospital Sírio-Libanês, que requisitou ajuda pra criar um modelo de machine learning que identifique quais pacientes com COVID-19 irão para a UTI e quais não irão para a UTI, lançando um desafio na plataforma de ciência de dados e inteligência artificial, Kaggle.

Primeiramente quem estiver interessado em ver os códigos usados na análise exploratória dos dados e ver como eu trabalhei os dados para obter as respostas acesse o meu notebook por este link []().

# **Quantos pacientes foram para a UTI em cada janela temporal?**

![foto1](https://github.com/tathi-martins/Predict_ICU_for_COVID-19/blob/main/Notebooks/Analise_Exploratoria/Imagens/Captura%20de%20Tela%20(1686).png)

Com o gráfico acima podemos observar que quanto mais o tempo avança, maior a chance de um paciente ir para a UTI, o que intensifica a importância de diagnosticar a severidade da doença o mais breve possível, de prever se um paciente irá para a UTI de forma mais precisa e precoce.



# **Quantos pacientes foram para a UTI e quantos não foram por faixa etária?**

![foto2](https://github.com/tathi-martins/Predict_ICU_for_COVID-19/blob/main/Notebooks/Analise_Exploratoria/Imagens/Captura%20de%20Tela%20(1687).png)

Com este gráfico podemos ver que quanto maior a idade, maior a chance de ir para a UTI. Confirmando o que a comunidade médica e científica diz, que a idade avançada é o fator de risco mais importante para desenvolver a forma grave da COVID-19.



# **Qual a média dos pacientes que foram para a UTI divididos pelo sexo? Será que o sexo do paciente é um fator importante para desenvolver complicações?**

![foto3](https://github.com/tathi-martins/Predict_ICU_for_COVID-19/blob/main/Notebooks/Analise_Exploratoria/Imagens/Captura%20de%20Tela%20(1688).png)



![foto4](https://github.com/tathi-martins/Predict_ICU_for_COVID-19/blob/main/Notebooks/Analise_Exploratoria/Imagens/Captura%20de%20Tela%20(1689).png)



Há mais homens na UTI, mas como o percentual é muito não podemos afirmar se isto é uma observação relevante ou se é apenas uma coincidência que há mais homens internados na UTI neste hospital. Para uma conclusão definitiva precisaríamos de mais dados, vindos de outros hospitais também.



# **Qual foi a média de idade dos pacientes homens e mulheres que foram para a UTI?**

![foto5](https://github.com/tathi-martins/Predict_ICU_for_COVID-19/blob/main/Notebooks/Analise_Exploratoria/Imagens/Captura%20de%20Tela%20(1690).png)

![foto6](https://github.com/tathi-martins/Predict_ICU_for_COVID-19/blob/main/Notebooks/Analise_Exploratoria/Imagens/Captura%20de%20Tela%20(1691).png)

**Contexto:**

- **Gender:**

-- 0 -> Refere-se aos homens;

-- 1 -> Refere-se as mulheres.

- **ICU:**

-- 0 -> Representa os que não foram para a UTI;

-- 1 -> Representa os que foram para a UTI.



![foto7](https://github.com/tathi-martins/Predict_ICU_for_COVID-19/blob/main/Notebooks/Analise_Exploratoria/Imagens/Captura%20de%20Tela%20(1692).png)



Neste gráfico podemos ver que a média de idade de pacientes que foram para a UTI é bem diferente, com a diferença em torno de uma década entre os homens e mulheres. Não sabemos se isso é uma característica relevante ou que se repete em outros hospitais.



# **Qual é o impacto que as comorbidades tem na evolução do quadro clínico do paciente com COVID-19?**



Os especialistas dizem que algumas comorbidades como, hipertensão, diabetes, doenças do sistema cardiovascular, asma, obesidade, entre outras, trazem um impacto negativo sobre os infectados pelo coronavírus. Por isso vamos analisar o tamanho do impacto dessas enfermidades nos pacientes com COVID-19.

![foto8](https://github.com/tathi-martins/Predict_ICU_for_COVID-19/blob/main/Notebooks/Analise_Exploratoria/Imagens/Captura%20de%20Tela%20(1693).png)

**Contexto:**

- **ICU:**

-- 0 -> Representa os que não foram para a UTI;

-- 1 -> Representa os que foram para a UTI.

Ao observamos o gráfico, percebemos que o impacto da DISEASE GROUPING 1 aumenta com a idade do paciente, entre a faixa etária dos mais jovens essa influencia é quase nula, já que apenas na faixa etária dos 30 anos é que vemos pacientes com esta comorbidade que tenham ido para a UTI.



![foto9](https://github.com/tathi-martins/Predict_ICU_for_COVID-19/blob/main/Notebooks/Analise_Exploratoria/Imagens/Captura%20de%20Tela%20(1694).png)

**Contexto:**

- **ICU:**

-- 0 -> Representa os que não foram para a UTI;

-- 1 -> Representa os que foram para a UTI.

A DISEASE GROUPING 2 diferentemente do DISEASE GROUPING 1, parece ter contribuído com o agravamento de pacientes portadores desta comorbidade com idade mais jovem.



![foto10](https://github.com/tathi-martins/Predict_ICU_for_COVID-19/blob/main/Notebooks/Analise_Exploratoria/Imagens/Captura%20de%20Tela%20(1695).png)

**Contexto:**

- **ICU:**

-- 0 -> Representa os que não foram para a UTI;

-- 1 -> Representa os que foram para a UTI.

Portadores desta comorbidade parecem desenvolver complicações sérias de COVID-19, considerando que apenas nas faixas etárias de 70 e 80 anos o número de portadores que não foram para UTI superou o número de portadores que foram para UTI. Por ser uma amostra de dados pequena, não podemos afirmar se isto ocorre em todos os hospitais do Brasil.



![foto11](https://github.com/tathi-martins/Predict_ICU_for_COVID-19/blob/main/Notebooks/Analise_Exploratoria/Imagens/Captura%20de%20Tela%20(1696).png)

**Contexto:**

- **ICU:**

-- 0 -> Representa os que não foram para a UTI;

-- 1 -> Representa os que foram para a UTI.

Outra comorbidade que afeta negativamente os pacientes com COVID-19, levando os portadores a desenvolver a forma mais grave da doença. Quase todos os pacientes portadores desta doença foram para a UTI.



![foto12](https://github.com/tathi-martins/Predict_ICU_for_COVID-19/blob/main/Notebooks/Analise_Exploratoria/Imagens/Captura%20de%20Tela%20(1697).png)

**Contexto:**

- **ICU:**

-- 0 -> Representa os que não foram para a UTI;

-- 1 -> Representa os que foram para a UTI.

A DISEASE GROUPING 5 parece ter mais impacto nos portadores com idade mais avançada.



![foto13](https://github.com/tathi-martins/Predict_ICU_for_COVID-19/blob/main/Notebooks/Analise_Exploratoria/Imagens/Captura%20de%20Tela%20(1698).png)

**Contexto:**

- **ICU:**

-- 0 -> Representa os que não foram para a UTI;

-- 1 -> Representa os que foram para a UTI.

Conseguimos ver um impacto negativo da DISEASE GROUPING 6 em seus portadores, mas parece ser menor do que nas comorbidades que vimos anteriormente.



![foto14](https://github.com/tathi-martins/Predict_ICU_for_COVID-19/blob/main/Notebooks/Analise_Exploratoria/Imagens/Captura%20de%20Tela%20(1699).png)

**Contexto:**

- **ICU:**

-- 0 -> Representa os que não foram para a UTI;

-- 1 -> Representa os que foram para a UTI.

O impacto desta doença parece ser maior nas faixas etárias mais altas, com exceção da faixa dos 20 anos.



![foto15](https://github.com/tathi-martins/Predict_ICU_for_COVID-19/blob/main/Notebooks/Analise_Exploratoria/Imagens/Captura%20de%20Tela%20(1701).png)



# **Conclusão:**

Conseguimos confirmar aquilo que os médicos e especialistas já vinham afirmando, que os pacientes acima de 60 anos são mais suscetíveis a desenvolver a forma mais grave da COVID-19. Outros fatores como algumas comorbidades também possuem um impacto negativo bem significativo em seus portadores, independente da idade, enquanto que outras comorbidades possuiam um impacto maior em pacientes idosos.

Por causa da anonimização de dados, não temos acesso a quais doenças o Grouping Desease ou OTHER representa, mas podemos inferir bastante informação destes dados, a interpretação certamente será mais efetiva e completa se este tipo de análise for usada como uma ferramenta de auxílio de tratamento aos pacientes por um médico, ou outro profissional de saúde, com acesso irrestrito aos dados médicos dos pacientes.