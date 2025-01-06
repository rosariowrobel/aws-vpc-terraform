# Infraestructura de AWS con Terraform

## Introducción

Este repositorio contiene el código necesario para implementar una infraestructura básica en AWS utilizando Terraform. La configuración incluye:

- Una VPC con subredes pública y privada.
- Un Internet Gateway para acceso a Internet.
- Tablas de rutas para la gestión del tráfico.

Este setup es ideal para aprender cómo estructurar servicios en AWS de forma eficiente.

## Requisitos

- Una cuenta activa de AWS.
- Terraform instalado en tu máquina local.
- AWS CLI configurado con tus credenciales.

## Pasos para Iniciar la Infraestructura

### 1. Clonar el Repositorio

Cloná el repositorio y accedé al directorio del proyecto:

```bash
git clone https://github.com/rosariowrobel/aws-vpc-terraform.git
cd aws-vpc-terraform
```

### 2. Inicializar Terraform

Este comando inicializa el proyecto de Terraform y descarga los proveedores necesarios:

```bash
terraform init
```

### 3. Planificar los Cambios

Antes de aplicar los cambios, podés verificar qué recursos se van a crear:

```bash
terraform plan
```

### 4. Aplicar la Configuración

Para desplegar la infraestructura en AWS:

```bash
terraform apply
```

- Escribí `yes` cuando te lo solicite para confirmar la creación de los recursos.

## Recursos Creados

### 1. VPC

- **Nombre**: VPC-Main
- **Rango CIDR**: `10.0.0.0/16`

### 2. Subred Pública

- **Rango CIDR**: `10.0.1.0/24`
- **Acceso a Internet**: Habilitado mediante Internet Gateway.

### 3. Subred Privada

- **Rango CIDR**: `10.0.2.0/24`
- **Acceso a Internet**: No habilitado.

### 4. Internet Gateway

- **Propósito**: Permitir el tráfico saliente desde la subred pública.

### 5. Tablas de Rutas

- **Tabla Pública**: Redirige el tráfico a Internet.
- **Tabla Privada**: Solo permite comunicación interna.

## Eliminar la Infraestructura

Para eliminar todos los recursos creados y evitar costos adicionales:

```bash
terraform destroy
```

- Escribí `yes` para confirmar la eliminación.

## Notas

- Asegurate de tener permisos suficientes en tu cuenta de AWS.
- Siempre revisá el plan (`terraform plan`) antes de aplicar los cambios.
