<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Flavor-Fusion Rajshahi | অর্ডার করুন</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: system-ui, 'Segoe UI', sans-serif; }
        body { background: #fef7e8; color: #2c3e2b; padding-bottom: 70px; }
        
        .navbar { 
            background: #ff6b35; 
            color: white; 
            padding: 12px 20px; 
            display: flex; 
            justify-content: space-between; 
            align-items: center; 
            flex-wrap: wrap; 
            position: sticky; 
            top: 0; 
            z-index: 100; 
        }
        .logo-area {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .logo-img {
            width: 45px;
            height: 45px;
            background: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 28px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.2);
        }
        .logo-text {
            text-align: center;
        }
        .logo-text h2 { font-size: 1.1rem; letter-spacing: 1px; }
        .logo-text p { font-size: 0.7rem; opacity: 0.9; }
        .nav-buttons { display: flex; gap: 8px; flex-wrap: wrap; }
        .nav-btn { background: #2c3e2f; color: white; border: none; padding: 8px 14px; border-radius: 40px; margin: 0; cursor: pointer; font-size: 12px; transition: 0.3s; }
        .nav-btn:hover { background: #1e5520; transform: scale(0.98); }
        .cart-icon { background: #2c3e2f; padding: 6px 14px; border-radius: 40px; cursor: pointer; transition: 0.3s; display: flex; align-items: center; gap: 5px; }
        .cart-icon:hover { background: #1e5520; }
        
        .slider-container {
            background: linear-gradient(135deg, #ff6b35, #ffb88c);
            padding: 25px 20px;
            overflow: hidden;
            position: relative;
            transition: background 0.5s ease;
        }
        .slider-content {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            animation: slideInRight 0.6s ease;
        }
        @keyframes slideInRight {
            from { opacity: 0; transform: translateX(100px); }
            to { opacity: 1; transform: translateX(0); }
        }
        @keyframes slideInLeft {
            from { opacity: 0; transform: translateX(-100px); }
            to { opacity: 1; transform: translateX(0); }
        }
        .slider-text { color: white; text-align: center; }
        .slider-text h2 { font-size: 1.6rem; margin-bottom: 5px; text-shadow: 2px 2px 4px rgba(0,0,0,0.2); }
        .slider-text p { font-size: 0.9rem; opacity: 0.95; }
        .slider-img {
            width: 70px; height: 70px; border-radius: 50%; border: 3px solid white;
            box-shadow: 0 4px 12px rgba(0,0,0,0.2);
            animation: bounce 1s ease infinite;
            background: rgba(255,255,255,0.3);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 40px;
        }
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-8px); }
        }
        
        .hero { background: linear-gradient(105deg, #ffe0b5, #ffb88c); padding: 1rem; text-align: center; }
        .filter-bar { padding: 12px 16px; display: flex; flex-wrap: wrap; gap: 10px; background: white; box-shadow: 0 2px 8px rgba(0,0,0,0.05); }
        .search-box input { padding: 8px 12px; border-radius: 40px; border: 1px solid #ffb88c; width: 200px; }
        .category-filters { display: flex; gap: 8px; flex-wrap: wrap; }
        .filter-btn { background: #fff0e0; border: none; padding: 6px 14px; border-radius: 40px; cursor: pointer; transition: 0.3s; }
        .filter-btn.active, .filter-btn:hover { background: #ff6b35; color: white; }
        .products { padding: 20px 16px; max-width: 1300px; margin: auto; }
        .product-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 20px; }
        .product-card { background: white; border-radius: 24px; overflow: hidden; box-shadow: 0 4px 12px rgba(0,0,0,0.08); transition: 0.3s; position: relative; }
        .product-card:hover { transform: translateY(-4px); box-shadow: 0 8px 24px rgba(0,0,0,0.12); }
        .product-card img { width: 100%; height: 180px; object-fit: cover; }
        .product-card h3 { margin: 12px 14px 4px; font-size: 1.2rem; }
        .price { font-size: 1.4rem; font-weight: bold; color: #ff6b35; margin: 4px 14px; }
        .per-kg { font-size: 0.85rem; color: #666; margin-left: 14px; margin-bottom: 8px; }
        .min-order-badge {
            position: absolute;
            top: 10px;
            left: 10px;
            background: #e67e22;
            color: white;
            padding: 4px 10px;
            border-radius: 20px;
            font-size: 0.65rem;
            font-weight: bold;
        }
        .delivery-badge {
            position: absolute;
            top: 10px;
            right: 10px;
            background: #2c6e2f;
            color: white;
            padding: 4px 10px;
            border-radius: 20px;
            font-size: 0.7rem;
            font-weight: bold;
        }
        .review-trigger { margin: 8px 14px; font-size: 0.75rem; color: #e67e22; cursor: pointer; display: inline-block; background: #fff1e0; padding: 4px 14px; border-radius: 20px; transition: 0.3s; }
        .review-trigger:hover { background: #ffe0c4; }
        .card-buttons { display: flex; gap: 10px; margin: 10px 14px 16px; }
        .btn-add, .btn-buy { flex: 1; padding: 10px 0; border-radius: 40px; font-weight: bold; border: none; cursor: pointer; transition: 0.3s; }
        .btn-add { background: #ffedd5; color: #ff6b35; border: 1px solid #ffd7a5; }
        .btn-add:hover { background: #ffe0b5; }
        .btn-buy { background: #ff6b35; color: white; }
        .btn-buy:hover { background: #e55a2b; transform: scale(0.98); }
        .modal { display: none; position: fixed; top:0; left:0; width:100%; height:100%; background: rgba(0,0,0,0.75); justify-content: center; align-items: center; z-index: 1000; }
        .modal-container { background: white; width: 92%; max-width: 550px; border-radius: 32px; padding: 24px; max-height: 85vh; overflow-y: auto; }
        .modal-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 20px; border-bottom: 2px solid #ffe0b5; padding-bottom: 12px; }
        .modal-header h3 { font-size: 1.4rem; color: #ff6b35; }
        .close-modal { font-size: 32px; cursor: pointer; color: #999; transition: 0.3s; }
        .close-modal:hover { color: #ff6b35; }
        .order-summary-item { display: flex; justify-content: space-between; padding: 10px 0; border-bottom: 1px solid #f0e0c0; }
        .form-group { margin-bottom: 18px; }
        .form-group label { display: block; margin-bottom: 6px; font-weight: 600; color: #2c3e2b; }
        .form-group input, .form-group textarea, .form-group select { width: 100%; padding: 12px 16px; border-radius: 40px; border: 1px solid #ffd6b0; font-size: 1rem; transition: 0.3s; }
        .form-group input:focus, .form-group textarea:focus, .form-group select:focus { outline: none; border-color: #ff6b35; box-shadow: 0 0 0 3px rgba(255,107,53,0.1); }
        .payment-option { display: flex; gap: 12px; background: #faf0e2; padding: 12px; border-radius: 60px; margin: 10px 0; flex-wrap: wrap; }
        .payment-option label { background: white; padding: 6px 18px; border-radius: 50px; cursor: pointer; transition: 0.3s; display: flex; align-items: center; gap: 6px; }
        .payment-option label:hover { background: #ff6b35; color: white; }
        .confirm-btn { background: #2c6e2f; width: 100%; padding: 14px; border: none; color: white; border-radius: 60px; font-weight: bold; font-size: 1.1rem; margin-top: 12px; cursor: pointer; transition: 0.3s; }
        .confirm-btn:hover { background: #1e5520; transform: scale(0.98); }
        .confirm-btn.disabled, .confirm-btn:disabled { background: #aaa; cursor: not-allowed; transform: none; }
        .review-item { border-bottom: 1px solid #eee; padding: 12px 0; }
        .review-img { max-width: 80px; border-radius: 16px; margin-top: 6px; }
        .star-rating { color: #f7b32b; margin: 4px 0; }
        .rating-input span { font-size: 32px; cursor: pointer; color: #ccc; transition: 0.2s; }
        .order-list { max-height: 400px; overflow-y: auto; }
        .order-card { background: #fef3e2; border-radius: 20px; padding: 12px; margin-bottom: 12px; border-left: 4px solid #ff6b35; }
        .whatsapp-float { position: fixed; bottom: 20px; right: 20px; background: #25D366; color: white; width: 55px; height: 55px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 28px; text-decoration: none; z-index: 999; box-shadow: 0 4px 12px rgba(0,0,0,0.2); transition: 0.3s; }
        .whatsapp-float:hover { transform: scale(1.1); background: #128C7E; }
        footer { background: #2d3e2b; color: #efe1c6; text-align: center; padding: 16px; margin-top: 20px; }
        .toast { position: fixed; bottom: 80px; left: 50%; transform: translateX(-50%); background: #2c6e2f; color: white; padding: 10px 24px; border-radius: 40px; z-index: 1100; animation: slideUp 0.3s ease; }
        @keyframes slideUp { from { opacity: 0; transform: translateX(-50%) translateY(20px); } to { opacity: 1; transform: translateX(-50%) translateY(0); } }
        @media (max-width: 600px) { .product-grid { grid-template-columns: 1fr; } .nav-buttons { gap: 5px; } .nav-btn { padding: 6px 10px; font-size: 10px; } .logo-text h2 { font-size: 0.9rem; } .logo-img { width: 35px; height: 35px; font-size: 20px; } }
        .quantity-input { display: flex; align-items: center; gap: 12px; background: #f5f5f5; padding: 8px 15px; border-radius: 60px; justify-content: center; }
        .quantity-input button { background: #ff6b35; color: white; border: none; width: 40px; height: 40px; border-radius: 50%; font-size: 22px; cursor: pointer; transition: 0.3s; }
        .quantity-input button:hover { background: #e55a2b; transform: scale(1.05); }
        .quantity-input button:disabled { background: #ccc; cursor: not-allowed; transform: none; }
        .quantity-input span { font-size: 1.3rem; font-weight: bold; min-width: 50px; text-align: center; }
        .total-price-display { background: #ffe0b5; padding: 12px; border-radius: 60px; text-align: center; margin: 15px 0; }
        .total-price-display strong { font-size: 1.3rem; color: #ff6b35; }
        .cart-item { background: #faf0e2; border-radius: 16px; padding: 10px; margin-bottom: 8px; }
        .cart-remove { color: #ff6b35; cursor: pointer; font-weight: bold; background: none; border: none; font-size: 18px; }
        .empty-cart { text-align: center; padding: 30px; color: #999; }
        .delivery-charge-box { background: #f0f0f0; padding: 10px; border-radius: 20px; margin: 10px 0; }
        .contact-buttons { display: flex; gap: 10px; margin: 15px 0; flex-wrap: wrap; }
        .contact-btn { flex: 1; padding: 12px; border-radius: 40px; text-align: center; text-decoration: none; font-weight: bold; }
        .contact-btn.whatsapp { background: #25D366; color: white; }
        .contact-btn.phone { background: #2196F3; color: white; }
        .confirmation-message { text-align: center; padding: 20px; }
        .success-icon { font-size: 64px; color: #2c6e2f; margin-bottom: 15px; }
        .order-details-card { background: #f5f5f5; border-radius: 20px; padding: 15px; margin: 15px 0; text-align: left; }
        .order-details-card p { margin: 6px 0; display: flex; justify-content: space-between; }
        .whatsapp-btn-small { background: #25D366; color: white; border: none; padding: 10px 20px; border-radius: 40px; cursor: pointer; font-weight: bold; margin-top: 10px; display: inline-block; text-decoration: none; }
        
        .bkash-note {
            background: linear-gradient(135deg, #e84393, #d63384);
            color: white;
            padding: 15px;
            border-radius: 20px;
            margin: 10px 0;
            text-align: center;
        }
        .bkash-note h4 { margin-bottom: 8px; font-size: 1rem; }
        .bkash-note .number { font-size: 1.3rem; font-weight: bold; letter-spacing: 1px; background: rgba(255,255,255,0.2); display: inline-block; padding: 5px 15px; border-radius: 40px; margin: 8px 0; }
        .bkash-note small { display: block; margin-top: 8px; opacity: 0.9; font-size: 0.75rem; }
        .nagad-note {
            background: linear-gradient(135deg, #f39c12, #e67e22);
            color: white;
            padding: 15px;
            border-radius: 20px;
            margin: 10px 0;
            text-align: center;
        }
        .nagad-note h4 { margin-bottom: 8px; font-size: 1rem; }
        .nagad-note .number { font-size: 1.3rem; font-weight: bold; letter-spacing: 1px; background: rgba(255,255,255,0.2); display: inline-block; padding: 5px 15px; border-radius: 40px; margin: 8px 0; }
        .payment-note-tabs { display: flex; gap: 10px; margin-bottom: 10px; }
        .payment-tab { flex: 1; padding: 10px; text-align: center; background: #f0f0f0; border-radius: 40px; cursor: pointer; transition: 0.3s; }
        .payment-tab.active { background: #ff6b35; color: white; }
        .payment-detail { display: none; }
        .payment-detail.active { display: block; }
        
        /* মিনিমাম অর্ডার নোটিফিকেশন */
        .min-order-warning {
            background: #fff3cd;
            border: 1px solid #ffc107;
            color: #856404;
            padding: 10px;
            border-radius: 40px;
            text-align: center;
            margin: 10px 0;
            font-size: 0.85rem;
        }
    </style>
</head>
<body>

<div class="navbar">
    <div class="logo-area">
        <div class="logo-img">🍑</div>
        <div class="logo-text">
            <h2>Flavor-Fusion Rajshahi</h2>
            <p>খামার থেকে বাড়ি</p>
        </div>
    </div>
    <div class="nav-buttons">
        <button class="nav-btn" id="myOrdersBtn">📋 আমার অর্ডার</button>
        <div class="cart-icon" id="viewCartBtn">🛒 <span id="cartCount">0</span></div>
    </div>
</div>

<div class="slider-container" id="sliderContainer">
    <div class="slider-content" id="sliderContent"></div>
</div>

<div class="hero"><h1>আম, লিচু, কাঁঠাল</h1><p>সর্বনিম্ন অর্ডার ৩ কেজি · ফ্রেশ ডেলিভারি</p></div>

<div class="filter-bar">
    <div class="search-box"><input type="text" id="searchInput" placeholder="🔍 পণ্য খুঁজুন"></div>
    <div class="category-filters">
        <button class="filter-btn active" data-cat="all">সব</button>
        <button class="filter-btn" data-cat="mango">আম</button>
        <button class="filter-btn" data-cat="lichu">লিচু</button>
        <button class="filter-btn" data-cat="jackfruit">কাঁঠাল</button>
        <button class="filter-btn" data-cat="others">অন্যান্য</button>
    </div>
</div>

<div class="products"><div class="product-grid" id="productList"></div></div>

<!-- কার্ট মডাল -->
<div id="cartModal" class="modal">
    <div class="modal-container">
        <div class="modal-header"><h3>🛒 আপনার কার্ট</h3><span class="close-modal" id="closeCartBtn">&times;</span></div>
        <div id="cartContent"></div>
        <div class="contact-buttons">
            <a href="https://wa.me/8801712345678?text=আমি%20অর্ডার%20করতে%20চাই" target="_blank" class="contact-btn whatsapp"><i class="fab fa-whatsapp"></i> WhatsApp</a>
            <a href="tel:+8801712345678" class="contact-btn phone"><i class="fas fa-phone"></i> কল করুন</a>
        </div>
    </div>
</div>

<!-- অর্ডার ফর্ম মডাল (সরাসরি অর্ডার) -->
<div id="directOrderModal" class="modal">
    <div class="modal-container">
        <div class="modal-header"><h3>📦 অর্ডার ফর্ম</h3><span class="close-modal" id="closeDirectOrderBtn">&times;</span></div>
        <div id="directOrderContent"></div>
        <div class="contact-buttons">
            <a href="https://wa.me/8801712345678?text=আমি%20অর্ডার%20করতে%20চাই" target="_blank" class="contact-btn whatsapp"><i class="fab fa-whatsapp"></i> WhatsApp</a>
            <a href="tel:+8801712345678" class="contact-btn phone"><i class="fas fa-phone"></i> কল করুন</a>
        </div>
    </div>
</div>

<!-- কনফার্মেশন মডাল -->
<div id="confirmationModal" class="modal">
    <div class="modal-container">
        <div class="modal-header"><h3>✅ অর্ডার কনফার্মেশন</h3><span class="close-modal" id="closeConfirmationBtn">&times;</span></div>
        <div id="confirmationContent"></div>
        <div class="contact-buttons" style="margin-top:15px;">
            <a href="https://wa.me/8801712345678?text=আমি%20অর্ডার%20করতে%20চাই" target="_blank" class="contact-btn whatsapp"><i class="fab fa-whatsapp"></i> WhatsApp এ যোগাযোগ</a>
            <a href="tel:+8801712345678" class="contact-btn phone"><i class="fas fa-phone"></i> কল করুন</a>
        </div>
    </div>
</div>

<!-- কার্ট থেকে অর্ডার মডাল -->
<div id="checkoutModal" class="modal">
    <div class="modal-container">
        <div class="modal-header"><h3>📦 অর্ডার কনফার্মেশন</h3><span class="close-modal" id="closeCheckoutBtn">&times;</span></div>
        <div id="checkoutContent"></div>
        <div class="contact-buttons">
            <a href="https://wa.me/8801712345678?text=আমি%20অর্ডার%20করতে%20চাই" target="_blank" class="contact-btn whatsapp"><i class="fab fa-whatsapp"></i> WhatsApp</a>
            <a href="tel:+8801712345678" class="contact-btn phone"><i class="fas fa-phone"></i> কল করুন</a>
        </div>
    </div>
</div>

<!-- রিভিউ মডাল -->
<div id="reviewModal" class="modal">
    <div class="modal-container">
        <div class="modal-header"><h3>📝 রিভিউ লিখুন</h3><span class="close-modal" id="closeReviewModalBtn">&times;</span></div>
        <div id="reviewModalBody"></div>
    </div>
</div>

<!-- আমার অর্ডার মডাল -->
<div id="myOrdersModal" class="modal">
    <div class="modal-container">
        <div class="modal-header"><h3>📋 আমার অর্ডার সমূহ</h3><span class="close-modal" id="closeMyOrdersBtn">&times;</span></div>
        <div id="myOrdersContent">
            <div class="verify-phone" style="text-align: center; padding: 20px;">
                <p style="margin-bottom: 15px;">আপনার অর্ডার দেখতে আপনার মোবাইল নম্বরটি দিন</p>
                <div style="margin: 20px 0;"><input type="tel" id="verifyPhoneInput" placeholder="01XXXXXXXXX" style="padding: 12px; border-radius: 40px; border: 1px solid #ffb88c; width: 90%; font-size: 1rem;"></div>
                <button id="verifyPhoneBtn" class="confirm-btn" style="margin-top: 10px;">✅ আমার অর্ডার দেখুন</button>
            </div>
            <div id="myOrdersList" style="display: none;"></div>
        </div>
    </div>
</div>

<a href="https://wa.me/8801712345678?text=আমি%20অর্ডার%20করতে%20চাই" class="whatsapp-float" target="_blank"><i class="fab fa-whatsapp"></i></a>
<footer><p>🍑 Flavor-Fusion Rajshahi — পেমেন্ট: bKash, Nagad, COD</p></footer>

<script>
    // ========== কনফিগারেশন ==========
    const GOOGLE_SHEETS_WEBHOOK_URL = "YOUR_GOOGLE_SHEETS_WEBHOOK_URL";
    const DELIVERY_CHARGE = 0;  // 0 = ফ্রি
    const MINIMUM_ORDER_KG = 3;  // নূন্যতম অর্ডার ৩ কেজি
    
    // bKash এবং Nagad নম্বর (আপনার নিজের নম্বর দিন)
    const BKASH_NUMBER = "017XXXXXXXX";
    const NAGAD_NUMBER = "017XXXXXXXX";
    
    // ========== স্লাইডার কন্টেন্ট ==========
    const sliderItems = [
        { text: "🎉 ১০% ডিসকাউন্ট", subtext: "প্রথম অর্ডারে পাবেন ১০% ছাড়!", icon: "🎉", bgImage: "linear-gradient(135deg, #ff6b35, #ff8c42)" },
        { text: "🚚 ফ্রি ডেলিভারি", subtext: "৩ কেজির বেশি অর্ডার ফ্রি!", icon: "🚚", bgImage: "linear-gradient(135deg, #e55a2b, #ff7e5e)" },
        { text: "⭐ বাজারের সেরা আম", subtext: "হিমসাগর, ল্যাংড়া, ফজলি", icon: "🥭", bgImage: "linear-gradient(135deg, #ff9a45, #ffc371)" },
        { text: "📦 নূন্যতম ৩ কেজি", subtext: "৩ কেজির কম অর্ডার গ্রহণযোগ্য নয়", icon: "📦", bgImage: "linear-gradient(135deg, #ff6b35, #ffb347)" },
        { text: "🕒 ২৪ ঘন্টায় ডেলিভারি", subtext: "রাজশাহী শহরে দ্রুত ডেলিভারি", icon: "⏱️", bgImage: "linear-gradient(135deg, #e8741a, #ffa559)" },
        { text: "💰 সাশ্রয়ী মূল্য", subtext: "সরাসরি খামার থেকে আপনার বাড়ি", icon: "💰", bgImage: "linear-gradient(135deg, #ff8c42, #ffb347)" }
    ];
    
    let sliderIndex = 0;
    let animationDirection = true;
    
    function updateSlider() {
        const item = sliderItems[sliderIndex];
        const sliderContent = document.getElementById('sliderContent');
        animationDirection = !animationDirection;
        const animationClass = animationDirection ? 'slideInRight' : 'slideInLeft';
        sliderContent.style.animation = 'none';
        sliderContent.offsetHeight;
        sliderContent.style.animation = `${animationClass} 0.6s ease`;
        sliderContent.innerHTML = `<div class="slider-text"><h2>${item.text}</h2><p>${item.subtext}</p></div><div class="slider-img">${item.icon}</div>`;
        document.getElementById('sliderContainer').style.background = item.bgImage;
        sliderIndex = (sliderIndex + 1) % sliderItems.length;
    }
    setInterval(updateSlider, 3000);
    updateSlider();

    const STORAGE_KEYS = { ORDERS: 'flavor_fusion_orders', REVIEWS: 'flavor_fusion_reviews', CART: 'flavor_fusion_cart' };

    const products = [
        { id:1, name:"হিমসাগর আম", price:130, unit:"কেজি", img:"https://images.unsplash.com/photo-1553279768-865429fa0078?w=400", category:"mango" },
        { id:2, name:"ল্যাংড়া আম", price:110, unit:"কেজি", img:"https://images.unsplash.com/photo-1521737604893-d14cc237f11d?w=400", category:"mango" },
        { id:3, name:"বোম্বাই লিচু", price:180, unit:"কেজি", img:"https://images.unsplash.com/photo-1513742966344-788b15e0d568?w=400", category:"lichu" },
        { id:4, name:"মাদ্রাজি লিচু", price:150, unit:"কেজি", img:"https://images.unsplash.com/photo-1596496181865-9626a1b9d11e?w=400", category:"lichu" },
        { id:5, name:"পাকা কাঁঠাল", price:95, unit:"কেজি", img:"https://images.unsplash.com/photo-1643513108087-456752cfd58c?w=400", category:"jackfruit" },
        { id:6, name:"কামরাঙ্গা", price:70, unit:"কেজি", img:"https://images.unsplash.com/photo-1615485290382-441e4d049cb5?w=400", category:"others" },
        { id:7, name:"ফজলি আম", price:160, unit:"কেজি", img:"https://images.unsplash.com/photo-1587520387446-2b7a3ad69ae7?w=400", category:"mango" }
    ];

    let allOrders = JSON.parse(localStorage.getItem(STORAGE_KEYS.ORDERS)) || [];
    let allReviews = JSON.parse(localStorage.getItem(STORAGE_KEYS.REVIEWS)) || {};
    let cart = JSON.parse(localStorage.getItem(STORAGE_KEYS.CART)) || [];

    if(Object.keys(allReviews).length === 0){
        allReviews = { 
            1: [{ name:"রাজিব", rating:5, comment:"অসাধারণ মিষ্টি!", image:"", date: new Date().toLocaleString() }], 
            3: [{ name:"নিশাত", rating:5, comment:"লিচু দারুণ!", image:"", date: new Date().toLocaleString() }] 
        };
        localStorage.setItem(STORAGE_KEYS.REVIEWS, JSON.stringify(allReviews));
    }

    let currentFilter = "all", searchQuery = "", currentProductForReview = null, tempImageBase64 = "";
    let currentDirectProduct = null;
    let currentKgValue = MINIMUM_ORDER_KG;

    function saveOrders() { localStorage.setItem(STORAGE_KEYS.ORDERS, JSON.stringify(allOrders)); }
    function saveCart() { localStorage.setItem(STORAGE_KEYS.CART, JSON.stringify(cart)); updateCartCount(); }
    function getTotalWithDelivery(subtotal) { let delivery = DELIVERY_CHARGE; let deliveryText = delivery === 0 ? "ফ্রি" : `৳${delivery}`; return { total: subtotal + delivery, delivery: delivery, deliveryText: deliveryText }; }

    async function saveOrderToGoogleSheets(orderData) {
        if(GOOGLE_SHEETS_WEBHOOK_URL === "YOUR_GOOGLE_SHEETS_WEBHOOK_URL") { console.log("⚠️ Google Sheets URL সেট করা নেই"); return false; }
        try { 
            await fetch(GOOGLE_SHEETS_WEBHOOK_URL, { method: 'POST', mode: 'no-cors', headers: { 'Content-Type': 'application/json' }, body: JSON.stringify(orderData) }); 
            return true; 
        } catch(error) { console.error("❌ Error:", error); return false; }
    }

    function showConfirmation(orderData) {
        const itemsList = orderData.items.map(item => `<p style="margin:5px 0;"><strong>${item.name}</strong> : ${item.quantityKg} কেজি = ৳${item.totalPrice}</p>`).join('');
        const deliveryText = orderData.deliveryCharge === 0 ? "ফ্রি" : `৳${orderData.deliveryCharge}`;
        const whatsappMsg = `🍑 Flavor-Fusion অর্ডার\n━━━━━━━━━━━━━━━━\n👤 নাম: ${orderData.name}\n📞 ফোন: ${orderData.phone}\n🏠 ঠিকানা: ${orderData.address}\n━━━━━━━━━━━━━━━━\n📦 পণ্য:\n${orderData.items.map(i => `${i.name} ${i.quantityKg} কেজি = ৳${i.totalPrice}`).join('\n')}\n━━━━━━━━━━━━━━━━\n🚚 ডেলিভারি চার্জ: ${deliveryText}\n💰 মোট: ৳${orderData.total}\n💳 পেমেন্ট: ${orderData.paymentMethod === 'cod' ? 'ক্যাশ অন ডেলিভারি' : 'bKash/নগদ'}\n━━━━━━━━━━━━━━━━\n📅 তারিখ: ${orderData.date}\n\nধন্যবাদ! 🍑`;
        const waLink = `https://wa.me/8801712345678?text=${encodeURIComponent(whatsappMsg)}`;
        document.getElementById('confirmationContent').innerHTML = `
            <div class="confirmation-message">
                <div class="success-icon">🎉</div>
                <h2 style="color:#2c6e2f;">আপনার অর্ডার কনফার্ম হয়েছে!</h2>
                <p style="margin: 10px 0; color: #555;">শীগ্রই আমরা আপনার সাথে যোগাযোগ করব।</p>
                <div class="order-details-card">
                    <h4>📋 অর্ডার ডিটেইলস:</h4>
                    <p><strong>অর্ডার নং:</strong> #${orderData.id}</p>
                    <p><strong>নাম:</strong> ${orderData.name}</p>
                    <p><strong>মোবাইল:</strong> ${orderData.phone}</p>
                    <p><strong>ঠিকানা:</strong> ${orderData.address}</p>
                    <p><strong>তারিখ:</strong> ${orderData.date}</p><hr>
                    <strong>📦 পণ্য:</strong>${itemsList}<hr>
                    <p><strong>পণ্যের মূল্য:</strong> ৳${orderData.subtotal}</p>
                    <p><strong>ডেলিভারি চার্জ:</strong> ${deliveryText}</p>
                    <p><strong>মোট টাকা:</strong> ৳${orderData.total}</p>
                    <p><strong>পেমেন্ট পদ্ধতি:</strong> ${orderData.paymentMethod === 'cod' ? 'ক্যাশ অন ডেলিভারি' : 'bKash/নগদ'} ${orderData.paymentMethod === 'bkash' && orderData.trxId !== 'COD' ? `(TrxID: ${orderData.trxId})` : ''}</p>
                </div>
                <a href="${waLink}" target="_blank" class="whatsapp-btn-small"><i class="fab fa-whatsapp"></i> WhatsApp এ শেয়ার করুন</a>
                <button onclick="closeAllModalsAndReset()" class="confirm-btn" style="background:#ff6b35; margin-top:10px;">ঠিক আছে</button>
            </div>`;
        document.getElementById('confirmationModal').style.display = 'flex';
    }
    
    function closeAllModalsAndReset() {
        document.getElementById('confirmationModal').style.display = 'none';
        document.getElementById('directOrderModal').style.display = 'none';
        document.getElementById('checkoutModal').style.display = 'none';
        document.getElementById('cartModal').style.display = 'none';
        if(cart.length === 0) updateCartCount();
    }
    window.closeConfirmation = closeAllModalsAndReset;

    function getPaymentNoteHTML() {
        return `
            <div class="payment-note-tabs">
                <div class="payment-tab active" data-payment="bkash">📱 bKash</div>
                <div class="payment-tab" data-payment="nagad">💳 Nagad</div>
            </div>
            <div id="bkashDetail" class="payment-detail active">
                <div class="bkash-note">
                    <i class="fab fa-bkash" style="font-size: 24px;"></i>
                    <h4>bKash এ পেমেন্ট করুন</h4>
                    <div class="number">${BKASH_NUMBER}</div>
                    <p>উপরের নম্বরে <strong>সঠিক টাকা</strong> Send Money করুন</p>
                    <small>পেমেন্ট করার পর নিচের ঘরে TrxID লিখুন</small>
                </div>
            </div>
            <div id="nagadDetail" class="payment-detail">
                <div class="nagad-note">
                    <i class="fas fa-mobile-alt" style="font-size: 24px;"></i>
                    <h4>Nagad এ পেমেন্ট করুন</h4>
                    <div class="number">${NAGAD_NUMBER}</div>
                    <p>উপরের নম্বরে <strong>সঠিক টাকা</strong> Send Money করুন</p>
                    <small>পেমেন্ট করার পর নিচের ঘরে TrxID লিখুন</small>
                </div>
            </div>
            <div class="form-group" style="margin-top: 10px;">
                <input type="text" id="trxId" placeholder="TrxID লিখুন (যেমন: 8AS7F9G3H)" style="width:100%; padding:12px; border-radius:40px; border:1px solid #ffb88c;">
            </div>
        `;
    }
    
    function initPaymentTabs() {
        const tabs = document.querySelectorAll('.payment-tab');
        tabs.forEach(tab => {
            tab.onclick = function() {
                tabs.forEach(t => t.classList.remove('active'));
                this.classList.add('active');
                const paymentType = this.dataset.payment;
                document.getElementById('bkashDetail').classList.toggle('active', paymentType === 'bkash');
                document.getElementById('nagadDetail').classList.toggle('active', paymentType === 'nagad');
            };
        });
    }

    function renderProducts() {
        let filtered = products.filter(p => (currentFilter==="all" || p.category===currentFilter) && (!searchQuery || p.name.toLowerCase().includes(searchQuery.toLowerCase())));
        const deliveryBadge = DELIVERY_CHARGE === 0 ? '<span class="delivery-badge">🚚 ফ্রি ডেলিভারি</span>' : '';
        const minOrderBadge = `<span class="min-order-badge">📦 নূন্যতম ${MINIMUM_ORDER_KG} কেজি</span>`;
        document.getElementById('productList').innerHTML = filtered.map(prod => {
            let reviewCount = allReviews[prod.id] ? allReviews[prod.id].length : 0;
            return `<div class="product-card">${minOrderBadge}${deliveryBadge}<img src="${prod.img}" onerror="this.src='https://placehold.co/400x300'"><h3>${prod.name}</h3><div class="price">৳${prod.price}/${prod.unit}</div><div class="per-kg">💰 প্রতি কেজি: ৳${prod.price}</div><div class="review-trigger" onclick="openReviewModal(${prod.id})">⭐ রিভিউ (${reviewCount}) দেখুন ও লিখুন</div><div class="card-buttons"><button class="btn-add" onclick="openAddToCart(${prod.id})">🛒 কার্টে যোগ</button><button class="btn-buy" onclick="openDirectOrder(${prod.id})">⚡ অর্ডার নাও</button></div></div>`;
        }).join('');
    }

    window.openAddToCart = function(productId) {
        let product = products.find(p => p.id === productId);
        if(!product) return;
        let modalHtml = `
            <div style="text-align: center; margin-bottom: 20px;"><h2 style="color:#ff6b35;">${product.name}</h2><p style="color:#666;">প্রতি কেজি: ৳${product.price}</p></div>
            <div class="min-order-warning">⚠️ নূন্যতম অর্ডার ${MINIMUM_ORDER_KG} কেজি</div>
            <div class="form-group"><label>📦 কত কেজি নিবেন? (ন্যূনতম ${MINIMUM_ORDER_KG} কেজি)</label><div class="quantity-input">
                <button onclick="window.changeCartKg(-0.5)" id="cartMinusBtn">−</button>
                <span id="cartKgValue">${MINIMUM_ORDER_KG}</span>
                <button onclick="window.changeCartKg(0.5)" id="cartPlusBtn">+</button>
            </div></div>
            <div class="total-price-display">মোট দাম: <strong id="cartTotalPrice">৳${(product.price * MINIMUM_ORDER_KG).toFixed(2)}</strong></div>
            <button class="confirm-btn" id="cartConfirmBtn" onclick="window.confirmAddToCart(${product.id})">✅ কার্টে যোগ করুন</button>`;
        let tempModal = document.createElement('div');
        tempModal.className = 'modal';
        tempModal.style.display = 'flex';
        tempModal.innerHTML = `<div class="modal-container" style="max-width:400px;"><div class="modal-header"><h3>🛒 কার্টে যোগ করুন</h3><span class="close-modal" onclick="this.closest('.modal').remove()">&times;</span></div>${modalHtml}</div>`;
        document.body.appendChild(tempModal);
        window.currentCartProduct = product;
        window.currentCartKg = MINIMUM_ORDER_KG;
        
        window.changeCartKg = function(change) {
            let newKg = window.currentCartKg + change;
            if(newKg < MINIMUM_ORDER_KG) newKg = MINIMUM_ORDER_KG;
            if(newKg > 50) newKg = 50;
            window.currentCartKg = newKg;
            document.getElementById('cartKgValue').innerText = newKg.toFixed(1);
            document.getElementById('cartTotalPrice').innerHTML = `৳${(window.currentCartProduct.price * newKg).toFixed(2)}`;
            
            // মাইনাস বাটন ডিজেবল করার লজিক
            const minusBtn = document.getElementById('cartMinusBtn');
            if(minusBtn) {
                if(window.currentCartKg <= MINIMUM_ORDER_KG) {
                    minusBtn.disabled = true;
                    minusBtn.style.opacity = '0.5';
                } else {
                    minusBtn.disabled = false;
                    minusBtn.style.opacity = '1';
                }
            }
        };
        
        // প্রাথমিকভাবে মাইনাস বাটন ডিজেবল করে দাও
        setTimeout(() => {
            const minusBtn = document.getElementById('cartMinusBtn');
            if(minusBtn) {
                minusBtn.disabled = true;
                minusBtn.style.opacity = '0.5';
            }
        }, 50);
        
        window.confirmAddToCart = function(productId) {
            let existing = cart.find(item => item.id === productId);
            if(existing) { existing.quantityKg += window.currentCartKg; existing.totalPrice = existing.quantityKg * existing.pricePerKg; } 
            else { cart.push({ id: window.currentCartProduct.id, name: window.currentCartProduct.name, pricePerKg: window.currentCartProduct.price, quantityKg: window.currentCartKg, totalPrice: window.currentCartProduct.price * window.currentCartKg }); }
            saveCart(); showToast(`${window.currentCartKg} কেজি ${window.currentCartProduct.name} কার্টে যোগ হয়েছে`); tempModal.remove();
        };
    };

    window.openDirectOrder = function(productId) {
        let product = products.find(p => p.id === productId);
        if(!product) return;
        currentDirectProduct = product;
        let defaultKg = MINIMUM_ORDER_KG;
        let subtotal = product.price * defaultKg;
        let { total, delivery, deliveryText } = getTotalWithDelivery(subtotal);
        document.getElementById('directOrderContent').innerHTML = `
            <div style="text-align: center; margin-bottom: 20px;"><h2 style="color:#ff6b35;">${product.name}</h2><p style="color:#666;">প্রতি কেজি: ৳${product.price}</p></div>
            <div class="min-order-warning">⚠️ নূন্যতম অর্ডার ${MINIMUM_ORDER_KG} কেজি</div>
            <div class="form-group"><label>📦 আপনি কত কেজি নিবেন? (ন্যূনতম ${MINIMUM_ORDER_KG} কেজি)</label><div class="quantity-input">
                <button onclick="changeDirectKg(-0.5)" id="directMinusBtn">−</button>
                <span id="directKgValue">${defaultKg}</span>
                <button onclick="changeDirectKg(0.5)" id="directPlusBtn">+</button>
            </div></div>
            <div class="delivery-charge-box"><p>🚚 ডেলিভারি চার্জ: <strong>${deliveryText}</strong></p><p>🛒 পণ্যের মূল্য: <strong id="directSubtotal">৳${subtotal}</strong></p><p>💰 মোট দাম: <strong id="directTotalPrice">৳${total}</strong></p></div>
            <div class="form-group"><label>👤 আপনার নাম</label><input type="text" id="orderName" placeholder="লুৎফর রহমান"></div>
            <div class="form-group"><label>📞 মোবাইল নম্বর</label><input type="tel" id="orderPhone" placeholder="01XXXXXXXXX"></div>
            <div class="form-group"><label>🏠 সম্পূর্ণ ঠিকানা</label><textarea id="orderAddress" rows="2" placeholder="জেলা, থানা, গ্রাম/রোড, বাসা নং"></textarea></div>
            <div class="payment-option"><label><input type="radio" name="payMethod" value="cod" checked> 💵 ক্যাশ অন ডেলিভারি</label><label><input type="radio" name="payMethod" value="bkash"> 📱 bKash/নগদ</label></div>
            <div id="mobilePaymentSection" style="display:none;">${getPaymentNoteHTML()}</div>
            <button class="confirm-btn" id="directOrderBtn" onclick="submitDirectOrder()">✅ অর্ডার কনফার্ম করুন</button>`;
        document.getElementById('directOrderModal').style.display = 'flex';
        
        // মাইনাস বাটন প্রাথমিকভাবে ডিজেবল
        setTimeout(() => {
            const minusBtn = document.getElementById('directMinusBtn');
            if(minusBtn) {
                minusBtn.disabled = true;
                minusBtn.style.opacity = '0.5';
            }
        }, 50);
        
        setTimeout(() => {
            document.querySelectorAll('input[name="payMethod"]').forEach(radio => {
                radio.onchange = function() {
                    const section = document.getElementById('mobilePaymentSection');
                    if(this.value === 'bkash') {
                        section.style.display = 'block';
                        initPaymentTabs();
                    } else {
                        section.style.display = 'none';
                    }
                };
            });
        }, 100);
    };
    
    window.changeDirectKg = function(change) {
        let kgSpan = document.getElementById('directKgValue');
        let currentKg = parseFloat(kgSpan.innerText);
        let newKg = currentKg + change;
        if(newKg < MINIMUM_ORDER_KG) newKg = MINIMUM_ORDER_KG;
        if(newKg > 50) newKg = 50;
        kgSpan.innerText = newKg.toFixed(1);
        if(currentDirectProduct) {
            let subtotal = currentDirectProduct.price * newKg;
            let { total, delivery, deliveryText } = getTotalWithDelivery(subtotal);
            document.getElementById('directSubtotal').innerHTML = `৳${subtotal.toFixed(2)}`;
            document.getElementById('directTotalPrice').innerHTML = `৳${total.toFixed(2)}`;
        }
        
        // মাইনাস বাটন ডিজেবল করার লজিক
        const minusBtn = document.getElementById('directMinusBtn');
        if(minusBtn) {
            if(newKg <= MINIMUM_ORDER_KG) {
                minusBtn.disabled = true;
                minusBtn.style.opacity = '0.5';
            } else {
                minusBtn.disabled = false;
                minusBtn.style.opacity = '1';
            }
        }
    };
    
    window.submitDirectOrder = async function() {
        if(!currentDirectProduct) return;
        let name = document.getElementById('orderName')?.value.trim();
        let phone = document.getElementById('orderPhone')?.value.trim();
        let address = document.getElementById('orderAddress')?.value.trim();
        let kgValue = parseFloat(document.getElementById('directKgValue')?.innerText || MINIMUM_ORDER_KG);
        let paymentMethod = document.querySelector('input[name="payMethod"]:checked')?.value;
        let trxId = '';
        
        if(kgValue < MINIMUM_ORDER_KG) {
            showToast(`❌ নূন্যতম অর্ডার ${MINIMUM_ORDER_KG} কেজি হতে হবে`);
            return;
        }
        
        if(paymentMethod === 'bkash') {
            let activeTab = document.querySelector('.payment-tab.active');
            trxId = document.getElementById('trxId')?.value.trim();
            if(!trxId) { showToast("❌ দয়া করে TrxID দিন"); return; }
        } else {
            trxId = 'COD';
        }
        if(!name || !phone || !address) { showToast("❌ দয়া করে নাম, মোবাইল ও ঠিকানা দিন"); return; }
        if(!/^01[3-9]\d{8}$/.test(phone)) { showToast("❌ সঠিক মোবাইল নম্বর দিন (01xxxxxxxxx)"); return; }
        
        let subtotal = currentDirectProduct.price * kgValue;
        let { total, delivery } = getTotalWithDelivery(subtotal);
        let orderData = { id: Date.now(), name, phone, address, items: [{ id: currentDirectProduct.id, name: currentDirectProduct.name, pricePerKg: currentDirectProduct.price, quantityKg: kgValue, totalPrice: subtotal }], subtotal, deliveryCharge: delivery, total, paymentMethod, trxId, date: new Date().toLocaleString('bn-BD'), status: 'pending' };
        await saveOrderToGoogleSheets(orderData);
        allOrders.unshift(orderData);
        saveOrders();
        showConfirmation(orderData);
        document.getElementById('directOrderModal').style.display = 'none';
        currentDirectProduct = null;
    };
    
    function showCart() {
        if(cart.length === 0) { document.getElementById('cartContent').innerHTML = '<div class="empty-cart">🛒 আপনার কার্ট খালি</div>'; }
        else {
            let totalKg = cart.reduce((s,i) => s + i.quantityKg, 0);
            let subtotal = cart.reduce((s,i) => s + i.totalPrice, 0);
            let { total, delivery, deliveryText } = getTotalWithDelivery(subtotal);
            
            // কার্টের মোট কেজি চেক করে মেসেজ দেখানো
            const minOrderWarning = totalKg < MINIMUM_ORDER_KG ? `<div class="min-order-warning">⚠️ নূন্যতম অর্ডার ${MINIMUM_ORDER_KG} কেজি প্রয়োজন। বর্তমানে ${totalKg} কেজি</div>` : '';
            
            document.getElementById('cartContent').innerHTML = `${minOrderWarning}${cart.map((item, idx) => `<div class="cart-item"><div style="display:flex; justify-content:space-between;"><div><strong>${item.name}</strong><br>${item.quantityKg} কেজি = ৳${item.totalPrice}</div><button class="cart-remove" onclick="removeFromCart(${idx})">🗑️</button></div></div>`).join('')}<div class="delivery-charge-box"><p>🛒 পণ্যের মূল্য: <strong>৳${subtotal}</strong></p><p>🚚 ডেলিভারি চার্জ: <strong>${deliveryText}</strong></p><p>💰 মোট দাম: <strong>৳${total}</strong></p></div><button class="confirm-btn" onclick="checkoutFromCart()" ${totalKg < MINIMUM_ORDER_KG ? 'disabled style="background:#aaa; cursor:not-allowed;"' : ''}>✅ অর্ডার কনফার্ম করুন</button>`;
        }
        document.getElementById('cartModal').style.display = 'flex';
    }
    
    window.removeFromCart = function(idx) { cart.splice(idx, 1); saveCart(); showCart(); showToast("পণ্য কার্ট থেকে সরানো হয়েছে"); };
    
    function checkoutFromCart() {
        if(cart.length === 0) { showToast("কার্ট খালি"); return; }
        let totalKg = cart.reduce((s,i) => s + i.quantityKg, 0);
        if(totalKg < MINIMUM_ORDER_KG) {
            showToast(`❌ নূন্যতম অর্ডার ${MINIMUM_ORDER_KG} কেজি হতে হবে। বর্তমানে ${totalKg} কেজি`);
            return;
        }
        
        let subtotal = cart.reduce((s,i) => s + i.totalPrice, 0);
        let { total, delivery, deliveryText } = getTotalWithDelivery(subtotal);
        document.getElementById('checkoutContent').innerHTML = `<div class="order-summary">${cart.map(i => `<div class="order-summary-item"><span>${i.name} x ${i.quantityKg} কেজি</span><span>৳${i.totalPrice}</span></div>`).join('')}<div class="order-summary-item"><span>🚚 ডেলিভারি চার্জ</span><span>${deliveryText}</span></div><div style="text-align:right; font-weight:bold; margin-top:8px;">মোট: ৳${total}</div></div><div class="form-group"><label>👤 আপনার নাম</label><input type="text" id="chkName" placeholder="আপনার নাম"></div><div class="form-group"><label>📞 মোবাইল নম্বর</label><input type="tel" id="chkPhone" placeholder="01XXXXXXXXX"></div><div class="form-group"><label>🏠 ঠিকানা</label><textarea id="chkAddress" rows="2" placeholder="ঠিকানা লিখুন"></textarea></div><div class="payment-option"><label><input type="radio" name="pay" value="cod" checked> 💵 ক্যাশ অন ডেলিভারি</label><label><input type="radio" name="pay" value="bkash"> 📱 bKash/নগদ</label></div><div id="chkMobileSection" style="display:none;">${getPaymentNoteHTML()}</div><button class="confirm-btn" onclick="submitCartOrder()">✅ অর্ডার কনফার্ম করুন</button>`;
        document.getElementById('checkoutModal').style.display = 'flex';
        document.getElementById('cartModal').style.display = 'none';
        setTimeout(() => {
            document.querySelectorAll('input[name="pay"]').forEach(r => {
                r.onchange = () => {
                    const section = document.getElementById('chkMobileSection');
                    if(r.value === 'bkash') { section.style.display = 'block'; initPaymentTabs(); } 
                    else { section.style.display = 'none'; }
                };
            });
        }, 100);
    }
    
    window.submitCartOrder = async function() {
        let name = document.getElementById('chkName')?.value.trim();
        let phone = document.getElementById('chkPhone')?.value.trim();
        let address = document.getElementById('chkAddress')?.value.trim();
        let paymentMethod = document.querySelector('input[name="pay"]:checked')?.value;
        let trxId = '';
        
        let totalKg = cart.reduce((s,i) => s + i.quantityKg, 0);
        if(totalKg < MINIMUM_ORDER_KG) {
            showToast(`❌ নূন্যতম অর্ডার ${MINIMUM_ORDER_KG} কেজি হতে হবে`);
            return;
        }
        
        if(paymentMethod === 'bkash') {
            let activeTab = document.querySelector('.payment-tab.active');
            trxId = document.getElementById('trxId')?.value.trim();
            if(!trxId) { showToast("❌ দয়া করে TrxID দিন"); return; }
        } else { trxId = 'COD'; }
        if(!name || !phone || !address) { showToast("সব তথ্য দিন"); return; }
        if(!/^01[3-9]\d{8}$/.test(phone)) { showToast("সঠিক মোবাইল নম্বর দিন"); return; }
        
        let subtotal = cart.reduce((s,i) => s + i.totalPrice, 0);
        let { total, delivery } = getTotalWithDelivery(subtotal);
        let orderData = { id: Date.now(), name, phone, address, items: [...cart], subtotal, deliveryCharge: delivery, total, paymentMethod, trxId, date: new Date().toLocaleString('bn-BD'), status: 'pending' };
        await saveOrderToGoogleSheets(orderData);
        allOrders.unshift(orderData);
        saveOrders();
        cart = [];
        saveCart();
        showConfirmation(orderData);
        document.getElementById('checkoutModal').style.display = 'none';
    };
    
    function showMyOrdersModal() {
        document.getElementById('verifyPhoneInput').value = '';
        document.getElementById('myOrdersList').style.display = 'none';
        document.getElementById('verifyPhoneInput').style.display = 'block';
        document.getElementById('verifyPhoneBtn').style.display = 'block';
        document.getElementById('myOrdersModal').style.display = 'flex';
    }
    
    function verifyAndShowOrders() {
        let phone = document.getElementById('verifyPhoneInput').value.trim();
        if(!phone) { showToast("মোবাইল নম্বর দিন"); return; }
        if(!/^01[3-9]\d{8}$/.test(phone)) { showToast("সঠিক মোবাইল নম্বর দিন"); return; }
        let myOrders = allOrders.filter(order => order.phone === phone);
        if(myOrders.length === 0) { document.getElementById('myOrdersList').innerHTML = '<div class="empty-cart">📭 আপনার কোনো অর্ডার নেই</div>'; }
        else {
            document.getElementById('myOrdersList').innerHTML = `<div class="order-list">${myOrders.map(o => `<div class="order-card"><div style="display:flex; justify-content:space-between;"><div><strong>#${o.id}</strong></div><small>${o.date}</small></div><div style="margin-top:8px;">📦 ${o.items.map(i => `${i.name} <strong>${i.quantityKg} কেজি</strong> = ৳${i.totalPrice}`).join('<br>')}</div><div style="margin-top:8px;">🚚 ডেলিভারি চার্জ: ${o.deliveryCharge === 0 ? 'ফ্রি' : `৳${o.deliveryCharge}`}</div><div style="margin-top:8px; display:flex; justify-content:space-between;"><span>💰 মোট: <strong>৳${o.total}</strong></span><span>💳 ${o.paymentMethod === 'cod' ? 'ক্যাশ অন' : 'bKash/Nagad'}</span></div><div style="margin-top:5px; color:#666;">🏠 ${o.address}</div><div class="order-status">✅ অর্ডার গ্রহণ করা হয়েছে</div></div>`).join('')}</div>`;
        }
        document.getElementById('verifyPhoneInput').style.display = 'none';
        document.getElementById('verifyPhoneBtn').style.display = 'none';
        document.getElementById('myOrdersList').style.display = 'block';
    }
    
    window.openReviewModal = function(id) {
        currentProductForReview = id;
        let prod = products.find(p=>p.id===id);
        let reviews = allReviews[id] || [];
        document.getElementById('reviewModalBody').innerHTML = `<div><strong style="font-size:1.2rem;">🍑 ${prod.name}</strong></div><div id="reviewsList" style="max-height:250px; overflow-y:auto;">${reviews.map(r=>`<div class="review-item"><b>${r.name}</b> <span class="star-rating">${'★'.repeat(r.rating)}${'☆'.repeat(5-r.rating)}</span><p>${r.comment}</p>${r.image?`<img src="${r.image}" class="review-img">`:''}<small>${r.date}</small></div>`).join('')}</div><hr><h4>✍️ আপনার রিভিউ দিন</h4><div class="form-group"><input type="text" id="revName" placeholder="আপনার নাম"></div><div class="rating-input" id="starSel"></div><textarea id="revComment" rows="3" placeholder="মন্তব্য লিখুন..."></textarea><div class="form-group"><input type="file" id="revImg" accept="image/*"><div id="imgPrev"></div></div><button id="submitReviewBtn" class="confirm-btn">⭐ রিভিউ পোস্ট করুন</button>`;
        let starDiv = document.getElementById('starSel');
        let selected=0;
        starDiv.innerHTML = [1,2,3,4,5].map(s=>`<span data-rate="${s}" style="font-size:32px;">★</span>`).join('');
        starDiv.querySelectorAll('span').forEach(span=>{
            span.onmouseover=()=>{ let v=parseInt(span.dataset.rate); starDiv.querySelectorAll('span').forEach((s,i)=>s.style.color= i<v ? '#f7b32b':'#ccc'); };
            span.onclick=()=>{ selected=parseInt(span.dataset.rate); starDiv.querySelectorAll('span').forEach((s,i)=>s.style.color= i<selected ? '#f7b32b':'#ccc'); };
        });
        document.getElementById('revImg').onchange=e=>{ let f=e.target.files[0]; if(f){ let rd=new FileReader(); rd.onload=ev=>{ tempImageBase64=ev.target.result; document.getElementById('imgPrev').innerHTML=`<img src="${tempImageBase64}" style="width:70px; border-radius:12px;">`; }; rd.readAsDataURL(f); } };
        document.getElementById('submitReviewBtn').onclick=()=>{
            let name=document.getElementById('revName').value.trim(); let comment=document.getElementById('revComment').value.trim();
            if(!name||!comment||selected===0){ alert("নাম, মন্তব্য ও রেটিং দিন"); return; }
            let newRev={ name, rating:selected, comment, image:tempImageBase64||"", date:new Date().toLocaleString() };
            if(!allReviews[id]) allReviews[id]=[];
            allReviews[id].unshift(newRev);
            localStorage.setItem(STORAGE_KEYS.REVIEWS, JSON.stringify(allReviews));
            tempImageBase64=""; document.getElementById('reviewModal').style.display='none'; renderProducts(); showToast("রিভিউ পোস্ট হয়েছে!");
        };
        document.getElementById('reviewModal').style.display='flex';
    };
    
    function updateCartCount() { let count = cart.reduce((s,i) => s + i.quantityKg, 0); document.getElementById('cartCount').innerText = count.toFixed(1); }
    function showToast(m) { let t = document.createElement('div'); t.className = 'toast'; t.innerText = m; document.body.appendChild(t); setTimeout(() => t.remove(), 3000); }
    
    document.getElementById('viewCartBtn').onclick = showCart;
    document.getElementById('closeCartBtn').onclick = () => document.getElementById('cartModal').style.display = 'none';
    document.getElementById('closeCheckoutBtn').onclick = () => document.getElementById('checkoutModal').style.display = 'none';
    document.getElementById('closeDirectOrderBtn').onclick = () => document.getElementById('directOrderModal').style.display = 'none';
    document.getElementById('closeReviewModalBtn').onclick = () => document.getElementById('reviewModal').style.display = 'none';
    document.getElementById('closeConfirmationBtn').onclick = () => document.getElementById('confirmationModal').style.display = 'none';
    document.getElementById('myOrdersBtn').onclick = showMyOrdersModal;
    document.getElementById('closeMyOrdersBtn').onclick = () => document.getElementById('myOrdersModal').style.display = 'none';
    document.getElementById('verifyPhoneBtn').onclick = verifyAndShowOrders;
    window.onclick = e => { if(e.target.classList.contains('modal')) e.target.style.display = 'none'; };
    document.querySelectorAll('.filter-btn').forEach(btn => { btn.onclick = () => { document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active')); btn.classList.add('active'); currentFilter = btn.dataset.cat; renderProducts(); }; });
    document.getElementById('searchInput').oninput = e => { searchQuery = e.target.value; renderProducts(); };
    
    updateCartCount();
    renderProducts();
</script>
</body>
</html>
