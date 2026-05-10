<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Feliz Día de la Madre</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Inter:wght@300;400;600&family=Dancing+Script:wght@700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            scroll-behavior: smooth;
        }
        .font-serif { font-family: 'Playfair Display', serif; }
        .font-script { font-family: 'Dancing Script', cursive; }
        
        @keyframes float {
            0% { transform: translateY(0px) rotate(0deg); opacity: 0; }
            50% { opacity: 1; }
            100% { transform: translateY(-100vh) rotate(360deg); opacity: 0; }
        }
        .flower {
            position: fixed;
            bottom: -50px;
            pointer-events: none;
            z-index: 0;
            animation: float 15s linear infinite;
        }
        
        .card-inner {
            transition: transform 0.6s;
            transform-style: preserve-3d;
        }
        .page-transition {
            transition: all 0.5s ease;
        }
        .hidden-section {
            display: none;
            opacity: 0;
        }
        .active-section {
            display: block;
            animation: fadeIn 0.8s forwards;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        /* Estilo para las notas adhesivas */
        .sticky-note {
            background-color: #fff9c4;
            box-shadow: 5px 5px 10px rgba(0,0,0,0.1);
            transform: rotate(-1deg);
            transition: transform 0.3s;
        }
        .sticky-note:nth-child(even) { transform: rotate(2deg); background-color: #fce4ec; }
        .sticky-note:nth-child(3n) { transform: rotate(-2deg); background-color: #e3f2fd; }
        .sticky-note:hover { transform: scale(1.05) rotate(0deg); z-index: 10; }
    </style>
</head>
<body class="bg-rose-50 text-rose-900 overflow-x-hidden">

    <div id="flower-container"></div>

    <!-- Navegación -->
    <nav class="fixed top-0 w-full bg-white/80 backdrop-blur-md z-50 border-b border-rose-100">
        <div class="max-w-4xl mx-auto px-6 h-16 flex items-center justify-between">
            <span class="font-script text-2xl text-rose-600">Para Mamá</span>
            <div class="flex gap-4">
                <button onclick="showSection('card')" class="text-sm font-semibold uppercase tracking-wider hover:text-rose-600 transition">Carta</button>
                <button onclick="showSection('notes')" class="text-sm font-semibold uppercase tracking-wider hover:text-rose-600 transition">Notas</button>
            </div>
        </div>
    </nav>

    <main class="pt-24 pb-12 px-4 max-w-4xl mx-auto min-h-screen relative z-10">
        
        <section id="card-section" class="active-section page-transition">
            <div class="bg-white rounded-3xl shadow-2xl overflow-hidden border border-rose-100">
                <div class="h-64 bg-[url('https://images.unsplash.com/photo-1526047932273-341f2a7631f9?auto=format&fit=crop&q=80&w=1000')] bg-cover bg-center relative">
                    <div class="absolute inset-0 bg-gradient-to-t from-white via-transparent to-transparent"></div>
                </div>
                
                <div class="px-8 pb-12 -mt-12 relative text-center">
                    <div class="inline-block bg-rose-600 text-white p-4 rounded-full shadow-lg mb-6">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z" />
                        </svg>
                    </div>
                    
                    <h1 class="font-serif text-4xl md:text-5xl font-bold mb-6 text-rose-800">¡Feliz Día de la Madre!</h1>
                    
                    <div class="max-w-2xl mx-auto text-left space-y-6 text-lg leading-relaxed text-rose-700">
                        <p class="font-script text-3xl text-rose-500 text-center mb-8">Querida Mamá,</p>
                        
                        <p>
                            Hoy quiero detenerme un momento para darte las gracias. Gracias por ser el ancla en mis tormentas, la luz en mis días grises y la sonrisa que siempre me espera al volver a casa.
                        </p>
                        
                        <p>
                            Tu amor no tiene límites y tu paciencia parece infinita. He aprendido de ti que la fuerza no se mide en músculos, sino en la capacidad de levantarse y seguir adelante por quienes amamos.
                        </p>
                        
                        <blockquote class="border-l-4 border-rose-300 pl-6 italic font-serif text-2xl my-8 text-rose-600">
                            "Una madre es alguien que puede tomar el lugar de todos los demás, pero cuyo lugar nadie más puede tomar."
                        </blockquote>

                        <p>
                            Eres mi mayor inspiración. Gracias por cada sacrificio, por cada consejo (incluso los que no quise escuchar en su momento) y por quererme exactamente como soy.
                        </p>

                        <p class="font-script text-3xl text-rose-500 text-right pt-8">Con todo mi amor, siempre.</p>
                    </div>
                </div>
            </div>
            
            <div class="mt-8 text-center">
                <button onclick="showSection('notes')" class="bg-rose-500 hover:bg-rose-600 text-white px-8 py-3 rounded-full font-bold shadow-lg transition transform hover:scale-105 active:scale-95">
                    Ver nuestras notas especiales 💌
                </button>
            </div>
        </section>

        <section id="notes-section" class="hidden-section page-transition">
            <div class="text-center mb-10">
                <h2 class="font-serif text-4xl font-bold text-rose-800">Muro de Recuerdos</h2>
                <p class="text-rose-600 mt-2">Pequeñas cosas que te hacen única</p>
            </div>

            <!-- Formulario para añadir nota (solo visual para este ejemplo) -->
            <div class="bg-white p-6 rounded-2xl shadow-md mb-12 border border-rose-100 max-w-lg mx-auto">
                <h3 class="font-bold mb-4">Escribe un mensaje nuevo:</h3>
                <textarea id="noteInput" placeholder="Escribe algo lindo para mamá..." class="w-full p-4 rounded-xl border border-rose-200 focus:ring-2 focus:ring-rose-400 focus:outline-none resize-none h-24 mb-4 text-rose-800"></textarea>
                <button onclick="addNote()" class="w-full bg-rose-500 text-white py-2 rounded-xl font-semibold hover:bg-rose-600 transition">Publicar Nota</button>
            </div>

            <!-- Grid de Notas -->
            <div id="notesContainer" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <!-- Notas predefinidas -->
                <div class="sticky-note p-6 h-48 flex flex-col justify-between">
                    <p class="text-rose-900 font-medium italic">"Gracias por tus abrazos que curan todo."</p>
                    <span class="text-xs text-rose-400 self-end font-bold">#AmorInfinito</span>
                </div>
                <div class="sticky-note p-6 h-48 flex flex-col justify-between">
                    <p class="text-rose-900 font-medium italic">"Nadie cocina con tanto amor como tú."</p>
                    <span class="text-xs text-rose-400 self-end font-bold">#LaMejorChef</span>
                </div>
                <div class="sticky-note p-6 h-48 flex flex-col justify-between">
                    <p class="text-rose-900 font-medium italic">"Gracias por enseñarme a ser valiente."</p>
                    <span class="text-xs text-rose-400 self-end font-bold">#MiEjemplo</span>
                </div>
                <div class="sticky-note p-6 h-48 flex flex-col justify-between">
                    <p class="text-rose-900 font-medium italic">"Te quiero más de lo que las palabras pueden decir."</p>
                    <span class="text-xs text-rose-400 self-end font-bold">#FelizDia</span>
                </div>
                <div class="sticky-note p-6 h-48 flex flex-col justify-between">
                    <p class="text-rose-900 font-medium italic">"Gracias por ser mi mejor amiga."</p>
                    <span class="text-xs text-rose-400 self-end font-bold">#Complices</span>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="bg-white py-8 border-t border-rose-100 text-center text-rose-400 text-sm">
        <p>Hecho con ❤️ para la mejor mamá del mundo</p>
    </footer>

    <script>
        // Función para cambiar entre pestañas
        function showSection(sectionId) {
            const cardSection = document.getElementById('card-section');
            const notesSection = document.getElementById('notes-section');
            
            if (sectionId === 'card') {
                notesSection.classList.remove('active-section');
                notesSection.classList.add('hidden-section');
                cardSection.classList.remove('hidden-section');
                cardSection.classList.add('active-section');
                window.scrollTo({ top: 0, behavior: 'smooth' });
            } else {
                cardSection.classList.remove('active-section');
                cardSection.classList.add('hidden-section');
                notesSection.classList.remove('hidden-section');
                notesSection.classList.add('active-section');
                window.scrollTo({ top: 0, behavior: 'smooth' });
            }
        }

        // Crear flores flotantes de fondo
        function createFlowers() {
            const container = document.getElementById('flower-container');
            const icons = ['🌸', '🌹', '🌷', '🌺', '✨', '❤️'];
            
            for (let i = 0; i < 15; i++) {
                const flower = document.createElement('div');
                flower.className = 'flower text-2xl';
                flower.innerText = icons[Math.floor(Math.random() * icons.length)];
                flower.style.left = Math.random() * 100 + 'vw';
                flower.style.animationDelay = Math.random() * 15 + 's';
                flower.style.fontSize = (Math.random() * 20 + 10) + 'px';
                container.appendChild(flower);
            }
        }

        // Añadir una nueva nota al muro
        function addNote() {
            const input = document.getElementById('noteInput');
            const container = document.getElementById('notesContainer');
            
            if (input.value.trim() === "") return;

            const newNote = document.createElement('div');
            newNote.className = 'sticky-note p-6 h-48 flex flex-col justify-between';
            newNote.innerHTML = `
                <p class="text-rose-900 font-medium italic">"${input.value}"</p>
                <span class="text-xs text-rose-400 self-end font-bold">#NuevoRecuerdo</span>
            `;
            
            // Insertar al principio
            container.insertBefore(newNote, container.firstChild);
            input.value = "";
            
            // Scroll suave a la nota
            newNote.scrollIntoView({ behavior: 'smooth', block: 'center' });
        }

        // Ejecutar al cargar
        window.onload = () => {
            createFlowers();
        };
    </script>
</body>
</html>
