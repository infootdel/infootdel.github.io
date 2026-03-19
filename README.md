# infootdel.github.io
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Азбука кибербезопасности</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Roboto, 'Helvetica Neue', sans-serif;
        }
        body {
            background: linear-gradient(145deg, #f0f7ff 0%, #e6f0fa 100%);
            min-height: 100vh;
            padding: 2rem 1rem;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            background-color: rgba(255,255,255,0.7);
            backdrop-filter: blur(10px);
            border-radius: 2.5rem;
            box-shadow: 0 20px 40px rgba(0,20,40,0.2);
            padding: 2.5rem 2rem;
            border: 1px solid rgba(255,255,255,0.5);
        }
        h1 {
            font-size: 2.8rem;
            color: #0b3954;
            text-align: center;
            margin-bottom: 0.5rem;
            letter-spacing: -0.5px;
            text-shadow: 2px 2px 0 #c7e3ff;
        }
        .subhead {
            text-align: center;
            color: #2c5f7b;
            font-size: 1.3rem;
            margin-bottom: 2.5rem;
            font-weight: 400;
        }
        section {
            margin-bottom: 3rem;
            background: rgba(255,255,255,0.5);
            border-radius: 2rem;
            padding: 2rem;
            box-shadow: 0 6px 14px rgba(0,30,30,0.1);
        }
        h2 {
            font-size: 2rem;
            color: #0a3142;
            border-left: 8px solid #3b9cbc;
            padding-left: 1.5rem;
            margin-bottom: 1.8rem;
        }
        .cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 1.5rem;
        }
        .card {
            background: white;
            padding: 1.8rem 1.2rem;
            border-radius: 1.8rem;
            box-shadow: 0 10px 20px rgba(0, 30, 50, 0.1);
            transition: 0.2s;
            border: 2px solid transparent;
            cursor: pointer;
        }
        .card:hover {
            transform: translateY(-5px);
            border-color: #4aa3c9;
        }
        .card.active {
            border-color: #f4b740;
            background: #fffbf0;
        }
        .card h3 {
            font-size: 1.6rem;
            color: #0f4b66;
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        .card p {
            color: #1d4e63;
            line-height: 1.5;
        }
        .emoji-icon {
            font-size: 2.4rem;
            margin-bottom: 0.5rem;
        }
        /* Стили для примеров (скрыты по умолчанию) */
        .card-example {
            display: none;
            background: #e5f3ff;
            border-radius: 1.2rem;
            padding: 1rem 1.2rem;
            margin-top: 1.2rem;
            border-left: 4px solid #3b9cbc;
            font-size: 0.95rem;
            color: #023047;
            box-shadow: inset 0 1px 4px rgba(0,0,0,0.05);
        }
        .card.active .card-example {
            display: block;
        }
        /* Тест */
        .quiz-question {
            background: white;
            border-radius: 1.5rem;
            padding: 1.5rem;
            margin-bottom: 1.5rem;
            box-shadow: 0 4px 10px rgba(0,0,0,0.03);
        }
        .quiz-question p {
            font-weight: 600;
            font-size: 1.2rem;
            color: #0e3b4f;
            margin-bottom: 1rem;
        }
        .options {
            display: flex;
            flex-direction: column;
            gap: 0.7rem;
        }
        .options label {
            display: flex;
            align-items: center;
            gap: 0.8rem;
            background: #f2faff;
            padding: 0.7rem 1.2rem;
            border-radius: 2rem;
            cursor: pointer;
            border: 1px solid transparent;
            transition: 0.1s;
            font-size: 1.1rem;
        }
        .options label:hover {
            background: #dff0fc;
            border-color: #6eb4d0;
        }
        input[type="radio"] {
            accent-color: #2b93b9;
            width: 1.2rem;
            height: 1.2rem;
        }
        .quiz-btn, .check-password-btn {
            background: #1b7e9f;
            color: white;
            border: none;
            padding: 1rem 2.5rem;
            font-size: 1.3rem;
            border-radius: 3rem;
            font-weight: 600;
            cursor: pointer;
            box-shadow: 0 8px 0 #0b4b63;
            transition: 0.1s ease;
            margin-top: 1rem;
            border: 1px solid #8ecceb;
        }
        .quiz-btn:active, .check-password-btn:active {
            transform: translateY(5px);
            box-shadow: 0 3px 0 #0b4b63;
        }
        .result-box {
            margin-top: 1.8rem;
            font-size: 1.5rem;
            font-weight: 600;
            padding: 1rem 2rem;
            border-radius: 3rem;
            background: #c1e3f5;
            display: inline-block;
            color: #003952;
        }
        /* Проверка пароля */
        .password-area {
            display: flex;
            flex-wrap: wrap;
            gap: 1.5rem;
            align-items: flex-end;
        }
        .password-input-group {
            flex: 2;
            min-width: 260px;
        }
        .password-input-group label {
            font-size: 1.2rem;
            color: #0b3e55;
            font-weight: 500;
            margin-bottom: 0.3rem;
            display: block;
        }
        .password-wrapper {
            display: flex;
            background: white;
            border-radius: 3rem;
            border: 2px solid #a2cfec;
            overflow: hidden;
        }
        .password-wrapper input {
            flex: 1;
            padding: 1rem 1.5rem;
            font-size: 1.1rem;
            border: none;
            outline: none;
            background: transparent;
        }
        .password-wrapper button {
            background: #e1f0f9;
            border: none;
            padding: 0 1.5rem;
            font-size: 1rem;
            font-weight: 600;
            color: #0a4d66;
            cursor: pointer;
            transition: 0.1s;
            border-left: 2px solid #a2cfec;
        }
        .password-wrapper button:hover {
            background: #c7e3f2;
        }
        .strength-meter {
            margin: 1rem 0 0.3rem;
            height: 0.8rem;
            border-radius: 1rem;
            background: #d9d9d9;
            width: 100%;
            overflow: hidden;
        }
        .strength-fill {
            height: 100%;
            width: 0%;
            background: #f44336;
            border-radius: 1rem;
            transition: 0.2s;
        }
        .strength-text {
            font-weight: 600;
            color: #134a61;
            font-size: 1.1rem;
        }
        .hint {
            color: #28697f;
            font-style: italic;
            margin-top: 0.3rem;
            font-size: 0.95rem;
        }
        footer {
            text-align: center;
            color: #2f6079;
            margin-top: 2rem;
            font-size: 1rem;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>🔐 Безопасный интернет</h1>
        <div class="subhead">Для школьников и их родителей — просто о важном</div>

        <!-- Информационные карточки (кликабельные) -->
        <section>
            <h2>📚 Основные правила (нажми на карточку ↓)</h2>
            <div class="cards" id="rulesCards">
                <div class="card">
                    <div class="emoji-icon">🔒</div>
                    <h3>Пароли</h3>
                    <p>Используй разные сложные пароли для разных сайтов. Длина — не меньше 8 символов, добавляй цифры и спецзнаки.</p>
                    <div class="card-example">
                        ✅ <strong>Пример плохого пароля:</strong> 123456, qwerty, имя ребёнка.<br>
                        ✅ <strong>Хороший пароль:</strong> G3nR@8!pL (заглавные, строчные, цифры, символ).
                    </div>
                </div>
                <div class="card">
                    <div class="emoji-icon">🎣</div>
                    <h3>Фишинг</h3>
                    <p>Не переходи по подозрительным ссылкам из писем и сообщений. Мошенники маскируются под известные сервисы.</p>
                    <div class="card-example">
                        ⚠️ <strong>Пример:</strong> Письмо "Ваш аккаунт заблокирован" со ссылкой vk.com-login.ru — это фишинг. Настоящий адрес — vk.com.
                    </div>
                </div>
                <div class="card">
                    <div class="emoji-icon">📱</div>
                    <h3>Приложения</h3>
                    <p>Скачивай программы только из официальных магазинов (Google Play, App Store). Не открывай файлы от незнакомцев.</p>
                    <div class="card-example">
                        📲 <strong>Пример:</strong> Не скачивай «взломанные» игры с форумов — вместо игры может оказаться вирус, который украдет данные.
                    </div>
                </div>
                <div class="card">
                    <div class="emoji-icon">👀</div>
                    <h3>Приватность</h3>
                    <p>Не выкладывай в открытый доступ адрес, телефон, документы. Настрой, кто видит твои посты.</p>
                    <div class="card-example">
                        🏠 <strong>Пример:</strong> Фото школьного пропуска или авиабилета в сторис — злоумышленники могут использовать данные. И не ставь геометку дома.
                    </div>
                </div>
            </div>
        </section>

        <!-- Тест по кибербезопасности -->
        <section>
            <h2>🧪 Проверь себя: маленький тест</h2>
            <form id="quizForm">
                <div class="quiz-question">
                    <p>1️⃣ Что такое фишинг?</p>
                    <div class="options">
                        <label><input type="radio" name="q1" value="a"> А) Вид спортивной рыбалки</label>
                        <label><input type="radio" name="q1" value="b"> Б) Способ взлома через поддельные сайты и письма</label>
                        <label><input type="radio" name="q1" value="c"> В) Антивирусная программа</label>
                    </div>
                </div>
                <div class="quiz-question">
                    <p>2️⃣ Какой пароль считается самым надёжным?</p>
                    <div class="options">
                        <label><input type="radio" name="q2" value="a"> А) 12345678</label>
                        <label><input type="radio" name="q2" value="b"> Б) Qwerty123</label>
                        <label><input type="radio" name="q2" value="c"> В) P@ssw0rd!9</label>
                        <label><input type="radio" name="q2" value="d"> Г) Дата рождения: 2009</label>
                    </div>
                </div>
                <div class="quiz-question">
                    <p>3️⃣ Пришло письмо от «Сбера» с вложением «Счёт.pdf». Твои действия?</p>
                    <div class="options">
                        <label><input type="radio" name="q3" value="a"> А) Открыть — вдруг важное</label>
                        <label><input type="radio" name="q3" value="b"> Б) Удалить, не открывая, и проверить адрес отправителя</label>
                        <label><input type="radio" name="q3" value="c"> В) Переслать другу, пусть он откроет</label>
                    </div>
                </div>
                <div class="quiz-question">
                    <p>4️⃣ Можно ли использовать один пароль для почты, соцсетей и госуслуг?</p>
                    <div class="options">
                        <label><input type="radio" name="q4" value="a"> А) Да, так проще запомнить</label>
                        <label><input type="radio" name="q4" value="b"> Б) Нет, если взломают один сервис — потеряешь всё</label>
                        <label><input type="radio" name="q4" value="c"> В) Можно, если пароль очень длинный</label>
                    </div>
                </div>
                <button type="button" class="quiz-btn" onclick="checkQuiz()">Узнать результат</button>
            </form>
            <div id="quizResult" class="result-box">👉 Жми кнопку!</div>
        </section>

        <!-- Проверка надёжности пароля -->
        <section>
            <h2>🔑 Оцени свой пароль</h2>
            <div class="password-area">
                <div class="password-input-group">
                    <label for="passwordInput">Введи пароль (не сохраняется)</label>
                    <div class="password-wrapper">
                        <input type="password" id="passwordInput" placeholder="например: MyP@ssw0rd" oninput="checkPasswordStrength()">
                        <button type="button" id="togglePassword">👁️</button>
                    </div>
                    <div class="strength-meter">
                        <div id="strengthFill" class="strength-fill"></div>
                    </div>
                    <div id="strengthText" class="strength-text">✏️ Начни ввод...</div>
                    <div class="hint">Используй заглавные, строчные буквы, цифры и символы. Длина от 8.</div>
                </div>
                <button class="check-password-btn" onclick="checkPasswordStrength()">Проверить надёжность</button>
            </div>
        </section>

        <footer>⚡ Помни: твоя безопасность — в твоих руках! Если что-то непонятно, спроси у родителей.</footer>
    </div>

    <script>
        // --- Интерактивные карточки (клик для показа примера) ---
        document.querySelectorAll('.card').forEach(card => {
            card.addEventListener('click', function(e) {
                // Если кликнули на сам пример, не закрываем (позволяем остаться открытым)
                if (e.target.closest('.card-example')) return;
                // Переключаем класс active
                this.classList.toggle('active');
            });
        });

        // --- ТЕСТ ---
        function checkQuiz() {
            const answers = {
                q1: 'b',
                q2: 'c',
                q3: 'b',
                q4: 'b'
            };
            let score = 0;
            const total = Object.keys(answers).length;

            for (let q in answers) {
                const selected = document.querySelector(`input[name="${q}"]:checked`);
                if (selected && selected.value === answers[q]) {
                    score++;
                }
            }

            const resultDiv = document.getElementById('quizResult');
            if (score === total) {
                resultDiv.innerHTML = '🏆 Отлично! Ты знаток кибербезопасности!';
                resultDiv.style.background = '#b9e6b9';
            } else if (score >= 2) {
                resultDiv.innerHTML = `👍 Неплохо! Правильных ответов: ${score} из ${total}. Повтори правила ещё раз.`;
                resultDiv.style.background = '#ffe68f';
            } else {
                resultDiv.innerHTML = `😟 Ой! Правильных ответов: ${score} из ${total}. Обязательно прочитай раздел с правилами!`;
                resultDiv.style.background = '#fbc0c0';
            }
        }

        // --- ПРОВЕРКА ПАРОЛЯ ---
        function checkPasswordStrength() {
            const password = document.getElementById('passwordInput').value;
            const fill = document.getElementById('strengthFill');
            const text = document.getElementById('strengthText');

            if (password.length === 0) {
                fill.style.width = '0%';
                fill.style.background = '#f44336';
                text.innerHTML = '✏️ Начни ввод...';
                return;
            }

            let strength = 0;
            // Критерии
            if (password.length >= 8) strength++;
            if (/[a-z]/.test(password)) strength++;
            if (/[A-Z]/.test(password)) strength++;
            if (/[0-9]/.test(password)) strength++;
            if (/[^a-zA-Z0-9]/.test(password)) strength++;

            const percent = (strength / 5) * 100;
            fill.style.width = percent + '%';

            if (strength <= 2) {
                fill.style.background = '#f44336';
                text.innerHTML = '🔴 Слабый пароль — легко взломать';
            } else if (strength === 3 || strength === 4) {
                fill.style.background = '#ffb74d';
                text.innerHTML = '🟡 Средний пароль — можно улучшить';
            } else if (strength === 5) {
                fill.style.background = '#4caf50';
                text.innerHTML = '🟢 Отличный надёжный пароль!';
            }
        }

        // --- ПОКАЗ ПАРОЛЯ ---
        document.getElementById('togglePassword').addEventListener('click', function () {
            const input = document.getElementById('passwordInput');
            const type = input.getAttribute('type') === 'password' ? 'text' : 'password';
            input.setAttribute('type', type);
            this.textContent = type === 'password' ? '👁️' : '👁️‍🗨️';
        });
    </script>
</body>
</html>
