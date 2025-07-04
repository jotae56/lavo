<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width,initial-scale=1.0">
    <title>La Voz del C.U.A.N - Comunidad Centro Urbano Antonio Nariño</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
    <style>
     /* Fuentes */
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&family=Montserrat:wght@600;700&display=swap');

/* Estilos base */
body {
    font-family: 'Roboto', sans-serif;
    overflow: auto;
    background-color: #f9fafb;
    color: #1f2937;
}

h1, h2, h3, h4 {
    font-family: 'Montserrat', sans-serif;
}

/* Hero Banner */
.hero-banner {
    background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('primera.jpg');
    background-size: cover;
    background-position: center;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    padding: 5rem 0;
}

@media (min-width: 768px) {
    .hero-banner {
        padding: 8rem 0;
    }
}

/* Tarjetas de servicio */
.service-card {
    background-color: white;
    border-radius: 0.5rem;
    overflow: hidden;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -2px rgba(0, 0, 0, 0.1);
    transition: all 0.3s ease;
}

.service-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 8px 10px -6px rgba(0, 0, 0, 0.1);
}

/* Imágenes adaptables */
.service-card img {
    width: 100%;
    height: 12rem;
    object-fit: cover;
    object-position: center;
}

/* Específicamente para la imagen de la iglesia */
.service-card .relative.w-full.h-48.overflow-hidden img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center;
}

/* Resaltado de historia */
.history-highlight {
    border-left: 4px solid #065f46;
    background-color: #f0fdf4;
    padding: 1.5rem;
    margin: 1rem 0;
}

/* Modal de video */
.video-modal {
    position: fixed;
    inset: 0;
    background-color: rgba(0, 0, 0, 0.9);
    z-index: 1000;
    display: flex;
    align-items: center;
    justify-content: center;
    display: none;
}

.video-modal-content {
    width: 90%;
    max-width: 800px;
    position: relative;
}

.video-modal-close {
    position: absolute;
    top: -40px;
    right: 0;
    color: white;
    font-size: 30px;
    cursor: pointer;
}

.video-container {
    position: relative;
    padding-bottom: 56.25%;
    height: 0;
    overflow: hidden;
}

.video-container iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border: none;
}

/* Modal de login */
#loginModal {
    position: fixed;
    inset: 0;
    background-color: rgba(0, 0, 0, 0.5);
    z-index: 50;
    display: flex;
    align-items: center;
    justify-content: center;
    display: none;
}

#loginModal .bg-white {
    width: 100%;
    max-width: 28rem;
    margin-left: 1rem;
    margin-right: 1rem;
    border-radius: 0.75rem;
    box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
    overflow: hidden;
}

/* Transiciones */
.transition {
    transition-property: color, background-color, border-color, text-decoration-color, fill, stroke, opacity, box-shadow, transform, filter, backdrop-filter;
    transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
    transition-duration: 150ms;
}

.duration-300 {
    transition-duration: 300ms;
}
    </style>
