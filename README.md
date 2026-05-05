# Challenge Sprint I — Análise de Recarga em Eletroposto

## Integrantes

| Nome                       | RM     |
| -------------------------- | ------ |
| Luca Almeida Lucareli      | 569061 |
| Leonardo Scotti Tobias     | 573305 |
| Henrique Almeida Lucareli  | 569183 |
| Natan Silva da Costa       | 573100 |
| Enzo Seiji Delgado Tabuchi | 573156 |

## Descrição do problema

Uma plataforma monitora e controla a potência elétrica entregue a veículos em um eletroposto comercial.  
A potência instantânea (em kW) é modelada por:

P(t) = 18 + (24t)/(t+2), t = 0

onde:
- \(t\) representa o tempo em minutos desde o início da recarga.

---

# 1. Gráfico da função

A função foi implementada em Python usando NumPy e Matplotlib para gerar o gráfico de \(P(t)\) ao longo do tempo.

### Código base:
```python
t = np.linspace(0.0001, 50, 500)
P = 18 + (24*t)/(t+2)
plt.plot(t, P)
```

# Comportamento observado

- Crescimento rápido no início  
- Tendência de estabilização  
- Assíntota horizontal em torno de **42 kW**

---

# 2. Limites da função

###  Quando (t 0+):

P(t) ~= 18

 A recarga inicia com aproximadamente **18 kW**

---

###  Quando (t infinito):

P(t) ~= 42

 A potência se estabiliza em aproximadamente **42 kW**

---

#  Interpretação

O sistema apresenta comportamento de saturação:

- crescimento inicial rápido  
- depois estabilização  
- limite físico de potência do carregador  

---

#  3. Variação média (t = 1 a t = 3)

VM = (P(3) - P(1)) / (3 - 1)= 3.2 KW/min

###  Interpretação

- A potência aumenta em média **3.2 kW por minuto**
- O sistema ainda está em fase de aceleração
- Importante para planejamento da demanda energética

---

# 4. Derivada da função

P'(t) = (24(t+2) - 24t) / (t+2)^2 = 48 / (t+2)^2

###  Significado físico

A derivada representa:

- a taxa de variação instantânea da potência  
- mede a velocidade de crescimento da recarga  
- unidade: kW/min  

---

#  5. Comparação P'(1) e P'(6)

### Resultados:
- P'(1) = 5.33
- P'(6) = 0.75

###  Interpretação:

- no início: crescimento rápido  
- depois: crescimento lento  

 O sistema desacelera com o tempo

---

#  6. Crescimento e comportamento da função

Como:

P′(t) t>0 ∀ t≥0 

###  Conclusão:

- a função é sempre crescente  
- nunca ocorre diminuição da potência  
- apenas estabilização  

---

#  7. Gráfico de P'(t)

```python
dP = 48 / (t + 2)**2
plt.plot(t, dP, color="green")
```

#  Comportamento da derivada

- alto no início  
- decresce continuamente  
- tende a zero  

---

#  Conclusão geral

- início com 18 kW  
- crescimento rápido inicial  
- estabilização em 42 kW  
- taxa de crescimento decrescente  
- ausência de queda de potência  

---

#  Tecnologias utilizadas

- Python  
- NumPy  
- Matplotlib  

---

#  Resultado final

- **P(t):** curva crescente com saturação  
- **P'(t):** curva decrescente tendendo a zero  
