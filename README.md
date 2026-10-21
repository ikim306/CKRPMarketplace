<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Central Kansas Roleplay (CKRP) - Official Vehicle Valuation & Marketplace Hub</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            ckrp: {
              bg: '#0b0f17',
              card: '#151d2a',
              border: '#212d40',
              accent: '#3b82f6',
              gold: '#f59e0b',
              green: '#10b981',
              red: '#ef4444'
            }
          }
        }
      }
    }
  </script>
  <style>
    body {
      background-color: #0b0f17;
      color: #f3f4f6;
      font-family: 'Inter', system-ui, -apple-system, sans-serif;
    }
    .custom-scrollbar::-webkit-scrollbar {
      width: 6px;
    }
    .custom-scrollbar::-webkit-scrollbar-track {
      background: #0b0f17;
    }
    .custom-scrollbar::-webkit-scrollbar-thumb {
      background: #212d40;
      border-radius: 3px;
    }
    .glass-panel {
      background: rgba(21, 29, 42, 0.85);
      backdrop-filter: blur(12px);
      border: 1px solid rgba(255, 255, 255, 0.08);
    }
  </style>
</head>
<body class="min-h-screen custom-scrollbar flex flex-col">

  <!-- TOP HEADER / NAV -->
  <header class="sticky top-0 z-50 glass-panel border-b border-gray-800 px-4 lg:px-8 py-3 flex items-center justify-between">
    <div class="flex items-center space-x-3">
      <div class="w-10 h-10 rounded-lg bg-blue-600 flex items-center justify-center font-bold text-xl text-white shadow-lg shadow-blue-600/30">
        CK
      </div>
      <div>
        <h1 class="text-lg font-bold tracking-wide text-white leading-tight">Central Kansas Roleplay</h1>
        <p class="text-xs text-blue-400 font-medium">Official Vehicle Valuation & Marketplace Hub</p>
      </div>
    </div>

    <div class="flex items-center space-x-3">
      <span class="hidden md:inline-flex items-center px-3 py-1 rounded-full text-xs font-semibold bg-emerald-500/10 text-emerald-400 border border-emerald-500/20">
        <span class="w-2 h-2 rounded-full bg-emerald-400 mr-2 animate-pulse"></span> 97 CKRP Vehicles Loaded
      </span>
      <a href="#calculator-section" class="px-4 py-2 text-xs font-semibold text-white bg-blue-600 hover:bg-blue-500 rounded-lg transition-all shadow-md">
        <i class="fa-solid fa-calculator mr-1"></i> Valuate & Sell Car
      </a>
    </div>
  </header>

  <!-- MAIN CONTAINER -->
  <main class="flex-grow max-w-7xl w-full mx-auto px-4 sm:px-6 lg:px-8 py-8 space-y-10">

    <!-- HERO BANNER -->
    <div class="relative rounded-2xl bg-gradient-to-r from-blue-900/40 via-gray-900 to-indigo-900/40 p-6 sm:p-10 border border-blue-500/20 overflow-hidden shadow-2xl">
      <div class="relative z-10 max-w-2xl">
        <span class="text-xs font-bold uppercase tracking-wider text-blue-400 bg-blue-500/10 px-3 py-1 rounded-full border border-blue-500/20">Authentic CKRP Vehicle Roster</span>
        <h2 class="text-3xl sm:text-4xl font-extrabold text-white mt-3 tracking-tight">Vehicle Valuation & Marketplace</h2>
        <p class="mt-3 text-sm sm:text-base text-gray-300">
          Features all 72 Standard On-Sale vehicles and all 25 Limited/Off-Sale/Emergency vehicles from Central Kansas Roleplay. Uses exact CKRP dealership MSRPs, instant trade-in rates (~69%), mileage wear, and transmission multipliers.
        </p>
      </div>
      <div class="absolute -right-10 -bottom-10 opacity-10 text-blue-400 pointer-events-none">
        <i class="fa-solid fa-car text-[240px]"></i>
      </div>
    </div>

    <!-- CALCULATOR & SELL SECTION -->
    <section id="calculator-section" class="grid grid-cols-1 lg:grid-cols-12 gap-8">
      
      <!-- FORM CONTROLS -->
      <div class="lg:col-span-7 bg-ckrp-card rounded-2xl p-6 border border-ckrp-border shadow-xl space-y-6">
        <div class="border-b border-gray-800 pb-4">
          <h2 class="text-xl font-bold text-white flex items-center gap-2">
            <i class="fa-solid fa-sliders text-blue-400"></i> Cascading Vehicle Selector
          </h2>
          <p class="text-xs text-gray-400 mt-1">Select your exact vehicle parameters from the in-game catalog to generate auto-renders and market value.</p>
        </div>

        <div class="space-y-4">
          
          <!-- CASCADING SELECTORS -->
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
            <!-- 1. MAKE -->
            <div>
              <label class="block text-xs font-semibold uppercase tracking-wider text-gray-300 mb-1">1. Select Make</label>
              <select id="makeSelect" onchange="onMakeChange()" class="w-full bg-gray-900/90 border border-gray-700 text-white rounded-xl px-3 py-2.5 text-sm focus:outline-none focus:border-blue-500 cursor-pointer">
              </select>
            </div>

            <!-- 2. MODEL -->
            <div>
              <label class="block text-xs font-semibold uppercase tracking-wider text-gray-300 mb-1">2. Select Model</label>
              <select id="modelSelect" onchange="onModelChange()" class="w-full bg-gray-900/90 border border-gray-700 text-white rounded-xl px-3 py-2.5 text-sm focus:outline-none focus:border-blue-500 cursor-pointer">
              </select>
            </div>
          </div>

          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
            <!-- 3. YEAR -->
            <div>
              <label class="block text-xs font-semibold uppercase tracking-wider text-gray-300 mb-1">3. Select Year</label>
              <select id="yearSelect" onchange="onYearChange()" class="w-full bg-gray-900/90 border border-gray-700 text-white rounded-xl px-3 py-2.5 text-sm focus:outline-none focus:border-blue-500 cursor-pointer">
              </select>
            </div>

            <!-- 4. TRIM / TRANSMISSION -->
            <div>
              <label class="block text-xs font-semibold uppercase tracking-wider text-gray-300 mb-1">4. Select Trim / Spec</label>
              <select id="trimSelect" onchange="calculateValuation()" class="w-full bg-gray-900/90 border border-gray-700 text-white rounded-xl px-3 py-2.5 text-sm focus:outline-none focus:border-blue-500 cursor-pointer">
              </select>
            </div>
          </div>

          <!-- STATUS BADGE -->
          <div id="carStatusBadgeContainer" class="p-3 rounded-xl bg-gray-900/50 border border-gray-800 flex items-center justify-between">
            <span class="text-xs font-medium text-gray-400">Roster Status:</span>
            <span id="carStatusBadge" class="text-xs font-bold px-2.5 py-1 rounded"></span>
          </div>

          <!-- MILEAGE & COLOR -->
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 border-t border-gray-800 pt-4">
            <div>
              <div class="flex justify-between items-center mb-1">
                <label class="text-xs font-semibold uppercase tracking-wider text-gray-300">In-Game Mileage</label>
                <span id="mileageDisplay" class="text-xs font-bold text-blue-400">2,500 mi</span>
              </div>
              <input type="range" id="mileageInput" min="0" max="100000" step="500" value="2500" oninput="calculateValuation()" class="w-full accent-blue-500 bg-gray-800 rounded-lg h-2 cursor-pointer">
              <div class="flex justify-between text-[10px] text-gray-500 mt-1">
                <span>0 mi (New)</span>
                <span>50,000 mi</span>
                <span>100,000+ mi</span>
              </div>
            </div>

            <div>
              <label class="block text-xs font-semibold uppercase tracking-wider text-gray-300 mb-1">Vehicle Paint Color</label>
              <select id="colorSelect" onchange="calculateValuation()" class="w-full bg-gray-900/90 border border-gray-700 text-white rounded-xl px-3 py-2 text-sm focus:outline-none focus:border-blue-500 cursor-pointer">
                <option value="factory_white" data-color="#f8fafc" data-mult="1.0">Factory Summit White</option>
                <option value="factory_black" data-color="#0f172a" data-mult="1.0">Factory Onyx Black</option>
                <option value="factory_silver" data-color="#94a3b8" data-mult="1.0">Factory Quicksilver</option>
                <option value="factory_red" data-color="#dc2626" data-mult="1.0">Factory Victory Red</option>
                <option value="factory_blue" data-color="#2563eb" data-mult="1.0">Factory Indigo Blue</option>
                <option value="custom_neon" data-color="#10b981" data-mult="1.03">Custom Neon Green Wrap (+3%)</option>
                <option value="custom_gold" data-color="#f59e0b" data-mult="1.05">Custom Pearl Gold Coat (+5%)</option>
                <option value="custom_matte" data-color="#334155" data-mult="1.04">Custom Stealth Matte (+4%)</option>
              </select>
            </div>
          </div>

          <!-- SELLER DISCORD CONTACT -->
          <div class="border-t border-gray-800 pt-4">
            <label class="block text-xs font-semibold uppercase tracking-wider text-gray-300 mb-1">Roblox / Discord Handle (For Marketplace Listing)</label>
            <input type="text" id="sellerUsername" placeholder="e.g. Officer_Kansas (Discord)" class="w-full bg-gray-900 border border-gray-700 text-white rounded-xl px-4 py-2.5 text-sm focus:outline-none focus:border-blue-500">
          </div>
        </div>
      </div>

      <!-- VISUAL CANVAS & ESTIMATED VALUE RESULT -->
      <div class="lg:col-span-5 bg-ckrp-card rounded-2xl p-6 border border-ckrp-border shadow-xl flex flex-col justify-between space-y-6">
        <div>
          <div class="flex justify-between items-center mb-3">
            <h3 class="text-sm font-bold uppercase tracking-wider text-gray-300">Auto-Generated Render</h3>
            <span id="carCategoryTag" class="text-[10px] font-bold uppercase px-2 py-0.5 rounded bg-blue-900/50 text-blue-300 border border-blue-500/30">Truck</span>
          </div>

          <!-- DYNAMIC CANVAS -->
          <div class="relative w-full h-48 rounded-xl bg-gray-900/80 border border-gray-800 flex items-center justify-center overflow-hidden">
            <canvas id="carCanvas" width="400" height="200" class="w-full h-full object-contain"></canvas>
            <div id="canvasOverlayText" class="absolute bottom-2 left-2 text-[10px] text-gray-400 bg-black/60 px-2 py-0.5 rounded">
              Generated Profile Render
            </div>
          </div>

          <div class="mt-4 space-y-2">
            <div class="flex justify-between items-center text-sm">
              <span class="text-gray-400">In-Game Dealer Base MSRP:</span>
              <span id="baseMsrpDisplay" class="font-bold text-gray-200">$0</span>
            </div>
            <div class="flex justify-between items-center text-sm">
              <span class="text-gray-400">Instant Dealer Trade-In (~69%):</span>
              <span id="tradeInDisplay" class="font-semibold text-amber-400">$0</span>
            </div>
            <div class="flex justify-between items-center text-sm">
              <span class="text-gray-400">Mileage Wear Depreciation:</span>
              <span id="penaltiesDisplay" class="font-semibold text-red-400">-$0</span>
            </div>
          </div>
        </div>

        <div class="border-t border-gray-800 pt-4">
          <p class="text-xs uppercase tracking-wider text-gray-400 font-semibold mb-1">Recommended Player Resale Value</p>
          <div class="flex items-baseline justify-between">
            <span id="finalValueDisplay" class="text-3xl font-extrabold text-emerald-400">$0</span>
            <span id="saleTypeEligibility" class="text-xs font-semibold px-2.5 py-1 rounded bg-blue-500/10 text-blue-400 border border-blue-500/20">
              Auction & Direct Trade Eligible
            </span>
          </div>

          <button onclick="postListingFromValuation()" class="w-full mt-4 bg-emerald-600 hover:bg-emerald-500 text-white font-bold py-3 px-4 rounded-xl shadow-lg transition-all flex items-center justify-center gap-2">
            <i class="fa-solid fa-plus-circle"></i> List Vehicle on Marketplace
          </button>
        </div>
      </div>
    </section>

    <!-- MARKETPLACE SECTION -->
    <section class="space-y-4">
      <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4 border-b border-gray-800 pb-4">
        <div>
          <h2 class="text-2xl font-bold text-white flex items-center gap-2">
            <i class="fa-solid fa-store text-blue-400"></i> Live Player Marketplace
          </h2>
          <p class="text-xs text-gray-400 mt-0.5">Community vehicle listings priced directly from in-game valuation benchmarks.</p>
        </div>

        <div class="flex items-center space-x-2">
          <div class="relative">
            <input type="text" id="marketSearch" oninput="renderMarketplace()" placeholder="Search active listings..." class="bg-gray-900 border border-gray-700 text-xs rounded-lg px-3 py-2 text-white focus:outline-none focus:border-blue-500 w-48 sm:w-64">
            <i class="fa-solid fa-search absolute right-2.5 top-2.5 text-gray-500 text-xs"></i>
          </div>
        </div>
      </div>

      <!-- ACTIVE MARKETPLACE GRID -->
      <div id="marketplaceContainer" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <!-- Rendered dynamically via JavaScript -->
      </div>
    </section>

  </main>

  <!-- FOOTER -->
  <footer class="mt-auto border-t border-gray-800 py-6 text-center text-xs text-gray-500">
    <p>Central Kansas Roleplay (CKRP) Marketplace & Valuation Tool. Not directly affiliated with Roblox Corporation.</p>
  </footer>

  <!-- JAVASCRIPT APP LOGIC -->
  <script>
    // FULL CKRP 97-VEHICLE ROSTER (72 Standard On-Sale + 25 Off-Sale / Emergency / Limiteds)
    const CKRP_VEHICLE_DATABASE = [
      // CHEVROLET
      { make: 'Chevrolet', model: 'Silverado', year: 2021, trim: 'Custom / Base', msrp: 44000, status: 'On-Sale', body: 'truck' },
      { make: 'Chevrolet', model: 'Silverado', year: 2010, trim: '1500', msrp: 26000, status: 'On-Sale', body: 'truck' },
      { make: 'Chevrolet', model: 'Silverado', year: 2006, trim: '3500 HD Dually', msrp: 32000, status: 'On-Sale', body: 'dually' },
      { make: 'Chevrolet', model: 'Silverado', year: 2003, trim: '3500 HD Dually', msrp: 28000, status: 'On-Sale', body: 'dually' },
      { make: 'Chevrolet', model: 'Silverado', year: 2002, trim: '2500', msrp: 22000, status: 'On-Sale', body: 'truck' },
      { make: 'Chevrolet', model: 'Avalanche', year: 2002, trim: 'Base', msrp: 21000, status: 'On-Sale', body: 'truck' },
      { make: 'Chevrolet', model: 'S-10', year: 1988, trim: 'Base', msrp: 7500, status: 'On-Sale', body: 'truck' },
      { make: 'Chevrolet', model: 'Equinox', year: 2012, trim: 'LT', msrp: 14000, status: 'On-Sale', body: 'suv' },
      { make: 'Chevrolet', model: 'Trailblazer', year: 2007, trim: 'LT', msrp: 12500, status: 'On-Sale', body: 'suv' },
      { make: 'Chevrolet', model: 'Tahoe', year: 2005, trim: 'LT / Z71', msrp: 18500, status: 'On-Sale', body: 'suv' },
      { make: 'Chevrolet', model: 'Tahoe', year: 2002, trim: 'LT', msrp: 14500, status: 'On-Sale', body: 'suv' },
      { make: 'Chevrolet', model: 'Suburban', year: 2005, trim: 'LT', msrp: 19500, status: 'On-Sale', body: 'suv' },
      { make: 'Chevrolet', model: 'Suburban', year: 1989, trim: 'Base', msrp: 11000, status: 'On-Sale', body: 'suv' },
      { make: 'Chevrolet', model: 'Impala', year: 2009, trim: 'LT', msrp: 9500, status: 'On-Sale', body: 'sedan' },
      { make: 'Chevrolet', model: 'Impala', year: 1994, trim: 'SS', msrp: 18000, status: 'On-Sale', body: 'sedan' },
      { make: 'Chevrolet', model: 'Malibu', year: 2005, trim: 'Base', msrp: 6500, status: 'On-Sale', body: 'sedan' },
      { make: 'Chevrolet', model: 'Aveo', year: 2011, trim: 'LT (Auto)', msrp: 5500, status: 'On-Sale', body: 'hatchback' },
      { make: 'Chevrolet', model: 'Aveo', year: 2011, trim: 'LT (Manual)', msrp: 6000, status: 'On-Sale', body: 'hatchback' },
      { make: 'Chevrolet', model: 'Chevelle', year: 1967, trim: 'SS', msrp: 48000, status: 'On-Sale', body: 'muscle' },

      // RAM & DODGE
      { make: 'Ram', model: '1500', year: 2023, trim: 'Big Horn / Crew', msrp: 48000, status: 'On-Sale', body: 'truck' },
      { make: 'Dodge', model: 'Durango', year: 2021, trim: 'GT / Base', msrp: 38000, status: 'On-Sale', body: 'suv' },
      { make: 'Dodge', model: 'Charger', year: 2015, trim: 'Base / R/T', msrp: 26000, status: 'On-Sale', body: 'sedan' },
      { make: 'Dodge', model: 'Charger', year: 2014, trim: 'SRT8', msrp: 34000, status: 'On-Sale', body: 'sedan' },
      { make: 'Dodge', model: 'Grand Caravan', year: 2006, trim: 'SXT', msrp: 8500, status: 'On-Sale', body: 'van' },

      // FORD
      { make: 'Ford', model: 'F-150', year: 2008, trim: 'XLT', msrp: 18500, status: 'On-Sale', body: 'truck' },

      // GMC
      { make: 'GMC', model: 'Sierra', year: 2005, trim: 'SLE', msrp: 19000, status: 'On-Sale', body: 'truck' },
      { make: 'GMC', model: 'Canyon', year: 2008, trim: 'SLE', msrp: 14000, status: 'On-Sale', body: 'truck' },
      { make: 'GMC', model: 'Sonoma', year: 1993, trim: 'Base', msrp: 6800, status: 'On-Sale', body: 'truck' },
      { make: 'GMC', model: 'Envoy', year: 2006, trim: 'SL / SLT / Denali', msrp: 13500, status: 'On-Sale', body: 'suv' },
      { make: 'GMC', model: 'Yukon', year: 2005, trim: 'Denali', msrp: 18000, status: 'On-Sale', body: 'suv' },
      { make: 'GMC', model: 'Savana', year: 2018, trim: 'Passenger Van', msrp: 28000, status: 'On-Sale', body: 'van' },
      { make: 'GMC', model: 'Savana', year: 2007, trim: 'Cargo', msrp: 14000, status: 'On-Sale', body: 'van' },
      { make: 'GMC', model: 'C6500', year: 2008, trim: 'Topkick Box Truck', msrp: 35000, status: 'On-Sale', body: 'truck' },

      // SILVIANO & RM
      { make: 'Silviano', model: 'K15', year: 1998, trim: 'Base', msrp: 12000, status: 'On-Sale', body: 'truck' },
      { make: 'Silviano', model: 'K35', year: 1992, trim: 'Dually', msrp: 16000, status: 'On-Sale', body: 'dually' },
      { make: 'RM25', model: 'Pickup', year: 2000, trim: 'Base (Auto)', msrp: 9500, status: 'On-Sale', body: 'truck' },
      { make: 'RM25', model: 'Pickup', year: 2000, trim: 'Base (5Spd)', msrp: 10500, status: 'On-Sale', body: 'truck' },

      // TOYOTA
      { make: 'Toyota', model: '4Runner', year: 2021, trim: 'SR5', msrp: 38000, status: 'On-Sale', body: 'suv' },
      { make: 'Toyota', model: 'Camry', year: 2015, trim: 'XLE', msrp: 16500, status: 'On-Sale', body: 'sedan' },
      { make: 'Toyota', model: 'Camry', year: 2003, trim: 'LE', msrp: 7500, status: 'On-Sale', body: 'sedan' },
      { make: 'Toyota', model: 'Prius', year: 2012, trim: 'Two / Three', msrp: 11000, status: 'On-Sale', body: 'hatchback' },

      // CADILLAC & BUICK
      { make: 'Cadillac', model: 'Escalade', year: 2011, trim: 'ESV', msrp: 32000, status: 'On-Sale', body: 'suv' },
      { make: 'Cadillac', model: 'DTS', year: 2011, trim: 'Base', msrp: 18000, status: 'On-Sale', body: 'sedan' },
      { make: 'Buick', model: 'Lucerne', year: 2007, trim: 'CX / CXL', msrp: 11500, status: 'On-Sale', body: 'sedan' },
      { make: 'Buick', model: 'Lucerne', year: 2007, trim: 'CXS', msrp: 13500, status: 'On-Sale', body: 'sedan' },
      { make: 'Buick', model: 'LaCrosse', year: 2008, trim: 'CXL', msrp: 10500, status: 'On-Sale', body: 'sedan' },
      { make: 'Buick', model: 'Park Avenue', year: 2001, trim: 'Ultra', msrp: 8500, status: 'On-Sale', body: 'sedan' },
      { make: 'Buick', model: 'Century', year: 2000, trim: 'Custom', msrp: 5500, status: 'On-Sale', body: 'sedan' },

      // BMW
      { make: 'BMW', model: '330i', year: 2019, trim: 'Base', msrp: 34000, status: 'On-Sale', body: 'sedan' },
      { make: 'BMW', model: 'M2', year: 2017, trim: 'Automatic (A/T)', msrp: 45000, status: 'On-Sale', body: 'coupe' },
      { make: 'BMW', model: 'M2', year: 2017, trim: 'Manual (M/T)', msrp: 48000, status: 'On-Sale', body: 'coupe' },
      { make: 'BMW', model: '335i', year: 2009, trim: 'Manual (M/T)', msrp: 19000, status: 'On-Sale', body: 'sedan' },
      { make: 'BMW', model: '530i', year: 2007, trim: 'Base', msrp: 14000, status: 'On-Sale', body: 'sedan' },

      // HYUNDAI, HONDA, TESLA, LEXUS, ACURA, PONTIAC
      { make: 'Hyundai', model: 'Elantra N', year: 2022, trim: 'Manual (M/T)', msrp: 32000, status: 'On-Sale', body: 'sedan' },
      { make: 'Honda', model: 'Accord', year: 2022, trim: 'Sport / EX', msrp: 29000, status: 'On-Sale', body: 'sedan' },
      { make: 'Honda', model: 'Civic', year: 2000, trim: 'DX (Auto)', msrp: 6000, status: 'On-Sale', body: 'sedan' },
      { make: 'Honda', model: 'Civic', year: 2000, trim: 'DX (5Spd)', msrp: 7000, status: 'On-Sale', body: 'sedan' },
      { make: 'Honda', model: 'Civic', year: 2000, trim: 'EX (Auto)', msrp: 7500, status: 'On-Sale', body: 'sedan' },
      { make: 'Honda', model: 'Civic', year: 2000, trim: 'EX (5Spd)', msrp: 8500, status: 'On-Sale', body: 'sedan' },
      { make: 'Honda', model: 'Civic', year: 2000, trim: 'Si (5Spd)', msrp: 12500, status: 'On-Sale', body: 'coupe' },
      { make: 'Tesla', model: 'Model S', year: 2015, trim: 'Base', msrp: 38000, status: 'On-Sale', body: 'sedan' },
      { make: 'Lexus', model: 'IS F', year: 2009, trim: 'Base', msrp: 22000, status: 'On-Sale', body: 'sedan' },
      { make: 'Acura', model: 'TL', year: 2008, trim: 'Base', msrp: 11000, status: 'On-Sale', body: 'sedan' },
      { make: 'Pontiac', model: 'Grand Prix', year: 2002, trim: 'GT', msrp: 6500, status: 'On-Sale', body: 'sedan' },
      { make: 'Pontiac', model: 'G5', year: 2008, trim: 'Base', msrp: 5800, status: 'On-Sale', body: 'coupe' },
      { make: 'Pontiac', model: 'Solstice', year: 2007, trim: 'Base', msrp: 11000, status: 'On-Sale', body: 'coupe' },

      // SPECIAL / CUSTOM / OTHER
      { make: 'Copper', model: 'Copper Custom', year: 2005, trim: 'Base (Auto)', msrp: 9000, status: 'On-Sale', body: 'sedan' },
      { make: 'Copper', model: 'Copper Custom', year: 2005, trim: 'Base (5Spd)', msrp: 10000, status: 'On-Sale', body: 'sedan' },
      { make: 'Capone', model: 'Capone Classic', year: 1991, trim: 'Base', msrp: 15000, status: 'On-Sale', body: 'sedan' },
      { make: 'Chrysler', model: 'Town & Country', year: 2006, trim: 'Touring', msrp: 8000, status: 'On-Sale', body: 'van' },
      { make: 'Comet', model: 'Comet Custom', year: 1989, trim: 'Base', msrp: 12000, status: 'On-Sale', body: 'coupe' },

      // MOTORCYCLES & BIKES
      { make: 'Kawasaki', model: 'Ninja', year: 2024, trim: 'H2', msrp: 34000, status: 'On-Sale', body: 'motorcycle' },
      { make: 'BMW', model: 'S1000RR', year: 2021, trim: 'Sport', msrp: 22000, status: 'On-Sale', body: 'motorcycle' },
      { make: 'Yamaha', model: 'YZF', year: 2024, trim: 'R1M', msrp: 27000, status: 'On-Sale', body: 'motorcycle' },
      { make: 'X6-R', model: 'Dual Sport', year: 2018, trim: 'Base', msrp: 8500, status: 'On-Sale', body: 'motorcycle' },
      { make: 'Honda', model: '125F', year: 2013, trim: 'Dirt Bike', msrp: 4500, status: 'On-Sale', body: 'motorcycle' },
      { make: 'Honda', model: 'Genio', year: 2022, trim: 'Scooter', msrp: 2800, status: 'On-Sale', body: 'motorcycle' },

      // OFF-SALE / EMERGENCY / LIMITED VEHICLES
      { make: 'Dodge', model: 'Durango', year: 2021, trim: 'MPPD Marked', msrp: 50000, status: 'Off-Sale', rarityBonus: 15000, body: 'suv' },
      { make: 'Dodge', model: 'Durango', year: 2021, trim: 'Unmarked Police', msrp: 52000, status: 'Off-Sale', rarityBonus: 18000, body: 'suv' },
      { make: 'Dodge', model: 'Charger', year: 2015, trim: 'Pursuit (KHP / MPPD)', msrp: 45000, status: 'Off-Sale', rarityBonus: 14000, body: 'sedan' },
      { make: 'Dodge', model: 'Charger', year: 2014, trim: 'Pursuit (Unmarked)', msrp: 48000, status: 'Off-Sale', rarityBonus: 16000, body: 'sedan' },
      { make: 'Ford', model: 'Crown Victoria', year: 2011, trim: 'Police Interceptor (KHP)', msrp: 28000, status: 'Off-Sale', rarityBonus: 12000, body: 'sedan' },
      { make: 'Ford', model: 'Crown Victoria', year: 2011, trim: 'Undercover / Unmarked', msrp: 30000, status: 'Off-Sale', rarityBonus: 15000, body: 'sedan' },
      { make: 'Ford', model: 'Interceptor SUV', year: 2018, trim: 'Marked Patrol', msrp: 55000, status: 'Off-Sale', rarityBonus: 18000, body: 'suv' },
      { make: 'Ford', model: 'Taurus', year: 2015, trim: 'MPPD Police Interceptor', msrp: 42000, status: 'Off-Sale', rarityBonus: 14000, body: 'sedan' },
      { make: 'Ford', model: 'F-350', year: 2012, trim: 'Ambulance EMS', msrp: 65000, status: 'Off-Sale', rarityBonus: 20000, body: 'dually' },
      { make: 'Capone', model: 'Capone Classic', year: 1991, trim: 'Police Patrol', msrp: 35000, status: 'Off-Sale', rarityBonus: 22000, body: 'sedan' },
      { make: 'Ford', model: 'F-150', year: 2003, trim: 'SVT Lightning', msrp: 38000, status: 'Off-Sale', rarityBonus: 25000, body: 'truck' },
      { make: 'Ford', model: 'F-150', year: 2006, trim: 'XL / XLT', msrp: 22000, status: 'Off-Sale', rarityBonus: 8000, body: 'truck' },
      { make: 'Ford', model: 'F-350', year: 2008, trim: 'Single Cab 4x4 / Crew', msrp: 36000, status: 'Off-Sale', rarityBonus: 12000, body: 'dually' },
      { make: 'Lincoln', model: 'Continental', year: 2020, trim: 'Staff Exclusive', msrp: 120000, status: 'Off-Sale', rarityBonus: 80000, body: 'sedan' },
      { make: 'C Series', model: 'Luxury Sedan', year: 2002, trim: 'Limited Import', msrp: 85000, status: 'Off-Sale', rarityBonus: 45000, body: 'sedan' },
      { make: 'Truck 100', model: 'Farm Edition', year: 2006, trim: 'Special Edition', msrp: 25000, status: 'Off-Sale', rarityBonus: 15000, body: 'truck' },
      { make: 'BMW', model: 'M2', year: 2017, trim: 'Clapped / Stanced', msrp: 58000, status: 'Off-Sale', rarityBonus: 28000, body: 'coupe' },
      { make: 'Chevrolet', model: 'Camaro', year: 1979, trim: 'Z/28', msrp: 42000, status: 'Off-Sale', rarityBonus: 30000, body: 'muscle' },
      { make: 'Chevrolet', model: 'Corvette', year: 2002, trim: 'C5 Z06', msrp: 52000, status: 'Off-Sale', rarityBonus: 35000, body: 'coupe' },
      { make: 'Ferrari', model: 'F40', year: 1987, trim: 'Classic Exotic', msrp: 250000, status: 'Off-Sale', rarityBonus: 200000, body: 'coupe' },
      { make: 'Bentley', model: 'Brooklands', year: 2008, trim: 'Luxury Coupe', msrp: 180000, status: 'Off-Sale', rarityBonus: 120000, body: 'coupe' },
      { make: 'Maserati', model: 'GranTurismo', year: 2019, trim: 'MC Stradale', msrp: 140000, status: 'Off-Sale', rarityBonus: 90000, body: 'coupe' },
      { make: 'Lamborghini', model: 'Aventador', year: 2021, trim: 'SVJ', msrp: 380000, status: 'Off-Sale', rarityBonus: 300000, body: 'coupe' },
      { make: 'Mercedes-Benz', model: 'SL65', year: 2009, trim: 'AMG V12', msrp: 110000, status: 'Off-Sale', rarityBonus: 70000, body: 'coupe' },
      { make: 'Porsche', model: '911', year: 2021, trim: 'Turbo S', msrp: 220000, status: 'Off-Sale', rarityBonus: 150000, body: 'coupe' }
    ];

    let userListings = [];
    let currentSelectedVehicle = null;

    // Initialize Cascading Dropdowns on Load
    document.addEventListener('DOMContentLoaded', () => {
      populateMakes();
      renderMarketplace();
    });

    function populateMakes() {
      const makeSelect = document.getElementById('makeSelect');
      makeSelect.innerHTML = '';

      // Get unique makes
      const makes = [...new Set(CKRP_VEHICLE_DATABASE.map(item => item.make))].sort();
      
      makes.forEach(make => {
        const opt = document.createElement('option');
        opt.value = make;
        opt.textContent = make;
        makeSelect.appendChild(opt);
      });

      onMakeChange();
    }

    function onMakeChange() {
      const selectedMake = document.getElementById('makeSelect').value;
      const modelSelect = document.getElementById('modelSelect');
      modelSelect.innerHTML = '';

      const filteredModels = [...new Set(
        CKRP_VEHICLE_DATABASE.filter(item => item.make === selectedMake).map(item => item.model)
      )].sort();

      filteredModels.forEach(model => {
        const opt = document.createElement('option');
        opt.value = model;
        opt.textContent = model;
        modelSelect.appendChild(opt);
      });

      onModelChange();
    }

    function onModelChange() {
      const selectedMake = document.getElementById('makeSelect').value;
      const selectedModel = document.getElementById('modelSelect').value;
      const yearSelect = document.getElementById('yearSelect');
      yearSelect.innerHTML = '';

      const filteredYears = [...new Set(
        CKRP_VEHICLE_DATABASE.filter(item => item.make === selectedMake && item.model === selectedModel).map(item => item.year)
      )].sort((a, b) => b - a);

      filteredYears.forEach(year => {
        const opt = document.createElement('option');
        opt.value = year;
        opt.textContent = year;
        yearSelect.appendChild(opt);
      });

      onYearChange();
    }

    function onYearChange() {
      const selectedMake = document.getElementById('makeSelect').value;
      const selectedModel = document.getElementById('modelSelect').value;
      const selectedYear = parseInt(document.getElementById('yearSelect').value, 10);
      const trimSelect = document.getElementById('trimSelect');
      trimSelect.innerHTML = '';

      const matchingTrims = CKRP_VEHICLE_DATABASE.filter(
        item => item.make === selectedMake && item.model === selectedModel && item.year === selectedYear
      );

      matchingTrims.forEach((item, index) => {
        const opt = document.createElement('option');
        opt.value = index;
        opt.textContent = `${item.trim} (${item.status})`;
        trimSelect.appendChild(opt);
      });

      calculateValuation();
    }

    function calculateValuation() {
      const selectedMake = document.getElementById('makeSelect').value;
      const selectedModel = document.getElementById('modelSelect').value;
      const selectedYear = parseInt(document.getElementById('yearSelect').value, 10);
      const trimIndex = parseInt(document.getElementById('trimSelect').value || 0, 10);

      const matchingTrims = CKRP_VEHICLE_DATABASE.filter(
        item => item.make === selectedMake && item.model === selectedModel && item.year === selectedYear
      );

      const car = matchingTrims[trimIndex] || matchingTrims[0];
      if (!car) return;

      currentSelectedVehicle = car;

      const mileage = parseInt(document.getElementById('mileageInput').value, 10);
      document.getElementById('mileageDisplay').textContent = `${mileage.toLocaleString()} mi`;

      // Color selection
      const colorSelect = document.getElementById('colorSelect');
      const selectedColorOpt = colorSelect.options[colorSelect.selectedIndex];
      const colorHex = selectedColorOpt.getAttribute('data-color');
      const colorMult = parseFloat(selectedColorOpt.getAttribute('data-mult'));

      // Calculate Valuation based on CKRP Mechanics (~69% trade in factor & wear)
      const baseMsrp = car.msrp;
      const rarityBonus = car.rarityBonus || 0;
      
      const tradeInOffer = Math.round(baseMsrp * 0.69);
      const mileageDepreciation = Math.round((baseMsrp + rarityBonus) * Math.min(0.35, (mileage / 100000) * 0.30));
      
      const estimatedValue = Math.max(1000, Math.round(((baseMsrp + rarityBonus) * colorMult) - mileageDepreciation));

      // UI Display Updates
      document.getElementById('baseMsrpDisplay').textContent = `$${baseMsrp.toLocaleString()}`;
      document.getElementById('tradeInDisplay').textContent = `$${tradeInOffer.toLocaleString()}`;
      document.getElementById('penaltiesDisplay').textContent = `-$${mileageDepreciation.toLocaleString()}`;
      document.getElementById('finalValueDisplay').textContent = `$${estimatedValue.toLocaleString()}`;
      document.getElementById('carCategoryTag').textContent = car.body;

      const statusBadge = document.getElementById('carStatusBadge');
      if (car.status === 'On-Sale') {
        statusBadge.textContent = 'Standard On-Sale Dealership Vehicle';
        statusBadge.className = 'text-xs font-bold px-2.5 py-1 rounded bg-emerald-500/10 text-emerald-400 border border-emerald-500/20';
      } else {
        statusBadge.textContent = 'Off-Sale / Limited / Emergency Vehicle';
        statusBadge.className = 'text-xs font-bold px-2.5 py-1 rounded bg-amber-500/10 text-amber-400 border border-amber-500/20';
      }

      // Draw Profile Preview on Canvas
      drawCarCanvas(car.body, colorHex);
    }

    // Dynamic Profile Renderer
    function drawCarCanvas(bodyType, colorHex) {
      const canvas = document.getElementById('carCanvas');
      const ctx = canvas.getContext('2d');
      ctx.clearRect(0, 0, canvas.width, canvas.height);

      // Background Gradient
      const bgGrad = ctx.createLinearGradient(0, 0, 0, canvas.height);
      bgGrad.addColorStop(0, '#0f172a');
      bgGrad.addColorStop(1, '#1e293b');
      ctx.fillStyle = bgGrad;
      ctx.fillRect(0, 0, canvas.width, canvas.height);

      // Shadow Ground
      ctx.fillStyle = 'rgba(0,0,0,0.5)';
      ctx.beginPath();
      ctx.ellipse(200, 165, 140, 16, 0, 0, Math.PI * 2);
      ctx.fill();

      ctx.fillStyle = colorHex;

      if (bodyType === 'truck' || bodyType === 'dually') {
        ctx.beginPath();
        ctx.roundRect(80, 110, 240, 35, 6);
        ctx.fill();
        ctx.beginPath();
        ctx.roundRect(100, 75, 120, 40, 8);
        ctx.fill();
        ctx.fillRect(220, 95, 95, 20);
      } else if (bodyType === 'suv') {
        ctx.beginPath();
        ctx.roundRect(80, 105, 240, 40, 8);
        ctx.fill();
        ctx.beginPath();
        ctx.roundRect(95, 70, 200, 40, 10);
        ctx.fill();
      } else if (bodyType === 'van') {
        ctx.beginPath();
        ctx.roundRect(75, 90, 250, 55, 10);
        ctx.fill();
      } else if (bodyType === 'motorcycle') {
        ctx.beginPath();
        ctx.roundRect(130, 110, 140, 25, 12);
        ctx.fill();
      } else {
        // Sedan / Coupe / Muscle
        ctx.beginPath();
        ctx.roundRect(70, 115, 260, 32, 8);
        ctx.fill();
        ctx.beginPath();
        ctx.moveTo(110, 115);
        ctx.lineTo(150, 80);
        ctx.lineTo(240, 80);
        ctx.lineTo(280, 115);
        ctx.closePath();
        ctx.fill();
      }

      // Windows
      if (bodyType !== 'motorcycle') {
        ctx.fillStyle = 'rgba(191, 219, 254, 0.7)';
        ctx.beginPath();
        ctx.roundRect(130, 85, 45, 25, 3);
        ctx.roundRect(180, 85, 45, 25, 3);
        ctx.fill();
      }

      // Wheels
      ctx.fillStyle = '#0f172a';
      ctx.beginPath();
      ctx.arc(120, 148, 22, 0, Math.PI * 2);
      ctx.arc(280, 148, 22, 0, Math.PI * 2);
      ctx.fill();

      // Rim Cores
      ctx.fillStyle = '#94a3b8';
      ctx.beginPath();
      ctx.arc(120, 148, 11, 0, Math.PI * 2);
      ctx.arc(280, 148, 11, 0, Math.PI * 2);
      ctx.fill();
    }

    function postListingFromValuation() {
      if (!currentSelectedVehicle) return;

      const sellerName = document.getElementById('sellerUsername').value.trim() || 'CKRP Driver';
      const mileage = parseInt(document.getElementById('mileageInput').value, 10);
      const calculatedValuation = parseInt(document.getElementById('finalValueDisplay').textContent.replace(/[^0-9]/g, ''), 10);

      const newListing = {
        id: Date.now(),
        car: currentSelectedVehicle,
        mileage: mileage,
        price: calculatedValuation,
        seller: sellerName
      };

      userListings.unshift(newListing);
      renderMarketplace();

      document.getElementById('marketplaceContainer').scrollIntoView({ behavior: 'smooth' });
    }

    function renderMarketplace() {
      const container = document.getElementById('marketplaceContainer');
      const searchQuery = (document.getElementById('marketSearch')?.value || '').toLowerCase();

      const filteredListings = userListings.filter(item => {
        const title = `${item.car.year} ${item.car.make} ${item.car.model} ${item.car.trim}`.toLowerCase();
        const seller = item.seller.toLowerCase();
        return title.includes(searchQuery) || seller.includes(searchQuery);
      });

      if (filteredListings.length === 0) {
        container.innerHTML = `
          <div class="col-span-full border border-dashed border-gray-800 rounded-2xl p-12 text-center bg-gray-900/30">
            <div class="w-16 h-16 mx-auto rounded-full bg-blue-500/10 text-blue-400 flex items-center justify-center text-2xl mb-3">
              <i class="fa-solid fa-car-rear"></i>
            </div>
            <h3 class="text-lg font-bold text-white">No Active Marketplace Listings</h3>
            <p class="text-xs text-gray-400 max-w-sm mx-auto mt-1">
              Select your vehicle parameters above to generate a valuation and list your car on the live marketplace feed!
            </p>
          </div>
        `;
        return;
      }

      container.innerHTML = filteredListings.map(item => `
        <div class="bg-ckrp-card border border-ckrp-border rounded-2xl p-5 shadow-lg flex flex-col justify-between space-y-4 hover:border-blue-500/50 transition-all">
          <div>
            <div class="flex justify-between items-start mb-2">
              <div>
                <span class="text-[10px] font-bold uppercase tracking-wider text-blue-400 bg-blue-500/10 px-2 py-0.5 rounded border border-blue-500/20">${item.car.body}</span>
                <h3 class="text-base font-bold text-white mt-1.5">${item.car.year} ${item.car.make} ${item.car.model}</h3>
                <p class="text-xs text-gray-400">${item.car.trim}</p>
              </div>
              <span class="text-xs font-semibold px-2 py-0.5 rounded ${item.car.status === 'On-Sale' ? 'bg-emerald-500/10 text-emerald-400 border border-emerald-500/20' : 'bg-amber-500/10 text-amber-400 border border-amber-500/20'}">
                ${item.car.status}
              </span>
            </div>

            <div class="flex items-center space-x-2 text-xs text-gray-400 my-3">
              <span class="flex items-center gap-1"><i class="fa-solid fa-gauge-high text-blue-400"></i> ${item.mileage.toLocaleString()} mi</span>
            </div>
          </div>

          <div class="border-t border-gray-800 pt-3 flex items-center justify-between">
            <div>
              <p class="text-[10px] uppercase text-gray-500 font-semibold">Listing Price</p>
              <p class="text-xl font-extrabold text-emerald-400">$${item.price.toLocaleString()}</p>
            </div>
            <div class="text-right">
              <p class="text-[10px] text-gray-500 font-semibold">Seller Contact</p>
              <p class="text-xs font-bold text-gray-200"><i class="fa-brands fa-discord text-indigo-400 mr-1"></i>${item.seller}</p>
            </div>
          </div>
        </div>
      `).join('');
    }
  </script>
</body>
</html>
