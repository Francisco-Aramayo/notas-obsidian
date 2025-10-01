## Teoría clase 1 - 18/8
### ¿Qué es el software?
El **software** es el conjunto de programas, instrucciones y datos que hacen que una computadora o dispositivo electrónico funcione y realice tareas. Dicho de forma simple, es la “parte intangible” de un sistema informático (a diferencia del **hardware**, que es la parte física).
>[!note]
>El software se ve como un elemento lógico, que se desarrolla y no se desgasta, pero si se deteriora

### Software genérico y software personalizado
El **software genérico** es una solución **preexistente y estandarizada**, creada para satisfacer las necesidades comunes de un mercado amplio (como Microsoft Office). Es **más económico y rápido de implementar**, pero ofrece **funcionalidades fijas y personalización limitada**, lo que puede obligar a la empresa a adaptar sus procesos al software.
Por otro lado el **software personalizado** es una solución **creada a medida** para satisfacer las necesidades únicas y específicas de una organización. Requiere mayor inversión inicial y más tiempo de desarrollo, pero se adapta perfectamente a los procesos de la empresa.
>[!note]
>Hoy en día se tiende a desarrollar genérico y luego se personaliza

### Clasificaciones de software
- Sistemas operativos
- Controladores de dispositivos
- Compiladores e intérpretes
- Entornos de desarrollo integrados
- Gestión empresarial
- Diseño y creatividad
- Productividad
Etc...
### ¿Qué es la ingeniería de software?
La aplicación de un enfoque sistemático, disciplinado y cuantificable al desarrollo, operación y mantenimiento del software.
Con esto se deja de ver al software como un arte o algo improvisado, si no más bien como una disciplina de **ingeniería rigurosa**, utilizando métodos, herramientas y procesos bien definidos para desarrollar software dentro del presupuesto y el plazo de manera eficiente y confiable.
### Participantes en el desarrollo de software
- **Cliente/Usuario** → quien necesita el software y define los requisitos.
    
- **Analista** → traduce las necesidades del cliente en especificaciones claras.
    
- **Diseñador/Arquitecto de software** → define la estructura y cómo se organizará el sistema.
    
- **Programador/Desarrollador** → escribe el código que hace funcionar el software.
    
- **Tester/QA (aseguramiento de calidad)** → prueba el software para detectar errores y asegurar que cumpla lo requerido.
    
- **Líder de proyecto / Scrum Master** → coordina al equipo, planifica tiempos y recursos.
    
- **Equipo de soporte/mantenimiento** → corrige errores y actualiza el software tras su entrega.
### Características de un ingeniero de software
### 🔧 **Técnicas**

- **Conocimientos sólidos en programación** (varios lenguajes y paradigmas).
    
- **Diseño y arquitectura de software** (estructuras, patrones, escalabilidad).
    
- **Manejo de bases de datos** y sistemas operativos.
    
- **Uso de metodologías de desarrollo** (ágiles, cascada, DevOps).
    
- **Capacidad de análisis y resolución de problemas**.
    

### 🤝 **Personales / Profesionales**

- **Trabajo en equipo** y buena comunicación con clientes y colegas.
    
- **Pensamiento lógico y analítico**.
    
- **Capacidad de aprender rápido**, dado que la tecnología evoluciona constantemente.
    
- **Responsabilidad y orientación a la calidad**.
    
- **Creatividad e innovación** para encontrar soluciones nuevas.
### ¿Qué es un requerimiento?
1. **Una condición o capacidad necesaria** para que un usuario resuelva un problema o logre un objetivo.
    
2. **Una condición o capacidad que un sistema debe poseer** para satisfacer un contrato, estándar, especificación u otro documento formal.
    
3. La **representación documentada** de esas condiciones o capacidades.
#### Fuentes de requerimientos
- **Usuarios finales** → quienes usarán el sistema en la práctica.
    
- **Cliente o patrocinador** → la persona o empresa que encarga y paga el software.
    
- **Expertos del dominio** → especialistas en el área donde se aplicará el sistema (ej: médicos, contadores).
    
- **Documentación existente** → manuales, procesos actuales, sistemas anteriores.
    
- **Normas, leyes y regulaciones** → requisitos legales o estándares que deben cumplirse.
    
- **Analistas y desarrolladores** → que detectan limitaciones técnicas y proponen requisitos.
    
- **Entorno y mercado** → tendencias, competencia, necesidades externas.
>[!quote]
>“Un _stakeholder_ es un individuo, equipo u organización con intereses en el desarrollo o funcionamiento de un sistema.”

### Elicitación de requerimientos
La **elicitación de requerimientos** es el **proceso de identificar**, **descubrir**, **recopilar y comprender las necesidades, expectativas y restricciones** que los stakeholders tienen respecto a un sistema de software.
#### Relación con los stakeholders
>[!note]
>- Los stakeholdes son la fuente principal de requerimientos
>- La elicitación implica entrevistarlos, observarlos o analizar sus procesos, para transformar sus necesidades en requerimientos documentados.
>- Sin particiáción activa de los stakeholders, es muy probable que los requerimientos sean incompletos o incorrectos
### **Puntos de vista en la Ingeniería de Software**

1. **Interactuador (o directo)**
    
    - Son los stakeholders que **interactúan directamente con el sistema**.
        
    - Ejemplo: un cajero que usa el software bancario, un estudiante que usa una plataforma educativa.
        
    - Aportan **requerimientos funcionales** (lo que el sistema debe hacer).
        
2. **Indirecto**
    
    - Son los que **no usan directamente el sistema, pero se ven afectados por él**.
        
    - Ejemplo: el jefe del cajero (necesita reportes), el departamento de contabilidad que recibe datos.
        
    - Aportan **requerimientos no funcionales** (restricciones de seguridad, rendimiento, informes).
        
3. **Dominio**
    
    - Representan el **conocimiento del área o contexto donde se aplica el software**.
        
    - Ejemplo: un médico en un sistema de salud, un abogado para un sistema legal.
        
    - Aportan **reglas de negocio, regulaciones y procesos específicos** que deben cumplirse.
#### Objetivos de la elicitación
1. Entender el problema o necesidad real del cliente/usuario.
2. Indentidicar qué debe hacer el sistema y bajo qué condiciones.
3. Lograr una visión compartida entre usuarios, analistas y desarrolladores.
4. Detectar restricciones, riesgos y propiedades.
5. Obtener información completa, clara y consistente para pasar a la explicación
#### Técnicas de elicitación de requerimientos
Algunas de las más comunes son:

- **Entrevistas** → diálogo directo con usuarios y clientes.
    
- **Encuestas/cuestionarios** → recopilar opiniones de muchos usuarios.
    
- **Observación** → ver cómo trabajan los usuarios en su entorno real.
    
- **Revisión de documentos** → analizar manuales, normas, procesos existentes.
    
- **Talleres o reuniones grupales (JAD)** → sesiones colaborativas con varios stakeholders.
    
- **Prototipos** → construir versiones preliminares para validar necesidades.
    
- **Tormenta de ideas (brainstorming)** → generar ideas de posibles funciones.
    
- **Historias de usuario / casos de uso** → describir interacciones entre usuario y sistema.

