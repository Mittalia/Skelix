
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Skelix - Your Journey From Idea to Reality</title>
    
    <!-- Google Fonts for typography -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;700&family=Playfair+Display:wght@400;700&family=Merriweather:wght@400;700&family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    
    <!-- Font Awesome for icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" xintegrity="sha512-DTOQO9RWCH3ppGqcWaEA1BIZOC6xxalwEsw9c2QQeAIftl+Vegovlnee1c9QX4TctnWMn13TZye+giMm8e2LwA==" crossorigin="anonymous" referrerpolicy="no-referrer" />

    <style>
        /* --- Global Styles and Variables --- */
        :root {
            --primary-font: 'Poppins', sans-serif;
            --logo-font: 'Playfair Display', serif;
            --gallery-font: 'Merriweather', serif;
            --text-color: #FFFFFF;
            --light-purple: #a491d2;
            --dark-purple: #3a2a62;
            --light-purple-rgb: 164, 145, 210;
            --bg-gradient: linear-gradient(120deg, var(--light-purple), var(--dark-purple));
            --footer-bg: rgba(30, 20, 60, 0.8);
            --card-bg: rgba(255, 255, 255, 0.1);
        }

        /* --- Base Reset --- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: var(--primary-font);
            background: var(--bg-gradient);
            color: var(--text-color);
            line-height: 1.7;
        }

        /* --- Typography --- */
        h1, h2, h3, h4 {
            font-family: var(--primary-font);
            font-weight: 700;
            line-height: 1.2;
        }

        h1 { font-size: 3.2rem; text-transform: uppercase; }
        h2 { font-size: 2.5rem; text-transform: uppercase; }
        h3 { font-size: 1.4rem; }
        p { font-size: 1rem; }
        a { color: var(--text-color); text-decoration: none; }
        ul { list-style: none; }

        /* --- Layout --- */
        section {
            padding: 6rem 5%;
            overflow: hidden;
        }
        
        main.hidden {
            display: none;
        }

        /* --- Header & Navigation --- */
        .main-header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
            padding: 1rem 5%;
            background: rgba(0,0,0,0.2);
            backdrop-filter: blur(8px);
            -webkit-backdrop-filter: blur(8px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            transition: background 0.5s ease, border-bottom-color 0.5s ease;
        }
        
        .main-header.gallery-active {
            background: var(--bg-gradient);
            border-bottom-color: rgba(255, 255, 255, 0.1);
        }
        
        .main-header.gallery-active .logo,
        .main-header.gallery-active .nav-links a {
            color: var(--text-color);
        }
        
        .main-header.gallery-active .nav-links a:hover {
            color: var(--light-purple);
        }
        
        .main-header.gallery-active .mobile-menu-button {
            color: var(--text-color);
        }


        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1400px;
            margin: 0 auto;
        }

        .logo {
            font-family: var(--logo-font);
            font-size: 2rem;
            font-weight: 700;
            transition: color 0.3s ease;
        }

        .nav-links {
            display: flex;
            gap: 2.5rem;
            align-items: center;
        }

        .nav-links a {
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .nav-links a:hover {
            color: var(--light-purple);
        }
        
        .show-code-btn {
            background-color: rgba(0,0,0,0.2);
            color: var(--text-color);
            border: 1px solid var(--text-color);
            padding: 0.5rem 1.5rem;
            border-radius: 20px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s ease;
            margin-left: 2rem;
        }
        
        .show-code-btn.hidden {
            display: none;
        }
        
        .show-code-btn:hover {
            background-color: var(--text-color);
            color: var(--dark-purple);
        }

        .mobile-menu-button {
            display: none;
            background: none;
            border: none;
            color: var(--text-color);
            font-size: 1.5rem;
            cursor: pointer;
            z-index: 1001;
        }

        /* --- Hero Section --- */
        .hero-section {
            display: flex;
            justify-content: center;
            align-items: center;
            text-align: center;
            min-height: 100vh;
        }

        .hero-content {
            max-width: 900px;
        }

        .hero-content h1 {
            margin-bottom: 1.5rem;
        }

        .hero-description {
            font-size: 1.2rem;
            margin-bottom: 2.5rem;
            opacity: 0.9;
        }

        .hero-buttons {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            flex-wrap: wrap;
        }

        .btn {
            padding: 0.8rem 2.5rem;
            border-radius: 50px;
            border: 2px solid var(--text-color);
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 1rem;
            text-transform: uppercase;
        }

        .btn-primary {
            background-color: var(--text-color);
            color: var(--dark-purple);
        }

        .btn-primary:hover {
            background-color: transparent;
            color: var(--text-color);
        }

        .btn-secondary {
            background-color: transparent;
            color: var(--text-color);
        }

        .btn-secondary:hover {
            background-color: var(--text-color);
            color: var(--dark-purple);
        }

        /* --- Services Section --- */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 4rem;
        }

        .service-card {
            background: var(--card-bg);
            padding: 2.5rem 2rem;
            text-align: left;
            border-radius: 12px;
            backdrop-filter: blur(10px);
            border: 2px solid transparent;
            transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.4s ease, background-color 0.4s ease;
            display: flex;
            flex-direction: column;
            height: 100%;
        }

        .service-card:hover {
            transform: translateY(-10px);
            border-color: var(--icon-color);
            box-shadow: 0 10px 30px rgba(0,0,0,0.2), 0 0 25px rgba(var(--icon-color-rgb), 0.5);
            background-color: rgba(var(--icon-color-rgb), 0.2);
        }

        .service-card .icon-container {
            width: 60px;
            height: 60px;
            display: flex;
            justify-content: center;
            align-items: center;
            border-radius: 8px;
            margin-bottom: 1.5rem;
            background-color: transparent;
            border: 3px solid var(--icon-color);
        }

        .service-card i {
            font-size: 2rem;
            color: var(--icon-color);
        }

        .service-card h3 {
            margin-bottom: 1rem;
        }

        /* --- About Us Section --- */
        .about-content {
            display: flex;
            align-items: center;
            gap: 4rem;
            margin-top: 2rem;
        }

        .about-image {
            flex: 1;
            background-color: rgba(255, 255, 255, 0.8);
            height: 400px;
            display: flex;
            justify-content: center;
            align-items: center;
            color: var(--dark-purple);
            font-weight: bold;
            font-size: 1.2rem;
            border-radius: 10px;
            min-width: 300px;
        }

        .about-text {
            flex: 1.5;
        }

        .about-text h3 {
            text-transform: uppercase;
            color: var(--light-purple);
            margin-bottom: 1rem;
            letter-spacing: 1px;
        }

        .about-text p {
            margin-bottom: 1.5rem;
            opacity: 0.9;
        }

        /* --- Footer Section --- */
        .footer-section {
            background: var(--footer-bg);
            padding: 4rem 5% 2rem;
            backdrop-filter: blur(10px);
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 2rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .footer-column .logo {
            font-size: 2.5rem;
        }

        .footer-column h4 {
            font-size: 1.2rem;
            margin-bottom: 1.5rem;
            font-weight: 500;
        }

        .footer-column ul li {
            margin-bottom: 0.8rem;
        }

        .footer-column a {
            opacity: 0.8;
            transition: opacity 0.3s ease;
        }

        .footer-column a:hover {
            opacity: 1;
            text-decoration: underline;
        }

        /* --- Modal Styles --- */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.6);
            backdrop-filter: blur(5px);
            -webkit-backdrop-filter: blur(5px);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 2000;
            opacity: 1;
            transition: opacity 0.3s ease-in-out;
        }

        .modal-overlay.hidden {
            opacity: 0;
            pointer-events: none;
        }

        .modal-content {
            background: var(--dark-purple);
            padding: 3rem;
            border-radius: 15px;
            text-align: center;
            max-width: 500px;
            width: 90%;
            position: relative;
            box-shadow: 0 5px 25px rgba(0,0,0,0.4);
            transform: scale(1);
            transition: transform 0.3s ease-in-out;
        }

        .modal-overlay.hidden .modal-content {
            transform: scale(0.9);
        }

        .modal-content h2 {
            font-size: 2rem;
            margin-bottom: 1rem;
            text-transform: none;
        }

        .modal-content p {
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .close-button {
            position: absolute;
            top: 15px;
            right: 20px;
            font-size: 2.5rem;
            font-weight: bold;
            color: var(--text-color);
            cursor: pointer;
            transition: transform 0.2s ease;
        }

        .close-button:hover {
            transform: scale(1.2);
        }

        .btn-modal {
            background-color: var(--light-purple);
            color: var(--text-color);
            border: none;
            padding: 0.8rem 3rem;
            border-radius: 50px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 1rem;
            text-transform: uppercase;
        }

        .btn-modal:hover {
            background-color: #b8a6de; /* A lighter shade of light-purple */
        }

        /* --- Multi-Step Modal Styles --- */
        .modal-step.hidden {
            display: none;
        }

        .choice-buttons {
            display: flex;
            flex-direction: column;
            gap: 1rem;
            margin: 2rem 0;
        }

        .btn-choice {
            width: 100%;
            padding: 1rem;
            border-radius: 10px;
            background-color: rgba(255, 255, 255, 0.1);
            border: 2px solid rgba(255, 255, 255, 0.2);
            color: var(--text-color);
            font-size: 1.1rem;
            font-weight: 500;
            cursor: pointer;
            transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease, background-color 0.3s ease;
        }

        .btn-choice:hover,
        .btn-choice.active {
            transform: translateY(-5px);
            border-color: var(--light-purple);
            box-shadow: 0 5px 20px rgba(0,0,0,0.2), 0 0 15px rgba(var(--light-purple-rgb), 0.5);
            background-color: rgba(var(--light-purple-rgb), 0.2);
        }
        
        .btn-choice-solid {
            background-color: rgba(255, 255, 255, 0.1);
            border: 2px solid rgba(255, 255, 255, 0.2);
        }

        .btn-choice-solid:hover {
             background-color: rgba(255, 255, 255, 0.2);
             border-color: var(--light-purple);
        }

        .btn-choice-solid.active {
            background-color: var(--dark-purple);
            border-color: var(--light-purple);
            box-shadow: 0 5px 20px rgba(0,0,0,0.2);
        }


        .navigation-buttons {
            display: flex;
            justify-content: flex-start; /* Aligns button to the left */
            width: 100%;
            margin-top: 1rem;
        }

        .btn-previous {
            background: transparent;
            color: var(--text-color);
            border: none;
            padding: 0.5rem 1rem;
            font-size: 1rem;
            font-weight: 500;
            cursor: pointer;
            transition: color 0.3s ease;
        }

        .btn-previous:hover {
            color: var(--light-purple);
        }

        /* --- Gallery & Editorial Page Styles --- */
        #gallery-page, #editorial-page {
            padding: 80px 0 0 0;
            background-color: transparent;
            position: relative;
        }
        
        .page-wrapper {
            display: flex;
            position: relative;
        }
        
        .page-container {
            --page-bg: #FFFFFF;
            --page-text: #212121;
            --page-accent: #C5B358;
            --page-secondary-bg: #e9e5e1;
            --page-heading-font: 'Merriweather', serif;
            --page-body-font: 'Poppins', sans-serif;
            
            flex-grow: 1;
            background-color: var(--page-bg);
            color: var(--page-text);
            transition: color 0.5s ease, background-color 0.5s ease;
        }
        
        .page-container.theme-noir-gold {
            --page-bg: #F8F5F2;
            --page-text: #212121;
            --page-accent: #C5B358;
            --page-secondary-bg: #e0e0e0;
        }
        .page-container.theme-champagne-ivory {
            --page-bg: #FFFDD0;
            --page-text: #706555;
            --page-accent: #D2B48C;
            --page-secondary-bg: #F0EAD6;
        }
        .page-container.theme-deep-jewel {
            --page-bg: #F8F5F2;
            --page-text: #000080;
            --page-accent: #006400;
            --page-secondary-bg: #e0e0e0;
        }
        
        .page-container.font-classic-serif {
            --page-heading-font: 'Playfair Display', serif;
            --page-body-font: 'Poppins', sans-serif;
        }
        .page-container.font-modern-minimalist {
            --page-heading-font: 'Roboto', sans-serif;
            --page-body-font: 'Roboto', sans-serif;
        }
        .page-container.font-understated-refined {
            --page-heading-font: 'Merriweather', serif;
            --page-body-font: 'Merriweather', serif;
        }
        
        .gallery-inner-nav {
            display: flex;
            justify-content: center;
            gap: 2rem;
            padding: 1.5rem 0;
            border-bottom: 1px solid #ddd;
            font-family: var(--primary-font);
        }
        
        .gallery-inner-nav a {
            color: var(--page-text);
            font-weight: 500;
            position: relative;
            transition: color 0.5s ease;
        }
        
        .gallery-inner-nav a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--page-text);
            transition: width 0.3s ease, background-color 0.5s ease;
        }
        
        .gallery-inner-nav a:hover::after {
            width: 100%;
        }

        .gallery-hero {
            text-align: center;
            padding: 4rem 5%;
        }
        
        .gallery-hero h1 {
            font-family: var(--page-heading-font);
            font-size: 4rem;
            font-weight: 400;
            color: var(--page-text);
            text-transform: none;
            margin-bottom: 1rem;
            transition: color 0.5s ease, font-family 0.5s ease;
        }
        
        .gallery-hero p {
            font-family: var(--page-body-font);
            font-size: 1.2rem;
            max-width: 600px;
            margin: 0 auto;
            line-height: 1.6;
            transition: color 0.5s ease, font-family 0.5s ease;
        }
        
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 3rem;
            padding: 2rem 5%;
        }
        
        .product-item {
            text-align: left;
        }
        
        .product-image-container {
            position: relative;
            height: 400px;
            margin-bottom: 1rem;
            cursor: pointer;
            overflow: hidden;
        }

        .product-image-placeholder {
            width: 100%;
            height: 100%;
            background-color: var(--page-secondary-bg);
            transition: background-color 0.5s ease;
        }
        
        .product-hover-details {
            position: absolute;
            top: 1rem;
            left: 1rem;
            background-color: rgba(255,255,255,0.9);
            color: var(--gallery-text-color);
            padding: 0.5rem 1rem;
            border-radius: 20px;
            opacity: 0;
            transform: translateY(10px);
            transition: opacity 0.3s ease, transform 0.3s ease;
            font-family: var(--primary-font);
            font-size: 0.9rem;
        }
        
        .product-image-container:hover .product-hover-details {
            opacity: 1;
            transform: translateY(0);
        }
        
        .product-info {
            padding: 0 0.5rem;
        }
        
        .product-number {
            font-family: var(--primary-font);
            font-size: 0.9rem;
            color: #888;
            display: block;
            margin-bottom: 0.5rem;
        }
        
        .product-name {
            font-family: var(--page-heading-font);
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            color: var(--page-text);
            transition: color 0.5s ease, font-family 0.5s ease;
        }
        
        .product-price {
            font-size: 1.2rem;
            color: var(--page-accent);
            transition: color 0.5s ease;
        }
        
        .philosophy-section {
            text-align: center;
            padding: 6rem 5%;
        }
        
        .philosophy-section h2 {
            font-family: var(--pa
