# Projeto Redes sem Fio — Transmissão via Satélite (GEO)

Repositório do trabalho da disciplina "UFABC - Redes sem Fio" (Prof. Dr. Carlo Kleber). Contém um notebook com análises e simulações de um enlace GEO: latência, orçamento de enlace (FSPL, SNR, Eb/N0), BER teórica (BPSK em AWGN), jitter (simulado) e um modelo simples de custo. Inclui também um arquivo KMZ de cobertura VHF (136–144 MHz) usado como recurso adicional.

## Conteúdo

- `Artigo_Redes-Sem-Fio.pdf`: artigo desenvolvido abordando os conceitos teóricos e práticos relacionados ao projeto.
- `Projeto_RedesSemFio.ipynb`: notebook principal com os cálculos, simulações e gráficos.
- `requirements.txt`: dependências mínimas para execução do notebook.
- `cobertura_VHF_136-144MHz.kmz`: camada de cobertura VHF (recurso complementar).

## Objetivos do notebook

- Calcular automaticamente a distância estação–satélite (slant range) em função da elevação.
- Estimar latências: one-way, RTT e impacto de processamento.
- Realizar orçamento de enlace: `FSPL`, `P_rx`, `SNR`, `Eb/N0` e `BER` (BPSK/AWGN).
- Simular jitter e latência média sob variabilidade de fila/atrasos extras.
- Avaliar custo mensal por um modelo simples parametrizável.

## Experimentos implementados

1. Efeito da elevação do satélite: distância, atraso, FSPL e Eb/N0 vs. elevação.
2. Trade-off taxa de bits (Rb) vs. Eb/N0 e BER.
3. Impacto de perdas adicionais (ex.: chuva) em SNR, Eb/N0 e BER.

Os gráficos são salvos como arquivos PDF na pasta `plots` ao executar as células correspondentes.

## Como executar

Requer Python 3.13+ (testado) e ambiente virtual recomendado.

```zsh
# 1) Opcional: criar e ativar ambiente virtual
python -m venv .venv
source .venv/bin/activate

# 2) Instalar dependências
pip install -r requirements.txt

# 3) Abrir o notebook no VS Code/Jupyter e executar as células
code Projeto_RedesSemFio.ipynb
# ou
jupyter notebook Projeto_RedesSemFio.ipynb
```

## Autores

- Adinan Alves de Brito Filho — RA 11201920527
- Bruno Melati Kuvasney — RA 11202021334
- Fernando Hsiao — RA 11202231201
- Gustavo Diogo Silva — RA 11201920321
- Marcos Vinicius Mira — RA 11201721404
- Vitor Marques Rodrigues — RA 11201722723

## Observações

- Ajuste parâmetros no construtor `GeoSatelliteLink(...)` para comparar cenários (ganhos de antena, potência, perdas extras, temperatura de ruído, taxa de bits, etc.).
- O arquivo KMZ é um recurso independente do notebook principal e pode ser aberto em ferramentas GIS/Google Earth.
