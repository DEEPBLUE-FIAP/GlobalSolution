Sistema de Ocorrências ao Vivo
Este é um sistema em Python para simular o monitoramento de ocorrências com diferentes níveis de perigo, incluindo alertas automáticos e funcionalidades de cadastro e login de usuários. É uma aplicação voltada para o estudo e aplicação de algoritmos, uso de dicionários e análise de complexidade com notação O(grande).

Integrantes: 
Fernando Carlos RM558095
Pedro Henrique Silva Batista RM558137
Juan Fuentes Rufino RM55763.

Funcionalidades

CADASTRO E LOGIN
Permite cadastro de usuários com nome e senha (com verificação para não duplicar).

Implementa login seguro, bloqueando múltiplos acessos simultâneos.

Após logado, o usuário pode acessar todas as funcionalidades do sistema.

REGISTRO DE OCORRÊNCIAS
Geração manual de ocorrências, com nível de perigo aleatório.

Geração automática a cada 3 segundos com dados reais de cidades brasileiras via API do IBGE.

NOTIFICAÇÕES DE PERIGO
Ocorrências com nível de perigo 4 ou 5 são destacadas como notificações.

O sistema envia alerta imediato ao usuário para ocorrências com nível 5.

Notificações são apagadas automaticamente após visualização.

VISUALIZAÇÃO DE DADOS
Exibe todas as ocorrências registradas.
Permite ver notificações críticas (nível ≥ 4) e todas as ocorrências já
registradas.


CONCEITOS APLICADOS
Análise de Complexidade (Notação O)
Este projeto aplica conceitos de eficiência algorítmica, com destaque para:

O(n) – Busca linear nos usuários e nas ocorrências.

O(log n) – Busca binária aplicada à lista de notificações ordenadas.

O(1) – Operações diretas com dicionários (inserção, leitura).

BUSCA BINÁRIA
A busca binária é usada para detectar rapidamente ocorrências com nível de perigo 5:


def busca_binaria(ocorrencias_ordenadas: list, nivel_alvo: int) -> int:
    # Retorna o índice da ocorrência com nível alvo, ou -1 se não encontrar
A lista de notificações é previamente ordenada por nível de perigo.

A busca binária retorna de forma eficiente qualquer ocorrência crítica.

Dicionários (JSON)
O sistema armazena dados em arquivos .json, usando dicionários como estrutura principal:
{
  "1234": {
    "local": "Campinas/SP",
    "data": "04/06/2025",
    "nivel_de_perigo": 5
  }
}
Permite acesso rápido e organizado às ocorrências.

A estrutura é simples, fácil de validar e expandir.

Execução do Projeto
Pré-requisitos: Python 3.10 ou superior.

Instalar dependências:
pip install requests #para uso da API

Executar o sistema:
Siga o menu interativo no terminal para:

Cadastrar-se

Fazer login

Registrar ocorrências

Verificar notificações
Verificar todas as ocorrências

Sair do sistema
Estrutura do Projeto
GlobalSolutionQueimada.py
usuarios.json
ocorrencias.json
notificacoes.json
Os arquivos .json são criados automaticamente na primeira execução.

Objetivos Didáticos
Este projeto foi feito com fins educacionais e explora os seguintes tópicos:

Algoritmos (busca binária, ordenação)

Análise de complexidade (O(n), O(log n), O(1))

Estruturas de dados com dicionários

Manipulação de arquivos JSON

Programação concorrente com threading

Requisições HTTP com requests

Interface em terminal com menus interativos