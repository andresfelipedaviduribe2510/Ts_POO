# Taller: Sistema de Cajero Automático (POO + TypeScript)

## Investigación Previa

Antes de escribir una sola línea de código, cada coder debe investigar los siguientes temas. El taller **no se puede completar correctamente** sin entender estos conceptos primero.

---

### 1. Tipos de Arquitectura de Software

Investiga qué es una arquitectura de software y cuáles son los patrones más comunes. Para cada uno, responde: **¿qué es?** y **¿cuándo conviene usarla?**

| Arquitectura | Descripción breve | ¿Cuándo usarla? |
|---|---|---|
| **Monolítica** | Toda la aplicación en un solo bloque | ? |
| **Capas (Layered)** | Separación en capas: presentación, lógica, datos | ? |
| **Microservicios** | Servicios pequeños e independientes | ? |
| **MVC** | Model – View – Controller | ? |
| **Hexagonal / Ports & Adapters** | Lógica de negocio aislada del mundo exterior | ? |

> **Pista:** Para este taller usarás una arquitectura por **capas**. ¿Por qué crees que tiene sentido aquí?

---

### 2. Genéricos en TypeScript

Investiga qué son los genéricos (`generics`) en TypeScript y para qué sirven.

Preguntas guía:
- ¿Qué problema resuelven los genéricos?
- ¿Cuál es la diferencia entre usar `any` y usar un genérico `<T>`?
- ¿Cómo se declara una función genérica? ¿Y una clase genérica?
- ¿Qué son las **constraints** (`<T extends ...>`)?

```ts
// Ejemplo básico para entender la idea
function identidad<T>(valor: T): T {
  return valor;
}
```

---

## El Reto

Construir un sistema de cajero automático que gestione cuentas bancarias. El sistema debe permitir:

- ✅ Consultar saldo de una cuenta
- ✅ Depositar dinero
- ✅ Retirar efectivo
- ✅ Validar que el cajero tenga fondos suficientes
- ✅ Validar que el usuario no retire más de lo que tiene en su cuenta

---

## Requisitos Técnicos

### Obligatorios

- [ ] **Al menos una clase** que modele una entidad del dominio (por ejemplo, `CuentaBancaria`, `Cajero`, etc.)
- [ ] **Al menos una función genérica** que tenga sentido en el contexto del sistema
- [ ] Uso de **interfaces** o **tipos** para definir contratos
- [ ] Manejo de **errores** con mensajes claros al usuario
- [ ] El código debe **compilar sin errores** con TypeScript estricto (`strict: true`)

### Recomendados

- [ ] Separar el código en capas o módulos con responsabilidad clara
- [ ] Aplicar principios básicos de POO: encapsulamiento, al menos un método público y atributos privados
- [ ] Agregar al menos un caso de prueba manual documentado en consola

---

## Estructura Sugerida del Proyecto

```
cajero-automatico/
├── src/
│   ├── models/
│   │   └── CuentaBancaria.ts      # Clase principal
│   ├── services/
│   │   └── CajeroService.ts       # Lógica de negocio
│   ├── utils/
│   │   └── validaciones.ts        # Función(es) genérica(s)
│   └── index.ts                   # Punto de entrada / pruebas
├── tsconfig.json
├── package.json
└── README.md
```

>  Esta estructura es una **sugerencia**. Puedes organizarlo diferente siempre que justifiques tu decisión de arquitectura.

---

## Pistas (sin spoilers)

<details>
<summary>Pista 1 — La clase CuentaBancaria</summary>

Piensa qué atributos necesita una cuenta: titular, número de cuenta, saldo. ¿Cuáles deberían ser privados? ¿Qué métodos expones públicamente?

</details>

<details>
<summary>Pista 2 — El Cajero</summary>

El cajero también tiene un estado propio: ¿cuánto efectivo tiene disponible? Eso es independiente del saldo de cada usuario.

</details>

<details>
<summary>Pista 3 — La función genérica</summary>

Piensa en una utilidad que pueda trabajar con diferentes tipos de datos. Por ejemplo: una función que valide que un valor no sea nulo/undefined, o una función que busque un elemento en un arreglo por un criterio. Ambas pueden ser genéricas y útiles en este contexto.

</details>

---


## Recursos de Apoyo

- [TypeScript Handbook — Generics](https://www.typescriptlang.org/docs/handbook/2/generics.html)
- [TypeScript Handbook — Classes](https://www.typescriptlang.org/docs/handbook/2/classes.html)
- [Patrones de Arquitectura de Software — refactoring.guru](https://refactoring.guru/es/design-patterns)
- [Arquitectura en capas explicada](https://www.oreilly.com/library/view/software-architecture-patterns/9781491971437/ch01.html)

---

>  *La idea no es solo que funcione — es que puedas explicar por qué lo estructuraste así.*
