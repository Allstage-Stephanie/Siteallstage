# Site ALL STAGE

Site institucional da ALL STAGE — locação de equipamentos técnicos para eventos.

Site estático: um único `index.html` com o CSS e o JavaScript embutidos. Não precisa
de build, npm, nem servidor. É só subir os arquivos.

---

## Como publicar no GitHub Pages

1. Crie um repositório novo no GitHub (pode ser público ou privado).
2. Suba **todo o conteúdo desta pasta** na raiz do repositório —
   o `index.html` precisa ficar no primeiro nível, não dentro de outra pasta.
3. No repositório, vá em **Settings → Pages**.
4. Em *Source*, escolha **Deploy from a branch**; em *Branch*, escolha `main` e a pasta `/ (root)`.
5. Salve. Em 1–2 minutos o site fica no ar no endereço que o GitHub mostrar na
   própria tela de Pages, algo como `https://SEU-USUARIO.github.io/NOME-DO-REPO/`.

---

## O único ajuste manual

Depois que o site estiver no ar, abra o `index.html`, procure por `og:url`
(fica no topo, por volta da linha 12) e troque o endereço de exemplo pelo
endereço real:

```html
<meta property="og:url" content="https://SEU-USUARIO.github.io/allstage/">
```

Isso é o que faz o link aparecer com a logo e a descrição quando alguém
compartilha o site no WhatsApp. Sem isso o link vai como uma caixa cinza vazia.

---

## Estrutura

```
index.html                 o site inteiro
apresentacao-allstage.pdf  catálogo do botão "Ver Catálogo"
og-image.png               imagem da prévia de link (WhatsApp, LinkedIn)
favicon.png                ícone da aba do navegador
favicon-192.png            ícone para Android
favicon-512.png            ícone para Android
apple-touch-icon.png       ícone para atalho no iPhone
logo-allstage-1.png        logo do rodapé
imgs-produtos/             fotos dos equipamentos
imgs-eventos/              fotos da galeria de eventos
imgs-marcas/               logos das marcas parceiras
imgs-agencias/             logos dos clientes
.nojekyll                  desliga o processamento do Jekyll no GitHub Pages
```

---

## Cuidados ao editar

**Nomes de arquivo**: sempre em minúsculas, sem espaço e sem acento.
O servidor do GitHub diferencia maiúscula de minúscula — `Foto.PNG` e `foto.png`
são arquivos diferentes lá, mesmo sendo iguais no Windows. É a causa mais comum
de "a imagem aparece no meu PC mas some no site".

**Extensão tem que bater com o formato**: um arquivo PNG salvo como `.jpg`
funciona no Windows e quebra em alguns servidores. Se exportar uma imagem nova,
confirme que a extensão corresponde ao formato de verdade.

**Fotografia é `.jpg`, gráfico com fundo transparente é `.png`.**
Foto salva em PNG chega a ficar 15× mais pesada sem ganho nenhum de qualidade.

**A classe `js`**: o `<script>` no topo do `<head>` marca que o JavaScript
carregou, e só então as animações de entrada escondem o conteúdo. Não remova —
é o que garante que o site apareça inteiro caso o JavaScript falhe.

---

## Pendências conhecidas

- **`apresentacao-allstage.pdf` tem 64 MB.** Funciona, mas o GitHub emite aviso
  em arquivos acima de 50 MB, e cada visitante que clica em "Ver Catálogo" baixa
  os 64 MB inteiros. Vale comprimir o PDF ou hospedá-lo no Drive e apontar o
  botão para lá.
- **As 6 TVs Samsung usam a mesma foto**, assim como os 2 notebooks Dell.
  Funciona, mas fotos distintas ficariam melhor.
- **`evento-06.jpg` não é usada** — a galeria mostra 5 fotos. A sexta ficou de
  fora desta pasta.
