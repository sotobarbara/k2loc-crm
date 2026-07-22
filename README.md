# K2LOC CRM - Prospects & Locação

Sistema de CRM online para K2LOC com Firebase Realtime Database. Totalmente gratuito e sem necessidade de instalação.

## 🚀 Deploy Online (Grátis)

### **Opção 1: Netlify (MAIS FÁCIL - 2 minutos)**

1. Acesse: https://app.netlify.com
2. Clique em **"Add new site"** → **"Deploy manually"**
3. Arraste o arquivo `index.html` para a área
4. **Pronto!** Você recebe um link público

Netlify vai dar um link tipo: `https://seu-site-random.netlify.app`

---

### **Opção 2: GitHub Pages (Grátis)**

1. Crie uma conta no GitHub (se não tiver): https://github.com
2. Crie um novo repositório público chamado `k2loc-crm`
3. Faça upload do arquivo `index.html` para a raiz
4. Vá em **Settings** → **Pages** → selecione **main branch**
5. GitHub vai gerar um link tipo: `https://seu-usuario.github.io/k2loc-crm`

---

### **Opção 3: Vercel (Grátis)**

1. Acesse: https://vercel.com/new
2. Importe o repositório GitHub (criado na Opção 2)
3. Deploy automático
4. Recebe um link tipo: `https://k2loc-crm.vercel.app`

---

## 📋 Como Usar

### **Fernanda:**
1. Abre o link no navegador
2. Seleciona seu nome ("Fernanda") no topo direito
3. Clica em um prospect
4. Muda o status (dropdown)
5. Adiciona notas (opcional)
6. Clica **Salvar**

### **Elizimario:**
1. Abre o MESMO link
2. Seleciona seu nome ("Elizimario")
3. VÊ INSTANTANEAMENTE as mudanças de Fernanda ⚡

---

## 🔧 Tecnologia

- **React 18** - Interface dinâmica
- **Firebase Realtime Database** - Sincronização em tempo real
- **Tailwind CSS** - Design responsivo
- **localStorage** - Backup offline

---

## 📊 Funcionalidades

✅ 42 prospects pré-carregados  
✅ 2 usuários (Fernanda + Elizimario)  
✅ 6 Status (Novo → Contatado → Interessado → Agendado → Cliente → Descartado)  
✅ Histórico completo de ações  
✅ Telefone clicável (liga direto)  
✅ Busca e filtros  
✅ Exportar dados em JSON  
✅ Sincronização em tempo real via Firebase  
✅ Funciona offline com localStorage  

---

## 🎨 Cores Oficiais K2LOC

- Navy: `#0A1F4B`
- Orange: `#E85D1A`

---

## 📱 Compatibilidade

- ✅ Desktop (Chrome, Firefox, Safari, Edge)
- ✅ Tablet (iPad, Android tablets)
- ✅ Mobile (iPhone, Android)

---

## 🔒 Dados

Todos os dados são:
- ✅ Salvos no Firebase (nuvem)
- ✅ Compartilhados entre Fernanda e Elizimario
- ✅ Com backup local (localStorage)
- ✅ Sem intermediários

---

## ⚙️ Sincronização em tempo real (Firebase)

O CRM usa o **Firebase Realtime Database** para a Fernanda e o Elizimário verem
as mudanças um do outro na hora. No canto superior direito há um indicador:

- 🟢 **Sincronizado** — conectado ao Firebase, tudo em tempo real.
- 🟡 **Conectando...** — tentando conectar (aguarde alguns segundos).
- ⚪ **Offline (local)** — sem Firebase; salva só neste aparelho.
- 🔴 **Sem acesso ao banco** — o Firebase respondeu, mas as **regras** estão bloqueando.

### Se aparecer 🔴 "Sem acesso ao banco"

As regras do Realtime Database precisam permitir leitura e escrita. No
[Console do Firebase](https://console.firebase.google.com) → projeto **k2loc-crm**
→ **Realtime Database** → aba **Regras**, use:

```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```

> Isso deixa a base aberta para qualquer um com o link. Para uma equipe pequena e
> uma lista de prospects, costuma ser suficiente — mas **não guarde dados sensíveis**
> e mantenha o link privado. Se quiser restringir depois, dá para colocar
> autenticação (Firebase Auth) por cima.

---

## ❓ Dúvidas

**P: Preciso pagar algo?**  
R: Não! Tudo é grátis (Firebase, Netlify, GitHub).

**P: Funciona offline?**  
R: Sim! Salvava locally e sincroniza quando volta online.

**P: Outros podem usar?**  
R: Qualquer um com o link pode acessar. Para restringir, guarde o link em segurança.

**P: Como adicionar mais prospects?**  
R: Entre em contato para editar o código (não é complexo).

---

## 👤 Criado por

Claude (Assistente AI)  
Data: Julho 2026  
Para: K2LOC Containers & Equipamentos  
Localização: Fortaleza, CE
