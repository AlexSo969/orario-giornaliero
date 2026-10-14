<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Orario</title>
    <style>
        body { font-family: sans-serif; text-align: center; padding: 50px 20px; background-color: #f4f7f6; }
        .card { background: white; padding: 30px; border-radius: 12px; max-width: 400px; margin: 0 auto; box-shadow: 0 4px 10px rgba(0,0,0,0.1); }
        h1 { color: #0066cc; }
        .orario { font-size: 2rem; font-weight: bold; color: #2ecc71; margin: 20px 0; }
    </style>
</head>
<body>
<div class="card">
    <h1>Orario di Oggi</h1>
    <div id="visualizza-data" style="color:#666;"></div>
    <div class="orario" id="visualizza-orario">Verifica in corso...</div>
</div>
<script>
    const orari = {
        '2026-10-14': '09:00 - 13:00 / 15:00 - 19:30',
        '2026-10-15': '09:00 - 13:00 / 15:00 - 19:30',
        '2026-10-16': '09:00 - 13:00 / 15:00 - 19:30',
        '2026-10-17': '09:00 - 13:00',
        '2026-10-18': 'Chiuso'
    };
    const oggi = new Date();
    const dataChiave = oggi.getFullYear() + '-' + String(oggi.getMonth() + 1).padStart(2, '0') + '-' + String(oggi.getDate()).padStart(2, '0');
    document.getElementById('visualizza-data').innerText = oggi.toLocaleDateString('it-IT', { weekday: 'long', day: 'numeric', month: 'long' });
    document.getElementById('visualizza-orario').innerText = orari[dataChiave] || 'Orario non inserito';
</script>
</body>
</html>
