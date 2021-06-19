# Backend Sistema Registro de Egresos

## Índice

### 1- Servidor

### 2- Crear Usuario

### 3- Obtener Usuario

### 4- Crear Egreso

### 5- Obtener Egreso

### 6- Obtener Egreso por Usuario

## ___________________________________________________________

## 1- Servidor

    servidor: https://backend-registro-egreso.herokuapp.com/api-backend-prueba
    Prefijo: api-backend-prueba

## 2-Crear Usuario

### Ruta

    Método POST /usuario/crear-usuario    

### Datos Recibidos

    nombre:String,
    apellido:String,
    rut: { type:String,default: null },
    correo: String,
    password: String,

### Respuesta

    (200)
    {
        "usuario": {
            "rut": "11111-1",
            "_id": "60c18078e752d41a04eea451",
            "nombre": "prueba",
            "apellido": "prueba",
            "correo": "correo@gmail.com",
            "password": "$2b$10$BiPTE4bi0H4iUCsnvbsqbO4TZRJTwhz.tVwQvbJn0gfmCjTVKIVWG",
            "__v": 0
        }
    }

## 3-Obtener Usuario

### Ruta

    Método GET /usuario/obtener-usuarios

### Datos Obtenidos

    {
        "usuarios": [
            {
                "rut": "111111",
                "_id": "60aee75a3230560015e8c085",
                "nombre": "nombre",
                "apellido": "apellido",
                "correo": "correo@gmail.com",
                "password": "$2b$10$zaSg/SaBEym22Nk8Yw/Pfug7dlL/qu8JGiQs//5EWcWZyZNx5X25C",
                "__v": 0
            },
            {
                "rut": "18.315.092-8",
                "_id": "60aef3fecde6252dd8410f3a",
                "nombre": "nombre",
                "apellido": "apellido",
                "correo": "correo@gmail.com",
                "password": "$2b$10$H2OhlpDOBnK3GoR9Vfcqeu4qbuX8q6iE0okT3H91MZhE2sNglNSC.",
                "__v": 0
            }
    }

## 4-Crear Egreso

### Ruta

    Método POST /egreso/crear-egreso    

### Datos Recibidos

    descripcion:String,
    precio: Number,
    id_usuario: {
        type: Schema.ObjectId,
        ref: 'Usuario',
        default: null
    }

### Respuesta

    {
        "egreso": {
            "id_usuario": "60c18078e752d41a04eea451",
            "_id": "60c8085aef26d600151770cf",
            "descripcion": "cft",
            "precio": 1009,
            "__v": 0
        }
    }

## 4-Obtener Egreso

### Ruta

   Método GET /egreso/obtener-egresos

### Datos Obtenidos

    {
    "egresos": [
        {
            "id_usuario": {
                "rut": "11111-1",
                "_id": "60c18078e752d41a04eea451",
                "nombre": "mauro",
                "apellido": "bloque",
                "correo": "correo@gmail.com",
                "password": "$2b$10$BiPTE4bi0H4iUCsnvbsqbO4TZRJTwhz.tVwQvbJn0gfmCjTVKIVWG",
                "__v": 0
            },
            "_id": "60c8085aef26d600151770cf",
            "descripcion": "cft",
            "precio": 1009,
            "__v": 0
        },
        {}...
    }

## 6- Obtener Egreso por Usuario

### Ruta

    Método GET /egreso/obtener-egresos-usuario/:id
    Ejemplo ruta: egreso/obtener-egresos-usuario/60aee75a3230560015e8c085

### Datos Obtenidos

    {
        "egresos_usuario": [
            {
                "id_usuario": {
                    "rut": "111111",
                    "_id": "60aee75a3230560015e8c085",
                    "nombre": "edgar",
                    "apellido": "cay",
                    "correo": "edgardo@gmail.com",
                    "password": "$2b$10$zaSg/SaBEym22Nk8Yw/Pfug7dlL/qu8JGiQs//5EWcWZyZNx5X25C",
                    "__v": 0
                },
                "_id": "60c6f4a8edc5912b280b2e23",
                "descripcion": "neuva noche",
                "precio": 5001,
                "__v": 0
            },
            {}...
    }
