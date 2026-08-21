<main>
<img src="imagem-blog.png"
alt="Logotipo conceitual de tecnologia e educacao: um livro aberto de onde emerge um cérebro digital brilhante, cercado por ícones de Wi-Fi, circuitos e lâmpada de ideia. Cores em tons de azul e branco.">

<div>
<h2>Meu primeiro post</h2>
<p class="artigo-autor">Por: Marcelo Paludetto</p>
<p>Boas-vindas ao meu novo blog! Aqui vou compartilhar dicas de programação
e curiosidades da área de tecnologia.</p>
<button>❤️<span>0</span></button>
<button>👍<span>0</span></button>
</div>

<img src="imagem-blog.png"
alt="Logotipo conceitual de tecnologia e educacao: um livro aberto de onde emerge um cérebro digital brilhante, cercado por ícones de Wi-Fi, circuitos e lâmpada de ideia. Cores em tons de azul e branco.">

<div>
<h2>Meu primeiro post</h2>
<p class="artigo-autor">Por: Marcelo Paludetto</p>
<p>Boas-vindas ao meu novo blog! Aqui vou compartilhar dicas de programação
e curiosidades da área de tecnologia.</p>
<button>❤️<span>0</span></button>
<button>👍<span>0</span></button>
</div>
</article>
</main>

article {
display: flex;
}

botoes.forEach(function (botao) {
let curtiu = false;

botao.addEventListener("click", botaoClicado);

function botaoClicado() {
console.log("fui clicado");
let texto = botao.querySelector("span");
texto.textContent++;
}
});

function botaoClicado() {
console.log("fui clicado");
let texto = botao.querySelector("span");

if (curtiu === false) {
texto.textContent++;
curtiu = true;
}
}

function botaoClicado() {
console.log("fui clicado");
let texto = botao.querySelector("span");

if (curtiu === false) {
texto.textContent++;
curtiu = true;
} else {
texto.textContent--;
curtiu = false;
}
}