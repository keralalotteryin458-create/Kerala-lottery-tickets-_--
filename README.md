<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kerala State Lottery - Official Portal</title>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-dark: #0b0e14;
            --card-bg: #141820;
            --border-color: #232936;
            --accent-gold: #f59e0b;
            --accent-yellow: #fbbf24;
            --whatsapp-green: #25d366;
            --text-white: #ffffff;
            --text-gray: #94a3b8;
        }

        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Plus Jakarta Sans', sans-serif; }
        body { background-color: var(--bg-dark); color: var(--text-white); padding-bottom: 90px; }

        header {
            display: flex; justify-content: space-between; align-items: center;
            padding: 15px 20px; background-color: rgba(11, 14, 20, 0.95);
            border-bottom: 1px solid var(--border-color); position: sticky; top: 0; z-index: 100;
        }

        .logo-box { display: flex; align-items: center; gap: 10px; }
        .logo-icon {
            background: linear-gradient(135deg, var(--accent-gold), var(--accent-yellow));
            color: #000; font-weight: 800; font-size: 20px; width: 40px; height: 40px;
            border-radius: 50%; display: flex; align-items: center; justify-content: center;
        }
        .logo-text h2 { font-size: 15px; font-weight: 800; line-height: 1.1; }
        .logo-text span { font-size: 10px; color: var(--accent-gold); letter-spacing: 1.5px; font-weight: 600; }

        .btn-header-wa {
            background-color: rgba(37, 211, 102, 0.15); color: var(--whatsapp-green);
            border: 1px solid var(--whatsapp-green); padding: 6px 12px; border-radius: 30px;
            font-size: 11px; font-weight: 700; text-decoration: none;
        }

        .container { max-width: 500px; margin: 0 auto; padding: 15px; }
        .badge-live {
            background: rgba(245, 158, 11, 0.15); border: 1px solid var(--accent-gold);
            color: var(--accent-gold); font-size: 11px; font-weight: 700; padding: 4px 12px;
            border-radius: 20px; display: inline-block; margin: 10px auto;
        }

        .hero-title { text-align: center; font-size: 26px; font-weight: 900; margin-bottom: 5px; }
        .hero-title span { color: var(--accent-gold); display: block; }
        .hero-sub { text-align: center; font-size: 12px; color: var(--text-gray); margin-bottom: 20px; }

        .jackpot-circle {
            width: 210px; height: 210px; margin: 0 auto 20px auto; border-radius: 50%;
            border: 3px solid var(--accent-gold); box-shadow: 0 0 25px rgba(245, 158, 11, 0.25);
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            background: radial-gradient(circle, rgba(245,158,11,0.1) 0%, rgba(20,24,32,1) 80%);
        }
        .jackpot-circle h1 { font-size: 36px; font-weight: 900; color: #fff; line-height: 1; }

        .timer-card {
            background: var(--card-bg); border: 1px solid var(--border-color);
            border-radius: 12px; padding: 12px; text-align: center; margin-bottom: 12px;
        }
        .timer-title { font-size: 11px; color: var(--accent-gold); font-weight: 700; margin-bottom: 6px; }
        .timer-digits { display: flex; justify-content: center; gap: 15px; font-weight: 800; }

        .progress-box {
            background: var(--card-bg); border: 1px solid var(--border-color);
            border-radius: 12px; padding: 12px; margin-bottom: 20px;
        }
        .progress-text { font-size: 12px; color: #ef4444; font-weight: 700; margin-bottom: 6px; }
        .progress-bar { height: 6px; background: #232936; border-radius: 10px; overflow: hidden; }
        .progress-fill { width: 78%; height: 100%; background: linear-gradient(90deg, #f59e0b, #ef4444); }

        .section-title { text-align: center; font-size: 18px; font-weight: 800; }
        .section-sub { text-align: center; font-size: 11px; color: var(--text-gray); margin-bottom: 12px; }

        .custom-input-box {
            background: var(--card-bg); border: 1px solid var(--border-color);
            border-radius: 10px; padding: 12px; margin-bottom: 15px;
        }
        .custom-input-box label { font-size: 11px; font-weight: 700; color: var(--accent-gold); display: block; margin-bottom: 6px; }
        .custom-input-group { display: flex; gap: 8px; }
        .custom-input-group input {
            flex: 1; background: #0b0e14; border: 1px solid var(--border-color);
            border-radius: 6px; padding: 10px 12px; color: #fff; font-weight: 700; font-size: 15px; outline: none;
        }
        .btn-add { background: var(--accent-gold); color: #000; border: none; padding: 0 18px; border-radius: 6px; font-weight: 800; font-size: 14px; cursor: pointer; }
        .btn-refresh-all {
            width: 100%; background: rgba(245, 158, 11, 0.12); color: var(--accent-gold);
            border: 1px dashed var(--accent-gold); padding: 10px; border-radius: 8px;
            font-size: 13px; font-weight: 800; cursor: pointer; margin-top: 10px;
        }

        .ticket-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 12px; margin-bottom: 25px; }
        .ticket-card {
            background: var(--card-bg); border: 1px solid var(--border-color);
            border-radius: 12px; padding: 12px 10px; text-align: center; cursor: pointer;
            position: relative; display: flex; flex-direction: column; justify-content: space-between; align-items: center; gap: 6px;
        }
        .ticket-card.selected { border-color: var(--accent-gold); background: rgba(245, 158, 11, 0.12); }
        .ticket-card.selected::after {
            content: "✓"; position: absolute; top: -5px; right: -5px;
            background: var(--accent-gold); color: #000; width: 20px; height: 20px;
            border-radius: 50%; font-size: 11px; font-weight: 900; display: flex; align-items: center; justify-content: center;
        }

        .ticket-name { font-size: 10px; font-weight: 800; color: var(--accent-gold); text-transform: uppercase; }
        .ticket-number { font-size: 16px; font-weight: 800; color: #ffffff; letter-spacing: 1px; }
        .ticket-price {
            background: rgba(245, 158, 11, 0.15); color: var(--accent-yellow);
            border: 1px solid rgba(245, 158, 11, 0.4); padding: 2px 10px; border-radius: 12px; font-size: 11px; font-weight: 800;
        }

        .bottom-bar {
            position: fixed; bottom: 0; left: 0; right: 0; background: #141820;
            border-top: 1px solid var(--border-color); padding: 12px 20px;
            display: flex; align-items: center; justify-content: space-between; z-index: 90;
        }
        .btn-proceed {
            background: linear-gradient(135deg, #f59e0b, #d97706); color: #000;
            border: none; padding: 12px 24px; border-radius: 8px; font-weight: 800; font-size: 14px; cursor: pointer;
        }

        .modal {
            display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0, 0, 0, 0.9); backdrop-filter: blur(5px);
            justify-content: center; align-items: center; z-index: 999; padding: 15px;
        }
        .modal-content {
            background: #141820; border: 1px solid var(--border-color);
            border-radius: 14px; width: 100%; max-width: 420px; padding: 20px; position: relative; max-height: 90vh; overflow-y: auto;
        }
        .close-btn { position: absolute; top: 10px; right: 15px; font-size: 24px; cursor: pointer; color: var(--text-gray); }

        .upi-box {
            background: #0b0e14; border: 1px dashed var(--accent-gold);
            border-radius: 8px; padding: 12px; text-align: center; margin: 12px 0;
            display: flex; align-items: center; justify-content: space-between;
        }
        .btn-copy { background: var(--accent-gold); color: #000; border: none; padding: 6px 12px; border-radius: 5px; font-size: 11px; font-weight: 800; cursor: pointer; }

        .btn-pay-now {
            display: block; width: 100%; background: #25d366; color: #fff;
            text-align: center; padding: 12px; border-radius: 8px; font-weight: 800;
            font-size: 15px; text-decoration: none; margin: 15px 0 10px 0; border: none;
        }

        .utr-field input {
            width: 100%; background: #0b0e14; border: 1px solid var(--accent-gold);
            border-radius: 6px; padding: 12px; color: #fff; font-size: 15px; font-weight: 700; outline: none; margin-top: 5px;
        }
        .btn-wa-submit {
            background: var(--whatsapp-green); color: #fff; border: none;
            width: 100%; padding: 14px; border-radius: 8px; font-size: 14px; font-weight: 800; cursor: pointer; margin-top: 15px;
        }
    </style>
</head>
<body>

    <header>
        <div class="logo-box">
            <div class="logo-icon">K</div>
            <div class="logo-text">
                <h2>KERALA LOTTERY</h2>
                <span>TICKETS</span>
            </div>
        </div>
        <a href="https://wa.me/916287138637" class="btn-header-wa" target="_blank">💬 WhatsApp Chat</a>
    </header>

    <div class="container">
        <div style="text-align: center;">
            <div class="badge-live">● LIVE DRAW</div>
            <h1 class="hero-title">KERALA <span>MEGA JACKPOT</span></h1>
            <p class="hero-sub">Your Luck, Our Trust. Daily Live Draws with Trusted Results</p>
        </div>

        <div class="jackpot-circle">
            <span style="font-size: 24px;">👑</span>
            <p style="font-size: 10px; color: var(--accent-gold); font-weight: 700;">FIRST PRIZE</p>
            <h1>₹25</h1>
            <p style="font-size: 13px; color: #fff; font-weight: 700;">CRORE</p>
            <div style="color: var(--accent-gold); font-size: 12px;">★★★★★</div>
        </div>

        <div class="timer-card">
            <div class="timer-title">⏱ DRAW CLOSES IN</div>
            <div class="timer-digits">
                <div>09 <span style="font-size: 9px; color: var(--text-gray); display: block;">HOURS</span></div>
                <div>47 <span style="font-size: 9px; color: var(--text-gray); display: block;">MINS</span></div>
                <div>24 <span style="font-size: 9px; color: var(--text-gray); display: block;">SECS</span></div>
            </div>
        </div>

        <div class="progress-box">
            <div class="progress-text">🔥 Only 78 VIP Tickets Remaining!</div>
            <div class="progress-bar"><div class="progress-fill"></div></div>
        </div>

        <div class="section-title">SELECT YOUR LUCKY TICKETS</div>
        <div class="section-sub">Tap ticket to select • Individual Rates & Series Included</div>

        <div class="custom-input-box">
            <label>Custom Ticket Number (6-Digits):</label>
            <div class="custom-input-group">
                <input type="text" id="customTicketInput" placeholder="000000" maxlength="6">
                <button type="button" class="btn-add" id="btnAddCustom">+ Add</button>
            </div>
            <button type="button" class="btn-refresh-all" id="btnChangeRandom">🔄 Change Naye Random Numbers</button>
        </div>

        <div class="ticket-grid" id="ticketGrid">
            <!-- ₹200 Bumper Ticket -->
            <div class="ticket-card" data-name="MEGA BUMPER" data-price="200">
                <div class="ticket-name">MEGA BUMPER</div>
                <div class="ticket-number">MB <span class="num-slot">100001</span></div>
                <div class="ticket-price">₹200</div>
            </div>

            <!-- ₹300 Bumper Ticket -->
            <div class="ticket-card" data-name="SUPER BUMPER" data-price="300">
                <div class="ticket-name">SUPER BUMPER</div>
                <div class="ticket-number">SB <span class="num-slot">100002</span></div>
                <div class="ticket-price">₹300</div>
            </div>

            <!-- ₹200 Monsoon Bumper -->
            <div class="ticket-card" data-name="MONSOON BUMPER" data-price="200">
                <div class="ticket-name">MONSOON BUMPER</div>
                <div class="ticket-number">BR <span class="num-slot">100003</span></div>
                <div class="ticket-price">₹200</div>
            </div>

            <!-- ₹300 Xmas Bumper -->
            <div class="ticket-card" data-name="XMAS BUMPER" data-price="300">
                <div class="ticket-name">XMAS BUMPER</div>
                <div class="ticket-number">XB <span class="num-slot">100004</span></div>
                <div class="ticket-price">₹300</div>
            </div>

            <!-- Regular Daily Tickets -->
            <div class="ticket-card" data-name="WIN-WIN (W-750)" data-price="40">
                <div class="ticket-name">WIN-WIN (W-750)</div>
                <div class="ticket-number">WA <span class="num-slot">100005</span></div>
                <div class="ticket-price">₹40</div>
            </div>
            
            <div class="ticket-card" data-name="NIRMAL (NR-380)" data-price="50">
                <div class="ticket-name">NIRMAL (NR-380)</div>
                <div class="ticket-number">NR <span class="num-slot">100006</span></div>
                <div class="ticket-price">₹50</div>
            </div>
        </div>
    </div>

    <div class="bottom-bar">
        <div>
            <p style="font-size: 10px; color: var(--text-gray);"><span id="ticketCountText">0</span> TICKETS SELECTED</p>
            <h3 id="totalAmountText" style="font-size: 16px; color: var(--accent-gold);">TOTAL: ₹0</h3>
        </div>
        <button type="button" class="btn-proceed" id="btnProceed">PROCEED TO PAY</button>
    </div>

    <div id="paymentModal" class="modal">
        <div class="modal-content">
            <span class="close-btn" id="btnCloseModal">&times;</span>
            <div style="font-size: 16px; font-weight: 800; color: var(--accent-gold); text-align: center;">MAKE UPI PAYMENT</div>

            <div class="upi-box">
                <div style="text-align: left;">
                    <span style="font-size: 9px; color: var(--text-gray); display: block;">UPI ID:</span>
                    <span id="upiIdText" style="font-size: 13px; font-weight: 800; color: #fff;">keralalotteryin41254@axl</span>
                </div>
                <button type="button" class="btn-copy" id="btnCopyUpi">Copy ID</button>
            </div>

            <a id="payDirectBtn" href="#" class="btn-pay-now">⚡ PAY NOW (OPEN UPI APP)</a>

            <div style="text-align: center; margin: 10px 0;">
                <p style="font-size: 10px; color: var(--text-gray); margin-bottom: 5px;">OR SCAN QR CODE:</p>
                <img id="qrCodeImg" src="" alt="Payment QR" style="width: 160px; height: 160px; background: #fff; padding: 5px; border-radius: 8px;">
            </div>

            <div class="utr-field">
                <label style="font-size: 11px; color: var(--accent-gold); font-weight: 700;">ENTER 12-DIGIT UTR / REFERENCE NO:*</label>
                <input type="text" id="utrInput" placeholder="e.g. 423456789012" maxlength="12">
            </div>

            <button type="button" class="btn-wa-submit" id="btnWaSubmit">📲 Confirm Payment on WhatsApp</button>
        </div>
    </div>

    <script>
        const UPI_ID = "keralalotteryin41254@axl";
        const WHATSAPP_NUMBER = "916287138637";

        function generateRandom6Digit() {
            return Math.floor(100000 + Math.random() * 900000).toString();
        }

        function updateAllRandomNumbers() {
            const slots = document.querySelectorAll('.num-slot');
            slots.forEach(slot => {
                slot.textContent = generateRandom6Digit();
            });
        }

        function calculateTotal() {
            const selectedCards = document.querySelectorAll('.ticket-card.selected');
            let total = 0;
            selectedCards.forEach(card => {
                total += parseInt(card.getAttribute('data-price') || 0);
            });
            document.getElementById('ticketCountText').textContent = selectedCards.length;
            document.getElementById('totalAmountText').textContent = 'TOTAL: ₹' + total;
            return total;
        }

        document.addEventListener('DOMContentLoaded', () => {
            updateAllRandomNumbers();

            document.getElementById('btnChangeRandom').addEventListener('click', () => {
                updateAllRandomNumbers();
            });

            document.getElementById('ticketGrid').addEventListener('click', (e) => {
                const card = e.target.closest('.ticket-card');
                if (card) {
                    card.classList.toggle('selected');
                    calculateTotal();
                }
            });

            document.getElementById('btnAddCustom').addEventListener('click', () => {
                const input = document.getElementById('customTicketInput');
                const val = input.value.replace(/[^0-9]/g, '');
                if (val.length !== 6) {
                    alert('Kripya 6-digit number hi daalein!');
                    return;
                }

                const grid = document.getElementById('ticketGrid');
                const newCard = document.createElement('div');
                newCard.className = 'ticket-card selected';
                newCard.setAttribute('data-name', 'CUSTOM SELECTION');
                newCard.setAttribute('data-price', '50');

                newCard.innerHTML = `
                    <div class="ticket-name">CUSTOM SELECTION</div>
                    <div class="ticket-number">KL <span class="num-slot">${val}</span></div>
                    <div class="ticket-price">₹50</div>
                `;

                grid.prepend(newCard);
                input.value = '';
                calculateTotal();
            });

            document.getElementById('btnCopyUpi').addEventListener('click', () => {
                navigator.clipboard.writeText(UPI_ID).then(() => {
                    alert('UPI ID Copied: ' + UPI_ID);
                }).catch(() => {
                    alert('UPI ID: ' + UPI_ID);
                });
            });

            document.getElementById('btnProceed').addEventListener('click', () => {
                const total = calculateTotal();
                if (total === 0) {
                    alert('Kripya kam se kam 1 ticket select karein!');
                    return;
                }

                const upiURI = `upi://pay?pa=${UPI_ID}&pn=KeralaLottery&am=${total}&cu=INR`;
                document.getElementById('payDirectBtn').href = upiURI;
                document.getElementById('qrCodeImg').src = `https://api.qrserver.com/v1/create-qr-code/?size=250x250&data=${encodeURIComponent(upiURI)}`;
                document.getElementById('paymentModal').style.display = 'flex';
            });

            document.getElementById('btnCloseModal').addEventListener('click', () => {
                document.getElementById('paymentModal').style.display = 'none';
            });

            document.getElementById('btnWaSubmit').addEventListener('click', () => {
                const utr = document.getElementById('utrInput').value.replace(/[^0-9]/g, '');
                if (utr.length !== 12) {
                    alert('12-digit valid UTR / Ref number enter karein!');
                    return;
                }

                const selectedCards = document.querySelectorAll('.ticket-card.selected');
                let total = 0;
                let msg = "*🎟️ KERALA LOTTERY BOOKING 🎟️*\n\n";

                selectedCards.forEach((card, index) => {
                    const name = card.getAttribute('data-name');
                    const num = card.querySelector('.ticket-number').textContent;
                    const price = parseInt(card.getAttribute('data-price') || 0);
                    total += price;
                    msg += `${index + 1}. ${name} - ${num} (₹${price})\n`;
                });

                msg += `\n*Total Paid:* ₹${total}\n`;
                msg += `*UPI ID:* ${UPI_ID}\n`;
                msg += `*UTR / Ref No:* ${utr}\n\n`;
                msg += "Payment successfully done. Please send my tickets.";

                window.open(`https://api.whatsapp.com/send?phone=${WHATSAPP_NUMBER}&text=${encodeURIComponent(msg)}`, '_blank');
            });
        });
    </script>
</body>
</html>