</head>
<body class="bg-gray-50 text-gray-800" style="overflow: auto;">
    <header class="bg-green-800 text-white shadow-lg">
        <div class="container mx-auto px-4 py-3">
            <div class="flex flex-col md:flex-row justify-between items-center">
                <div class="flex items-center mb-4 md:mb-0">
                    <img src="logo.jpg" alt="Logo C.U.A.N" class="h-16 w-16 rounded-full mr-4 border-2 border-white">
                    <div>
                        <h1 class="text-xl md:text-2xl font-bold">LA VOZ DEL C.U.A.N</h1>
                        <p class="text-sm text-green-200">Una comunidad sana es una comunidad sin secretos</p>
                    </div>
                </div>
                <nav class="w-full md:w-auto">
                    <ul class="flex flex-wrap justify-center md:justify-end items-center space-x-1 md:space-x-2">
                        <li><a href="#inicio" class="px-3 py-2 rounded hover:bg-green-700 transition">Inicio</a></li>
                        <li><a href="#historia" class="px-3 py-2 rounded hover:bg-green-700 transition">Historia</a></li>
                        <li><a href="#noticias" class="px-3 py-2 rounded hover:bg-green-700 transition">Noticias</a></li>
                        <li><a href="#servicios" class="px-3 py-2 rounded hover:bg-green-700 transition">Servicios</a></li>
                        <li><a href="#naturaleza" class="px-3 py-2 rounded hover:bg-green-700 transition">Naturaleza</a></li>
                        <li><a href="#teatro" class="px-3 py-2 rounded hover:bg-green-700 transition">Teatro</a></li>
                        <li><a href="#contacto" class="px-3 py-2 rounded hover:bg-green-700 transition">Contacto</a></li>
                        <li><button id="loginBtn" class="ml-2 px-4 py-2 bg-yellow-500 text-gray-900 rounded-lg font-medium hover:bg-yellow-400 transition flex items-center"><span class="material-icons mr-1">login</span>Acceso Residentes</button></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>

    <section id="inicio" class="hero-banner flex items-center justify-center text-white py-20 md:py-32">
        <div class="container mx-auto px-4 text-center">
            <h2 class="text-3xl md:text-5xl font-bold mb-4">Bienvenidos a nuestra comunidad</h2>
            <p class="text-xl md:text-2xl mb-8 max-w-3xl mx-auto">El Centro Urbano Antonio Nariño, un espacio de convivencia y armonía</p>
            <div class="flex flex-wrap justify-center gap-4">
                <a href="#historia" class="px-6 py-3 bg-green-600 hover:bg-green-700 rounded-lg font-medium transition">Conoce nuestra historia</a>
                <a href="#servicios" class="px-6 py-3 bg-yellow-500 hover:bg-yellow-600 text-gray-900 rounded-lg font-medium transition">Nosotros</a>
            </div>
        </div>
    </section>

    <section class="bg-gray-100 py-12">
        <div class="container mx-auto px-4">
            <div class="grid grid-cols-2 md:grid-cols-4 gap-6 text-center">
                <div class="bg-white p-6 rounded-lg shadow-md">
                    <span class="material-icons text-green-600 text-5xl mb-3">apartment</span>
                    <h3 class="text-3xl font-bold text-green-700">67</h3>
                    <p class="text-gray-600">Años de historia</p>
                </div>
                <div class="bg-white p-6 rounded-lg shadow-md">
                    <span class="material-icons text-green-600 text-5xl mb-3">groups</span>
                    <h3 class="text-3xl font-bold text-green-700">3,000+</h3>
                    <p class="text-gray-600">Residentes</p>
                </div>
                <div class="bg-white p-6 rounded-lg shadow-md">
                    <span class="material-icons text-green-600 text-5xl mb-3">home</span>
                    <h3 class="text-3xl font-bold text-green-700">864</h3>
                    <p class="text-gray-600">Apartamentos</p>
                </div>
                <div class="bg-white p-6 rounded-lg shadow-md">
                    <span class="material-icons text-green-600 text-5xl mb-3">park</span>
                    <h3 class="text-3xl font-bold text-green-700">12</h3>
                    <p class="text-gray-600">Zonas verdes</p>
                </div>
            </div>
        </div>
    </section>

    <main class="container mx-auto px-4 py-12">
        <section id="historia" class="mb-16">
            <div class="flex flex-col md:flex-row items-center gap-8">
                <div class="md:w-1/2">
                    <img src="historia.jpg" alt="Historia del C.U.A.N" class="rounded-lg shadow-xl w-full">
                </div>
                <div class="md:w-1/2">
                    <h2 class="text-3xl font-bold mb-6 text-green-800 flex items-center"><span class="material-icons mr-2">history</span>Nuestra Historia</h2>
                    <div class="mb-6">
                        <p class="text-gray-700 mb-4">El Centro Urbano Antonio Nariño (CUAN) es un conjunto residencial ubicado en la ciudad de Bogotá, Colombia. Se encuentra específicamente en la zona occidental del centro de la ciudad, en la localidad de Teusaquillo. Este conjunto es notable por su diseño y por su importancia histórica en el desarrollo urbano de Bogotá.</p>
                    </div>
                    <h3 class="text-2xl font-bold mb-4 text-green-700">Diseño y Construcción</h3>
                    <div class="mb-6">
                        <p class="text-gray-700 mb-4">El CUAN fue diseñado por los arquitectos Néstor C. Gutiérrez y la firma Esguerra Sáenz, Urdaneta, Suárez y Cía. Su construcción se inició a finales de la década de 1940, y fue inaugurado en 1952. El diseño del conjunto se caracteriza por su estilo moderno y funcional, con un uso eficiente de los materiales de construcción.</p>
                        <p class="text-gray-700">El conjunto está compuesto por 14 edificios de apartamentos, de los cuales ocho tienen 13 pisos de altura, y seis tienen cuatro pisos. En total, el Centro Urbano Antonio Nariño alberga 960 apartamentos, con capacidad para unas 6,400 personas. Además de las residencias, el conjunto también incluye una escuela primaria, un colegio de bachillerato, una iglesia, un teatro y un supermercado, lo que lo convierte en una comunidad autosuficiente.</p>
                    </div>
                    <h3 class="text-2xl font-bold mb-4 text-green-700">Significado Histórico</h3>
                    <div class="mb-6">
                        <p class="text-gray-700 mb-4">El Centro Urbano Antonio Nariño es considerado un hito importante en la historia de la arquitectura y el desarrollo urbano de Bogotá. Fue uno de los primeros conjuntos residenciales de gran escala en la ciudad, y su diseño sirvió como modelo para muchos otros proyectos de vivienda que se construyeron posteriormente.</p>
                        <p class="text-gray-700">El CUAN representó un nuevo enfoque en la planificación urbana, buscando crear comunidades integrales que ofrecieran a sus residentes no solo vivienda, sino también acceso a servicios esenciales y espacios recreativos.</p>
                    </div>
                    <div class="history-highlight mb-6">
                        <p class="text-gray-700 font-medium">En reconocimiento a su valor arquitectónico e histórico, el Centro Urbano Antonio Nariño fue declarado Monumento Nacional de Colombia.</p>
                    </div>
                    <h3 class="text-2xl font-bold mb-4 text-green-700">Ubicación</h3>
                    <div class="mb-6">
                        <p class="text-gray-700">El conjunto está ubicado en la Calle 25 con Carrera 37, en la localidad de Teusaquillo, una zona tradicional y de gran importancia en Bogotá. Su ubicación céntrica facilita el acceso a otras partes de la ciudad y a una amplia gama de servicios y comodidades.</p>
                    </div>
                    <div class="bg-green-800 text-white p-6 rounded-lg">
                        <p class="font-medium">Hoy en día, el Centro Urbano Antonio Nariño sigue siendo un lugar de residencia importante en Bogotá, y su legado perdura como un ejemplo destacado de la arquitectura moderna y la planificación urbana en Colombia.</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="servicios" class="mb-16">
            <h2 class="text-3xl font-bold mb-8 text-green-800 text-center"><span class="material-icons mr-2">miscellaneous_services</span>NOSOTROS</h2>
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6">
                
                <!-- Iglesia Católica Modificada -->
                <div class="service-card bg-white rounded-lg overflow-hidden shadow-md transition duration-300 hover:shadow-xl">
                    <div class="relative w-full h-48 overflow-hidden">
                        <img src="xx.jpg" alt="Iglesia Cosmes y Damián" class="w-full h-full object-cover">
                    </div>
                    
                    <div class="p-5">
                        <h3 class="text-xl font-bold mb-2 text-green-700">Iglesia Católica</h3>
                        <p class="text-gray-600 mb-3">Parroquia Cosmes y Damián</p>
                        
                        <div class="mb-4">
                            <h4 class="font-semibold text-gray-800 mb-2 flex items-center">
                                <span class="material-icons text-green-600 mr-2">schedule</span>
                                Horarios de Misa
                            </h4>
                            <ul class="text-sm text-gray-700 space-y-1">
                                <li class="flex justify-between">
                                    <span>Domingos:</span>
                                    <span class="font-medium">7:00 am, 9:00 am, 11:00 am, 6:00 pm</span>
                                </li>
                                <li class="flex justify-between">
                                    <span>Lunes a Viernes:</span>
                                    <span class="font-medium">7:00 am, 12:00 m, 6:00 pm</span>
                                </li>
                                <li class="flex justify-between">
                                    <span>Sábados:</span>
                                    <span class="font-medium">7:00 am, 6:00 pm (Vísperas)</span>
                                </li>
                            </ul>
                        </div>
                        
                        <div class="mb-4">
                            <h4 class="font-semibold text-gray-800 mb-2 flex items-center">
                                <span class="material-icons text-green-600 mr-2">healing</span>
                                Horarios de Confesiones
                            </h4>
                            <ul class="text-sm text-gray-700 space-y-1">
                                <li class="flex justify-between">
                                    <span>Martes y Jueves:</span>
                                    <span class="font-medium">4:00 pm - 6:00 pm</span>
                                </li>
                                <li class="flex justify-between">
                                    <span>Sábados:</span>
                                    <span class="font-medium">9:00 am - 11:00 am</span>
                                </li>
                            </ul>
                        </div>
                        
                        <button onclick="openVideoModal('VIDEO_ID_IGLESIA')" class="w-full mt-3 px-4 py-2 bg-red-600 hover:bg-red-700 text-white rounded-lg flex items-center justify-center">
                            <span class="material-icons mr-2">live_tv</span>
                         Misa a Cualquier Hora
                        </button>
                    </div>
                </div>
                
                <!-- Supermercado cambiado a Ejercicios y Fitness -->
                <div class="service-card bg-white rounded-lg overflow-hidden shadow-md transition duration-300 hover:shadow-xl">
                    <img src="eje.jpg" alt="Ejercicios y Fitness" class="w-full h-48 object-cover">
                    <div class="p-5">
                        <h3 class="text-xl font-bold mb-2 text-green-700">Ejercicios y Fitness</h3>
                        <p class="text-gray-600 mb-3">ESTIRAMIENTO YOGA FUERZA CHIKUNG</p>
                        <div class="flex items-center text-sm text-gray-500">
                            <span class="material-icons text-yellow-500 mr-1 text-sm">schedule</span>Horario: A Cualquier Hora
                            <button onclick="openVideoModal('srvrIN3dnXE')" class="w-full mt-3 px-4 py-2 bg-red-600 hover:bg-red-700 text-white rounded-lg flex items-center justify-center">
                            <span class="material-icons mr-2">live_tv</span>
                    </button>
                         </div>
                    </div>
                </div>

             <div class="service-card bg-white rounded-lg overflow-hidden shadow-md transition duration-300 hover:shadow-xl">
                    <img src="99.jpg" alt="Abogados" class="w-full h-48 object-cover">
                    <div class="p-5">
                        <h3 class="text-xl font-bold mb-2 text-green-700">PODCASTS CULTURA ARTE CINE </h3>
                        <p class="text-gray-600 mb-3"></p>
                        <div class="flex items-center text-sm text-gray-500">
                            <span class="material-icons text-yellow-500 mr-1 text-sm">schedule</span>Horario:A Cualquier Hora
                            <button onclick="openVideoModal('Wx7BJFaQecA')" class="w-full mt-3 px-4 py-2 bg-red-600 hover:bg-red-700 text-white rounded-lg flex items-center justify-center">
                            <span class="material-icons mr-2">live_tv</span>
                        </button>
                        </div>
                    </div>
                </div>

                <div class="service-card bg-white rounded-lg overflow-hidden shadow-md transition duration-300 hover:shadow-xl">
                    <img src="17.jpg" alt="Abogados" class="w-full h-48 object-cover">
                    <div class="p-5" >
                        <h3 class="text-xl font-bold mb-2 text-green-700">MEMORIAS ANECDOTAS Y VIVENCIAS</h3>
                        <p class="text-gray-600 mb-3"></p>
                        <div class="flex items-center text-sm text-gray-500">
                            <span class="material-icons text-yellow-500 mr-1 text-sm">schedule</span>Horario:A Cualquier Hora
                        <button onclick="openVideoModal('7fz_87_ikH0')" class="w-full mt-3 px-4 py-2 bg-red-600 hover:bg-red-700 text-white rounded-lg flex items-center justify-center">
                            <span class="material-icons mr-2">live_tv</span>
                        </button>
                          </div>
                    </div>
                </div>
                
                <div class="service-card bg-white rounded-lg overflow-hidden shadow-md transition duration-300 hover:shadow-xl">
                    <img src="https://images.unsplash.com/photo-1600585152220-90363fe7e115?ixlib=rb-1.2.1&amp;auto=format&amp;fit=crop&amp;w=800&amp;q=80" alt="Carpintería" class="w-full h-48 object-cover">
                    <div class="p-5">
                        <h3 class="text-xl font-bold mb-2 text-green-700">HOGAR Y BIENESTAR</h3>
                        <p class="text-gray-600 mb-3">Bienestar</p>
                        <div class="flex items-center text-sm text-gray-500">
                            <span class="material-icons text-yellow-500 mr-1 text-sm">schedule</span>Horario:A Cualquier Hora
                            <button onclick="openVideoModal('L5Tfja6mZDY')" class="w-full mt-3 px-4 py-2 bg-red-600 hover:bg-red-700 text-white rounded-lg flex items-center justify-center">
                            <span class="material-icons mr-2">live_tv</span>
                        </button>
                        </div>
                    </div>
                </div>
                  <div class="service-card bg-white rounded-lg overflow-hidden shadow-md transition duration-300 hover:shadow-xl">
                    <img src="veciapojpg.jpg" alt="Ventanería" class="w-full h-48 object-cover">
                    <div class="p-5">
                        <h3 class="text-xl font-bold mb-2 text-green-700">Vecinos Apoyan Vecinos</h3>
                        <p class="text-gray-600 mb-3">vecinos</p>
                        <div class="flex items-center text-sm text-gray-500">
                            <span class="material-icons text-yellow-500 mr-1 text-sm">schedule</span>Horario: A Cualquier Hora
                            <button onclick="openVideoModal('jTOQTkGN-xs')" class="w-full mt-3 px-4 py-2 bg-red-600 hover:bg-red-700 text-white rounded-lg flex items-center justify-center">
                            <span class="material-icons mr-2">live_tv</span>
                        </button>
                        </div>
                    </div>
                </div>
                <div class="service-card bg-white rounded-lg overflow-hidden shadow-md transition duration-300 hover:shadow-xl">
                    <img src="images.jpg" alt="Ventanería" class="w-full h-48 object-cover">
                    <div class="p-5">
                        <h3 class="text-xl font-bold mb-2 text-green-700">RADIO NOVELAS Y AUDIOLIBROS</h3>
                        <p class="text-gray-600 mb-3">vecinos</p>
                        <div class="flex items-center text-sm text-gray-500">
                            <span class="material-icons text-yellow-500 mr-1 text-sm">schedule</span>Horario: A Cualquier Hora
                            <button onclick="openVideoModal('FdJ_6PSbToI')" class="w-full mt-3 px-4 py-2 bg-red-600 hover:bg-red-700 text-white rounded-lg flex items-center justify-center">
                            <span class="material-icons mr-2">live_tv</span>
                        </button>
                        <button onclick="openVideoModal('_0-if4ASuJw')" class="w-full mt-3 px-4 py-2 bg-red-600 hover:bg-red-700 text-white rounded-lg flex items-center justify-center">
                            <span class="material-icons mr-2">live_tv</span>
                        </button>
                        </div>
                    </div>
                </div>
                
                <div class="service-card bg-white rounded-lg overflow-hidden shadow-md transition duration-300 hover:shadow-xl">
                    <img src="lectura.jpg" alt="Biblioteca" class="w-full h-48 object-cover">
                    <div class="p-5">
                        <h3 class="text-xl font-bold mb-2 text-green-700">Biblioteca Comunitaria y Club de Lectura</h3>
                        <p class="text-gray-600 mb-3">Más de 1,000 títulos</p>
                        <div class="flex items-center text-sm text-gray-500">
                            <span class="material-icons text-yellow-500 mr-1 text-sm">schedule</span>Horario: 10am - 6pm24 
                            <button onclick="openVideoModal('L6ZHNjsujJg')" class="w-full mt-3 px-4 py-2 bg-red-600 hover:bg-red-700 text-white rounded-lg flex items-center justify-center">
                            <span class="material-icons mr-2">live_tv</span>
                        </button>
                        
                       
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="naturaleza" class="mb-16 bg-green-50 rounded-xl p-8">
            <div class="flex flex-col md:flex-row items-center gap-8">
                <div class="md:w-1/2 order-2 md:order-1">
                    <h2 class="text-3xl font-bold mb-6 text-green-800 flex items-center"><span class="material-icons mr-2">nature</span>Nuestra Naturaleza</h2>
                    <p class="text-lg mb-4">Contamos con una zona verde llena de árboles y naturaleza donde los pájaros de varias especies conviven con nosotros. Somos un pulmón para la ciudad de Bogotá.</p>
                    <p class="text-lg">Nuestros jardines incluyen especies nativas como robles, cedros y arrayanes, que atraen colibríes, mirlas y otras aves que alegran nuestros días con su canto y colorido.Realmente es un privilegio poder vivir en el Centro Nariño PATRIMONIO DE LA NACION</p>
                </div>
                <div class="md:w-1/2 order-1 md:order-2">
                    <img src="natu.jpg" alt="Naturaleza en el C.U.A.N" class="rounded-lg shadow-xl w-full">
                </div>
            </div>
        </section>

        <section id="teatro" class="mb-16">
            <div class="bg-gray-800 text-white rounded-xl overflow-hidden shadow-xl">
                <div class="flex flex-col md:flex-row">
                    <div class="md:w-1/2">
                        <img src="cadiz.jpg" alt="Teatro Cadiz" class="w-full h-full object-cover">
                    </div>
                    <div class="md:w-1/2 p-8">
                        <h2 class="text-3xl font-bold mb-6 text-yellow-400 flex items-center"><span class="material-icons mr-2">theater_comedy</span>Teatro Cadiz</h2>
                        <p class="text-lg mb-4">Nuestro teatro comunitario con capacidad para 380 personas es un espacio cultural vibrante donde se presentan obras teatrales, conciertos y eventos comunitarios.</p>
                        <div class="mb-6">
                            <h3 class="text-xl font-bold mb-3 text-yellow-400">Próximos Eventos</h3>
                            <ul class="space-y-3">
                                <li class="flex items-start"><span class="material-icons text-yellow-400 mr-2">event</span><span>por anunciar</span></li>
                                <li class="flex items-start"><span class="material-icons text-yellow-400 mr-2">event</span><span>por anunciar</span></li>
                                <li class="flex items-start"><span class="material-icons text-yellow-400 mr-2">event</span><span>por anunciar</span></li>
                            </ul>
                        </div>
                        <button class="px-6 py-3 bg-yellow-500 hover:bg-yellow-600 text-gray-900 rounded-lg font-medium transition flex items-center">
                            <span class="material-icons mr-2">confirmation_number</span>Reservar Entradas
                        </button>
                    </div>
                </div>
            </div>
        </section>

        <section id="documentos" class="mb-16">
            <h2 class="text-3xl font-bold mb-6 text-green-800 text-center"><span class="material-icons mr-2">description</span>Documentos Importantes</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <div class="bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition">
                    <div class="flex items-start">
                        <span class="material-icons text-green-600 text-4xl mr-4">menu_book</span>
                        <div>
                            <h3 class="text-xl font-bold mb-2 text-green-700">Manual de Convivencia</h3>
                            <p class="text-gray-600 mb-4">Normas y regulaciones para la armonía de nuestra comunidad.</p>
                            <a href="#" class="text-green-600 hover:text-green-800 font-medium flex items-center">Descargar PDF<span class="material-icons ml-1">download</span></a>
                        </div>
                    </div>
                </div>
                <div class="bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition">
                    <div class="flex items-start">
                        <span class="material-icons text-green-600 text-4xl mr-4">gavel</span>
                        <div>
                            <h3 class="text-xl font-bold mb-2 text-green-700">Ley 675 de 2001</h3>
                            <p class="text-gray-600 mb-4">Ley de Propiedad Horizontal de Colombia.</p>
                            <a href="#" class="text-green-600 hover:text-green-800 font-medium flex items-center">Descargar PDF<span class="material-icons ml-1">download</span></a>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <footer id="contacto" class="bg-gray-900 text-white pt-12 pb-6">
        <div class="container mx-auto px-4">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mb-8">
                <div>
                    <h4 class="text-xl font-bold mb-4 text-green-400 flex items-center"><span class="material-icons mr-2">contact_mail</span>Contacto</h4>
                    <ul class="space-y-3">
                        <li class="flex items-start"><span class="material-icons mr-2 text-green-400">phone</span><span>Teléfono: (601) 555-1234</span></li>
                        <li class="flex items-start"><span class="material-icons mr-2 text-green-400">email</span><span>Email: contacto@lavozdelcuan.com.co</span></li>
                        <li class="flex items-start"><span class="material-icons mr-2 text-green-400">location_on</span><span>Dirección: Calle 25 # 35 39, Bogotá</span></li>
                    </ul>
                </div> 
                <div>
                    <h4 class="text-xl font-bold mb-4 text-green-400 flex items-center">
                        <span class="material-icons mr-2">link</span>Enlaces Rápidos
                    </h4>
                    <ul class="space-y-3">
                        <li>
                            <a href="https://drive.google.com/drive/folders/0ACjaNGromPRoUk9PVA" 
                               class="hover:text-green-400 transition flex items-center"
                               target="_blank">
                                <span class="material-icons mr-2 text-sm">chevron_right</span>Manual de Convivencia
                            </a>
                        </li>
                        <li><a href="#" class="hover:text-green-400 transition flex items-center"><span class="material-icons mr-2 text-sm">chevron_right</span>Reglamento Interno</a></li>
                        <li><a href="#" class="hover:text-green-400 transition flex items-center"><span class="material-icons mr-2 text-sm">chevron_right</span>Consejo Administrativo</a></li>
                        <li><a href="#" class="hover:text-green-400 transition flex items-center"><span class="material-icons mr-2 text-sm">chevron_right</span>Calendario de Eventos</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-xl font-bold mb-4 text-green-400 flex items-center"><span class="material-icons mr-2">share</span>Síguenos</h4>
                    <div class="flex space-x-4 mb-6">
                        <a href="#" class="bg-gray-700 hover:bg-blue-600 w-10 h-10 rounded-full flex items-center justify-center transition"><span class="material-icons">facebook</span></a>
                        <a href="#" class="bg-gray-700 hover:bg-pink-600 w-10 h-10 rounded-full flex items-center justify-center transition"><span class="material-icons">instagram</span></a>
                        <a href="#" class="bg-gray-700 hover:bg-blue-400 w-10 h-10 rounded-full flex items-center justify-center transition"><span class="material-icons">twitter</span></a>
                        <a href="#" class="bg-gray-700 hover:bg-red-500 w-10 h-10 rounded-full flex items-center justify-center transition"><span class="material-icons">youtube</span></a>
                    </div>
                    <h4 class="text-xl font-bold mb-4 text-green-400 flex items-center"><span class="material-icons mr-2">language</span>Sitio Web</h4>
                    <a href="#" class="text-green-400 hover:underline">www.lavozdelcuan.com.co</a>
                </div>
            </div>
            <div class="border-t border-gray-800 pt-6 text-center text-gray-400">
                <p>© 2025 La Voz del C.U.A.N - Todos los derechos reservados</p>
            </div>
        </div>
    </footer>

    <!-- Modal de Login -->
    <div id="loginModal" class="fixed inset-0 bg-black bg-opacity-50 z-50 flex items-center justify-center hidden">
        <div class="bg-white rounded-xl shadow-2xl w-full max-w-md mx-4">
            <div class="p-6">
                <div class="flex justify-between items-center mb-6">
                    <h3 class="text-2xl font-bold text-gray-800 flex items-center"><span class="material-icons mr-2 text-green-600">login</span>Acceso Residentes</h3>
                    <button id="closeModal" class="text-gray-500 hover:text-gray-700"><span class="material-icons">close</span></button>
                </div>
                <form id="loginForm" class="space-y-4">
                    <div>
                        <label for="apartment" class="block text-sm font-medium text-gray-700 mb-1">Apartamento</label>
                        <input type="text" id="apartment" required placeholder="Ej: Torre 1 - 101" class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-green-500 focus:border-green-500">
                    </div>
                    <div>
                        <label for="pin" class="block text-sm font-medium text-gray-700 mb-1">PIN de acceso</label>
                        <input type="password" id="pin" required class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-green-500 focus:border-green-500">
                    </div>
                    <div class="pt-2">
                        <button type="submit" class="w-full bg-green-600 hover:bg-green-700 text-white py-3 px-4 rounded-lg font-medium transition flex items-center justify-center">
                            <span class="material-icons mr-2">lock_open</span>Ingresar
                        </button>
                    </div>
                    <div class="text-center text-sm text-gray-600">
                        <p>¿No tienes acceso? <a href="#" class="text-green-600 hover:underline">Solicítalo aquí</a></p>
                    </div>
                 </form>
            </div>
        </div>
    </div>

    <!-- Modal de Video -->
    <div id="videoModal" class="video-modal">
        <div class="video-modal-content">
            <span class="video-modal-close" onclick="closeVideoModal()">&times;</span>
            <div class="video-container">
                <iframe id="videoFrame" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
            </div>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Control del modal de login
            const loginBtn = document.getElementById('loginBtn');
            const loginModal = document.getElementById('loginModal');
            const closeModal = document.getElementById('closeModal');
            
            loginBtn.addEventListener('click', function(e) {
                e.preventDefault();
                loginModal.style.display = 'flex';
            });
            
            closeModal.addEventListener('click', function() {
                loginModal.style.display = 'none';
            });
            
            window.addEventListener('click', function(e) {
                if(e.target === loginModal) {
                    loginModal.style.display = 'none';
                }
            });
            
            document.getElementById('loginForm').addEventListener('submit', function(e) {
                e.preventDefault();
                const apartment = document.getElementById('apartment').value;
                const pin = document.getElementById('pin').value;
                
                if(apartment && pin) {
                    showAlert('Acceso concedido. Redirigiendo...', 'success');
                    setTimeout(() => {
                        loginModal.style.display = 'none';
                    }, 1500);
                } else {
                    showAlert('Por favor complete todos los campos', 'error');
                }
            });
            
            // Navegación suave
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    const targetId = this.getAttribute('href');
                    const targetElement = document.querySelector(targetId);
                    if(targetElement) {
                        window.scrollTo({
                            top: targetElement.offsetTop - 80,
                            behavior: 'smooth'
                        });
                    }
                });
            });
            
            // Mostrar notificaciones
            function showAlert(message, type) {
                const alertDiv = document.createElement('div');
                alertDiv.className = `fixed bottom-6 right-6 px-6 py-4 rounded-lg shadow-lg z-50 flex items-center ${type==='success'?'bg-green-500':'bg-red-500'} text-white`;
                
                const icon = document.createElement('span');
                icon.className = 'material-icons mr-2';
                icon.textContent = type==='success'?'check_circle':'error';
                alertDiv.appendChild(icon);
                
                const text = document.createElement('span');
                text.textContent = message;
                alertDiv.appendChild(text);
                
                document.body.appendChild(alertDiv);
                
                setTimeout(() => {
                    alertDiv.classList.add('opacity-0', 'transition-opacity', 'duration-500');
                    setTimeout(() => {
                        document.body.removeChild(alertDiv);
                    }, 500);
                }, 3000);
            }
        });

        // Control de modal de video
        function openVideoModal(videoId) {
            const modal = document.getElementById('videoModal');
            const iframe = document.getElementById('videoFrame');
            
            iframe.src = `https://www.youtube.com/embed/${videoId}?autoplay=1`;
            modal.style.display = 'flex';
            document.body.style.overflow = 'hidden';
        }

        function closeVideoModal() {
            const modal = document.getElementById('videoModal');
            const iframe = document.getElementById('videoFrame');
            
            iframe.src = '';
            modal.style.display = 'none';
            document.body.style.overflow = 'auto';
        }

        // Cerrar modal al hacer clic fuera
        window.addEventListener('click', function(event) {
            const modal = document.getElementById('videoModal');
            if (event.target === modal) {
                closeVideoModal();
            }
        });
    </script>
</body>
</html>avo
