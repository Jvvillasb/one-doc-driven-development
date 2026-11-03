---
odd: "1.0"
id: ODD-0000
titulo: "<nome curto do pedido>"
status: rascunho        # rascunho | em-chancela | aprovado | aplicado | conferido | recusado
risco: "?"              # baixo | medio | alto  (a IA sugere, o Guardião TI confirma)
solicitante: "<seu nome>"
gestor: "<nome do gestor>"
guardiao_ti: "<nome do guardião de TI>"
criado_em: AAAA-MM-DD
---

# <Título do pedido>

> **ODD — One-Doc Driven Development.** Um pedido, um arquivo. Sem chancela, sem apply.

---

## 1. Pedido ✍️
*Quem escreve: **você**. Use palavras do dia a dia; não precisa saber nada de tecnologia.*

**1.1 O que você quer?**
<Ex.: "Quero um lugar onde a equipe marque as férias e eu veja quem está fora em cada semana.">

**1.2 Por que isso importa? Que problema resolve?**
<Ex.: "Hoje é numa planilha que ninguém atualiza e já tivemos duas pessoas de férias ao mesmo tempo.">

**1.3 Quem vai usar?**
<Ex.: "Os 8 analistas da equipe e eu, como gestora.">

**1.4 Como você vai saber que deu certo?**
<Dê 2 ou 3 exemplos concretos. Ex.: "Se eu marcar férias de 10 a 20/01 e a Ana já estiver fora nesse período, aparece um aviso.">

**1.5 O que NÃO pode acontecer?**
<Dados que não podem vazar, sistemas que não podem ser mexidos, prazo, orçamento.>

---

## 2. Proposta 🤖
*Quem escreve: **a IA**, a partir do Pedido. Não edite à mão; se algo estiver errado, ajuste o Pedido e peça uma nova versão.*

### 2.1 Resumo em uma frase
<…>

### 2.2 Escopo
- **Faz:** <…>
- **Não faz:** <…>

### 2.3 Critérios de aceite
- [ ] Dado <situação>, quando <ação>, então <resultado esperado>.
- [ ] <…>

### 2.4 Como vai funcionar (em linguagem simples)
<O que a pessoa vê e faz, passo a passo. Detalhes técnicos só no fim e em poucas linhas.>

### 2.5 Riscos e cuidados
| Tema | Avaliação | Observação |
|---|---|---|
| Dados pessoais ou sensíveis | <não / sim> | <…> |
| Acesso e segurança | <…> | <…> |
| Custo (licenças, nuvem, APIs) | <…> | <…> |
| Integração com outros sistemas | <…> | <…> |

**Risco sugerido:** <baixo / médio / alto>, porque <…>

### 2.6 Plano de execução (o roteiro que a IA vai seguir no apply)
1. <…>
2. <…>

### 2.7 Dúvidas em aberto
- <Pergunta que o solicitante, o gestor ou o Guardião TI precisa responder antes do apply. Se não houver nenhuma, escreva "Nenhuma".>

---

## 3. Chancela ✅
*Quem preenche: **o gestor e o Guardião TI**. O apply só acontece com as duas aprovações e nenhuma dúvida em aberto.*

| Papel | Nome | Decisão (aprovado / ajustar / recusado) | Data | Comentário |
|---|---|---|---|---|
| Gestor (o "o quê") | | | | |
| Guardião TI (o "risco") | | | | |

---

## 4. Registro do Apply 🛠️
*Quem preenche: **a IA**, ao final da execução.*

- **Data:** <…>
- **O que foi feito:** <…>
- **Onde está:** <repositório, branch, link>
- **Como testar:** <passo a passo>
- **Desvios do plano:** <nenhum, ou o que mudou e por quê>

---

## 5. Conferência 🔍
*Quem preenche: **o solicitante**.*

- [ ] Testei cada critério de aceite da seção 2.3
- **Resultado:** <conferido / precisa de ajuste>
- **Observações:** <…>
