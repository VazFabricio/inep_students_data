# Microdados do Censo Escolar da Educação Básica 2025 (Versão 2)

Este repositório contém os microdados oficiais do **Censo Escolar da Educação Básica de 2025**, publicados pelo **INEP / Ministério da Educação** em julho de 2026 (Versão 2), acompanhados de documentação técnica, questionários, dicionário de variáveis e um notebook interativo para exploração analítica dos dados.

---

## 📁 Estrutura do Repositório

```text
├── dados/                                            # Arquivos CSV com os microdados e checksums
│   ├── md5_microdados_ed_basica_2025.txt            # Hashes MD5 para garantia de integridade
│   ├── Tabela_Escola_2025_V2.csv                    # Cadastro e infraestrutura das escolas
│   ├── Tabela_Matricula_2025_V2.csv                 # Matrículas por etapa, turno e demografia
│   ├── Tabela_Docente_2025_V2.csv                   # Quantitativo docente e titulação
│   ├── Tabela_Turma_2025_V2.csv                     # Turmas, etapas e modalidades
│   ├── Tabela_Gestor_Escolar_2025_v2.csv            # Perfil do gestor e forma de provimento
│   └── Tabela_Curso_Tecnico_2025_V2.csv             # Oferta de cursos técnicos de nível médio
├── Anexos/
│   ├── ANEXO I - Dicionário de Dados/
│   │   └── dicionário_dados_educação_básica.xlsx   # Dicionário oficial com todas as variáveis
│   └── ANEXO II - Questionários do Censo/          # Questionários aplicados pelo Inep (PDF)
├── leia-me/
│   ├── Leia-me_v2.pdf                              # Manual do usuário oficial do Inep
│   ├── Nota Técnica nº 5 de 2021...pdf             # Recomendações do TED UFMG/Inep
│   ├── Parecer Jurídico da Projur...pdf             # Parecer sobre divulgação e LGPD
│   ├── RIP Relatório de Impacto...pdf               # Relatório de Impacto à Proteção de Dados
│   └── Termo de Execução Descentralizada (TED)...pdf
└── exploracao_censo_escolar_2025.ipynb             # Notebook Jupyter com análise exploratória completa
```

---

## 🔒 Metodologia e LGPD (Granularidade das Tabelas)

Em atendimento à **Lei nº 12.527/2011 (LAI)** e à **Lei nº 13.709/2018 (LGPD)**, os Microdados são estruturados no nível de **estabelecimento de ensino**:
- **Chave primária de integração:** `CO_ENTIDADE` (Código Inep da Escola).
- Permite o relacionamento relacional direto entre todas as bases (`Escola`, `Matrícula`, `Docente`, `Turma`, `Gestor` e `Curso Técnico`).
- **Formato dos arquivos:** CSV delimitado por ponto e vírgula (`;`), codificação `latin1` (ISO-8859-1).

---

## 📊 Resumo das Bases de Dados

| Tabela | Linhas | Colunas | Escopo Principal |
| :--- | :---: | :---: | :--- |
| `Tabela_Escola_2025_V2.csv` | 214.192 | 290 | Cadastro escolar, dependência, localização, infraestrutura e conectividade. (180.540 em atividade) |
| `Tabela_Matricula_2025_V2.csv` | 178.766 | 263 | 46.018.380 matrículas da Educação Básica por etapa, gênero, cor/raça, tempo integral e Educação Especial (2.458.159 alunos com deficiência/TEA/altas habilidades, 93,5% em classes comuns). |
| `Tabela_Docente_2025_V2.csv` | 178.772 | 184 | 2.992.045 funções docentes na Educação Básica, formação superior (89,2%) e pós-graduação (51,6%). |
| `Tabela_Turma_2025_V2.csv` | 178.772 | 218 | 2.233.976 turmas registradas (média de 20,6 alunos por turma no país). |
| `Tabela_Gestor_Escolar_2025_v2.csv` | 180.540 | 88 | Diretores escolares: gênero, raça, escolaridade e formas de acesso (indicação, concurso, eleição). |
| `Tabela_Curso_Tecnico_2025_V2.csv` | 32.136 | 49 | Cursos técnicos de nível médio (Administração, Enfermagem e Informática lideram). |

---

### 🌟 Destaques do Notebook: Educação Especial e Inclusão Escolar
A Seção 6 do notebook [`exploracao_censo_escolar_2025.ipynb`](./exploracao_censo_escolar_2025.ipynb) traz uma análise aprofundada:
- **Metodologia de Coleta vs. Disseminação (LGPD)**: Esclarece o tratamento dos dados sensíveis de saúde coletados no questionário de aluno (*Cegueira, Baixa Visão, Surdez, Deficiência Auditiva, Surdocegueira, Deficiência Física, Deficiência Intelectual, Deficiência Múltipla, TEA, Altas Habilidades/Superdotação e Transtornos de Aprendizagem*) e consolidados nos microdados públicos em `QT_MAT_ESP`.
- **Panorama Geral da Inclusão**: 2.458.159 estudantes da Educação Especial, dos quais 2.298.005 (93,5%) estão incluídos em Classes Comuns e 160.154 (6,5%) em Classes Exclusivas.
- **Estratificação por Nível de Ensino**: Detalhamento completo do volume e das taxas de inclusão da Creche à EJA e Ensino Profissional.
- **Acessibilidade Escolar**: Cobertura de Salas de Recursos Multifuncionais (AEE), profissionais tradutores de Libras, revisores de Braille e acessibilidade arquitetônica.


---

## 🚀 Como Executar o Notebook

O arquivo [`exploracao_censo_escolar_2025.ipynb`](./exploracao_censo_escolar_2025.ipynb) já está pré-executado com todos os gráficos e tabelas renderizados.

Para executá-lo novamente em seu ambiente local:

```bash
# Instalação dos requisitos recomendados
pip install pandas numpy matplotlib seaborn openpyxl nbformat
```

Abra o arquivo diretamente no VS Code / Antigravity IDE ou via Jupyter Notebook:
```bash
jupyter notebook exploracao_censo_escolar_2025.ipynb
```
