# PRD.md

## Contexto y objetivo
AI Personalized Travel Planner es una aplicación web que genera itinerarios de viaje personalizados a partir de información estructurada proporcionada por el usuario. El sistema transforma datos como destino, duración del viaje, estilo de viaje, presupuesto y preferencias en un plan diario claro con recomendaciones de lugares, imágenes y descripciones breves.

El objetivo del MVP es demostrar cómo la IA puede generar itinerarios estructurados y visualmente atractivos para ayudar a los viajeros a planificar un viaje de forma rápida sin necesidad de investigar manualmente qué visitar.

---

# Usuario objetivo

Viajeros que quieren visitar una ciudad pero no saben cómo organizar su itinerario.

Usuarios principales:

- Viajeros individuales  
- Parejas  
- Pequeños grupos de amigos  
- Familias  

Caso típico:

Un usuario quiere visitar una ciudad durante varios días, introduce sus preferencias y recibe un itinerario diario con lugares recomendados.

---

# Caso de uso principal

Un usuario introduce información básica del viaje (destino, duración, estilo de viaje, presupuesto y preferencias) y el sistema genera automáticamente un itinerario organizado por días con recomendaciones de lugares turísticos, imágenes del lugar y descripciones breves.

---

# Flujo principal del usuario

## Paso 1 — Travel Profile

El usuario introduce información del viaje:

Campos:

- Destination (texto)
- Number of travelers (número)
- Age range (dropdown)
- Trip duration (número de días)
- Budget level (dropdown)
- Daily activity pace (dropdown)

Opciones de presupuesto:

- Low  
- Medium  
- High  

Daily activity pace:

- Relaxed (2–3 actividades por día)
- Balanced (3–5 actividades por día)
- Packed (5–7 actividades por día)

Botón:

Generate Trip

---

## Paso 2 — Travel Style

El usuario selecciona **uno o varios estilos de viaje**.

La interfaz debe permitir selección múltiple (multi-select).

Opciones disponibles:

- Cultural
- Adventure
- Relaxation
- Foodie
- Nightlife
- Family

El usuario puede seleccionar **uno o más estilos** que describan su tipo de viaje.

Ejemplos:

Cultural + Foodie  
Relaxation + Family  
Adventure + Nightlife

Botón:

Next

---

## Paso 3 — Travel Preferences

El usuario selecciona intereses mediante checkboxes.

Opciones:

- Culture
- Local food
- Museums
- Nature
- Nightlife
- Shopping
- Architecture
- Beaches
- Local markets

El usuario puede seleccionar múltiples opciones.

Botón:

Generate Itinerary

---

## Paso 4 — Resultados

El sistema genera:

1. Trip Style Summary  
2. Itinerary by Day  

---

# Estructura de la página de resultados

## Trip Style Summary

Debe mostrar:

- Destination
- Number of travelers
- Trip duration
- Selected travel styles
- Budget
- Daily pace
- Selected interests

Ejemplo:

Destination: Barcelona  
Travelers: 2  
Duration: 4 days  

Travel Styles: Cultural, Foodie  

Budget: Medium  
Daily Pace: Balanced  

Focus: Culture, Museums, Local Food  

---

# Itinerary Structure

El itinerario se organiza por día.

Ejemplo:

Day 1  
Day 2  
Day 3  
Day 4  

---

# Daily Activities

Número de actividades según el ritmo seleccionado:

Relaxed  
2–3 actividades por día  

Balanced  
3–5 actividades por día  

Packed  
5–7 actividades por día  

---

# Estructura de cada actividad

Cada actividad debe representarse como una tarjeta visual.

Cada tarjeta incluye:

- Nombre del lugar
- Imagen del lugar
- Descripción breve (1–2 frases)

Ejemplo:

Sagrada Familia  

Description:  
Sagrada Familia is Barcelona's iconic basilica designed by Antoni Gaudí and one of the most recognizable landmarks in the world.

---

# Reglas para imágenes de atracciones

Cada atracción recomendada debe incluir una imagen real del lugar específico.

Reglas:

- Cada atracción del itinerario debe estar acompañada por una imagen representativa del lugar.
- La imagen debe corresponder al nombre específico de la atracción cuando sea posible.

Ejemplos:

Sagrada Familia → imagen de Sagrada Familia  
Park Güell → imagen de Park Güell  
Picasso Museum → imagen del museo  

El sistema debe evitar:

- usar imágenes genéricas del destino cuando existe una atracción concreta
- repetir la misma imagen para múltiples atracciones diferentes
- mostrar imágenes que no correspondan al lugar recomendado

