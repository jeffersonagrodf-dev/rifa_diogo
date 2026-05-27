# 🍳 Rifa Beneficente — Ajude o Diogo

Rifa online com 200 números para arrecadar fundos para o tratamento do Diogo contra osteomielite crônica.

## 🚀 Como publicar no GitHub Pages

1. Crie um repositório público no GitHub (ex: `rifa-diogo`)
2. Faça upload dos arquivos desta pasta
3. Vá em **Settings → Pages → Source: main / root**
4. Aguarde ~1 minuto — seu link será: `https://SEU-USUARIO.github.io/rifa-diogo`

## ⚙️ Configuração (primeira vez)

Na primeira abertura do site, configure:
- URL do Supabase
- Anon Key do Supabase
- Senha do painel admin

## 📋 SQL para criar o banco (Supabase)

```sql
CREATE TABLE numeros (
  numero INT PRIMARY KEY,
  status TEXT DEFAULT 'available',
  nome TEXT DEFAULT '',
  telefone TEXT DEFAULT '',
  updated_at TIMESTAMPTZ DEFAULT now()
);
INSERT INTO numeros (numero) SELECT generate_series(1,200);

ALTER TABLE numeros ENABLE ROW LEVEL SECURITY;
CREATE POLICY "leitura publica" ON numeros FOR SELECT USING (true);
CREATE POLICY "reserva publica" ON numeros FOR UPDATE USING (status = 'available');
```

## 💸 PIX
Chave: **61992659634** — Francineide Gonçalves Ramos
