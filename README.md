# ⚡ Challenge Sprint I — Análise de Recarga em Eletroposto

## 📌 Descrição do problema

Uma plataforma monitora e controla a potência elétrica entregue a veículos em um eletroposto comercial.  
A potência instantânea (em kW) é modelada por:

\[
P(t) = 18 + \frac{24t}{t+2}, \quad t \ge 0
\]

onde:
- \(t\) representa o tempo em minutos desde o início da recarga.

---

# 📊 1. Gráfico da função

A função foi implementada em Python usando NumPy e Matplotlib para gerar o gráfico de \(P(t)\) ao longo do tempo.

### Código base:
```python
t = np.linspace(0.0001, 50, 500)
P = 18 + (24*t)/(t+2)
plt.plot(t, P)
