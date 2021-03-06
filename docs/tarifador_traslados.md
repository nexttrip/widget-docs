# Modulo tarifador para ALLUSA - Como funciona? 
El módulo tarifador cuenta con al menos 3 stores o almacenes de datos importantes a saber: Un respositorio con todos los datos de los vehiculos en donde figuran todos los vehiculos que se tienen en la actualidad, otro store con los destinos posibles y finalmente una matriz que cruza vehiculos, destino y precio. En lo sucesivo se explicará en detalle el funcionamiento y caracteristica de cada store. 

Es importante tener presente que estos tres stores definen la parametrización y la forma en como se determinan el costo de los servicios por lo cual toda información mal cargada o mal informada no generará un fallo per-se sino que tendrá un comportamiento no esperado.


# Google Maps como sistema de coordenadas primario 
El sistema de tarifación para los traslados toma como base una posición de origen y una posición de destino. Para calcular ambos puntos se utiliza el servicio de google Maps para determinar la geoposición tanto del origen como del destino. Esta caracteristica permite a la solución:

1. Poder determinar con exactitud tanto el punto de partida como de llegada evitando de esta forma malos entendidos al momento de prestar el servicio
2. Extender a mayores y diferentes destinos 

Todo el sistema de coordenadas de la solución se basa en cuatro puntos para determinar un poligono. Estos puntos se deben establecer como un sistema de ejes de coordenadas XY, es decir, que cada punto contiene minimamente dos coordenadas. Debido a que un poligono tiene al menos cuatro puntos y cada punto tiene dos coordendas XY finalmente para poder definir un poligono necesitaremos de 8 puntos. Estos puntos se definen en el sentido de las agujas del reloj. Al momento de definirlos una metodología es situarse en el mapa de google maps y dibujar mentalmente un área o poligono. Luego con el mouse seleccionamos cada uno de los puntos. Estos serán (siempre conservando este orden) 

1. Inferior izquierdo 
2. Superior izquierdo
3. Superior derecho
4. Inferior Derecho 

Para situar un ejemplo. El aeropuerto de denver tiene estas coordendas 

1. Inferior izquierdo = 39.842786, -104.686097 
2. Superior izquierdo = 39.870195, -104.685754 
3. Superior derecho   = 39.870590, -104.661206
4. Inferior Derecho   = 39.843576, -104.661721

Por lo cual esos cuatro puntos determinan finalmente el poligono donde estaría ubicado (par nuestros sistema) el Aeropuerto Internacional de Denver en EEUU. 

El sistema de coordenadas GPS es una pieza fundamental para el correcto funcionamiento de la aplicacion. Es importante tener el cuenta el sentido en como se agregan las coordendas. 

# Repositorio y/o almacen de destinos 

Este repositorio contiene cada uno de los destinos sobre los cuales se brinda servicio y sus respectivas 4 coodenadas como se mencionaba anteriormente. 


Como se presenta anteriormente en este repositorio no importa si se trata de un origen o de un destino sino que lo importante es definir claramente el destino y su ubicacion GPS. Aqui se deben definir TODOS los destinos sobre los cuales se presetará servicio en forma de cuadrante o bien de poligono.  Es importante tener presente que los identificadores debe ser UNICOS e IRREPETIBLES.

# Matriz de tarifacion
Una vez que los servicios han sido definidos (esperamos que correctamente) resta definir la matriz que actua como tarifador. Esta matriz contiene 6 atributos a saber 

1. Identificador del origen. Es el ID que esta establecido en el repositorio de destinos 
2. Identificador del destino. Es el ID que esta establecido en el repositorio de destinos
3. Cantidad maxima de pasajeros 
4. Tipo de Vehiculo
5. Tipo de Servicio (PRIVATE, REGULAR, EXCLUSIVE) 
6. Precio