Si la actividad no corresponde a un lugar concreto (por ejemplo "Tapas Dinner" o "Local Market"):

El sistema puede mostrar una imagen representativa de la experiencia dentro del destino.

Ejemplo:

Tapas Dinner → imagen de tapas en Barcelona

---

# Fuentes de imágenes

Las imágenes deben obtenerse de plataformas de fotografía gratuitas.

Fuentes permitidas:

- Unsplash
- Pexels

El sistema debe buscar imágenes utilizando el nombre del lugar turístico.

Ejemplo de búsqueda:

"Sagrada Familia Barcelona"  
"Park Güell Barcelona"  
"Picasso Museum Barcelona"

---

# UI Design

Estilo visual:

- Clean
- Minimal
- Card-based
- Modern dashboard layout

---

# Páginas de la aplicación

## Página 1 — Travel Profile

Formulario con campos:

- destination
- travelers
- age range
- duration
- budget
- daily pace

Botón:

Generate Trip

---

## Página 2 — Travel Style

Selección múltiple de estilos de viaje.

Opciones:

- Cultural
- Adventure
- Relaxation
- Foodie
- Nightlife
- Family

Botón:

Next

---

## Página 3 — Preferences

Checkboxes de intereses.

Botón:

Generate Itinerary

---

## Página 4 — Results

Secciones:

Top section  
Trip Style Summary

Main section  
Daily itinerary

Cada día muestra tarjetas de actividades.

---

# Exportación de itinerario

El usuario debe poder descargar el itinerario generado.

Botón:

Download PDF

El PDF debe incluir:

- Trip Style Summary
- Itinerary by Day
- Activity names
- Descriptions

Las imágenes pueden incluirse si están disponibles.

---

# Alcance del MVP

Incluye:

- Travel profile form
- Selección múltiple de travel styles
- Preference selection
- AI-generated itinerary
- Trip Style Summary
- Attraction cards con imagen
- Exportación a PDF

---

# Fuera del alcance del MVP

No incluye:

- reservas de hotel
- reservas de vuelos
- pagos
- cuentas de usuario
- mapas
- edición avanzada del itinerario
- guardar itinerarios

---

# Requisitos funcionales

FR-01  
El usuario puede introducir un destino.

FR-02  
El usuario puede introducir el número de viajeros.

FR-03  
El usuario puede seleccionar rango de edad.

FR-04  
El usuario puede definir duración del viaje.

FR-05  
El usuario puede seleccionar presupuesto.

FR-06  
El usuario puede seleccionar ritmo diario de actividades.

FR-07  
El usuario puede seleccionar **uno o varios estilos de viaje**.

FR-08  
El usuario puede seleccionar múltiples preferencias.

FR-09  
El sistema genera un itinerario personalizado.

FR-10  
El sistema organiza el itinerario por días.

FR-11  
Cada día contiene un número de actividades acorde al ritmo seleccionado.

FR-12  
Cada actividad se muestra como tarjeta con nombre, imagen y descripción.

FR-13  
El sistema muestra un Trip Style Summary.

FR-14  
El usuario puede descargar el itinerario como PDF.

FR-15  
Cada atracción recomendada debe incluir una imagen representativa del lugar específico cuando sea posible.

---

# Requisitos no funcionales

Rendimiento  
El itinerario debe generarse en menos de 5 segundos.

Fiabilidad  
La interfaz no debe mostrar tarjetas con imágenes rotas.

Compatibilidad  
Debe funcionar en navegadores modernos.

Accesibilidad  
Formularios y botones deben ser claros y utilizables.

Consistencia visual  
Todas las tarjetas deben mantener tamaño y estilo consistente.

---

# Métricas de éxito

- 70% de los usuarios completan el flujo hasta ver el itinerario
- tiempo medio de generación inferior a 5 segundos
- al menos 1 itinerario generado por usuario
- al menos 20% de usuarios descargan el PDF

---

# Dependencias y riesgos

Dependencias:

- API de IA para generar itinerarios
- plataformas de imágenes (Unsplash o Pexels)
- librería de generación de PDF

Riesgos:

- imágenes no encontradas para algunos lugares
- resultados inconsistentes de la IA
- dependencia de APIs externas

---

# Suposiciones

- El MVP tendrá un solo tipo de usuario
- No se almacenarán itinerarios en base de datos
- Las imágenes se obtendrán dinámicamente desde APIs externas
- El sistema genera el itinerario mediante IA