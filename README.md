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