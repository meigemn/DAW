# Constructor
## Planetas
---
En este programa, se practica y explica el uso de *constructures*,*atributos* y *metodos*

### Apartados
---
1. Código
2. Explicación *paquete* _planeta_
3. Explicación *clase* _Planeta_
4. Constructor
5. Metodos
  * Imprimir
  * Calcular densidad
  * Determine exterior o no
6. Método Main

### 1. Codigo
``` java
package planeta;

public class Planeta {
	private String nombre;//valor inicializado
	private int cantidadSatelites;//valor inicializado
	private double masaPlaneta;//valor inicializado
	private double volumenPlaneta;//valor inicializado
	private int diametro;//valor inicializado
	private int distanciaSol;//valor inicializado
	private TiposPlanetas tiposPlanetas;
	private boolean observable=false;
	
	
	public Planeta(String nombre, int cantidadSatelites, double masaPlaneta, double volumenPlaneta, int diametro,
			int distanciaSol, TiposPlanetas tiposPlanetas, boolean observable) {
		this.nombre = nombre;
		this.cantidadSatelites = cantidadSatelites;
		this.masaPlaneta = masaPlaneta;
		this.volumenPlaneta = volumenPlaneta;
		this.diametro = diametro;
		this.distanciaSol = distanciaSol;
		this.tiposPlanetas = tiposPlanetas;
		this.observable = observable;
	}
	
	public void impresionDeDatos() {
		System.out.println("Nombre del planeta = " + nombre);
		System.out.println("Cantidad de satélites = "+ cantidadSatelites);
		System.out.println("Masa del planeta = " + masaPlaneta);
		System.out.println("Volumen del planeta = " + volumenPlaneta);
		System.out.println("Diámetro del planeta = "+ diametro);
		System.out.println("Distancia al sol = " + distanciaSol);
		System.out.println("Tipo de planeta = " + tiposPlanetas);
		System.out.println("Es observable = " + observable);
		System.out.println("Densidad del planeta = " + densidad(masaPlaneta, volumenPlaneta) );
		System.out.println("Es planeta exterior = "+ esExterior(distanciaSol));
		System.out.println("");
	}	
		
	
	public double densidad(double masaPlaneta, double volumenPlaneta) {
		return masaPlaneta/volumenPlaneta;
	}
	
	//metodo que determine si el planeta es exterior. Es exterior si está más lejos de 3.4UA
	
	public boolean esExterior(double distanciaSol){
		if(distanciaSol>(3.4*149597870)) {
			return true;	
		}else {
			return false;
		}
	}

	public static void main(String[] args) {
		Planeta planeta1=new Planeta("Tierra", 1, 5.9736E24, 1.0832E12, 12742, 149597870, TiposPlanetas.TERRESTRE, true);//Objeto dentro del main
		Planeta planeta2=new Planeta("Júpiter", 79, 1.899E27, 1.4313E15, 139820, 750000000, TiposPlanetas.GASEOSO, true);
		
		planeta1.impresionDeDatos(); //Objeto y lo que hace ese objeto(con el metodo)
		planeta2.impresionDeDatos();
		
		planeta1.esExterior(0);
		planeta2.esExterior(0);
	}

}

```
### 2. Explicación *paquete* _planeta_
Creamos este paquete donde ubicaremos las *clases* `Planeta.java` y `TiposPlanetas`
---
### 3. Explicación *clase* _Planeta_
Dentro del _paquete planeta_ mencionado anteriormente, creamos una clase pública llamada *Planeta*.
> Si imaginamos un planeta, podemos pensar en diferentes apartados que lo convierten en un planeta. En nuestro caso, los apartados que componen a un planeta serán:
>  * Nombre
>  * Cantidad de satélites
>  * Masa 
>  * Volumen
>  * Diametro
>  * Distancia con el Sol
>  * Si es Gaseoso, Terrestre o Enano
>  * Si es observable o no
> Estos apartados deben ser especificados su tipo de valor previamente, del siguiente modo
``` java
package planeta;

public class Planeta {
	private String nombre;//valor inicializado
	private int cantidadSatelites;//valor inicializado
	private double masaPlaneta;//valor inicializado
	private double volumenPlaneta;//valor inicializado
	private int diametro;//valor inicializado
	private int distanciaSol;//valor inicializado
	private TiposPlanetas tiposPlanetas;
	private boolean observable=false;

```
La clase `Planeta`, es accesible porque es pública, sin embargo sus atributos son `privados`

---
### 4. Constructor
El constructor en este caso tendría este aspecto:
``` java
public Planeta(String nombre, int cantidadSatelites, double masaPlaneta, double volumenPlaneta, int diametro,
			int distanciaSol, TiposPlanetas tiposPlanetas, boolean observable) {
		this.nombre = nombre;
		this.cantidadSatelites = cantidadSatelites;
		this.masaPlaneta = masaPlaneta;
		this.volumenPlaneta = volumenPlaneta;
		this.diametro = diametro;
		this.distanciaSol = distanciaSol;
		this.tiposPlanetas = tiposPlanetas;
		this.observable = observable;
	}
```
En primer lugar nos encontramos 
``` java
public Planeta(String nombre, int cantidadSatelites, double masaPlaneta, double volumenPlaneta, int diametro,
			int distanciaSol, TiposPlanetas tiposPlanetas, boolean observable) {
```
Primero entendemos que estamos usando la clase pública *Planeta*. Dentro de esta clase, utilizaremos los atributos `(String nombre, int cantidadSatelites, double masaPlaneta, double volumenPlaneta, int diametro,
			int distanciaSol, TiposPlanetas tiposPlanetas, boolean observable)`
