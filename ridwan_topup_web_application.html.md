```md
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ridwan topup - Store Top Up Game & Digital</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap');
        body { font-family: 'Plus Jakarta Sans', sans-serif; }
        .card-select { @apply border-2 border-indigo-500 bg-indigo-950/40 text-white shadow-lg shadow-indigo-500/20 scale-[1.02]; }
        .card-unselect { @apply border border-slate-800 bg-slate-900 text-slate-300 hover:border-slate-700 hover:bg-slate-850; }
        .game-card-select { @apply border-2 border-indigo-500 bg-indigo-950/40 shadow-xl shadow-indigo-500/20 scale-105; }
        .game-card-unselect { @apply border border-slate-800/80 bg-slate-900 hover:border-indigo-500/50 hover:scale-[1.02]; }
    </style>
</head>
<body class="bg-slate-950 text-slate-100 min-h-screen pb-20">

    <!-- Navbar -->
    <header class="bg-slate-900/90 backdrop-blur-md border-b border-slate-800 sticky top-0 z-30">
        <div class="max-w-6xl mx-auto px-4 py-3 flex justify-between items-center">
            <div class="flex items-center gap-3 cursor-pointer" onclick="resetForm()">
                <div class="bg-gradient-to-tr from-indigo-600 via-indigo-500 to-violet-500 p-2.5 rounded-2xl text-white shadow-lg shadow-indigo-500/30">
                    <i data-lucide="gamepad-2" class="w-6 h-6"></i>
                </div>
                <div>
                    <h1 class="text-xl font-extrabold tracking-tight bg-gradient-to-r from-white via-indigo-100 to-indigo-400 bg-clip-text text-transparent">Ridwan topup</h1>
                    <p class="text-[10px] text-slate-400 font-medium">Layanan Top Up Game Fast & Reliable</p>
                </div>
            </div>

            <div class="flex items-center gap-3">
                <span class="inline-flex items-center gap-1.5 text-xs font-semibold px-3 py-1.5 rounded-full bg-emerald-500/10 text-emerald-400 border border-emerald-500/20">
                    <span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></span>
                    <span class="hidden sm:inline">Sistem Otomatis 24/7</span>
                    <span class="sm:hidden">Online</span>
                </span>
            </div>
        </div>
    </header>

    <!-- Main Container -->
    <main class="max-w-6xl mx-auto px-4 py-6">

        <!-- Banner Promo -->
        <div class="bg-gradient-to-r from-indigo-950 via-slate-900 to-slate-950 border border-indigo-500/30 rounded-3xl p-6 mb-8 relative overflow-hidden shadow-2xl">
            <div class="absolute -right-10 -bottom-10 w-72 h-72 bg-indigo-600/15 rounded-full blur-3xl pointer-events-none"></div>
            <div class="relative z-10 max-w-2xl">
                <span class="bg-indigo-500/20 text-indigo-300 text-xs font-bold px-3 py-1 rounded-full uppercase tracking-wider border border-indigo-500/30 mb-3 inline-block">Official Store</span>
                <h2 class="text-2xl sm:text-3xl font-extrabold text-white mb-2 leading-tight">Top Up Game Favoritmu di Ridwan topup</h2>
                <p class="text-xs sm:text-sm text-slate-300">Nikmati layanan isi ulang voucher & diamond tercepat, termurah, dan terpercaya dengan berbagai pilihan metode pembayaran.</p>
            </div>
        </div>

        <!-- STEP 1: PILIH GAME -->
        <section class="mb-8">
            <div class="flex items-center gap-2.5 mb-5">
                <span class="w-7 h-7 rounded-xl bg-indigo-600 text-white font-bold flex items-center justify-center text-sm shadow-md shadow-indigo-600/30">1</span>
                <h2 class="text-lg font-bold text-white">Pilih Game</h2>
            </div>
            
            <div id="game-grid" class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-6 gap-4">
                <!-- JS Inject Games -->
            </div>
        </section>

        <!-- FORM CHECKOUT TOPUP (Tampil setelah game dipilih) -->
        <div id="checkout-section" class="space-y-8 hidden">
            
            <!-- STEP 2: MASUKKAN DATA AKUN -->
            <section class="bg-slate-900 border border-slate-800/90 rounded-2xl p-5 shadow-xl">
                <div class="flex items-center gap-2.5 mb-4">
                    <span class="w-7 h-7 rounded-xl bg-indigo-600 text-white font-bold flex items-center justify-center text-sm shadow-md shadow-indigo-600/30">2</span>
                    <h2 class="text-lg font-bold text-white">Masukkan Data Akun</h2>
                </div>
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                    <div>
                        <label class="block text-xs font-semibold text-slate-400 mb-1.5">User ID / ID Game</label>
                        <input type="text" id="input-userid" placeholder="Contoh: 12345678" class="w-full bg-slate-950 border border-slate-800 rounded-xl px-4 py-2.5 text-sm text-white focus:outline-none focus:border-indigo-500 transition-all">
                    </div>
                    <div id="zone-container">
                        <label class="block text-xs font-semibold text-slate-400 mb-1.5">Zone ID / Server</label>
                        <input type="text" id="input-zoneid" placeholder="Contoh: 1234" class="w-full bg-slate-950 border border-slate-800 rounded-xl px-4 py-2.5 text-sm text-white focus:outline-none focus:border-indigo-500 transition-all">
                    </div>
                </div>
            </section>

            <!-- STEP 3: PILIH NOMINAL / ITEM -->
            <section class="bg-slate-900 border border-slate-800/90 rounded-2xl p-5 shadow-xl">
                <div class="flex items-center gap-2.5 mb-4">
                    <span class="w-7 h-7 rounded-xl bg-indigo-600 text-white font-bold flex items-center justify-center text-sm shadow-md shadow-indigo-600/30">3</span>
                    <h2 class="text-lg font-bold text-white">Pilih Nominal Top Up</h2>
                </div>
                <div id="item-grid" class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-3">
                    <!-- JS Inject Items -->
                </div>
            </section>

            <!-- STEP 4: PILIH METODE PEMBAYARAN -->
            <section class="bg-slate-900 border border-slate-800/90 rounded-2xl p-5 shadow-xl">
                <div class="flex items-center gap-2.5 mb-4">
                    <span class="w-7 h-7 rounded-xl bg-indigo-600 text-white font-bold flex items-center justify-center text-sm shadow-md shadow-indigo-600/30">4</span>
                    <h2 class="text-lg font-bold text-white">Pilih Pembayaran</h2>
                </div>
                <div id="payment-grid" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-3">
                    <!-- JS Inject Payments -->
                </div>
            </section>

            <!-- STEP 5: KONTAK & BAYAR -->
            <section class="bg-slate-900 border border-slate-800/90 rounded-2xl p-5 shadow-xl">
                <div class="flex items-center gap-2.5 mb-4">
                    <span class="w-7 h-7 rounded-xl bg-indigo-600 text-white font-bold flex items-center justify-center text-sm shadow-md shadow-indigo-600/30">5</span>
                    <h2 class="text-lg font-bold text-white">Nomor WhatsApp & Beli</h2>
                </div>
                <div class="space-y-4">
                    <div>
                        <label class="block text-xs font-semibold text-slate-400 mb-1.5">No. WhatsApp (Untuk Bukti Transaksi)</label>
                        <input type="tel" id="input-wa" placeholder="081234567890" class="w-full bg-slate-950 border border-slate-800 rounded-xl px-4 py-2.5 text-sm text-white focus:outline-none focus:border-indigo-500 transition-all">
                    </div>

                    <div class="bg-slate-950 p-4 rounded-xl border border-slate-800 flex flex-col sm:flex-row justify-between items-center gap-4">
                        <div>
                            <p class="text-xs text-slate-400">Total Pembayaran:</p>
                            <p id="summary-total" class="text-2xl font-extrabold text-emerald-400">Rp 0</p>
                        </div>
                        <button onclick="processCheckout()" class="w-full sm:w-auto bg-gradient-to-r from-indigo-600 to-violet-600 hover:from-indigo-500 hover:to-violet-500 text-white font-bold px-8 py-3.5 rounded-xl shadow-lg shadow-indigo-600/30 flex items-center justify-center gap-2 transition-all">
                            <i data-lucide="shopping-bag" class="w-5 h-5"></i> Beli Sekarang
                        </button>
                    </div>
                </div>
            </section>

        </div>
    </main>

    <!-- MODAL INVOICE PEMBAYARAN -->
    <div id="modal-invoice" class="fixed inset-0 bg-slate-950/80 backdrop-blur-md z-50 flex items-center justify-center hidden p-4">
        <div class="bg-slate-900 border border-slate-800 rounded-3xl w-full max-w-lg p-6 shadow-2xl relative overflow-hidden">
            <div class="flex justify-between items-center pb-4 border-b border-slate-800 mb-4">
                <div class="flex items-center gap-2.5">
                    <div class="p-2 bg-emerald-500/10 text-emerald-400 rounded-xl"><i data-lucide="check-circle-2" class="w-5 h-5"></i></div>
                    <div>
                        <h3 class="font-bold text-white">Invoice Ridwan topup</h3>
                        <p class="text-[10px] text-slate-400" id="inv-id">INV-100234</p>
                    </div>
                </div>
                <button onclick="closeInvoice()" class="text-slate-400 hover:text-white p-1"><i data-lucide="x" class="w-5 h-5"></i></button>
            </div>

            <div class="space-y-4 text-xs">
                <div class="bg-slate-950 p-3.5 rounded-xl border border-slate-800/80 space-y-2">
                    <div class="flex justify-between"><span class="text-slate-400">Game:</span><span id="inv-game" class="font-semibold text-white">Honor of Kings</span></div>
                    <div class="flex justify-between"><span class="text-slate-400">User ID:</span><span id="inv-user" class="font-semibold text-white">1234567</span></div>
                    <div class="flex justify-between"><span class="text-slate-400">Item:</span><span id="inv-item" class="font-semibold text-indigo-400">240 Tokens</span></div>
                    <div class="flex justify-between"><span class="text-slate-400">Metode Bayar:</span><span id="inv-method" class="font-semibold text-white">QRIS All Payment</span></div>
                    <div class="flex justify-between border-t border-slate-800 pt-2"><span class="text-slate-300 font-bold">Total Bayar:</span><span id="inv-total" class="font-extrabold text-emerald-400 text-sm">Rp 35.000</span></div>
                </div>

                <!-- QRIS / Code Display -->
                <div class="text-center p-4 bg-white text-slate-900 rounded-2xl">
                    <p class="font-bold text-xs uppercase mb-2">Scan QRIS Untuk Membayar</p>
                    <img src="https://api.qrserver.com/v1/create-qr-code/?size=180x180&data=RidwanTopupPaymentInvoice" alt="QRIS Code" class="mx-auto w-40 h-40 rounded-lg shadow-md mb-2">
                    <p class="text-[10px] text-slate-500">Mendukung GoPay, DANA, OVO, ShopeePay & All Mobile Banking</p>
                </div>
            </div>

            <button onclick="closeInvoice()" class="w-full mt-5 bg-indigo-600 hover:bg-indigo-500 text-white font-bold py-3 rounded-xl shadow-lg transition-all text-xs">
                Konfirmasi Sudah Bayar
            </button>
        </div>
    </div>

    <!-- SCRIPT APPLICATION -->
    <script>
        // DATA GAME BERDENGAN ICON RESMI PLAY STORE / OFFICIAL CDN
        const gamesData = [
            { 
                id: 'hok', 
                name: 'Honor of Kings', 
                publisher: 'Level Infinite', 
                hasZone: false, 
                logo: 'https://play-lh.googleusercontent.com/9aJ43pQ-tAnA2Yf-x8S_Y5f1K5kR0lA5P0pXW-z0oB2zP6A6K_s4l3e6uA4e0mR=w240-h240',
                fallbackLogo: 'https://upload.wikimedia.org/wikipedia/en/thumb/e/e0/Honor_of_Kings_logo.png/220px-Honor_of_Kings_logo.png',
                items: [
                    { id: 'hok-1', name: '80 Tokens', price: 12000 },
                    { id: 'hok-2', name: '240 Tokens', price: 35000 },
                    { id: 'hok-3', name: '400 Tokens', price: 58000 },
                    { id: 'hok-4', name: 'Weekly Pass', price: 28000 }
                ]
            },
            { 
                id: 'ml', 
                name: 'Mobile Legends', 
                publisher: 'Moonton', 
                hasZone: true, 
                logo: 'https://play-lh.googleusercontent.com/m-M2zP00d_w4E1cI3d3u54uE3A8L1A3x22C-4I1_A0Z=w240-h240',
                fallbackLogo: 'https://upload.wikimedia.org/wikipedia/id/thumb/a/a2/Mobile_Legends_Bang_Bang_logo.png/220px-Mobile_Legends_Bang_Bang_logo.png',
                items: [
                    { id: 'ml-1', name: '86 Diamonds', price: 21000 },
                    { id: 'ml-2', name: '172 Diamonds', price: 42000 },
                    { id: 'ml-3', name: '257 Diamonds', price: 63000 },
                    { id: 'ml-4', name: 'Weekly Diamond Pass', price: 28500 }
                ]
            },
            { 
                id: 'ff', 
                name: 'Free Fire', 
                publisher: 'Garena', 
                hasZone: false, 
                logo: 'https://play-lh.googleusercontent.com/WW8T7zW-9Y2323_y0A2Z3=w240-h240',
                fallbackLogo: 'https://upload.wikimedia.org/wikipedia/id/thumb/0/00/Garena_Free_Fire_logo.png/220px-Garena_Free_Fire_logo.png',
                items: [
                    { id: 'ff-1', name: '140 Diamonds', price: 19000 },
                    { id: 'ff-2', name: '355 Diamonds', price: 47000 },
                    { id: 'ff-3', name: '720 Diamonds', price: 92000 }
                ]
            },
            { 
                id: 'pubg', 
                name: 'PUBG Mobile', 
                publisher: 'Tencent Games', 
                hasZone: false, 
                logo: 'https://play-lh.googleusercontent.com/J_q3b2uE-X22c2A1u=w240-h240',
                fallbackLogo: 'https://upload.wikimedia.org/wikipedia/commons/thumb/c/c5/PUBG_Mobile_logo.png/220px-PUBG_Mobile_logo.png',
                items: [
                    { id: 'pubg-1', name: '60 UC', price: 14500 },
                    { id: 'pubg-2', name: '325 UC', price: 73000 }
                ]
            },
            { 
                id: 'genshin', 
                name: 'Genshin Impact', 
                publisher: 'Cognosphere / HoYoverse', 
                hasZone: true, 
                logo: 'https://play-lh.googleusercontent.com/o2xX81-3zX2zX012=w240-h240',
                fallbackLogo: 'https://upload.wikimedia.org/wikipedia/en/5/5d/Genshin_Impact_logo.svg',
                items: [
                    { id: 'gi-1', name: '60 Genesis Crystals', price: 15000 },
                    { id: 'gi-2', name: '300 Genesis Crystals', price: 74000 },
                    { id: 'gi-3', name: 'Blessing of Welkin Moon', price: 74000 }
                ]
            },
            { 
                id: 'valorant', 
                name: 'Valorant', 
                publisher: 'Riot Games', 
                hasZone: false, 
                logo: 'https://upload.wikimedia.org/wikipedia/commons/f/fc/Valorant_logo_-_symbol_only.svg',
                fallbackLogo: 'https://upload.wikimedia.org/wikipedia/commons/f/fc/Valorant_logo_-_symbol_only.svg',
                items: [
                    { id: 'val-1', name: '475 VP', price: 52000 },
                    { id: 'val-2', name: '1000 VP', price: 105000 }
                ]
            }
        ];

        const paymentsData = [
            { id: 'qris', name: 'QRIS All Payment', fee: 0, icon: 'qr-code' },
            { id: 'dana', name: 'DANA', fee: 1000, icon: 'wallet' },
            { id: 'gopay', name: 'GoPay', fee: 1000, icon: 'smartphone' },
            { id: 'shopeepay', name: 'ShopeePay', fee: 1000, icon: 'shopping-bag' },
            { id: 'bri', name: 'BRI Virtual Account', fee: 2500, icon: 'landmark' },
            { id: 'bca', name: 'BCA Virtual Account', fee: 2500, icon: 'building-2' }
        ];

        // STATE
        let selectedGame = null;
        let selectedItem = null;
        let selectedPayment = null;

        document.addEventListener('DOMContentLoaded', () => {
            renderGameGrid();
            lucide.createIcons();
        });

        const formatRp = (num) => new Intl.NumberFormat('id-ID', { style: 'currency', currency: 'IDR', maximumFractionDigits: 0 }).format(num);

        function renderGameGrid() {
            const grid = document.getElementById('game-grid');
            grid.innerHTML = '';

            gamesData.forEach(game => {
                const card = document.createElement('div');
                const isSelected = selectedGame?.id === game.id;
                card.className = `p-3 rounded-2xl cursor-pointer transition-all duration-200 flex flex-col items-center text-center ${isSelected ? 'game-card-select' : 'game-card-unselect'}`;
                card.onclick = () => selectGame(game);

                card.innerHTML = `
                    <div class="relative w-16 h-16 sm:w-20 sm:h-20 mb-2.5 rounded-2xl overflow-hidden shadow-lg border border-slate-700/50 bg-slate-800">
                        <img src="${game.logo}" alt="${game.name}" class="w-full h-full object-cover" onerror="this.src='${game.fallbackLogo}';">
                    </div>
                    <h3 class="font-bold text-xs sm:text-sm text-white leading-tight line-clamp-1">${game.name}</h3>
                    <p class="text-[10px] text-slate-400 mt-0.5 line-clamp-1">${game.publisher}</p>
                `;
                grid.appendChild(card);
            });
        }

        function selectGame(game) {
            selectedGame = game;
            selectedItem = null;
            renderGameGrid();

            // Show Checkout Section
            document.getElementById('checkout-section').classList.remove('hidden');

            // Zone ID visibility
            const zoneContainer = document.getElementById('zone-container');
            if (game.hasZone) {
                zoneContainer.classList.remove('hidden');
            } else {
                zoneContainer.classList.add('hidden');
            }

            renderItemGrid();
            renderPaymentGrid();
            calculateTotal();

            // Smooth Scroll
            document.getElementById('checkout-section').scrollIntoView({ behavior: 'smooth' });
        }

        function renderItemGrid() {
            const grid = document.getElementById('item-grid');
            grid.innerHTML = '';

            if (!selectedGame) return;

            selectedGame.items.forEach(item => {
                const isSelected = selectedItem?.id === item.id;
                const card = document.createElement('div');
                card.className = `p-3.5 rounded-xl cursor-pointer transition-all flex flex-col justify-between ${isSelected ? 'card-select' : 'card-unselect'}`;
                card.onclick = () => { selectedItem = item; renderItemGrid(); calculateTotal(); };

                card.innerHTML = `
                    <div>
                        <p class="font-bold text-xs text-white">${item.name}</p>
                    </div>
                    <div class="mt-2 text-indigo-400 font-extrabold text-sm">${formatRp(item.price)}</div>
                `;
                grid.appendChild(card);
            });
        }

        function renderPaymentGrid() {
            const grid = document.getElementById('payment-grid');
            grid.innerHTML = '';

            paymentsData.forEach(pay => {
                const isSelected = selectedPayment?.id === pay.id;
                const card = document.createElement('div');
                card.className = `p-3.5 rounded-xl cursor-pointer transition-all flex items-center justify-between ${isSelected ? 'card-select' : 'card-unselect'}`;
                card.onclick = () => { selectedPayment = pay; renderPaymentGrid(); calculateTotal(); };

                card.innerHTML = `
                    <div class="flex items-center gap-3">
                        <i data-lucide="${pay.icon}" class="w-5 h-5 text-indigo-400"></i>
                        <div>
                            <p class="font-bold text-xs text-white">${pay.name}</p>
                            <p class="text-[10px] text-slate-400">${pay.fee === 0 ? 'Bebas Admin' : '+ Admin ' + formatRp(pay.fee)}</p>
                        </div>
                    </div>
                `;
                grid.appendChild(card);
            });
            lucide.createIcons();
        }

        function calculateTotal() {
            const itemPrice = selectedItem ? selectedItem.price : 0;
            const adminFee = selectedPayment ? selectedPayment.fee : 0;
            const grandTotal = itemPrice + adminFee;

            document.getElementById('summary-total').innerText = formatRp(grandTotal);
        }

        function processCheckout() {
            const userId = document.getElementById('input-userid').value.trim();
            const zoneId = document.getElementById('input-zoneid').value.trim();
            const waNum = document.getElementById('input-wa').value.trim();

            if (!selectedGame) { alert('Silakan pilih game terlebih dahulu!'); return; }
            if (!userId) { alert('Silakan isi User ID akun game kamu!'); return; }
            if (selectedGame.hasZone && !zoneId) { alert('Silakan isi Zone ID / Server!'); return; }
            if (!selectedItem) { alert('Silakan pilih nominal top up!'); return; }
            if (!selectedPayment) { alert('Silakan pilih metode pembayaran!'); return; }
            if (!waNum) { alert('Silakan isi nomor WhatsApp untuk penerimaan bukti pembayaran!'); return; }

            // Populate Invoice Modal
            const invId = 'RWT-' + Math.floor(100000 + Math.random() * 900000);
            document.getElementById('inv-id').innerText = invId;
            document.getElementById('inv-game').innerText = selectedGame.name;
            document.getElementById('inv-user').innerText = selectedGame.hasZone ? `${userId} (${zoneId})` : userId;
            document.getElementById('inv-item').innerText = selectedItem.name;
            document.getElementById('inv-method').innerText = selectedPayment.name;
            document.getElementById('inv-total').innerText = formatRp(selectedItem.price + selectedPayment.fee);

            document.getElementById('modal-invoice').classList.remove('hidden');
        }

        function closeInvoice() {
            document.getElementById('modal-invoice').classList.add('hidden');
            alert('Terima kasih! Pesanan kamu di Ridwan topup sedang diproses oleh sistem.');
            resetForm();
        }

        function resetForm() {
            selectedGame = null;
            selectedItem = null;
            selectedPayment = null;
            document.getElementById('input-userid').value = '';
            document.getElementById('input-zoneid').value = '';
            document.getElementById('input-wa').value = '';
            document.getElementById('checkout-section').classList.add('hidden');
            renderGameGrid();
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }
    </script>
</body>
</html>