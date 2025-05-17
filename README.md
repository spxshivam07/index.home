<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Shayari Blog - Share and read beautiful Hindi shayari about love, emotions, and life. Add your own shayari and explore the world of poetry.">
    <meta name="keywords" content="hindi shayari, love shayari, shayari blog, poetry, emotional shayari, add shayari">
    <meta name="author" content="Your Name">
    <meta name="robots" content="index, follow">
    <title>Shayari Blog - Hindi Shayari and Poetry</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            background-color: #f0f4f8;
            font-family: Arial, sans-serif;
            line-height: 1.6;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }
        header {
            background-color: #2c3e50;
            color: white;
            text-align: center;
            padding: 20px;
            width: 100%;
        }
        header h1 {
            font-family: 'Great Vibes', cursive;
            font-size: 3em;
        }
        nav {
            background-color: #34495e;
            padding: 10px 0;
            width: 100%;
            border-top: 2px solid #ecf0f1;
            border-bottom: 2px solid #ecf0f1;
        }
        nav ul {
            list-style: none;
            text-align: center;
        }
        nav ul li {
            display: inline-block;
            margin: 0 15px;
        }
        nav ul li button {
            background-color: #7f8c8d;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
        }
        nav ul li button:hover {
            background-color: #95a5a6;
        }
        .intro-section {
            max-width: 800px;
            margin: 30px auto;
            text-align: center;
        }
        .intro-section p {
            font-family: 'Dancing Script', cursive;
            font-size: 1.5em;
            color: #2c3e50;
            margin-bottom: 30px;
        }
        .shayari-form-section {
            max-width: 800px;
            margin: 20px auto;
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            text-align: center;
            display: none; /* Initially hidden */
        }
        .shayari-form-section h2 {
            font-family: 'Great Vibes', cursive;
            color: #2c3e50;
            font-size: 2em;
            margin-bottom: 20px;
        }
        .shayari-form-section form {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .shayari-form-section textarea {
            width: 100%;
            max-width: 600px;
            height: 100px;
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-family: "Montserrat", sans-serif;
            font-size: 1em;
        }
        .shayari-form-section .button-group {
            display: flex;
            gap: 10px;
        }
        .shayari-form-section button {
            background-color: #27ae60;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1em;
        }
        .shayari-form-section button:hover {
            background-color: #219653;
        }
        .shayari-form-section button.post-btn {
            background-color: #e67e22;
        }
        .shayari-form-section button.post-btn:hover {
            background-color: #d35400;
        }
        .posted-shayari-list {
            max-width: 800px;
            margin: 20px auto;
            padding: 0 20px;
            display: none; /* Initially hidden for non-admins */
        }
        .posted-shayari-item {
            background-color: white;
            padding: 20px;
            margin-bottom: 20px;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            position: relative;
        }
        .posted-shayari-item p {
            font-family: "Montserrat", sans-serif;
            font-weight: bold;
            color: #2c3e50;
            font-size: 1.1em;
        }
        .posted-shayari-item .date {
            color: #7f8c8d;
            font-size: 0.9em;
            margin-top: 10px;
        }
        .posted-shayari-item .action-buttons {
            position: absolute;
            top: 10px;
            right: 10px;
            display: flex;
            gap: 5px;
        }
        .edit-btn, .delete-btn {
            color: white;
            border: none;
            padding: 5px 10px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 0.9em;
        }
        .edit-btn {
            background-color: #2980b9;
        }
        .edit-btn:hover {
            background-color: #2471a3;
        }
        .delete-btn {
            background-color: #c0392b;
        }
        .delete-btn:hover {
            background-color: #a93226;
        }
        .posted-shayari-list h3 {
            font-family: 'Great Vibes', cursive;
            color: #2c3e50;
            font-size: 1.8em;
            text-align: center;
            margin-bottom: 20px;
        }
        .more-shayari-section {
            max-width: 800px;
            margin: 20px auto;
            text-align: center;
        }
        .more-shayari-section button {
            background-color: #8e44ad;
            color: white;
            border: none;
            padding: 15px 30px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1.2em;
            font-family: 'Montserrat', sans-serif;
        }
        .more-shayari-section button:hover {
            background-color: #7d3c98;
        }
        footer {
            text-align: center;
            padding: 20px;
            border-top: 2px solid #2c3e50;
            margin-top: auto;
            color: #7f8c8d;
        }
        /* Custom Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            justify-content: center;
            align-items: center;
        }
        .modal-content {
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
            text-align: center;
            width: 300px;
        }
        .modal-content h3 {
            font-family: 'Great Vibes', cursive;
            color: #2c3e50;
            font-size: 1.8em;
            margin-bottom: 15px;
        }
        .modal-content input {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-family: "Montserrat", sans-serif;
            font-size: 1em;
        }
        .modal-content button {
            width: 100%;
            padding: 10px;
            margin: 5px 0;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1em;
            font-family: 'Montserrat', sans-serif;
        }
        .modal-content .confirm-btn {
            background-color: #27ae60;
            color: white;
        }
        .modal-content .confirm-btn:hover {
            background-color: #219653;
        }
        .modal-content .skip-btn {
            background-color: #e74c3c;
            color: white;
        }
        .modal-content .skip-btn:hover {
            background-color: #c0392b;
        }
        @media (max-width: 600px) {
            header h1 {
                font-size: 2em;
            }
            nav ul li {
                display: block;
                margin: 10px 0;
            }
            .intro-section p {
                font-size: 1.2em;
            }
            .shayari-form-section {
                padding: 20px;
            }
            .shayari-form-section h2 {
                font-size: 1.5em;
            }
            .shayari-form-section textarea {
                width: 90%;
            }
            .modal-content {
                width: 90%;
            }
        }
    </style>
</head>
<body>
    <!-- Password Modal -->
    <div class="modal" id="passwordModal">
        <div class="modal-content">
            <h3>Admin Access</h3>
            <input type="password" id="passwordInput" placeholder="Enter password">
            <button class="confirm-btn" onclick="checkPassword()">Confirm Password</button>
            <button class="skip-btn" onclick="skipPassword()">Skip</button>
        </div>
    </div>

    <header>
        <h1>Shayari Blog</h1>
    </header>

    <nav>
        <ul>
            <li><button onclick="window.location.href='index.html'">Home</button></li>
            <li><button onclick="window.location.href='shayari.html'">More Shayari</button></li>
            <li><button onclick="window.location.href='#'">About</button></li>
            <li><button onclick="window.location.href='#'">Contact</button></li>
        </ul>
    </nav>

    <div class="intro-section">
        <p>Dil ke ehsaas ko shayari mein bayaan karo,<br>Har lafz se pyar ka izhaar karo...</p>
    </div>

    <div class="shayari-form-section" id="shayariFormSection">
        <h2>Add Your Shayari</h2>
        <form id="shayariForm">
            <textarea id="shayariInput" placeholder="Apni shayari yahan likhein..." required></textarea>
            <div class="button-group">
                <button type="submit">Add Shayari</button>
                <button type="button" class="post-btn" onclick="postShayari()">Post</button>
            </div>
        </form>
    </div>

    <div class="posted-shayari-list" id="postedShayariList">
        <h3>Posted Shayari</h3>
        <!-- Yahan posted shayari add hogi -->
    </div>

    <div class="more-shayari-section">
        <button onclick="window.location.href='shayari.html'">More Shayari</button>
    </div>

    <footer>
        <!-- Footer khali rakha hai -->
    </footer>

    <script>
        // Password authentication
        const correctPassword = "manasanu05";
        let isAdmin = false;

        // Show modal on page load
        window.onload = function() {
            document.getElementById('passwordModal').style.display = 'flex';
        };

        // Check password
        function checkPassword() {
            const userPassword = document.getElementById('passwordInput').value;
            if (userPassword === correctPassword) {
                isAdmin = true;
                document.getElementById('passwordModal').style.display = 'none';
                document.getElementById('shayariFormSection').style.display = 'block';
                document.getElementById('postedShayariList').style.display = 'block';
                loadShayariFromStorage();
            } else {
                alert("Incorrect password! Please try again or skip.");
                document.getElementById('passwordInput').value = '';
            }
        }

        // Skip password
        function skipPassword() {
            document.getElementById('passwordModal').style.display = 'none';
        }

        // Form submit hone par shayari add karne ka function (only for admin)
        document.getElementById('shayariForm').addEventListener('submit', function(e) {
            e.preventDefault();
            postShayari();
        });

        // Post button ke liye function
        function postShayari(editId = null) {
            if (!isAdmin) return;

            const shayariText = document.getElementById('shayariInput').value.trim();
            if (!shayariText) return;

            // Current date and time (May 17, 2025, 09:35 AM IST)
            const now = new Date('2025-05-17T09:35:00+05:30');
            const dateString = now.toLocaleDateString('en-US', {
                year: 'numeric',
                month: 'long',
                day: 'numeric',
                hour: 'numeric',
                minute: 'numeric',
                hour12: true
            });

            const shayariObj = {
                text: shayariText,
                date: dateString,
                id: editId || Date.now()
            };

            saveShayariToStorage(shayariObj);

            if (editId) {
                const existingShayari = document.querySelector(`[data-id="${editId}"]`);
                if (existingShayari) existingShayari.remove();
            }

            addShayariToDOM(shayariObj);

            document.getElementById('shayariInput').value = '';
            document.getElementById('shayariForm').onsubmit = function(e) {
                e.preventDefault();
                postShayari();
            };
        }

        // Shayari ko DOM mein add karne ka function
        function addShayariToDOM(shayariObj) {
            const shayariItem = document.createElement('div');
            shayariItem.classList.add('posted-shayari-item');
            shayariItem.dataset.id = shayariObj.id;
            shayariItem.innerHTML = `
                <p>${shayariObj.text.replace(/\n/g, '<br>')}</p>
                <div class="date">Posted on ${shayariObj.date}</div>
                <div class="action-buttons">
                    <button class="edit-btn" onclick="editShayari(this)">Edit</button>
                    <button class="delete-btn" onclick="deleteShayari(this)">Delete</button>
                </div>
            `;

            const postedShayariList = document.getElementById('postedShayariList');
            postedShayariList.insertBefore(shayariItem, postedShayariList.firstChild.nextSibling);
        }

        // Shayari ko localStorage mein save karne ka function
        function saveShayariToStorage(shayariObj) {
            let shayariData = JSON.parse(localStorage.getItem('shayariData')) || [];
            shayariData = shayariData.filter(shayari => shayari.id != shayariObj.id);
            shayariData.push(shayariObj);
            localStorage.setItem('shayariData', JSON.stringify(shayariData));
        }

        // localStorage se shayari load karne ka function
        function loadShayariFromStorage() {
            if (!isAdmin) return;
            const shayariData = JSON.parse(localStorage.getItem('shayariData')) || [];
            shayariData.forEach(shayariObj => {
                addShayariToDOM(shayariObj);
            });
        }

        // Shayari edit karne ka function
        function editShayari(button) {
            if (!isAdmin) return;
            const shayariItem = button.parentElement.parentElement;
            const shayariText = shayariItem.querySelector('p').innerText;
            document.getElementById('shayariInput').value = shayariText;

            document.getElementById('shayariForm').onsubmit = function(e) {
                e.preventDefault();
                postShayari(shayariItem.dataset.id);
            };
        }

        // Shayari delete karne ka function
        function deleteShayari(button) {
            if (!isAdmin) return;
            const shayariItem = button.parentElement.parentElement;
            removeShayariFromStorage(shayariItem.dataset.id);
            shayariItem.remove();
        }

        // localStorage se shayari hatao
        function removeShayariFromStorage(id) {
            let shayariData = JSON.parse(localStorage.getItem('shayariData')) || [];
            shayariData = shayariData.filter(shayari => shayari.id != id);
            localStorage.setItem('shayariData', JSON.stringify(shayariData));
        }
    </script>
</body>
</html>
