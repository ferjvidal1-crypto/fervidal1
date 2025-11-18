# fervidal1
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Evaluación Entrenadores - SENA Bienestar al Funcionario 2025</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            padding: 20px;
            min-height: 100vh;
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.1);
            overflow: hidden;
        }

        .header {
            background: linear-gradient(135deg, #FF6B00 0%, #FF8C00 100%);
            color: white;
            padding: 40px 30px;
            text-align: center;
        }

        .header-logos {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 30px;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }

        .logo-box {
            background: white;
            padding: 15px 25px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .logo-text {
            font-size: 28px;
            font-weight: bold;
            color: #39A900;
            margin: 0;
        }

        .logo-subtitle {
            font-size: 14px;
            color: #FF6B00;
            margin-top: 5px;
        }

        .header h1 {
            font-size: 28px;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
        }

        .header p {
            font-size: 16px;
            opacity: 0.95;
        }

        /* Progress Bar */
        .progress-container {
            background: white;
            padding: 20px 30px;
            border-bottom: 2px solid #e0e0e0;
        }

        .progress-steps {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            position: relative;
        }

        .progress-steps::before {
            content: '';
            position: absolute;
            top: 20px;
            left: 0;
            right: 0;
            height: 3px;
            background: #e0e0e0;
            z-index: 1;
        }

        .progress-line {
            position: absolute;
            top: 20px;
            left: 0;
            height: 3px;
            background: linear-gradient(90deg, #39A900 0%, #FF6B00 100%);
            z-index: 2;
            transition: width 0.4s ease;
        }

        .step {
            position: relative;
            z-index: 3;
            text-align: center;
            flex: 1;
        }

        .step-circle {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: white;
            border: 3px solid #e0e0e0;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 8px;
            font-weight: bold;
            color: #999;
            transition: all 0.3s ease;
        }

        .step.active .step-circle {
            border-color: #39A900;
            background: #39A900;
            color: white;
            transform: scale(1.1);
        }

        .step.completed .step-circle {
            border-color: #39A900;
            background: #39A900;
            color: white;
        }

        .step-label {
            font-size: 13px;
            color: #666;
            font-weight: 500;
        }

        .step.active .step-label {
            color: #39A900;
            font-weight: bold;
        }

        /* Form Content */
        .form-content {
            padding: 40px 30px;
            min-height: 500px;
        }

        .form-section {
            display: none;
            animation: fadeIn 0.5s ease;
        }

        .form-section.active {
            display: block;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .section-header {
            margin-bottom: 30px;
            text-align: center;
        }

        .section-icon {
            font-size: 50px;
            margin-bottom: 15px;
        }

        .section-title {
            font-size: 26px;
            color: #39A900;
            margin-bottom: 10px;
            font-weight: bold;
        }

        .section-description {
            font-size: 15px;
            color: #666;
            line-height: 1.6;
        }

        .card {
            background: #f8f9fa;
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 25px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
            border-left: 5px solid #39A900;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .card:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
        }

        .card-header {
            font-size: 16px;
            color: #333;
            font-weight: 600;
            margin-bottom: 15px;
        }

        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            margin-bottom: 10px;
            color: #333;
            font-weight: 500;
            font-size: 15px;
        }

        input[type="text"],
        input[type="email"],
        select,
        textarea {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            font-size: 15px;
            transition: all 0.3s ease;
            font-family: inherit;
        }

        input[type="text"]:focus,
        input[type="email"]:focus,
        select:focus,
        textarea:focus {
            outline: none;
            border-color: #39A900;
            box-shadow: 0 0 0 3px rgba(57, 169, 0, 0.1);
        }

        textarea {
            resize: vertical;
            min-height: 100px;
        }

        .emoji-scale {
            display: flex;
            justify-content: space-between;
            gap: 10px;
            margin-top: 15px;
            flex-wrap: wrap;
        }

        .emoji-option {
            flex: 1;
            min-width: 80px;
            text-align: center;
            cursor: pointer;
            padding: 15px 10px;
            border: 3px solid #e0e0e0;
            border-radius: 12px;
            transition: all 0.3s ease;
            background: white;
        }

        .emoji-option:hover {
            border-color: #FF6B00;
            transform: scale(1.05);
        }

        .emoji-option input[type="radio"] {
            display: none;
        }

        .emoji-option.selected {
            border-color: #39A900;
            background: #f0f8e8;
            box-shadow: 0 5px 15px rgba(57, 169, 0, 0.2);
        }

        .emoji-content {
            pointer-events: none;
        }

        .emoji {
            font-size: 40px;
            display: block;
            margin-bottom: 8px;
        }

        .emoji-label {
            font-size: 13px;
            font-weight: 600;
            color: #666;
        }

        .checkbox-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 12px;
            margin-top: 15px;
        }

        .checkbox-item {
            display: flex;
            align-items: center;
            padding: 10px;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s ease;
            background: white;
        }

        .checkbox-item:hover {
            border-color: #39A900;
            background: #f0f8e8;
        }

        .checkbox-item input[type="checkbox"],
        .checkbox-item input[type="radio"] {
            margin-right: 10px;
            width: 20px;
            height: 20px;
            cursor: pointer;
            accent-color: #39A900;
        }

        .checkbox-item label {
            margin: 0;
            cursor: pointer;
            flex: 1;
            font-weight: normal;
        }

        .radio-group {
            display: flex;
            flex-direction: column;
            gap: 12px;
            margin-top: 15px;
        }

        .radio-item {
            display: flex;
            align-items: center;
            padding: 12px;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
            background: white;
        }

        .radio-item:hover {
            border-color: #FF6B00;
            background: #fff5f0;
        }

        .radio-item input[type="radio"] {
            margin-right: 12px;
            width: 22px;
            height: 22px;
            cursor: pointer;
            accent-color: #39A900;
        }

        .radio-item.selected {
            border-color: #39A900;
            background: #f0f8e8;
        }

        /* Navigation Buttons */
        .form-navigation {
            display: flex;
            justify-content: space-between;
            gap: 15px;
            margin-top: 40px;
            padding-top: 30px;
            border-top: 2px solid #e0e0e0;
        }

        .nav-btn {
            padding: 15px 40px;
            font-size: 16px;
            font-weight: bold;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .btn-prev {
            background: #e0e0e0;
            color: #666;
        }

        .btn-prev:hover {
            background: #d0d0d0;
            transform: translateX(-3px);
        }

        .btn-next {
            background: linear-gradient(135deg, #39A900 0%, #2d8000 100%);
            color: white;
            box-shadow: 0 5px 20px rgba(57, 169, 0, 0.3);
            margin-left: auto;
        }

        .btn-next:hover {
            transform: translateX(3px);
            box-shadow: 0 8px 25px rgba(57, 169, 0, 0.4);
        }

        .btn-submit {
            background: linear-gradient(135deg, #FF6B00 0%, #FF8C00 100%);
            color: white;
            box-shadow: 0 5px 20px rgba(255, 107, 0, 0.3);
            margin-left: auto;
        }

        .btn-submit:hover {
            box-shadow: 0 8px 25px rgba(255, 107, 0, 0.4);
        }

        .btn-next:disabled,
        .btn-submit:disabled {
            background: #cccccc;
            cursor: not-allowed;
            box-shadow: none;
        }

        .required {
            color: #FF6B00;
            font-weight: bold;
        }

        .success-message,
        .error-message {
            display: none;
            padding: 20px;
            border-radius: 10px;
            margin: 20px 0;
            border: 2px solid;
            text-align: center;
        }

        .success-message {
            background: #d4edda;
            color: #155724;
            border-color: #c3e6cb;
        }

        .error-message {
            background: #f8d7da;
            color: #721c24;
            border-color: #f5c6cb;
        }

        .loading {
            display: none;
            text-align: center;
            padding: 40px;
        }

        .spinner {
            border: 4px solid #f3f3f3;
            border-top: 4px solid #39A900;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            animation: spin 1s linear infinite;
            margin: 0 auto 20px;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Tabla de cambio de entrenador */
        .trainer-change-table {
            margin-top: 15px;
        }

        .table-header {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr;
            gap: 10px;
            font-weight: bold;
            padding: 12px;
            background: #39A900;
            color: white;
            border-radius: 8px;
            margin-bottom: 10px;
        }

        .table-row {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr;
            gap: 10px;
            align-items: center;
            padding: 12px;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            margin-bottom: 8px;
            background: white;
            transition: all 0.3s ease;
        }

        .table-row:hover {
            border-color: #39A900;
            background: #f0f8e8;
        }

        .table-row input[type="radio"] {
            width: 20px;
            height: 20px;
            accent-color: #39A900;
            cursor: pointer;
        }

        @media (max-width: 768px) {
            .container {
                border-radius: 0;
            }

            .header {
                padding: 30px 20px;
            }

            .header h1 {
                font-size: 22px;
            }

            .form-content {
                padding: 25px 20px;
            }

            .emoji-scale {
                gap: 8px;
            }

            .emoji {
                font-size: 32px;
            }

            .checkbox-grid {
                grid-template-columns: 1fr;
            }

            .form-navigation {
                flex-direction: column;
            }

            .btn-prev,
            .btn-next,
            .btn-submit {
                width: 100%;
                justify-content: center;
            }

            .progress-steps {
                overflow-x: auto;
                padding-bottom: 10px;
            }

            .step-label {
                font-size: 11px;
            }

            .table-header,
            .table-row {
                grid-template-columns: 1.5fr 1fr 1fr;
                font-size: 13px;
            }
        }

        /* Ocultar sección de éxito inicialmente */
        #successSection {
            display: none;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="header-logos">
                <div class="logo-box">
                    <p class="logo-text">SENA</p>
                    <p class="logo-subtitle">Regional Valle</p>
                </div>
                <div class="logo-box">
                    <p class="logo-text" style="color: #FF6B00;">Bienestar</p>
                    <p class="logo-subtitle">al Funcionario</p>
                </div>
            </div>
            <h1>📋 Evaluación de Entrenadores</h1>
            <p>Programa Deportivo y Cultural 2025</p>
        </div>

        <!-- Progress Bar -->
        <div class="progress-container">
            <div class="progress-steps">
                <div class="progress-line" id="progressLine" style="width: 0%"></div>
                <div class="step active" data-step="1">
                    <div class="step-circle">1</div>
                    <div class="step-label">Información Personal</div>
                </div>
                <div class="step" data-step="2">
                    <div class="step-circle">2</div>
                    <div class="step-label">Evaluación Entrenador</div>
                </div>
                <div class="step" data-step="3">
                    <div class="step-circle">3</div>
                    <div class="step-label">Percepción Personal</div>
                </div>
                <div class="step" data-step="4">
                    <div class="step-circle">4</div>
                    <div class="step-label">Cambios y Mejoras</div>
                </div>
            </div>
        </div>

        <div class="form-content">
            <form id="evaluacionForm">
                
                <!-- SECCIÓN 1: INFORMACIÓN PERSONAL -->
                <div class="form-section active" data-section="1">
                    <div class="section-header">
                        <div class="section-icon">👤</div>
                        <h2 class="section-title">Información Personal</h2>
                        <p class="section-description">
                            Por favor, completa tus datos básicos. Esta información nos ayudará a 
                            contextualizar tu evaluación y mejorar nuestros programas.
                        </p>
                    </div>

                    <div class="card">
                        <div class="card-header">Nombre Completo <span class="required">*</span></div>
                        <div class="form-group">
                            <input type="text" name="nombre" id="nombre" required placeholder="Ingrese su nombre completo">
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">Correo Institucional <span class="required">*</span></div>
                        <div class="form-group">
                            <input type="email" name="correo" id="correo" required placeholder="ejemplo@sena.edu.co">
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">Centro de Formación <span class="required">*</span></div>
                        <div class="form-group">
                            <select name="centro" id="centro" required>
                                <option value="">Seleccione su centro</option>
                                <option value="Centro de la Construcción">Centro de la Construcción</option>
                                <option value="Centro de Diseño Tecnológico Industrial">Centro de Diseño Tecnológico Industrial</option>
                                <option value="Centro Náutico Pesquero Buenaventura">Centro Náutico Pesquero Buenaventura</option>
                                <option value="Centro de Electricidad y Automatización Industrial">Centro de Electricidad y Automatización Industrial</option>
                                <option value="Centro Gestión Tecnológica de servicios">Centro Gestión Tecnológica de servicios</option>
                                <option value="Centro de Biotecnología Industrial Palmira">Centro de Biotecnología Industrial Palmira</option>
                                <option value="Centro Agropecuario de Buga">Centro Agropecuario de Buga</option>
                                <option value="Centro Latinoamericano de Especies menores Tuluá">Centro Latinoamericano de Especies menores Tuluá</option>
                                <option value="Centro de Tecnologías Agroindustriales Cartago">Centro de Tecnologías Agroindustriales Cartago</option>
                                <option value="Despacho Regional valle">Despacho Regional valle</option>
                                <option value="Centro Nacional De Asistencia Técnica A La Industria">Centro Nacional De Asistencia Técnica A La Industria</option>
                            </select>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">Disciplina(s) deportiva o cultural <span class="required">*</span></div>
                        <div class="form-group">
                            <div class="checkbox-grid">
                                <div class="checkbox-item">
                                    <input type="checkbox" name="disciplina" value="Natación" id="disc1">
                                    <label for="disc1">Natación</label>
                                </div>
                                <div class="checkbox-item">
                                    <input type="checkbox" name="disciplina" value="Acondicionamiento físico – Gym Salomia" id="disc2">
                                    <label for="disc2">Gym Salomia</label>
                                </div>
                                <div class="checkbox-item">
                                    <input type="checkbox" name="disciplina" value="Baloncesto" id="disc3">
                                    <label for="disc3">Baloncesto</label>
                                </div>
                                <div class="checkbox-item">
                                    <input type="checkbox" name="disciplina" value="Yoga y Pilates" id="disc4">
                                    <label for="disc4">Yoga y Pilates</label>
                                </div>
                                <div class="checkbox-item">
                                    <input type="checkbox" name="disciplina" value="Fútbol" id="disc5">
                                    <label for="disc5">Fútbol</label>
                                </div>
                                <div class="checkbox-item">
                                    <input type="checkbox" name="disciplina" value="Volleyball" id="disc6">
                                    <label for="disc6">Volleyball</label>
                                </div>
                                <div class="checkbox-item">
                                    <input type="checkbox" name="disciplina" value="Fisioterapia" id="disc7">
                                    <label for="disc7">Fisioterapia</label>
                                </div>
                                <div class="checkbox-item">
                                    <input type="checkbox" name="disciplina" value="Tenis de mesa" id="disc8">
                                    <label for="disc8">Tenis de mesa</label>
                                </div>
                                <div class="checkbox-item">
                                    <input type="checkbox" name="disciplina" value="Atletismo" id="disc9">
                                    <label for="disc9">Atletismo</label>
                                </div>
                                <div class="checkbox-item">
                                    <input type="checkbox" name="disciplina" value="Bolos" id="disc10">
                                    <label for="disc10">Bolos</label>
                                </div>
                                <div class="checkbox-item">
                                    <input type="checkbox" name="disciplina" value="Ajedrez" id="disc11">
                                    <label for="disc11">Ajedrez</label>
                                </div>
                                <div class="checkbox-item">
                                    <input type="checkbox" name="disciplina" value="Tejo" id="disc12">
                                    <label for="disc12">Tejo</label>
                                </div>
                                <div class="checkbox-item">
                                    <input type="checkbox" name="disciplina" value="Teatro" id="disc13">
                                    <label for="disc13">Teatro</label>
                                </div>
                                <div class="checkbox-item">
                                    <input type="checkbox" name="disciplina" value="Preparación física Buenaventura" id="disc14">
                                    <label for="disc14">Prep. Física Buenaventura</label>
                                </div>
                                <div class="checkbox-item">
                                    <input type="checkbox" name="disciplina" value="Preparación física Tuluá" id="disc15">
                                    <label for="disc15">Prep. Física Tuluá</label>
                                </div>
                                <div class="checkbox-item">
                                    <input type="checkbox" name="disciplina" value="Canto" id="disc16">
                                    <label for="disc16">Canto</label>
                                </div>
                                <div class="checkbox-item">
                                    <input type="checkbox" name="disciplina" value="Baile" id="disc17">
                                    <label for="disc17">Baile</label>
                                </div>
                                <div class="checkbox-item">
                                    <input type="checkbox" name="disciplina" value="Grupo musical" id="disc18">
                                    <label for="disc18">Grupo musical</label>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">Tiempo de participación <span class="required">*</span></div>
                        <div class="form-group">
                            <div class="radio-group">
                                <div class="radio-item">
                                    <input type="radio" name="tiempo" value="Menos de tres meses" id="tiempo1" required>
                                    <label for="tiempo1">⏱️ Menos de tres meses</label>
                                </div>
                                <div class="radio-item">
                                    <input type="radio" name="tiempo" value="De 3 a 6 meses" id="tiempo2">
                                    <label for="tiempo2">📅 De 3 a 6 meses</label>
                                </div>
                                <div class="radio-item">
                                    <input type="radio" name="tiempo" value="Más de 6 meses" id="tiempo3">
                                    <label for="tiempo3">🗓️ Más de 6 meses</label>
                                </div>
                                <div class="radio-item">
                                    <input type="radio" name="tiempo" value="1 Año" id="tiempo4">
                                    <label for="tiempo4">📆 1 Año</label>
                                </div>
                                <div class="radio-item">
                                    <input type="radio" name="tiempo" value="Más de 1 año" id="tiempo5">
                                    <label for="tiempo5">🎯 Más de 1 año</label>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- SECCIÓN 2: EVALUACIÓN DEL ENTRENADOR -->
                <div class="form-section" data-section="2">
                    <div class="section-header">
                        <div class="section-icon">⭐</div>
                        <h2 class="section-title">Evaluación del Entrenador</h2>
                        <p class="section-description">
                            Evalúa diferentes aspectos del desempeño de tu entrenador usando la escala de emojis,
                            donde 1 es "Deficiente" y 5 es "Excelente".
                        </p>
                    </div>

                    <div class="card">
                        <div class="card-header">Nivel de conocimiento técnico del entrenador</div>
                        <div class="emoji-scale">
                            <label class="emoji-option">
                                <input type="radio" name="conocimiento_tecnico" value="1" required>
                                <div class="emoji-content">
                                    <span class="emoji">😞</span>
                                    <span class="emoji-label">1 - Deficiente</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="conocimiento_tecnico" value="2">
                                <div class="emoji-content">
                                    <span class="emoji">😕</span>
                                    <span class="emoji-label">2 - Malo</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="conocimiento_tecnico" value="3">
                                <div class="emoji-content">
                                    <span class="emoji">😐</span>
                                    <span class="emoji-label">3 - Regular</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="conocimiento_tecnico" value="4">
                                <div class="emoji-content">
                                    <span class="emoji">😊</span>
                                    <span class="emoji-label">4 - Bueno</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="conocimiento_tecnico" value="5">
                                <div class="emoji-content">
                                    <span class="emoji">😄</span>
                                    <span class="emoji-label">5 - Excelente</span>
                                </div>
                            </label>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">Nivel de conocimiento táctico del entrenador</div>
                        <div class="emoji-scale">
                            <label class="emoji-option">
                                <input type="radio" name="conocimiento_tactico" value="1" required>
                                <div class="emoji-content">
                                    <span class="emoji">😞</span>
                                    <span class="emoji-label">1 - Deficiente</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="conocimiento_tactico" value="2">
                                <div class="emoji-content">
                                    <span class="emoji">😕</span>
                                    <span class="emoji-label">2 - Malo</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="conocimiento_tactico" value="3">
                                <div class="emoji-content">
                                    <span class="emoji">😐</span>
                                    <span class="emoji-label">3 - Regular</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="conocimiento_tactico" value="4">
                                <div class="emoji-content">
                                    <span class="emoji">😊</span>
                                    <span class="emoji-label">4 - Bueno</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="conocimiento_tactico" value="5">
                                <div class="emoji-content">
                                    <span class="emoji">😄</span>
                                    <span class="emoji-label">5 - Excelente</span>
                                </div>
                            </label>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">Capacidad para planificar sesiones acordes a mi nivel</div>
                        <div class="emoji-scale">
                            <label class="emoji-option">
                                <input type="radio" name="planificacion" value="1" required>
                                <div class="emoji-content">
                                    <span class="emoji">😞</span>
                                    <span class="emoji-label">1 - Deficiente</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="planificacion" value="2">
                                <div class="emoji-content">
                                    <span class="emoji">😕</span>
                                    <span class="emoji-label">2 - Malo</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="planificacion" value="3">
                                <div class="emoji-content">
                                    <span class="emoji">😐</span>
                                    <span class="emoji-label">3 - Regular</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="planificacion" value="4">
                                <div class="emoji-content">
                                    <span class="emoji">😊</span>
                                    <span class="emoji-label">4 - Bueno</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="planificacion" value="5">
                                <div class="emoji-content">
                                    <span class="emoji">😄</span>
                                    <span class="emoji-label">5 - Excelente</span>
                                </div>
                            </label>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">Comunicación clara y efectiva en las instrucciones</div>
                        <div class="emoji-scale">
                            <label class="emoji-option">
                                <input type="radio" name="comunicacion" value="1" required>
                                <div class="emoji-content">
                                    <span class="emoji">😞</span>
                                    <span class="emoji-label">1 - Deficiente</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="comunicacion" value="2">
                                <div class="emoji-content">
                                    <span class="emoji">😕</span>
                                    <span class="emoji-label">2 - Malo</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="comunicacion" value="3">
                                <div class="emoji-content">
                                    <span class="emoji">😐</span>
                                    <span class="emoji-label">3 - Regular</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="comunicacion" value="4">
                                <div class="emoji-content">
                                    <span class="emoji">😊</span>
                                    <span class="emoji-label">4 - Bueno</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="comunicacion" value="5">
                                <div class="emoji-content">
                                    <span class="emoji">😄</span>
                                    <span class="emoji-label">5 - Excelente</span>
                                </div>
                            </label>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">Brindó conocimiento sobre el plan de trabajo 2025</div>
                        <div class="emoji-scale">
                            <label class="emoji-option">
                                <input type="radio" name="plan_trabajo" value="1" required>
                                <div class="emoji-content">
                                    <span class="emoji">😞</span>
                                    <span class="emoji-label">1 - Deficiente</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="plan_trabajo" value="2">
                                <div class="emoji-content">
                                    <span class="emoji">😕</span>
                                    <span class="emoji-label">2 - Malo</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="plan_trabajo" value="3">
                                <div class="emoji-content">
                                    <span class="emoji">😐</span>
                                    <span class="emoji-label">3 - Regular</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="plan_trabajo" value="4">
                                <div class="emoji-content">
                                    <span class="emoji">😊</span>
                                    <span class="emoji-label">4 - Bueno</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="plan_trabajo" value="5">
                                <div class="emoji-content">
                                    <span class="emoji">😄</span>
                                    <span class="emoji-label">5 - Excelente</span>
                                </div>
                            </label>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">Cumplió el plan de trabajo establecido en 2025</div>
                        <div class="emoji-scale">
                            <label class="emoji-option">
                                <input type="radio" name="cumplimiento_plan" value="1" required>
                                <div class="emoji-content">
                                    <span class="emoji">😞</span>
                                    <span class="emoji-label">1 - Deficiente</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="cumplimiento_plan" value="2">
                                <div class="emoji-content">
                                    <span class="emoji">😕</span>
                                    <span class="emoji-label">2 - Malo</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="cumplimiento_plan" value="3">
                                <div class="emoji-content">
                                    <span class="emoji">😐</span>
                                    <span class="emoji-label">3 - Regular</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="cumplimiento_plan" value="4">
                                <div class="emoji-content">
                                    <span class="emoji">😊</span>
                                    <span class="emoji-label">4 - Bueno</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="cumplimiento_plan" value="5">
                                <div class="emoji-content">
                                    <span class="emoji">😄</span>
                                    <span class="emoji-label">5 - Excelente</span>
                                </div>
                            </label>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">Capacidad para adaptar ejercicios (inclusión)</div>
                        <div class="emoji-scale">
                            <label class="emoji-option">
                                <input type="radio" name="adaptacion" value="1" required>
                                <div class="emoji-content">
                                    <span class="emoji">😞</span>
                                    <span class="emoji-label">1 - Deficiente</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="adaptacion" value="2">
                                <div class="emoji-content">
                                    <span class="emoji">😕</span>
                                    <span class="emoji-label">2 - Malo</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="adaptacion" value="3">
                                <div class="emoji-content">
                                    <span class="emoji">😐</span>
                                    <span class="emoji-label">3 - Regular</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="adaptacion" value="4">
                                <div class="emoji-content">
                                    <span class="emoji">😊</span>
                                    <span class="emoji-label">4 - Bueno</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="adaptacion" value="5">
                                <div class="emoji-content">
                                    <span class="emoji">😄</span>
                                    <span class="emoji-label">5 - Excelente</span>
                                </div>
                            </label>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">Manejo adecuado de seguridad y prevención de lesiones</div>
                        <div class="emoji-scale">
                            <label class="emoji-option">
                                <input type="radio" name="seguridad" value="1" required>
                                <div class="emoji-content">
                                    <span class="emoji">😞</span>
                                    <span class="emoji-label">1 - Deficiente</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="seguridad" value="2">
                                <div class="emoji-content">
                                    <span class="emoji">😕</span>
                                    <span class="emoji-label">2 - Malo</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="seguridad" value="3">
                                <div class="emoji-content">
                                    <span class="emoji">😐</span>
                                    <span class="emoji-label">3 - Regular</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="seguridad" value="4">
                                <div class="emoji-content">
                                    <span class="emoji">😊</span>
                                    <span class="emoji-label">4 - Bueno</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="seguridad" value="5">
                                <div class="emoji-content">
                                    <span class="emoji">😄</span>
                                    <span class="emoji-label">5 - Excelente</span>
                                </div>
                            </label>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">Fomentó la motivación y el trabajo en equipo</div>
                        <div class="emoji-scale">
                            <label class="emoji-option">
                                <input type="radio" name="motivacion" value="1" required>
                                <div class="emoji-content">
                                    <span class="emoji">😞</span>
                                    <span class="emoji-label">1 - Deficiente</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="motivacion" value="2">
                                <div class="emoji-content">
                                    <span class="emoji">😕</span>
                                    <span class="emoji-label">2 - Malo</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="motivacion" value="3">
                                <div class="emoji-content">
                                    <span class="emoji">😐</span>
                                    <span class="emoji-label">3 - Regular</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="motivacion" value="4">
                                <div class="emoji-content">
                                    <span class="emoji">😊</span>
                                    <span class="emoji-label">4 - Bueno</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="motivacion" value="5">
                                <div class="emoji-content">
                                    <span class="emoji">😄</span>
                                    <span class="emoji-label">5 - Excelente</span>
                                </div>
                            </label>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">Gestión y organización de competencias/eventos</div>
                        <div class="emoji-scale">
                            <label class="emoji-option">
                                <input type="radio" name="gestion_eventos" value="1" required>
                                <div class="emoji-content">
                                    <span class="emoji">😞</span>
                                    <span class="emoji-label">1 - Deficiente</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="gestion_eventos" value="2">
                                <div class="emoji-content">
                                    <span class="emoji">😕</span>
                                    <span class="emoji-label">2 - Malo</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="gestion_eventos" value="3">
                                <div class="emoji-content">
                                    <span class="emoji">😐</span>
                                    <span class="emoji-label">3 - Regular</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="gestion_eventos" value="4">
                                <div class="emoji-content">
                                    <span class="emoji">😊</span>
                                    <span class="emoji-label">4 - Bueno</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="gestion_eventos" value="5">
                                <div class="emoji-content">
                                    <span class="emoji">😄</span>
                                    <span class="emoji-label">5 - Excelente</span>
                                </div>
                            </label>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">Puntualidad y responsabilidad en las sesiones</div>
                        <div class="emoji-scale">
                            <label class="emoji-option">
                                <input type="radio" name="puntualidad" value="1" required>
                                <div class="emoji-content">
                                    <span class="emoji">😞</span>
                                    <span class="emoji-label">1 - Deficiente</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="puntualidad" value="2">
                                <div class="emoji-content">
                                    <span class="emoji">😕</span>
                                    <span class="emoji-label">2 - Malo</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="puntualidad" value="3">
                                <div class="emoji-content">
                                    <span class="emoji">😐</span>
                                    <span class="emoji-label">3 - Regular</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="puntualidad" value="4">
                                <div class="emoji-content">
                                    <span class="emoji">😊</span>
                                    <span class="emoji-label">4 - Bueno</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="puntualidad" value="5">
                                <div class="emoji-content">
                                    <span class="emoji">😄</span>
                                    <span class="emoji-label">5 - Excelente</span>
                                </div>
                            </label>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">Trato respetuoso y ético hacia los deportistas</div>
                        <div class="emoji-scale">
                            <label class="emoji-option">
                                <input type="radio" name="respeto" value="1" required>
                                <div class="emoji-content">
                                    <span class="emoji">😞</span>
                                    <span class="emoji-label">1 - Deficiente</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="respeto" value="2">
                                <div class="emoji-content">
                                    <span class="emoji">😕</span>
                                    <span class="emoji-label">2 - Malo</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="respeto" value="3">
                                <div class="emoji-content">
                                    <span class="emoji">😐</span>
                                    <span class="emoji-label">3 - Regular</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="respeto" value="4">
                                <div class="emoji-content">
                                    <span class="emoji">😊</span>
                                    <span class="emoji-label">4 - Bueno</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="respeto" value="5">
                                <div class="emoji-content">
                                    <span class="emoji">😄</span>
                                    <span class="emoji-label">5 - Excelente</span>
                                </div>
                            </label>
                        </div>
                    </div>
                </div>

                <!-- SECCIÓN 3: PERCEPCIÓN PERSONAL -->
                <div class="form-section" data-section="3">
                    <div class="section-header">
                        <div class="section-icon">💭</div>
                        <h2 class="section-title">Percepción Personal</h2>
                        <p class="section-description">
                            Comparte tu experiencia personal y los beneficios que has obtenido 
                            del programa deportivo o cultural.
                        </p>
                    </div>

                    <div class="card">
                        <div class="card-header">Aspectos destacados del trabajo del entrenador</div>
                        <div class="form-group">
                            <textarea name="aspectos_destacados" placeholder="Describa los aspectos que más destaca..." required></textarea>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">Cualidad física que más mejoró en 2025</div>
                        <div class="radio-group">
                            <div class="radio-item">
                                <input type="radio" name="cualidad_fisica" value="Resistencia" id="cf1" required>
                                <label for="cf1">💪 Resistencia</label>
                            </div>
                            <div class="radio-item">
                                <input type="radio" name="cualidad_fisica" value="Velocidad" id="cf2">
                                <label for="cf2">⚡ Velocidad</label>
                            </div>
                            <div class="radio-item">
                                <input type="radio" name="cualidad_fisica" value="Fuerza" id="cf3">
                                <label for="cf3">🏋️ Fuerza</label>
                            </div>
                            <div class="radio-item">
                                <input type="radio" name="cualidad_fisica" value="Coordinación" id="cf4">
                                <label for="cf4">🤸 Coordinación</label>
                            </div>
                            <div class="radio-item">
                                <input type="radio" name="cualidad_fisica" value="Flexibilidad" id="cf5">
                                <label for="cf5">🧘 Flexibilidad</label>
                            </div>
                            <div class="radio-item">
                                <input type="radio" name="cualidad_fisica" value="Potencia" id="cf6">
                                <label for="cf6">💥 Potencia</label>
                            </div>
                            <div class="radio-item">
                                <input type="radio" name="cualidad_fisica" value="Agilidad" id="cf7">
                                <label for="cf7">🏃 Agilidad</label>
                            </div>
                            <div class="radio-item">
                                <input type="radio" name="cualidad_fisica" value="Ninguna de las anteriores" id="cf8">
                                <label for="cf8">❌ Ninguna de las anteriores</label>
                            </div>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">Cualidad coordinativa que más mejoró en 2025</div>
                        <div class="radio-group">
                            <div class="radio-item">
                                <input type="radio" name="cualidad_coordinativa" value="Equilibrio" id="cc1" required>
                                <label for="cc1">⚖️ Equilibrio</label>
                            </div>
                            <div class="radio-item">
                                <input type="radio" name="cualidad_coordinativa" value="Ritmo" id="cc2">
                                <label for="cc2">🎵 Ritmo</label>
                            </div>
                            <div class="radio-item">
                                <input type="radio" name="cualidad_coordinativa" value="Reacción" id="cc3">
                                <label for="cc3">⚡ Reacción</label>
                            </div>
                            <div class="radio-item">
                                <input type="radio" name="cualidad_coordinativa" value="Coordinación Espacio Tiempo" id="cc4">
                                <label for="cc4">🎯 Coordinación Espacio-Tiempo</label>
                            </div>
                            <div class="radio-item">
                                <input type="radio" name="cualidad_coordinativa" value="Orientación" id="cc5">
                                <label for="cc5">🧭 Orientación</label>
                            </div>
                            <div class="radio-item">
                                <input type="radio" name="cualidad_coordinativa" value="Ninguna de las anteriores" id="cc6">
                                <label for="cc6">❌ Ninguna de las anteriores</label>
                            </div>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">¿La práctica deportiva contribuyó a su bienestar?</div>
                        <div class="radio-group">
                            <div class="radio-item">
                                <input type="radio" name="contribucion_bienestar" value="Sí" id="bien1" required>
                                <label for="bien1">✅ Sí</label>
                            </div>
                            <div class="radio-item">
                                <input type="radio" name="contribucion_bienestar" value="No" id="bien2">
                                <label for="bien2">❌ No</label>
                            </div>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">Emoción predominante en su práctica deportiva/cultural</div>
                        <div class="radio-group">
                            <div class="radio-item">
                                <input type="radio" name="emocion" value="Alegría" id="emo1" required>
                                <label for="emo1">😄 Alegría</label>
                            </div>
                            <div class="radio-item">
                                <input type="radio" name="emocion" value="Sorpresa" id="emo2">
                                <label for="emo2">😮 Sorpresa</label>
                            </div>
                            <div class="radio-item">
                                <input type="radio" name="emocion" value="Miedo" id="emo3">
                                <label for="emo3">😨 Miedo</label>
                            </div>
                            <div class="radio-item">
                                <input type="radio" name="emocion" value="Ira" id="emo4">
                                <label for="emo4">😠 Ira</label>
                            </div>
                            <div class="radio-item">
                                <input type="radio" name="emocion" value="Tristeza" id="emo5">
                                <label for="emo5">😢 Tristeza</label>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- SECCIÓN 4: CAMBIOS Y MEJORAS -->
                <div class="form-section" data-section="4">
                    <div class="section-header">
                        <div class="section-icon">🔄</div>
                        <h2 class="section-title">Cambios y Sugerencias</h2>
                        <p class="section-description">
                            Tu opinión es fundamental para mejorar. Ayúdanos a identificar 
                            áreas de oportunidad en nuestros programas.
                        </p>
                    </div>

                    <div class="card">
                        <div class="card-header">¿Considera necesario un cambio de entrenador en su(s) disciplina(s)?</div>
                        <p style="color: #666; font-size: 14px; margin-bottom: 15px;">
                            Seleccione su respuesta solo para las disciplinas en las que participa
                        </p>
                        <div class="trainer-change-table">
                            <div class="table-header">
                                <div>Disciplina</div>
                                <div style="text-align: center;">Sí, cambio</div>
                                <div style="text-align: center;">No, conforme</div>
                            </div>
                            
                            <div class="table-row">
                                <div>Natación</div>
                                <div style="text-align: center;"><input type="radio" name="cambio_natacion" value="Sí"></div>
                                <div style="text-align: center;"><input type="radio" name="cambio_natacion" value="No"></div>
                            </div>
                            
                            <div class="table-row">
                                <div>Baloncesto</div>
                                <div style="text-align: center;"><input type="radio" name="cambio_baloncesto" value="Sí"></div>
                                <div style="text-align: center;"><input type="radio" name="cambio_baloncesto" value="No"></div>
                            </div>
                            
                            <div class="table-row">
                                <div>Yoga y Pilates</div>
                                <div style="text-align: center;"><input type="radio" name="cambio_yoga" value="Sí"></div>
                                <div style="text-align: center;"><input type="radio" name="cambio_yoga" value="No"></div>
                            </div>
                            
                            <div class="table-row">
                                <div>Fútbol</div>
                                <div style="text-align: center;"><input type="radio" name="cambio_futbol" value="Sí"></div>
                                <div style="text-align: center;"><input type="radio" name="cambio_futbol" value="No"></div>
                            </div>
                            
                            <div class="table-row">
                                <div>Volleyball</div>
                                <div style="text-align: center;"><input type="radio" name="cambio_volleyball" value="Sí"></div>
                                <div style="text-align: center;"><input type="radio" name="cambio_volleyball" value="No"></div>
                            </div>
                            
                            <div class="table-row">
                                <div>Fisioterapia</div>
                                <div style="text-align: center;"><input type="radio" name="cambio_fisioterapia" value="Sí"></div>
                                <div style="text-align: center;"><input type="radio" name="cambio_fisioterapia" value="No"></div>
                            </div>
                            
                            <div class="table-row">
                                <div>Tenis de Mesa</div>
                                <div style="text-align: center;"><input type="radio" name="cambio_tenis" value="Sí"></div>
                                <div style="text-align: center;"><input type="radio" name="cambio_tenis" value="No"></div>
                            </div>
                            
                            <div class="table-row">
                                <div>Atletismo</div>
                                <div style="text-align: center;"><input type="radio" name="cambio_atletismo" value="Sí"></div>
                                <div style="text-align: center;"><input type="radio" name="cambio_atletismo" value="No"></div>
                            </div>
                            
                            <div class="table-row">
                                <div>Bolos</div>
                                <div style="text-align: center;"><input type="radio" name="cambio_bolos" value="Sí"></div>
                                <div style="text-align: center;"><input type="radio" name="cambio_bolos" value="No"></div>
                            </div>
                            
                            <div class="table-row">
                                <div>Ajedrez</div>
                                <div style="text-align: center;"><input type="radio" name="cambio_ajedrez" value="Sí"></div>
                                <div style="text-align: center;"><input type="radio" name="cambio_ajedrez" value="No"></div>
                            </div>
                            
                            <div class="table-row">
                                <div>Tejo</div>
                                <div style="text-align: center;"><input type="radio" name="cambio_tejo" value="Sí"></div>
                                <div style="text-align: center;"><input type="radio" name="cambio_tejo" value="No"></div>
                            </div>
                            
                            <div class="table-row">
                                <div>GYM Salomia</div>
                                <div style="text-align: center;"><input type="radio" name="cambio_gym_salomia" value="Sí"></div>
                                <div style="text-align: center;"><input type="radio" name="cambio_gym_salomia" value="No"></div>
                            </div>
                            
                            <div class="table-row">
                                <div>GYM Buga</div>
                                <div style="text-align: center;"><input type="radio" name="cambio_gym_buga" value="Sí"></div>
                                <div style="text-align: center;"><input type="radio" name="cambio_gym_buga" value="No"></div>
                            </div>
                            
                            <div class="table-row">
                                <div>Funcional Tuluá</div>
                                <div style="text-align: center;"><input type="radio" name="cambio_funcional_tulua" value="Sí"></div>
                                <div style="text-align: center;"><input type="radio" name="cambio_funcional_tulua" value="No"></div>
                            </div>
                            
                            <div class="table-row">
                                <div>Funcional Buenaventura</div>
                                <div style="text-align: center;"><input type="radio" name="cambio_funcional_buenaventura" value="Sí"></div>
                                <div style="text-align: center;"><input type="radio" name="cambio_funcional_buenaventura" value="No"></div>
                            </div>
                            
                            <div class="table-row">
                                <div>Teatro</div>
                                <div style="text-align: center;"><input type="radio" name="cambio_teatro" value="Sí"></div>
                                <div style="text-align: center;"><input type="radio" name="cambio_teatro" value="No"></div>
                            </div>
                            
                            <div class="table-row">
                                <div>Baile</div>
                                <div style="text-align: center;"><input type="radio" name="cambio_baile" value="Sí"></div>
                                <div style="text-align: center;"><input type="radio" name="cambio_baile" value="No"></div>
                            </div>
                            
                            <div class="table-row">
                                <div>Canto</div>
                                <div style="text-align: center;"><input type="radio" name="cambio_canto" value="Sí"></div>
                                <div style="text-align: center;"><input type="radio" name="cambio_canto" value="No"></div>
                            </div>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">Calificación general de su experiencia</div>
                        <div class="emoji-scale">
                            <label class="emoji-option">
                                <input type="radio" name="calificacion_general" value="1" required>
                                <div class="emoji-content">
                                    <span class="emoji">😞</span>
                                    <span class="emoji-label">1 - Ínfimo</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="calificacion_general" value="2">
                                <div class="emoji-content">
                                    <span class="emoji">😕</span>
                                    <span class="emoji-label">2 - Malo</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="calificacion_general" value="3">
                                <div class="emoji-content">
                                    <span class="emoji">😐</span>
                                    <span class="emoji-label">3 - Regular</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="calificacion_general" value="4">
                                <div class="emoji-content">
                                    <span class="emoji">😊</span>
                                    <span class="emoji-label">4 - Bueno</span>
                                </div>
                            </label>
                            <label class="emoji-option">
                                <input type="radio" name="calificacion_general" value="5">
                                <div class="emoji-content">
                                    <span class="emoji">😄</span>
                                    <span class="emoji-label">5 - Excelente</span>
                                </div>
                            </label>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">Aspectos que podrían mejorarse en el programa</div>
                        <div class="form-group">
                            <textarea name="mejoras" placeholder="Describa qué aspectos considera que podrían mejorarse..." required></textarea>
                        </div>
                    </div>
                </div>

                <!-- Sección de éxito -->
                <div id="successSection" class="form-section">
                    <div class="section-header">
                        <div class="section-icon">🎉</div>
                        <h2 class="section-title">¡Gracias por tu participación!</h2>
                        <p class="section-description">
                            Tu evaluación ha sido enviada exitosamente. Tus comentarios son muy valiosos 
                            para mejorar nuestros programas de Bienestar al Funcionario.
                        </p>
                    </div>
                    <div class="card" style="text-align: center; padding: 40px;">
                        <div style="font-size: 80px; margin-bottom: 20px;">✅</div>
                        <h3 style="color: #39A900; margin-bottom: 15px;">Encuesta completada</h3>
                        <p style="color: #666; line-height: 1.8;">
                            El equipo de Bienestar al Funcionario revisará cuidadosamente tus respuestas.<br>
                            Estamos comprometidos con la mejora continua de nuestros servicios.
                        </p>
                    </div>
                </div>

                <!-- Mensajes de estado -->
                <div class="success-message" id="successMessage">
                    <h3>✅ ¡Encuesta enviada con éxito!</h3>
                    <p>Gracias por tu participación. Tus respuestas han sido registradas correctamente.</p>
                </div>

                <div class="error-message" id="errorMessage">
                    <h3>❌ Error al enviar la encuesta</h3>
                    <p id="errorText">Por favor, intente nuevamente.</p>
                </div>

                <div class="loading" id="loadingMessage">
                    <div class="spinner"></div>
                    <p>Enviando tu encuesta...</p>
                </div>

                <!-- Botones de navegación -->
                <div class="form-navigation">
                    <button type="button" class="nav-btn btn-prev" id="prevBtn" style="display: none;">
                        ← Anterior
                    </button>
                    <button type="button" class="nav-btn btn-next" id="nextBtn">
                        Siguiente →
                    </button>
                    <button type="submit" class="nav-btn btn-submit" id="submitBtn" style="display: none;">
                        📨 Enviar Evaluación
                    </button>
                </div>
            </form>
        </div>
    </div>

    <script>
        // URL de tu Google Apps Script
        const SCRIPT_URL = 'https://script.google.com/macros/s/AKfycbzenvamZEz9GME0WjDP7sAG_CRnYHx9yybBcu5g-_Av1dqdXQYPg_tipMCs6vvuo_ARBA/exec;

        let currentSection = 1;
        const totalSections = 4;

        // Elementos del DOM
        const sections = document.querySelectorAll('.form-section');
        const steps = document.querySelectorAll('.step');
        const prevBtn = document.getElementById('prevBtn');
        const nextBtn = document.getElementById('nextBtn');
        const submitBtn = document.getElementById('submitBtn');
        const progressLine = document.getElementById('progressLine');

        // Inicialización
        document.addEventListener('DOMContentLoaded', function() {
            setupEmojiListeners();
            setupRadioListeners();
            updateNavigation();
        });

        // Configurar listeners para emojis
        function setupEmojiListeners() {
            document.querySelectorAll('.emoji-option').forEach(option => {
                option.addEventListener('click', function() {
                    const radio = this.querySelector('input[type="radio"]');
                    const name = radio.name;
                    
                    document.querySelectorAll(`input[name="${name}"]`).forEach(input => {
                        input.closest('.emoji-option').classList.remove('selected');
                    });
                    
                    this.classList.add('selected');
                    radio.checked = true;
                });
            });
        }

        // Configurar listeners para radio buttons
        function setupRadioListeners() {
            document.querySelectorAll('.radio-item input[type="radio"]').forEach(radio => {
                radio.addEventListener('change', function() {
                    const name = this.name;
                    
                    document.querySelectorAll(`input[name="${name}"]`).forEach(input => {
                        input.closest('.radio-item').classList.remove('selected');
                    });
                    
                    this.closest('.radio-item').classList.add('selected');
                });
            });
        }

        // Navegación: Siguiente
        nextBtn.addEventListener('click', function() {
            if (validateCurrentSection()) {
                currentSection++;
                showSection(currentSection);
                window.scrollTo({ top: 0, behavior: 'smooth' });
            }
        });

        // Navegación: Anterior
        prevBtn.addEventListener('click', function() {
            currentSection--;
            showSection(currentSection);
            window.scrollTo({ top: 0, behavior: 'smooth' });
        });

        // Mostrar sección específica
        function showSection(sectionNum) {
            sections.forEach(section => {
                section.classList.remove('active');
                if (parseInt(section.dataset.section) === sectionNum) {
                    section.classList.add('active');
                }
            });

            // Actualizar steps
            steps.forEach(step => {
                const stepNum = parseInt(step.dataset.step);
                step.classList.remove('active', 'completed');
                
                if (stepNum === sectionNum) {
                    step.classList.add('active');
                } else if (stepNum < sectionNum) {
                    step.classList.add('completed');
                }
            });

            // Actualizar línea de progreso
            const progress = ((sectionNum - 1) / (totalSections - 1)) * 100;
            progressLine.style.width = progress + '%';

            updateNavigation();
        }

        // Actualizar botones de navegación
        function updateNavigation() {
            // Mostrar/ocultar botón anterior
            if (currentSection === 1) {
                prevBtn.style.display = 'none';
            } else {
                prevBtn.style.display = 'flex';
            }

            // Mostrar botón siguiente o enviar
            if (currentSection === totalSections) {
                nextBtn.style.display = 'none';
                submitBtn.style.display = 'flex';
            } else {
                nextBtn.style.display = 'flex';
                submitBtn.style.display = 'none';
            }
        }

        // Validar sección actual
        function validateCurrentSection() {
            const currentSectionEl = document.querySelector(`.form-section[data-section="${currentSection}"]`);
            const requiredFields = currentSectionEl.querySelectorAll('[required]');
            let isValid = true;
            let firstInvalidField = null;

            requiredFields.forEach(field => {
                if (field.type === 'radio' || field.type === 'checkbox') {
                    const name = field.name;
                    const checked = currentSectionEl.querySelector(`[name="${name}"]:checked`);
                    
                    if (!checked) {
                        isValid = false;
                        if (!firstInvalidField) {
                            firstInvalidField = field.closest('.card');
                        }
                    }
                } else if (field.value.trim() === '') {
                    isValid = false;
                    if (!firstInvalidField) {
                        firstInvalidField = field;
                    }
                    field.style.borderColor = '#FF6B00';
                    setTimeout(() => {
                        field.style.borderColor = '';
                    }, 3000);
                }
            });

            // Validación especial para disciplinas (al menos una)
            if (currentSection === 1) {
                const disciplinas = currentSectionEl.querySelectorAll('input[name="disciplina"]:checked');
                if (disciplinas.length === 0) {
                    alert('Por favor, seleccione al menos una disciplina deportiva o cultural.');
                    return false;
                }
            }

            if (!isValid) {
                alert('Por favor, complete todos los campos obligatorios antes de continuar.');
                if (firstInvalidField) {
                    firstInvalidField.scrollIntoView({ behavior: 'smooth', block: 'center' });
                }
            }

            return isValid;
        }

        // Envío del formulario
        document.getElementById('evaluacionForm').addEventListener('submit', async function(e) {
            e.preventDefault();
            
            if (!validateCurrentSection()) {
                return;
            }

            // Mostrar loading
            document.getElementById('loadingMessage').style.display = 'block';
            submitBtn.disabled = true;
            document.getElementById('successMessage').style.display = 'none';
            document.getElementById('errorMessage').style.display = 'none';

            // Recopilar datos
            const formData = new FormData(this);
            
            // Convertir disciplinas a array
            const disciplinasArray = [];
            formData.getAll('disciplina').forEach(disc => disciplinasArray.push(disc));
            formData.set('disciplina', disciplinasArray.join(', '));

            // Convertir a objeto
            const data = {};
            formData.forEach((value, key) => {
                if (!data[key]) {
                    data[key] = value;
                }
            });

            // Agregar timestamp
            data.timestamp = new Date().toLocaleString('es-CO');

            try {
                // Enviar datos
                await fetch(SCRIPT_URL, {
                    method: 'POST',
                    mode: 'no-cors',
                    headers: {
                        'Content-Type': 'application/json',
                    },
                    body: JSON.stringify(data)
                });

                // Mostrar sección de éxito
                document.getElementById('loadingMessage').style.display = 'none';
                sections.forEach(s => s.classList.remove('active'));
                document.getElementById('successSection').style.display = 'block';
                document.querySelector('.form-navigation').style.display = 'none';
                document.querySelector('.progress-container').style.display = 'none';
                
                window.scrollTo({ top: 0, behavior: 'smooth' });

            } catch (error) {
                console.error('Error:', error);
                document.getElementById('loadingMessage').style.display = 'none';
                document.getElementById('errorMessage').style.display = 'block';
                document.getElementById('errorText').textContent = 'Hubo un problema al enviar la encuesta. Por favor, intente nuevamente.';
                submitBtn.disabled = false;
            }
        });
    </script>
</body>
</html>
