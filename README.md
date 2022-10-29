<!DOCTYPE html>
<html lang="pt-br">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Números Perfeitos</title>
    <link rel="stylesheet" href="numeros_perfeitos.css">
</head>

<body>
    <div id="corpo">
        <div>
            <h1 class="titulo">Número perfeitos</h1>
        </div>
        <div>
            <p class="numero">Número: <input class="quadradoNumero" type="number" id="inNumero" placeholder="100"></p>
        </div>
        <p><input class="botao" type="button" value="Verificar" id="btVerificar"></p>
        <p class="divisores">Divisores:</p>
        <p id="outResposta" class="resposta1"></p>
        <p id="outResposta2" class="resposta2"></p>
        <h2 id="outPerfeito" class="resposta3"></h2>

        <script>

            let btVerificar = document.getElementById("btVerificar");
            btVerificar.addEventListener("click", numerosPerfeitos)

            function numerosPerfeitos() {
                let inNumero = document.getElementById("inNumero");
                let outResposta = document.getElementById("outResposta");
                let outResposta2 = document.getElementById("outResposta2");
                let outPerfeito = document.getElementById("outPerfeito");

                let numero = Number(inNumero.value);
                let i
                let div = ""
                let soma = 0
                let perfeito

                for (i = 1; i < numero; i++) {
                    if (numero % i == 0) {
                        div = div + i + ", " + "\n"
                        soma = soma + i
                    }
                    if (soma == numero) {
                        perfeito = " é PERFEITO."
                    }
                    else {
                        perfeito = " NÃO é perfeito."
                    }
                }
                outResposta.textContent = div
                outResposta2.textContent = "soma: " + soma
                outPerfeito.textContent = numero + perfeito

                if (numero == 0 || isNaN(numero)) {
                    alert("O campo precisa ser preenchido corretamente!");
                    inNumero.focus();
                    return;
                }
            }

        </script>
    </div>
</body>

</html>
