# ShopSphere

## 🔗My website is live
👉 [Click here to view the website](https://shadow44343455454.github.io/shopsphere/)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    ShopSphere | Premium E-commerce Experience
    
    <!-- Favicon -->
    <link rel="icon" type="image/svg+xml" href="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI0OCIgaGVpZ2h0PSI0OCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSIjNGE2ZGU1IiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMC41Ij48Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIxMCI+PC9jaXJjbGU+PHBhdGggZD0ibTggOSA0IDQgNC00IiBmaWxsPSJub25lIj48L3BhdGg+PC9zdmc+" />
    
    <!-- External Libraries -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.7/dist/css/bootstrap.min.css" rel="stylesheet">
    
    <style>
        :root {
            --primary: #4a6de5;
            --primary-dark: #3a5bd0;
            --primary-light: #6b8ef7;
            --secondary: #ff6b6b;
            --secondary-dark: #ff5252;
            --accent: #20c997;
            --accent-dark: #1ea085;
            --success: #28a745;
            --warning: #ffc107;
            --danger: #dc3545;
            --info: #17a2b8;
            --dark: #2c3e50;
            --dark-light: #34495e;
            --light: #f8f9fa;
            --gray: #6c757d;
            --gray-light: #adb5bd;
            --gray-dark: #495057;
            --white: #ffffff;
            --black: #000000;
            --border: #dee2e6;
            --border-dark: #ced4da;
            --shadow: 0 4px 6px rgba(0,0,0,0.1);
            --shadow-lg: 0 10px 30px rgba(0,0,0,0.1);
            --shadow-xl: 0 20px 50px rgba(0,0,0,0.15);
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            --transition-slow: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
            --glass: rgba(255, 255, 255, 0.15);
            --glass-border: rgba(255, 255, 255, 0.2);
            --gradient-primary: linear-gradient(135deg, var(--primary) 0%, var(--primary-dark) 100%);
            --gradient-secondary: linear-gradient(135deg, var(--secondary) 0%, var(--secondary-dark) 100%);
            --gradient-light: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
            --spacing-xs: 0.25rem;
            --spacing-sm: 0.5rem;
            --spacing-md: 1rem;
            --spacing-lg: 1.5rem;
            --spacing-xl: 2rem;
            --spacing-2xl: 3rem;
            --spacing-3xl: 4rem;
            --radius-sm: 0.375rem;
            --radius-md: 0.5rem;
            --radius-lg: 0.75rem;
            --radius-xl: 1rem;
            --radius-2xl: 1.5rem;
            --radius-full: 9999px;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Poppins', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            color: var(--dark);
            background-color: var(--white);
            line-height: 1.6;
            overflow-x: hidden;
            font-size: 16px;
        }

        /* Loading Screen */
        .loading-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--gradient-primary);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            z-index: 9999;
            transition: opacity 2s ease-out, visibility 2s ease-out;
        }

        .loading-screen.fade-out {
            opacity: 0;
            visibility: hidden;
        }

        .loading-logo {
            width: 120px;
            height: 120px;
            background: var(--white);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: var(--spacing-xl);
            box-shadow: var(--shadow-xl);
            animation: pulse-loader 2s infinite ease-in-out;
        }

        .loading-logo i {
            font-size: 3rem;
            color: var(--primary);
            animation: rotate-slow 3s linear infinite;
        }

        .loading-text {
            color: var(--white);
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: var(--spacing-md);
            animation: fadeInUp 1s ease-out;
        }

        .loading-subtitle {
            color: rgba(255, 255, 255, 0.8);
            font-size: 1.1rem;
            font-weight: 400;
            animation: fadeInUp 1s ease-out 0.3s both;
        }

        .loading-progress {
            width: 300px;
            height: 4px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: var(--radius-full);
            margin-top: var(--spacing-xl);
            overflow: hidden;
            animation: fadeInUp 1s ease-out 0.6s both;
        }

        .loading-progress-bar {
            width: 0%;
            height: 100%;
            background: var(--white);
            border-radius: var(--radius-full);
            animation: loading-progress 3s ease-in-out forwards;
        }

        @keyframes pulse-loader {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        @keyframes rotate-slow {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        @keyframes loading-progress {
            to { width: 100%; }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Global Styles */
        .section {
            padding: var(--spacing-3xl) 0;
            position: relative;
        }

        .section-title {
            text-align: center;
            margin-bottom: var(--spacing-3xl);
            font-size: clamp(2rem, 5vw, 3.5rem);
            font-weight: 800;
            position: relative;
            color: var(--dark);
            line-height: 1.2;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 5px;
            background: var(--gradient-primary);
            border-radius: var(--radius-md);
        }

        .section-subtitle {
            text-align: center;
            max-width: 600px;
            margin: 0 auto var(--spacing-2xl);
            font-size: 1.2rem;
            color: var(--gray);
            font-weight: 400;
        }

   
        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: var(--spacing-sm);
            padding: 14px 32px;
            background: var(--primary);
            color: var(--white);
            border: none;
            border-radius: var(--radius-full);
            text-decoration: none;
            font-weight: 600;
            font-size: 1rem;
            transition: var(--transition);
            cursor: pointer;
            position: relative;
            overflow: hidden;
            z-index: 1;
            box-shadow: var(--shadow);
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: var(--primary-dark);
            transition: var(--transition-slow);
            z-index: -1;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: var(--shadow-lg);
            color: var(--white);
        }

        .btn:hover::before {
            left: 0;
        }

        .btn-outline {
            background: transparent;
            color: var(--primary);
            border: 2px solid var(--primary);
        }

        .btn-outline::before {
            background: var(--primary);
        }

        .btn-outline:hover {
            color: var(--white);
            border-color: var(--primary);
        }

        .btn-secondary {
            background: var(--secondary);
        }

        .btn-secondary::before {
            background: var(--secondary-dark);
        }

        .btn-accent {
            background: var(--accent);
        }

        .btn-accent::before {
            background: var(--accent-dark);
        }

        .btn-lg {
            padding: 18px 40px;
            font-size: 1.1rem;
        }

        .btn-sm {
            padding: 10px 20px;
            font-size: 0.9rem;
        }

   
        .glass-card {
            background: var(--glass);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border-radius: var(--radius-xl);
            border: 1px solid var(--glass-border);
            box-shadow: var(--shadow-xl);
            position: relative;
            overflow: hidden;
            transition: var(--transition);
        }

        .glass-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 1px;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.4), transparent);
        }

        .glass-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 25px 60px rgba(0,0,0,0.12);
        }

        /* Header Styles */
        .header-top {
            background: var(--dark);
            color: var(--white);
            padding: var(--spacing-sm) 0;
            font-size: 0.9rem;
            position: relative;
            overflow: hidden;
        }

        .header-top::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.1), transparent);
            animation: slide-shine 3s infinite;
        }

        @keyframes slide-shine {
            0% { left: -100%; }
            50% { left: 100%; }
            100% { left: -100%; }
        }

        .header-top-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

        .contact-info a {
            color: var(--white);
            text-decoration: none;
            margin-right: var(--spacing-lg);
            transition: var(--transition);
            display: inline-flex;
            align-items: center;
            gap: var(--spacing-xs);
        }

        .contact-info a:hover {
            color: var(--primary-light);
            transform: translateY(-2px);
        }

        .social-icons {
            display: flex;
            gap: var(--spacing-md);
        }

        .social-icons a {
            color: var(--white);
            font-size: 1.1rem;
            transition: var(--transition);
            width: 32px;
            height: 32px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            background: rgba(255,255,255,0.1);
        }

        .social-icons a:hover {
            color: var(--white);
            background: var(--primary);
            transform: translateY(-3px) scale(1.1);
        }

        header {
            background: var(--white);
            box-shadow: var(--shadow);
            position:relative;
            top: 0;
            z-index: 1000;
            transition: var(--transition);
        }

        .main-header {
            padding: var(--spacing-lg) 0;
            border-bottom: 1px solid var(--border);
        }

        .header-content {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: var(--spacing-lg);
        }

        .logo {
            display: flex;
            align-items: center;
            text-decoration: none;
            transition: var(--transition);
        }

        .logo:hover {
            transform: scale(1.02);
        }

        .logo-icon {
            width: 60px;
            height: 60px;
            background: var(--gradient-primary);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: var(--spacing-md);
            box-shadow: var(--shadow);
            animation: logo-float 6s ease-in-out infinite;
        }

        .logo-icon i {
            font-size: 1.8rem;
            color: var(--white);
        }

        .logo-text h1 {
            font-size: 2.2rem;
            font-weight: 800;
            background: var(--gradient-primary);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin: 0;
            line-height: 1;
        }

        .logo-text span {
            font-size: 0.8rem;
            color: var(--gray);
            font-weight: 400;
            display: block;
            margin-top: var(--spacing-xs);
            letter-spacing: 2px;
            text-transform: uppercase;
        }

        @keyframes logo-float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-5px); }
        }

        .search-bar {
            flex: 1;
            max-width: 600px;
            position: relative;
        }

        .search-container {
            position: relative;
            display: flex;
            align-items: center;
            background: var(--light);
            border-radius: var(--radius-full);
            overflow: hidden;
            transition: var(--transition);
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
        }

        .search-container:focus-within {
            box-shadow: 0 0 0 3px rgba(74, 109, 229, 0.2);
            transform: scale(1.02);
        }

        .search-container input {
            flex: 1;
            padding: 16px 24px;
            border: none;
            background: transparent;
            font-size: 1rem;
            outline: none;
        }

        .search-container button {
            background: var(--primary);
            border: none;
            color: var(--white);
            padding: 16px 24px;
            cursor: pointer;
            transition: var(--transition);
            font-size: 1rem;
        }

        .search-container button:hover {
            background: var(--primary-dark);
        }

        .header-actions {
            display: flex;
            gap: var(--spacing-lg);
            align-items: center;
        }

        .action-link {
            position: relative;
            color: var(--dark);
            font-size: 1.5rem;
            text-decoration: none;
            transition: var(--transition);
            padding: var(--spacing-sm);
            border-radius: 50%;
            background: transparent;
        }

        .action-link:hover {
            color: var(--primary);
            transform: translateY(-3px) scale(1.1);
            background: rgba(74, 109, 229, 0.1);
        }

        .cart-badge {
            position: absolute;
            top: -5px;
            right: -5px;
            background: var(--secondary);
            color: var(--white);
            font-size: 0.7rem;
            width: 22px;
            height: 22px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            animation: pulse-badge 2s infinite;
        }

        @keyframes pulse-badge {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        /*  Navigation */
        .main-navigation {
            background: var(--primary);
            position: relative;
            overflow: hidden;
        }

        .main-navigation::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, transparent 30%, rgba(255,255,255,0.1) 50%, transparent 70%);
            transform: translateX(-100%);
            transition: transform 0.6s ease;
        }

        .main-navigation:hover::before {
            transform: translateX(100%);
        }

        .navbar-nav {
            gap: var(--spacing-xs);
        }

        .nav-link {
            color: var(--white);
            font-weight: 500;
            padding: 18px 24px;
            border-radius: var(--radius-sm);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .nav-link::before {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            width: 0;
            height: 3px;
            background: var(--white);
            transition: var(--transition);
            transform: translateX(-50%);
        }

        .nav-link:hover {
            color: var(--white);
            background: rgba(255,255,255,0.15);
            transform: translateY(-2px);
        }

        .nav-link:hover::before {
            width: 80%;
        }

        .dropdown-menu {
            background: var(--white);
            border: none;
            border-radius: var(--radius-lg);
            box-shadow: var(--shadow-xl);
            margin-top: var(--spacing-sm);
            padding: var(--spacing-sm);
            min-width: 250px;
            transform: translateY(-10px);
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
        }

        .nav-item.dropdown:hover .dropdown-menu {
            transform: translateY(0);
            opacity: 1;
            visibility: visible;
        }

        .dropdown-item {
            color: var(--dark);
            padding: 12px 20px;
            border-radius: var(--radius-sm);
            transition: var(--transition);
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: var(--spacing-sm);
        }

        .dropdown-item:hover {
            background: var(--light);
            color: var(--primary);
            transform: translateX(5px);
        }

        .dropdown-divider {
            margin: var(--spacing-sm) 0;
            border-color: var(--border);
        }

        /* Hero Section */
        .hero {
            background: var(--gradient-primary);
            color: var(--white);
            padding: 120px 0;
            text-align: center;
            position: relative;
            overflow: hidden;
            min-height: 80vh;
            display: flex;
            align-items: center;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-image: 
                radial-gradient(circle at 25% 25%, rgba(255,255,255,0.1) 1px, transparent 1px),
                radial-gradient(circle at 75% 75%, rgba(255,255,255,0.05) 1px, transparent 1px);
            background-size: 50px 50px;
            animation: float-pattern 20s linear infinite;
        }

        @keyframes float-pattern {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 900px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: clamp(2.5rem, 8vw, 5rem);
            font-weight: 800;
            margin-bottom: var(--spacing-lg);
            text-shadow: 0 4px 8px rgba(0,0,0,0.2);
            line-height: 1.1;
            animation: hero-title 1s ease-out;
        }

        .hero-subtitle {
            font-size: clamp(1.1rem, 4vw, 1.6rem);
            margin-bottom: var(--spacing-2xl);
            opacity: 0.95;
            font-weight: 400;
            animation: hero-subtitle 1s ease-out 0.3s both;
        }

        .hero-actions {
            display: flex;
            justify-content: center;
            gap: var(--spacing-lg);
            flex-wrap: wrap;
            animation: hero-actions 1s ease-out 0.6s both;
        }

        @keyframes hero-title {
            from {
                opacity: 0;
                transform: translateY(50px) scale(0.9);
            }
            to {
                opacity: 1;
                transform: translateY(0) scale(1);
            }
        }

        @keyframes hero-subtitle {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 0.95;
                transform: translateY(0);
            }
        }

        @keyframes hero-actions {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Floating Particles */
        .particles {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .particle {
            position: absolute;
            background: rgba(255, 255, 255, 0.6);
            border-radius: 50%;
            animation: float-up linear infinite;
        }

        @keyframes float-up {
            0% {
                transform: translateY(0) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(-1000px) rotate(720deg);
                opacity: 0;
            }
        }

        /* Categories Section */
        .categories {
            background: var(--gradient-light);
            position: relative;
        }

        .category-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: var(--spacing-xl);
            padding: var(--spacing-xl) 0;
        }

        .category-card {
            background: var(--white);
            border-radius: var(--radius-xl);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition-slow);
            text-align: center;
            position: relative;
            transform: translateY(30px);
            opacity: 0;
        }

        .category-card.animate {
            transform: translateY(0);
            opacity: 1;
        }

        .category-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: var(--shadow-xl);
        }

        .category-image {
            height: 200px;
            background: var(--gradient-light);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .category-image::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: var(--gradient-primary);
            opacity: 0;
            transition: var(--transition);
        }

        .category-card:hover .category-image::before {
            opacity: 0.1;
        }

        .category-image i {
            font-size: 4rem;
            color: var(--primary);
            transition: var(--transition-slow);
            position: relative;
            z-index: 2;
        }

        .category-card:hover .category-image i {
            transform: scale(1.2) rotate(5deg);
            color: var(--primary-dark);
        }

        .category-info {
            padding: var(--spacing-xl);
        }

        .category-info h3 {
            font-size: 1.4rem;
            font-weight: 600;
            margin-bottom: var(--spacing-sm);
            color: var(--dark);
        }

        .category-info p {
            color: var(--gray);
            font-size: 0.95rem;
            margin: 0;
        }

        /* Product Cards */
        .products-section {
            background: var(--white);
        }

        .products-filter {
            display: flex;
            justify-content: center;
            gap: var(--spacing-md);
            margin-bottom: var(--spacing-3xl);
            flex-wrap: wrap;
        }

        .filter-btn {
            padding: 12px 24px;
            background: var(--white);
            border: 2px solid var(--border);
            border-radius: var(--radius-full);
            cursor: pointer;
            transition: var(--transition);
            font-weight: 500;
            color: var(--dark);
            position: relative;
            overflow: hidden;
        }

        .filter-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: var(--primary);
            transition: var(--transition-slow);
            z-index: -1;
        }

        .filter-btn:hover,
        .filter-btn.active {
            color: var(--white);
            border-color: var(--primary);
            transform: translateY(-2px);
            box-shadow: var(--shadow);
        }

        .filter-btn:hover::before,
        .filter-btn.active::before {
            left: 0;
        }

        .product-card {
            background: var(--white);
            border-radius: var(--radius-xl);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition-slow);
            position: relative;
            height: 100%;
            display: flex;
            flex-direction: column;
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-xl);
        }

        .product-badge {
            position: absolute;
            top: var(--spacing-md);
            left: var(--spacing-md);
            background: var(--secondary);
            color: var(--white);
            padding: 6px 12px;
            border-radius: var(--radius-sm);
            font-size: 0.8rem;
            font-weight: 600;
            z-index: 10;
            box-shadow: var(--shadow);
            animation: badge-glow 2s ease-in-out infinite alternate;
        }

        @keyframes badge-glow {
            0% { box-shadow: var(--shadow); }
            100% { box-shadow: 0 0 15px rgba(255, 107, 107, 0.5); }
        }

        .product-image {
            height: 280px;
            background: var(--gradient-light);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .product-image i {
            font-size: 5rem;
            transition: var(--transition-slow);
        }

        .product-card:hover .product-image i {
            transform: scale(1.1) rotate(5deg);
        }

        .product-actions {
            position: absolute;
            top: 50%;
            right: -80px;
            transform: translateY(-50%);
            display: flex;
            flex-direction: column;
            gap: var(--spacing-sm);
            transition: var(--transition-slow);
        }

        .product-card:hover .product-actions {
            right: var(--spacing-md);
        }

        .product-action-btn {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background: var(--white);
            border: 1px solid var(--border);
            color: var(--dark);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
            cursor: pointer;
            box-shadow: var(--shadow);
        }

        .product-action-btn:hover {
            background: var(--primary);
            color: var(--white);
            transform: scale(1.1);
            border-color: var(--primary);
        }

        .product-info {
            padding: var(--spacing-xl);
            flex: 1;
            display: flex;
            flex-direction: column;
        }

        .product-category {
            font-size: 0.85rem;
            color: var(--gray);
            margin-bottom: var(--spacing-xs);
            text-transform: uppercase;
            letter-spacing: 1px;
            font-weight: 500;
        }

        .product-title {
            font-weight: 600;
            margin-bottom: var(--spacing-md);
            font-size: 1.2rem;
            color: var(--dark);
            line-height: 1.3;
        }

        .product-description {
            color: var(--gray);
            font-size: 0.9rem;
            margin-bottom: var(--spacing-md);
            flex: 1;
        }

        .product-price {
            display: flex;
            align-items: center;
            gap: var(--spacing-md);
            margin-bottom: var(--spacing-md);
        }

        .current-price {
            font-weight: 700;
            font-size: 1.4rem;
            color: var(--primary);
        }

        .old-price {
            color: var(--gray);
            text-decoration: line-through;
            font-size: 1rem;
        }

        .discount-badge {
            background: var(--success);
            color: var(--white);
            padding: 4px 8px;
            border-radius: var(--radius-sm);
            font-size: 0.75rem;
            font-weight: 600;
        }

        .product-rating {
            display: flex;
            align-items: center;
            gap: var(--spacing-sm);
            margin-bottom: var(--spacing-lg);
        }

        .rating-stars {
            color: var(--warning);
            display: flex;
            gap: 2px;
        }

        .rating-count {
            color: var(--gray);
            font-size: 0.9rem;
        }

        .product-footer {
            display: flex;
            gap: var(--spacing-md);
            margin-top: auto;
        }

        /* Special Offers Section */
        .offers-section {
            background: var(--gradient-light);
            position: relative;
            overflow: hidden;
        }

        .offers-container {
            position: relative;
            z-index: 2;
        }

        .offer-slider {
            display: flex;
            gap: var(--spacing-xl);
            overflow-x: auto;
            padding: var(--spacing-lg) 0;
            scroll-snap-type: x mandatory;
            scrollbar-width: thin;
            scrollbar-color: var(--primary) var(--light);
        }

        .offer-slider::-webkit-scrollbar {
            height: 8px;
        }

        .offer-slider::-webkit-scrollbar-track {
            background: var(--light);
            border-radius: var(--radius-sm);
        }

        .offer-slider::-webkit-scrollbar-thumb {
            background: var(--primary);
            border-radius: var(--radius-sm);
        }

        .offer-card {
            min-width: 400px;
            background: var(--white);
            border-radius: var(--radius-xl);
            overflow: hidden;
            box-shadow: var(--shadow);
            display: flex;
            scroll-snap-align: start;
            transition: var(--transition);
            position: relative;
        }

        .offer-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: var(--gradient-secondary);
        }

        .offer-card:hover {
            transform: scale(1.02);
            box-shadow: var(--shadow-xl);
        }

        .offer-image {
            width: 40%;
            background: var(--gradient-light);
            display: flex;
            align-items: center;
            justify-content: center;
            padding: var(--spacing-2xl);
            position: relative;
        }

        .offer-image i {
            font-size: 4rem;
            color: var(--primary);
            animation: offer-icon-float 3s ease-in-out infinite;
        }

        @keyframes offer-icon-float {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-10px) rotate(5deg); }
        }

        .offer-content {
            width: 60%;
            padding: var(--spacing-2xl);
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .offer-tag {
            background: var(--gradient-secondary);
            color: var(--white);
            display: inline-block;
            padding: 6px 12px;
            border-radius: var(--radius-sm);
            font-size: 0.85rem;
            margin-bottom: var(--spacing-md);
            font-weight: 600;
            align-self: flex-start;
            box-shadow: var(--shadow);
        }

        .offer-title {
            font-size: 1.4rem;
            font-weight: 700;
            margin-bottom: var(--spacing-md);
            color: var(--dark);
        }

        .offer-description {
            color: var(--gray);
            margin-bottom: var(--spacing-lg);
            font-size: 0.95rem;
        }

        .countdown-timer {
            display: flex;
            gap: var(--spacing-md);
            margin-bottom: var(--spacing-lg);
            justify-content: flex-start;
        }

        .timer-unit {
            background: var(--dark);
            color: var(--white);
            width: 60px;
            height: 60px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            border-radius: var(--radius-md);
            box-shadow: var(--shadow);
            position: relative;
            overflow: hidden;
        }

        .timer-unit::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: var(--gradient-primary);
            opacity: 0;
            transition: var(--transition);
        }

        .timer-unit:hover::before {
            opacity: 1;
        }

        .timer-value {
            font-weight: 700;
            font-size: 1.3rem;
            position: relative;
            z-index: 2;
        }

        .timer-label {
            font-size: 0.7rem;
            opacity: 0.8;
            position: relative;
            z-index: 2;
        }

        /* Features Section */
        .features-section {
            background: var(--white);
            position: relative;
        }

        .feature-card {
            text-align: center;
            padding: var(--spacing-2xl);
            border-radius: var(--radius-xl);
            background: var(--white);
            box-shadow: var(--shadow);
            transition: var(--transition);
            height: 100%;
            position: relative;
            overflow: hidden;
        }

        .feature-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: var(--gradient-primary);
            opacity: 0;
            transition: var(--transition-slow);
            transform: scale(0);
            border-radius: 50%;
        }

        .feature-card:hover::before {
            opacity: 0.05;
            transform: scale(2);
        }

        .feature-icon {
            width: 80px;
            height: 80px;
            background: var(--gradient-primary);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto var(--spacing-lg);
            transition: var(--transition);
            position: relative;
            z-index: 2;
        }

        .feature-card:hover .feature-icon {
            transform: scale(1.1) rotate(10deg);
            box-shadow: var(--shadow-lg);
        }

        .feature-icon i {
            font-size: 2rem;
            color: var(--white);
        }

        .feature-title {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: var(--spacing-md);
            color: var(--dark);
            position: relative;
            z-index: 2;
        }

        .feature-description {
            color: var(--gray);
            font-size: 0.95rem;
            line-height: 1.6;
            position: relative;
            z-index: 2;
        }

        /* Brands Section */
        .brands-section {
            background: var(--light);
            padding: var(--spacing-3xl) 0;
        }

        .brands-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: var(--spacing-xl);
            align-items: center;
        }

        .brand-item {
            background: var(--white);
            height: 120px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: var(--radius-lg);
            transition: var(--transition);
            filter: grayscale(100%);
            opacity: 0.6;
            position: relative;
            overflow: hidden;
        }

        .brand-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(74,109,229,0.1), transparent);
            transition: var(--transition-slow);
        }

        .brand-item:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: var(--shadow-lg);
            filter: grayscale(0%);
            opacity: 1;
        }

        .brand-item:hover::before {
            left: 100%;
        }

        .brand-item i {
            font-size: 2.5rem;
            color: var(--primary);
            transition: var(--transition);
        }

        .brand-item:hover i {
            transform: scale(1.1);
        }

        /* Newsletter Section */
        .newsletter-section {
            background: var(--gradient-primary);
            color: var(--white);
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .newsletter-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 20"><defs><pattern id="b" patternUnits="userSpaceOnUse" width="100" height="20"><circle cx="50" cy="10" r="2" fill="%23ffffff" opacity="0.1"/></pattern></defs><rect width="100%" height="100%" fill="url(%23b)"/></svg>');
            animation: pattern-move 20s linear infinite;
        }

        @keyframes pattern-move {
            0% { transform: translateX(0); }
            100% { transform: translateX(100px); }
        }

        .newsletter-content {
            position: relative;
            z-index: 2;
            max-width: 600px;
            margin: 0 auto;
        }

        .newsletter-title {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: var(--spacing-lg);
            text-shadow: 0 2px 4px rgba(0,0,0,0.2);
        }

        .newsletter-subtitle {
            font-size: 1.2rem;
            opacity: 0.9;
            margin-bottom: var(--spacing-2xl);
        }

        .newsletter-form {
            display: flex;
            max-width: 500px;
            margin: 0 auto;
            gap: var(--spacing-md);
            background: rgba(255,255,255,0.1);
            padding: 8px;
            border-radius: var(--radius-full);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255,255,255,0.2);
        }

        .newsletter-form input {
            flex: 1;
            padding: 16px 24px;
            border: none;
            background: transparent;
            color: var(--white);
            font-size: 1rem;
            outline: none;
            border-radius: var(--radius-full);
        }

        .newsletter-form input::placeholder {
            color: rgba(255,255,255,0.7);
        }

        .newsletter-form button {
            background: var(--secondary);
            color: var(--white);
            border: none;
            padding: 16px 32px;
            border-radius: var(--radius-full);
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            white-space: nowrap;
        }

        .newsletter-form button:hover {
            background: var(--secondary-dark);
            transform: scale(1.05);
        }

        /* Footer */
        footer {
            background: var(--dark);
            color: var(--white);
            position: relative;
            overflow: hidden;
        }

        footer::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, transparent 30%, rgba(74,109,229,0.05) 50%, transparent 70%);
            animation: footer-shimmer 8s linear infinite;
        }

        @keyframes footer-shimmer {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        .footer-main {
            padding: var(--spacing-3xl) 0 var(--spacing-2xl);
            position: relative;
            z-index: 2;
        }

        .footer-column h3 {
            font-size: 1.4rem;
            margin-bottom: var(--spacing-lg);
            font-weight: 600;
            position: relative;
            padding-bottom: var(--spacing-md);
        }

        .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 60px;
            height: 3px;
            background: var(--primary);
            border-radius: var(--radius-sm);
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: var(--spacing-md);
        }

        .footer-links a {
            color: rgba(255,255,255,0.8);
            text-decoration: none;
            transition: var(--transition);
            display: inline-flex;
            align-items: center;
            gap: var(--spacing-sm);
            padding: var(--spacing-xs) 0;
        }

        .footer-links a:hover {
            color: var(--white);
            transform: translateX(8px);
            padding-left: var(--spacing-sm);
        }

        .footer-links a::before {
            content: '→';
            opacity: 0;
            transform: translateX(-10px);
            transition: var(--transition);
        }

        .footer-links a:hover::before {
            opacity: 1;
            transform: translateX(0);
        }

        .footer-social {
            display: flex;
            gap: var(--spacing-md);
            margin-top: var(--spacing-lg);
        }

        .social-link {
            width: 50px;
            height: 50px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            text-decoration: none;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .social-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: var(--gradient-primary);
            opacity: 0;
            transition: var(--transition);
            border-radius: 50%;
            transform: scale(0);
        }

        .social-link:hover {
            transform: translateY(-5px) scale(1.1);
            color: var(--white);
        }

        .social-link:hover::before {
            opacity: 1;
            transform: scale(1);
        }

        .social-link i {
            position: relative;
            z-index: 2;
            font-size: 1.2rem;
        }

        .contact-info {
            display: flex;
            align-items: flex-start;
            gap: var(--spacing-md);
            margin-bottom: var(--spacing-lg);
            color: rgba(255,255,255,0.8);
            transition: var(--transition);
        }

        .contact-info:hover {
            color: var(--white);
            transform: translateX(5px);
        }

        .contact-info i {
            margin-top: 3px;
            color: var(--primary);
            font-size: 1.1rem;
            transition: var(--transition);
        }

        .payment-methods {
            display: flex;
            gap: var(--spacing-md);
            flex-wrap: wrap;
            margin-top: var(--spacing-lg);
        }

        .payment-method {
            background: rgba(255,255,255,0.1);
            padding: 8px 16px;
            border-radius: var(--radius-sm);
            font-size: 0.9rem;
            display: flex;
            align-items: center;
            gap: var(--spacing-xs);
            transition: var(--transition);
            border: 1px solid rgba(255,255,255,0.1);
        }

        .payment-method:hover {
            background: rgba(255,255,255,0.2);
            transform: translateY(-2px);
        }

        .footer-bottom {
            border-top: 1px solid rgba(255,255,255,0.1);
            padding: var(--spacing-xl) 0;
            text-align: center;
            color: rgba(255,255,255,0.8);
            font-size: 0.95rem;
            position: relative;
            z-index: 2;
        }

        .footer-bottom p {
            margin: 0;
        }

        /*  Chatbot */
        .chatbot-trigger {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 70px;
            height: 70px;
            background: var(--gradient-primary);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-size: 1.8rem;
            cursor: pointer;
            box-shadow: var(--shadow-lg);
            z-index: 998;
            transition: var(--transition);
            animation: chatbot-pulse 3s infinite;
            border: 3px solid var(--white);
        }

        .chatbot-trigger:hover {
            transform: scale(1.1);
            box-shadow: var(--shadow-xl);
        }

        @keyframes chatbot-pulse {
            0%, 100% {
                box-shadow: var(--shadow-lg), 0 0 0 0 rgba(74, 109, 229, 0.4);
            }
            50% {
                box-shadow: var(--shadow-lg), 0 0 0 20px rgba(74, 109, 229, 0);
            }
        }

        .chatbot-container {
            position: fixed;
            bottom: 120px;
            right: 30px;
            width: 380px;
            height: 550px;
            background: var(--white);
            border-radius: var(--radius-2xl);
            box-shadow: var(--shadow-xl);
            z-index: 999;
            transform: translateY(20px) scale(0.95);
            opacity: 0;
            visibility: hidden;
            transition: var(--transition-slow);
            display: flex;
            flex-direction: column;
            border: 1px solid var(--border);
        }

        .chatbot-container.active {
            transform: translateY(0) scale(1);
            opacity: 1;
            visibility: visible;
        }

        .chatbot-header {
            background: var(--gradient-primary);
            color: var(--white);
            padding: var(--spacing-lg);
            border-top-left-radius: var(--radius-2xl);
            border-top-right-radius: var(--radius-2xl);
            display: flex;
            align-items: center;
            justify-content: space-between;
            position: relative;
            overflow: hidden;
        }

        .chatbot-header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, transparent 30%, rgba(255,255,255,0.1) 50%, transparent 70%);
            animation: header-shine 4s linear infinite;
        }

        @keyframes header-shine {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        .chatbot-header h3 {
            font-size: 1.2rem;
            font-weight: 600;
            margin: 0;
            position: relative;
            z-index: 2;
        }

        .chatbot-close {
            background: none;
            border: none;
            color: var(--white);
            font-size: 1.5rem;
            cursor: pointer;
            transition: var(--transition);
            position: relative;
            z-index: 2;
            width: 35px;
            height: 35px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .chatbot-close:hover {
            background: rgba(255,255,255,0.2);
            transform: rotate(90deg);
        }

        .chatbot-messages {
            flex: 1;
            padding: var(--spacing-lg);
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            gap: var(--spacing-md);
            background: #fafafa;
        }

        .chatbot-messages::-webkit-scrollbar {
            width: 6px;
        }

        .chatbot-messages::-webkit-scrollbar-thumb {
            background: var(--primary);
            border-radius: var(--radius-sm);
        }

        .message {
            max-width: 80%;
            padding: 12px 16px;
            border-radius: var(--radius-lg);
            font-size: 0.9rem;
            line-height: 1.5;
            position: relative;
            animation: message-appear 0.3s ease;
        }

        @keyframes message-appear {
            from {
                opacity: 0;
                transform: translateY(10px) scale(0.95);
            }
            to {
                opacity: 1;
                transform: translateY(0) scale(1);
            }
        }

        .bot-message {
            background: var(--white);
            color: var(--dark);
            border-bottom-left-radius: var(--radius-sm);
            align-self: flex-start;
            box-shadow: var(--shadow);
        }

        .user-message {
            background: var(--primary);
            color: var(--white);
            border-bottom-right-radius: var(--radius-sm);
            align-self: flex-end;
        }

        .chatbot-input {
            display: flex;
            padding: var(--spacing-lg);
            border-top: 1px solid var(--border);
            gap: var(--spacing-md);
            background: var(--white);
            border-bottom-left-radius: var(--radius-2xl);
            border-bottom-right-radius: var(--radius-2xl);
        }

        .chatbot-input input {
            flex: 1;
            padding: 14px 20px;
            border: 1px solid var(--border);
            border-radius: var(--radius-full);
            outline: none;
            font-size: 0.95rem;
            transition: var(--transition);
        }

        .chatbot-input input:focus {
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(74, 109, 229, 0.2);
        }

        .chatbot-input button {
            background: var(--primary);
            color: var(--white);
            border: none;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .chatbot-input button:hover {
            background: var(--primary-dark);
            transform: scale(1.05);
        }

        /* Review Section */
        .reviews-section {
            background: var(--white);
        }

        .review-form {
            background: var(--light);
            padding: var(--spacing-2xl);
            border-radius: var(--radius-xl);
            margin-bottom: var(--spacing-3xl);
            box-shadow: var(--shadow);
            position: relative;
            overflow: hidden;
        }

        .review-form::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: var(--gradient-primary);
        }

        .review-form h3 {
            font-size: 1.5rem;
            margin-bottom: var(--spacing-lg);
            color: var(--dark);
            font-weight: 600;
        }

        .form-floating {
            position: relative;
        }

        .form-floating input,
        .form-floating textarea {
            border-radius: var(--radius-md);
            border: 2px solid var(--border);
            transition: var(--transition);
        }

        .form-floating input:focus,
        .form-floating textarea:focus {
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(74, 109, 229, 0.2);
        }

        .rating-input {
            display: flex;
            align-items: center;
            gap: var(--spacing-md);
            margin-bottom: var(--spacing-lg);
        }

        .star-rating {
            display: flex;
            gap: var(--spacing-xs);
        }

        .star-rating i {
            font-size: 1.8rem;
            color: var(--border);
            cursor: pointer;
            transition: var(--transition);
        }

        .star-rating i:hover,
        .star-rating i.active {
            color: var(--warning);
            transform: scale(1.2);
        }

        .review-item {
            background: var(--light);
            padding: var(--spacing-xl);
            border-radius: var(--radius-xl);
            margin-bottom: var(--spacing-xl);
            box-shadow: var(--shadow);
            transition: var(--transition);
            transform: translateY(30px);
            opacity: 0;
        }

        .review-item.visible {
            transform: translateY(0);
            opacity: 1;
        }

        .review-item:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-lg);
        }

        .review-header {
            display: flex;
            align-items: center;
            margin-bottom: var(--spacing-md);
        }

        .reviewer-avatar {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: var(--gradient-primary);
            color: var(--white);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            font-weight: 700;
            margin-right: var(--spacing-md);
            box-shadow: var(--shadow);
        }

        .reviewer-info h4 {
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: var(--spacing-xs);
            color: var(--dark);
        }

        .review-date {
            color: var(--gray);
            font-size: 0.85rem;
        }

        .review-rating {
            color: var(--warning);
            margin-bottom: var(--spacing-md);
            display: flex;
            gap: 2px;
        }

        .review-text {
            color: var(--dark);
            line-height: 1.6;
            margin-bottom: var(--spacing-md);
        }

        .review-actions {
            display: flex;
            gap: var(--spacing-lg);
        }

        .review-action {
            color: var(--gray);
            font-size: 0.9rem;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: var(--spacing-xs);
            padding: var(--spacing-xs) var(--spacing-sm);
            border-radius: var(--radius-sm);
        }

        .review-action:hover {
            color: var(--primary);
            background: rgba(74, 109, 229, 0.1);
        }

        /* Notification System */
        .notification {
            position: fixed;
            bottom: 100px;
            right: 30px;
            background: var(--white);
            color: var(--dark);
            padding: var(--spacing-md) var(--spacing-lg);
            border-radius: var(--radius-lg);
            box-shadow: var(--shadow-xl);
            z-index: 1001;
            transform: translateX(100%);
            transition: var(--transition);
            border-left: 4px solid var(--primary);
            display: flex;
            align-items: center;
            gap: var(--spacing-md);
            min-width: 300px;
        }

        .notification.show {
            transform: translateX(0);
        }

        .notification.success {
            border-left-color: var(--success);
        }

        .notification.warning {
            border-left-color: var(--warning);
        }

        .notification.error {
            border-left-color: var(--danger);
        }

        .notification-icon {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
        }

        .notification.success .notification-icon {
            background: var(--success);
            color: var(--white);
        }

        .notification.warning .notification-icon {
            background: var(--warning);
            color: var(--white);
        }

        .notification.error .notification-icon {
            background: var(--danger);
            color: var(--white);
        }

        /* Advanced Animations */
        .fade-in-up {
            animation: fadeInUp 0.8s ease forwards;
        }

        .fade-in-left {
            animation: fadeInLeft 0.8s ease forwards;
        }

        .fade-in-right {
            animation: fadeInRight 0.8s ease forwards;
        }

        @keyframes fadeInLeft {
            from {
                opacity: 0;
                transform: translateX(-30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes fadeInRight {
            from {
                opacity: 0;
                transform: translateX(30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .scale-in {
            animation: scaleIn 0.5s ease forwards;
        }

        @keyframes scaleIn {
            from {
                opacity: 0;
                transform: scale(0.8);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        /* Parallax Effects */
        .parallax-element {
            transition: transform 0.1s ease-out;
        }

        /* Hover Effects */
        .hover-lift {
            transition: var(--transition);
        }

        .hover-lift:hover {
            transform: translateY(-10px);
        }

        .hover-scale {
            transition: var(--transition);
        }

        .hover-scale:hover {
            transform: scale(1.05);
        }

        .hover-glow {
            transition: var(--transition);
        }

        .hover-glow:hover {
            box-shadow: 0 0 30px rgba(74, 109, 229, 0.3);
        }

        /* Mobile Optimizations */
        @media (max-width: 1199.98px) {
            .hero h1 {
                font-size: clamp(2.2rem, 6vw, 4rem);
            }
            
            .offer-card {
                min-width: 350px;
            }
            
            .chatbot-container {
                width: 350px;
            }
        }

        @media (max-width: 991.98px) {
            .header-content {
                flex-direction: column;
                gap: var(--spacing-md);
            }
            
            .search-bar {
                order: 3;
                width: 100%;
                max-width: 100%;
            }
            
            .header-actions {
                order: 2;
            }
            
            .navbar-nav {
                text-align: center;
                width: 100%;
            }
            
            .hero {
                padding: 80px 0;
            }
            
            .hero-actions {
                flex-direction: column;
                align-items: center;
            }
            
            .offer-card {
                flex-direction: column;
                min-width: 300px;
            }
            
            .offer-image,
            .offer-content {
                width: 100%;
            }
            
            .offer-image {
                height: 200px;
            }
        }

        @media (max-width: 767.98px) {
            :root {
                --spacing-3xl: 3rem;
                --spacing-2xl: 2rem;
            }
            
            .header-top-content {
                flex-direction: column;
                gap: var(--spacing-sm);
                text-align: center;
            }
            
            .contact-info {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .contact-info a {
                margin-right: var(--spacing-sm);
            }
            
            .hero {
                padding: 60px 0;
                text-align: center;
            }
            
            .hero-actions {
                flex-direction: column;
                width: 100%;
            }
            
            .hero-actions .btn {
                width: 100%;
                max-width: 280px;
            }
            
            .newsletter-form {
                flex-direction: column;
            }
            
            .newsletter-form input,
            .newsletter-form button {
                width: 100%;
                border-radius: var(--radius-md);
            }
            
            .section {
                padding: var(--spacing-2xl) 0;
            }
            
            .section-title {
                font-size: 2.2rem;
                margin-bottom: var(--spacing-2xl);
            }
            
            .chatbot-container {
                width: calc(100% - 40px);
                right: 20px;
                left: 20px;
                height: 70vh;
                max-height: 500px;
            }
            
            .chatbot-trigger {
                bottom: 20px;
                right: 20px;
            }
            
            .products-filter {
                overflow-x: auto;
                justify-content: flex-start;
                padding-bottom: var(--spacing-sm);
                scroll-snap-type: x mandatory;
            }
            
            .filter-btn {
                flex-shrink: 0;
                scroll-snap-align: start;
            }
        }

        @media (max-width: 575.98px) {
            .logo-text h1 {
                font-size: 1.8rem;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero-subtitle {
                font-size: 1rem;
            }
            
            .offer-slider {
                padding-left: var(--spacing-lg);
                padding-right: var(--spacing-lg);
            }
            
            .offer-card {
                min-width: 280px;
            }
            
            .newsletter-title {
                font-size: 2rem;
            }
            
            .newsletter-subtitle {
                font-size: 1rem;
            }
        }

        /* Print Styles */
        @media print {
            .header-top,
            .main-navigation,
            .chatbot-trigger,
            .chatbot-container,
            .particles {
                display: none !important;
            }
            
            .section {
                padding: var(--spacing-lg) 0;
            }
            
            .hero {
                background: var(--light) !important;
                color: var(--dark) !important;
            }
        }

        /* Accessibility Improvements */
        @media (prefers-reduced-motion: reduce) {
            *,
            *::before,
            *::after {
                animation-duration: 0.01ms !important;
                animation-iteration-count: 1 !important;
                transition-duration: 0.01ms !important;
            }
        }

        .sr-only {
            position: absolute;
            width: 1px;
            height: 1px;
            padding: 0;
            margin: -1px;
            overflow: hidden;
            clip: rect(0, 0, 0, 0);
            white-space: nowrap;
            border: 0;
        }

        /* Focus Styles for Better Accessibility */
        .btn:focus,
        .nav-link:focus,
        .dropdown-item:focus,
        input:focus,
        textarea:focus,
        button:focus {
            outline: 2px solid var(--primary);
            outline-offset: 2px;
        }

        /* Custom Utilities */
        .text-gradient {
            background: var(--gradient-primary);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .bg-gradient {
            background: var(--gradient-primary);
        }

        .bg-glass {
            background: var(--glass);
            backdrop-filter: blur(10px);
        }

        .border-gradient {
            border: 2px solid;
            border-image: var(--gradient-primary) 1;
        }

        /* Loading States */
        .loading {
            position: relative;
            overflow: hidden;
        }

        .loading::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.4), transparent);
            animation: loading-shimmer 1.5s infinite;
        }

        @keyframes loading-shimmer {
            0% { left: -100%; }
            100% { left: 100%; }
        }

        /* Error States */
        .error-message {
            background: rgba(220, 53, 69, 0.1);
            color: var(--danger);
            padding: var(--spacing-md);
            border-radius: var(--radius-md);
            border: 1px solid rgba(220, 53, 69, 0.3);
            font-size: 0.9rem;
            margin-top: var(--spacing-sm);
        }

        /* Success States */
        .success-message {
            background: rgba(40, 167, 69, 0.1);
            color: var(--success);
            padding: var(--spacing-md);
            border-radius: var(--radius-md);
            border: 1px solid rgba(40, 167, 69, 0.3);
            font-size: 0.9rem;
            margin-top: var(--spacing-sm);
        }

        /* Advanced Grid Layouts */
        .grid-auto {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: var(--spacing-xl);
        }

        .grid-2 {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: var(--spacing-xl);
        }

        .grid-3 {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: var(--spacing-xl);
        }

        .grid-4 {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: var(--spacing-xl);
        }

        @media (max-width: 991.98px) {
            .grid-4 {
                grid-template-columns: repeat(2, 1fr);
            }
            .grid-3 {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 575.98px) {
            .grid-4,
            .grid-3,
            .grid-2 {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Loading Screen -->
    <div class="loading-screen" id="loadingScreen">
        <div class="loading-logo">
            <i class="fas fa-shopping-bag"></i>
        </div>
        <div class="loading-text">ShopSphere</div>
        <div class="loading-subtitle">Premium Shopping Experience</div>
        <div class="loading-progress">
            <div class="loading-progress-bar"></div>
        </div>
    </div>

    <!-- Floating Particles -->
    <div class="particles" id="particles"></div>

    <!-- Header -->
    <header>
<!--         <!-- Header Top Bar 
        <div class="header-top">
            <div class="container">
                <div class="header-top-content">
                    <div class="contact-info">
                        <a href="tel:+1234567890">
                            <i class="fas fa-phone"></i>
                            +1 (234) 567-8900
                        </a>
                        <a href="mailto:support@shopsphere.com">
                            <i class="fas fa-envelope"></i>
                            support@shopsphere.com
                        </a>
                        <span>
                            <i class="fas fa-truck"></i>
                            Free shipping on orders over $50
                        </span>
                    </div>
                    <div class="social-icons">
                        <a href="#" aria-label="Facebook"><i class="fab fa-facebook-f"></i></a>
                        <a href="#" aria-label="Twitter"><i class="fab fa-twitter"></i></a>
                        <a href="#" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
                        <a href="#" aria-label="Pinterest"><i class="fab fa-pinterest"></i></a>
                        <a href="#" aria-label="YouTube"><i class="fab fa-youtube"></i></a>
                    </div>
                </div>
            </div>
        </div>
 -->
        <!-- Main Header -->
        <div class="main-header">
            <div class="container">
                <div class="header-content">
                    <a href="#" class="logo">
                        <div class="logo-icon">
                            <i class="fas fa-shopping-bag"></i>
                        </div>
                        <div class="logo-text">
                            <h1>ShopSphere</h1>
                            <span>Premium Shopping</span>
                        </div>
                    </a>
                    
                    <div class="search-bar">
                        <div class="search-container">
                            <input type="text" placeholder="Search thousands of products..." aria-label="Search products">
                            <button type="button" aria-label="Search">
                                <i class="fas fa-search"></i>
                            </button>
                        </div>
                    </div>
                    
                    <div class="header-actions">
                        <a href="#" class="action-link" title="My Account" aria-label="My Account">
                            <i class="fas fa-user"></i>
                        </a>
                        <a href="#" class="action-link" title="Wishlist" aria-label="Wishlist">
                            <i class="fas fa-heart"></i>
                        </a>
                        <a href="#" class="action-link" title="Shopping Cart" aria-label="Shopping Cart">
                            <i class="fas fa-shopping-cart"></i>
                            <span class="cart-badge">3</span>
                        </a>
                    </div>
                </div>
            </div>
        </div>

        <!-- Main Navigation -->
        <nav class="navbar navbar-expand-lg main-navigation">
            <div class="container">
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#mainNavigation" aria-controls="mainNavigation" aria-expanded="false" aria-label="Toggle navigation">
                    <i class="fas fa-bars text-white"></i>
                </button>
                
                <div class="collapse navbar-collapse justify-content-center" id="mainNavigation">
                    <ul class="navbar-nav">
                        <li class="nav-item">
                            <a class="nav-link" href="#home">
                                <i class="fas fa-home me-2"></i>Home
                            </a>
                        </li>
                        
                        <li class="nav-item dropdown">
                            <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
                                <i class="fas fa-store me-2"></i>Shop
                            </a>
                            <ul class="dropdown-menu">
                                <li><h6 class="dropdown-header">Electronics</h6></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-mobile-alt me-2"></i>Smartphones</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-laptop me-2"></i>Laptops & Computers</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-tv me-2"></i>TVs & Audio</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-camera me-2"></i>Cameras</a></li>
                                <li><hr class="dropdown-divider"></li>
                                <li><h6 class="dropdown-header">Fashion</h6></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-tshirt me-2"></i>Men's Fashion</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-female me-2"></i>Women's Fashion</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-child me-2"></i>Kids & Baby</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-shoe-prints me-2"></i>Shoes & Accessories</a></li>
                                <li><hr class="dropdown-divider"></li>
                                <li><h6 class="dropdown-header">Home & Living</h6></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-couch me-2"></i>Furniture</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-utensils me-2"></i>Kitchen & Dining</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-lightbulb me-2"></i>Home Decor</a></li>
                                <li><hr class="dropdown-divider"></li>
                                <li><h6 class="dropdown-header">Beauty & Health</h6></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-spa me-2"></i>Skincare</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-brush me-2"></i>Makeup</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-dumbbell me-2"></i>Health & Fitness</a></li>
                            </ul>
                        </li>
                        
                        <li class="nav-item dropdown">
                            <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
                                <i class="fas fa-tags me-2"></i>Deals
                            </a>
                            <ul class="dropdown-menu">
                                <li><a class="dropdown-item" href="#"><i class="fas fa-fire me-2"></i>Flash Deals</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-percentage me-2"></i>Daily Deals</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-star me-2"></i>Featured Offers</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-clock me-2"></i>Limited Time</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-gift me-2"></i>Bundle Deals</a></li>
                            </ul>
                        </li>
                        
                        <li class="nav-item dropdown">
                            <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
                                <i class="fas fa-info-circle me-2"></i>About
                            </a>
                            <ul class="dropdown-menu">
                                <li><a class="dropdown-item" href="#"><i class="fas fa-building me-2"></i>Our Company</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-users me-2"></i>Our Team</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-award me-2"></i>Awards & Recognition</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-newspaper me-2"></i>Press & Media</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-briefcase me-2"></i>Careers</a></li>
                            </ul>
                        </li>
                        
                        <li class="nav-item dropdown">
                            <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
                                <i class="fas fa-headset me-2"></i>Support
                            </a>
                            <ul class="dropdown-menu">
                                <li><a class="dropdown-item" href="#contact"><i class="fas fa-phone me-2"></i>Contact Us</a></li>
                                <li><a class="dropdown-item" href="#faq"><i class="fas fa-question-circle me-2"></i>FAQ</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-shipping-fast me-2"></i>Shipping Info</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-undo me-2"></i>Returns & Exchanges</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-search me-2"></i>Track Order</a></li>
                                <li><a class="dropdown-item" href="#"><i class="fas fa-shield-alt me-2"></i>Privacy Policy</a></li>
                            </ul>
                        </li>
                    </ul>
                </div>
            </div>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero section" id="home">
        <div class="container">
            <div class="hero-content">
                <h1>Transform Your Shopping Experience</h1>
                <p class="hero-subtitle">Discover premium products with cutting-edge technology, unbeatable prices, and exceptional customer service</p>
                <div class="hero-actions">
                    <a href="#products" class="btn btn-lg">
                        <i class="fas fa-shopping-bag me-2"></i>Shop Now
                    </a>
                    <a href="#features" class="btn btn-outline btn-lg">
                        <i class="fas fa-play me-2"></i>Watch Demo
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- Categories Section -->
    <section class="categories section">
        <div class="container">
            <h2 class="section-title">Shop by Category</h2>
            <p class="section-subtitle">Explore our vast collection of premium products across multiple categories</p>
            
            <div class="row g-4">
                <div class="col-lg-3 col-md-6">
                    <div class="category-card hover-lift">
                        <div class="category-image">
                            <i class="fas fa-mobile-alt"></i>
                        </div>
                        <div class="category-info">
                            <h3>Electronics</h3>
                            <p>Latest gadgets & technology</p>
                        </div>
                    </div>
                </div>
                
                <div class="col-lg-3 col-md-6">
                    <div class="category-card hover-lift">
                        <div class="category-image">
                            <i class="fas fa-tshirt"></i>
                        </div>
                        <div class="category-info">
                            <h3>Fashion</h3>
                            <p>Trendy styles for everyone</p>
                        </div>
                    </div>
                </div>
                
                <div class="col-lg-3 col-md-6">
                    <div class="category-card hover-lift">
                        <div class="category-image">
                            <i class="fas fa-home"></i>
                        </div>
                        <div class="category-info">
                            <h3>Home & Kitchen</h3>
                            <p>Everything for your home that you need</p>
                        </div>
                    </div>
                </div>
                
                <div class="col-lg-3 col-md-6">
                    <div class="category-card hover-lift">
                        <div class="category-image">
                            <i class="fas fa-spa"></i>
                        </div>
                        <div class="category-info">
                            <h3>Beauty & Health</h3>
                            <p>Premium beauty products</p>
                        </div>
                    </div>
                </div>
                
                <div class="col-lg-3 col-md-6">
                    <div class="category-card hover-lift">
                        <div class="category-image">
                            <i class="fas fa-dumbbell"></i>
                        </div>
                        <div class="category-info">
                            <h3>Sports & Fitness</h3>
                            <p>Gear for active lifestyle and gym</p>
                        </div>
                    </div>
                </div>
                
                <div class="col-lg-3 col-md-6">
                    <div class="category-card hover-lift">
                        <div class="category-image">
                            <i class="fas fa-baby"></i>
                        </div>
                        <div class="category-info">
                            <h3>Baby & Kids</h3>
                            <p>Safe & fun products for kids</p>
                        </div>
                    </div>
                </div>
                
                <div class="col-lg-3 col-md-6">
                    <div class="category-card hover-lift">
                        <div class="category-image">
                            <i class="fas fa-book"></i>
                        </div>
                        <div class="category-info">
                            <h3>Books & Media</h3>
                            <p>Knowledge & entertainment</p>
                        </div>
                    </div>
                </div>
                
                <div class="col-lg-3 col-md-6">
                    <div class="category-card hover-lift">
                        <div class="category-image">
                            <i class="fas fa-car"></i>
                        </div>
                        <div class="category-info">
                            <h3>Automotive</h3>
                            <p>Car accessories & parts available</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Featured Products -->
    <section class="products-section section" id="products">
        <div class="container">
            <h2 class="section-title">Featured Products</h2>
            <p class="section-subtitle">Handpicked products that represent the best in quality, innovation, and value</p>
            
            <div class="products-filter">
                <button class="filter-btn active" data-filter="all">All Products</button>
                <button class="filter-btn" data-filter="electronics">Electronics</button>
                <button class="filter-btn" data-filter="fashion">Fashion</button>
                <button class="filter-btn" data-filter="home">Home & Kitchen</button>
                <button class="filter-btn" data-filter="beauty">Beauty</button>
                <button class="filter-btn" data-filter="sports">Sports</button>
            </div>
            
            <div class="row g-4">
                <!-- Product 1 -->
                <div class="col-xl-3 col-lg-4 col-md-6" data-category="electronics">
                    <div class="product-card hover-lift hover-glow">
                        <div class="product-badge">30% OFF</div>
                        <div class="product-image">
                            <i class="fas fa-laptop" style="color: var(--primary);"></i>
                            <div class="product-actions">
                                <button class="product-action-btn" title="Add to Wishlist" aria-label="Add to Wishlist">
                                    <i class="far fa-heart"></i>
                                </button>
                                <button class="product-action-btn" title="Add to Cart" aria-label="Add to Cart">
                                    <i class="fas fa-shopping-cart"></i>
                                </button>
                                <button class="product-action-btn" title="Quick View" aria-label="Quick View">
                                    <i class="fas fa-eye"></i>
                                </button>
                            </div>
                        </div>
                        <div class="product-info">
                            <div class="product-category">Electronics</div>
                            <h3 class="product-title">MacBook Pro 16" M3 Chip</h3>
                            <p class="product-description">Professional laptop with M3 chip, 32GB RAM, 1TB SSD storage</p>
                            <div class="product-price">
                                <span class="current-price">₹2,299</span>
                                <span class="old-price">₹2,999</span>
                                <span class="discount-badge">30% OFF</span>
                            </div>
                            <div class="product-rating">
                                <div class="rating-stars">
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                </div>
                                <span class="rating-count">(342 reviews)</span>
                            </div>
                            <div class="product-footer">
                                <a href="#" class="btn btn-sm flex-fill">Add to Cart</a>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Product 2 -->
                <div class="col-xl-3 col-lg-4 col-md-6" data-category="fashion">
                    <div class="product-card hover-lift hover-glow">
                        <div class="product-badge">New Arrival</div>
                        <div class="product-image">
                            <i class="fas fa-tshirt" style="color: var(--secondary);"></i>
                            <div class="product-actions">
                                <button class="product-action-btn" title="Add to Wishlist" aria-label="Add to Wishlist">
                                    <i class="far fa-heart"></i>
                                </button>
                                <button class="product-action-btn" title="Add to Cart" aria-label="Add to Cart">
                                    <i class="fas fa-shopping-cart"></i>
                                </button>
                                <button class="product-action-btn" title="Quick View" aria-label="Quick View">
                                    <i class="fas fa-eye"></i>
                                </button>
                            </div>
                        </div>
                        <div class="product-info">
                            <div class="product-category">Fashion</div>
                            <h3 class="product-title">Premium Cotton T-Shirt</h3>
                            <p class="product-description">100% organic cotton, slim fit, available in 8 vibrant colors</p>
                            <div class="product-price">
                                <span class="current-price">₹39.99</span>
                            </div>
                            <div class="product-rating">
                                <div class="rating-stars">
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="far fa-star"></i>
                                </div>
                                <span class="rating-count">(128 reviews)</span>
                            </div>
                            <div class="product-footer">
                                <a href="#" class="btn btn-sm flex-fill">Add to Cart</a>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Product 3 -->
                <div class="col-xl-3 col-lg-4 col-md-6" data-category="home">
                    <div class="product-card hover-lift hover-glow">
                        <div class="product-badge">Best Seller</div>
                        <div class="product-image">
                            <i class="fas fa-blender" style="color: var(--accent);"></i>
                            <div class="product-actions">
                                <button class="product-action-btn" title="Add to Wishlist" aria-label="Add to Wishlist">
                                    <i class="far fa-heart"></i>
                                </button>
                                <button class="product-action-btn" title="Add to Cart" aria-label="Add to Cart">
                                    <i class="fas fa-shopping-cart"></i>
                                </button>
                                <button class="product-action-btn" title="Quick View" aria-label="Quick View">
                                    <i class="fas fa-eye"></i>
                                </button>
                            </div>
                        </div>
                        <div class="product-info">
                            <div class="product-category">Home & Kitchen</div>
                            <h3 class="product-title">Professional Blender Pro</h3>
                            <p class="product-description">2000W motor, 10-speed settings, self-cleaning, BPA-free</p>
                            <div class="product-price">
                                <span class="current-price">₹149.99</span>
                                <span class="old-price">₹199.99</span>
                                <span class="discount-badge">25% OFF</span>
                            </div>
                            <div class="product-rating">
                                <div class="rating-stars">
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                </div>
                                <span class="rating-count">(567 reviews)</span>
                            </div>
                            <div class="product-footer">
                                <a href="#" class="btn btn-sm flex-fill">Add to Cart</a>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Product 4 -->
                <div class="col-xl-3 col-lg-4 col-md-6" data-category="electronics">
                    <div class="product-card hover-lift hover-glow">
                        <div class="product-badge">Featured</div>
                        <div class="product-image">
                            <i class="fas fa-headphones" style="color: var(--dark);"></i>
                            <div class="product-actions">
                                <button class="product-action-btn" title="Add to Wishlist" aria-label="Add to Wishlist">
                                    <i class="far fa-heart"></i>
                                </button>
                                <button class="product-action-btn" title="Add to Cart" aria-label="Add to Cart">
                                    <i class="fas fa-shopping-cart"></i>
                                </button>
                                <button class="product-action-btn" title="Quick View" aria-label="Quick View">
                                    <i class="fas fa-eye"></i>
                                </button>
                            </div>
                        </div>
                        <div class="product-info">
                            <div class="product-category">Electronics</div>
                            <h3 class="product-title">Wireless Noise-Canceling Headphones</h3>
                            <p class="product-description">Premium audio quality with active noise cancellation</p>
                            <div class="product-price">
                                <span class="current-price">₹299.99</span>
                            </div>
                            <div class="product-rating">
                                <div class="rating-stars">
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star-half-alt"></i>
                                </div>
                                <span class="rating-count">(234 reviews)</span>
                            </div>
                            <div class="product-footer">
                                <a href="#" class="btn btn-sm flex-fill">Add to Cart</a>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Product 5 -->
                <div class="col-xl-3 col-lg-4 col-md-6" data-category="beauty">
                    <div class="product-card hover-lift hover-glow">
                        <div class="product-badge">Limited Edition</div>
                        <div class="product-image">
                            <i class="fas fa-heart" style="color: #e83e8c;"></i>
                            <div class="product-actions">
                                <button class="product-action-btn" title="Add to Wishlist" aria-label="Add to Wishlist">
                                    <i class="far fa-heart"></i>
                                </button>
                                <button class="product-action-btn" title="Add to Cart" aria-label="Add to Cart">
                                    <i class="fas fa-shopping-cart"></i>
                                </button>
                                <button class="product-action-btn" title="Quick View" aria-label="Quick View">
                                    <i class="fas fa-eye"></i>
                                </button>
                            </div>
                        </div>
                        <div class="product-info">
                            <div class="product-category">Beauty</div>
                            <h3 class="product-title">Luxury Skincare Collection</h3>
                            <p class="product-description">Complete 7-step skincare routine with natural ingredients</p>
                            <div class="product-price">
                                <span class="current-price">₹189.99</span>
                                <span class="old-price">₹249.99</span>
                                <span class="discount-badge">24% OFF</span>
                            </div>
                            <div class="product-rating">
                                <div class="rating-stars">
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                </div>
                                <span class="rating-count">(89 reviews)</span>
                            </div>
                            <div class="product-footer">
                                <a href="#" class="btn btn-sm flex-fill">Add to Cart</a>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Product 6 -->
                <div class="col-xl-3 col-lg-4 col-md-6" data-category="sports">
                    <div class="product-card hover-lift hover-glow">
                        <div class="product-image">
                            <i class="fas fa-running" style="color: var(--info);"></i>
                            <div class="product-actions">
                                <button class="product-action-btn" title="Add to Wishlist" aria-label="Add to Wishlist">
                                    <i class="far fa-heart"></i>
                                </button>
                                <button class="product-action-btn" title="Add to Cart" aria-label="Add to Cart">
                                    <i class="fas fa-shopping-cart"></i>
                                </button>
                                <button class="product-action-btn" title="Quick View" aria-label="Quick View">
                                    <i class="fas fa-eye"></i>
                                </button>
                            </div>
                        </div>
                        <div class="product-info">
                            <div class="product-category">Sports</div>
                            <h3 class="product-title">Professional Running Shoes</h3>
                            <p class="product-description">Advanced cushioning technology for professional athletes</p>
                            <div class="product-price">
                                <span class="current-price">$159.99</span>
                            </div>
                            <div class="product-rating">
                                <div class="rating-stars">
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="far fa-star"></i>
                                </div>
                                <span class="rating-count">(176 reviews)</span>
                            </div>
                            <div class="product-footer">
                                <a href="#" class="btn btn-sm flex-fill">Add to Cart</a>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Product 7 -->
                <div class="col-xl-3 col-lg-4 col-md-6" data-category="fashion">
                    <div class="product-card hover-lift hover-glow">
                        <div class="product-badge">Trending</div>
                        <div class="product-image">
                            <i class="fas fa-gem" style="color: #6f42c1;"></i>
                            <div class="product-actions">
                                <button class="product-action-btn" title="Add to Wishlist" aria-label="Add to Wishlist">
                                    <i class="far fa-heart"></i>
                                </button>
                                <button class="product-action-btn" title="Add to Cart" aria-label="Add to Cart">
                                    <i class="fas fa-shopping-cart"></i>
                                </button>
                                <button class="product-action-btn" title="Quick View" aria-label="Quick View">
                                    <i class="fas fa-eye"></i>
                                </button>
                            </div>
                        </div>
                        <div class="product-info">
                            <div class="product-category">Fashion</div>
                            <h3 class="product-title">Diamond Tennis Bracelet</h3>
                            <p class="product-description">18K white gold with genuine diamonds, certified authentic</p>
                            <div class="product-price">
                                <span class="current-price">₹899.99</span>
                                <span class="old-price">₹1,199.99</span>
                                <span class="discount-badge">25% OFF</span>
                            </div>
                            <div class="product-rating">
                                <div class="rating-stars">
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                </div>
                                <span class="rating-count">(67 reviews)</span>
                            </div>
                            <div class="product-footer">
                                <a href="#" class="btn btn-sm flex-fill">Add to Cart</a>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Product 8 -->
                <div class="col-xl-3 col-lg-4 col-md-6" data-category="home">
                    <div class="product-card hover-lift hover-glow">
                        <div class="product-image">
                            <i class="fas fa-couch" style="color: #fd7e14;"></i>
                            <div class="product-actions">
                                <button class="product-action-btn" title="Add to Wishlist" aria-label="Add to Wishlist">
                                    <i class="far fa-heart"></i>
                                </button>
                                <button class="product-action-btn" title="Add to Cart" aria-label="Add to Cart">
                                    <i class="fas fa-shopping-cart"></i>
                                </button>
                                <button class="product-action-btn" title="Quick View" aria-label="Quick View">
                                    <i class="fas fa-eye"></i>
                                </button>
                            </div>
                        </div>
                        <div class="product-info">
                            <div class="product-category">Home & Kitchen</div>
                            <h3 class="product-title">Modern Sectional Sofa</h3>
                            <p class="product-description">L-shaped design with premium fabric and memory foam cushions</p>
                            <div class="product-price">
                                <span class="current-price">₹1,299.99</span>
                            </div>
                            <div class="product-rating">
                                <div class="rating-stars">
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="far fa-star"></i>
                                </div>
                                <span class="rating-count">(94 reviews)</span>
                            </div>
                            <div class="product-footer">
                                <a href="#" class="btn btn-sm flex-fill">Add to Cart</a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Special Offers -->
    <section class="offers-section section">
        <div class="container">
            <h2 class="section-title">Limited Time Offers</h2>
            <p class="section-subtitle">Exclusive deals that won't last long - grab them while you can!</p>
            
            <div class="offer-slider">
                <!-- Offer 1 -->
                <div class="offer-card hover-scale">
                    <div class="offer-image">
                        <i class="fas fa-tv"></i>
                    </div>
                    <div class="offer-content">
                        <div class="offer-tag">Flash Sale</div>
                        <h3 class="offer-title">65" 4K Smart TV</h3>
                        <p class="offer-description">Ultra HD resolution with HDR support and smart streaming capabilities</p>
                        <div class="countdown-timer">
                            <div class="timer-unit">
                                <div class="timer-value" data-timer="days">02</div>
                                <div class="timer-label">Days</div>
                            </div>
                            <div class="timer-unit">
                                <div class="timer-value" data-timer="hours">14</div>
                                <div class="timer-label">Hours</div>
                            </div>
                            <div class="timer-unit">
                                <div class="timer-value" data-timer="minutes">32</div>
                                <div class="timer-label">Min</div>
                            </div>
                            <div class="timer-unit">
                                <div class="timer-value" data-timer="seconds">45</div>
                                <div class="timer-label">Sec</div>
                            </div>
                        </div>
                        <a href="#" class="btn btn-secondary">Grab Deal - $699.99</a>
                    </div>
                </div>

                <!-- Offer 2 -->
                <div class="offer-card hover-scale">
                    <div class="offer-image">
                        <i class="fas fa-tshirt"></i>
                    </div>
                    <div class="offer-content">
                        <div class="offer-tag">Summer Sale</div>
                        <h3 class="offer-title">Fashion Bundle Deal</h3>
                        <p class="offer-description">Complete summer wardrobe with designer pieces at incredible prices</p>
                        <div class="countdown-timer">
                            <div class="timer-unit">
                                <div class="timer-value" data-timer="days">07</div>
                                <div class="timer-label">Days</div>
                            </div>
                            <div class="timer-unit">
                                <div class="timer-value" data-timer="hours">09</div>
                                <div class="timer-label">Hours</div>
                            </div>
                            <div class="timer-unit">
                                <div class="timer-value" data-timer="minutes">18</div>
                                <div class="timer-label">Min</div>
                            </div>
                            <div class="timer-unit">
                                <div class="timer-value" data-timer="seconds">27</div>
                                <div class="timer-label">Sec</div>
                            </div>
                        </div>
                        <a href="#" class="btn btn-secondary">Shop Bundle - $199.99</a>
                    </div>
                </div>

                <!-- Offer 3 -->
                <div class="offer-card hover-scale">
                    <div class="offer-image">
                        <i class="fas fa-laptop"></i>
                    </div>
                    <div class="offer-content">
                        <div class="offer-tag">Tech Week</div>
                        <h3 class="offer-title">Gaming Laptop Setup</h3>
                        <p class="offer-description">High-performance gaming laptop with accessories and warranty</p>
                        <div class="countdown-timer">
                            <div class="timer-unit">
                                <div class="timer-value" data-timer="days">03</div>
                                <div class="timer-label">Days</div>
                            </div>
                            <div class="timer-unit">
                                <div class="timer-value" data-timer="hours">21</div>
                                <div class="timer-label">Hours</div>
                            </div>
                            <div class="timer-unit">
                                <div class="timer-value" data-timer="minutes">44</div>
                                <div class="timer-label">Min</div>
                            </div>
                            <div class="timer-unit">
                                <div class="timer-value" data-timer="seconds">12</div>
                                <div class="timer-label">Sec</div>
                            </div>
                        </div>
                        <a href="#" class="btn btn-secondary">Complete Setup - $1,499.99</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features-section section" id="features">
        <div class="container">
            <h2 class="section-title">Why Choose ShopSphere?</h2>
            <p class="section-subtitle">Experience the future of online shopping with our innovative features and services</p>
            
            <div class="row g-4">
                <div class="col-lg-4 col-md-6">
                    <div class="feature-card">
                        <div class="feature-icon">
                            <i class="fas fa-shipping-fast"></i>
                        </div>
                        <h3 class="feature-title">Lightning Fast Delivery</h3>
                        <p class="feature-description">Get your orders delivered in 24 hours with our premium shipping network across the country</p>
                    </div>
                </div>
                
                <div class="col-lg-4 col-md-6">
                    <div class="feature-card">
                        <div class="feature-icon">
                            <i class="fas fa-shield-alt"></i>
                        </div>
                        <h3 class="feature-title">Secure Shopping</h3>
                        <p class="feature-description">256-bit SSL encryption and fraud protection ensure your personal and payment information is always safe</p>
                    </div>
                </div>
                
                <div class="col-lg-4 col-md-6">
                    <div class="feature-card">
                        <div class="feature-icon">
                            <i class="fas fa-headset"></i>
                        </div>
                        <h3 class="feature-title">24/7 Customer Support</h3>
                        <p class="feature-description">Our dedicated support team is available round the clock to help you with any questions or concerns</p>
                    </div>
                </div>
                
                <div class="col-lg-4 col-md-6">
                    <div class="feature-card">
                        <div class="feature-icon">
                            <i class="fas fa-undo-alt"></i>
                        </div>
                        <h3 class="feature-title">Easy Returns</h3>
                        <p class="feature-description">30-day hassle-free return policy with free return shipping for all eligible items</p>
                    </div>
                </div>
                
                <div class="col-lg-4 col-md-6">
                    <div class="feature-card">
                        <div class="feature-icon">
                            <i class="fas fa-star"></i>
                        </div>
                        <h3 class="feature-title">Premium Quality</h3>
                        <p class="feature-description">All products are carefully curated and quality-tested to meet our high standards</p>
                    </div>
                </div>
                
                <div class="col-lg-4 col-md-6">
                    <div class="feature-card">
                        <div class="feature-icon">
                            <i class="fas fa-mobile-alt"></i>
                        </div>
                        <h3 class="feature-title">AR Try-On Technology</h3>
                        <p class="feature-description">Revolutionary augmented reality features let you try products virtually before purchasing</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Brands Section -->
    <section class="brands-section">
        <div class="container">
            <h2 class="section-title">Trusted by Leading Brands</h2>
            <p class="section-subtitle">We partner with the world's most respected brands to bring you authentic, high-quality products</p>
            
            <div class="brands-grid">
                <div class="brand-item hover-lift">
                    <i class="fab fa-apple"></i>
                </div>
                <div class="brand-item hover-lift">
                    <i class="fab fa-microsoft"></i>
                </div>
                <div class="brand-item hover-lift">
                    <i class="fab fa-google"></i>
                </div>
                <div class="brand-item hover-lift">
                    <i class="fab fa-amazon"></i>
                </div>
                <div class="brand-item hover-lift">
                    <i class="fab fa-samsung"></i>
                </div>
                <div class="brand-item hover-lift">
                    <i class="fab fa-nike"></i>
                </div>
                <div class="brand-item hover-lift">
                    <i class="fab fa-adidas"></i>
                </div>
                <div class="brand-item hover-lift">
                    <i class="fab fa-sony"></i>
                </div>
            </div>
        </div>
    </section>

    <!-- Customer Reviews -->
    <section class="reviews-section section">
        <div class="container">
            <h2 class="section-title">Customer Reviews</h2>
            <p class="section-subtitle">Real feedback from our satisfied customers worldwide</p>
            
            <div class="row">
                <div class="col-lg-8 mx-auto">
                    <!-- Review Form -->
                    <div class="review-form">
                        <h3>Share Your Experience</h3>
                        <form id="reviewForm">
                            <div class="row g-3">
                                <div class="col-md-6">
                                    <div class="form-floating">
                                        <input type="text" class="form-control" id="reviewerName" placeholder="Your Name" required>
                                        <label for="reviewerName">Your Name</label>
                                    </div>
                                </div>
                                <div class="col-md-6">
                                    <div class="form-floating">
                                        <input type="email" class="form-control" id="reviewerEmail" placeholder="Your Email" required>
                                        <label for="reviewerEmail">Your Email</label>
                                    </div>
                                </div>
                            </div>
                            
                            <div class="rating-input">
                                <span>Your Rating:</span>
                                <div class="star-rating" id="starRating">
                                    <i class="far fa-star" data-rating="1"></i>
                                    <i class="far fa-star" data-rating="2"></i>
                                    <i class="far fa-star" data-rating="3"></i>
                                    <i class="far fa-star" data-rating="4"></i>
                                    <i class="far fa-star" data-rating="5"></i>
                                </div>
                                <input type="hidden" id="ratingValue" value="0">
                            </div>
                            
                            <div class="form-floating mb-3">
                                <textarea class="form-control" id="reviewText" placeholder="Share your experience..." style="height: 120px" required></textarea>
                                <label for="reviewText">Your Review</label>
                            </div>
                            
                            <button type="submit" class="btn btn-lg">
                                <i class="fas fa-paper-plane me-2"></i>Submit Review
                            </button>
                        </form>
                    </div>

                    <!-- Existing Reviews -->
                    <div class="reviews-list" id="reviewsList">
                        <div class="review-item">
                            <div class="review-header">
                                <div class="reviewer-avatar">JD</div>
                                <div class="reviewer-info">
                                    <h4>John Davidson</h4>
                                    <div class="review-date">December 15, 2024</div>
                                </div>
                            </div>
                            <div class="review-rating">
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                            </div>
                            <div class="review-text">
                                <p>Absolutely exceptional service! The MacBook Pro I ordered arrived ahead of schedule and was exactly as described. The packaging was premium quality and the product was in perfect condition. ShopSphere has definitely earned my trust and loyalty.</p>
                            </div>
                            <div class="review-actions">
                                <div class="review-action">
                                    <i class="far fa-thumbs-up"></i>
                                    <span>Helpful (47)</span>
                                </div>
                                <div class="review-action">
                                    <i class="far fa-comment"></i>
                                    <span>Reply</span>
                                </div>
                                <div class="review-action">
                                    <i class="far fa-share-square"></i>
                                    <span>Share</span>
                                </div>
                            </div>
                        </div>

                        <div class="review-item">
                            <div class="review-header">
                                <div class="reviewer-avatar">SM</div>
                                <div class="reviewer-info">
                                    <h4>Sarah Martinez</h4>
                                    <div class="review-date">December 10, 2024</div>
                                </div>
                            </div>
                            <div class="review-rating">
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="far fa-star"></i>
                            </div>
                            <div class="review-text">
                                <p>Great variety of products and competitive pricing. The AR try-on feature for glasses was incredibly accurate and saved me from making a wrong purchase. Only wish the shipping was a bit faster, but overall very satisfied with my experience.</p>
                            </div>
                            <div class="review-actions">
                                <div class="review-action">
                                    <i class="far fa-thumbs-up"></i>
                                    <span>Helpful (23)</span>
                                </div>
                                <div class="review-action">
                                    <i class="far fa-comment"></i>
                                    <span>Reply</span>
                                </div>
                                <div class="review-action">
                                    <i class="far fa-share-square"></i>
                                    <span>Share</span>
                                </div>
                            </div>
                        </div>

                        <div class="review-item">
                            <div class="review-header">
                                <div class="reviewer-avatar">RJ</div>
                                <div class="reviewer-info">
                                    <h4>Robert Johnson</h4>
                                    <div class="review-date">December 5, 2024</div>
                                </div>
                            </div>
                            <div class="review-rating">
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                            </div>
                            <div class="review-text">
                                <p>Outstanding customer service and product quality! I had an issue with my order and their support team resolved it within hours. The chatbot is surprisingly helpful and the human agents are knowledgeable and friendly. Highly recommended!</p>
                            </div>
                            <div class="review-actions">
                                <div class="review-action">
                                    <i class="far fa-thumbs-up"></i>
                                    <span>Helpful (89)</span>
                                </div>
                                <div class="review-action">
                                    <i class="far fa-comment"></i>
                                    <span>Reply</span>
                                </div>
                                <div class="review-action">
                                    <i class="far fa-share-square"></i>
                                    <span>Share</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Newsletter -->
    <section class="newsletter-section section">
        <div class="container">
            <div class="newsletter-content">
                <h2 class="newsletter-title">Stay Updated</h2>
                <p class="newsletter-subtitle">Subscribe to our newsletter and be the first to know about exclusive deals, new arrivals, and special events</p>
                
                <form class="newsletter-form" id="newsletterForm">
                    <input type="email" placeholder="Enter your email address" required aria-label="Email address">
                    <button type="submit">
                        <i class="fas fa-paper-plane me-2"></i>Subscribe
                    </button>
                </form>
            </div>
        </div>
    </section>

    <!-- Enhanced Footer -->
    <footer>
        <div class="footer-main">
            <div class="container">
                <div class="row g-5">
                    <div class="col-lg-4 col-md-6">
                        <div class="footer-column">
                            <h3>ShopSphere</h3>
                            <p>Your premier destination for premium shopping experiences. We're committed to providing exceptional products, outstanding service, and innovative technology to enhance your shopping journey.</p>
                            <div class="footer-social">
                                <a href="#" class="social-link" aria-label="Facebook">
                                    <i class="fab fa-facebook-f"></i>
                                </a>
                                <a href="#" class="social-link" aria-label="Twitter">
                                    <i class="fab fa-twitter"></i>
                                </a>
                                <a href="#" class="social-link" aria-label="Instagram">
                                    <i class="fab fa-instagram"></i>
                                </a>
                                <a href="#" class="social-link" aria-label="LinkedIn">
                                    <i class="fab fa-linkedin-in"></i>
                                </a>
                                <a href="#" class="social-link" aria-label="YouTube">
                                    <i class="fab fa-youtube"></i>
                                </a>
                            </div>
                        </div>
                    </div>
                    
                    <div class="col-lg-2 col-md-6">
                        <div class="footer-column">
                            <h3>Shop</h3>
                            <ul class="footer-links">
                                <li><a href="#">Electronics</a></li>
                                <li><a href="#">Fashion</a></li>
                                <li><a href="#">Home & Kitchen</a></li>
                                <li><a href="#">Beauty & Health</a></li>
                                <li><a href="#">Sports & Fitness</a></li>
                                <li><a href="#">Books & Media</a></li>
                            </ul>
                        </div>
                    </div>
                    <section="faq">
                    <div class="col-lg-2 col-md-6">
                        <div class="footer-column">
                            <h3>Customer Care</h3>
                            <ul class="footer-links">
                                <li><a href="#">Contact Support</a></li>
                                <li><a href="#">FAQ & Help</a></li>
                                <li><a href="#">Order Tracking</a></li>
                                <li><a href="#">Shipping Policy</a></li>
                                <li><a href="#">Returns & Refunds</a></li>
                                <li><a href="#">Size Guide</a></li>
                            </ul>
                        </div>
                    </div>
                    </section>
                    <div class="col-lg-2 col-md-6">
                        <div class="footer-column">
                            <h3>Company</h3>
                            <ul class="footer-links">
                                <li><a href="#">About Us</a></li>
                                <li><a href="#">Careers</a></li>
                                <li><a href="#">Press & Media</a></li>
                                <li><a href="#">Investor Relations</a></li>
                                <li><a href="#">Sustainability</a></li>
                                <li><a href="#">Terms of Service</a></li>
                            </ul>
                        </div>
                    </div>
                    <section="contact">
                    <div class="col-lg-2 col-md-6">
                        <div class="footer-column">
                            <h3>Contact Info</h3>
                            <div class="contact-info">
                                <i class="fas fa-map-marker-alt"></i>
                                <span>123 Commerce Plaza<br>New York, NY 10001</span>
                            </div>
                            <div class="contact-info">
                                <i class="fas fa-phone-alt"></i>
                                <span>+1 (234) 567-8900</span>
                            </div>
                            <div class="contact-info">
                                <i class="fas fa-envelope"></i>
                                <span>support@shopsphere.com</span>
                            </div>
                            
                            <h4 style="margin-top: var(--spacing-lg); margin-bottom: var(--spacing-md); font-size: 1.1rem;">We Accept</h4>
                            <div class="payment-methods">
                                <div class="payment-method">
                                    <i class="fab fa-cc-visa"></i>
                                    <span>Visa</span>
                                </div>
                                <div class="payment-method">
                                    <i class="fab fa-cc-mastercard"></i>
                                    <span>MC</span>
                                </div>
                                <div class="payment-method">
                                    <i class="fab fa-cc-paypal"></i>
                                    <span>PayPal</span>
                                </div>
                                <div class="payment-method">
                                    <i class="fab fa-cc-amex"></i>
                                    <span>Amex</span>
                                </div>
                                <div class="payment-method">
                                    <i class="fab fa-apple-pay"></i>
                                    <span>Apple Pay</span>
                                </div>
                                <div class="payment-method">
                                    <i class="fab fa-google-pay"></i>
                                    <span>Google Pay</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
        <div class="footer-bottom">
            <div class="container">
                <p>&copy; 2025 ShopSphere. All rights reserved. Designed with <i class="fas fa-heart" style="color: var(--secondary);"></i> for shoppers worldwide. | Privacy Policy | Terms of Service | Cookie Policy</p>
            </div>
        </div>
    </footer>

    <!-- AI Chatbot -->
    <div class="chatbot-trigger" id="chatbotTrigger" title="Chat with us">
        <i class="fas fa-robot"></i>
    </div>
    
    <div class="chatbot-container" id="chatbotContainer">
        <div class="chatbot-header">
            <h3><i class="fas fa-robot me-2"></i>ShopSphere Assistant</h3>
            <button class="chatbot-close" id="chatbotClose" aria-label="Close chat">
                <i class="fas fa-times"></i>
            </button>
        </div>
        <div class="chatbot-messages" id="chatbotMessages">
            <div class="message bot-message">
                <strong>Welcome to ShopSphere! 👋</strong><br><br>
                I'm your personal shopping assistant. I can help you with:
                <br>• Finding products
                <br>• Checking order status  
                <br>• Product recommendations
                <br>• Store policies
                <br><br>How can I assist you today?
            </div>
        </div>
        <div class="chatbot-input">
            <input type="text" placeholder="Type your message..." id="chatbotInput" aria-label="Chat message">
            <button id="chatbotSend" aria-label="Send message">
                <i class="fas fa-paper-plane"></i>
            </button>
        </div>
    </div>

    <!-- Bootstrap JS -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.7/dist/js/bootstrap.bundle.min.js"></script>

    <script>
        // Enhanced JavaScript with Professional Features
        class ShopSphereApp {
            constructor() {
                this.cart = JSON.parse(localStorage.getItem('cart')) || [];
                this.wishlist = JSON.parse(localStorage.getItem('wishlist')) || [];
                this.currentRating = 0;
                this.chatHistory = [];
                this.init();
            }

            init() {
                this.initLoadingScreen();
                this.initScrollAnimations();
                this.initParticles();
                this.initProductFilters();
                this.initProductActions();
                this.initChatbot();
                this.initReviewSystem();
                this.initNewsletter();
                this.initCountdownTimers();
                this.initParallaxEffects();
                this.initKeyboardNavigation();
                this.updateCartCount();
                this.initIntersectionObserver();
            }

            // Loading Screen Animation
            initLoadingScreen() {
                const loadingScreen = document.getElementById('loadingScreen');
                
                // Fade in for 3 seconds, then fade out for 2 seconds
                setTimeout(() => {
                    loadingScreen.classList.add('fade-out');
                }, 3000);
                
                setTimeout(() => {
                    loadingScreen.style.display = 'none';
                    document.body.style.overflow = 'visible';
                    this.triggerPageAnimations();
                }, 5000);
            }

            // Trigger animations when page loads
            triggerPageAnimations() {
                const animatedElements = document.querySelectorAll('.category-card, .product-card, .feature-card');
                animatedElements.forEach((element, index) => {
                    setTimeout(() => {
                        element.classList.add('fade-in-up');
                    }, index * 100);
                });
            }

            // Enhanced Scroll Animations
            initScrollAnimations() {
                let ticking = false;
                
                const handleScroll = () => {
                    if (!ticking) {
                        requestAnimationFrame(() => {
                            this.updateScrollAnimations();
                            ticking = false;
                        });
                        ticking = true;
                    }
                };
                
                window.addEventListener('scroll', handleScroll, { passive: true });
            }

            updateScrollAnimations() {
                const scrolled = window.pageYOffset;
                const parallaxElements = document.querySelectorAll('.parallax-element');
                
                parallaxElements.forEach(element => {
                    const speed = element.dataset.speed || 0.5;
                    const yPos = -(scrolled * speed);
                    element.style.transform = `translateY(${yPos}px)`;
                });

                // Header background opacity on scroll
                const header = document.querySelector('header');
                if (scrolled > 100) {
                    header.style.background = 'rgba(255, 255, 255, 0.98)';
                    header.style.backdropFilter = 'blur(10px)';
                } else {
                    header.style.background = 'var(--white)';
                    header.style.backdropFilter = 'none';
                }
            }

            // Enhanced Particle System
            initParticles() {
                const particlesContainer = document.getElementById('particles');
                const particleCount = window.innerWidth > 768 ? 50 : 25;
                
                for (let i = 0; i < particleCount; i++) {
                    this.createParticle(particlesContainer);
                }

                // Regenerate particles periodically
                setInterval(() => {
                    if (particlesContainer.children.length < particleCount) {
                        this.createParticle(particlesContainer);
                    }
                }, 2000);
            }

            createParticle(container) {
                const particle = document.createElement('div');
                particle.classList.add('particle');
                
                const size = Math.random() * 8 + 3;
                const opacity = Math.random() * 0.6 + 0.2;
                const duration = Math.random() * 15 + 10;
                const delay = Math.random() * 5;
                
                particle.style.width = `${size}px`;
                particle.style.height = `${size}px`;
                particle.style.left = `${Math.random() * 100}%`;
                particle.style.bottom = '-10px';
                particle.style.opacity = opacity;
                particle.style.animationDuration = `${duration}s`;
                particle.style.animationDelay = `${delay}s`;
                
                container.appendChild(particle);
                
                // Remove particle after animation
                setTimeout(() => {
                    if (particle.parentNode) {
                        particle.parentNode.removeChild(particle);
                    }
                }, (duration + delay) * 1000);
            }

            // Advanced Product Filtering
            initProductFilters() {
                const filterButtons = document.querySelectorAll('.filter-btn');
                const products = document.querySelectorAll('[data-category]');
                
                filterButtons.forEach(button => {
                    button.addEventListener('click', () => {
                        const filter = button.dataset.filter;
                        
                        // Update active button
                        filterButtons.forEach(btn => btn.classList.remove('active'));
                        button.classList.add('active');
                        
                        // Filter products with animation
                        products.forEach((product, index) => {
                            const productCategory = product.dataset.category;
                            const shouldShow = filter === 'all' || productCategory === filter;
                            
                            if (shouldShow) {
                                setTimeout(() => {
                                    product.style.display = 'block';
                                    product.style.animation = 'fadeInUp 0.5s ease forwards';
                                }, index * 50);
                            } else {
                                product.style.animation = 'fadeOut 0.3s ease forwards';
                                setTimeout(() => {
                                    product.style.display = 'none';
                                }, 300);
                            }
                        });
                        
                        this.showNotification(`Showing ${filter === 'all' ? 'all' : filter} products`, 'info');
                    });
                });
            }

            // Enhanced Product Actions
            initProductActions() {
                // Add to cart functionality
                const cartButtons = document.querySelectorAll('.product-action-btn .fa-shopping-cart, .product-footer .btn');
                cartButtons.forEach(button => {
                    button.addEventListener('click', (e) => {
                        e.preventDefault();
                        const productCard = button.closest('.product-card');
                        const productTitle = productCard.querySelector('.product-title').textContent;
                        const productPrice = productCard.querySelector('.current-price').textContent;
                        
                        const product = {
                            id: Date.now(),
                            title: productTitle,
                            price: productPrice,
                            quantity: 1
                        };
                        
                        this.addToCart(product);
                    });
                });

                // Wishlist functionality
                const wishlistButtons = document.querySelectorAll('.product-action-btn .fa-heart');
                wishlistButtons.forEach(button => {
                    button.addEventListener('click', (e) => {
                        e.preventDefault();
                        const productCard = button.closest('.product-card');
                        const productTitle = productCard.querySelector('.product-title').textContent;
                        
                        this.toggleWishlist(button, productTitle);
                    });
                });

                // Quick view functionality
                const quickViewButtons = document.querySelectorAll('.product-action-btn .fa-eye');
                quickViewButtons.forEach(button => {
                    button.addEventListener('click', (e) => {
                        e.preventDefault();
                        const productCard = button.closest('.product-card');
                        const productTitle = productCard.querySelector('.product-title').textContent;
                        this.showQuickView(productTitle);
                    });
                });
            }

            addToCart(product) {
                this.cart.push(product);
                localStorage.setItem('cart', JSON.stringify(this.cart));
                this.updateCartCount();
                this.animateCartIcon();
                this.showNotification(`${product.title} added to cart!`, 'success');
            }

            toggleWishlist(button, productTitle) {
                const isInWishlist = button.classList.contains('fas');
                
                if (isInWishlist) {
                    button.classList.remove('fas');
                    button.classList.add('far');
                    this.wishlist = this.wishlist.filter(item => item !== productTitle);
                    this.showNotification(`${productTitle} removed from wishlist`, 'info');
                } else {
                    button.classList.remove('far');
                    button.classList.add('fas');
                    this.wishlist.push(productTitle);
                    this.showNotification(`${productTitle} added to wishlist!`, 'success');
                }
                
                localStorage.setItem('wishlist', JSON.stringify(this.wishlist));
            }

            updateCartCount() {
                const cartBadge = document.querySelector('.cart-badge');
                if (cartBadge) {
                    cartBadge.textContent = this.cart.length;
                    if (this.cart.length > 0) {
                        cartBadge.style.display = 'flex';
                    } else {
                        cartBadge.style.display = 'none';
                    }
                }
            }

            animateCartIcon() {
                const cartIcon = document.querySelector('.fa-shopping-cart').closest('.action-link');
                cartIcon.style.animation = 'none';
                setTimeout(() => {
                    cartIcon.style.animation = 'pulse 0.5s ease';
                }, 10);
            }

            showQuickView(productTitle) {
                this.showNotification(`Quick view for ${productTitle} - Feature coming soon!`, 'info');
            }

            // Advanced Chatbot System
            initChatbot() {
                const trigger = document.getElementById('chatbotTrigger');
                const container = document.getElementById('chatbotContainer');
                const closeBtn = document.getElementById('chatbotClose');
                const messages = document.getElementById('chatbotMessages');
                const input = document.getElementById('chatbotInput');
                const sendBtn = document.getElementById('chatbotSend');

                if (!trigger) return;

                trigger.addEventListener('click', () => {
                    container.classList.toggle('active');
                    if (container.classList.contains('active')) {
                        input.focus();
                    }
                });

                closeBtn.addEventListener('click', () => {
                    container.classList.remove('active');
                });

                const sendMessage = () => {
                    const message = input.value.trim();
                    if (!message) return;

                    this.addChatMessage(message, 'user');
                    input.value = '';
                    
                    // Simulate typing indicator
                    this.showTypingIndicator();
                    
                    setTimeout(() => {
                        this.removeTypingIndicator();
                        const response = this.generateChatResponse(message);
                        this.addChatMessage(response, 'bot');
                    }, 1500 + Math.random() * 1000);
                };

                sendBtn.addEventListener('click', sendMessage);
                input.addEventListener('keypress', (e) => {
                    if (e.key === 'Enter') {
                        sendMessage();
                    }
                });
            }

            addChatMessage(message, type) {
                const messagesContainer = document.getElementById('chatbotMessages');
                const messageElement = document.createElement('div');
                messageElement.className = `message ${type}-message`;
                messageElement.innerHTML = message;
                
                messagesContainer.appendChild(messageElement);
                messagesContainer.scrollTop = messagesContainer.scrollHeight;
                
                // Add to chat history
                this.chatHistory.push({ message, type, timestamp: new Date() });
            }

            showTypingIndicator() {
                const messagesContainer = document.getElementById('chatbotMessages');
                const typingElement = document.createElement('div');
                typingElement.className = 'message bot-message typing-indicator';
                typingElement.innerHTML = '<i class="fas fa-ellipsis-h"></i> Assistant is typing...';
                typingElement.style.opacity = '0.7';
                
                messagesContainer.appendChild(typingElement);
                messagesContainer.scrollTop = messagesContainer.scrollHeight;
            }

            removeTypingIndicator() {
                const typingIndicator = document.querySelector('.typing-indicator');
                if (typingIndicator) {
                    typingIndicator.remove();
                }
            }

            generateChatResponse(userMessage) {
                const message = userMessage.toLowerCase();
                
                const responses = {
                    greeting: [
                        "Hello! Welcome to ShopSphere. How can I help you find the perfect product today?",
                        "Hi there! I'm excited to help you discover amazing deals and products. What are you looking for?",
                        "Welcome to ShopSphere! I'm here to make your shopping experience exceptional. What can I assist you with?"
                    ],
                    product: [
                        "We have an amazing selection of products! Could you tell me what category you're interested in?",
                        "I'd love to help you find the perfect product. Are you looking for electronics, fashion, home items, or something else?",
                        "Our product catalog is extensive! What specific item or category can I help you explore?"
                    ],
                    price: [
                        "We offer competitive pricing across all categories. Many items have special discounts right now!",
                        "Pricing varies by category, but we always strive for the best value. Check our current deals section for amazing offers!",
                        "We have products for every budget! Would you like me to show you items in a specific price range?"
                    ],
                    shipping: [
                        "We offer free shipping on orders over $50! Express delivery is available for $9.99.",
                        "Standard shipping takes 3-5 business days, but premium members get free 2-day shipping!",
                        "We have multiple shipping options including same-day delivery in select cities. What's your location?"
                    ],
                    support: [
                        "Our customer support team is available 24/7! You can reach us at support@shopsphere.com or +1 (234) 567-8900.",
                        "I'm here to help! For complex issues, I can connect you with our human specialists. What do you need assistance with?",
                        "We're committed to excellent customer service. How can I make your ShopSphere experience better today?"
                    ],
                    default: [
                        "That's an interesting question! Could you provide more details so I can give you the best answer?",
                        "I want to make sure I understand correctly. Could you rephrase that or give me more context?",
                        "Let me help you with that! Can you be more specific about what you're looking for?"
                    ]
                };

                // Determine response category
                let category = 'default';
                
                if (message.includes('hello') || message.includes('hi') || message.includes('hey')) {
                    category = 'greeting';
                } else if (message.includes('product') || message.includes('item') || message.includes('buy')) {
                    category = 'product';
                } else if (message.includes('price') || message.includes('cost') || message.includes('expensive')) {
                    category = 'price';
                } else if (message.includes('shipping') || message.includes('delivery') || message.includes('ship')) {
                    category = 'shipping';
                } else if (message.includes('support') || message.includes('help') || message.includes('problem')) {
                    category = 'support';
                }

                const categoryResponses = responses[category];
                return categoryResponses[Math.floor(Math.random() * categoryResponses.length)];
            }

            // Enhanced Review System
            initReviewSystem() {
                const reviewForm = document.getElementById('reviewForm');
                const starRating = document.getElementById('starRating');
                const ratingValue = document.getElementById('ratingValue');

                if (!reviewForm) return;

                // Star rating interaction
                const stars = starRating.querySelectorAll('i');
                stars.forEach((star, index) => {
                    star.addEventListener('mouseenter', () => {
                        this.updateStarDisplay(index + 1);
                    });
                    
                    star.addEventListener('click', () => {
                        this.currentRating = index + 1;
                        ratingValue.value = this.currentRating;
                        this.updateStarDisplay(this.currentRating, true);
                    });
                });

                starRating.addEventListener('mouseleave', () => {
                    this.updateStarDisplay(this.currentRating, true);
                });

                // Form submission
                reviewForm.addEventListener('submit', (e) => {
                    e.preventDefault();
                    this.submitReview();
                });
            }

            updateStarDisplay(rating, permanent = false) {
                const stars = document.querySelectorAll('#starRating i');
                stars.forEach((star, index) => {
                    if (index < rating) {
                        star.classList.remove('far');
                        star.classList.add('fas');
                    } else {
                        star.classList.remove('fas');
                        star.classList.add('far');
                    }
                });
            }

            submitReview() {
                const form = document.getElementById('reviewForm');
                const name = form.querySelector('#reviewerName').value;
                const email = form.querySelector('#reviewerEmail').value;
                const reviewText = form.querySelector('#reviewText').value;
                const rating = this.currentRating;

                if (!name || !email || !reviewText || rating === 0) {
                    this.showNotification('Please fill all fields and provide a rating!', 'error');
                    return;
                }

                // Create new review element
                const reviewsList = document.getElementById('reviewsList');
                const newReview = this.createReviewElement(name, reviewText, rating);
                
                reviewsList.insertBefore(newReview, reviewsList.firstChild);
                
                // Reset form
                form.reset();
                this.currentRating = 0;
                this.updateStarDisplay(0, true);
                
                // Animate new review
                setTimeout(() => {
                    newReview.classList.add('visible');
                }, 100);
                
                this.showNotification('Thank you for your review! 🌟', 'success');
            }

            createReviewElement(name, reviewText, rating) {
                const reviewElement = document.createElement('div');
                reviewElement.className = 'review-item';
                
                const initials = name.split(' ').map(n => n[0]).join('').toUpperCase();
                const currentDate = new Date().toLocaleDateString('en-US', { 
                    year: 'numeric', 
                    month: 'long', 
                    day: 'numeric' 
                });
                
                let starsHTML = '';
                for (let i = 0; i < 5; i++) {
                    starsHTML += `<i class="${i < rating ? 'fas' : 'far'} fa-star"></i>`;
                }
                
                reviewElement.innerHTML = `
                    <div class="review-header">
                        <div class="reviewer-avatar">${initials}</div>
                        <div class="reviewer-info">
                            <h4>${name}</h4>
                            <div class="review-date">${currentDate}</div>
                        </div>
                    </div>
                    <div class="review-rating">${starsHTML}</div>
                    <div class="review-text">
                        <p>${reviewText}</p>
                    </div>
                    <div class="review-actions">
                        <div class="review-action">
                            <i class="far fa-thumbs-up"></i>
                            <span>Helpful (0)</span>
                        </div>
                        <div class="review-action">
                            <i class="far fa-comment"></i>
                            <span>Reply</span>
                        </div>
                        <div class="review-action">
                            <i class="far fa-share-square"></i>
                            <span>Share</span>
                        </div>
                    </div>
                `;
                
                return reviewElement;
            }

            // Newsletter Subscription
            initNewsletter() {
                const newsletterForm = document.getElementById('newsletterForm');
                
                if (newsletterForm) {
                    newsletterForm.addEventListener('submit', (e) => {
                        e.preventDefault();
                        const email = newsletterForm.querySelector('input').value;
                        
                        if (this.validateEmail(email)) {
                            this.showNotification('Successfully subscribed! Welcome to ShopSphere family 🎉', 'success');
                            newsletterForm.reset();
                        } else {
                            this.showNotification('Please enter a valid email address', 'error');
                        }
                    });
                }
            }

            validateEmail(email) {
                const regex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
                return regex.test(email);
            }

            // Countdown Timers
            initCountdownTimers() {
                const timers = document.querySelectorAll('.countdown-timer');
                
                timers.forEach(timer => {
                    this.startCountdown(timer);
                });
            }

            startCountdown(timerElement) {
                const days = parseInt(timerElement.querySelector('[data-timer="days"]').textContent);
                const hours = parseInt(timerElement.querySelector('[data-timer="hours"]').textContent);
                const minutes = parseInt(timerElement.querySelector('[data-timer="minutes"]').textContent);
                const seconds = parseInt(timerElement.querySelector('[data-timer="seconds"]').textContent);
                
                let totalSeconds = (days * 86400) + (hours * 3600) + (minutes * 60) + seconds;
                
                const countdownInterval = setInterval(() => {
                    if (totalSeconds <= 0) {
                        clearInterval(countdownInterval);
                        this.handleCountdownComplete(timerElement);
                        return;
                    }
                    
                    const d = Math.floor(totalSeconds / 86400);
                    const h = Math.floor((totalSeconds % 86400) / 3600);
                    const m = Math.floor((totalSeconds % 3600) / 60);
                    const s = totalSeconds % 60;
                    
                    timerElement.querySelector('[data-timer="days"]').textContent = String(d).padStart(2, '0');
                    timerElement.querySelector('[data-timer="hours"]').textContent = String(h).padStart(2, '0');
                    timerElement.querySelector('[data-timer="minutes"]').textContent = String(m).padStart(2, '0');
                    timerElement.querySelector('[data-timer="seconds"]').textContent = String(s).padStart(2, '0');
                    
                    totalSeconds--;
                }, 1000);
            }

            handleCountdownComplete(timerElement) {
                const offerCard = timerElement.closest('.offer-card');
                const button = offerCard.querySelector('.btn');
                button.textContent = 'Deal Expired';
                button.disabled = true;
                button.style.background = 'var(--gray)';
            }

            // Parallax Effects
            initParallaxEffects() {
                const parallaxElements = document.querySelectorAll('.parallax-element');
                
                window.addEventListener('scroll', () => {
                    const scrolled = window.pageYOffset;
                    
                    parallaxElements.forEach(element => {
                        const speed = element.dataset.speed || 0.5;
                        const yPos = -(scrolled * speed);
                        element.style.transform = `translateY(${yPos}px)`;
                    });
                }, { passive: true });
            }

            // Keyboard Navigation
            initKeyboardNavigation() {
                document.addEventListener('keydown', (e) => {
                    // ESC to close chatbot
                    if (e.key === 'Escape') {
                        const chatbot = document.getElementById('chatbotContainer');
                        if (chatbot.classList.contains('active')) {
                            chatbot.classList.remove('active');
                        }
                    }
                    
                    // Ctrl/Cmd + K to focus search
                    if ((e.ctrlKey || e.metaKey) && e.key === 'k') {
                        e.preventDefault();
                        const searchInput = document.querySelector('.search-container input');
                        searchInput.focus();
                    }
                });
            }

            // Intersection Observer for Animations
            initIntersectionObserver() {
                const observerOptions = {
                    threshold: 0.1,
                    rootMargin: '0px 0px -50px 0px'
                };

                const observer = new IntersectionObserver((entries) => {
                    entries.forEach(entry => {
                        if (entry.isIntersecting) {
                            entry.target.classList.add('animate');
                            // Add specific animations based on element type
                            if (entry.target.classList.contains('category-card')) {
                                entry.target.style.animationDelay = `${Math.random() * 0.5}s`;
                            }
                        }
                    });
                }, observerOptions);

                // Observe all animated elements
                const elementsToObserve = document.querySelectorAll('.category-card, .product-card, .feature-card, .review-item');
                elementsToObserve.forEach(el => observer.observe(el));
            }

            // Enhanced Notification System
            showNotification(message, type = 'info') {
                const notification = document.createElement('div');
                notification.className = `notification ${type}`;
                
                const icons = {
                    success: 'fas fa-check-circle',
                    error: 'fas fa-exclamation-circle',
                    warning: 'fas fa-exclamation-triangle',
                    info: 'fas fa-info-circle'
                };
                
                notification.innerHTML = `
                    <div class="notification-icon">
                        <i class="${icons[type]}"></i>
                    </div>
                    <div class="notification-content">
                        <div class="notification-message">${message}</div>
                    </div>
                `;
                
                document.body.appendChild(notification);
                
                // Animate in
                setTimeout(() => {
                    notification.classList.add('show');
                }, 100);
                
                // Auto remove
                setTimeout(() => {
                    notification.classList.remove('show');
                    setTimeout(() => {
                        if (notification.parentNode) {
                            notification.parentNode.removeChild(notification);
                        }
                    }, 300);
                }, 4000);
            }

            // Search Functionality
            initSearch() {
                const searchInput = document.querySelector('.search-container input');
                const searchButton = document.querySelector('.search-container button');
                
                const performSearch = () => {
                    const query = searchInput.value.trim();
                    if (query) {
                        this.showNotification(`Searching for "${query}"...`, 'info');
                        // In a real app, this would trigger actual search
                        setTimeout(() => {
                            this.showNotification(`Found 42 results for "${query}"`, 'success');
                        }, 1000);
                    }
                };

                searchButton.addEventListener('click', performSearch);
                searchInput.addEventListener('keypress', (e) => {
                    if (e.key === 'Enter') {
                        performSearch();
                    }
                });
            }

            // Advanced Product Recommendations
            getProductRecommendations(currentProduct) {
                // Simulate AI-powered recommendations
                const recommendations = [
                    'Based on your interests, you might like our Premium Wireless Earbuds',
                    'Customers who bought this also purchased our Smart Watch Pro',
                    'Complete your setup with our Laptop Stand and Wireless Mouse',
                    'You might be interested in our Extended Warranty Protection'
                ];
                
                return recommendations[Math.floor(Math.random() * recommendations.length)];
            }

            // Shopping Cart Management
            removeFromCart(productId) {
                this.cart = this.cart.filter(item => item.id !== productId);
                localStorage.setItem('cart', JSON.stringify(this.cart));
                this.updateCartCount();
                this.showNotification('Item removed from cart', 'info');
            }

            clearCart() {
                this.cart = [];
                localStorage.setItem('cart', JSON.stringify(this.cart));
                this.updateCartCount();
                this.showNotification('Cart cleared', 'info');
            }

            // Wishlist Management
            clearWishlist() {
                this.wishlist = [];
                localStorage.setItem('wishlist', JSON.stringify(this.wishlist));
                this.showNotification('Wishlist cleared', 'info');
            }

            // Price Tracking
            trackPriceChanges() {
                // Simulate price tracking functionality
                const products = document.querySelectorAll('.product-card');
                products.forEach(product => {
                    const priceElement = product.querySelector('.current-price');
                    if (priceElement && Math.random() > 0.8) {
                        // Simulate price drop
                        setTimeout(() => {
                            this.showNotification('Price drop alert! One of your watched items is now cheaper!', 'success');
                        }, Math.random() * 10000);
                    }
                });
            }

            // Advanced Analytics
            trackUserBehavior(action, data) {
                // In a real app, this would send data to analytics service
                console.log(`Analytics: ${action}`, data);
            }

            // Performance Optimizations
            debounce(func, wait) {
                let timeout;
                return function executedFunction(...args) {
                    const later = () => {
                        clearTimeout(timeout);
                        func(...args);
                    };
                    clearTimeout(timeout);
                    timeout = setTimeout(later, wait);
                };
            }

            throttle(func, limit) {
                let inThrottle;
                return function() {
                    const args = arguments;
                    const context = this;
                    if (!inThrottle) {
                        func.apply(context, args);
                        inThrottle = true;
                        setTimeout(() => inThrottle = false, limit);
                    }
                }
            }
        }

        // Initialize Application
        const app = new ShopSphereApp();

        // Additional Event Listeners
        document.addEventListener('DOMContentLoaded', function() {
            // Smooth scrolling for anchor links
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    const target = document.querySelector(this.getAttribute('href'));
                    if (target) {
                        target.scrollIntoView({
                            behavior: 'smooth',
                            block: 'start'
                        });
                    }
                });
            });

            // Enhanced dropdown hover effects
            const dropdownItems = document.querySelectorAll('.dropdown-item');
            dropdownItems.forEach(item => {
                item.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateX(8px)';
                });
                
                item.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateX(0)';
                });
            });

            // Product card interactions
            const productCards = document.querySelectorAll('.product-card');
            productCards.forEach(card => {
                card.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateY(-15px) scale(1.02)';
                });
                
                card.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateY(0) scale(1)';
                });
            });

            // Dynamic background colors for categories
            const categoryCards = document.querySelectorAll('.category-card');
            categoryCards.forEach((card, index) => {
                const colors = ['#4a6de5', '#ff6b6b', '#20c997', '#ffc107', '#6f42c1', '#fd7e14', '#e83e8c', '#17a2b8'];
                const icon = card.querySelector('i');
                if (icon) {
                    icon.style.color = colors[index % colors.length];
                }
                
                card.addEventListener('mouseenter', function() {
                    this.style.background = `linear-gradient(135deg, ${colors[index % colors.length]}10, ${colors[index % colors.length]}05)`;
                });
                
                card.addEventListener('mouseleave', function() {
                    this.style.background = 'var(--white)';
                });
            });

            // Advanced search suggestions
            const searchInput = document.querySelector('.search-container input');
            if (searchInput) {
                searchInput.addEventListener('input', app.debounce(function() {
                    const query = this.value;
                    if (query.length > 2) {
                        // In a real app, this would show search suggestions
                        console.log('Searching for:', query);
                    }
                }, 300));
            }

            // Footer link animations
            const footerLinks = document.querySelectorAll('.footer-links a');
            footerLinks.forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    this.style.animation = 'pulse 0.3s ease';
                    setTimeout(() => {
                        this.style.animation = '';
                    }, 300);
                });
            });

            // Payment method hover effects
            const paymentMethods = document.querySelectorAll('.payment-method');
            paymentMethods.forEach(method => {
                method.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateY(-3px) scale(1.05)';
                    this.style.background = 'rgba(74, 109, 229, 0.2)';
                });
                
                method.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateY(0) scale(1)';
                    this.style.background = 'rgba(255,255,255,0.1)';
                });
            });

            // Add scroll-to-top functionality
            const scrollToTop = document.createElement('div');
            scrollToTop.innerHTML = '<i class="fas fa-arrow-up"></i>';
            scrollToTop.style.cssText = `
                position: fixed;
                bottom: 120px;
                left: 30px;
                width: 50px;
                height: 50px;
                background: var(--primary);
                color: var(--white);
                border-radius: 50%;
                display: flex;
                align-items: center;
                justify-content: center;
                cursor: pointer;
                z-index: 997;
                opacity: 0;
                visibility: hidden;
                transition: var(--transition);
                box-shadow: var(--shadow);
            `;
            document.body.appendChild(scrollToTop);

            window.addEventListener('scroll', () => {
                if (window.pageYOffset > 300) {
                    scrollToTop.style.opacity = '1';
                    scrollToTop.style.visibility = 'visible';
                } else {
                    scrollToTop.style.opacity = '0';
                    scrollToTop.style.visibility = 'hidden';
                }
            });

            scrollToTop.addEventListener('click', () => {
                window.scrollTo({ top: 0, behavior: 'smooth' });
            });

            // Initialize price tracking
            app.trackPriceChanges();

            // Add CSS animations for fade effects
            const style = document.createElement('style');
            style.textContent = `
                @keyframes fadeOut {
                    from { opacity: 1; transform: scale(1); }
                    to { opacity: 0; transform: scale(0.9); }
                }
                
                @keyframes pulse {
                    0%, 100% { transform: scale(1); }
                    50% { transform: scale(1.05); }
                }
                
                .animate {
                    animation: fadeInUp 0.6s ease forwards;
                }
                
                .product-card {
                    transform: translateY(30px);
                    opacity: 0;
                    transition: all 0.6s ease;
                }
                
                .product-card.animate {
                    transform: translateY(0);
                    opacity: 1;
                }
                
                .category-card {
                    transform: translateY(30px);
                    opacity: 0;
                    transition: all 0.6s ease;
                }
                
                .category-card.animate {
                    transform: translateY(0);
                    opacity: 1;
                }
                
                .feature-card {
                    transform: translateY(30px);
                    opacity: 0;
                    transition: all 0.6s ease;
                }
                
                .feature-card.animate {
                    transform: translateY(0);
                    opacity: 1;
                }
            `;
            document.head.appendChild(style);
        });

        // Service Worker for Progressive Web App features
        if ('serviceWorker' in navigator) {
            window.addEventListener('load', () => {
                // In a real app, you would register a service worker here
                console.log('PWA features ready');
            });
        }

        // Advanced Error Handling
        window.addEventListener('error', (e) => {
            console.error('JavaScript Error:', e.error);
            // In a real app, you would send this to an error tracking service
        });

        window.addEventListener('unhandledrejection', (e) => {
            console.error('Unhandled Promise Rejection:', e.reason);
            // In a real app, you would send this to an error tracking service
        });

        // Performance monitoring
        window.addEventListener('load', () => {
            if ('performance' in window) {
                const loadTime = performance.timing.loadEventEnd - performance.timing.navigationStart;
                console.log(`Page loaded in ${loadTime}ms`);
                
                // In a real app, you would send performance metrics to analytics
            }
        });

        // Advanced theme switching (for future implementation)
        function initThemeToggle() {
            const themes = {
                light: {
                    '--primary': '#4a6de5',
                    '--dark': '#2c3e50',
                    '--light': '#f8f9fa',
                    '--white': '#ffffff'
                },
                dark: {
                    '--primary': '#6b8ef7',
                    '--dark': '#ffffff',
                    '--light': '#2c3e50',
                    '--white': '#1a1a1a'
                }
            };
            
            // Theme toggle functionality would go here
        }

        // Advanced form validation
        function validateForm(form) {
            const inputs = form.querySelectorAll('input[required], textarea[required]');
            let isValid = true;
            
            inputs.forEach(input => {
                const value = input.value.trim();
                const errorElement = input.parentNode.querySelector('.error-message');
                
                if (errorElement) {
                    errorElement.remove();
                }
                
                if (!value) {
                    isValid = false;
                    const error = document.createElement('div');
                    error.className = 'error-message';
                    error.textContent = `${input.labels[0]?.textContent || 'This field'} is required`;
                    input.parentNode.appendChild(error);
                    input.style.borderColor = 'var(--danger)';
                } else {
                    input.style.borderColor = 'var(--success)';
                }
            });
            
            return isValid;
        }

        // Local Storage Management
        class StorageManager {
            static set(key, value) {
                try {
                    localStorage.setItem(key, JSON.stringify(value));
                    return true;
                } catch (e) {
                    console.error('Storage error:', e);
                    return false;
                }
            }
            
            static get(key) {
                try {
                    const value = localStorage.getItem(key);
                    return value ? JSON.parse(value) : null;
                } catch (e) {
                    console.error('Storage error:', e);
                    return null;
                }
            }
            
            static remove(key) {
                try {
                    localStorage.removeItem(key);
                    return true;
                } catch (e) {
                    console.error('Storage error:', e);
                    return false;
                }
            }
        }

        // Image lazy loading
        function initLazyLoading() {
            if ('IntersectionObserver' in window) {
                const imageObserver = new IntersectionObserver((entries) => {
                    entries.forEach(entry => {
                        if (entry.isIntersecting) {
                            const img = entry.target;
                            img.src = img.dataset.src;
                            img.classList.remove('lazy');
                            imageObserver.unobserve(img);
                        }
                    });
                });

                document.querySelectorAll('img[data-src]').forEach(img => {
                    imageObserver.observe(img);
                });
            }
        }

        // Initialize all additional features
        document.addEventListener('DOMContentLoaded', () => {
            initLazyLoading();
            
            // Add custom CSS animations for specific interactions
            const additionalStyles = `
                .category-card:nth-child(1) { animation-delay: 0.1s; }
                .category-card:nth-child(2) { animation-delay: 0.2s; }
                .category-card:nth-child(3) { animation-delay: 0.3s; }
                .category-card:nth-child(4) { animation-delay: 0.4s; }
                .category-card:nth-child(5) { animation-delay: 0.5s; }
                .category-card:nth-child(6) { animation-delay: 0.6s; }
                .category-card:nth-child(7) { animation-delay: 0.7s; }
                .category-card:nth-child(8) { animation-delay: 0.8s; }
                
                .product-card:nth-child(1) { animation-delay: 0.1s; }
                .product-card:nth-child(2) { animation-delay: 0.2s; }
                .product-card:nth-child(3) { animation-delay: 0.3s; }
                .product-card:nth-child(4) { animation-delay: 0.4s; }
                .product-card:nth-child(5) { animation-delay: 0.5s; }
                .product-card:nth-child(6) { animation-delay: 0.6s; }
                .product-card:nth-child(7) { animation-delay: 0.7s; }
                .product-card:nth-child(8) { animation-delay: 0.8s; }
            `;
            
            const styleSheet = document.createElement('style');
            styleSheet.textContent = additionalStyles;
            document.head.appendChild(styleSheet);
        });
    </script>
</body>
</html>




