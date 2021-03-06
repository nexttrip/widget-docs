# Cómo integrar el widget en su sitio.

Antes de iniciar este documento debe estar seguro de haber recibido sus códigos de uso.
Al menos tres: un __customerId__, un __dealId__ y un __productId__

Para comenzar a utilizar nuestro widget debe agregar el siguiente fragmento de código en el HTML de su página.
El lugar recomendado para agregarlo sería antes del cierre del tag `</body>`, aunque también podría agregarlo
entre los tags `<header></header>`.  

__IMPORTANTE__: Remplace el __customerId__, __dealId__ y __productId__ con los que recibió.

{% include snippet.md %}

Luego, usted querrá que ciertos botones o links de su sitio inicien los pasos para que sus clientes realicen las reservas.  Para ello deberá agregar un poco de texto en ellos, del siguiente modo:

Pongamos como ejemplo el siguiente botón:

```html
<button type="button" class="btn btn-solid">Reservar</button>
```

Lo único que debe agregar es el atributo __data-nexttrip__ en el tag del botón:

```html
<button type="button" class="btn btn-solid" data-nexttrip >Reservar</button>
```

Si además desea que acada botón cambie alguna opción de configuración.  Por ejemplo, si quisiera utilizar
otro productId para un botón particular: 

```html
<button type="button" class="btn btn-solid" 
        data-nexttrip data-nexttrip-productId="ASUNTAWEEKLY2017">Reservar</button>
```
