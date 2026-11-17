# ProjectConcurso

Plataforma pessoal de estudos diários para concursos de TI, configurada para o perfil **Matheus Goes**, com foco inicial no edital **FADE/UFPE (Edital nº 10/2023 — Analista de TI: Datacenter, Infraestrutura e Redes)** e uso contínuo em **PC** e **Samsung Galaxy S23 FE**.

---

## Estrutura do Projeto

- `index.html` — Aplicação web completa em arquivo único (HTML + CSS responsivo + JavaScript + banco de 80 questões).
- `manifest.json` — Manifesto PWA para instalação na tela inicial do celular quando hospedado via HTTPS.
- `README.md` — Documentação de arquitetura, manutenção e evolução.

---

## Funcionalidades Implementadas

1. **Menu Principal sem Login (`Provas`):**
   - Saudação fixa (`Matheus Goes`) e contagem regressiva sutil até a data da prova no cabeçalho (editável ao clicar).
   - **Meta Diária de 50 questões** com barra de progresso, ofensiva (`🔥 Xd`) e salvamento automático a cada resposta/segundo.
   - **Retomada de Sessão (`Continuar`):** se sair no meio do treino, o estado fica salvo até concluir.
   - **Modelos de Provas Diárias:**
     - **Modelo A (Rotina Equilibrada — 50q):** 28 Infra/Redes + 12 Português + 6 Legislação + 4 Raciocínio Lógico.
     - **Modelo B (Foco Técnico + Leis — 50q):** 35 Infra/Redes + 10 Legislação + 5 Raciocínio Lógico.
     - **Modelo C (Caderno de Erros):** revisa automaticamente as questões erradas no histórico.
     - **Modelo D (Bloco Express — 25q):** treino rápido para o celular.
   - **Prova Completa (80 questões)** no padrão oficial UFPE/FADE:
     - 20 Língua Portuguesa
     - 5 Raciocínio Lógico
     - 10 Legislação Aplicada ao Servidor
     - 45 Conhecimentos Específicos (Datacenter, Infraestrutura e Redes)
   - **Treino por Assunto** para reforço direcionado.

2. **Sessão de Prova (`Modo Sessão`):**
   - Correção imediata ao clicar na alternativa com bloco **Por que você errou** (quando incorreta) + **Gabarito comentado** + atalho **Entender este assunto**.
   - Cronômetro aberto (sem penalização) registrando tempo total da sessão e tempo individual por questão.
   - Cartão-Resposta interativo + marcação para revisão (`⚐ Revisar`) + **Modo Escuro (`🌙` / `☀️`)**.

3. **Guia de Assuntos (`Assuntos`):**
   - Resumos didáticos pesquisáveis de todas as disciplinas com dicas de prova e botão direto para treinar.

3. **Histórico Diário (`Histórico Diário`):**
   - Agrupamento por data (`YYYY-MM-DD`) com total de questões, % de acertos, tempo total, tempo médio/questão, resumo por disciplina e lista detalhada questão a questão.
   - **Exportar / Importar Backup (`.json`)** para transferência manual entre PC e celular.

4. **Desempenho Semanal (`Desempenho Semanal`):**
   - Percentual de acertos na semana (Seg–Dom), gráfico diário e barras de aproveitamento por assunto.

5. **Dicas de Evolução (`Dicas de Evolução`):**
   - Diagnóstico automático baseado na taxa de acerto semanal, disciplina mais fraca e tempo médio por questão.

---

## Como Dar Manutenção

### 1. Adicionar ou editar questões
No arquivo `index.html`, localize o array `const quizData = [...]`. Cada questão segue o formato:

```js
{
    subject: "Conhecimentos Específicos", // "Língua Portuguesa" | "Raciocínio Lógico" | "Legislação" | "Conhecimentos Específicos"
    q: "(FADE/UFPE - Assunto) Enunciado da questão...",
    options: [
        "A) Opção 1",
        "B) Opção 2",
        "C) Opção 3",
        "D) Opção 4",
        "E) Opção 5"
    ],
    answer: 0, // Índice da alternativa correta (0=A, 1=B, 2=C, 3=D, 4=E)
    summary: "Resumo explicativo exibido após a resposta."
}
```

### 2. Estrutura de Persistência (`localStorage`)
Chave utilizada: `ufpe_study_matheus_v1`

```json
{
  "examDate": "2026-12-20",
  "activeSession": null,
  "dailyHistory": {
    "2026-11-17": {
      "totalTimeSec": 1800,
      "questions": [
        {
          "qIndex": 0,
          "subject": "Língua Portuguesa",
          "correct": true,
          "timeSec": 35,
          "answeredAt": "2026-11-17T15:30:00.000Z"
        }
      ]
    }
  }
}
```

---

## Próximos Passos Recomendados (Roadmap)

1. **Hospedagem Gratuita (Link único PC + S23 FE):** Publicar a pasta `ProjectConcurso` no **GitHub Pages**, **Vercel** ou **Netlify** para acessar via HTTPS e instalar como app no S23 FE.
2. **Sincronização em Nuvem (Histórico igual no PC e no S23 FE):** Integrar **Supabase** ou **Firebase Firestore** usando chave fixa `matheus_goes` (substituindo a necessidade de exportar/importar JSON).
3. **Modo Escuro (Dark Mode):** Adicionar alternância de tema claro/escuro para leitura noturna no celular.
4. **Expansão do Banco de Questões:** Separar `quizData` em arquivos JSON por banca/edital conforme o banco crescer além de 200+ questões.
