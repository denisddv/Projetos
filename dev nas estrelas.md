<head> 
    <title>Jogo da Força</title>
    <meta charset="utf 8"/> 

    <style>
        @font-face {
            font-family: Starjedi;
            src: url("assets/Starjedi.ttf");
        }
        body  {
            background: #0e0e13;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            gap: 24px;  
            margin-top: 30px;
            
        }
        h1 {
            color:#E6b93c;
            font-family: Starjedi;
        }

        .darth-vader {
        
            width: 300px;
        }
        .boneco {
      width: 300px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;

      position: relative;
    }

    .darth-vader {
      width: 300px;
    }

    .cabeca {
      background: #0e0e13;
      width: 300px;
      height: 120px;

      position: absolute;
      top: 0;
    }

    .braco-esquerdo {
      background: #0e0e13;
      width: 100px;
      height: 160px;

      position: absolute;
      left: 0;
    }

    .torso {
      background: #0e0e13;
      width: 100px;
      height: 160px;

      position: absolute;
      left: 100px;
    }

    .braco-direito {
      background: #0e0e13;
      width: 100px;
      height: 160px;

      position: absolute;
      right: 0;
    }

    .perna-esquerda {
      background: #0e0e13;
      width: 155px;
      height: 160px;

      position: absolute;
      left: 0;
      top: 190px;
    }

    .perna-direita {
      background: #0e0e13;
      width: 155px;
      height: 160px;

      position: absolute;
      right: 0;
      top: 190px;
    }
    .mostrar {
       background: transparent; 
    }
        button {
            background: #4894C3;
            color: #ffffff;
            border: 0;
            border-radius: 4px;
            padding: 12px 24px;
            cursor: pointer;
        }
        .palavra {
            color: #E6b93c;
            font-size: 42px;
        }
        .letra{
          border: 1px solid #E6b93c;  
        }
    

    </style>
</head>
<body>
    <h1>Jogo da Força</h1>
    
  <div class="boneco">
    <img src="assets/darth-vader.png" class="darth-vader" />
    <div class="parte-do-boneco cabeca"></div>
    <div class="parte-do-boneco braco-esquerdo"></div>
    <div class="parte-do-boneco torso"></div>
    <div class="parte-do-boneco braco-direito"></div>
    <div class="parte-do-boneco perna-esquerda"></div>
    <div class="parte-do-boneco perna-direita"></div>
  </div>


    <p class="palavra"> </p>
    <button onclick="Chutar()">Chutar Letra</button>
    <img src="assets/driven.png" class="logo-driven"/>

    <script>

        const partesDoBoneco = Array.from(querySelectorAll(".parte-do-boneco"));
        const chuteEfetuados = [];
        const palavra = "uma palavra";
        let errosCometidos = 0;
        const quantidadeMaximaDeErros =  partesDoBoneco.length;
       
        mostrarPalavra ();
        
function mostrarPalavra () {
    let palavraMostrada = "";

}

        function Chutar () {
          const Chute = prompt("Qual é seu Chute?");
            
        if (chuteEfetuados.includes(Chute)) {
         alert("Chute já efetuado");
        return;
}

chuteEfetuados.push(Chute);

if(palavra.includes(Chute)) {
    palavraMostrada ()

    let palavraMostrada = "";
    for (let i = 0; i < 10; i = + 1) {
        if (chuteEfetuados.includes(palavra[i])) {
            palavraMostrada = palavraMostrada + '<span class="letra">' + palavra[i] + '</span>'
        } else if (palavra[i] === ' ') { 
            palavraMostrada = palavraMostrada + " ";
        } else {
            palavraMostrada = 
            palavraMostrada + '<span class="letra">'_'</span>'

        }
    }
   
 document.querySelector(".palavra").innerHTML = palavraMostrada;
} else {   
    errosCometidos = errosCometidos + 1;
    for (let 1 =0; i < errosCometidos; i = i + 1) { 
     partesDoBoneco[i].classList.add ("mostrar")
    }

    if (errosCometidos === quantidadeMaximaDeErros) {
        alert ("Você perdeu");
    } else {
        alert("Chute errado, tente novamente!")
    }
}
         }
        </script>
</body>
