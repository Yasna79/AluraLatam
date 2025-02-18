# Lista de Amigos - Sorteo

Este proyecto permite agregar nombres a una lista, mostrarlos en pantalla y sortear aleatoriamente un amigo. Está desarrollado con JavaScript, HTML y CSS.

## Características
- Agregar nombres a una lista.
- Mostrar los nombres ingresados.
- Seleccionar aleatoriamente un nombre de la lista.
- Resetear la lista y el resultado del sorteo.

## Cómo usarlo
1. Escribe un nombre en el campo de entrada.
2. Haz clic en el botón **Agregar Amigo** para añadirlo a la lista.
3. Puedes seguir agregando más nombres.
4. Para sortear un nombre aleatorio, presiona **Sortear Amigo**.
5. Si deseas reiniciar la lista y el sorteo, presiona **Resetear**.

## Código Principal (JavaScript)
```js
let listaAmigos = [];
console.log(listaAmigos);
let lista = document.getElementById("listaAmigos");

function agregarAmigo() {
    let nombreAmigo = document.getElementById("amigo").value;
    
    if (nombreAmigo === "") {
        alert("Por favor, inserte un nombre.");
    } else {
        listaAmigos.push(nombreAmigo);
        document.getElementById("amigo").value = "";
        actualizarLista();
    }

    console.log(listaAmigos);
}

function actualizarLista() {
    lista.innerHTML = "";
    
    let inicioLista = 0;
    let finalLista = listaAmigos.length -1;

    while (inicioLista <= finalLista) {
        let listaNombre = document.createElement("li");
        listaNombre.textContent = listaAmigos[inicioLista];
        lista.appendChild(listaNombre);
        inicioLista++;
    }
}

function sortearAmigo() {
    if (listaAmigos.length === 0) {
        alert("No hay ningún nombre disponible.");
    } else {
        let indiceSorteado = Math.floor(Math.random() * listaAmigos.length);
        let nombreSorteado = listaAmigos[indiceSorteado];
        let nombreMostrado = document.getElementById("resultado");
        nombreMostrado.innerHTML = nombreSorteado;
        lista.innerHTML = "";
    }
}

function Resetear() {
    lista.remove();
    let nombreMostrado = document.getElementById("resultado");
    nombreMostrado.innerHTML = "";
}
```

## Tecnologías utilizadas
- HTML
- CSS
- JavaScript

## Mejoras futuras
- Agregar estilos con CSS para mejorar la interfaz.
- Permitir eliminar nombres individuales de la lista.
- Guardar la lista en `localStorage` para que no se pierda al recargar la página.

## Autor
Yasna Perez Montenegro
