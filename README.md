<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EL EDEN</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;500&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        :root {
            --color-primary: #2c1810;
            --color-secondary: #8c5e3d;
            --color-accent: #c7916f;
            --color-background: #f5e6d3;
            --color-text: #4a3428;
            --color-text-light: #666;
            --border-radius: 15px;
            --transition-speed: 0.3s;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            color: var(--color-text);
            background-color: var(--color-background);
            line-height: 1.6;
        }
        
        /* Header Styles */
        header {
            text-align: center;
            padding: 120px 20px;
            background-image: url('https://images.unsplash.com/photo-1501339847302-ac426a4a7cbb?ixlib=rb-1.2.1&auto=format&fit=crop&w=1200&q=80');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            position: relative;
            color: #fff;
        }
        
        header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.5);
            z-index: 1;
        }
        
        header h1, header p {
            position: relative;
            z-index: 2;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
            font-family: 'Playfair Display', serif;
        }
        
        header h1 {
            font-size: 3.5em;
            margin-bottom: 15px;
            font-weight: 700;
            letter-spacing: 1px;
        }
        
        header p {
            font-size: 1.5em;
            font-style: italic;
            font-weight: 300;
        }
        
        /* Main Content Styles */
        main {
            max-width: 1200px;
            margin: 40px auto;
            padding: 20px;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }
        
        .menu-category {
            background: #fff;
            padding: 25px;
            border-radius: var(--border-radius);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            transition: transform var(--transition-speed) ease;
            position: relative;
            overflow: hidden;
        }
        
        .menu-category:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
        }
        
        .menu-category::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, var(--color-accent), var(--color-secondary));
        }
        
        .menu-category h2 {
            font-size: 2em;
            color: var(--color-primary);
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid var(--color-background);
            position: relative;
            font-family: 'Playfair Display', serif;
        }
        
        /* Item Styles */
        .item {
            display: grid;
            grid-template-columns: 80px 1fr auto;
            gap: 15px;
            padding: 15px 0;
            border-bottom: 1px dashed var(--color-background);
            align-items: center;
        }
        
        .item:last-child {
            border-bottom: none;
        }
        
        .item-image {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            object-fit: cover;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            transition: transform var(--transition-speed) ease;
        }
        
        .item-image:hover {
            transform: scale(1.1) rotate(5deg);
        }
        
        .item-info {
            flex: 1;
        }
        
        .item-info h3 {
            font-size: 1.3em;
            margin-bottom: 5px;
            color: var(--color-primary);
            font-family: 'Playfair Display', serif;
        }
        
        .item-info p {
            font-size: 0.9em;
            color: var(--color-text-light);
            line-height: 1.4;
        }
        
        .item span {
            font-weight: bold;
            color: var(--color-secondary);
            font-size: 1.2em;
            font-family: 'Playfair Display', serif;
        }
        
        /* Price tag animation */
        .item span {
            transition: transform var(--transition-speed) ease;
            display: inline-block;
        }
        
        .item:hover span {
            transform: scale(1.1);
            color: var(--color-primary);
        }
        
        /* Footer Styles */
        footer {
            text-align: center;
            padding: 40px 20px;
            background: linear-gradient(to right, var(--color-primary), var(--color-secondary));
            color: #fff;
        }
        
        footer p {
            margin-bottom: 20px;
            font-size: 1.2em;
        }
        
        footer img {
            width: 120px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            transition: transform var(--transition-speed) ease;
        }
        
        footer img:hover {
            transform: scale(1.1);
        }
        
        /* Loading Animation */
        .item-image.loading {
            animation: pulse 1.5s infinite;
        }
        
        @keyframes pulse {
            0% { opacity: 0.6; }
            50% { opacity: 1; }
            100% { opacity: 0.6; }
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            header {
                padding: 80px 20px;
                background-attachment: scroll;
            }
            
            header h1 {
                font-size: 2.5em;
            }
            
            main {
                grid-template-columns: 1fr;
                padding: 15px;
            }
            
            .item {
                grid-template-columns: 60px 1fr auto;
            }
            
            .item-image {
                width: 60px;
                height: 60px;
            }
            
            .item-info h3 {
                font-size: 1.1em;
            }
            
            .item span {
                font-size: 1.1em;
            }
        }
        
        @media (max-width: 480px) {
            .menu-category {
                padding: 15px;
            }
            
            .item {
                grid-template-columns: 50px 1fr auto;
                gap: 10px;
            }
            
            .item-image {
                width: 50px;
                height: 50px;
            }
        }
        
        /* Print Styles */
        @media print {
            header {
                background-image: none;
                color: var(--color-primary);
                padding: 20px;
            }
            
            header::before {
                display: none;
            }
            
            .menu-category {
                box-shadow: none;
                break-inside: avoid;
            }
            
            .item-image {
                print-color-adjust: exact;
                -webkit-print-color-adjust: exact;
            }
            
            footer {
                background: none;
                color: var(--color-primary);
            }
        }
    </style>
