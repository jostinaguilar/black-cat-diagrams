usecase-beta

actor Administrador("Administrador")
actor Disenador("Diseñador")
actor Impresor("Impresor")
actor Instalador("Instalador")

systemBoundary "Módulo 1: Seguridad y Accesos"
  CU01("CU-01: Iniciar sesión")
  CU02("CU-02: Cerrar sesión")
  CU03("CU-03: Gestionar colaboradores")
end

Administrador -- CU01
Administrador -- CU02
Administrador -- CU03

Disenador -- CU01
Disenador -- CU02

CU01 -- Impresor
CU02 -- Impresor

CU01 -- Instalador
CU02 -- Instalador

usecase-beta

actor Administrador("Administrador")

systemBoundary "Módulo 2: Catálogo y Clientes"
  CU04("CU-04: Gestionar catálogo de servicios")
  CU05("CU-05: Gestionar clientes")
end

Administrador -- CU04
Administrador -- CU05

usecase-beta

actor Administrador("Administrador")

systemBoundary "Módulo 3: Cotizaciones"
  CU04("CU-04: Gestionar servicios")
  CU05("CU-05: Gestionar clientes")
  CU06("CU-06: Registrar cotización")
  CU07("CU-07: Consultar y actualizar cotizaciones")
  CU08("CU-08: Generar cotización en PDF")
  CU09("CU-09: Convertir cotización aprobada en pedido")
  CU10("CU-10: Anular cotización")
end

Administrador -- CU06
Administrador -- CU07

CU06 ..> : include CU05
CU06 ..> : include CU04

CU07 ..> : extend CU08
CU07 ..> : extend CU09
CU07 ..> : extend CU10

usecase-beta

actor Administrador("Administrador")
actor Disenador("Diseñador")
actor Impresor("Impresor")
actor Instalador("Instalador")

systemBoundary "Módulo 4: Pedidos y Producción"
  CU11("CU-11: Consultar y actualizar estado de pedidos")
  CU12("CU-12: Anular pedido")
  CU13("CU-13: Crear y gestionar tareas de pedido")
  CU14("CU-14: Consultar tareas asignadas")
  CU15("CU-15: Actualizar estado de tarea asignada")
end

Administrador -- CU11
Administrador -- CU12

Disenador -- CU14
Impresor -- CU14
Instalador -- CU14

CU11 ..> : extend CU13
CU14 ..> : extend CU15

usecase-beta

actor Administrador("Administrador")

systemBoundary "Módulo 5: Pagos y Caja"
  CU16("CU-16: Registrar pago de pedido")
  CU17("CU-17: Consultar y corregir pagos")
  CU18("CU-18: Anular pago")
  CU19("CU-19: Emitir comprobante de pago")
end

Administrador -- CU16
Administrador -- CU17
Administrador -- CU18

CU16 ..> : include CU19

usecase-beta

actor Administrador("Administrador")

systemBoundary "Módulo 6: Inventario y Reportes"
  CU20("CU-20: Gestionar catálogo de materiales")
  CU21("CU-21: Registrar movimiento de inventario")
  CU22("CU-22: Generar reporte diario de operaciones e ingresos")
end

Administrador -- CU20
Administrador -- CU21
Administrador -- CU22
