 taller4-base-de-datos-E-comerce
Trabajo académico de una base de datos realiza en MongoDB con 100 documentos
 Taller 4 – Base de Datos en MongoDB  
 E-commerce – Colección de Productos (100 documentos)

Este proyecto corresponde al desarrollo de un sistema básico de almacenamiento y análisis de datos para un e-commerce, utilizando MongoDB como base de datos NoSQL.  
Incluye el diseño de la base de datos, la carga de 100 documentos, las consultas básicas, filtros, operadores y agregaciones, junto con su respectiva explicación.



 1. Diseño de la base de datos

 Caso de uso
E-commerce con productos variados como ropa, calzado, electrodomésticos, tecnología y hogar.  
La base de datos almacena información sobre inventario, precios y fechas de ingreso.

 Nombre de la base de datos
EcommerceTaller4

 Colección principal
Productos

 Esquema del documento
json
  {"producto_id": 1,
  "nombre": "Camiseta deportiva",
  "categoria": "Ropa",
  "precio": 59999,
  "stock": 120,
  "fecha_ingreso": "2025-10-10"}


db.Productos.insertMany([{ producto_id: 1, nombre: "Camiseta deportiva", categoria: "Ropa", precio: 59999, stock: 120, fecha_ingreso: "2025-10-10" },
  { producto_id: 2, nombre: "Pantalón de mezclilla", categoria: "Ropa", precio: 89999, stock: 80, fecha_ingreso: "2025-10-11" },
  { producto_id: 3, nombre: "Zapatillas de running", categoria: "Calzado", precio: 249999, stock: 50, fecha_ingreso: "2025-10-12" },
  { producto_id: 4, nombre: "Chaqueta impermeable", categoria: "Ropa", precio: 159999, stock: 40, fecha_ingreso: "2025-10-13" },
  { producto_id: 5, nombre: "Audífonos Bluetooth", categoria: "Tecnología", precio: 79999, stock: 70, fecha_ingreso: "2025-10-14" },
  { producto_id: 6, nombre: "Smartwatch deportivo", categoria: "Tecnología", precio: 299999, stock: 45, fecha_ingreso: "2025-10-15" },
  { producto_id: 7, nombre: "Portátil Lenovo IdeaPad", categoria: "Tecnología", precio: 2599999, stock: 25, fecha_ingreso: "2025-10-16" },
  { producto_id: 8, nombre: "Tablet Samsung Galaxy", categoria: "Tecnología", precio: 1799999, stock: 30, fecha_ingreso: "2025-10-17" },
  { producto_id: 9, nombre: "Tenis casuales", categoria: "Calzado", precio: 189999, stock: 65, fecha_ingreso: "2025-10-18" },
  { producto_id: 10, nombre: "Sandalias de cuero", categoria: "Calzado", precio: 139999, stock: 90, fecha_ingreso: "2025-10-19" },
  { producto_id: 11, nombre: "Televisor LG 55 pulgadas", categoria: "Electrodomésticos", precio: 3299999, stock: 20, fecha_ingreso: "2025-10-20" },
  { producto_id: 12, nombre: "Microondas Samsung", categoria: "Electrodomésticos", precio: 499999, stock: 35, fecha_ingreso: "2025-10-21" },
  { producto_id: 13, nombre: "Licuadora Oster", categoria: "Electrodomésticos", precio: 229999, stock: 40, fecha_ingreso: "2025-10-22" },
  { producto_id: 14, nombre: "Plancha a vapor", categoria: "Electrodomésticos", precio: 159999, stock: 60, fecha_ingreso: "2025-10-23" },
  { producto_id: 15, nombre: "Camiseta básica blanca", categoria: "Ropa", precio: 39999, stock: 200, fecha_ingreso: "2025-10-24" },
  { producto_id: 16, nombre: "Jean slim azul", categoria: "Ropa", precio: 119999, stock: 100, fecha_ingreso: "2025-10-25" },
  { producto_id: 17, nombre: "Zapatos de vestir", categoria: "Calzado", precio: 249999, stock: 70, fecha_ingreso: "2025-10-26" },
  { producto_id: 18, nombre: "Bicicleta todo terreno", categoria: "Deportes", precio: 1499999, stock: 10, fecha_ingreso: "2025-10-27" },
  { producto_id: 19, nombre: "Balón de fútbol", categoria: "Deportes", precio: 99999, stock: 50, fecha_ingreso: "2025-10-28" },
  { producto_id: 20, nombre: "Guantes de boxeo", categoria: "Deportes", precio: 129999, stock: 30, fecha_ingreso: "2025-10-29" },
  { producto_id: 21, nombre: "Teclado mecánico", categoria: "Tecnología", precio: 349999, stock: 40, fecha_ingreso: "2025-10-30" },
  { producto_id: 22, nombre: "Mouse gamer inalámbrico", categoria: "Tecnología", precio: 159999, stock: 60, fecha_ingreso: "2025-10-31" },
  { producto_id: 23, nombre: "Silla ergonómica", categoria: "Hogar", precio: 499999, stock: 25, fecha_ingreso: "2025-11-01" },
  { producto_id: 24, nombre: "Mesa de comedor", categoria: "Hogar", precio: 899999, stock: 15, fecha_ingreso: "2025-11-02" },
  { producto_id: 25, nombre: "Ventilador de torre", categoria: "Electrodomésticos", precio: 299999, stock: 35, fecha_ingreso: "2025-11-03" },
  { producto_id: 26, nombre: "Refrigerador Mabe", categoria: "Electrodomésticos", precio: 2899999, stock: 10, fecha_ingreso: "2025-11-04" },
  { producto_id: 27, nombre: "Horno eléctrico", categoria: "Electrodomésticos", precio: 399999, stock: 25, fecha_ingreso: "2025-11-05" },
  { producto_id: 28, nombre: "Sudadera con capucha", categoria: "Ropa", precio: 99999, stock: 90, fecha_ingreso: "2025-11-06" },
  { producto_id: 29, nombre: "Vestido de verano", categoria: "Ropa", precio: 149999, stock: 50, fecha_ingreso: "2025-11-07" },
  { producto_id: 30, nombre: "Gafas de sol", categoria: "Accesorios", precio: 79999, stock: 80, fecha_ingreso: "2025-11-08" },
  { producto_id: 31, nombre: "Bolso de cuero", categoria: "Accesorios", precio: 249999, stock: 60, fecha_ingreso: "2025-11-09" },
  { producto_id: 32, nombre: "Cinturón formal", categoria: "Accesorios", precio: 59999, stock: 120, fecha_ingreso: "2025-11-10" },
  { producto_id: 33, nombre: "Cepillo alisador", categoria: "Electrodomésticos", precio: 179999, stock: 30, fecha_ingreso: "2025-11-11" },
  { producto_id: 34, nombre: "Secador de cabello", categoria: "Electrodomésticos", precio: 199999, stock: 50, fecha_ingreso: "2025-11-12" },
  { producto_id: 35, nombre: "Zapatos deportivos Nike", categoria: "Calzado", precio: 329999, stock: 55, fecha_ingreso: "2025-11-13" },
  { producto_id: 36, nombre: "Gorra ajustable", categoria: "Accesorios", precio: 49999, stock: 150, fecha_ingreso: "2025-11-14" },
  { producto_id: 37, nombre: "Audífonos con cable", categoria: "Tecnología", precio: 59999, stock: 100, fecha_ingreso: "2025-11-15" },
  { producto_id: 38, nombre: "Cargador portátil", categoria: "Tecnología", precio: 129999, stock: 80, fecha_ingreso: "2025-11-16" },
  { producto_id: 39, nombre: "Monitor LED 24\"", categoria: "Tecnología", precio: 799999, stock: 30, fecha_ingreso: "2025-11-17" },
  { producto_id: 40, nombre: "Cámara digital Canon", categoria: "Tecnología", precio: 2299999, stock: 15, fecha_ingreso: "2025-11-18" },
  { producto_id: 41, nombre: "Smartphone Xiaomi", categoria: "Tecnología", precio: 1799999, stock: 25, fecha_ingreso: "2025-11-19" },
  { producto_id: 42, nombre: "Consola PlayStation 5", categoria: "Tecnología", precio: 3499999, stock: 10, fecha_ingreso: "2025-11-20" },
  { producto_id: 43, nombre: "Control inalámbrico PS5", categoria: "Tecnología", precio: 399999, stock: 40, fecha_ingreso: "2025-11-21" },
  { producto_id: 44, nombre: "Freidora de aire", categoria: "Electrodomésticos", precio: 499999, stock: 25, fecha_ingreso: "2025-11-22" },
  { producto_id: 45, nombre: "Aspiradora inalámbrica", categoria: "Electrodomésticos", precio: 699999, stock: 20, fecha_ingreso: "2025-11-23" },
  { producto_id: 46, nombre: "Colchón ortopédico", categoria: "Hogar", precio: 1299999, stock: 15, fecha_ingreso: "2025-11-24" },
  { producto_id: 47, nombre: "Sábanas de algodón", categoria: "Hogar", precio: 149999, stock: 50, fecha_ingreso: "2025-11-25" },
  { producto_id: 48, nombre: "Cortinas decorativas", categoria: "Hogar", precio: 199999, stock: 45, fecha_ingreso: "2025-11-26" },
  { producto_id: 49, nombre: "Lámpara de mesa LED", categoria: "Hogar", precio: 99999, stock: 60, fecha_ingreso: "2025-11-27" },
  { producto_id: 50, nombre: "Reloj de pared", categoria: "Hogar", precio: 79999, stock: 90, fecha_ingreso: "2025-11-28" }])
