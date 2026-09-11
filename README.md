<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Ubicaciones | Bobaluba El Salvador</title>

    <meta name="description" content="Encuentra tu sucursal Bobaluba más cercana en El Salvador.">

    <style>

        /* ================================
           PALETA DE COLORES BOBALUBA
        ================================= */

        :root {
            --verde-menta: #99C2A2;
            --melocoton: #F4C2A4;
            --lila: #8E7CC3;
            --rosa-fresa: #F2968F;
            --rosa-fresa: #F2968F;
            --blanco: #FFFFFF;
            --morado-oscuro: #5B4F78;

            --texto: #5B4F78;
            --gris: #5B4F78;

            --sombra: 0 10px 30px rgba(91, 79, 120, 0.15);
        }


        /* ================================
           ESTILOS GENERALES
        ================================= */

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: Arial, Helvetica, sans-serif;
            background: var(--verde-menta);
            color: var(--texto);
            line-height: 1.6;
        }

        a {
            text-decoration: none;
        }


        /* ================================
           HEADER
        ================================= */

        .header {
            background: var(--blanco);
            padding: 18px 6%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 3px 15px rgba(91, 79, 120, 0.12);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .logo {
            font-size: 30px;
            font-weight: 900;
            color: var(--lila);
            letter-spacing: -1px;
        }

        .logo span {
            color: var(--rosa-fresa);
        }

        .home-button {
            color: var(--lila);
            font-weight: bold;
            border: 2px solid var(--lila);
            padding: 9px 18px;
            border-radius: 25px;
            transition: 0.3s;
        }

        .home-button:hover {
            background: var(--lila);
            color: var(--blanco);
        }


        /* ================================
           HERO
        ================================= */

        .hero {
            background:
                radial-gradient(
                    circle at 10% 20%,
                    rgba(142, 124, 195, 0.25) 0 80px,
                    transparent 81px
                ),
                radial-gradient(
                    circle at 90% 70%,
                    rgba(242, 150, 143, 0.30) 0 100px,
                    transparent 101px
                ),
                linear-gradient(
                    135deg,
                    #99C2A2,
                    #F4C2A4
                );

            text-align: center;
            padding: 75px 20px 60px;
        }

        .bubble-decoration {
            font-size: 42px;
            margin-bottom: 15px;
        }

        .hero h1 {
            color: var(--blanco);
            font-size: clamp(38px, 6vw, 64px);
            font-weight: 900;
            margin-bottom: 15px;
            text-shadow: 0 3px 8px rgba(91, 79, 120, 0.15);
        }

        .hero h1 span {
            color: var(--rosa-fresa);
        }

        .hero p {
            max-width: 650px;
            margin: auto;
            font-size: 18px;
            color: var(--morado-oscuro);
        }


        /* ================================
           CONTENEDOR
        ================================= */

        .locations-container {
            max-width: 1200px;
            margin: -25px auto 80px;
            padding: 0 20px;
            position: relative;
            z-index: 2;
        }


        /* ================================
           FILTROS
        ================================= */

        .filter-box {
            background: var(--blanco);
            padding: 25px;
            border-radius: 20px;
            box-shadow: var(--sombra);
            margin-bottom: 45px;
        }

        .filter-title {
            text-align: center;
            font-size: 18px;
            font-weight: bold;
            color: var(--morado-oscuro);
            margin-bottom: 18px;
        }

        .filters {
            display: flex;
            justify-content: center;
            gap: 12px;
            flex-wrap: wrap;
        }

        .filter-btn {
            border: 2px solid var(--lila);
            background: var(--blanco);
            color: var(--lila);
            padding: 10px 22px;
            border-radius: 30px;
            font-weight: bold;
            cursor: pointer;
            transition: 0.3s;
            font-size: 15px;
        }

        .filter-btn:hover,
        .filter-btn.active {
            background: var(--lila);
            color: var(--blanco);
            transform: translateY(-2px);
        }


        /* ================================
           DEPARTAMENTOS
        ================================= */

        .department {
            margin-bottom: 55px;
        }

        .department-title {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 25px;
        }

        .department-title h2 {
            color: var(--morado-oscuro);
            font-size: 30px;
            font-weight: 900;
        }

        .department-title::after {
            content: "";
            height: 3px;
            flex: 1;
            background: linear-gradient(
                to right,
                var(--rosa-fresa),
                transparent
            );
        }


        /* ================================
           TARJETAS
        ================================= */

        .locations-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 22px;
        }

        .location-card {
            background: var(--blanco);
            border-radius: 22px;
            padding: 27px;
            box-shadow: var(--sombra);
            border: 1px solid rgba(142, 124, 195, 0.15);
            transition: transform 0.3s, box-shadow 0.3s;
            position: relative;
            overflow: hidden;
        }

        .location-card::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(
                to right,
                var(--rosa-fresa),
                var(--lila)
            );
        }

        .location-card:hover {
            transform: translateY(-7px);
            box-shadow: 0 18px 35px rgba(91, 79, 120, 0.22);
        }

        .location-icon {
            width: 52px;
            height: 52px;
            background: var(--melocoton);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 25px;
            margin-bottom: 18px;
        }

        .location-card h3 {
            color: var(--morado-oscuro);
            font-size: 20px;
            margin-bottom: 10px;
        }

        .location-card p {
            color: var(--morado-oscuro);
            font-size: 15px;
            min-height: 68px;
            margin-bottom: 20px;
        }


        /* ================================
           BOTÓN GOOGLE MAPS
        ================================= */

        .maps-button {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            width: 100%;
            background: var(--rosa-fresa);
            color: var(--blanco);
            padding: 12px 15px;
            border-radius: 25px;
            font-weight: bold;
            transition: 0.3s;
        }

        .maps-button:hover {
            background: var(--lila);
            transform: scale(1.02);
        }


        /* ================================
           MENSAJE SIN RESULTADOS
        ================================= */

        .no-results {
            display: none;
            text-align: center;
            background: var(--blanco);
            padding: 40px;
            border-radius: 20px;
            color: var(--morado-oscuro);
        }


        /* ================================
           FOOTER
        ================================= */

        footer {
            background: var(--morado-oscuro);
            color: var(--blanco);
            text-align: center;
            padding: 35px 20px;
        }

        footer .footer-logo {
            font-size: 28px;
            font-weight: 900;
            color: var(--rosa-fresa);
            margin-bottom: 8px;
        }

        footer p {
            opacity: 0.85;
            font-size: 14px;
        }


        /* ================================
           RESPONSIVE
        ================================= */

        @media (max-width: 950px) {

            .locations-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 600px) {

            .header {
                padding: 15px 20px;
            }

            .logo {
                font-size: 25px;
            }

            .home-button {
                font-size: 13px;
                padding: 8px 13px;
            }

            .hero {
                padding: 55px 20px 50px;
            }

            .hero h1 {
                font-size: 42px;
            }

            .hero p {
                font-size: 16px;
            }

            .locations-container {
                margin-top: -20px;
            }

            .locations-grid {
                grid-template-columns: 1fr;
            }

            .department-title h2 {
                font-size: 25px;
            }

            .department-title::after {
                display: none;
            }
        }

    </style>
