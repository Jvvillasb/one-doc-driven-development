---
odd: "1.0"
id: ODD-0001
titulo: "Controle de férias da equipe"
status: aplicado
risco: medio
solicitante: "Carla Souza"
gestor: "Roberto Lima"
guardiao_ti: "Felipe Andrade"
criado_em: 2026-11-03
---

# Controle de férias da equipe

> **ODD — One-Doc Driven Development.** Um pedido, um arquivo. Sem chancela, sem apply.
> *Exemplo fictício.*

---

## 1. Pedido ✍️

**1.1 O que você quer?**
Um lugar simples onde cada pessoa da equipe marque as férias e eu veja, num calendário, quem está fora em cada semana.

**1.2 Por que isso importa? Que problema resolve?**
Hoje usamos uma planilha que ninguém atualiza. Duas vezes este ano ficamos com duas pessoas do mesmo turno de férias ao mesmo tempo e o atendimento atrasou.

**1.3 Quem vai usar?**
Os 8 analistas da equipe de atendimento e eu, como coordenadora.

**1.4 Como você vai saber que deu certo?**
- Se eu marcar férias de 10 a 20/01 e a Ana já estiver fora nesse período, aparece um aviso antes de salvar.
- Eu abro o calendário e vejo, por semana, quem está fora.
- Cada pessoa só consegue editar as próprias férias.

**1.5 O que NÃO pode acontecer?**
Não pode mexer no sistema de RH oficial. Ninguém de fora da equipe pode ver os dados.

---

## 2. Proposta 🤖

### 2.1 Resumo em uma frase
Uma página web interna onde a equipe registra as férias, vê um calendário semanal e recebe um aviso quando há sobreposição no mesmo turno.

### 2.2 Escopo
- **Faz:** cadastro de férias (início e fim), calendário semanal da equipe, aviso de sobreposição por turno, login com a conta corporativa.
- **Não faz:** aprovação formal de férias, integração com o sistema de RH, cálculo de saldo de dias, notificação por e-mail.

### 2.3 Critérios de aceite
- [ ] Dado que a Ana (turno manhã) está de férias de 08 a 15/01, quando a Carla (turno manhã) tenta marcar de 10 a 20/01, então aparece o aviso "Ana já estará fora de 10 a 15/01" e é preciso confirmar para salvar.
- [ ] Dado que estou logada como coordenadora, quando abro o calendário, então vejo cada semana com o nome de quem está fora.
- [ ] Dado que estou logado como Bruno, quando tento editar as férias da Ana, então o botão de editar não aparece.
- [ ] Dado um usuário de fora da equipe, quando ele tenta abrir a página, então vê "acesso negado".

### 2.4 Como vai funcionar (em linguagem simples)
1. A pessoa entra com o login da empresa.
2. Clica em "Marcar férias", escolhe início e fim e salva.
3. Se alguém do mesmo turno já estiver fora em algum desses dias, aparece um aviso com os nomes e as datas.
4. A tela inicial mostra o calendário da equipe, semana a semana.

*Técnico:* app web pequeno (Next.js) com login via conta corporativa (SSO), banco SQLite e a lista dos 8 membros e seus turnos num arquivo de configuração.

### 2.5 Riscos e cuidados
| Tema | Avaliação | Observação |
|---|---|---|
| Dados pessoais ou sensíveis | sim, baixo volume | Nome e datas de férias; nenhum dado de saúde ou salário |
| Acesso e segurança | atenção | Acesso restrito aos 9 e-mails da equipe |
| Custo (licenças, nuvem, APIs) | baixo | Roda no servidor interno que já existe |
| Integração com outros sistemas | nenhuma | Só o login corporativo |

**Risco sugerido:** médio, porque guarda dados pessoais (nomes e datas), mesmo que poucos.

### 2.6 Plano de execução
1. Criar o projeto e a tela de login com a conta corporativa, restrita à lista da equipe.
2. Criar o cadastro de férias (início e fim), em que cada pessoa edita apenas as próprias.
3. Criar a regra de sobreposição por turno e o aviso antes de salvar.
4. Criar o calendário semanal da equipe.
5. Escrever testes automatizados para os 4 critérios de aceite.
6. Publicar no servidor interno e registrar o endereço na seção 4.

### 2.7 Dúvidas em aberto
- Nenhuma. *(Resolvida: "Quem define o turno de cada pessoa?" Resposta do Roberto: um arquivo de configuração mantido pela coordenadora.)*

---

## 3. Chancela ✅

| Papel | Nome | Decisão (aprovado / ajustar / recusado) | Data | Comentário |
|---|---|---|---|---|
| Gestor (o "o quê") | Roberto Lima | aprovado | 2026-11-04 | Atende à dor do time. |
| Guardião TI (o "risco") | Felipe Andrade | aprovado | 2026-11-04 | Ok com acesso restrito à lista e backup diário do SQLite. |

---

## 4. Registro do Apply 🛠️

- **Data:** 2026-11-05
- **O que foi feito:** passos 1 a 6 do plano; 4 testes automatizados passando.
- **Onde está:** repositório `ferias-equipe`, branch `odd-0001`; endereço `https://ferias.intranet.exemplo`
- **Como testar:** entre com sua conta, marque um período que se sobreponha ao de alguém do seu turno e confira o aviso.
- **Desvios do plano:** backup diário do SQLite incluído, conforme pedido do Guardião TI.

---

## 5. Conferência 🔍

- [ ] Testei cada critério de aceite da seção 2.3
- **Resultado:** <aguardando a Carla>
- **Observações:**