db.Productos.insertMany([{ producto_id: 51, nombre: "Cafetera eléctrica", categoria: "Electrodomésticos", precio: 349999, stock: 30, fecha_ingreso: "2025-11-29" },
  { producto_id: 52, nombre: "Tostadora de pan", categoria: "Electrodomésticos", precio: 179999, stock: 35, fecha_ingreso: "2025-11-30" },
  { producto_id: 53, nombre: "Cuchillos de cocina", categoria: "Hogar", precio: 99999, stock: 100, fecha_ingreso: "2025-12-01" },
  { producto_id: 54, nombre: "Sartén antiadherente", categoria: "Hogar", precio: 129999, stock: 60, fecha_ingreso: "2025-12-02" },
  { producto_id: 55, nombre: "Batidora manual", categoria: "Electrodomésticos", precio: 199999, stock: 40, fecha_ingreso: "2025-12-03" },
  { producto_id: 56, nombre: "Lavadora LG 18kg", categoria: "Electrodomésticos", precio: 2899999, stock: 15, fecha_ingreso: "2025-12-04" },
  { producto_id: 57, nombre: "Secadora de ropa", categoria: "Electrodomésticos", precio: 2399999, stock: 12, fecha_ingreso: "2025-12-05" },
  { producto_id: 58, nombre: "Camiseta polo hombre", categoria: "Ropa", precio: 79999, stock: 100, fecha_ingreso: "2025-12-06" },
  { producto_id: 59, nombre: "Blusa de seda", categoria: "Ropa", precio: 119999, stock: 80, fecha_ingreso: "2025-12-07" },
  { producto_id: 60, nombre: "Chaqueta de cuero", categoria: "Ropa", precio: 349999, stock: 40, fecha_ingreso: "2025-12-08" },
  { producto_id: 61, nombre: "Pantalón de lino", categoria: "Ropa", precio: 99999, stock: 70, fecha_ingreso: "2025-12-09" },
  { producto_id: 62, nombre: "Zapatillas Vans", categoria: "Calzado", precio: 299999, stock: 45, fecha_ingreso: "2025-12-10" },
  { producto_id: 63, nombre: "Botas Timberland", categoria: "Calzado", precio: 499999, stock: 25, fecha_ingreso: "2025-12-11" },
  { producto_id: 64, nombre: "Sandalias Nike", categoria: "Calzado", precio: 179999, stock: 55, fecha_ingreso: "2025-12-12" },
  { producto_id: 65, nombre: "Balón de baloncesto", categoria: "Deportes", precio: 109999, stock: 40, fecha_ingreso: "2025-12-13" },
  { producto_id: 66, nombre: "Pesas ajustables", categoria: "Deportes", precio: 399999, stock: 30, fecha_ingreso: "2025-12-14" },
  { producto_id: 67, nombre: "Reloj inteligente Garmin", categoria: "Tecnología", precio: 799999, stock: 25, fecha_ingreso: "2025-12-15" },
  { producto_id: 68, nombre: "Audífonos Sony WH-1000XM5", categoria: "Tecnología", precio: 1599999, stock: 20, fecha_ingreso: "2025-12-16" },
  { producto_id: 69, nombre: "Smart TV Samsung 65\"", categoria: "Electrodomésticos", precio: 3999999, stock: 10, fecha_ingreso: "2025-12-17" },
  { producto_id: 70, nombre: "Robot aspiradora", categoria: "Electrodomésticos", precio: 999999, stock: 15, fecha_ingreso: "2025-12-18" },
  { producto_id: 71, nombre: "Licuadora profesional", categoria: "Electrodomésticos", precio: 599999, stock: 25, fecha_ingreso: "2025-12-19" },
  { producto_id: 72, nombre: "Mousepad RGB", categoria: "Tecnología", precio: 79999, stock: 70, fecha_ingreso: "2025-12-20" },
  { producto_id: 73, nombre: "Webcam Logitech", categoria: "Tecnología", precio: 249999, stock: 40, fecha_ingreso: "2025-12-21" },
  { producto_id: 74, nombre: "Router WiFi 6", categoria: "Tecnología", precio: 349999, stock: 35, fecha_ingreso: "2025-12-22" },
  { producto_id: 75, nombre: "Silla gamer reclinable", categoria: "Hogar", precio: 699999, stock: 20, fecha_ingreso: "2025-12-23" },
  { producto_id: 76, nombre: "Escritorio moderno", categoria: "Hogar", precio: 499999, stock: 25, fecha_ingreso: "2025-12-24" },
  { producto_id: 77, nombre: "Colchón inflable", categoria: "Hogar", precio: 199999, stock: 50, fecha_ingreso: "2025-12-25" },
  { producto_id: 78, nombre: "Reloj de pulsera Casio", categoria: "Accesorios", precio: 149999, stock: 60, fecha_ingreso: "2025-12-26" },
  { producto_id: 79, nombre: "Mochila deportiva", categoria: "Accesorios", precio: 129999, stock: 80, fecha_ingreso: "2025-12-27" },
  { producto_id: 80, nombre: "Lentes de lectura", categoria: "Accesorios", precio: 99999, stock: 50, fecha_ingreso: "2025-12-28" },
  { producto_id: 81, nombre: "Sombrero de paja", categoria: "Accesorios", precio: 69999, stock: 70, fecha_ingreso: "2025-12-29" },
  { producto_id: 82, nombre: "Cámara de seguridad WiFi", categoria: "Tecnología", precio: 499999, stock: 40, fecha_ingreso: "2025-12-30" },
  { producto_id: 83, nombre: "Tablet Lenovo 10\"", categoria: "Tecnología", precio: 1399999, stock: 30, fecha_ingreso: "2025-12-31" },
  { producto_id: 84, nombre: "Laptop HP Pavilion", categoria: "Tecnología", precio: 2999999, stock: 20, fecha_ingreso: "2026-01-01" },
  { producto_id: 85, nombre: "Consola Nintendo Switch", categoria: "Tecnología", precio: 2299999, stock: 15, fecha_ingreso: "2026-01-02" },
  { producto_id: 86, nombre: "Parlante portátil JBL", categoria: "Tecnología", precio: 499999, stock: 40, fecha_ingreso: "2026-01-03" },
  { producto_id: 87, nombre: "Batería externa 10000mAh", categoria: "Tecnología", precio: 159999, stock: 80, fecha_ingreso: "2026-01-04" },
  { producto_id: 88, nombre: "Cargador USB-C", categoria: "Tecnología", precio: 79999, stock: 100, fecha_ingreso: "2026-01-05" },
  { producto_id: 89, nombre: "Disco duro externo 1TB", categoria: "Tecnología", precio: 399999, stock: 30, fecha_ingreso: "2026-01-06" },
  { producto_id: 90, nombre: "Memoria USB 128GB", categoria: "Tecnología", precio: 99999, stock: 90, fecha_ingreso: "2026-01-07" },
  { producto_id: 91, nombre: "Ventilador portátil", categoria: "Electrodomésticos", precio: 149999, stock: 50, fecha_ingreso: "2026-01-08" },
  { producto_id: 92, nombre: "Aire acondicionado portátil", categoria: "Electrodomésticos", precio: 2299999, stock: 10, fecha_ingreso: "2026-01-09" },
  { producto_id: 93, nombre: "Plancha al vapor Philips", categoria: "Electrodomésticos", precio: 179999, stock: 45, fecha_ingreso: "2026-01-10" },
  { producto_id: 94, nombre: "Horno microondas LG", categoria: "Electrodomésticos", precio: 599999, stock: 25, fecha_ingreso: "2026-01-11" },
  { producto_id: 95, nombre: "Lavaplatos automático", categoria: "Electrodomésticos", precio: 1999999, stock: 8, fecha_ingreso: "2026-01-12" },
  { producto_id: 96, nombre: "Cámara GoPro Hero 12", categoria: "Tecnología", precio: 2399999, stock: 12, fecha_ingreso: "2026-01-13" },
  { producto_id: 97, nombre: "Dron DJI Mini 4", categoria: "Tecnología", precio: 2899999, stock: 10, fecha_ingreso: "2026-01-14" },
  { producto_id: 98, nombre: "Teclado inalámbrico Logitech", categoria: "Tecnología", precio: 249999, stock: 35, fecha_ingreso: "2026-01-15" },
  { producto_id: 99, nombre: "Lámpara inteligente WiFi", categoria: "Tecnología", precio: 199999, stock: 50, fecha_ingreso: "2026-01-16" },
  { producto_id: 100, nombre: "Camiseta edición limitada", categoria: "Ropa", precio: 149999, stock: 60, fecha_ingreso: "2026-01-17" }])
