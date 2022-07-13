# Notas Sección 2: Clean Code y Deuda Técnica
___

#### Deuda Técnica

Es la falta de calidad en el código, que genera una deuda que repercutirá en costos futuros que usualmente son costos económicos y son producto de tiempo en: 

 - Realizar mantenimientos. 
 - Refactorizar código.
 - Comprender el código. 
 - Adicional en la transferencia de código. 

![deudaTecnica](/src/images/deuda%20tecnica.PNG)

Caer en deuda técnica es normal y a menudo es inevitable. 

La dueda técnica se paga con refactorización, el cual es un proceso que tiene como objetivo mejorar el código sin alterar su comportamiento para que sea más entendible y tolerante a cambios. 

Para la factorización es imprescindible que cuente con pruebas automáticas. 

La mala calidad en el software siempre la acaba pagando o asumiendo alguien, ya se el cliente, proveedor con recursos o el propio desarrollador dedicando tiempo a refactorizar o malgastando tiempo programando sobre un sistema frágil. 

#### Nombres Pronunciables y Expresivos

Mal ❌

    const n        = 53;
    const tx       = 0.15;
    const cat      = 'T-Shirts';
    const ddmmyyyy = new Date('August 15, 1996 00:00:00');
 
Mejor ✅

    const numberOfUnits = 53;
    const tax           = 0.15;
    const category      = 'T-Shirts';
    const birthDate     = new Date('August 15, 1996 00:00:00');

#### Ausencia de Información Técnica en Nombres

Es la implementación que esa clase o interfaz está realizando, se debe evitar que el nombre no contenga información técnica en ellos. 

Mal ❌

    class AbstractUser { };
    class UserMixin { };
    class UserImplementation { };
    interface UserInterface { };

Mejor ✅
    
    class User { };
    interface User { };

#### Nombres de Variables según el Tipo de Dato

__`Arreglos - Arrays`__

Mal ❌

    const fruit = ['manzana', 'platano', 'fresa'];

Mejor ✅

    const fruitList = ['manzana', 'platano', 'fresa'];

O ✅
    
    const fruits = ['manzana', 'platano', 'fresa'];

O Mucho Mejor ✅

    const fruitNames = ['manzana', 'platano', 'fresa'];

__`Booleanos - Booleans`__

Mal ❌

    const open     = true;
    const write    = true;
    const fruit    = true;
    const active   = false;
    const noValues = true;
    const notEmpty = true;

Mejor ✅

    const isOpen     = true;
    const canWrite   = true;
    const hasFruit   = true;
    const isActive   = false;
    const hasValues  = false;
    const isEmpty    = false;

__`Números`__

Mal ❌

    const fruits = 3;
    const cars   = 10;

Mejor ✅

    const maxFruits   = 5;
    const minFruits   = 1;
    const totalFruits = 3;
    const totalOfCars = 5;

__`Funciones - functions`__

Deben de construirse usando el verbo que representa la acción seguido de un sustantivo, el cual deben ser descriptivos y concisos. 

Mal ❌

    createUserIfNotExists();
    updateUserIfNotEmpty();
    sendEmailIfFieldsValid();

Mejor ✅

    createUser();
    updateUser();
    seendEmail();

- Se prioriza que la simplicidad es fundamental de una función. 
- Las funciones deben tener un tamaño reducido. 
- Se recomienda hacer funciones de una sola línea sin causar complejidad. 
- Se recomienda tener máximo 20 líneas de código. 
- Se debe evitar el uso del `else`.
- Se debe priorizar el uso de la condicional ternaria. 

#### Clases

Las clases deben estar formadas por frases de sustantivo o por un sustantivo, se debe evitar nombre genéricos. 

El nombre es lo má importate de la clase y usar UpperCamelCase.

Mal ❌

    class Manager {};
    class Data {};
    class Info {};
    class Individual {};
    class Processor {};
    class SpecialMonsterView {};


Más palabas `!==` mejor nombre.

    class SpecialViewingCaseMonsterManagerEventsHandlerActivitySingleton {};

Para determinar si es un buen nombre a la clase: 

1. ¿Qué hace exactamente la clase?
2. ¿Cómo exactamente esta clase realica la tarea?
3. ¿Hay algo específico sobre su ubicación? 

#### Nombre de Funciones, Argumentos y Parámetros

Se recomienda que en una función tenga máximo 3 parámetro posicionales.

Bien ✅

    function sendEmail( toWhom: string, from: string, body: string ): boolean {};

Mal ❌

    function sendEmail( 
        toWhom : string, 
        from   : string, 
        body   : string,
        subject: string, 
        apikey : string
    ): boolean {};

Otro ejemplo:

![parametros](/src/images/parametros.PNG)