</head>
<body>
    <!-- El contenido HTML permanece igual que en el ejemplo anterior -->
    <header>
        <h1>Café-Bar Gourmet</h1>
        <p>Una experiencia única para tus sentidos</p>
    </header>

    <main>
        <section class="menu-category">
            <h2>Cafés</h2>
            <div class="item">
                <img src="https://images.unsplash.com/photo-1514432324607-a09d9b4aefdd?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&q=80" 
                     alt="Espresso" 
                     class="item-image">
                <div class="item-info">
                    <h3>Espresso</h3>
                    <p>Un espresso clásico y fuerte, preparado con granos selectos</p>
                </div>
                <span>$2.00</span>
            </div>
            <div class="item">
                <img src="https://images.unsplash.com/photo-1534778101976-62847782c213?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&q=80" 
                     alt="Latte" 
                     class="item-image">
                <div class="item-info">
                    <h3>Latte</h3>
                    <p>Café suave con leche espumosa y arte latte personalizado</p>
                </div>
                <span>$3.50</span>
            </div>
        </section>

        <section class="menu-category">
            <h2>Tés y Bebidas Calientes</h2>
            <div class="item">
                <img src="https://images.unsplash.com/photo-1564890369478-c89ca6d9cde9?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&q=80" 
                     alt="Té Verde" 
                     class="item-image">
                <div class="item-info">
                    <h3>Té Verde</h3>
                    <p>Refrescante y natural, con notas de jazmín</p>
                </div>
                <span>$2.50</span>
            </div>
            <div class="item">
                <img src="https://images.unsplash.com/photo-1517578239113-b03992dcdd25?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&q=80" 
                     alt="Chocolate Caliente" 
                     class="item-image">
                <div class="item-info">
                    <h3>Chocolate Caliente</h3>
                    <p>Delicioso y cremoso, con chocolate belga</p>
                </div>
                <span>$3.00</span>
            </div>
        </section>

        <section class="menu-category">
            <h2>Postres</h2>
            <div class="item">
                <img src="https://images.unsplash.com/photo-1564355808539-22fda35bed7e?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&q=80" 
                     alt="Brownie" 
                     class="item-image">
                <div class="item-info">
                    <h3>Brownie</h3>
                    <p>Chocolate con nueces, servido caliente con helado</p>
                </div>
                <span>$1.50</span>
            </div>
            <div class="item">
                <img src="https://images.unsplash.com/photo-1524351199678-941a58a3df50?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&q=80" 
                     alt="Cheesecake" 
                     class="item-image">
                <div class="item-info">
                    <h3>Cheesecake</h3>
                    <p>Pastel de queso cremoso con frutos rojos</p>
                </div>
                <span>$2.50</span>
            </div>
        </section>
    </main>

    <footer>
        <p>Síguenos en nuestras redes sociales para más sorpresas</p>
        <img src="https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=https://example.com/cafe-menu" 
             alt="Código QR del Menú">
    </footer>
</body>
</html>
