usecase-beta

actor Cliente("Cliente")
actor Proveedor("Proveedor")
actor Administrador("Administrador")
actor Colaborador("Colaborador")

systemBoundary "Agencia de Publicidad Black Cat"
  CUN01("Atender solicitud y cotizar el servicio publicitario")
  CUN02("Formalizar pedido y gestionar pagos")
  CUN03("Ejecutar producción e instalación")
  CUN04("Abastecer y controlar inventario de materiales")
end

Cliente -- CUN01
Cliente -- CUN02
Cliente -- CUN03

Proveedor -- CUN04

CUN01 -- Administrador
CUN02 -- Administrador
CUN03 -- Administrador
CUN04 -- Administrador

CUN03 -- Colaborador