</head>


<body>


    <!-- ================================
         HEADER
    ================================= -->

    <header class="header">

        <div class="logo">
            Boba<span>luba</span>
        </div>

        <a href="/" class="home-button">
            ← Inicio
        </a>

    </header>



    <!-- ================================
         HERO
    ================================= -->

    <section class="hero">

        <div class="bubble-decoration">
            🧋
        </div>

        <h1>
            Encuentra tu <span>Bobaluba</span>
        </h1>

        <p>
            Descubre nuestras sucursales y encuentra el lugar más cercano
            para disfrutar tu bubble tea favorito.
        </p>

    </section>



    <!-- ================================
         UBICACIONES
    ================================= -->

    <main class="locations-container">


        <!-- FILTROS -->

        <div class="filter-box">

            <div class="filter-title">
                ¿Dónde quieres disfrutar tu Bobaluba?
            </div>

            <div class="filters">

                <button
                    class="filter-btn active"
                    data-filter="todos">
                    Todas
                </button>

                <button
                    class="filter-btn"
                    data-filter="san-salvador">
                    San Salvador
                </button>

                <button
                    class="filter-btn"
                    data-filter="santa-ana">
                    Santa Ana
                </button>

                <button
                    class="filter-btn"
                    data-filter="san-miguel">
                    San Miguel
                </button>

            </div>

        </div>



        <!-- ================================
             SAN SALVADOR
        ================================= -->

        <section
            class="department"
            data-department="san-salvador">

            <div class="department-title">
                <h2>📍 San Salvador y alrededores</h2>
            </div>

            <div class="locations-grid">


                <!-- Estación del Casco -->

                <article class="location-card">

                    <div class="location-icon">
                        🧋
                    </div>

                    <h3>
                        Estación del Casco
                    </h3>

                    <p>
                        <strong>Casa Matriz</strong><br>
                        C.C. Estación del Casco, Local No. 204,
                        Av. El Espino, San Salvador.
                    </p>

                    <a
                        class="maps-button"
                        href="https://www.google.com/maps/search/?api=1&query=Bobaluba+Estación+del+Casco+San+Salvador"
                        target="_blank"
                        rel="noopener noreferrer">

                        📍 Ver en Google Maps

                    </a>

                </article>



                <!-- Galerías -->

                <article class="location-card">

                    <div class="location-icon">
                        🧋
                    </div>

                    <h3>
                        Centro Comercial Galerías
                    </h3>

                    <p>
                        Paseo General Escalón #3700,
                        San Salvador.
                    </p>

                    <a
                        class="maps-button"
                        href="https://www.google.com/maps/search/?api=1&query=Bobaluba+Galerías+San+Salvador"
                        target="_blank"
                        rel="noopener noreferrer">

                        📍 Ver en Google Maps

                    </a>

                </article>



                <!-- Multiplaza -->

                <article class="location-card">

                    <div class="location-icon">
                        🧋
                    </div>

                    <h3>
                        Centro Comercial Multiplaza
                    </h3>

                    <p>
                        Planta baja, Local A16,
                        San Salvador.
                    </p>

                    <a
                        class="maps-button"
                        href="https://www.google.com/maps/search/?api=1&query=Bobaluba+Multiplaza+San+Salvador"
                        target="_blank"
                        rel="noopener noreferrer">

                        📍 Ver en Google Maps

                    </a>

                </article>



                <!-- Metrocentro San Salvador -->

                <article class="location-card">

                    <div class="location-icon">
                        🧋
                    </div>

                    <h3>
                        Metrocentro San Salvador
                    </h3>

                    <p>
                        Sucursal disponible dentro
                        del centro comercial.
                    </p>

                    <a
                        class="maps-button"
                        href="https://www.google.com/maps/search/?api=1&query=Bobaluba+Metrocentro+San+Salvador"
                        target="_blank"
                        rel="noopener noreferrer">

                        📍 Ver en Google Maps

                    </a>

                </article>



                <!-- Centro Histórico -->

                <article class="location-card">

                    <div class="location-icon">
                        🧋
                    </div>

                    <h3>
                        Centro Histórico
                    </h3>

                    <p>
                        Ubicado a la par de
                        Super Selectos.
                    </p>

                    <a
                        class="maps-button"
                        href="https://www.google.com/maps/search/?api=1&query=Bobaluba+Centro+Histórico+San+Salvador"
                        target="_blank"
                        rel="noopener noreferrer">

                        📍 Ver en Google Maps

                    </a>

                </article>



                <!-- Plaza Futura -->

                <article class="location-card">

                    <div class="location-icon">
                        🧋
                    </div>

                    <h3>
                        Plaza Futura
                    </h3>

                    <p>
                        Torre Futura,
                        San Salvador.
                    </p>

                    <a
                        class="maps-button"
                        href="https://www.google.com/maps/search/?api=1&query=Bobaluba+Plaza+Futura+San+Salvador"
                        target="_blank"
                        rel="noopener noreferrer">

                        📍 Ver en Google Maps

                    </a>

                </article>



                <!-- Plaza Madero -->

                <article class="location-card">

                    <div class="location-icon">
                        🧋
                    </div>

                    <h3>
                        Plaza Madero
                    </h3>

                    <p>
                        Sucursal Bobaluba
                        en Plaza Madero.
                    </p>

                    <a
                        class="maps-button"
                        href="https://www.google.com/maps/search/?api=1&query=Bobaluba+Plaza+Madero+San+Salvador"
                        target="_blank"
                        rel="noopener noreferrer">

                        📍 Ver en Google Maps

                    </a>

                </article>



                <!-- Plaza Las Ramblas -->

                <article class="location-card">

                    <div class="location-icon">
                        🧋
                    </div>

                    <h3>
                        Plaza Las Ramblas
                    </h3>

                    <p>
                        Sucursal Bobaluba
                        en Plaza Las Ramblas.
                    </p>

                    <a
                        class="maps-button"
                        href="https://www.google.com/maps/search/?api=1&query=Bobaluba+Plaza+Las+Ramblas+San+Salvador"
                        target="_blank"
                        rel="noopener noreferrer">

                        📍 Ver en Google Maps

                    </a>

                </article>

            </div>

        </section>



        <!-- ================================
             SANTA ANA
        ================================= -->

        <section
            class="department"
            data-department="santa-ana">

            <div class="department-title">
                <h2>📍 Santa Ana</h2>
            </div>

            <div class="locations-grid">

                <article class="location-card">

                    <div class="location-icon">
                        🧋
                    </div>

                    <h3>
                        Metrocentro Santa Ana
                    </h3>

                    <p>
                        Sucursal disponible en
                        Metrocentro Santa Ana para
                        disfrutar bebidas y tapiocas.
                    </p>

                    <a
                        class="maps-button"
                        href="https://www.google.com/maps/search/?api=1&query=Bobaluba+Metrocentro+Santa+Ana"
                        target="_blank"
                        rel="noopener noreferrer">

                        📍 Ver en Google Maps

                    </a>

                </article>

            </div>

        </section>



        <!-- ================================
             SAN MIGUEL
        ================================= -->

        <section
            class="department"
            data-department="san-miguel">

            <div class="department-title">
                <h2>📍 San Miguel</h2>
            </div>

            <div class="locations-grid">

                <article class="location-card">

                    <div class="location-icon">
                        🧋
                    </div>

                    <h3>
                        Metrocentro San Miguel
                    </h3>

                    <p>
                        Sucursal disponible en
                        Metrocentro San Miguel,
                        zona oriental.
                    </p>

                    <a
                        class="maps-button"
                        href="https://www.google.com/maps/search/?api=1&query=Bobaluba+Metrocentro+San+Miguel"
                        target="_blank"
                        rel="noopener noreferrer">

                        📍 Ver en Google Maps

                    </a>

                </article>

            </div>

        </section>



        <!-- ================================
             SIN RESULTADOS
        ================================= -->

        <div class="no-results" id="noResults">

            <h3>
                No encontramos sucursales
            </h3>

            <p>
                Selecciona otro departamento para ver
                las ubicaciones disponibles.
            </p>

        </div>


    </main>



    <!-- ================================
         FOOTER
    ================================= -->

    <footer>

        <div class="footer-logo">
            Bobaluba
        </div>

        <p>
            El mejor Bubble Tea en El Salvador 🧋
        </p>

    </footer>



    <!-- ================================
         JAVASCRIPT
    ================================= -->

    <script>

        const filterButtons =
            document.querySelectorAll(".filter-btn");

        const departments =
            document.querySelectorAll(".department");

        const noResults =
            document.getElementById("noResults");


        filterButtons.forEach(button => {

            button.addEventListener("click", () => {

                /* Quitar estado activo */

                filterButtons.forEach(btn => {
                    btn.classList.remove("active");
                });


                /* Activar botón seleccionado */

                button.classList.add("active");


                const filter =
                    button.getAttribute("data-filter");


                let visibleDepartments = 0;


                departments.forEach(department => {

                    const departmentName =
                        department.getAttribute("data-department");


                    if (
                        filter === "todos" ||
                        filter === departmentName
                    ) {

                        department.style.display = "block";

                        visibleDepartments++;

                    } else {

                        department.style.display = "none";

                    }

                });


                /* Mostrar mensaje si no existen resultados */

                if (visibleDepartments === 0) {

                    noResults.style.display = "block";

                } else {

                    noResults.style.display = "none";

                }


                /* Regresar al inicio de las ubicaciones */

                document
                    .querySelector(".locations-container")
                    .scrollIntoView({
                        behavior: "smooth",
                        block: "start"
                    });

            });

        });

    </script>


</body>
</html>
