# Landing Page — Dr. Vitor Guimarães

Site estático (HTML/CSS puro, sem build). Pronto para deploy no Vercel.

## ⚠️ ANTES DE PUBLICAR: trocar o número do WhatsApp

O número está com um placeholder (`5512999999999`) em `public/index.html`.
Abra o arquivo, use "Localizar e Substituir" e troque **todas** as ocorrências de:

```
5512999999999
```

pelo número real do Dr. Vitor no formato internacional, sem espaços nem símbolos:
`55` + DDD + número. Ex.: para (12) 99123-4567 → `5512991234567`

São 4 botões que apontam pro WhatsApp (hero, seção "para quem é", CTA final e botão flutuante), todos usam esse mesmo número.

---

## Como publicar no Vercel

### Opção 1 — Arrastar e soltar (mais rápido, sem conta técnica)

1. Acesse https://vercel.com e crie uma conta (pode logar com Google/GitHub).
2. No painel, clique em **Add New → Project**.
3. Procure a opção de deploy manual / arraste a pasta `public/` para a área de upload.
   - No Vercel também dá pra usar https://vercel.com/new e soltar a pasta.
4. Confirme. Em segundos o site estará no ar num endereço `.vercel.app`.

### Opção 2 — Via GitHub (recomendado para atualizações futuras)

1. Suba esta pasta para um repositório no GitHub.
2. No Vercel: **Add New → Project → Import** o repositório.
3. Nas configurações de build, deixe assim:
   - **Framework Preset:** Other
   - **Build Command:** (deixe em branco)
   - **Output Directory:** `public`
4. Clique em **Deploy**. Pronto.

Toda vez que você atualizar o repositório, o Vercel republica sozinho.

### Opção 3 — Via CLI

```bash
npm i -g vercel
cd lp-dr-vitor
vercel        # segue o assistente; quando perguntar o output dir, informe: public
vercel --prod # publica em produção
```

---

## Domínio próprio (opcional)

Se o Dr. Vitor tiver um domínio (ex.: `drvitorguimaraes.com.br`):
1. No projeto do Vercel → **Settings → Domains → Add**.
2. Digite o domínio e siga as instruções de DNS que o Vercel mostrar
   (geralmente apontar um registro A ou CNAME no provedor onde o domínio foi registrado).

---

## Estrutura

```
lp-dr-vitor/
├── public/
│   ├── index.html      → a página
│   ├── dr-vitor.jpg     → foto do doutor
│   └── robots.txt
├── vercel.json          → config (cache da foto + headers de segurança)
├── package.json
└── README.md
```

## O que já está configurado

- Foto com cache de 1 ano (carregamento rápido em visitas repetidas).
- Headers de segurança básicos.
- `cleanUrls` ativo (URLs sem `.html`).
- Responsivo, com botão flutuante de WhatsApp em todas as telas.
