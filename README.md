## 🔧 WordPress Admin Panel - Quản lý nội dung

### Dashboard Overview
```
WordPress Admin Dashboard
├── 📊 Dashboard
│   ├── Quick Actions
│   ├── Recent Posts/Pages
│   └── Site Stats
├── 📄 Pages
│   ├── All Pages
│   ├── Add New
│   └── UX Builder Templates
├── 📝 Posts (Blog)
│   ├── All Posts
│   ├── Categories
│   └── Tags
├── 🍽️ Menu Items (Custom Post Type)
│   ├── All Menu Items
│   ├── Add New Menu Item
│   ├── Categories (Cơm, Mì, Sashimi, Đồ uống)
│   └── Tags
├── ⭐ Reviews (Custom Post Type)
│   ├── All Reviews
│   ├── Add New Review
│   └── Review Settings
├── 🎉 Events (Custom Post Type)# Hướng dẫn xây dựng Website Nhà hàng Nhật Bản

## 📋 Thông tin dự án

- **Domain**: test.vietsora.com
- **CMS**: WordPress 6.8
- **Theme**: Flatsome (UX Builder)
- **Framework CSS**: Tailwind CSS + Flatsome CSS
- **Builder**: UX Builder (Flatsome built-in)
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

## 🔧 Theme & Plugin Setup

### Theme chính
```
Flatsome Theme (Latest version)
- UX Builder (built-in page builder)
- WooCommerce ready (nếu cần bán online sau này)
- Responsive design system
- Multiple header/footer layouts
```

### Plugin bắt buộc
```
1. Flatsome Theme (Primary theme)
2. Polylang - Đa ngôn ngữ
3. Contact Form 7 - Form liên hệ
4. RankMath SEO - Tối ưu SEO
5. [Tên plugin đặt bàn hiện có]
6. Custom Post Type UI - Tạo custom post types
7. Advanced Custom Fields (ACF) - Custom fields
8. WP Rocket hoặc W3 Total Cache - Tối ưu tốc độ
```

### Custom Post Types cần tạo
```php
1. Menu Items (menu_item)
2. Customer Reviews (review)
3. Gallery (gallery)
4. Events (events) - Sự kiện nhà hàng
```

## 🏗️ Cấu trúc Website với Flatsome + UX Builder

### Cấu trúc thư mục WordPress
```
wp-content/
├── themes/
│   ├── flatsome/           # Theme chính
│   └── flatsome-child/     # Child theme (custom code)
├── plugins/
│   ├── polylang/
│   ├── contact-form-7/
│   ├── rankmath/
│   └── advanced-custom-fields/
├── uploads/
│   ├── 2024/
│   │   ├── menu-images/
│   │   ├── gallery/
│   │   └── blog/
│   └── ux-builder-templates/   # UX Builder saved templates
```

### Cấu trúc Admin WordPress
```
Dashboard
├── Pages (Trang)
│   ├── Home (Trang chủ)
│   ├── About Us (Về chúng tôi) 
│   ├── Menu (Thực đơn)
│   ├── Reservation (Đặt bàn)
│   ├── Contact (Liên hệ)
│   └── Gallery (Thư viện ảnh)
├── Posts (Bài viết - Blog)
├── Menu Items (Custom Post Type)
├── Reviews (Custom Post Type)
├── Events (Custom Post Type)
├── Media Library
│   ├── Menu Photos
│   ├── Restaurant Photos
│   ├── Chef Photos
│   └── Blog Images
└── UX Builder Templates
    ├── Header Templates
    ├── Footer Templates
    ├── Section Templates
    └── Page Templates
```

## 🎨 Flatsome Customization với UX Builder

### Flatsome Theme Customizer Settings
```css
/* Trong WordPress Admin > Appearance > Customize */

1. Site Identity:
   - Site Title: Restaurant Name
   - Tagline: 味と心の芸術 - Nghệ thuật của vị giác và tâm hồn
   - Logo: Upload logo chính
   - Site Icon: Upload favicon

2. Colors:
   - Primary Color: #8B4513 (Nâu)
   - Secondary Color: #6B7280 (Xám)
   - Success Color: #10B981 (Xanh lá)
   - Alert Color: #F59E0B (Vàng)
   - Color Scheme: Custom

3. Typography:
   - Body Font: Noto Sans
   - Heading Font: Playfair Display
   - Alt Font: Noto Sans JP (cho tiếng Nhật)

4. Header:
   - Header Type: Header Builder
   - Header Height: Auto
   - Header Background: White
   - Sticky Header: Yes

5. Footer:
   - Footer Type: Footer Builder
   - Footer Background: Black
   - Footer Text Color: White
```

### UX Builder - Custom Sections Library

#### 1. Hero Section Template
```html
<!-- UX Builder: Row > Banner với Video/Image Background -->
[ux_banner height="70vh" bg_color="rgb(0,0,0)" bg_overlay="rgba(0,0,0,0.4)"]
  [text_box position_x="50" position_y="50" text_align="center"]
    <h1 class="hero-title">味と心の芸術</h1>
    <p class="hero-subtitle">Nghệ thuật của vị giác và tâm hồn</p>
    [button text="Xem thực đơn" color="alert" style="outline" size="large" link="/menu"]
    [button text="Đặt bàn" color="white" style="outline" size="large" link="/reservation"]
  [/text_box]
