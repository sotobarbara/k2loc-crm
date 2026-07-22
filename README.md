# K2LOC CRM — Funil de Vendas

CRM profissional (estilo Pipedrive) para a **K2 LOC** gerenciar prospects e locações.
Página única, sem instalação, **grátis**, com sincronização em tempo real via Firebase.

![K2LOC](logo-k2loc.png)

## ✨ O que tem

- **Funil de vendas visual (Kanban)** — arraste o lead entre as etapas
  (Novo → Contato Feito → Qualificado → Proposta → Negociação → Ganho).
- **Ficha completa do lead** — dados, **anotações**, **tarefas com data**, e uma
  **timeline** com tudo que aconteceu (mudanças de etapa, notas, tarefas).
- **Ações rápidas** — WhatsApp, ligar e e-mail direto do card.
- **Dashboard** — leads por etapa, por origem, desempenho por vendedor,
  valor no funil, ganhos no mês e taxa de conversão.
- **Contatos** — lista/tabela com busca e filtros (dono, origem).
- **Atividades** — todas as tarefas pendentes num lugar só, com atrasadas em destaque.
- **Entrada de leads** — cadastro rápido, import de planilha e **integração** com
  WhatsApp / Instagram / Facebook / site.
- **Tempo real** — Fernanda e Elizimário veem as mudanças um do outro na hora.
- **Backup offline** — funciona no localStorage quando cai a internet.

## 🚀 Como abrir / hospedar

É um único `index.html`. Basta hospedar em qualquer lugar estático:

- **Vercel / Netlify / GitHub Pages** — arraste o arquivo ou conecte o repositório.
- **Local:** `python -m http.server 8000` e acesse `http://localhost:8000`.

## 👥 Como usar

1. Selecione seu nome (Fernanda / Elizimário) no canto superior direito.
2. **Novo Lead** (botão laranja) para cadastrar, ou arraste os cards no funil.
3. Clique em qualquer lead para abrir a **ficha**: mude a etapa, escreva
   **anotações**, crie **tarefas** ("ligar quinta") e veja a **timeline**.
4. Marque **Ganhou** / **Perdeu** quando fechar (ou não) o negócio.

## ⚙️ Sincronização em tempo real (Firebase)

O indicador no topo mostra o estado da conexão:

- 🟢 **Sincronizado** · 🟡 **Conectando…** · ⚪ **Offline (local)** · 🔴 **Sem acesso ao banco**

### Se aparecer 🔴 "Sem acesso ao banco"

As regras do Realtime Database precisam permitir leitura e escrita. No
[Console do Firebase](https://console.firebase.google.com) → projeto **k2loc-crm**
→ **Realtime Database** → aba **Regras**:

```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```

> Deixa a base aberta para quem tiver o link. Para uma equipe pequena costuma bastar —
> mantenha o link privado e não guarde dados sensíveis. Dá para colocar login
> (Firebase Auth) por cima depois, se quiser restringir.

## 🔌 Integração — receber leads automaticamente

Para os contatos de **WhatsApp**, **Instagram/Facebook (Meta)** ou do **site**
caírem sozinhos no funil, conecte a origem ao endpoint do Firebase usando uma
automação (Make, Zapier ou n8n). Tudo isso está explicado na aba **Entrada de Leads**.

**Endpoint (POST):**

```
https://k2loc-crm-default-rtdb.firebaseio.com/leads.json
```

**Corpo (JSON):**

```json
{
  "name": "Nome da empresa/cliente",
  "phone": "(85) 99999-9999",
  "source": "whatsapp",
  "stage": "novo"
}
```

- 💬 **WhatsApp** — API oficial da Meta ou um bot (Z-API, Twilio) → POST a cada nova conversa.
- 📸 **Instagram / Facebook Lead Ads** — no Make/Zapier: gatilho "Novo Lead" → ação "HTTP POST".
- 🌐 **Site / Landing** — o formulário "Peça um orçamento" envia o POST direto.

> Origens aceitas no campo `source`: `whatsapp`, `instagram`, `facebook`, `site`,
> `indicacao`, `manual`, `planilha`. Campos que faltarem recebem um padrão automático.

## 🎨 Marca

- Navy: `#0A1F4B` · Laranja: `#E85D1A`
- Logo oficial: `logo-k2loc.png`

---

K2 LOC · Locação de Containers e Equipamentos · Fortaleza/CE
