# Verus Studio — Landing Page (Parceiros)

Landing page estática (HTML/CSS/JS, sem build) para agências, gestores de tráfego e estrategistas.

## Estrutura

```
.
├── index.html                # Página principal (entry point)
├── .cpanel.yml               # Tarefas de deploy do cPanel (Git Version Control)
├── .gitignore
├── assets/
│   ├── images/               # hero, bio, fundo do CTA
│   ├── logo/                 # logos (SVG)
│   ├── bullets/              # selos da hero
│   ├── dividers/             # divisores das seções
│   └── projects/             # imagens do portfólio
└── reference/                # design system (NÃO é publicado)
```

## Rodar localmente

Abra o `index.html` no navegador, ou rode um servidor estático:

```bash
python3 -m http.server 8000
# acesse http://localhost:8000
```

## Subir para o GitHub

```bash
git init
git add .
git commit -m "Landing page Verus Studio"
git branch -M main
git remote add origin https://github.com/verus-std/verus-para-agencias.git
git push -u origin main
```

## Deploy no cPanel (Git™ Version Control)

1. No cPanel, abra **Git Version Control → Create**.
2. Em **Clone URL**, cole `https://github.com/verus-std/verus-para-agencias.git`.
3. Defina o diretório do repositório (ex.: `/home/USUARIO/repositories/verus-para-agencias`).
4. Após clonar, clique em **Manage → Pull or Deploy → Update from Remote** e depois **Deploy HEAD Commit**.
5. O `.cpanel.yml` copia o `index.html` e a pasta `assets/` para `~/public_html/para-agencias`.

Com essa configuração, a landing fica disponível em:

```text
https://SEU_DOMINIO.com.br/para-agencias/
```

A cada novo push no GitHub, repita o **Update from Remote** + **Deploy HEAD Commit** (ou configure deploy automático por webhook).

> Se a landing precisar ficar em outro caminho, troque `$HOME/public_html/para-agencias` no `.cpanel.yml` pelo document root correto.

## Segurança

- Não há segredos, chaves ou credenciais no projeto — é um site 100% estático.
- O número de WhatsApp nos botões é um dado de contato público (intencional).
- `.gitignore` bloqueia `.env`, chaves e arquivos de sistema, evitando commits acidentais de dados sensíveis.

## Observação de performance (opcional)

`assets/images/hero-image.png` é grande (~2,4 MB). Para acelerar o carregamento, vale comprimir/converter as imagens para WebP antes de publicar.