[/ux_banner]
```

#### 2. About Preview Section
```html
<!-- UX Builder: Row với 2 columns -->
[row style="large" v_align="middle"]
  [col span="6" span__sm="12"]
    [ux_image id="about-image" image_hover="overlay-add"]
  [/col]
  [col span="6" span__sm="12"]
    [text_box style="normal"]
      <h2>Về nhà hàng chúng tôi</h2>
      <p>Chào mừng đến với [Tên nhà hàng] - nơi hội tụ tinh hoa ẩm thực Nhật Bản...</p>
      [button text="Tìm hiểu thêm" color="primary" link="/about"]
    [/text_box]
  [/col]
[/row]
```

#### 3. Menu Grid Template
```html
<!-- UX Builder: Blog Posts Grid hiển thị Menu Items -->
[blog_posts style="normal" columns="3" columns__md="2" columns__sm="1" 
posts="9" show_date="false" excerpt="false" image_height="250px"
cat="menu-items" post_type="menu_item"]
```

#### 4. Reviews Carousel
```html
<!-- UX Builder: Testimonials Slider -->
[ux_testimonials style="push" columns="3" columns__md="2" columns__sm="1" 
auto_slide="5000" infinitive="true"]
  [testimonial name="Nguyễn Văn A" company="Khách hàng VIP" image="review1.jpg"]
    Món ăn tuyệt vời, dịch vụ chuyên nghiệp...
  [/testimonial]
  [testimonial name="Trần Thị B" company="Food Blogger" image="review2.jpg"]
    Không gian sang trọng, hương vị chính thống...
  [/testimonial]
[/ux_testimonials]
```

### UX Builder - Global Elements

#### Header Builder Layout
```html
<!-- Header Structure trong UX Builder -->
[section class="header-main"]
  [row style="collapse" width="full-width"]
    [col span="3" span__sm="6" align="left"]
      <!-- Logo -->
      [logo img="logo.png" height="60px"]
    [/col]
    [col span="6" span__sm="0" align="center" class="nav-main"]
      <!-- Main Navigation -->
      [ux_menu menu="primary-menu" text_color="dark"]
    [/col]
    [col span="3" span__sm="6" align="right"]
      <!-- Language Switcher + Mobile Menu -->
      [ux_language_switcher]
      [mobile_sidebar_toggle]
    [/col]
  [/row]
[/section]
```

#### Footer Builder Layout
```html
<!-- Footer Structure trong UX Builder -->
[section bg_color="rgb(0,0,0)" text_color="light"]
  [row style="large"]
    [col span="3" span__sm="12"]
      [text_box]
        <h4>Restaurant Name</h4>
        <p>味と心の芸術</p>
        [follow style="outline" size="small"]
      [/text_box]
    [/col]
    [col span="3" span__sm="12"]
      [text_box]
        <h4>Liên kết nhanh</h4>
        [ux_menu menu="footer-menu" text_color="light"]
      [/text_box]
    [/col]
    [col span="3" span__sm="12"]
      [text_box]
        <h4>Liên hệ</h4>
        <p>📍 Địa chỉ nhà hàng</p>
        <p>📞 (024) 1234 5678</p>
        <p>✉️ info@restaurant.com</p>
      [/text_box]
    [/col]
    [col span="3" span__sm="12"]
      [text_box]
        <h4>Giờ mở cửa</h4>
        <p>Thứ 2 - Thứ 6: 11:00 - 22:00</p>
        <p>Thứ 7 - CN: 10:00 - 23:00</p>
      [/text_box]
    [/col]
  [/row]
  
  [row style="collapse"]
    [col span="12" align="center"]
      [gap height="20px"]
      <p>&copy; 2024 Restaurant Name. All rights reserved.</p>
    [/col]
  [/row]
[/section]
```

## 📄 Hướng dẫn tạo Pages với UX Builder

### 1. Trang chủ (Home Page)
```
WordPress Admin > Pages > Add New > "Trang chủ"
- Template: UX Builder
- Page Attributes: Front Page

UX Builder Structure:
```

#### Section 1: Hero Banner
```html
[section class="hero-section" bg_overlay="rgba(0,0,0,0.5)" bg_pos="center center"]
  [ux_banner height="80vh" bg="hero-bg.jpg"]
    [text_box position_x="50" position_y="50" text_align="center" text_color="light"]
      <h1 class="display-1">味と心の芸術</h1>
      <p class="lead">Nghệ thuật của vị giác và tâm hồn</p>
      [gap height="30px"]
      [button text="Xem thực đơn" style="outline" color="white" size="xlarge" link="#menu"]
      [button text="Đặt bàn ngay" color="alert" size="xlarge" link="/reservation"]
    [/text_box]
  [/ux_banner]
