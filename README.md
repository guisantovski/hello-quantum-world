# Hello Quantum World

Repositório de estudos da disciplina de Computação Quântica (USP).

> Este repositório é independente do meu TCC — mantido separado propositalmente, inclusive em termos de ambiente Python, para evitar qualquer conflito de dependências entre os dois projetos.

## Setup do ambiente

Este projeto usa um **ambiente virtual Python (venv)** isolado, para não misturar dependências com outros projetos (como meu TCC) instalados no Python global da máquina.

### 1. Clonar o repositório

```bash
git clone <url-do-repo>
cd "hello quantum world"
```

### 2. Criar e ativar o ambiente virtual

**Windows (PowerShell):**
```powershell
python -m venv venv
venv\Scripts\activate
```

**Linux / macOS:**
```bash
python3 -m venv venv
source venv/bin/activate
```

Quando o ambiente estiver ativo, o terminal deve mostrar `(venv)` no início da linha.

### 3. Instalar as dependências

```bash
pip install -r requirements.txt
```

Ou, para instalar o pacote principal manualmente:

```bash
pip install qiskit-ibm-runtime
```

### 4. Desativar o ambiente (quando terminar)

```bash
deactivate
```

## Por que um venv?

Sem um ambiente virtual, o `pip install` instala pacotes globalmente no sistema, o que pode:
- Misturar dependências de projetos diferentes (ex: versões de `numpy`, `scipy`) no mesmo lugar;
- Causar conflitos difíceis de rastrear entre bibliotecas de projetos não relacionados;
- Dificultar saber quais pacotes pertencem a qual projeto.

Usando um `venv` por repositório, cada projeto tem suas próprias dependências isoladas, sem risco de um afetar o outro.

## Sobre o `.gitignore`

A pasta `venv/` (e outros arquivos gerados localmente, como cache do Python e do Jupyter) **não é versionada** — ela é recriada localmente a partir do `requirements.txt`. Isso mantém o repositório limpo e evita subir milhares de arquivos de ambiente virtual sem querer.

## Estrutura

```
hello-quantum-world/
├── venv/              # ambiente virtual (não versionado)
├── .gitignore
├── requirements.txt
├── README.md
└── ...                # notebooks e scripts da disciplina
```

## Requisitos

- Python 3.11+
- [Qiskit IBM Runtime](https://docs.quantum.ibm.com/) para execução em simuladores/hardware IBM Quantum