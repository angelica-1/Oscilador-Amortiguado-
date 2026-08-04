# Avance 2 — Oscilador Amortiguado (EDO, UIP)

Simulación numérica del modelo de oscilador armónico amortiguado desarrollado
analíticamente en el Avance 1, para el Proyecto Final de Ecuaciones Diferenciales
Ordinarias.

## Contenido

- `Avance2_Oscilador_Amortiguado.ipynb` — notebook con la implementación (RK4
  manual), su validación contra `scipy.integrate.solve_ivp`, los cuatro
  escenarios simulados y la discusión preliminar.
- `requirements.txt` — versiones exactas de las dependencias usadas.

## Cómo ejecutarlo

```bash
python3 -m venv venv
source venv/bin/activate        # En Windows: venv\Scripts\activate
pip install -r requirements.txt
pip install jupyter
jupyter notebook Avance2_Oscilador_Amortiguado.ipynb
```

Luego, en Jupyter: **Kernel → Restart & Run All**. El notebook es determinista
(no usa aleatoriedad), por lo que debe producir siempre los mismos resultados
numéricos y gráficos.

## Escenarios simulados

| Escenario | c [N·s/m] | β [1/s] | Régimen | x₀ [m] | v₀ [m/s] |
|---|---|---|---|---|---|
| A | 2  | 1  | Subamortiguado (β<ω₀)     | 1 | 0 |
| B | 10 | 5  | Crítico (β=ω₀)            | 1 | 0 |
| C | 20 | 10 | Sobreamortiguado (β>ω₀)   | 1 | 0 |
| D | 2  | 1  | Subamortiguado, otra C.I. | 0 | 5 |

Parámetros base: m = 1 kg, k = 25 N/m → ω₀ = 5 rad/s.
