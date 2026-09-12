    }
<!DOCTYPE html>
<html>
<head>
    <title>Metal Matrimony Quotation Tool</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            background: #f2f2f2;
            margin: 0;
            padding: 20px;
        }

        .container {
            max-width: 600px;
            margin: auto;
            background: white;
            padding: 25px;
            border-radius: 15px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.15);
        }

        .logo {
            display: block;
            width: 120px;
            max-width: 60%;
            margin: 0 auto 15px;
        }

        h1 {
            text-align: center;
            margin-bottom: 5px;
        }

        .tagline {
            text-align: center;
            color: #777;
            margin-bottom: 25px;
        }

        label {
            font-weight: bold;
            display: block;
            margin-top: 15px;
        }

        input, select {
            width: 100%;
            padding: 12px;
            margin-top: 6px;
            box-sizing: border-box;
            border: 1px solid #ccc;
            border-radius: 8px;
            font-size: 16px;
        }

        button {
            width: 100%;
            padding: 14px;
            margin-top: 20px;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
        }

        .calculate {
            background: #111;
            color: white;
        }

        .whatsapp {
            background: #25D366;
            color: white;
        }

        #quotation {
            display: none;
            margin-top: 25px;
            padding: 20px;
            border: 2px solid #111;
            border-radius: 10px;
        }

        .total {
            font-size: 24px;
            font-weight: bold;
            text-align: center;
            margin-top: 20px;
        }

        .footer {
            text-align: center;
            margin-top: 25px;
            font-size: 13px;
            color: #777;
        }
    </style>
</head>

<body>

<div class="container">

    <!-- METAL MATRIMONY LOGO -->
    <img
        class="logo"
        src="file_00000000fdf081f4ac4e1833d9dc2eb1.png"
        alt="Metal Matrimony Logo"
    >

    <h1>METAL MATRIMONY</h1>

    <div class="tagline">
        Quality is my priority
    </div>

    <label>Client Name</label>
    <input type="text" id="client" placeholder="Enter client name">

    <label>Project Type</label>
    <select id="project">
        <option>Gate</option>
        <option>Handrail</option>
        <option>Metal Table</option>
        <option>Shelves</option>
        <option>Shop Counter</option>
        <option>Office Structure</option>
        <option>Other</option>
    </select>

    <label>Material Cost (KSh)</label>
    <input type="number" id="material" placeholder="0">

    <label>Labour Cost (KSh)</label>
    <input type="number" id="labour" placeholder="0">

    <label>Transport Cost (KSh)</label>
    <input type="number" id="transport" placeholder="0">

    <label>Other Costs (KSh)</label>
    <input type="number" id="other" placeholder="0">

    <label>Profit (%)</label>
    <input type="number" id="profit" value="20">

    <button class="calculate" onclick="generateQuotation()">
        GENERATE QUOTATION
    </button>

    <div id="quotation">

        <h2>QUOTATION</h2>

        <p><strong>Metal Matrimony</strong></p>

        <p>Client: <span id="qClient"></span></p>
        <p>Project: <span id="qProject"></span></p>

        <hr>

        <p>Material: KSh <span id="qMaterial"></span></p>
        <p>Labour: KSh <span id="qLabour"></span></p>
        <p>Transport: KSh <span id="qTransport"></span></p>
        <p>Other costs: KSh <span id="qOther"></span></p>

        <p>Profit: <span id="qProfit"></span>%</p>

        <hr>

        <div class="total">
            TOTAL: KSh <span id="qTotal"></span>
        </div>

        <button class="whatsapp" onclick="sendWhatsApp()">
            SEND QUOTATION ON WHATSAPP
        </button>

    </div>

    <div class="footer">
        Metal Matrimony — Quality is my priority
    </div>

</div>

<script>

function generateQuotation() {

    let client =
        document.getElementById("client").value;

    let project =
        document.getElementById("project").value;

    let material =
        Number(document.getElementById("material").value) || 0;

    let labour =
        Number(document.getElementById("labour").value) || 0;

    let transport =
        Number(document.getElementById("transport").value) || 0;

    let other =
        Number(document.getElementById("other").value) || 0;

    let profit =
        Number(document.getElementById("profit").value) || 0;

    let cost =
        material + labour + transport + other;

    let total =
        cost + (cost * profit / 100);

    document.getElementById("qClient").innerText =
        client || "Client";

    document.getElementById("qProject").innerText =
        project;

    document.getElementById("qMaterial").innerText =
        material.toLocaleString();

    document.getElementById("qLabour").innerText =
        labour.toLocaleString();

    document.getElementById("qTransport").innerText =
        transport.toLocaleString();

    document.getElementById("qOther").innerText =
        other.toLocaleString();

    document.getElementById("qProfit").innerText =
        profit;

    document.getElementById("qTotal").innerText =
        total.toLocaleString(undefined, {
            minimumFractionDigits: 2,
            maximumFractionDigits: 2
        });

    document.getElementById("quotation").style.display =
        "block";
}


function sendWhatsApp() {

    let client =
        document.getElementById("qClient").innerText;

    let project =
        document.getElementById("qProject").innerText;

    let total =
        document.getElementById("qTotal").innerText;

    let message =
        "METAL MATRIMONY\n\n" +
        "QUOTATION\n" +
        "Client: " + client + "\n" +
        "Project: " + project + "\n" +
        "Total: KSh " + total + "\n\n" +
        "Quality is my priority.";

    let whatsappURL =
        "https://wa.me/?text=" +
        encodeURIComponent(message);

    window.open(whatsappURL, "_blank");
}

</script>

</body>
</html>
    #quotation {
                <p>Transport: KSh <span id="qTransport"></span></p>
        <p>Other costs: KSh <span id="qOther"></span></p>

        <p>Profit: <span id="qProfit"></span>%</p>

        <hr>

        <div class="total">
            TOTAL: KSh <span id="qTotal"></span>
        </div>

        <button class="whatsapp" onclick="sendWhatsApp()">
            SEND QUOTATION ON WHATSAPP
        </button>

    </div>

    <div class="footer">
        Metal Matrimony — Quality is my priority
    </div>


function sendWhatsApp() {

    let client = document.getElementById("qClient").innerText;
    let project = document.getElementById("qProject").innerText;
    let total = document.getElementById("qTotal").innerText;

    let message =
        "METAL MATRIMONY%0A%0A" +
        "QUOTATION%0A" +
        "Client: " + client + "%0A" +
        "Project: " + project + "%0A" +
        "Total: KSh " + total + "%0A%0A" +
        "Quality is my priority.";

    window.open(
        "https://wa.me/?text=" + message,
        "_blank"
    );
}

</script>

</body>
</html>