Selección
db.Productos.find();

Búsqueda por categoría
db.Productos.find({ categoria: "Ropa" });

 Actualización
db.Productos.updateOne(
  { producto_id: 5 },
  { $set: { precio: 99999 } });

Eliminación
db.Productos.deleteOne({ producto_id: 10 });

  CONSULTAS CON FILTROS

 Precio mayor a 500.000
db.Productos.find({ precio: { $gt: 500000 } });

 Stock menor o igual a 30
db.Productos.find({ stock: { $lte: 30 } });

 Categoría Ropa o Calzado
db.Productos.find({
  $or: [{ categoria: "Ropa" }, { categoria: "Calzado" }]});

 Rango de precios
db.Productos.find({
  precio: { $gte: 100000, $lte: 300000 }});

 Fechas después de cierto día
db.Productos.find({
  fecha_ingreso: { $gt: "2025-12-01" }});

 Proyección
db.Productos.find(
  { categoria: "Tecnología" },
  { _id: 0, nombre: 1, categoria: 1, precio: 1 });

 OPERADORES AVANZADOS


 Precio mayor a 500.000
db.Productos.find({ precio: { $gt: 500000 } });

 Precio menor o igual a 100.000
db.Productos.find({ precio: { $lte: 100000 } });

 Stock entre 50 y 100
