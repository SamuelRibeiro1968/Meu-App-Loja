# Copilot Instructions for lojaproject

## Visão Geral
Este projeto é uma aplicação Django voltada para e-commerce, estruturada em dois principais apps: `lojaproject` (configuração global) e `lojaapp` (lógica de negócio). O fluxo central envolve produtos, usuários e páginas de navegação, com arquivos estáticos e de mídia organizados em pastas dedicadas.

## Estrutura de Pastas
- `lojaproject/`: Configurações globais do Django (settings, urls, wsgi/asgi).
- `lojaapp/`: Modelos, views, urls e testes do app principal.
- `templates/`: HTMLs para renderização das páginas.
- `static/` e `media/`: Arquivos estáticos e uploads de produtos.

## Convenções Específicas
- Os modelos estão em `lojaapp/models.py` e seguem o padrão Django ORM.
- As views em `lojaapp/views.py` usam funções, não classes.
- URLs do app são definidas em `lojaapp/urls.py` e incluídas em `lojaproject/urls.py`.
- Templates usam herança via `base.html`.
- Imagens de produtos são servidas via pasta `media/produtos/`.

## Fluxos de Desenvolvimento
- **Migrações:**
  - Criar/atualizar modelos: `python manage.py makemigrations lojaapp`
  - Aplicar migrações: `python manage.py migrate`
- **Execução do servidor:**
  - `python manage.py runserver`
- **Testes:**
  - Testes unitários em `lojaapp/tests.py`: `python manage.py test lojaapp`
- **Administração:**
  - Admin customizado em `lojaapp/admin.py`. Acesse `/admin` após criar superusuário: `python manage.py createsuperuser`

## Integrações e Dependências
- Banco de dados SQLite (`db.sqlite3` por padrão).
- Dependências listadas em `requeriments.txt` (atenção ao nome não padrão).
- Imagens e arquivos estáticos devem ser referenciados via diretórios `media/` e `static/`.

## Padrões e Recomendações
- Siga o padrão Django para organização de apps e templates.
- Use nomes de arquivos e pastas em minúsculo, sem espaços.
- Para novos apps, registre-os em `settings.py` e inclua suas URLs em `lojaproject/urls.py`.
- Evite lógica de negócio em views; prefira modelos ou funções utilitárias.

## Exemplos de Comandos
```powershell
python manage.py makemigrations lojaapp
python manage.py migrate
python manage.py runserver
python manage.py test lojaapp
python manage.py createsuperuser
```

## Arquivos-Chave
- `lojaapp/models.py`: Modelos principais
- `lojaapp/views.py`: Lógica de exibição
- `lojaapp/urls.py` e `lojaproject/urls.py`: Roteamento
- `templates/base.html`: Template base
- `requeriments.txt`: Dependências

---

> Atualize este documento conforme novas convenções ou fluxos surgirem. Dúvidas ou padrões não documentados? Solicite feedback do time antes de automatizar mudanças.
