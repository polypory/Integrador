https://drive.google.com/file/d/1RWAnRSUn5amkpmxQcO8Jo1kgblhGZlmK/view?usp=sharing

aca dejo la idea general  del UML para que se sepa que cosas faltan y que ya esta hecho

es una cadena de librerias, tenemos usuarios como abstracto que se divide entre consumidor y empleado.

el  consumidor tiene su propio carrito de compra, puede ver todo el catalogo y una vez este listo puede proceder al pago de una venta online, esta se construye a partir de la clase abstracta ventas pero ventas online indica el tipo de entrega de los productos y la sucursal(si lo retira en fisico). Esta informacion pasa a una queue si hay que llevarlo al correo o a un hashmap si lo pasan a retirar por sucursal.

Aparte tenemos la clase Sucursal, que tiene una arraylist de empleados, los horarios de toda la semana, la lista de productos que son para retirar, la lista de productosque se llevan al correo, el stock, la caja y un historial de ventas. Al final del dia si la caja no coincide con el registro de ventas automaticamente se envia una notificacion de cuanta diferencia hay a oficina a una queue. Tambien se hace un arqueo al principio de cada dia para ver que coincida la plata del dia anterior con la actual. Ante caulquier cosa que ocurra con la caja, el empleado de sucursal puede enviar una observacion con respecto a la caja a oficina(ej: un billete falso para que despues lo resten de la caja)

La clase empleado se divide en dos a su vez: DE OFICINA y DE SUCURSAL. Ambos se pueden comunicar dejandose mensajes en una queue

el empleadode sucursal va a puede realizar una venta, se carga un arralist con los isbn de los libros con los isbn y se indica el medio de pago. Puede realizar cambios de productos, reembolsos, peticiones a oficina y anular ventas. Ademas completan las tareas previamente mencionadas de apertura y cierre de caja, llevar paquetes al correo, entregar compra_online y realizar depositos de dinero.

El empleado de oficina se maneja con una queue de tareas, que son observaciones desde los locales, peticiones (que pueden ser cambios de horario o categoria) y notificaciones de errores en caja. Puede modificar la caja en base a esas observaciones, modifica horarrios, cambia categorias, pasa aumentos, dependiendo los errores de caja u otras observaciones tambien puede hacerle deducciones a los empleados de sucursal(por aceptar billetes falsos de 10 0 20k o por errores de gran tamaño en caja) y tambien da de baja o ingresa empleados.



