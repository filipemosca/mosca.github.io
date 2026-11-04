---
title: Buscador de artigos de revisão no PubMed
layout: page
published: true
---

Essa ferramenta busca artigos de revisão nas revistas: NEJM, Lancet, JAMA, BMJ e Annals of Internal Medicine. É só digitar o nome de um assunto, em inglês, na barra abaixo e dar enter.

<center>
<form onsubmit="buscarPubmed(); return false;">
<input type="text" id="termo" placeholder="Digite o termo (ex: pneumonia)" size="40" required>
<button type="submit">Buscar</button>
</form>

<br>
</center>

<script>
function buscarPubmed() {
    const termo = document.getElementById("termo").value.trim();
    if (!termo) return;

    const baseUrl = "https://pubmed.ncbi.nlm.nih.gov/?term=";

    const filtros = '+AND+('
        + '"N+Engl+J+Med"[Journal]+OR+'
        + '"Lancet"[Journal]+OR+'
        + '"JAMA"[Journal]+OR+'
        + '"Ann+Intern+Med"[Journal]+OR+'
        + '"BMJ"[Journal]+OR+'
        + '"Am+Fam+Physician"[Journal]+OR+'
        + '"Nat+Rev*"[Journal]'
        + ')+AND+(Review[ptyp])&sort=date';

    const url = baseUrl + encodeURIComponent(termo) + filtros;

    window.open(url, "_blank");
}
</script>
