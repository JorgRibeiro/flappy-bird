# 🐦 Flappy Bird com IA (NEAT)

Um clone do clássico jogo Flappy Bird desenvolvido em Python com Pygame, onde uma inteligência artificial aprende a jogar usando o algoritmo **NEAT** (NeuroEvolution of Augmenting Topologies).

## 📋 Sobre o Projeto

Este projeto implementa o famoso jogo Flappy Bird e utiliza algoritmos genéticos para treinar uma rede neural que aprende a jogar automaticamente. A IA evolui ao longo de várias gerações, melhorando sua performance até conseguir jogar perfeitamente.

### 🎮 Características

- **Modo IA**: Assista a IA aprender e evoluir através de múltiplas gerações
- **Modo Manual**: Jogue você mesmo pressionando a barra de espaço
- **Visualização em tempo real**: Acompanhe a pontuação e geração atual
- **Evolução genética**: Utiliza NEAT para evoluir redes neurais

## 🛠️ Tecnologias Utilizadas

- **Python 3.x**
- **Pygame**: Renderização gráfica e gerenciamento do jogo
- **NEAT-Python**: Implementação do algoritmo NEAT para evolução de redes neurais

## 📦 Instalação

1. Clone este repositório:
```bash
git clone https://github.com/JorgRibeiro/flappy-bird.git
cd flappy-bird
```

2. Instale as dependências necessárias:
```bash
pip install pygame neat-python
```

## 🚀 Como Usar

### Modo IA (Padrão)
Execute o arquivo principal para treinar a IA:
```bash
python FlappyBird.py
```

A IA começará a treinar automaticamente, e você verá:
- Múltiplos pássaros aprendendo simultaneamente
- Contador de geração no canto superior esquerdo
- Pontuação atual

### Modo Manual
Para jogar manualmente, altere a variável no início do código:
```python
ai_jogando = False
```

Depois execute:
```bash
python FlappyBird.py
```

Controles:
- **Espaço**: Pular

## 🧠 Como Funciona a IA

### Entradas da Rede Neural (3 inputs)
1. **Posição Y do pássaro**: Altura atual do pássaro na tela
2. **Distância até o cano**: Distância vertical entre o pássaro e o topo do próximo cano
3. **Altura do cano**: Posição da abertura do próximo cano

### Saída da Rede Neural (1 output)
- **Decisão de pular**: Se o valor for > 0.5, o pássaro pula

### Sistema de Fitness
- **+0.1**: Por cada frame que o pássaro permanece vivo
- **+5**: Por cada cano ultrapassado com sucesso
- **-1**: Por colidir com um cano

### Evolução
- **População**: 100 pássaros por geração
- **Gerações**: Evolui por até 50 gerações (configurável)
- **Objetivo**: Atingir pontuação de 1000 pontos

## ⚙️ Configuração

Os parâmetros do algoritmo NEAT podem ser ajustados em `config.txt`. Para entender cada parâmetro, consulte `config_explain.txt`, que contém explicações detalhadas em português de cada configuração.

### Principais Configurações

- **pop_size**: Tamanho da população (100 pássaros)
- **fitness_threshold**: Meta de pontuação (1000 pontos)
- **activation_default**: Função de ativação (tanh)
- **num_inputs**: Número de entradas (3)
- **num_outputs**: Número de saídas (1)

## 📁 Estrutura do Projeto

```
flappy-bird/
├── FlappyBird.py          # Código principal do jogo e IA
├── config.txt             # Configurações do NEAT
├── config_explain.txt     # Explicações das configurações
├── README.md              # Este arquivo
└── imgs/                  # Recursos gráficos
    ├── bird1.png
    ├── bird2.png
    ├── bird3.png
    ├── pipe.png
    ├── base.png
    └── bg.png
```

## 🎯 Resultados Esperados

Após algumas gerações, a IA aprenderá a:
- Evitar canos com precisão
- Manter altura ideal
- Sobreviver indefinidamente
- Atingir pontuações muito altas

## 📝 Licença

Este projeto é de código aberto e está disponível para fins educacionais.

## 👤 Autor

**Jorge Ribeiro**
- GitHub: [@JorgRibeiro](https://github.com/JorgRibeiro)

## 🤝 Contribuições

Contribuições, issues e pedidos de features são bem-vindos!

---

⭐ Se este projeto te ajudou, considere dar uma estrela!