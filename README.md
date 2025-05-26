## 📊 Global Market Power BI Report

_Vista de la Página Resumen_

![ProyectoReporte_page-0002](https://github.com/user-attachments/assets/94d43fd8-5cba-4eca-88d5-9e4e20cda7a7)


### 🏢 Project Background

Este proyecto corresponde a la evaluación final del curso de Inteligencia de Negocios con Power BI. Se centra en el análisis de datos del sector retail de la empresa Global Market. El objetivo fue desarrollar un dashboard visualmente atractivo y funcional para la alta dirección, permitiendo evaluar ventas, desempeño por producto, cliente y vendedor, así como identificar oportunidades de mejora en la estrategia comercial.

---

### 🗃️ Data Structure

Se trabajó con las siguientes tablas:

* **DimCliente**: Información demográfica y de clasificación de clientes.
* **DimDistritos**: Ubicación geográfica de ventas.
* **DimProducto**: Detalles de cada producto vendido.
* **DimLinea**: Categorías o líneas de productos.
* **DimVendedor**: Datos de los vendedores.
* **FactHistoricoVentas y FactActualVentas**: Datos transaccionales con precios, cantidades, fechas y pedidos.

Estas tablas se integraron mediante relaciones definidas por claves, respetando buenas prácticas de modelado en estrella.

---

### 📈 Executive Summary

El informe revela hallazgos claves:

* Las mujeres representan la mayor proporción del total de ventas (S/ 909 millones) comparado con los hombres (S/ 85 millones).
* Los distritos con mayor volumen de ventas incluyen Tauriija, Islay y Lince.
* Productos líderes en ventas incluyen ZEPOL UNGUENTO y ARTROSAMIN.
* La línea **Zetelox** lidera en ventas (S/ 243 millones).
* El KPI “Total de Ventas” experimentó una recuperación significativa en 2023 con un incremento de 51.46% respecto al año anterior.

---

### ⚙️ Technical Implementation

* **Power BI Desktop** fue la herramienta empleada para la carga, modelado y visualización de datos.
* Se crearon medidas DAX para KPIs como:

  * Total Ventas = SUM('Ventas'\[PrecioUnitario] \* 'Ventas'\[CantidadFacturada])
  * Promedio por Cliente, Producto y Factura.
* Se diseñaron tres lienzos temáticos:

  1. **Resumen Comercial General**.
  2. **Análisis de Productos y Clientes**.
  3. **Desempeño de Vendedores**.
* Se implementaron filtros por fechas, productos, sexo y ubicación, con elementos visuales como gráficos de columnas, líneas, tablas comparativas y tarjetas de KPI.

---

### 📌 Conclusiones

* La herramienta Power BI permitió integrar diversas fuentes y visualizar insights accionables.
* Se identificaron oportunidades de mejora geográfica y demográfica.
* La implementación de KPIs permite monitorear el cumplimiento de metas y segmentar estrategias de ventas.
* El dashboard es una herramienta escalable para futuras iteraciones, incluyendo análisis predictivos y benchmarking interno.
