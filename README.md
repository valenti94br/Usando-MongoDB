**1.1. Desarrollar el Proyecto**

db.createCollection('Users')
db.createCollection('Posts')

**1.2.1 INSERTAR DATOS**

*Insertar al menos 15 publicaciones nuevas con almenos 2 comentarios por publicación:*

db.posts.insertMany([
    {
        Title: 'Murcia',
        Body: 'Menuda movida',
        Username: 'Manolo',
        Comments:[{
            Username: 'Manu',
            Body: 'Ya ves'
        }],
    },

    {
        Title: 'Receta de pollo',
        Body: 'Pollo asado crujiente',
        Username: 'cocinero123',
        Comments: {
            Username: 'amantedelpollo',
            Body: 'Me encanta esta receta'
        },
    },

    {
        Title: 'Consejos de sueño',
        Body: 'Mejora tus hábitos',
        Username: 'dormilon22',
        Comments: {
            Username: 'insomniaco123',
            Body: 'Gracias por compartir'
        },
    },

    {
        Title: 'Rutina de ejercicio',
        Body: '20 minutos diarios',
        Username: 'fitguru',
        Comments: {
            Username: 'novatogym',
            Body: 'Voy a intentarlo'
        },
    },

    {
        Title: 'Libro recomendado',
        Body: 'El Alquimista',
        Username: 'lectorvoraz',
        Comments: {
            Username: 'fanaticaCoelho',
            Body: 'Es mi libro favorito'
        },
    },

    {
        Title: 'Destino de viaje',
        Body: 'París en primavera',
        Username: 'viajero79',
        Comments: {
            Username: 'amantedeparis',
            Body: 'La mejor época'
        },
    },

    {
        Title: 'Consejos de belleza',
        Body: 'Hidrata tu piel',
        Username: 'beautyqueen',
        Comments: {
            Username: 'productoadicta',
            Body: 'Recomienden un hidratante'
        },
    },

    {
        Title: 'Técnica de estudio',
        Body: 'Pomodoro de 25 minutos',
        Username: 'estudiantemoderno',
        Comments: {
            Username: 'estresadaporlexamen',
            Body: 'Lo probaré'
        },
    },

    {
        Title: 'Receta vegana',
        Body: 'Tacos de lentejas',
        Username: 'veganlover',
        Comments: {
            Username: 'carnivoroconvencido',
            Body: 'Se ven deliciosos'
        },
    },

    {
        Title: 'Consejos financieros',
        Body: 'Ahorrar para el futuro',
        Username: 'ahorrador123',
        Comments: {
            Username: 'deudorperpetuo',
            Body: 'No sé por dónde empezar'
        },
    },

    {
        Title: 'Película recomendada',
        Body: 'Forrest Gump',
        Username: 'cinefilo89',
        Comments: {
            Username: 'amantedelcine',
            Body: 'Excelente elección'
        },
    },

    {
        Title: 'Consejos de moda',
        Body: 'Combina colores',
        Username: 'fashionista123',
        Comments: {
            Username: 'sinestilopropio',
            Body: 'Gracias por los tips'
        },
    },

    {
        Title: 'Actividad al aire libre',
        Body: 'Senderismo en montaña',
        Username: 'amantenaturaleza',
        Comments: {
            Username: 'urbanitaalegre',
            Body: 'Me encanta el senderismo'
        },
    },

    {
        Title: 'Receta rápida pasta',
        Body: 'Salsa tomate queso',
        Username: 'Cocinero123',
        Comments: {
            Username: 'Foodie22',
            Body: 'Deliciosa receta!'
        },
    },

    {
        Title: 'Viaje a París',
        Body: 'Torre Eiffel Louvre',
        Username: 'TravelLover',
        Comments: {
            Username: 'Explorer01',
            Body: 'Me encantó París!'
        },
    },

])

*Insertar al menos 10 nuevos usuarios:*

db.users.insertMany([
    {
        Username: 'Pedro',
        Email: 'pedro_martinez@yahoo.com',
        Age: 'Joven aún'
        },

        {
        Username: 'Ana',
        Email: 'ana_gonzalez@yahoo.com',
        Age: 'Veintitantos',
        },

        {
        Username: 'Lucía',
        Email: 'lucia.perez@yahoo.com',
        Age: 'Dieciocho años',
        },

        {
        Username: 'Carlos',
        Email: 'carlos_santos@yahoo.com',
        Age: 'Treinta y tantos',
        },

        {
        Username: 'Sofía',
        Email: 'sofia_rivera@yahoo.com',
        Age: 'Veinticuatro años',
        },

        {
        Username: 'Juan',
        Email: 'juan_mendez@yahoo.com',
        Age: 'Cincuenta y algo',
        },

        {
        Username: 'Eva',
        Email: 'eva_garcia@yahoo.com',
        Age: 'Tres décadas',
        },

        {
        Username: 'Luis',
        Email: 'luis_fernandez@yahoo.com',
        Age: 'Mediana edad',
        },

        {
        Username: 'Isabel',
        Email: 'isabel_hernandez@yahoo.com',
        Age: 'Casi cuarenta',
        },

        {
        Username: 'Mario',
        Email: 'mario_gomez@yahoo.com',
        Age: 'Recién nacido',
        }
])

**1.2.2 ACTUALIZAR DATOS**

*Actualizar publicaciones:*

*Actualiza todos los campos de una publicación*

db.posts.updateOne({ Title: 'Murcia' },

    { $set: { Title: 'Panda', Body: 'Muy mono', Username: 'Felipe', Comments: {
        Username: 'Panxo',
        Body: 'Siempre'
    }, } })

*Cambiar el body de una publicación*

db.posts.updateOne({ Title: 'Viaje a París' },

{

$set: {
    Body: 'La torre una mierda'

},

})

*Actualiza el comentario de una publicación*

db.posts.updateOne({ Title: 'Viaje a París' },

{

$set: {

    Comments: {
        Username: 'Panfleto987',
        Body: 'París huele raro'
    }

}

})

*Actualizar usuarios:*

*Actualiza todos los campos de un usuario*

db.users.updateMany({ Username: 'Pedro' },

{ $set:{Username: 'Uperino', Email: 'pedro_martinez@yahoo.com', Age: 'Joven aún'}})

*Cambiar el email de dos usuarios es decir hacer la query dos veces.*

db.products.updateOne({ Username: 'Ana' },{ $set:{Email: 'ana_gonzalez@yahoo.com'}})

db.products.updateOne({ Username: 'Lucía' },{ $set:{Email: 'lucia.perez@yahoo.com'}})

*Aumenta en 5 años la edad de un usuario*

db.users.updateOne({ name: 'Ana' },

{

$inc: {

Age: 5

}

})

*OBTENER DATOS*

*Seleccionar todas las publicaciones*

