# **Testing Plan — *School News Game Project***

## **1\. Overview**

Este plan describe cómo se probará el proyecto. Conecta requisitos, casos de prueba, resultados esperados y oportunidades de pruebas automatizadas en un sistema organizado.

## **2\. Requirements / User Stories**

* **US-1 — Ver noticias escolares**  
  * Acceptance Criteria:  
    * El usuario puede abrir la pestaña de noticias.  
    * Las noticias se muestran en orden cronológico.  
* **US-2 — Jugar minijuego educativo**  
  * Acceptance Criteria:  
    * El usuario puede iniciar el minijuego desde el menú principal.  
    * El puntaje se actualiza correctamente después de cada ronda.  
* **US-3 — Guardar progreso**  
  * Acceptance Criteria:  
    * El sistema guarda el puntaje y nivel alcanzado.  
    * El usuario puede recuperar su progreso al volver a iniciar sesión.

## **3\. Test Procedures**

### **Test Case T-1: Mostrar Noticias**

* **Related Requirement(s):** US-1  
* **Purpose:** Verificar que las noticias se despliegan correctamente.  
* **Setup:** El sistema tiene al menos 3 noticias cargadas.  
* **Test Steps:**  
  1. Abrir la pestaña de noticias.  
  2. Revisar el orden de las noticias.  
  3. Confirmar que cada noticia muestra título y fecha.  
* **Expected Result:** Las noticias aparecen en orden cronológico con título y fecha visibles.  
* **Automation Candidate:** Sí, porque es repetitivo y puede validarse con pruebas de interfaz automatizadas.

### **Test Case T-2: Minijuego Puntaje**

* **Related Requirement(s):** US-2  
* **Purpose:** Validar que el puntaje se actualiza correctamente.  
* **Setup:** Usuario inicia el minijuego con puntaje \= 0\.  
* **Test Steps:**  
  1. Jugar una ronda.  
  2. Revisar el puntaje mostrado.  
  3. Comparar con el puntaje esperado según reglas.  
* **Expected Result:** El puntaje aumenta según las reglas del juego.  
* **Automation Candidate:** Sí, porque se puede simular jugadas y validar resultados.

### **Test Case T-3: Guardar Progreso**

* **Related Requirement(s):** US-3  
* **Purpose:** Confirmar que el progreso se guarda y se recupera.  
* **Setup:** Usuario juega y alcanza nivel 2 con puntaje 50\.  
* **Test Steps:**  
  1. Salir del juego.  
  2. Volver a iniciar sesión.  
  3. Revisar nivel y puntaje.  
* **Expected Result:** El sistema muestra nivel 2 y puntaje 50\.  
* **Automation Candidate:** Sí, porque se puede automatizar con pruebas de base de datos y login.

## **4\. Expected Results**

* **Test T-1:** Noticias en orden cronológico con título y fecha.  
* **Test T-2:** Puntaje actualizado correctamente según reglas.  
* **Test T-3:** Progreso guardado y recuperado sin errores.

## **5\. Automated Test List**

* **T-1:** Automatizar validación de interfaz de noticias.  
* **T-2:** Automatizar simulación de jugadas y puntajes.  
* **T-3:** Automatizar pruebas de login y recuperación de progreso.

## **6\. Boundary & Edge Case Reference**

* **B-1 — Sin noticias cargadas**  
  * Related Requirement: US-1  
  * Expected Behavior: Mostrar mensaje “No hay noticias disponibles”.  
* **B-2 — Puntaje máximo alcanzado**  
  * Related Requirement: US-2  
  * Expected Behavior: El sistema no permite superar el límite y muestra mensaje de logro.  
* **B-3 — Usuario sin conexión al guardar progreso**  
  * Related Requirement: US-3  
  * Expected Behavior: Guardar localmente y sincronizar al reconectarse.

## **7\. Traceability Summary**

* **US-1** → T-1  
* **US-2** → T-2  
* **US-3** → T-3

## **8\. Plan Status**

* Last Updated: 08-12-2025  
* Requirements Covered: US-1, US-2, US-3  
* Requirements Not Covered Yet: Ninguno  
* Automated Tests Identified: T-1, T-2, T-3

