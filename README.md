#Criptografia de Textos#


Esta aplicação web criptografa e descriptografa textos para permitir a troca de mensagens secretas. A criptografia é feita substituindo certas letras por palavras específicas, conforme as regras abaixo:

"e" -> "enter"
"i" -> "imes"
"a" -> "ai"
"o" -> "ober"
"u" -> "ufat"
Funcionalidades
Criptografar texto.
Descriptografar texto criptografado.
Copiar texto criptografado/descriptografado para a área de transferência.
Requisitos
Funciona apenas com letras minúsculas.
Não aceita acentos ou caracteres especiais.
Estrutura do Projeto
index.html: Estrutura da página web.
styles.css: Estilização da página.
script.js: Lógica de criptografia e descriptografia.
Como Usar
Insira o texto no campo de entrada.
Clique em "Criptografar" ou "Descriptografar" para transformar o texto.
O resultado aparecerá no campo de saída.
Clique em "Copiar" para copiar o resultado para a área de transferência.

HTML code:

<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Criptografia de Textos</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>Criptografia de Textos</h1>
    <textarea id="inputTexto" placeholder="Digite o texto aqui..."></textarea>
    <br>
    <button onclick="criptografar()">Criptografar</button>
    <button onclick="descriptografar()">Descriptografar</button>
    <br><br>
    <textarea id="resultado" readonly placeholder="Resultado..."></textarea>
    <br>
    <button onclick="copiarTexto()">Copiar</button>

    <script src="script.js"></script>
</body>
</html>

CSS code:

body {
    font-family: Arial, sans-serif;
    text-align: center;
    margin: 50px;
}

textarea {
    width: 80%;
    height: 100px;
    margin: 10px 0;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
}

button {
    padding: 10px 20px;
    margin: 10px;
    border: none;
    background-color: #007BFF;
    color: white;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}

JavaScript code: 

function criptografar() {
    let texto = document.getElementById("inputTexto").value;
    let textoCriptografado = texto
        .replace(/e/g, "enter")
        .replace(/i/g, "imes")
        .replace(/a/g, "ai")
        .replace(/o/g, "ober")
        .replace(/u/g, "ufat");
    document.getElementById("resultado").value = textoCriptografado;
}

function descriptografar() {
    let texto = document.getElementById("inputTexto").value;
    let textoDescriptografado = texto
        .replace(/enter/g, "e")
        .replace(/imes/g, "i")
        .replace(/ai/g, "a")
        .replace(/ober/g, "o")
        .replace(/ufat/g, "u");
    document.getElementById("resultado").value = textoDescriptografado;
}

function copiarTexto() {
    let texto = document.getElementById("resultado");
    texto.select();
    document.execCommand("copy");
    alert("Texto copiado para a área de transferência!");
}




