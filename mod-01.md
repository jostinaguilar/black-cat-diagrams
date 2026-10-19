```mermaid
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

```
