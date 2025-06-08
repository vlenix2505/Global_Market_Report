# 📊 Global Market Power BI Report

_Vista de la Pantalla Resumen_

![ProyectoReporte_page-0002](https://github.com/user-attachments/assets/7e7932c7-0054-4a78-8690-718d50559d80)


## 🏢 Project Background

Este proyecto corresponde a la evaluación final del curso de Inteligencia de Negocios con Power BI. Se centra en el análisis de datos del sector retail de la empresa Global Market. El objetivo fue desarrollar un dashboard visualmente atractivo y funcional para la alta dirección, permitiendo evaluar ventas, desempeño por producto, cliente y vendedor, así como identificar oportunidades de mejora en la estrategia comercial.

Puedes acceder al dashboard online en este [enlace](https://app.powerbi.com/view?r=eyJrIjoiZjM3YTcwYzItYWFkYy00NzU0LTliMWItNzE5ZjNiNDQyZjEzIiwidCI6IjBlMGNiMDYwLTA5YWQtNDlmNS1hMDA1LTY4YjliNDlhYTFmNiIsImMiOjR9&pageName=2a594790742e802d06a0)

## 🗃️ Data Structure

Se trabajó con las siguientes tablas:

* **DimCliente**: Información demográfica y de clasificación de clientes.
* **DimDistritos**: Ubicación geográfica de ventas.
* **DimProducto**: Detalles de cada producto vendido.
* **DimLinea**: Categorías o líneas de productos.
* **DimVendedor**: Datos de los vendedores.
* **FactHistoricoVentas y FactActualVentas**: Datos transaccionales con precios, cantidades, fechas y pedidos.

Estas tablas se integraron mediante relaciones definidas por claves, respetando buenas prácticas de modelado en estrella.

_Modelo de datos_

![image](https://github.com/user-attachments/assets/9bb0192c-cfe3-4c6b-a76b-b830910e1ab7)


## 📈 Executive Summary

El informe revela hallazgos claves:

* Las mujeres representan la mayor proporción del total de ventas (S/ 909 millones) comparado con los hombres (S/ 85 millones).
* Los distritos con mayor volumen de ventas incluyen Tauriija, Islay y Lince.
* Productos líderes en ventas incluyen ZEPOL UNGUENTO y ARTROSAMIN.
* La línea **Zetelox** lidera en ventas (S/ 243 millones).
* El KPI “Total de Ventas” experimentó una recuperación significativa en 2023 con un incremento de 51.46% respecto al año anterior.

## 🎨 Diseño Visual

El diseño de la interfaz y disposición visual del dashboard fue previamente prototipado utilizando **Figma**, lo que permitió estructurar los elementos gráficos, paleta de colores, distribución de KPIs y zonas de interacción de manera intuitiva y alineada con los objetivos del negocio. Esta etapa de diseño facilitó una implementación coherente y estética dentro de Power BI.

_Vista de la Portada_

![ProyectoReporte_page-0001](https://github.com/user-attachments/assets/d3766390-3fe1-40eb-9edf-61036b2ac89d)


## ⚙️ Technical Implementation

Se utilizó **Python** en el entorno de **Google Colab** para el tratamiento y limpieza del archivo **DimProducto**, el cual contenía desorden e inconsistencias en los campos relacionados a productos farmacéuticos. Estas inconsistencias dificultaban su análisis, comparación y clasificación, por lo que se aplicaron procesos de normalización y extracción estructurada.

### 🧪 Procesos aplicados:

- **Estandarización de texto**: Conversión a mayúsculas, eliminación de caracteres especiales (como asteriscos, comas innecesarias) y normalización de espacios.
- **Unificación de unidades de medida**: Ej. reemplazo de "GR" por "G", estandarización de "SUSP." como "SUSP".
- **Separación de dosis y unidades**: Extracción de información como `25 MG`, `10 ML`, `1 G`, entre otros, desde descripciones complejas.
- **Detección de formatos especiales**: Manejo de patrones como `10 CC 22 1.5`, tallas `7 1/2`, o combinaciones con múltiples números y unidades.
- **Tratamiento de excepciones**: Inclusión de listas de productos con reglas personalizadas para evitar errores de interpretación (ej. `MANZATIN-E INFANTIL`, `DEKOFEN 25MG`, `RARPEZIT-600`).
- **Extracción antes de paréntesis**: En casos donde los nombres incluían información del laboratorio entre paréntesis (ej.`VIRO-GIP JBE GIPE Y TOS 120 ML ( VIJOSA)`), se extrajo solo la parte relevante previa al paréntesis.

### 🧾 Ejemplos del resultado:

_Antes de la limpieza_

![image](https://github.com/user-attachments/assets/4ffc39e5-329d-4282-8962-7e491b8213e2)

_Después de la limpieza_

![image](https://github.com/user-attachments/assets/594973f1-1c85-4bb1-83b5-352e3ca55bc0)

Estos pasos permitieron estructurar adecuadamente los datos, facilitando su análisis posterior y reduciendo significativamente los errores de interpretación.

* **Power BI Desktop** fue la herramienta empleada para la carga, modelado y visualización de datos.

* Se crearon medidas DAX para KPIs como:

  * Total Ventas = SUM('Ventas'\[PrecioUnitario] \* 'Ventas'\[CantidadFacturada])
  * Promedio por Cliente, Producto y Factura.

* Se diseñaron tres lienzos temáticos:

  1. **Resumen Comercial General**: Brinda una vista agregada del estado general del negocio. Se presentan los valores acumulados y promedios de KPIs como total de ventas, cantidad de pedidos, ventas promedio por factura, clientes activos y productos únicos. Incluye gráficos de evolución anual, mensual y por sexo, así como distribución geográfica (Top distritos).

   _Pantalla Resumen Comercial_
  
   ![ProyectoReporte_page-0002](https://github.com/user-attachments/assets/994c7020-ad71-4e3f-9760-2893d9cede09)


  2. **Análisis de Productos y Clientes**: Este lienzo permite explorar la composición de las ventas en función de las líneas de producto y clientes. Incluye visualizaciones de los productos más vendidos, ventas promedio por producto y cliente, número de clientes activos por sexo y rango etario, y comparativas entre volumen de ventas y variedad de productos.

  _Pantalla Análisis de Productos y Clientes_

  ![ProyectoReporte_page-0003](https://github.com/user-attachments/assets/dd25c960-45a3-4ec1-8c18-080fc2db0040)


  3. **Desempeño de Vendedores**: Presenta el rendimiento comercial del equipo de ventas. Se muestra el total de ventas por vendedor, promedio por factura, cantidad de facturas emitidas, pedidos gestionados y comparativa de ventas por periodo. Permite identificar a los vendedores más eficientes y sus tendencias a lo largo del tiempo.

  _Pantalla Desempeño Vendedores_
 
  ![ProyectoReporte_page-0004](https://github.com/user-attachments/assets/a870ad47-4cbe-4798-9a34-d31efc42260a)


* Se implementaron filtros por fechas, productos, sexo y ubicación, con elementos visuales como gráficos de columnas, líneas, tablas comparativas y tarjetas de KPI.

## 📌 Conclusiones

* La herramienta Power BI permitió integrar diversas fuentes y visualizar insights accionables.
* Se identificaron oportunidades de mejora geográfica y demográfica.
* La implementación de KPIs permite monitorear el cumplimiento de metas y segmentar estrategias de ventas.
* El dashboard es una herramienta escalable para futuras iteraciones, incluyendo análisis predictivos y benchmarking interno.