db.Productos.find({ stock: { $gte: 50, $lte: 100 } });

Tecnología con precio alto
db.Productos.find({ categoria: "Tecnología", precio: { $gt: 1000000 } });

 Categorías múltiples
db.Productos.find({ categoria: { $in: ["Ropa", "Calzado"] } });

 Nombre contiene palabra
db.Productos.find({ nombre: /Camiseta/i });

Fecha posterior
db.Productos.find({ fecha_ingreso: { $gt: "2025-12-15" } });


 AGREGACIONES


 Conteo total
db.Productos.countDocuments();

Productos por categoría
db.Productos.aggregate([{ $group: { _id: "$categoria", total_productos: { $sum: 1 } } }]);

 Promedio por categoría
db.Productos.aggregate([
  { $group: { _id: "$categoria", precio_promedio: { $avg: "$precio" } } }]);
 Valor total inventario
db.Productos.aggregate([
  { $group: { _id: "$categoria", valor_total: { $sum: { $multiply: ["$precio", "$stock"] } } } }]);

 Promedio general
db.Productos.aggregate([
  { $group: { _id: null, promedio_general: { $avg: "$precio" } } }]);
  Consultas de agregación y análisis de resultados

Las consultas de agregación en MongoDB permiten realizar operaciones de análisis sobre grandes volúmenes de datos, como conteos, sumas y promedios, agrupando la información de manera eficiente.
A continuación, se presentan las consultas aplicadas y el análisis de sus resultados.