[/section]
```

#### Section 2: About Preview
```html
[section class="about-preview" padding="80px"]
  [row style="large" v_align="middle"]
    [col span="6" span__sm="12"]
      [ux_image id="about-restaurant" lightbox="true" image_hover="zoom"]
    [/col]
    [col span="6" span__sm="12"]
      [gap height="30px" visibility="hide-for-medium"]
      [text_box style="normal"]
        <h2>Câu chuyện của chúng tôi</h2>
        <p class="lead">Hành trình mang tinh hoa ẩm thực Nhật Bản đến Việt Nam...</p>
        <p>Chi tiết về nhà hàng, chef, và cam kết chất lượng...</p>
        [gap height="20px"]
        [button text="Tìm hiểu thêm" color="primary" style="outline"]
      [/text_box]
    [/col]
  [/row]
[/section]
```

#### Section 3: Featured Menu
```html
[section class="featured-menu" bg_color="rgb(248,248,248)" padding="80px"]
  [row]
    [col span="12" align="center"]
      <h2>Thực đơn đặc sắc</h2>
      <p class="lead">Những món ăn tinh túy được yêu thích nhất</p>
      [gap height="50px"]
    [/col]
  [/row]
  
  [blog_posts style="normal" type="grid" columns="4" columns__md="2" columns__sm="1"
  posts="8" show_date="false" excerpt="false" text_align="center"
  post_type="menu_item" meta_key="featured" meta_value="yes"]
[/section]
```

#### Section 4: Customer Reviews
```html
[section class="reviews-section" padding="80px"]
  [row]
    [col span="12" align="center"]
      <h2>Khách hàng nói gì về chúng tôi</h2>
      [gap height="50px"]
    [/col]
  [/row]
  
  [ux_testimonials style="push" columns="3" columns__md="2" columns__sm="1" 
  auto_slide="5000" infinitive="true" bg_color="rgb(255,255,255)"]
[/section]
```

### 2. Trang Thực đơn (Menu Page)
```
WordPress Admin > Pages > Add New > "Thực đơn"
- Template: UX Builder

UX Builder Structure:
```

#### Page Header
```html
[section class="page-header" bg_color="rgb(248,248,248)" padding="60px"]
  [row]
    [col span="12" align="center"]
      <h1>Thực đơn của chúng tôi</h1>
      <p class="lead">Hương vị Nhật Bản chính thống</p>
    [/col]
  [/row]
[/section]
```

#### Menu Categories Filter
```html
[section class="menu-filters" padding="40px"]
  [row]
    [col span="12" align="center"]
      [ux_portfolio_filter filter="menu-category"]
    [/col]
  [/row]
[/section]
```

#### Menu Items Grid
```html
[section class="menu-grid" padding="40px"]
  [ux_portfolio style="normal" columns="3" columns__md="2" columns__sm="1"
  type="slider" cat="menu-items" posts="-1" image_height="250px"
  text_align="center" filter="menu-category"]
[/section]
```

### 3. Trang Đặt bàn (Reservation Page)
```html
[section class="reservation-hero" bg="reservation-bg.jpg" padding="60px"]
  [row]
    [col span="12" align="center"]
      <h1 class="text-white">Đặt bàn</h1>
      <p class="lead text-white">Trải nghiệm ẩm thực đáng nhớ</p>
    [/col]
  [/row]
[/section]

[section class="reservation-form" padding="80px"]
  [row]
    [col span="8" span__sm="12"]
      [contact-form-7 id="123" title="Reservation Form"]
    [/col]
    [col span="4" span__sm="12"]
      [text_box]
        <h3>Thông tin liên hệ</h3>
        <p><strong>Địa chỉ:</strong> 123 Đường ABC, Quận XYZ</p>
        <p><strong>Điện thoại:</strong> (024) 1234 5678</p>
        <p><strong>Email:</strong> info@restaurant.com</p>
        
        <h4>Giờ mở cửa:</h4>
        <p>Thứ 2 - Thứ 6: 11:00 - 22:00</p>
        <p>Thứ 7 - Chủ nhật: 10:00 - 23:00</p>
      [/text_box]
    [/col]
  [/row]
[/section]
```

### 4. Trang Liên hệ (Contact Page)
```html
[section class="contact-info" padding="80px"]
  [row]
    [col span="6" span__sm="12"]
      [text_box]
        <h2>Liên hệ với chúng tôi</h2>
        <p>Chúng tôi luôn sẵn sàng phục vụ bạn</p>
        
        <h4>Địa chỉ nhà hàng:</h4>
        <p>123 Đường ABC, Quận XYZ, TP.HCM</p>
        
        <h4>Liên hệ:</h4>
        <p>📞 (024) 1234 5678</p>
        <p>✉️ info@restaurant.com</p>
        
        [follow style="fill" size="medium"]
      [/text_box]
    [/col]
    
    [col span="6" span__sm="12"]
      [contact-form-7 id="456" title="Contact Form"]
    [/col]
  [/row]
[/section]

[section class="map-section" padding="0px"]
  [row style="collapse"]
    [col span="12"]
      [map height="400px" lat="21.0285" long="105.8542" zoom="15"]
    [/col]
  [/row]
[/section]
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
