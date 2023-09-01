<!DOCTYPE html>
<html>
<head>
    <title>Página con Buscador y Lista</title>
    <script>
        function buscar() {
            var input = document.getElementById("buscarInput");
            var filtro = input.value.toUpperCase();
            var lista = document.getElementById("lista");
            var elementos = lista.getElementsByTagName("li");

            for (var i = 0; i < elementos.length; i++) {
                var textoElemento = elementos[i].textContent || elementos[i].innerText;
                if (textoElemento.toUpperCase().indexOf(filtro) > -1) {
                    elementos[i].style.display = "";
                } else {
                    elementos[i].style.display = "none";
                }
            }
        }

        function agregarElemento() {
            var nuevoElemento = document.createElement("li");
            var texto = prompt("Ingrese el nuevo elemento:");
            if (texto) {
                nuevoElemento.textContent = texto;
                document.getElementById("lista").appendChild(nuevoElemento);
            }
        }
    </script>
</head>
<body>
    <h1>Buscador y Lista</h1>
    <input type="text" id="buscarInput" onkeyup="buscar()" placeholder="Buscar elementos...">
    <button onclick="agregarElemento()">Agregar Elemento</button>
    <ul id="lista">
        <li>Elemento 1</li>
        <li>Elemento 2</li>
        <li>Elemento 3</li>
        <li>Elemento 4</li>
        <li>Elemento 5</li>
    </ul>
</body>
</html>
