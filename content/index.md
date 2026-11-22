---
title: Pedroh99z - Wiki
---

Bem-vindo a minha Wiki pessoal. Aqui estão reunidos meus trabalhos, minhas aulas, listas de exercícios, etc, para fácil acesso. Para encontrar qualquer tipo de conteúdo, basta pesquisar por termos relevantes, ou procurar no explorador. Esta Wiki está em constante desenvolvimento, então novos conteúdos, bem como correções, podem chegar a qualquer momento.

---

#### 🎵 Música de fundo

Uma musiquinha para ouvir de fundo enquanto navega pelo digital garden.

<a id="link-musica" href="#">Clique aqui!</a>

<script>
function sortear(porcentagem) {
    if (porcentagem < 0 || porcentagem > 100) {
        throw new Error("A chance deve estar entre 0 e 100.");
    }

    return Math.random() * 100 < porcentagem;
}

var link = "";

if (sortear(3.14)) {
    link = "https://www.youtube.com/watch?v=Ey8wSKvxWfI";
} else {
    link = "https://www.youtube.com/watch?v=dQw4w9WgXcQ";
}

const elemento = document.getElementById("link-musica");

elemento.href = link;
elemento.target = "_blank";
elemento.rel = "noopener noreferrer";
</script>

Esteja avisado que existe uma chance de 3.14% de você sofrer um rickroll.