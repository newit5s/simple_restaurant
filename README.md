# Hướng dẫn xây dựng Website Nhà hàng Nhật Bản

## 📋 Thông tin dự án

- **Domain**: test.vietsora.com
- **CMS**: WordPress 6.8
- **Framework CSS**: Tailwind CSS
- **Ngôn ngữ**: Tiếng Anh, Tiếng Việt, Tiếng Nhật
- **Target**: Giới thượng lưu
- **Style**: Đơn giản, sang trọng
- **Color Palette**: Đen (#000000), Xám (#6B7280), Nâu (#8B4513), Trắng (#FFFFFF)

## 🎯 Slogan
**"味と心の芸術" - Nghệ thuật của vị giác và tâm hồn**

## 🏗️ Cấu trúc Website

### Menu chính
1. **Trang chủ** (Home / ホーム)
2. **Về chúng tôi** (About Us / 私たちについて)
3. **Thực đơn** (Menu / メニュー)
4. **Đặt bàn** (Reservation / 予約)
5. **Liên hệ** (Contact / お問い合わせ)
6. **Blog** (Blog / ブログ)

### Cấu trúc thực đơn
- **Cơm** (Rice Dishes / ご飯)
- **Mì** (Noodles / 麺類)
- **Sashimi** (Sashimi / 刺身)
- **Đồ uống** (Beverages / 飲み物)

## 🔧 Plugin và tích hợp cần thiết

### Plugin bắt buộc
```
1. Polylang - Đa ngôn ngữ
2. Contact Form 7 - Form liên hệ
3. RankMath SEO - Tối ưu SEO
4. [Tên plugin đặt bàn hiện có]
5. Custom Post Type UI - Tạo custom post types
6. Advanced Custom Fields (ACF) - Custom fields
7. WP Rocket hoặc W3 Total Cache - Tối ưu tốc độ
```

### Custom Post Types cần tạo
```php
1. Menu Items (menu_item)
2. Customer Reviews (review)
3. Gallery (gallery)
```

## 🎨 Design System với Tailwind CSS

### Color Variables
```css
:root {
  --color-black: #000000;
  --color-gray: #6B7280;
  --color-brown: #8B4513;
  --color-white: #FFFFFF;
  --color-gray-light: #F3F4F6;
  --color-brown-light: #D2B48C;
}
```

### Typography
```css
/* Primary Font - Noto Sans (hỗ trợ đa ngôn ngữ) */
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans:wght@300;400;500;600;700&family=Noto+Sans+JP:wght@300;400;500;600;700&display=swap');

.font-primary {
  font-family: 'Noto Sans', 'Noto Sans JP', sans-serif;
}

/* Accent Font - Playfair Display cho tiêu đề */
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500;600;700&display=swap');

.font-accent {
  font-family: 'Playfair Display', serif;
}
```

### Responsive Breakpoints
```css
/* Mobile: iPhone 14 trở lên (390px+) */
@media (min-width: 390px) { ... }

/* Tablet: iPad (768px+) */
@media (min-width: 768px) { ... }

/* Desktop: (1024px+) */
@media (min-width: 1024px) { ... }

/* Large Desktop: (1440px+) */
@media (min-width: 1440px) { ... }
```

## 🧩 Component Library

### 1. Header Component
```html
<header class="bg-white shadow-lg sticky top-0 z-50">
  <nav class="container mx-auto px-4 py-4">
    <div class="flex justify-between items-center">
      <!-- Logo -->
      <div class="font-accent text-2xl font-bold text-black">
        Restaurant Name
      </div>
      
      <!-- Desktop Menu -->
      <ul class="hidden md:flex space-x-8">
        <li><a href="#" class="text-gray-700 hover:text-brown transition-colors">Trang chủ</a></li>
        <li><a href="#" class="text-gray-700 hover:text-brown transition-colors">Về chúng tôi</a></li>
        <li><a href="#" class="text-gray-700 hover:text-brown transition-colors">Thực đơn</a></li>
        <li><a href="#" class="text-gray-700 hover:text-brown transition-colors">Đặt bàn</a></li>
        <li><a href="#" class="text-gray-700 hover:text-brown transition-colors">Liên hệ</a></li>
        <li><a href="#" class="text-gray-700 hover:text-brown transition-colors">Blog</a></li>
      </ul>
      
      <!-- Language Switcher -->
      <div class="language-switcher">
        <!-- Polylang language switcher -->
      </div>
      
      <!-- Mobile Menu Button -->
      <button class="md:hidden" id="mobile-menu-btn">
        <span class="sr-only">Mở menu</span>
        <!-- Hamburger icon -->
      </button>
    </div>
  </nav>
</header>
```

### 2. Hero Section Component
```html
<section class="hero bg-gradient-to-r from-black to-gray-800 text-white py-20">
  <div class="container mx-auto px-4 text-center">
    <h1 class="font-accent text-4xl md:text-6xl font-bold mb-6">
      味と心の芸術
    </h1>
    <p class="text-xl md:text-2xl mb-8 text-gray-300">
      Nghệ thuật của vị giác và tâm hồn
    </p>
    <div class="space-x-4">
      <a href="#menu" class="bg-brown hover:bg-brown-dark text-white px-8 py-3 rounded-lg transition-colors">
        Xem thực đơn
      </a>
      <a href="#reservation" class="border border-white hover:bg-white hover:text-black text-white px-8 py-3 rounded-lg transition-colors">
        Đặt bàn
      </a>
    </div>
  </div>
</section>
```

### 3. Menu Card Component
```html
<div class="menu-card bg-white rounded-lg shadow-lg overflow-hidden hover:shadow-xl transition-shadow">
  <div class="aspect-w-16 aspect-h-9">
    <img src="[image-url]" alt="Menu item" class="w-full h-48 object-cover">
  </div>
  <div class="p-6">
    <h3 class="font-accent text-xl font-semibold mb-2 text-black">Tên món</h3>
    <p class="text-gray-600 mb-4">Mô tả món ăn chi tiết...</p>
    <div class="flex justify-between items-center">
      <span class="text-brown font-bold text-lg">299.000 VNĐ</span>
      <button class="bg-black hover:bg-gray-800 text-white px-4 py-2 rounded transition-colors">
        Thêm vào
      </button>
    </div>
  </div>
</div>
```

### 4. Review Component
```html
<div class="review-card bg-gray-50 p-6 rounded-lg">
  <div class="flex items-center mb-4">
    <img src="[avatar-url]" alt="Customer" class="w-12 h-12 rounded-full mr-4">
    <div>
      <h4 class="font-semibold text-black">Tên khách hàng</h4>
      <div class="flex text-yellow-400">
        ★★★★★
      </div>
    </div>
  </div>
  <p class="text-gray-700 italic">
    "Đánh giá của khách hàng về nhà hàng..."
  </p>
</div>
```

### 5. Footer Component
```html
<footer class="bg-black text-white py-12">
  <div class="container mx-auto px-4">
    <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
      <!-- Logo & Info -->
      <div>
        <h3 class="font-accent text-2xl font-bold mb-4">Restaurant Name</h3>
        <p class="text-gray-300 mb-4">味と心の芸術</p>
        <div class="flex space-x-4">
          <!-- Social Media Icons -->
        </div>
      </div>
      
      <!-- Quick Links -->
      <div>
        <h4 class="font-semibold mb-4">Liên kết nhanh</h4>
        <ul class="space-y-2">
          <li><a href="#" class="text-gray-300 hover:text-white transition-colors">Về chúng tôi</a></li>
          <li><a href="#" class="text-gray-300 hover:text-white transition-colors">Thực đơn</a></li>
          <li><a href="#" class="text-gray-300 hover:text-white transition-colors">Đặt bàn</a></li>
        </ul>
      </div>
      
      <!-- Contact Info -->
      <div>
        <h4 class="font-semibold mb-4">Liên hệ</h4>
        <div class="space-y-2 text-gray-300">
          <p>📍 Địa chỉ nhà hàng</p>
          <p>📞 (024) 1234 5678</p>
          <p>✉️ info@restaurant.com</p>
        </div>
      </div>
      
      <!-- Opening Hours -->
      <div>
        <h4 class="font-semibold mb-4">Giờ mở cửa</h4>
        <div class="space-y-2 text-gray-300">
          <p>Thứ 2 - Thứ 6: 11:00 - 22:00</p>
          <p>Thứ 7 - Chủ nhật: 10:00 - 23:00</p>
        </div>
      </div>
    </div>
    
    <div class="border-t border-gray-800 mt-8 pt-8 text-center text-gray-300">
      <p>&copy; 2024 Restaurant Name. All rights reserved.</p>
    </div>
  </div>
</footer>
```

## 📱 Page Templates

### 1. Trang chủ (Home Page)
```php
<?php
// Template: index.php hoặc front-page.php
get_header(); ?>

<!-- Hero Section -->
<section class="hero">
  <!-- Hero component -->
</section>

<!-- About Preview -->
<section class="py-16 bg-white">
  <div class="container mx-auto px-4">
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
      <div>
        <h2 class="font-accent text-3xl font-bold mb-6">Về nhà hàng chúng tôi</h2>
        <p class="text-gray-600 mb-6">Mô tả ngắn về nhà hàng...</p>
        <a href="/about" class="bg-brown text-white px-6 py-3 rounded-lg hover:bg-brown-dark transition-colors">
          Tìm hiểu thêm
        </a>
      </div>
      <div>
        <img src="[about-image]" alt="About" class="rounded-lg shadow-lg">
      </div>
    </div>
  </div>
</section>

<!-- Featured Menu -->
<section class="py-16 bg-gray-50">
  <div class="container mx-auto px-4">
    <h2 class="font-accent text-3xl font-bold text-center mb-12">Món ăn nổi bật</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
      <!-- Menu cards -->
    </div>
  </div>
</section>

<!-- Reviews -->
<section class="py-16 bg-white">
  <div class="container mx-auto px-4">
    <h2 class="font-accent text-3xl font-bold text-center mb-12">Đánh giá khách hàng</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
      <!-- Review components -->
    </div>
  </div>
</section>

<?php get_footer(); ?>
```

### 2. Trang thực đơn (Menu Page)
```php
<?php
// Template: page-menu.php
get_header(); ?>

<div class="container mx-auto px-4 py-12">
  <h1 class="font-accent text-4xl font-bold text-center mb-12">Thực đơn</h1>
  
  <!-- Menu Categories -->
  <div class="menu-categories mb-8">
    <div class="flex justify-center space-x-4 mb-8">
      <button class="menu-filter active bg-black text-white px-6 py-2 rounded-lg" data-filter="all">
        Tất cả
      </button>
      <button class="menu-filter bg-gray-200 text-gray-700 px-6 py-2 rounded-lg hover:bg-gray-300" data-filter="rice">
        Cơm
      </button>
      <button class="menu-filter bg-gray-200 text-gray-700 px-6 py-2 rounded-lg hover:bg-gray-300" data-filter="noodles">
        Mì
      </button>
      <button class="menu-filter bg-gray-200 text-gray-700 px-6 py-2 rounded-lg hover:bg-gray-300" data-filter="sashimi">
        Sashimi
      </button>
      <button class="menu-filter bg-gray-200 text-gray-700 px-6 py-2 rounded-lg hover:bg-gray-300" data-filter="drinks">
        Đồ uống
      </button>
    </div>
  </div>
  
  <!-- Menu Items Grid -->
  <div class="menu-grid grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
    <?php
    $menu_items = new WP_Query([
      'post_type' => 'menu_item',
      'posts_per_page' => -1,
      'meta_key' => 'menu_order',
      'orderby' => 'meta_value_num',
      'order' => 'ASC'
    ]);
    
    if ($menu_items->have_posts()) :
      while ($menu_items->have_posts()) : $menu_items->the_post();
        $category = get_field('menu_category');
        $price = get_field('price');
        $description = get_field('description');
        $image = get_field('menu_image');
    ?>
    
    <div class="menu-item" data-category="<?php echo esc_attr($category); ?>">
      <!-- Menu card component -->
    </div>
    
    <?php
      endwhile;
      wp_reset_postdata();
    endif;
    ?>
  </div>
</div>

<?php get_footer(); ?>
```

## ⚙️ Functions.php Setup

```php
<?php
// Theme setup
function japanese_restaurant_setup() {
    // Add theme support
    add_theme_support('title-tag');
    add_theme_support('post-thumbnails');
    add_theme_support('html5', array('search-form', 'comment-form', 'comment-list', 'gallery', 'caption'));
    
    // Register navigation menus
    register_nav_menus(array(
        'primary' => 'Primary Menu',
        'footer' => 'Footer Menu',
    ));
}
add_action('after_setup_theme', 'japanese_restaurant_setup');

// Enqueue styles and scripts
function japanese_restaurant_scripts() {
    // Tailwind CSS
    wp_enqueue_style('tailwind', 'https://cdn.tailwindcss.com');
    
    // Google Fonts
    wp_enqueue_style('google-fonts', 'https://fonts.googleapis.com/css2?family=Noto+Sans:wght@300;400;500;600;700&family=Noto+Sans+JP:wght@300;400;500;600;700&family=Playfair+Display:wght@400;500;600;700&display=swap');
    
    // Custom styles
    wp_enqueue_style('theme-style', get_stylesheet_uri(), array(), '1.0.0');
    
    // Custom scripts
    wp_enqueue_script('theme-script', get_template_directory_uri() . '/js/main.js', array('jquery'), '1.0.0', true);
}
add_action('wp_enqueue_scripts', 'japanese_restaurant_scripts');

// Custom Post Types
function create_menu_post_type() {
    register_post_type('menu_item', array(
        'labels' => array(
            'name' => 'Menu Items',
            'singular_name' => 'Menu Item',
        ),
        'public' => true,
        'has_archive' => false,
        'supports' => array('title', 'editor', 'thumbnail'),
        'show_in_rest' => true,
    ));
}

function create_review_post_type() {
    register_post_type('review', array(
        'labels' => array(
            'name' => 'Reviews',
            'singular_name' => 'Review',
        ),
        'public' => true,
        'has_archive' => true,
        'supports' => array('title', 'editor', 'thumbnail'),
        'show_in_rest' => true,
    ));
}

add_action('init', 'create_menu_post_type');
add_action('init', 'create_review_post_type');

// Custom image sizes
function japanese_restaurant_image_sizes() {
    add_image_size('menu-card', 400, 300, true);
    add_image_size('hero-image', 1920, 800, true);
    add_image_size('gallery-thumb', 300, 300, true);
}
add_action('after_setup_theme', 'japanese_restaurant_image_sizes');
?>
```

## 🌐 Multilingual Setup với Polylang

### Cấu hình ngôn ngữ
1. **Cài đặt Polylang plugin**
2. **Thêm ngôn ngữ**: 
   - Tiếng Việt (vi) - Default
   - English (en)
   - 日本語 (ja)

### Translation strings
```php
// strings.php
<?php
// Register strings for translation
if (function_exists('pll_register_string')) {
    pll_register_string('site-slogan', '味と心の芸術 - Nghệ thuật của vị giác và tâm hồn');
    pll_register_string('menu-title', 'Thực đơn');
    pll_register_string('about-title', 'Về chúng tôi');
    pll_register_string('contact-title', 'Liên hệ');
    pll_register_string('reservation-title', 'Đặt bàn');
    pll_register_string('blog-title', 'Blog');
}
?>
```

## 🚀 Performance Optimization

### Image Optimization
```php
// Lazy loading images
function add_lazy_loading($content) {
    return str_replace('<img', '<img loading="lazy"', $content);
}
add_filter('the_content', 'add_lazy_loading');

// WebP support
function add_webp_support($mime_types) {
    $mime_types['webp'] = 'image/webp';
    return $mime_types;
}
add_filter('upload_mimes', 'add_webp_support');
```

### Caching và minification
- **Plugin**: WP Rocket hoặc W3 Total Cache
- **CDN**: Cloudflare (recommended)
- **Image compression**: Smush hoặc ShortPixel

## 📊 SEO Setup với RankMath

### Schema Markup cho nhà hàng
```json
{
  "@context": "https://schema.org",
  "@type": "Restaurant",
  "name": "Restaurant Name",
  "image": "https://test.vietsora.com/images/restaurant-logo.jpg",
  "description": "Nhà hàng Nhật Bản cao cấp tại Việt Nam",
  "servesCuisine": "Japanese",
  "priceRange": "$$$",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "Địa chỉ cụ thể",
    "addressLocality": "Thành phố",
    "addressCountry": "VN"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": "21.0285",
    "longitude": "105.8542"
  },
  "openingHours": "Mo-Fr 11:00-22:00, Sa-Su 10:00-23:00",
  "telephone": "+84-24-1234-5678"
}
```

## 📝 Content Samples

### Về chúng tôi (Sample)
```
**Tiếng Việt:**
Chào mừng đến với [Tên nhà hàng] - nơi hội tụ tinh hoa ẩm thực Nhật Bản giữa lòng Việt Nam. Với hơn 10 năm kinh nghiệm, chúng tôi tự hào mang đến những món ăn chính thống, được chế biến từ nguyên liệu tươi ngon nhất và nghệ thuật ẩm thực truyền thống Nhật Bản.

**English:**
Welcome to [Restaurant Name] - where authentic Japanese culinary excellence meets Vietnamese hospitality. With over 10 years of experience, we pride ourselves on serving traditional dishes crafted from the finest ingredients and time-honored Japanese culinary techniques.

**日本語:**
[レストラン名]へようこそ - ベトナムの中心で本格的な日本料理の真髄をお楽しみいただけます。10年以上の経験を持つ私たちは、最高品質の食材と伝統的な日本の調理技術で作られた本格的な料理を提供することを誇りにしています。
```

### Sample Menu Items
```
1. **Chirashi Don** - 799.000 VNĐ
   Cơm sashimi đặc biệt với 8 loại cá tươi
   
2. **Ramen Tonkotsu** - 299.000 VNĐ
   Mì ramen nước dùng xương heo đậm đà
   
3. **Sashimi Moriawase** - 899.000 VNĐ
   Sashimi tổng hợp cao cấp (12 miếng)
   
4. **Sake Premium** - 150.000 VNĐ/ly
   Rượu sake Nhật Bản nhập khẩu
```

## 📞 Contact Integration

### Google Maps Embed
```html
<div class="google-map h-96 rounded-lg overflow-hidden">
  <iframe 
    src="https://www.google.com/maps/embed?pb=..." 
    width="100%" 
    height="100%" 
    style="border:0;" 
    allowfullscreen="" 
    loading="lazy">
  </iframe>
</div>
```

### Contact Form 7 Setup
```html
[text* your-name placeholder "Họ và tên"]
[email* your-email placeholder "Email"]
[tel your-phone placeholder "Số điện thoại"]
[date reservation-date placeholder "Ngày đặt bàn"]
[select reservation-time "Chọn giờ" "18:00" "18:30" "19:00" "19:30" "20:00" "20:30"]
[number guests min:1 max:20 placeholder "Số khách"]
[textarea your-message placeholder "Ghi chú đặc biệt"]
[submit "Gửi yêu cầu đặt bàn"]
```

## 🔗 Social Media Integration

### Social Media Links
- **Facebook**: facebook.com/restaurantname
- **Instagram**: instagram.com/restaurantname
- **YouTube**: youtube.com/@restaurantname
- **TikTok**: tiktok.com/@restaurantname

### Open Graph Meta Tags
```html
<meta property="og:title" content="Nhà hàng Nhật Bản cao cấp - 味と心の芸術">
<meta property="og:description" content="Nghệ thuật của vị giác và tâm hồn">
<meta property="og:image" content="https://test.vietsora.com/images/og-image.jpg">
<meta property="og:url" content="https://test.vietsora.com">
<meta property="og:type" content="restaurant">
```

## ✅ Checklist triển khai

### Phase 1: Setup cơ bản
- [ ] Cài đặt WordPress 6.8
- [ ] Cài đặt và cấu hình các plugin cần thiết
- [ ] Tạo custom post types
- [ ] Setup Tailwind CSS
- [ ] Tạo component library

### Phase 2: Content & Design
- [ ] Upload logo tạm thời
- [ ] Tạo header và footer
- [ ] Thiết kế trang chủ
- [ ] Tạo trang thực đơn
- [ ] Thiết kế form đặt bàn

### Phase 3: Multilingual
- [ ] Cấu hình Polylang
- [ ] Dịch nội dung sang 3 ngôn ngữ
- [ ] Test language switcher

### Phase 4: Optimization & Testing
- [ ] Tối ưu hình ảnh
- [ ] Cấu hình caching
- [ ] Test responsive design
- [ ] SEO optimization
- [ ] Test tốc độ tải trang (<5s)

### Phase 5: Final touches
- [ ] Tích hợp Google Maps
- [ ] Setup social media links
- [ ] Test form liên hệ
- [ ] Final QA testing

## 🎯 Notes cho Developer

1. **Sử dụng Tailwind utilities** thay vì custom CSS khi có thể
2. **Component-based approach** - tạo các component có thể tái sử dụng
3. **Mobile-first design** - thiết kế từ mobile rồi scale lên desktop
4. **Performance first** - optimize hình ảnh và code để đạt <5s loading
5. **Accessibility** - đảm bảo website accessible cho người khuyết tật
6. **SEO-friendly** - URL structure, meta tags, schema markup
7. **Cross-browser testing** - test trên Chrome, Firefox, Safari, Edge

---

**Liên hệ hỗ trợ**: Nếu cần clarification hoặc hỗ trợ thêm trong quá trình phát triển, vui lòng liên hệ để được hướng dẫn chi tiết hơn.
