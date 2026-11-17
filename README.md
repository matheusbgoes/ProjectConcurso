# ProjectConcurso

Plataforma gratuita, simples e **beginner-friendly** para qualquer pessoa estudar diariamente para **qualquer concurso público, certificação ou prova**, no **computador** ou em **qualquer celular (Android ou iOS)**.

> Criado por **Matheus Goes** — pronto para usar direto no navegador, sem precisar de login ou instalação complexa.

---

## Para quem é este projeto?

- **Iniciantes e concurseiros de qualquer área:** Já vem pronto com um **simulado modelo completo (80 questões)** e guia de assuntos, mas permite **trocar por completo o concurso, as matérias, a meta diária e as questões** em poucos cliques.
- **Uso no celular ou PC:** Layout responsivo com barra inferior no celular (ideal para estudar no ônibus, intervalo ou em casa) e cartão-resposta lateral no computador.
- **Customização com Agente de IA:** Possui um gerador integrado de prompt para IA — você informa qual prova vai fazer, os assuntos que precisa estudar e quanto tempo tem até o dia da prova, e a IA gera um pacote `.json` personalizado para importar direto no app.

---

## Principais Funcionalidades

1. **Configuração Fácil (`⚙️ Meu Concurso`):**
   - Personalize seu **nome**, o **nome da prova/concurso**, a **data da prova** (com contagem regressiva sutil no topo) e a **meta diária de questões** (ex.: 20, 30, 50...).
   - **Trocar Concurso por Completo:** Importe um pacote `.json` com novas questões e novos resumos de assuntos, ou restaure o pacote modelo inicial quando quiser.
   - **Assistente IA Integrado:** Gere um prompt pronto para pedir ao ChatGPT, Gemini, Claude ou outro agente de IA montar questões e explicações sob medida para o seu edital e prazo.

2. **Provas, Modelos Diários e Retomada Automática:**
   - **Meta Diária configurável** (padrão inicial: 50 questões/dia) com contador de sequência de dias (`🔥`) e salvamento automático a cada clique.
   - **Modelos de Provas Diárias:** *Rotina Equilibrada*, *Bloco Express (25 questões)*, *Caderno de Erros* (revisa automaticamente o que você errou), *Prova Completa* e *Treinos por Disciplina* (gerados dinamicamente a partir das matérias do pacote ativo).

3. **Correção Imediata + Explicação do Erro:**
   - Ao errar uma alternativa, o sistema mostra o bloco **Por que você errou**, o **Gabarito comentado** e um botão direto para **Entender este assunto**.
   - Cronômetro aberto (sem pressão ou bloqueio) registrando o tempo total e o tempo gasto em cada questão.

4. **Guia de Assuntos (`Assuntos`):**
   - Resumos didáticos e pesquisáveis por palavra-chave e disciplina, com dicas de prova e botão para treinar o tema na hora.

5. **Histórico Diário, Desempenho Semanal e Dicas:**
   - Histórico dia a dia por assunto, detalhamento questão a questão e **Exportar / Importar Backup (`.json`)** para transferir seu progresso entre celular e PC.
   - Gráfico semanal de constância e percentual de acertos por disciplina.
   - Diagnóstico automático + plano progressivo de estudo na aba **Dicas de Evolução**.

---

## Como Começar (Passo a Passo)

1. Acesse o link do projeto (ou abra o arquivo `index.html` no navegador do seu computador ou celular).
2. Clique em **⚙️ Meu Concurso** no topo para colocar seu nome, o concurso que vai prestar, a data da prova e sua meta diária.
3. Quer estudar para outra prova? Na mesma janela, use a aba **Trocar Concurso (IA)** para gerar o prompt com suas matérias e prazo, peça à sua IA gerar o `.json` e clique em **Importar Pacote (.json)**.
4. No celular (Android ou iOS), toque em **"Adicionar à tela inicial"** no navegador para usar como aplicativo.

---

## Estrutura do Pacote de Concurso (`.json`)

Para trocar todo o conteúdo do **ProjectConcurso**, o arquivo `.json` segue este formato simples:

```json
{
  "examName": "Nome do Concurso ou Prova",
  "questions": [
    {
      "subject": "Nome da Matéria",
      "q": "Enunciado da questão...",
      "options": [
        "A) Alternativa A",
        "B) Alternativa B",
        "C) Alternativa C",
        "D) Alternativa D",
        "E) Alternativa E"
      ],
      "answer": 0,
      "summary": "Explicação clara do gabarito.",
      "wrongNotes": {
        "1": "Opcional: por que a alternativa B está errada."
      }
    }
  ],
  "topics": [
    {
      "subject": "Nome da Matéria",
      "title": "Título do Assunto",
      "body": "Explicação didática do conteúdo.",
      "tip": "Dica rápida de prova."
    }
  ]
}
```
