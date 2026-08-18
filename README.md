# Rumbero.net Welcome Screen Fixed

<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rumbero.net | Siente el Ritmo de la Salsa</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts for Latin Flavor Typography -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,300;0,600;0,900;1,400&family=Playfair+Display:ital,wght@0,700;1,900&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Montserrat', sans-serif;
            overflow: hidden;
        }
        .serif-title {
            font-family: 'Playfair Display', serif;

        }
        /* Custom slide crossfade animations */
        .bg-slide {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-size: cover;
            background-position: center;
            opacity: 0;
            transition: opacity 1.5s ease-in-out;
            transform: scale(1.05);
            animation: subtleZoom 20s infinite alternate;
        }
        .bg-slide.active {
            opacity: 1;
        }
        @keyframes subtleZoom {

            from { transform: scale(1.05); }
            to { transform: scale(1.12); }
        }
    </style>
</head>
<body class="bg-black text-white h-screen w-screen relative flex items-center justify-center">

    <!-- Fullscreen Dynamic Background Slideshow -->
    <div id="slideshow-container" class="absolute inset-0 z-0 overflow-hidden">
        <!-- Slide 1: Group dancing in a circle at night -->
        <div class="bg-slide active" style="background-image: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.75)), url('https://images.unsplash.com/photo-1504609813442-a8924e83f76e?fm=jpg&q=60&w=3000&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Mnx8c2Fsc2ElMjBkYW5jZXxlbnwwfHwwfHx8MA%3D%3D');"></div>
        <!-- Slide 2: Couple dancing in a studio setting -->
        <div class="bg-slide" style="background-image: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.75)), url('https://images.unsplash.com/photo-1575449235878-6de79c4c8ef4?fm=jpg&q=60&w=3000&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTF8fHNhbHNhJTIwZGFuY2V8ZW58MHx8MHx8fDA%3D');"></div>
        <!-- Slide 3: Vibrant couple salsa dancing -->
        <div class="bg-slide" style="background-image: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.75)), url('https://images.unsplash.com/photo-1555489401-79c274997434?fm=jpg&q=60&w=3000&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Nnx8c2Fsc2ElMjBkYW5jZXxlbnwwfHwwfHx8MA%3D%3D');"></div>
    </div>

    <!-- Main Content Container with Glassmorphism Overlays -->
    <main class="relative z-10 max-w-4xl mx-auto px-6 text-center flex flex-col items-center justify-center h-full select-none">

        
        <!-- Dynamic Textured Glass Panel -->
        <div class="bg-black/40 backdrop-blur-xl border border-white/10 rounded-3xl p-8 md:p-12 shadow-2xl max-w-2xl transform transition-transform duration-500 hover:scale-[1.01]">
            
            <!-- Site Title & Branding -->
            <h1 class="text-5xl md:text-7xl font-black tracking-wider uppercase mb-3 bg-gradient-to-r from-red-500 via-orange-500 to-amber-400 bg-clip-text text-transparent serif-title">
                Rumbero<span class="text-white text-3xl md:text-5xl">.net</span>
            </h1>
            
            <!-- Passionate Subtitle -->
            <p class="text-lg md:text-xl font-medium tracking-wide text-gray-200 max-w-lg mx-auto">
                Donde la pasión, el sabor y el ritmo se encuentran. A placeholder for the salsa lover domain owner.
            </p>
        </div>

        <!-- Subtle Bottom Branding / Footer inside welcome screen -->
        <div class="absolute bottom-8 left-0 right-0 text-center text-xs tracking-widest text-gray-400/60 uppercase">
            © 2026 Rumbero.net • Pasión por el Baile Latino
        </div>

    </main>

    <!-- Custom Logic for Background Slideshow Wrapped in an IIFE to prevent global scope collisions -->
    <script>
        (function () {
            let currentSlideIndex = 0;
            const slides = document.querySelectorAll('.bg-slide');
            const slideIntervalTime = 6000; // 6 seconds per slide change

            function nextSlide() {
                // Remove active status from current slide
                slides[currentSlideIndex].classList.remove('active');
                
                // Increment index sequentially
                currentSlideIndex = (currentSlideIndex + 1) % slides.length;
                
                // Add active status to next slide
                slides[currentSlideIndex].classList.add('active');
            }


            // Initialize background carousel loop
            setInterval(nextSlide, slideIntervalTime);
        })();
    </script>
</body>
</html>


