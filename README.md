
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Budget Tracker</title>

    <style>
        /* General page styling */
        * {
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            background-color: #f4f7fb;
            color: #263238;
            margin: 0;
            line-height: 1.6;
        }

        .page-header {
            display: flex;
            align-items: center;
            gap: 15px;
            background-color: #2563eb;
            color: white;
            padding: 20px;
        }

        .page-header img {
            border-radius: 50%;
        }

        .page-header h1,
        .page-header p {
            margin: 0;
        }

        main {
            max-width: 1000px;
            margin: 25px auto;
            padding: 0 15px;
        }

        .add-expense-section,
        .expenses-section,
        .help-section,
        .video-section {
            background-color: white;
            padding: 20px;
            margin-bottom: 25px;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
        }

        h2 {
            color: #1d4ed8;
        }

        /* Expense form */
        .add-expense-section form {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .add-expense-section form > input,
        .add-expense-section form > select {
            width: 100%;
            padding: 11px;
            border: 1px solid #cbd5e1;
            border-radius: 5px;
            font-size: 16px;
        }

        .add-expense-section form > label {
            font-weight: bold;
        }

        input:not([type="checkbox"]) {
            background-color: #fff;
        }

        input:focus,
        select:focus {
            outline: 2px solid #2563eb;
            border-color: #2563eb;
        }

        button {
            background-color: #2563eb;
            color: white;
            padding: 12px 18px;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
            margin-top: 10px;
        }

        button:hover {
            background-color: #1d4ed8;
        }

        /* Expense table */
        .table-container {
            width: 100%;
            overflow-x: auto;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 15px;
        }

        th,
        td {
            border: 1px solid #cbd5e1;
            padding: 12px;
            text-align: left;
        }

        thead {
            background-color: #2563eb;
            color: white;
        }

        tbody tr:nth-child(even) {
            background-color: #eaf1ff;
        }

        tbody tr:first-child {
            font-weight: 500;
        }

        tbody tr:hover {
            background-color: #d1fae5;
        }

        .expenses-section td {
            font-size: 15px;
        }

        /* Collapsible instructions */
        summary {
            font-weight: bold;
            cursor: pointer;
            color: #1d4ed8;
        }

        .help-section details p {
            margin-top: 12px;
        }

        /* YouTube video */
        .video-section iframe {
            display: block;
            max-width: 100%;
            border: none;
            border-radius: 6px;
        }

        .video-note {
            font-size: 13px;
            color: #64748b;
        }

        /* Footer */
        footer {
            background-color: #1e293b;
            color: white;
            text-align: center;
            padding: 15px;
        }

        /* Mobile responsiveness */
        @media (max-width: 600px) {
            .page-header {
                padding: 15px;
                align-items: flex-start;
            }

            .page-header h1 {
                font-size: 22px;
            }

            th,
            td {
                padding: 8px;
                font-size: 13px;
            }
        }
    </style>
</head>

<body>

    <!-- Page heading and logo -->
    <header class="page-header">
        <img
            src="https://placehold.co/80x80/2563eb/ffffff?text=BT"
            alt="Budget Tracker logo"
            width="60"
        >

        <div>
            <h1>My Budget Tracker</h1>
            <p>Track your expenses and manage your money wisely.</p>
        </div>
    </header>

    <main>

        <!-- Add Expense Form -->
        <section class="add-expense-section">
            <h2>Add an Expense</h2>

            <form>
                <label for="expense-name">Expense Name:</label>
                <input
                    type="text"
                    id="expense-name"
                    name="expense-name"
                    placeholder="e.g. Groceries"
                    required
                >

                <label for="expense-amount">Amount (KSh):</label>
                <input
                    type="number"
                    id="expense-amount"
                    name="expense-amount"
                    min="0"
                    step="0.01"
                    placeholder="e.g. 500"
                    required
                >

                <label for="expense-category">Category:</label>
                <select
                    id="expense-category"
                    name="expense-category"
                    required
                >
                    <option value="">Choose a category</option>
                    <option value="Food">Food</option>
                    <option value="Transport">Transport</option>
                    <option value="Rent">Rent</option>
                    <option value="Entertainment">Entertainment</option>
                    <option value="Other">Other</option>
                </select>

                <label for="expense-date">Date:</label>
                <input
                    type="date"
                    id="expense-date"
                    name="expense-date"
                    required
                >

                <button type="button" id="add-expense-button">
                    Add Expense
                </button>
            </form>
        </section>

        <!-- Expenses Table -->
        <section class="expenses-section">
            <h2>Your Expenses</h2>

            <div class="table-container">
                <table>
                    <thead>
                        <tr>
                            <th>Name</th>
                            <th>Amount</th>
                            <th>Category</th>
                            <th>Date</th>
                        </tr>
                    </thead>

                    <tbody>
                        <tr>
                            <td>Groceries</td>
                            <td>KSh 1,200</td>
                            <td>Food</td>
                            <td>2026-10-01</td>
                        </tr>

                        <tr>
                            <td>Bus Fare</td>
                            <td>KSh 300</td>
                            <td>Transport</td>
                            <td>2026-10-02</td>
                        </tr>

                        <tr>
                            <td>House Rent</td>
                            <td>KSh 4,000</td>
                            <td>Rent</td>
                            <td>2026-10-03</td>
                        </tr>

                        <tr>
                            <td>Movie Ticket</td>
                            <td>KSh 500</td>
                            <td>Entertainment</td>
                            <td>2026-10-04</td>
                        </tr>

                        <tr>
                            <td>Exercise Book</td>
                            <td>KSh 150</td>
                            <td>Other</td>
                            <td>2026-10-05</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </section>

        <!-- Collapsible instructions -->
        <section class="help-section">
            <details>
                <summary>How to use this tracker</summary>
                <p>
                    Enter the expense name, amount, category, and date.
                    The table shows example expenses. The Add Expense
                    button is not functional yet because JavaScript
                    functionality will be added in a later week.
                </p>
            </details>
        </section>

        <!-- Budgeting video -->
        <section class="video-section">
            <h2>Budgeting Tips</h2>
            <p>Learn useful tips for managing your money.</p>

            <iframe
                width="560"
                height="315"
                src="https://www.youtube.com/embed/VIDEO_ID"
                title="Budgeting tips video"
                frameborder="0"
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                allowfullscreen>
            </iframe>

            <p class="video-note">
                Replace VIDEO_ID with the ID of a budgeting video
                from YouTube.
            </p>
        </section>

    </main>

    <footer>
        <p>&copy; 2026 My Budget Tracker. Manage your money wisely.</p>
    </footer>

</body>
</html>
