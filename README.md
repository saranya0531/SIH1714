# Create the HTML file with CSS and JavaScript
html_code = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Speech Language Therapy Management</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background-color: #e9ecef;
        }
        .container {
            max-width: 600px;
            margin: auto;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 8px;
            background-color: #ffffff;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        h1, h2 {
            color: #343a40;
        }
        section {
            margin-bottom: 20px;
        }
        input[type="text"], textarea {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            border: 1px solid #ced4da;
            border-radius: 4px;
        }
        button {
            padding: 10px 15px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        button:hover {
            background-color: #0056b3;
        }
        #caseStatus {
            padding: 10px;
            border: 1px solid #ced4da;
            border-radius: 4px;
            background-color: #f8f9fa;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Speech Language Therapy Management System</h1>

        <section>
            <h2>Case Allocation</h2>
            <input type="text" id="patientName" placeholder="Patient Name" />
            <input type="text" id="therapistName" placeholder="Therapist Name" />
            <button onclick="allocateCase()">Allocate Case</button>
        </section>

        <section>
            <h2>Therapy Plan</h2>
            <textarea id="therapyPlan" placeholder="Enter Therapy Plan..."></textarea>
            <button onclick="submitPlan()">Submit Plan</button>
        </section>

        <section>
            <h2>Supervisor Feedback</h2>
            <textarea id="feedback" placeholder="Enter Supervisor Feedback..."></textarea>
            <button onclick="submitFeedback()">Submit Feedback</button>
        </section>

        <section>
            <h2>Progress Reports</h2>
            <textarea id="progressReport" placeholder="Enter Progress Report..."></textarea>
            <button onclick="submitReport()">Submit Report</button>
        </section>

        <h2>Case Status</h2>
        <div id="caseStatus"></div>
    </div>

    <script>
        let caseData = {
            patientName: '',
            therapistName: '',
            therapyPlan: '',
            feedback: '',
            progressReport: ''
        };

        function allocateCase() {
            caseData.patientName = document.getElementById('patientName').value;
            caseData.therapistName = document.getElementById('therapistName').value;
            updateCaseStatus();
            alert('Case allocated to ' + caseData.therapistName + ' for patient ' + caseData.patientName);
        }

        function submitPlan() {
            caseData.therapyPlan = document.getElementById('therapyPlan').value;
            alert('Therapy Plan submitted!');
            updateCaseStatus();
        }

        function submitFeedback() {
            caseData.feedback = document.getElementById('feedback').value;
            alert('Feedback submitted!');
            updateCaseStatus();
        }

        function submitReport() {
            caseData.progressReport = document.getElementById('progressReport').value;
            alert('Progress Report submitted!');
            updateCaseStatus();
        }

        function updateCaseStatus() {
            const caseStatusDiv = document.getElementById('caseStatus');
            caseStatusDiv.innerHTML = `
                <strong>Patient Name:</strong> ${caseData.patientName}<br />
                <strong>Therapist Name:</strong> ${caseData.therapistName}<br />
                <strong>Therapy Plan:</strong> ${caseData.therapyPlan}<br />
                <strong>Feedback:</strong> ${caseData.feedback}<br />
                <strong>Progress Report:</strong> ${caseData.progressReport}<br />
            `;
        }
    </script>
</body>
</html>
"""

# Save the HTML file
with open('index.html', 'w') as f:
    f.write(html_code)