Posteriormente, a esos atributos le daremos un valor, que serán las variables declaradas al principio de código.
> Podriamos imaginarnos a un constructor como una plantilla: `this.nombre` `=``nombre` nos quiere decir que la variable del principio *nombre* tendrá el valor a partir de lo que le den en el atributo _nombre_ de este constructor.
> Sabemos que queremos crear varios planetas, esos planetas compartiran todas las características que los hacen planetas, pero todos tendrán diferentes valores. Para no repetir el proceso tantas veces, creamos esta plantilla que posteriormente podremos reutilizar

 ---
### 5. Metodos :Imprimir, Calcular densidad, exterior o no

### Imprimir
Código
``` java
public void impresionDeDatos() {
		System.out.println("Nombre del planeta = " + nombre);
		System.out.println("Cantidad de satélites = "+ cantidadSatelites);
		System.out.println("Masa del planeta = " + masaPlaneta);
		System.out.println("Volumen del planeta = " + volumenPlaneta);
		System.out.println("Diámetro del planeta = "+ diametro);
		System.out.println("Distancia al sol = " + distanciaSol);
		System.out.println("Tipo de planeta = " + tiposPlanetas);
		System.out.println("Es observable = " + observable);
		System.out.println("Densidad del planeta = " + densidad(masaPlaneta, volumenPlaneta) );
		System.out.println("Es planeta exterior = "+ esExterior(distanciaSol));
		System.out.println("");

```
Como no devuelve nada (no realiza ninguna operación más que imprimir), declaramos como `void`
En el siguiente ejemplo: `System.out.println("Nombre del planeta = " + nombre);`, `+ nombre` hace referencia a la variable declarada al inicio.

### Densidad
```java
public double densidad(double masaPlaneta, double volumenPlaneta) {
		return masaPlaneta/volumenPlaneta;
	}
```
Para calcular la densidad, creamos un método que nos divida la masa entre el volumen.
> Con los *atributos* `double masaPlaneta`, y `double volumenPlaneta`, devuelve el resultado que da divir el valor de la *variable* `masaPlaneta` y `volumenPlaneta`.
> Aunque en este caso atributo y variable coincidan en nombre no tiene por qué ser así.

### Exterior o no
Este método determina si el planeta es exterior o no según una medida delongitud, si es superada se entiende que es exterior
``` java
public boolean esExterior(double distanciaSol){
		if(distanciaSol>(3.4*149597870)) {
			return true;	
		}else {
			return false;
		}
	}
```
> Lo que se crea aquí,`public boolean esExterior(double distanciaSol)` que es un valor de tipo  _boolean_, tomará la variable *distanciaSol* y mediante un _if_ determinará si se cumplen o no las condiciones.

### 6. Método Main
```java
public static void main(String[] args) {
		Planeta planeta1=new Planeta("Tierra", 1, 5.9736E24, 1.0832E12, 12742, 149597870, TiposPlanetas.TERRESTRE, true);//Objeto dentro del main
		Planeta planeta2=new Planeta("Júpiter", 79, 1.899E27, 1.4313E15, 139820, 750000000, TiposPlanetas.GASEOSO, true);
		
		planeta1.impresionDeDatos(); //Objeto y lo que hace ese objeto(con el metodo)
		planeta2.impresionDeDatos();
		
		planeta1.esExterior(0);
		planeta2.esExterior(0);
	}

```
Podemos separar el código en: 
```java
public static void main(String[] args) {
```
> Declaramos el método Main, donde a partir de las clases y el constructor anteriormente creados, podremos crear objetos.
> En nuestro caso los objetos serán diferentes planetas. para referirnos a ellos usaremos `planeta1` y `planeta2`.
```java
Planeta planeta1=new Planeta("Tierra", 1, 5.9736E24, 1.0832E12, 12742, 149597870, TiposPlanetas.TERRESTRE, true);
```
> Como si de un `Scanner`se tratase , Dentro de la clase Planeta, creamos el objeto planeta1. Este objeto tendrá los atributos entre paréntesis. Los valores que le demos, darán valor sentido alas variables anteriormente creadas, gracias a esta especie de "plantilla" llamada constructor.
> Si los ponemos uno cerca del otro quizá se entienda mejor:
``` java
public Planeta(String nombre, int cantidadSatelites, double masaPlaneta, double volumenPlaneta, int diametro,
			int distanciaSol, TiposPlanetas tiposPlanetas, boolean observable) {
		this.nombre = nombre;
		this.cantidadSatelites = cantidadSatelites;
		this.masaPlaneta = masaPlaneta;
		this.volumenPlaneta = volumenPlaneta;
		this.diametro = diametro;
		this.distanciaSol = distanciaSol;
		this.tiposPlanetas = tiposPlanetas;
		this.observable = observable;
	}
```

Una vez creado el objeto y los métodos, podemos trabajar con ambos de la siguiente manera:

```java
    planeta1.impresionDeDatos(); //Objeto y lo que hace ese objeto(con el metodo)
		planeta2.impresionDeDatos();
		
		planeta1.esExterior(0);
		planeta2.esExterior(0);
	}
```
> Con el `planeta1`, usa este método `impresionDeDatos`.
> A partir de los datos dados en `Planeta planeta1=new Planeta("Tierra", 1, 5.9736E24, 1.0832E12, 12742, 149597870, TiposPlanetas.TERRESTRE, true);` el `método impresionDeDatos` trabajará con unos valores u otros.


  
  