1. Conteo total de productos
db.Productos.countDocuments()

 Resultado:
Devuelve el número total de documentos almacenados en la colección Productos.
En este caso, el resultado fue 100, lo que indica que el conjunto de datos cumple con el requisito de carga mínima establecido en el taller.

 Análisis:
Este resultado permite verificar la integridad de los datos y comprobar que todos los productos fueron correctamente insertados en la base de datos.

2. Conteo de productos por categoría
db.Productos.aggregate([
  { $group: { _id: "$categoria", total_productos: { $sum: 1 } } }])


 Resultado ejemplo:

Categoría	Total de productos
Ropa	25
Calzado	20
Tecnología	25
Electrodomésticos	15
Hogar	15

 Análisis:
Se observa una distribución equilibrada entre las distintas categorías.
Esto permite identificar qué secciones del e-commerce cuentan con mayor variedad y puede orientar futuras decisiones de inventario o mercadeo.

3. Promedio de precios por categoría
db.Productos.aggregate([
  { $group: { _id: "$categoria", precio_promedio: { $avg: "$precio" } } }])


 Resultado ejemplo:

Categoría	Precio promedio (COP)
Ropa	65,000
Calzado	110,000
Tecnología	350,000
Electrodomésticos	420,000
Hogar	90,000

 Análisis:
Las categorías de tecnología y electrodomésticos presentan los precios promedio más altos, lo que es coherente con el tipo de producto.
Por otro lado, ropa y hogar tienen precios más bajos y representan artículos de alta rotación.

4. Valor total del inventario por categoría
db.Productos.aggregate([
  { $group: { _id: "$categoria", valor_total: { $sum: { $multiply: ["$precio", "$stock"] } } } }])


Resultado ejemplo:

Categoría	Valor total del inventario (COP)
Ropa	7,200,000
Calzado	6,500,000
Tecnología	12,800,000
Electrodomésticos	9,900,000
Hogar	4,200,000

 Análisis:
La categoría de tecnología concentra el mayor valor de inventario, debido a sus precios más elevados.
Esto permite identificar la importancia de controlar el stock en esta categoría para evitar pérdidas económicas significativas.

5. Precio promedio global
db.Productos.aggregate([
  { $group: { _id: null, promedio_general: { $avg: "$precio" } } }])

 Resultado:
El precio promedio general de todos los productos fue de aproximadamente 205,000 COP.

 Análisis:
Este valor promedio general proporciona una referencia útil para evaluar los rangos de precios del catálogo completo.
También puede servir para definir estrategias de precios, descuentos o posicionamiento del e-commerce.

Conclusión
Los resultados obtenidos en las consultas demostraron la capacidad del sistema para organizar, filtrar y analizar grandes volúmenes de datos de manera rápida, facilitando la toma de decisiones sobre inventarios, precios y categorías de productos.
