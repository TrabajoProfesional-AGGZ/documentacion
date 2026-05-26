# **Análisis de Requisitos**

En este documento se detallan todos los requisitos identificados para la plataforma de SocioUnido. Los requisitos se dividirán entre requisitos funcionales, dentro de los cuales habrá una categoría para cada uno de los microservicios de la plataforma; y requisitos no funcionales. Se desarrollará una breve explicación para cada uno de los requisitos, y al final del documento se podrá encontrar una matriz que contenga a todos los requisitos identificados. 

## **Generalidades**
Los requisitos van a estar representados por un código, y una numeración ascendente dentro de cada categoría. De un requisito pueden derivar otros. Estos requisitos derivados tendrán una numeración jerárquica, que dependerá de su antecesor. Los requisitos además pueden estar relacionados entre sí, sea por esta dependencia jerárquica, o por otras conexiones que serán detalladas en el análisis. Por último, los requisitos tendrán una prioridad con la que deben ser tratados. No todos los requisitos serán cubiertos para el Mínimo Producto Viable. Se delimitará claramente cuáles son los que entran en el alcance de este MVP.

### **Prioridades de requisitos**
Como se mencionó anteriormente, la prioridad de los requisitos va a ir del 1 al 4 según su influencia tanto en la plataforma como en el Mínimo Producto Viable. A continuación, una breve explicación de cada una:

| **Prioridad** | **Numeración** | **Explicación** |
| :---: | :---: | :---: |
| Alta | 1 | INSERTAR EXPLICACION |
| Media-Alta | 2 | INSERTAR EXPLICACION |
| Media-Baja | 3 | INSERTAR EXPLICACION |
| Baja | 4 | INSERTAR EXPLICACION |

### **Documentación de requisitos**
Los requisitos serán documentados de la siguiente forma: `<Tipo>-<Numeración>`
* **Tipo**: indica la categoría general del requisito:
    * **Requisitos Funcionales (RF)**: describen lo que el sistema debe hacer. Acciones, flujos y/o reglas de negocio que se deban cumplir.
    Dentro de los requisitos funcionales, habrán subtipos, según el área del negocio con la que se relacione el requisito. En caso de existir un subtipo, la documentación del requisito será: `<Tipo>-<Subtipo>-<Numeración>`. Se aclarará en cada caso el subtipo de requisito.
    * **Requisitos No Funcionales (RNF)**: describen cómo el sistema se debe comportar. Calidad del servicio y propiedades generales del sistema. 
* **Numeración**: jerárquica y ascendente. Se asignarán 2 números separados por un punto para cada requisito. El primer número indica la numeración respecto del **Tipo** de requisito (y **Subtipo** en caso de existir). El segundo número será para requisitos derivados, y solamente aumentará cuando existan esta clase de requisitos. En casos excepcionales, si un requisito derivado tiene a su vez derivaciones, se agregará un nuevo punto y un tercer número.
    * **Requisito no derivado**:  `X.0` donde `X` es el número correspondiente dentro del **Tipo** de requisito. Por ejemplo: `1.0`
    * **Requisito derivado**: `X.Y` donde `X` es de vuelta el número correspondiente dentro del **Tipo** e `Y` es la nueva numeración dentro de la jerarquía del requisito. Por ejemplo, el primer requisito derivado del `1.0` tendrá numeración `1.1`, el segundo tendrá numeración `1.2`, y el `n` requisito derivado tendrá numeración `1.n`
    * **Requisito derivado segundo (excepcional)**: como se mencionó anteriormente, son poco frecuentes. De todas formas, su numeración sigue la misma lógica que los anteriores: `X.Y.Z`, donde `X` e `Y` cumplen las mismas funciones que en los casos anteriores, y `Z` es la numeración dentro del requisito derivado. Por ejemplo: el primer requisito derivado del `1.1` será el `1.1.1`, el segundo tendrá `1.1.2`, y el `n` requisito derivado tendrá numeración `1.1.n`.


## **Requisitos Funcionales**
**Código de Tipo**: RF


### **SUBTIPO 1**
**Código de Subtipo**: 

### **SUBTIPO 2**
**Código de Subtipo**:

## **Requisitos No Funcionales**
**Código de Tipo**: RNF


## **Matriz de Requisitos Completa**

| **Requisito** | **Breve Explicación** | **Requisitos relacionados** | **Prioridad** |
| :---: | :---: | :---: | :---: |
| TT-X.Y | INSERTAR EXPLICACIÓN | --- | 1 a 4 |
