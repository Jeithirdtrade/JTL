<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>O.C app</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/intl-tel-input@17.0.12/build/css/intlTelInput.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.7.2/css/all.min.css">
    <style>
        
           
        
        
                     /* Product Kebab Menu Styles */
.product-menu {
    position: absolute;
    top: 10px;
    right: 10px;
    z-index: 10;
}

.product-menu-btn {
    background-color: rgba(255, 255, 255, 0.9);
    border: none;
    border-radius: 50%;
    width: 30px;
    height: 30px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    color: #333;
    font-size: 14px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    transition: background-color 0.2s;
}

.product-menu-btn:hover {
    background-color: white;
}

.product-menu-dropdown {
    position: absolute;
    top: 35px;
    right: 0;
    background-color: white;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.15);
    min-width: 120px;
    z-index: 100;
    display: none;
}

.product-menu-dropdown.show {
    display: block;
}

.product-menu-option {
    padding: 10px 15px;
    cursor: pointer;
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 14px;
    transition: background-color 0.2s;
}

.product-menu-option:hover {
    background-color: #f0f2f5;
}

.product-menu-option.edit {
    color: #4267B2;
}

.product-menu-option.delete {
    color: #e74c3c;
}

.product-menu-option i {
    width: 16px;
}

/* For product item relative positioning */
.product-item {
    position: relative;
}

.wishlist-item {
    position: absolute;
}

/* Dark mode support */
body.dark-mode .product-menu-btn {
    background-color: rgba(52, 53, 65, 0.9);
    color: #e4e6eb;
}

body.dark-mode .product-menu-dropdown {
    background-color: #242526;
    border: 1px solid #393a3b;
}

body.dark-mode .product-menu-option:hover {
    background-color: #3a3b3c;
}
        
              
        
        
        
        
        .shop-product-item {
    position: relative;
}
        
        
        
        /* Reset and Base Styles */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }
        
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            display: flex;
            flex-direction: column;
            align-items: center;
            color: #333;
            line-height: 1.6;
        }

        .container {
            width: 100%;
            max-width: 600px;
            background-color: white;
            min-height: 100vh;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            position: relative;
            padding-bottom: 60px;
        }

        /* Header Styles */
        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px;
            background-color: #4267B2;
            color: white;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .logo {
            font-weight: bold;
            font-size: 1.5rem;
        }

        .nav-icons {
            display: flex;
            gap: 15px;
            position: relative;
        }

        .nav-icons i {
            cursor: pointer;
            font-size: 1.2rem;
        }

        /* Ad Banner Styles */
        .ad-banner-container {
            position: relative;
            width: 100%;
            height: 160px;
            overflow: hidden;
            background-color: #ddd;
        }

        .ad-banner {
            display: flex;
            width: 100%;
            height: 100%;
            transition: transform 0.5s ease;
        }

        .ad-slide {
            min-width: 100%;
            height: 100%;
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            font-size: 24px;
            position: relative;
            cursor: pointer;
        }

        .ad-slide-content {
            background-color: rgba(0, 0, 0, 0.6);
            padding: 15px;
            border-radius: 10px;
            text-align: center;
            max-width: 80%;
        }

        .ad-product-name {
            font-size: 18px;
            margin-bottom: 5px;
        }

        .ad-product-price {
            font-size: 16px;
            color: #ffcc00;
            margin-bottom: 5px;
        }

        .ad-product-company {
            font-size: 14px;
            opacity: 0.8;
        }

        .ad-control {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background-color: rgba(0, 0, 0, 0.5);
            color: white;
            padding: 10px;
            cursor: pointer;
            z-index: 10;
        }

        .prev {
            left: 0;
        }

        .next {
            right: 0;
        }

        .ad-nav {
            position: absolute;
            bottom: 10px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 8px;
        }

        .ad-dot {
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background-color: rgba(255, 255, 255, 0.5);
            cursor: pointer;
        }

        .ad-dot.active {
            background-color: white;
        }

        /* Post Creation Styles */
        .create-post {
            padding: 15px;
            border-bottom: 1px solid #eee;
            background-color: white;
        }

        .post-input {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 10px;
        }

        .user-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: #ddd;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .user-avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .post-input input {
            flex: 1;
            padding: 10px 15px;
            border: 1px solid #ddd;
            border-radius: 20px;
            outline: none;
            cursor: pointer;
        }

        .post-actions {
            display: flex;
            justify-content: space-around;
        }

        .post-action {
            display: flex;
            align-items: center;
            gap: 5px;
            color: #65676B;
            cursor: pointer;
            padding: 5px 10px;
            border-radius: 5px;
        }

        .post-action:hover {
            background-color: #f0f2f5;
        }

        /* Upload Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }

        .modal-content {
            background-color: white;
            width: 90%;
            max-width: 500px;
            border-radius: 10px;
            overflow: hidden;
            max-height: 90vh;
            overflow-y: auto;
        }

        .modal-header {
            padding: 15px;
            border-bottom: 1px solid #eee;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .modal-body {
            padding: 15px;
        }

        .modal-footer {
            padding: 15px;
            border-top: 1px solid #eee;
            display: flex;
            justify-content: flex-end;
            gap: 10px;
        }

        .btn {
            padding: 8px 16px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
        }

        .btn-primary {
            background-color: #4267B2;
            color: white;
        }

        .btn-secondary {
            background-color: #e4e6eb;
            color: #333;
        }

        .preview-container {
            width: 100%;
            margin: 15px 0;
            display: flex;
            justify-content: center;
        }

        .media-preview {
            max-width: 100%;
            max-height: 300px;
            border-radius: 5px;
        }

        textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            resize: vertical;
            min-height: 100px;
            margin-bottom: 15px;
        }

        /* Posts Container Styles */
        .posts-container {
            padding: 10px;
        }

        .post {
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
            margin-bottom: 15px;
            overflow: hidden;
        }

        .post-header {
            display: flex;
            align-items: center;
            padding: 12px;
            gap: 10px;
        }

        .post-user-info {
            flex: 1;
        }

        .post-user-info .name {
            font-weight: bold;
            margin-bottom: 3px;
        }

        .post-user-info .time {
            font-size: 12px;
            color: #65676B;
        }

        .post-menu {
            cursor: pointer;
            color: #65676B;
            padding: 5px;
            position: relative;
        }

        .post-menu-dropdown {
            display: none;
            position: absolute;
            right: 0;
            top: 25px;
            background-color: white;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
            border-radius: 5px;
            z-index: 10;
            width: 150px;
        }

        .post-menu-dropdown div {
            padding: 10px;
            cursor: pointer;
        }

        .post-menu-dropdown div:hover {
            background-color: #f0f2f5;
        }

        .post-content {
            padding: 0 12px 12px;
        }

        .post-caption {
            margin-bottom: 10px;
            line-height: 1.4;
            overflow: hidden;
            display: -webkit-box;
            -webkit-line-clamp: 3;
            -webkit-box-orient: vertical;
        }

        .post-caption.expanded {
            -webkit-line-clamp: unset;
        }

        .read-more {
            color: #65676B;
            font-size: 14px;
            cursor: pointer;
            margin-top: 5px;
        }

        .post-media {
            width: 100%;
            margin-bottom: 10px;
            border-radius: 5px;
            overflow: hidden;
        }

        .post-media img,
        .post-media video {
            width: 100%;
            max-height: 400px;
            object-fit: cover;
        }

        .post-stats {
            padding: 0 12px;
            display: flex;
            justify-content: space-between;
            color: #65676B;
            font-size: 14px;
            border-bottom: 1px solid #eee;
            padding-bottom: 10px;
        }

        .post-actions-row {
            display: flex;
            justify-content: space-around;
            padding: 8px 0;
            border-bottom: 1px solid #eee;
        }

        .post-action-btn {7
            display: flex;
            align-items: center;
            gap: 5px;
            color: #65676B;
            cursor: pointer;
            padding: 5px 10px;
            border-radius: 5px;
        }

        .post-action-btn:hover {
            background-color: #f0f2f5;
        }

        .post-action-btn.liked {
            color: #1877F2;
        }

        .comments-section {
            padding: 10px 12px;
            display: none;
        }

        .comment {
            display: flex;
            gap: 10px;
            margin-bottom: 10px;
        }

        .comment-avatar {
            width: 32px;
            height: 32px;
            border-radius: 50%;
            background-color: #ddd;
            flex-shrink: 0;
            overflow: hidden;
        }

        .comment-avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .comment-content {
            flex: 1;
            background-color: #f0f2f5;
            padding: 8px 12px;
            border-radius: 18px;
        }

        .comment-author {
            font-weight: bold;
            font-size: 13px;
            margin-bottom: 3px;
        }

        .comment-text {
            font-size: 14px;
        }

        .comment-actions {
            display: flex;
            gap: 10px;
            margin-top: 5px;
            font-size: 12px;
            color: #65676B;
        }

        .comment-action {
            cursor: pointer;
        }

        .add-comment {
            display: flex;
            gap: 10px;
            margin-top: 10px;
        }

        .add-comment input {
            flex: 1;
            padding: 8px 12px;
            border: none;
            background-color: #f0f2f5;
            border-radius: 18px;
            outline: none;
        }

        /* Products Section Styles */
        .products-section {
            padding: 15px;
            display: none;
            justify-content: center:
            align-items: center;
        }

        .section-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }

        .section-title {
            font-weight: bold;
            font-size: 18px;
        }

        .view-all {
            color: #4267B2;
            font-size: 14px;
            cursor: pointer;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
        }

        .product-item {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
            cursor: pointer;
        }

        .product-image {
            width: 100%;
            height: 150px;
            object-fit: cover;
        }

        .product-info {
            padding: 10px;
        }

        .product-name {
            font-weight: bold;
            margin-bottom: 5px;
            font-size: 14px;
        }

        .product-price {
            color: #4267B2;
            font-weight: bold;
        }

        /* Search Bar Styles */
        .search-bar {
            padding: 10px 15px;
            background-color: white;
            border-bottom: 1px solid #eee;
            display: none;
        }

        .search-input {
            width: 100%;
            padding: 10px 15px;
            border: none;
            background-color: #f0f2f5;
            border-radius: 20px;
            outline: none;
        }

        /* Earnings Section Styles */
        .earnings-section {
            padding: 15px;
            display: none;
        }

        .earnings-card {
            background: linear-gradient(135deg, #4267B2, #898F9C);
            border-radius: 10px;
            padding: 20px;
            color: white;
            margin-bottom: 20px;
        }

        .earnings-total {
            font-size: 32px;
            font-weight: bold;
            margin: 10px 0;
        }

        .earnings-label {
            font-size: 14px;
            opacity: 0.8;
        }

        .earnings-stats {
            display: flex;
            justify-content: space-between;
            background-color: white;
            border-radius: 10px;
            padding: 15px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            margin-bottom: 20px;
        }

        .stat-item {
            text-align: center;
        }

        .stat-value {
            font-size: 18px;
            font-weight: bold;
            color: #4267B2;
        }

        .stat-label {
            font-size: 14px;
            color: #65676B;
        }

        .withdraw-btn {
            background-color: #4267B2;
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 5px;
            width: 100%;
            font-weight: bold;
            cursor: pointer;
        }

        /* Profile Section Styles */
        .profile-section {
            padding: 15px;
            display: none;
        }

        .profile-header {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 20px;
        }

        .profile-avatar {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            overflow: hidden;
            position: relative;
        }

        .profile-avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .profile-avatar .edit-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background-color: rgba(0, 0, 0, 0.6);
            color: white;
            text-align: center;
            padding: 5px;
            font-size: 12px;
            cursor: pointer;
            display: none;
        }

        .profile-avatar:hover .edit-overlay {
            display: block;
        }

        .profile-info h2 {
            margin: 0;
            font-size: 20px;
        }

        .profile-info p {
            margin: 5px 0 0;
            color: #65676B;
        }

        .profile-stats {
            display: flex;
            justify-content: space-around;
            background-color: white;
            border-radius: 10px;
            padding: 15px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            margin-bottom: 20px;
        }

        .profile-menu {
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            overflow: hidden;
        }

        .menu-item {
            padding: 15px;
            border-bottom: 1px solid #eee;
            display: flex;
            align-items: center;
            gap: 10px;
            cursor: pointer;
        }

        .menu-item:last-child {
            border-bottom: none;
        }

        .menu-item:hover {
            background-color: #f0f2f5;
        }

        /* Bottom Navigation */
        .bottom-nav {
            position: fixed;
            bottom: 0;
            width: 100%;
            max-width: 600px;
            display: flex;
            justify-content: space-around;
            background-color: white;
            padding: 10px 0;
            border-top: 1px solid #eee;
            z-index: 100;
            box-shadow: 0 -2px 5px rgba(0, 0, 0, 0.1);
        }

        .nav-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 3px;
            color: #65676B;
            cursor: pointer;
        }

        .nav-item.active {
            color: #4267B2;
        }

        .nav-icon {
            font-size: 20px;
        }

        .nav-label {
            font-size: 12px;
        }

        /* Product Listing Page Styles */
        .product-listing-page {
            display: none;
            padding: 15px;
        }

        .product-listing-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            position: relative;
        }

        .categories-btn {
            background-color: #4267B2;
            color: white;
            border: none;
            padding: 10px 15px;
            border-radius: 5px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 5px;
        }

        .sell-btn {
            background-color: #42B983;
            color: white;
            border: none;
            padding: 10px 15px;
            border-radius: 5px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 5px;
        }

        /* Product Form Styles */
        .product-form-container {
            display: none;
            padding: 15px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            margin-bottom: 20px;
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }

        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }

        .form-title {
            text-align: center;
            color: #4267B2;
            margin-bottom: 20px;
        }

        .payment-options {
            display: flex;
            gap: 15px;
            margin-bottom: 15px;
        }

        .payment-option {
            flex: 1;
            text-align: center;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            cursor: pointer;
        }

        .payment-option.selected {
            border-color: #4267B2;
            background-color: #f0f7ff;
        }

        .upload-btn {
            display: block;
            width: 100%;
            padding: 10px;
            background-color: #f0f2f5;
            border: 1px dashed #ddd;
            border-radius: 5px;
            text-align: center;
            cursor: pointer;
            margin-bottom: 15px;
        }

        .submit-btn {
            display: block;
            width: 100%;
            padding: 12px;
            background-color: #4267B2;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
        }

        /* Image Preview Styles */
        .image-preview {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin: 15px 0;
        }

        .image-preview img {
            width: 100px;
            height: 100px;
            object-fit: cover;
            border-radius: 5px;
        }

        /* Status Messages */
        .loader, .success, .error {
            display: none;
            text-align: center;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
        }

        .loader {
            background-color: #f0f7ff;
            color: #4267B2;
        }

        .success {
            background-color: #f0fff4;
            color: #2ecc71;
        }

        .error {
            background-color: #fff0f0;
            color: #e74c3c;
        }

        /* Categories Page Styles */
        .categories-page {
            display: none;
            padding: 15px;
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: white;
            z-index: 1000;
        }

        .categories-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .categories-list {
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            overflow: hidden;
        }

        .category-item {
            padding: 15px;
            border-bottom: 1px solid #eee;
            cursor: pointer;
        }

        .category-item:last-child {
            border-bottom: none;
        }

        .category-item:hover {
            background-color: #f0f2f5;
        }

        /* Profile Setup Modal Styles */
        .profile-setup-modal {
            display: none;
        }

        .profile-setup-content {
            background-color: white;
            width: 90%;
            max-width: 500px;
            border-radius: 10px;
            overflow: hidden;
            max-height: 90vh;
            overflow-y: auto;
        }

        .profile-setup-header {
            padding: 15px;
            border-bottom: 1px solid #eee;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: #4267B2;
            color: white;
        }

        .profile-setup-body {
            padding: 20px;
        }

        .profile-setup-footer {
            padding: 15px;
            border-top: 1px solid #eee;
            display: flex;
            justify-content: flex-end;
            gap: 10px;
        }

        .profile-avatar-upload {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin-bottom: 20px;
        }

        .profile-avatar-large {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            overflow: hidden;
            margin-bottom: 10px;
            position: relative;
        }

        .profile-avatar-large img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .profile-avatar-large .edit-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background-color: rgba(0, 0, 0, 0.6);
            color: white;
            text-align: center;
            padding: 8px;
            font-size: 14px;
            cursor: pointer;
        }

        .form-row {
            display: flex;
            gap: 15px;
            margin-bottom: 15px;
        }

        .form-row .form-group {
            flex: 1;
            margin-bottom: 0;
        }

        .phone-input-container {
            display: flex;
            gap: 10px;
        }

        .phone-input-container .iti {
            width: 100%;
        }

        .phone-input-container .iti__selected-flag {
            padding: 0 10px;
        }

        .phone-input-container .iti__country-list {
            z-index: 1001;
        }

        .email-options {
            margin-top: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            overflow: hidden;
        }

        .email-option {
            padding: 12px 15px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 10px;
            border-bottom: 1px solid #eee;
        }

        .email-option:last-child {
            border-bottom: none;
        }

        .email-option:hover {
            background-color: #f5f5f5;
        }

        .email-option i {
            font-size: 18px;
        }

        .google-option {
            color: #DB4437;
        }

        .create-option {
            color: #4267B2;
        }

        .email-input-container {
            display: flex;
            gap: 10px;
        }

        .email-input-container input {
            flex: 1;
        }

        .verify-btn {
            background-color: #4267B2;
            color: white;
            border: none;
            border-radius: 5px;
            padding: 10px 15px;
            cursor: pointer;
            white-space: nowrap;
        }

        .verify-btn:disabled {
            background-color: #cccccc;
            cursor: not-allowed;
        }

        .verification-code {
            display: none;
            margin-top: 10px;
        }

        .verification-code.active {
            display: block;
        }

        .code-inputs {
            display: flex;
            gap: 10px;
            margin-bottom: 10px;
        }

        .code-input {
            width: 40px;
            height: 40px;
            text-align: center;
            font-size: 18px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }

        .resend-code {
            color: #4267B2;
            font-size: 14px;
            cursor: pointer;
            text-align: center;
            margin-top: 10px;
        }

        .google-connect-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }

        .google-connect-content {
            background-color: white;
            width: 90%;
            max-width: 400px;
            border-radius: 10px;
            overflow: hidden;
        }

        .google-connect-header {
            padding: 15px;
            border-bottom: 1px solid #eee;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: #DB4437;
            color: white;
        }

        .google-connect-body {
            padding: 20px;
            text-align: center;
        }

        .google-connect-icon {
            font-size: 48px;
            color: #DB4437;
            margin-bottom: 20px;
        }

        .google-connect-title {
            font-size: 20px;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .google-connect-description {
            margin-bottom: 20px;
            color: #666;
        }

        .google-connect-options {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .google-connect-option {
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 5px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .google-connect-option:hover {
            background-color: #f5f5f5;
        }

        .google-connect-option i {
            font-size: 18px;
        }

        .google-connect-footer {
            padding: 15px;
            border-top: 1px solid #eee;
            display: flex;
            justify-content: flex-end;
        }

        /* Help & Support Section Styles */
        .help-support-section {
            padding: 15px;
            display: none;
        }

        .support-header {
            text-align: center;
            margin-bottom: 30px;
        }

        .support-header h2 {
            color: #4267B2;
            margin-bottom: 10px;
        }

        .support-header p {
            color: #65676B;
            font-size: 16px;
        }

        .support-options {
            display: flex;
            flex-direction: column;
            gap: 20px;
            margin-bottom: 30px;
        }

        .support-option {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 20px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            cursor: pointer;
            transition: transform 0.2s ease, box-shadow 0.2s ease;
        }

        .support-option:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
        }

        .support-icon {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            color: white;
        }

        .whatsapp-icon {
            background-color: #25D366;
        }

        .call-icon {
            background-color: #4267B2;
        }

        .support-info {
            flex: 1;
        }

        .support-info h3 {
            margin: 0 0 5px 0;
            font-size: 18px;
        }

        .support-info p {
            margin: 0;
            color: #65676B;
            font-size: 14px;
        }

        .faq-section {
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            overflow: hidden;
        }

        .faq-header {
            padding: 15px;
            border-bottom: 1px solid #eee;
            font-weight: bold;
            background-color: #f8f9fa;
        }

        .faq-item {
            padding: 15px;
            border-bottom: 1px solid #eee;
        }

        .faq-item:last-child {
            border-bottom: none;
        }

        .faq-question {
            font-weight: bold;
            margin-bottom: 10px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            cursor: pointer;
        }

        .faq-answer {
            color: #65676B;
            line-height: 1.5;
            display: none;
        }

        .faq-item.active .faq-answer {
            display: block;
        }

        /* Product Details Page Styles */
        .product-details-page {
            display: none;
            padding: 15px;
        }

        .product-details-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .back-btn {
            background-color: #f0f2f5;
            border: none;
            padding: 10px;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .product-details-image {
            width: 100%;
            height: 300px;
            object-fit: cover;
            border-radius: 10px;
            margin-bottom: 20px;
        }

        .product-details-info {
            background-color: white;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            margin-bottom: 20px;
        }

        .product-details-name {
            font-size: 24px;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .product-details-price {
            font-size: 20px;
            color: #4267B2;
            font-weight: bold;
            margin-bottom: 15px;
        }

        .product-details-company {
            font-size: 16px;
            color: #65676B;
            margin-bottom: 15px;
        }

        .product-details-description {
            line-height: 1.6;
            margin-bottom: 20px;
        }

        .product-details-meta {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
            font-size: 14px;
            color: #65676B;
        }

        .product-details-actions {
            display: flex;
            gap: 10px;
        }

        .action-btn {
            flex: 1;
            padding: 12px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .buy-btn {
            background-color: #4267B2;
            color: white;
        }

        .contact-btn {
            background-color: #42B983;
            color: white;
        }

        .wishlist-btn {
            background-color: #f0f2f5;
            color: #333;
        }

        .wishlist-btn.active {
            background-color: #ffe6e6;
            color: #e74c3c;
        }

        .wishlist-btn.active i {
            color: #e74c3c;
        }

        /* Wishlist Page Styles */
        .wishlist-page {
            display: none;
            padding: 15px;
        }

        .wishlist-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .wishlist-title {
            font-size: 24px;
            font-weight: bold;
            color: #4267B2;
        }

        .wishlist-empty {
            text-align: center;
            padding: 40px 20px;
            color: #65676B;
        }

        .wishlist-empty i {
            font-size: 64px;
            margin-bottom: 20px;
            color: #ddd;
        }

        .wishlist-empty h3 {
            margin-bottom: 10px;
        }

        .wishlist-empty p {
            margin-bottom: 20px;
        }

        .wishlist-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
        }

        .wishlist-item {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
            position: relative;
        }

        .wishlist-remove {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: rgba(255, 255, 255, 0.8);
            border-radius: 50%;
            width: 30px;
            height: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            color: #e74c3c;
            font-size: 14px;
        }

        .wishlist-remove:hover {
            background-color: white;
        }

        /* Add Friends Section Styles */
        .friends-section {
            padding: 15px;
            display: none;
        }

        .friends-tabs {
            display: flex;
            border-bottom: 1px solid #ddd;
            margin-bottom: 20px;
        }

        .friends-tab {
            flex: 1;
            text-align: center;
            padding: 12px;
            cursor: pointer;
            border-bottom: 3px solid transparent;
            font-weight: bold;
            color: #65676B;
        }

        .friends-tab.active {
            color: #4267B2;
            border-bottom-color: #4267B2;
        }

        .friends-list {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .friend-item {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 15px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .friend-avatar {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            overflow: hidden;
        }

        .friend-avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .friend-info {
            flex: 1;
        }

        .friend-name {
            font-weight: bold;
            margin-bottom: 5px;
        }

        .friend-mutual {
            font-size: 14px;
            color: #65676B;
        }

        .friend-actions {
            display: flex;
            gap: 10px;
        }

        .friend-action-btn {
            padding: 8px 15px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
        }

        .add-friend-btn {
            background-color: #4267B2;
            color: white;
        }

        .cancel-request-btn {
            background-color: #e4e6eb;
            color: #333;
        }

        .message-btn {
            background-color: #42B983;
            color: white;
        }

        .friend-status {
            font-size: 14px;
            color: #65676B;
            font-style: italic;
        }

        .empty-state {
            text-align: center;
            padding: 40px 20px;
            color: #65676B;
        }

        .empty-state i {
            font-size: 64px;
            margin-bottom: 20px;
            color: #ddd;
        }

        .empty-state h3 {
            margin-bottom: 10px;
        }

        .empty-state p {
            margin-bottom: 20px;
        }

        /* Update bottom nav to include friends icon */
        .notification-badge {
            position: absolute;
            top: -5px;
            right: -5px;
            background-color: #ff4444;
            color: white;
            border-radius: 50%;
            width: 18px;
            height: 18px;
            font-size: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
        }

        /* Messaging Styles */
        .messaging-container {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: white;
            z-index: 1000;
            flex-direction: column;
        }

        .messaging-header {
            display: flex;
            align-items: center;
            padding: 15px;
            background-color: #4267B2;
            color: white;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .messaging-back-btn {
            background: none;
            border: none;
            color: white;
            font-size: 18px;
            margin-right: 15px;
            cursor: pointer;
        }

        .messaging-user-info {
            display: flex;
            align-items: center;
            flex: 1;
        }

        .messaging-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            overflow: hidden;
            margin-right: 10px;
        }

        .messaging-avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .messaging-user-name {
            font-weight: bold;
            font-size: 16px;
        }

        .messaging-body {
            flex: 1;
            overflow-y: auto;
            padding: 15px;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .message {
            max-width: 70%;
            padding: 10px 15px;
            border-radius: 18px;
            position: relative;
            word-wrap: break-word;
        }

        .message.received {
            align-self: flex-start;
            background-color: #f0f0f0;
            color: #333;
            border-bottom-left-radius: 5px;
        }

        .message.sent {
            align-self: flex-end;
            background-color: #4267B2;
            color: white;
            border-bottom-right-radius: 5px;
        }

        .message-time {
            font-size: 11px;
            margin-top: 5px;
            opacity: 0.7;
            text-align: right;
        }

        .message.received .message-time {
            text-align: left;
        }

        .messaging-footer {
            display: flex;
            padding: 15px;
            border-top: 1px solid #eee;
            background-color: white;
        }

        .message-input {
            flex: 1;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 24px;
            outline: none;
            font-size: 14px;
        }

        .send-btn {
            background-color: #4267B2;
            color: white;
            border: none;
            border-radius: 50%;
            width: 44px;
            height: 44px;
            margin-left: 10px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .message-notification {
            position: fixed;
            top: 70px;
            right: 20px;
            background-color: #4267B2;
            color: white;
            padding: 10px 15px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
            display: none;
            align-items: center;
            z-index: 1001;
            max-width: 300px;
        }

        .notification-avatar {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            overflow: hidden;
            margin-right: 10px;
        }

        .notification-avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .notification-content {
            flex: 1;
        }

        .notification-close {
            background: none;
            border: none;
            color: white;
            cursor: pointer;
            margin-left: 10px;
        }

        /* Notifications Panel Styles */
        .notifications-panel {
            position: fixed;
            top: 60px;
            right: 20px;
            width: 350px;
            max-height: 500px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            z-index: 1002;
            display: none;
            flex-direction: column;
            overflow: hidden;
        }

        .notifications-header {
            padding: 15px;
            border-bottom: 1px solid #eee;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .notifications-title {
            font-weight: bold;
            font-size: 16px;
        }

        .notifications-actions {
            display: flex;
            gap: 10px;
        }

        .notifications-action {
            background: none;
            border: none;
            color: #4267B2;
            cursor: pointer;
            font-size: 14px;
        }

        .notifications-list {
            flex: 1;
            overflow-y: auto;
        }

        .notification-item {
            padding: 15px;
            border-bottom: 1px solid #f0f0f0;
            cursor: pointer;
            display: flex;
            align-items: flex-start;
            gap: 10px;
        }

        .notification-item.unread {
            background-color: #f0f8ff;
        }

        .notification-icon {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 16px;
            flex-shrink: 0;
        }

        .notification-icon.like {
            background-color: #ff4444;
        }

        .notification-icon.comment {
            background-color: #4267B2;
        }

        .notification-icon.friend {
            background-color: #42B983;
        }

        .notification-icon.message {
            background-color: #FF9800;
        }

        .notification-icon.system {
            background-color: #9C27B0;
        }

        .notification-content {
            flex: 1;
        }

        .notification-text {
            margin-bottom: 5px;
            line-height: 1.4;
        }

        .notification-time {
            font-size: 12px;
            color: #65676B;
        }

        .notification-dot {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background-color: #4267B2;
            flex-shrink: 0;
            margin-top: 5px;
        }

        .notifications-empty {
            padding: 40px 20px;
            text-align: center;
            color: #65676B;
        }

        .notifications-empty i {
            font-size: 48px;
            margin-bottom: 15px;
            color: #ddd;
        }

        .notification-settings {
            padding: 15px;
            border-top: 1px solid #eee;
        }

        .notification-setting-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
        }

        .notification-setting-label {
            font-size: 14px;
        }

        .notification-toggle {
            position: relative;
            display: inline-block;
            width: 44px;
            height: 24px;
        }

        .notification-toggle input {
            opacity: 0;
            width: 0;
            height: 0;
        }

        .notification-slider {
            position: absolute;
            cursor: pointer;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: #ccc;
            transition: .4s;
            border-radius: 24px;
        }

        .notification-slider:before {
            position: absolute;
            content: "";
            height: 16px;
            width: 16px;
            left: 4px;
            bottom: 4px;
            background-color: white;
            transition: .4s;
            border-radius: 50%;
        }

        input:checked + .notification-slider {
            background-color: #4267B2;
        }

        input:checked + .notification-slider:before {
            transform: translateX(20px);
        }

        /* Push Notification Styles */
        .push-notification {
            position: fixed;
            top: 20px;
            right: 20px;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
            padding: 15px;
            width: 300px;
            z-index: 1003;
            display: none;
            animation: slideInRight 0.3s ease-out;
            border-left: 4px solid #4267B2;
        }

        .push-notification-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 8px;
        }

        .push-notification-title {
            font-weight: bold;
            font-size: 14px;
            color: #4267B2;
        }

        .push-notification-close {
            background: none;
            border: none;
            color: #65676B;
            cursor: pointer;
            font-size: 16px;
        }

        .push-notification-body {
            font-size: 13px;
            line-height: 1.4;
            color: #333;
        }

        .push-notification-footer {
            margin-top: 10px;
            display: flex;
            justify-content: flex-end;
            gap: 10px;
        }

        .push-notification-btn {
            padding: 5px 10px;
            border: none;
            border-radius: 4px;
            font-size: 12px;
            cursor: pointer;
        }

        .push-notification-btn.primary {
            background-color: #4267B2;
            color: white;
        }

        .push-notification-btn.secondary {
            background-color: #f0f0f0;
            color: #333;
        }

        @keyframes slideInRight {
            from {
                transform: translateX(100%);
                opacity: 0;
            }
            to {
                transform: translateX(0);
                opacity: 1;
            }
        }

        @keyframes slideOutRight {
            from {
                transform: translateX(0);
                opacity: 1;
            }
            to {
                transform: translateX(100%);
                opacity: 0;
            }
        }
        
        /* Payment Modal Styles */
        .payment-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }

        .payment-content {
            background-color: white;
            width: 90%;
            max-width: 400px;
            border-radius: 10px;
            overflow: hidden;
            max-height: 90vh;
            overflow-y: auto;
        }

        .payment-header {
            padding: 15px;
            border-bottom: 1px solid #eee;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: #4267B2;
            color: white;
        }

        .payment-body {
            padding: 20px;
        }

        .payment-footer {
            padding: 15px;
            border-top: 1px solid #eee;
            display: flex;
            justify-content: flex-end;
            gap: 10px;
        }

        .payment-amount {
            text-align: center;
            font-size: 24px;
            font-weight: bold;
            color: #4267B2;
            margin: 20px 0;
        }

        .payment-instructions {
            background-color: #f8f9fa;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 20px;
        }

        .payment-instructions ol {
            padding-left: 20px;
            margin: 10px 0;
        }

        .payment-instructions li {
            margin-bottom: 8px;
            line-height: 1.4;
        }

        .payment-account {
            background-color: #e8f4fd;
            padding: 15px;
            border-radius: 8px;
            text-align: center;
            margin-bottom: 20px;
        }

        .payment-account-number {
            font-size: 18px;
            font-weight: bold;
            color: #4267B2;
            margin: 10px 0;
        }

        .payment-reference {
            font-size: 14px;
            color: #65676B;
        }

        .payment-confirmation {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin-bottom: 20px;
        }

        .payment-status {
            text-align: center;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            display: none;
        }

        .payment-success {
            background-color: #f0fff4;
            color: #2ecc71;
        }

        .payment-error {
            background-color: #fff0f0;
            color: #e74c3c;
        }

        .payment-processing {
            background-color: #f0f7ff;
            color: #4267B2;
        }

        .payment-actions {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .payment-btn {
            padding: 12px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            width: 100%;
        }

        .confirm-payment-btn {
            background-color: #4267B2;
            color: white;
        }

        .cancel-payment-btn {
            background-color: #e4e6eb;
            color: #333;
        }

        .skip-payment-btn {
            background-color: #42B983;
            color: white;
        }

        /* Password Setup Page Styles */
        .password-setup-page {
            display: none;
            padding: 20px;
            max-width: 500px;
            margin: 0 auto;
            background-color: white;
            min-height: 100vh;
        }
        
        .password-setup-header {
            text-align: center;
            margin-bottom: 30px;
        }
        
        .password-setup-header h2 {
            color: #4267B2;
            margin-bottom: 10px;
        }
        
        .password-setup-header p {
            color: #65676B;
            font-size: 16px;
        }
        
        .password-form {
            background-color: white;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        
        .password-strength {
            margin-top: 5px;
            height: 5px;
            border-radius: 5px;
            background-color: #f0f0f0;
            overflow: hidden;
        }
        
        .password-strength-bar {
            height: 100%;
            width: 0%;
            border-radius: 5px;
            transition: width 0.3s ease;
        }
        
        .password-strength-text {
            font-size: 12px;
            margin-top: 5px;
            color: #65676B;
        }
        
        .password-requirements {
            margin-top: 15px;
            font-size: 14px;
            color: #65676B;
        }
        
        .password-requirements ul {
            padding-left: 20px;
            margin: 10px 0;
        }
        
        .password-requirements li {
            margin-bottom: 5px;
            list-style-type: none;
            position: relative;
        }
        
        .password-requirements li:before {
            content: "•";
            color: #ddd;
            position: absolute;
            left: -15px;
        }
        
        .password-requirements li.valid {
            color: #42B983;
        }
        
        .password-requirements li.valid:before {
            color: #42B983;
        }
        
        .forgot-password {
            text-align: center;
            margin-top: 20px;
        }
        
        .forgot-password-btn {
            background: none;
            border: none;
            color: #4267B2;
            cursor: pointer;
            font-size: 14px;
            text-decoration: underline;
        }
        
        .password-actions {
            display: flex;
            gap: 10px;
            margin-top: 20px;
        }
        
        .password-btn {
            flex: 1;
            padding: 12px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
        }
        
        .password-cancel {
            background-color: #e4e6eb;
            color: #333;
        }
        
        .password-submit {
            background-color: #4267B2;
            color: white;
        }
        
        /* Email Verification Page Styles */
        .email-verification-page {
            display: none;
            padding: 20px;
            max-width: 500px;
            margin: 0 auto;
            background-color: white;
            min-height: 100vh;
        }
        
        .email-verification-header {
            text-align: center;
            margin-bottom: 30px;
        }
        
        .email-verification-header h2 {
            color: #4267B2;
            margin-bottom: 10px;
        }
        
        .email-verification-header p {
            color: #65676B;
            font-size: 16px;
        }
        
        .email-verification-form {
            background-color: white;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        
        .email-actions {
            display: flex;
            gap: 10px;
            margin-top: 20px;
        }
        
        .email-btn {
            flex: 1;
            padding: 12px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
        }
        
        .email-cancel {
            background-color: #e4e6eb;
            color: #333;
        }
        
        .email-save {
            background-color: #4267B2;
            color: white;
        }
        
        /* Password Recovery Modal Styles */
        .password-recovery-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }
        
        .password-recovery-content {
            background-color: white;
            width: 90%;
            max-width: 400px;
            border-radius: 10px;
            overflow: hidden;
            max-height: 90vh;
            overflow-y: auto;
        }
        
        .password-recovery-header {
            padding: 15px;
            border-bottom: 1px solid #eee;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: #4267B2;
            color: white;
        }
        
        .password-recovery-body {
            padding: 20px;
        }
        
        .password-recovery-footer {
            padding: 15px;
            border-top: 1px solid #eee;
            display: flex;
            justify-content: flex-end;
            gap: 10px;
        }
        
        .recovery-options {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin-bottom: 20px;
        }
        
        .recovery-option {
            padding: 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .recovery-option:hover {
            background-color: #f5f5f5;
        }
        
        .recovery-option i {
            font-size: 20px;
            color: #4267B2;
        }
        
        .recovery-form {
            display: none;
        }
        
        .recovery-form.active {
            display: block;
        }
        
        .recovery-instructions {
            background-color: #f8f9fa;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 20px;
            font-size: 14px;
            color: #65676B;
        }
        
        .recovery-actions {
            display: flex;
            gap: 10px;
            margin-top: 20px;
        }
        
        .recovery-btn {
            flex: 1;
            padding: 12px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
        }
        
        .recovery-cancel {
            background-color: #e4e6eb;
            color: #333;
        }
        
        .recovery-submit {
            background-color: #4267B2;
            color: white;
        }
        
        /* Success Message Styles */
        .success-message {
            text-align: center;
            padding: 20px;
            background-color: #f0fff4;
            color: #2ecc71;
            border-radius: 8px;
            margin-bottom: 20px;
            display: none;
            
        }
        
        .success-message i {
            font-size: 48px;
            margin-bottom: 15px;
        }
        
        /* Withdrawal Password Verification Styles */
        .withdrawal-password-page {
            display: none;
            padding: 20px;
            max-width: 500px;
            margin: 0 auto;
            background-color: white;
            min-height: 100vh;
            position: relative;
        }
        
        .withdrawal-password-header {
            text-align: center;
            margin-bottom: 30px;
        }
        
        .withdrawal-password-header h2 {
            color: #4267B2;
            margin-bottom: 10px;
        }
        
        .withdrawal-password-header p {
            color: #65676B;
            font-size: 16px;
        }
        
        .withdrawal-password-form {
            background-color: white;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        
        .withdrawal-amount {
            text-align: center;
            margin-bottom: 20px;
            padding: 15px;
            background-color: #f8f9fa;
            border-radius: 8px;
        }
        
        .withdrawal-amount-label {
            font-size: 14px;
            color: #65676B;
            margin-bottom: 5px;
        }
        
        .withdrawal-amount-value {
            font-size: 24px;
            font-weight: bold;
            color: #4267B2;
        }
        
        .withdrawal-phone {
            text-align: center;
            margin-bottom: 20px;
            padding: 15px;
            background-color: #e8f4fd;
            border-radius: 8px;
        }
        
        .withdrawal-phone-label {
            font-size: 14px;
            color: #65676B;
            margin-bottom: 5px;
        }
        
        .withdrawal-phone-value {
            font-size: 18px;
            font-weight: bold;
            color: #4267B2;
        }
        
        .withdrawal-actions {
            display: flex;
            gap: 10px;
            margin-top: 20px;
        }
        
        .withdrawal-btn {
            flex: 1;
            padding: 12px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
        }
        
        .withdrawal-cancel {
            background-color: #e4e6eb;
            color: #333;
        }
        
        .withdrawal-confirm {
            background-color: #4267B2;
            color: white;
        }
        
        /* Responsive Adjustments */
        @media (max-width: 480px) {
            .ad-banner-container {
                height: 120px;
            }
            
            .products-grid {
                grid-template-columns: 1fr;
            }
            
            .form-row {
                flex-direction: column;
                gap: 0;
            }
            
            .support-option {
                padding: 15px;
            }
            
            .support-icon {
                width: 50px;
                height: 50px;
                font-size: 20px;
            }
            
            .product-details-image {
                height: 250px;
            }
            
            .product-details-actions {
                flex-direction: column;
            }
            
            .password-actions,
            .email-actions,
            .recovery-actions,
            .withdrawal-actions {
                flex-direction: column;
            }
            
            .password-btn,
            .email-btn,
            .recovery-btn,
            .withdrawal-btn {
                width: 100%;
            }
        }        
        
        /* Settings Section Styles - Modified to be separate */
        .settings-section {
            padding: 15px;
            display: none;
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: white;
            z-index: 1000;
            overflow-y: auto;
        }

        .settings-header {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
            gap: 15px;
        }

        .settings-title {
            font-size: 24px;
            font-weight: bold;
            color: #4267B2;
        }

        .settings-menu {
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            margin-bottom: 20px;
        }

        .settings-category {
            padding: 15px;
            border-bottom: 1px solid #eee;
            font-weight: bold;
            background-color: #f8f9fa;
        }

        .settings-item {
            padding: 15px;
            border-bottom: 1px solid #eee;
            display: flex;
            justify-content: space-between;
            align-items: center;
            cursor: pointer;
        }

        .settings-item:last-child {
            border-bottom: none;
        }

        .settings-item:hover {
            background-color: #f0f2f5;
        }

        .settings-item-info {
            display: flex;
            flex-direction: column;
            flex: 1;
        }

        .settings-item-title {
            font-weight: bold;
            margin-bottom: 5px;
        }

        .settings-item-description {
            font-size: 14px;
            color: #65676B;
        }

        .settings-item-action {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .toggle-switch {
            position: relative;
            display: inline-block;
            width: 44px;
            height: 24px;
        }

        .toggle-switch input {
            opacity: 0;
            width: 0;
            height: 0;
        }

        .toggle-slider {
            position: absolute;
            cursor: pointer;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: #ccc;
            transition: .4s;
            border-radius: 24px;
        }

        .toggle-slider:before {
            position: absolute;
            content: "";
            height: 16px;
            width: 16px;
            left: 4px;
            bottom: 4px;
            background-color: white;
            transition: .4s;
            border-radius: 50%;
        }

        input:checked + .toggle-slider {
            background-color: #4267B2;
        }

        input:checked + .toggle-slider:before {
            transform: translateX(20px);
        }

        .chevron-right {
            color: #65676B;
        }

        /* Dark Mode Styles */
        body.dark-mode {
            background-color: #18191a;
            color: #e4e6eb;
        }

        body.dark-mode .container {
            background-color: #242526;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
        }

        body.dark-mode .header {
            background-color: #242526;
            border-bottom: 1px solid #393a3b;
        }

        body.dark-mode .create-post,
        body.dark-mode .post,
        body.dark-mode .products-section,
        body.dark-mode .earnings-section,
        body.dark-mode .profile-section,
        body.dark-mode .friends-section,
        body.dark-mode .help-support-section,
        body.dark-mode .product-listing-page,
        body.dark-mode .product-form-container,
        body.dark-mode .categories-page,
        body.dark-mode .settings-section,
        body.dark-mode .settings-menu,
        body.dark-mode .profile-menu,
        body.dark-mode .faq-section,
        body.dark-mode .product-details-info,
        body.dark-mode .earnings-stats,
        body.dark-mode .profile-stats,
        body.dark-mode .wishlist-item,
        body.dark-mode .friend-item,
        body.dark-mode .support-option,
        body.dark-mode .modal-content,
        body.dark-mode .profile-setup-content,
        body.dark-mode .google-connect-content,
        body.dark-mode .password-setup-page,
        body.dark-mode .email-verification-page,
        body.dark-mode .password-recovery-content,
        body.dark-mode .withdrawal-password-page,
        body.dark-mode .payment-content,
        body.dark-mode .notifications-panel,
        body.dark-mode .push-notification {
            background-color: #242526;
            color: #e4e6eb;
        }      
        
        /* Add missing modal styles */
        .language-modal,
        .privacy-modal,
        .ads-creation-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }

        .language-content,
        .privacy-content,
        .ads-creation-content {
            background-color: white;
            width: 90%;
            max-width: 400px;
            border-radius: 10px;
            overflow: hidden;
            max-height: 90vh;
            overflow-y: auto;
        }

        .language-header,
        .privacy-header,
        .ads-creation-header {
            padding: 15px;
            border-bottom: 1px solid #eee;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: #4267B2;
            color: white;
        }

        .language-body,
        .privacy-body,
        .ads-creation-body {
            padding: 20px;
        }

        .language-footer,
        .privacy-footer,
        .ads-creation-footer {
            padding: 15px;
            border-top: 1px solid #eee;
            display: flex;
            justify-content: flex-end;
            gap: 10px;
        }

        .language-option {
            padding: 15px;
            border-bottom: 1px solid #eee;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .language-option:last-child {
            border-bottom: none;
        }

        .language-option:hover {
            background-color: #f0f2f5;
        }

        .language-check {
            color: #4267B2;
            font-size: 14px;
            display: none;
        }

        .ads-preview {
            width: 100%;
            height: 200px;
            background-color: #f0f0f0;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 15px;
            overflow: hidden;
        }

        .ads-preview img {
            max-width: 100%;
            max-height: 100%;
            object-fit: contain;
        }

        /* Dark mode styles for new elements */
        body.dark-mode .language-content,
        body.dark-mode .privacy-content,
        body.dark-mode .ads-creation-content {
            background-color: #242526;
            color: #e4e6eb;
        }

        body.dark-mode .language-option:hover,
        body.dark-mode .privacy-option:hover {
            background-color: #3a3b3c;
        }

        body.dark-mode .ads-preview {
            background-color: #3a3b3c;
        }

                                                                                                                                                                      
                                                                                                  
        /* Ads Payment Page Styles - Modified to be a next page */
        .ads-payment-page {
            position: absolute;
            display: none;
            top: 1px;
            padding: 20px;
            max-width: 500px;
            margin: 0 auto;
            background-color: white;
            min-height: 85vh;
            overflow-y: auto;
            z-index: 1000;
        }
        
        .ads-payment-header {
            text-align: center;
            margin-bottom: 30px;
        }
        
        .ads-payment-header h2 {
            color: #4267B2;
            margin-bottom: 10px;
        }
        
        .ads-payment-header p {
            color: #65676B;
            font-size: 16px;
        }
        
        .ads-payment-form {
            background-color: white;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        
        .ads-payment-summary {
            background-color: #f8f9fa;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 20px;
        }
        
        .ads-payment-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
        }
        
        .ads-payment-label {
            color: #65676B;
        }
        
        .ads-payment-value {
            font-weight: bold;
        }
        
        .ads-payment-total {
            display: flex;
            justify-content: space-between;
            margin-top: 10px;
            padding-top: 10px;
            border-top: 1px solid #ddd;
            font-size: 18px;
            font-weight: bold;
            color: #4267B2;
        }
        
        .ads-payment-instructions {
            background-color: #f0f7ff;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 20px;
            font-size: 14px;
            color: #4267B2;
        }
        
        .ads-payment-instructions ol {
            padding-left: 20px;
            margin: 10px 0;
        }
        
        .ads-payment-instructions li {
            margin-bottom: 8px;
            line-height: 1.4;
        }
        
        .ads-payment-account {
            background-color: #e8f4fd;
            padding: 15px;
            border-radius: 8px;
            text-align: center;
            margin-bottom: 20px;
        }
        
        .ads-payment-account-number {
            font-size: 18px;
            font-weight: bold;
            color: #4267B2;
            margin: 10px 0;
        }
        
        .ads-payment-reference {
            font-size: 14px;
            color: #65676B;
        }
        
        .ads-payment-confirmation {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin-bottom: 20px;
        }
        
        .ads-payment-status {
            text-align: center;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            display: none;
        }
        
        .ads-payment-success {
            background-color: #f0fff4;
            color: #2ecc71;
        }
        
        .ads-payment-error {
            background-color: #fff0f0;
            color: #e74c3c;
        }
        
        .ads-payment-processing {
            background-color: #f0f7ff;
            color: #4267B2;
        }
        
        .ads-payment-actions {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        
        .ads-payment-btn {
            padding: 12px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            width: 100%;
        }
        
        .confirm-ads-payment-btn {
            background-color: #4267B2;
            color: white;
        }
        
        .cancel-ads-payment-btn {
            background-color: #e4e6eb;
            color: #333;
        }
        
        .back-to-ads-btn {
            background-color: #42B983;
            color: white;
        }
        
        /* Dark mode styles for ads payment page */
        body.dark-mode .ads-payment-page,
        body.dark-mode .ads-payment-form {
            background-color: #242526;
            color: #e4e6eb;
        }
        
        body.dark-mode .ads-payment-summary {
            background-color: #3a3b3c;
        }
        
        body.dark-mode .ads-payment-instructions {
            background-color: #2d3748;
        }
        
        body.dark-mode .ads-payment-account {
            background-color: #2d3748;
        }
                                                      
        
        /* Share Modal Styles */
.share-modal {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.7);
    z-index: 1000;
    align-items: center;
    justify-content: center;
}

.share-content {
    background-color: white;
    width: 90%;
    max-width: 500px;
    border-radius: 10px;
    overflow: hidden;
    max-height: 90vh;
    overflow-y: auto;
}

.share-header {
    padding: 15px;
    border-bottom: 1px solid #eee;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #4267B2;
    color: white;
}

.share-body {
    padding: 20px;
}

.share-options-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 15px;
    margin-bottom: 20px;
}

.share-option {
    display: flex;
    flex-direction: column;
    align-items: center;
    cursor: pointer;
    transition: transform 0.2s;
}

.share-option:hover {
    transform: translateY(-5px);
}

.share-icon {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-size: 20px;
    margin-bottom: 8px;
}

.share-label {
    font-size: 12px;
    text-align: center;
    color: #333;
}

.share-post-preview {
    background-color: #f8f9fa;
    border-radius: 8px;
    padding: 15px;
    margin-bottom: 15px;
    max-height: 200px;
    overflow-y: auto;
}

.share-preview-content {
    display: flex;
    flex-direction: column;
    gap: 10px;
}

.share-preview-user {
    display: flex;
    align-items: center;
    gap: 10px;
}

.share-preview-avatar {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    overflow: hidden;
}

.share-preview-avatar img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.share-preview-info {
    flex: 1;
}

.share-preview-name {
    font-weight: bold;
    font-size: 14px;
}

.share-preview-time {
    font-size: 12px;
    color: #65676B;
}

.share-preview-caption {
    font-size: 14px;
    line-height: 1.4;
    color: #333;
}

.share-preview-media {
    width: 100%;
    border-radius: 5px;
    overflow: hidden;
    max-height: 100px;
    object-fit: cover;
}

.share-message {
    margin-top: 15px;
}

.share-message textarea {
    width: 100%;
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 5px;
    resize: vertical;
    font-family: inherit;
    font-size: 14px;
}

.share-footer {
    padding: 15px;
    border-top: 1px solid #eee;
    display: flex;
    justify-content: space-between;
    gap: 10px;
}

/* Dark mode support */
body.dark-mode .share-content {
    background-color: #242526;
    color: #e4e6eb;
}

body.dark-mode .share-icon {
    color: white;
}

body.dark-mode .share-label {
    color: #e4e6eb;
}

body.dark-mode .share-post-preview {
    background-color: #3a3b3c;
}

body.dark-mode .share-preview-caption {
    color: #e4e6eb;
}

body.dark-mode .share-message textarea {
    background-color: #3a3b3c;
    color: #e4e6eb;
    border-color: #4e4f50;
}

@media (max-width: 480px) {
    .share-options-grid {
        grid-template-columns: repeat(3, 1fr);
        gap: 10px;
    }
    
    .share-icon {
        width: 40px;
        height: 40px;
        font-size: 16px;
    }
    
    .share-label {
        font-size: 11px;
    }
}

        
        /* Enhanced Comment Styles */
        .comment {
            display: flex;
            gap: 10px;
            margin-bottom: 10px;
            padding: 8px;
            border-radius: 8px;
            transition: background-color 0.2s ease;
        }

        .comment:hover {
            background-color: #f8f9fa;
        }

        .comment-avatar {
            width: 32px;
            height: 32px;
            border-radius: 50%;
            background-color: #ddd;
            flex-shrink: 0;
            overflow: hidden;
        }

        .comment-avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .comment-content {
            flex: 1;
            background-color: #f0f2f5;
            padding: 8px 12px;
            border-radius: 18px;
            position: relative;
        }

        .comment-author {
            font-weight: bold;
            font-size: 13px;
            margin-bottom: 3px;
            color: #050505;
        }

        .comment-text {
            font-size: 14px;
            color: #050505;
            line-height: 1.4;
        }

        .comment-actions {
            display: flex;
            gap: 15px;
            margin-top: 8px;
            font-size: 12px;
            color: #65676B;
        }

        .comment-action {
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 4px;
            transition: color 0.2s ease;
        }

        .comment-action:hover {
            color: #4267B2;
        }

        .comment-action.liked {
            color: #ff4444;
        }

        .comment-action.liked i {
            color: #ff4444;
        }

        .comment-time {
            color: #65676B;
            font-size: 11px;
        }

        .reply-btn {
            background: none;
            border: none;
            color: #65676B;
            cursor: pointer;
            padding: 4px 8px;
            border-radius: 4px;
            font-size: 12px;
            transition: background-color 0.2s ease;
        }

        .reply-btn:hover {
            background-color: #e4e6eb;
        }

        .comment-replies {
            margin-left: 1px;
            margin-top: 10px;
            padding-left: 15px;
            border-left: 2px solid #e4e6eb;
        }

        .reply {
            margin-bottom: 8px;
        }

        .reply .comment-content {
            background-color: #fff;
            border: 1px solid #e4e6eb;
        }

        .add-comment {
            display: flex;
            gap: 10px;
            margin-top: 15px;
            padding: 10px;
            background-color: #f0f2f5;
            border-radius: 20px;
            align-items: center;
        }

        .add-comment input {
            flex: 1;
            padding: 8px 12px;
            border: none;
            background-color: transparent;
            outline: none;
            font-size: 14px;
            color: #050505;
        }

        .add-comment input::placeholder {
            color: #65676B;
        }

        .comment-send-btn {
            background: none;
            border: none;
            color: #4267B2;
            cursor: pointer;
            padding: 8px;
            border-radius: 50%;
            transition: background-color 0.2s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            width: 36px;
            height: 36px;
        }

        .comment-send-btn:hover {
            background-color: #e4e6eb;
        }

        .comment-send-btn i {
            font-size: 16px;
        }

        .reply-input-container {
            margin-top: 10px;
            padding-left: 40px;
            display: none;
        }

        .reply-input-container.active {
            display: block;
        }

        .reply-input {
            display: flex;
            gap: 8px;
            align-items: center;
        }

        .reply-input input {
            flex: 1;
            padding: 8px 12px;
            border: 1px solid #e4e6eb;
            border-radius: 18px;
            outline: none;
            font-size: 14px;
        }

        .reply-send-btn {
            background: #4267B2;
            color: white;
            border: none;
            border-radius: 50%;
            width: 36px;
            height: 36px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: background-color 0.2s ease;
        }

        .reply-send-btn:hover {
            background-color: #365899;
        }

        .comment-edit-input {
            display: none;
            margin-top: 8px;
        }

        .comment-edit-input.active {
            display: block;
        }

        .comment-edit-input textarea {
            width: 100%;
            padding: 8px 12px;
            border: 1px solid #e4e6eb;
            border-radius: 8px;
            resize: vertical;
            min-height: 60px;
            font-size: 14px;
            outline: none;
        }

        .comment-edit-actions {
            display: flex;
            gap: 8px;
            margin-top: 8px;
            justify-content: flex-end;
        }

        .comment-edit-btn {
            padding: 6px 12px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 12px;
            font-weight: 600;
        }

        .comment-edit-save {
            background-color: #4267B2;
            color: white;
        }

        .comment-edit-cancel {
            background-color: #e4e6eb;
            color: #050505;
        }

        .comment-more-options {
            position: absolute;
            top: 8px;
            right: 8px;
            cursor: pointer;
            color: #65676B;
            padding: 4px;
            border-radius: 50%;
            transition: background-color 0.2s ease;
        }

        .comment-more-options:hover {
            background-color: #e4e6eb;
        }

        .comment-options-dropdown {
            position: absolute;
            top: 30px;
            right: 0;
            background-color: white;
            border: 1px solid #e4e6eb;
            border-radius: 8px;
            box-shadow: 0 2px 12px rgba(0, 0, 0, 0.1);
            z-index: 100;
            min-width: 120px;
            display: none;
        }

        .comment-options-dropdown.show {
            display: block;
        }

        .comment-option {
            padding: 10px 16px;
            cursor: pointer;
            font-size: 13px;
            color: #050505;
            transition: background-color 0.2s ease;
        }

        .comment-option:hover {
            background-color: #f0f2f5;
        }

        .comment-option.delete {
            color: #ff4444;
        }

        .comment-likes-count {
            display: flex;
            align-items: center;
            gap: 4px;
            color: #65676B;
            font-size: 11px;
            margin-top: 4px;
        }

        .comment-likes-count i {
            color: #ff4444;
            font-size: 10px;
        }

        /* Message like button styles */
        .message-actions {
            display: flex;
            gap: 15px;
            margin-top: 8px;
            padding-left: 5px;
        }

        .message-like-btn {
            background: none;
            border: none;
            color: #65676B;
            cursor: pointer;
            font-size: 12px;
            display: flex;
            align-items: center;
            gap: 4px;
            transition: color 0.2s ease;
        }

        .message-like-btn:hover {
            color: #4267B2;
        }

        .message-like-btn.liked {
            color: #ff4444;
        }

        .message-like-btn.liked i {
            color: #ff4444;
        }

        /* Dark mode support */
        body.dark-mode .comment:hover {
            background-color: #3a3b3c;
        }

        body.dark-mode .comment-content {
            background-color: #3a3b3c;
            color: #e4e6eb;
        }

        body.dark-mode .comment-author {
            color: #e4e6eb;
        }

        body.dark-mode .comment-text {
            color: #e4e6eb;
        }

        body.dark-mode .add-comment {
            background-color: #3a3b3c;
        }

        body.dark-mode .add-comment input {
            color: #e4e6eb;
        }

        body.dark-mode .reply .comment-content {
            background-color: #242526;
            border-color: #4e4f50;
        }

        body.dark-mode .comment-options-dropdown {
            background-color: #242526;
            border-color: #4e4f50;
        }

        body.dark-mode .comment-option:hover {
            background-color: #3a3b3c;
        }

        body.dark-mode .comment-edit-input textarea {
            background-color: #3a3b3c;
            border-color: #4e4f50;
            color: #e4e6eb;
        }

        body.dark-mode .comment-edit-cancel {
            background-color: #3a3b3c;
            color: #e4e6eb;
        }

        body.dark-mode .reply-input input {
            background-color: #3a3b3c;
            border-color: #4e4f50;
            color: #e4e6eb;
        }

        body.dark-mode .comment-more-options:hover {
            background-color: #3a3b3c;
        }

        
        
        
        
        
        
        
        
        
        
        
        

        /* NEW: Shop Profile Styles */
        .shop-profile-section {
            background: white;
            border-radius: 10px;
            padding: 15px;
            margin-bottom: 15px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            cursor: pointer;
            transition: transform 0.2s;
        }

        .shop-profile-section:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0,0,0,0.15);
        }

        .shop-profile-header {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 10px;
        }

        .shop-profile-avatar {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            overflow: hidden;
            border: 3px solid #4267B2;
        }

        .shop-profile-avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .shop-profile-info {
            flex: 1;
        }

        .shop-profile-name {
            font-size: 18px;
            font-weight: bold;
            color: #333;
            margin-bottom: 5px;
        }

        .shop-profile-type {
            font-size: 14px;
            color: #666;
            background: #f0f2f5;
            padding: 4px 10px;
            border-radius: 15px;
            display: inline-block;
        }

        .shop-profile-stats {
            display: flex;
            justify-content: space-around;
            border-top: 1px solid #eee;
            padding-top: 10px;
            margin-top: 10px;
        }

        .shop-profile-stat {
            text-align: center;
        }

        .shop-profile-stat-value {
            font-size: 16px;
            font-weight: bold;
            color: #4267B2;
        }

        .shop-profile-stat-label {
            font-size: 12px;
            color: #666;
        }

        /* Shop Profile Page */
        .shop-profile-page {
            display: none;
            padding: 20px;
            max-width: 500px;
            margin: 0 auto;
        }

        .shop-profile-page-header {
            display: flex;
            align-items: center;
            margin-bottom: 30px;
            position: relative;
        }

        .shop-profile-back-btn {
            background: none;
            border: none;
            font-size: 20px;
            color: #4267B2;
            cursor: pointer;
            position: absolute;
            left: 0;
        }

        .shop-profile-page-title {
            text-align: center;
            flex: 1;
            font-size: 20px;
            font-weight: bold;
        }

        .shop-profile-page-avatar {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            overflow: hidden;
            margin: 0 auto 20px;
            border: 5px solid #4267B2;
        }

        .shop-profile-page-avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .shop-profile-page-name {
            text-align: center;
            font-size: 24px;
            font-weight: bold;
            margin-bottom: 10px;
            color: #333;
        }

        .shop-profile-page-type {
            text-align: center;
            color: #666;
            font-size: 16px;
            margin-bottom: 20px;
        }

        .shop-profile-page-details {
            background: white;
            border-radius: 10px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .shop-profile-detail-item {
            margin-bottom: 15px;
            padding-bottom: 15px;
            border-bottom: 1px solid #eee;
        }

        .shop-profile-detail-item:last-child {
            margin-bottom: 0;
            padding-bottom: 0;
            border-bottom: none;
        }

        .shop-profile-detail-label {
            font-size: 14px;
            color: #666;
            margin-bottom: 5px;
        }

        .shop-profile-detail-value {
            font-size: 16px;
            color: #333;
        }

        .shop-profile-page-products {
            background: white;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .shop-products-title {
            font-size: 18px;
            font-weight: bold;
            margin-bottom: 15px;
            color: #333;
        }

        .shop-products-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 10px;
        }

        .shop-product-item {
            background: #f8f9fa;
            border-radius: 8px;
            overflow: hidden;
            cursor: pointer;
            transition: transform 0.2s;
        }

        .shop-product-item:hover {
            transform: translateY(-2px);
        }

        .shop-product-image {
            width: 100%;
            height: 100px;
            object-fit: cover;
        }

        .shop-product-info {
            padding: 10px;
        }

        .shop-product-name {
            font-size: 14px;
            font-weight: bold;
            margin-bottom: 5px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

        .shop-product-price {
            font-size: 14px;
            color: #4267B2;
            font-weight: bold;
        }

        
        
        
        
        
        /* Enhanced Product Menu Styles */
        .product-menu {
            position: absolute;
            top: 10px;
            right: 10px;
            z-index: 10;
        }

        .product-menu-btn {
            background-color: rgba(255, 255, 255, 0.9);
            border: none;
            border-radius: 50%;
            width: 30px;
            height: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            color: #333;
            font-size: 14px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            transition: background-color 0.2s;
            position: relative;
            z-index: 11;
        }

        .product-menu-btn:hover {
            background-color: white;
        }

        .product-menu-dropdown {
            position: absolute;
            top: 35px;
            right: 0;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.15);
            min-width: 120px;
            z-index: 100;
            display: none;
            border: 1px solid #e0e0e0;
        }

        .product-menu-dropdown.show {
            display: block;
        }

        .product-menu-option {
            padding: 10px 15px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 14px;
            transition: background-color 0.2s;
            border-bottom: 1px solid #f0f0f0;
        }

        .product-menu-option:last-child {
            border-bottom: none;
        }

        .product-menu-option:hover {
            background-color: #f0f2f5;
        }

        .product-menu-option.edit {
            color: #4267B2;
        }

        .product-menu-option.delete {
            color: #e74c3c;
        }

        .product-menu-option i {
            width: 16px;
        }

        /* For product item relative positioning */
        .product-item {
            position: relative;
        }

        .wishlist-item {
            position: relative;
        }

        /* Dark mode support */
        body.dark-mode .product-menu-btn {
            background-color: rgba(52, 53, 65, 0.9);
            color: #e4e6eb;
        }

        body.dark-mode .product-menu-dropdown {
            background-color: #242526;
            border: 1px solid #393a3b;
        }

        body.dark-mode .product-menu-option:hover {
            background-color: #3a3b3c;
        }

        .shop-product-item {
            position: relative;
        }
        
        /* Prevent clicking through product menu */
        .product-menu * {
            pointer-events: auto;
        }
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
    /* Ads Preview Page Styles */
    .ads-preview-page {
        display: none;
        padding: 15px;
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: white;
        z-index: 1000;
        overflow-y: auto;
    }

    .ads-preview-header {
        display: flex;
        align-items: center;
        margin-bottom: 20px;
        gap: 15px;
    }

    .ads-preview-title {
        font-size: 24px;
        font-weight: bold;
        color: #4267B2;
        flex: 1;
    }

    .create-ads-btn {
        background-color: #4267B2;
        color: white;
        border: none;
        padding: 10px 15px;
        border-radius: 5px;
        cursor: pointer;
        display: flex;
        align-items: center;
        gap: 5px;
    }

    .ads-preview-grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
        gap: 15px;
        margin-bottom: 20px;
    }

    .ads-item {
        background-color: white;
        border-radius: 10px;
        overflow: hidden;
        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        position: relative;
        transition: transform 0.2s;
    }

    .ads-item:hover {
        transform: translateY(-2px);
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
    }

    .ads-image {
        width: 100%;
        height: 150px;
        object-fit: cover;
    }

    .ads-info {
        padding: 15px;
    }

    .ads-title {
        font-weight: bold;
        margin-bottom: 5px;
        font-size: 16px;
        color: #333;
    }

    .ads-description {
        font-size: 14px;
        color: #666;
        margin-bottom: 10px;
        line-height: 1.4;
    }

    .ads-details {
        display: flex;
        justify-content: space-between;
        font-size: 12px;
        color: #888;
    }

    .ads-target {
        background-color: #f0f2f5;
        padding: 2px 8px;
        border-radius: 10px;
    }

    .ads-menu {
        position: absolute;
        top: 10px;
        right: 10px;
        z-index: 10;
    }

    .ads-menu-btn {
        background-color: rgba(255, 255, 255, 0.9);
        border: none;
        border-radius: 50%;
        width: 30px;
        height: 30px;
        display: flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
        color: #333;
        font-size: 14px;
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    }

    .ads-menu-dropdown {
        position: absolute;
        top: 35px;
        right: 0;
        background-color: white;
        border-radius: 8px;
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.15);
        min-width: 120px;
        z-index: 100;
        display: none;
        border: 1px solid #e0e0e0;
    }

    .ads-menu-dropdown.show {
        display: block;
    }

    .ads-menu-option {
        padding: 10px 15px;
        cursor: pointer;
        display: flex;
        align-items: center;
        gap: 8px;
        font-size: 14px;
        transition: background-color 0.2s;
        border-bottom: 1px solid #f0f0f0;
    }

    .ads-menu-option:last-child {
        border-bottom: none;
    }

    .ads-menu-option:hover {
        background-color: #f0f2f5;
    }

    .ads-menu-option.edit {
        color: #4267B2;
    }

    .ads-menu-option.delete {
        color: #e74c3c;
    }

    .ads-status {
        position: absolute;
        top: 10px;
        left: 10px;
        background-color: rgba(0, 0, 0, 0.7);
        color: white;
        padding: 4px 8px;
        border-radius: 4px;
        font-size: 10px;
        font-weight: bold;
    }

    .ads-status.active {
        background-color: #2ecc71;
    }

    .ads-status.pending {
        background-color: #f39c12;
    }

    .ads-status.expired {
        background-color: #e74c3c;
    }

    .ads-empty-state {
        text-align: center;
        padding: 40px 20px;
        color: #65676B;
    }

    .ads-empty-state i {
        font-size: 64px;
        margin-bottom: 20px;
        color: #ddd;
    }

    /* Edit Ads Page */
    .edit-ads-page {
        display: none;
        padding: 20px;
        max-width: 500px;
        margin: 0 auto;
        background-color: white;
        min-height: 100vh;
        overflow-y: auto;
    }

    .edit-ads-header {
        display: flex;
        align-items: center;
        margin-bottom: 30px;
        gap: 15px;
    }

    .edit-ads-title {
        font-size: 24px;
        font-weight: bold;
        color: #4267B2;
        flex: 1;
    }

    .edit-ads-form {
        background-color: white;
        border-radius: 10px;
        padding: 20px;
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    }

    /* Dark mode support */
    body.dark-mode .ads-preview-page,
    body.dark-mode .edit-ads-page,
    body.dark-mode .edit-ads-form,
    body.dark-mode .ads-item {
        background-color: #242526;
        color: #e4e6eb;
    }

    body.dark-mode .ads-menu-btn {
        background-color: rgba(52, 53, 65, 0.9);
        color: #e4e6eb;
    }

    body.dark-mode .ads-menu-dropdown {
        background-color: #242526;
        border: 1px solid #393a3b;
    }

    body.dark-mode .ads-menu-option:hover {
        background-color: #3a3b3c;
    }

    body.dark-mode .ads-title {
        color: #e4e6eb;
    }

    body.dark-mode .ads-description {
        color: #b0b3b8;
    }

        
        
        
        /* ... (rest of your existing CSS styles remain the same) ... */
    </style>
</head>
<body>
    <div class="container">
        
        
                        <!-- Header -->
        <div class="header">
            <div class="logo">O.C App</div>
            <div class="nav-icons">
                <i class="fas fa-search" onclick="toggleSearch()"></i>
                <i class="fas fa-bell" onclick="toggleNotifications()" id="notificationIcon">
                    <span class="notification-badge" id="notificationBadge" style="display: none;">0</span>
                </i>
                <i class="fas fa-user" onclick="showProfile()"></i>
            </div>
        </div>

        <!-- Notifications Panel -->
        <div class="notifications-panel" id="notificationsPanel">
            <div class="notifications-header">
                <div class="notifications-title">Notifications</div>
                <div class="notifications-actions">
                    <button class="notifications-action" onclick="markAllAsRead()">Mark all as read</button>
                    <button class="notifications-action" onclick="showNotificationSettings()">Settings</button>
                </div>
            </div>
            <div class="notifications-list" id="notificationsList">
                <!-- Notifications will be dynamically added here -->
            </div>
            <div class="notification-settings" id="notificationSettings" style="display: none;">
                <h3>Notification Settings</h3>
                <div class="notification-setting-item">
                    <span class="notification-setting-label">Push Notifications</span>
                    <label class="notification-toggle">
                        <input type="checkbox" id="pushNotificationsToggle" checked>
                        <span class="notification-slider"></span>
                    </label>
                </div>
                <div class="notification-setting-item">
                    <span class="notification-setting-label">Sound</span>
                    <label class="notification-toggle">
                        <input type="checkbox" id="soundToggle" checked>
                        <span class="notification-slider"></span>
                    </label>
                </div>
                <div class="notification-setting-item">
                    <span class="notification-setting-label">Email Notifications</span>
                    <label class="notification-toggle">
                        <input type="checkbox" id="emailNotificationsToggle">
                        <span class="notification-slider"></span>
                    </label>
                </div>
                <button class="btn btn-primary" onclick="saveNotificationSettings()" style="width: 100%; margin-top: 10px;">Save Settings</button>
            </div>
        </div>

        <!-- Push Notification -->
        <div class="push-notification" id="pushNotification">
            <div class="push-notification-header">
                <div class="push-notification-title" id="pushNotificationTitle">New Notification</div>
                <button class="push-notification-close" onclick="closePushNotification()">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            <div class="push-notification-body" id="pushNotificationBody">
                This is a sample push notification.
            </div>
            <div class="push-notification-footer">
                <button class="push-notification-btn secondary" onclick="closePushNotification()">Dismiss</button>
                <button class="push-notification-btn primary" id="pushNotificationAction">View</button>
            </div>
        </div>

        <!-- Search Bar -->
        <div class="search-bar" id="searchBar">
            <input type="text" class="search-input" placeholder="Search..." id="media-search" oninput="searchMedia()">
        </div>

        <!-- Ad Banner -->
        <div class="ad-banner-container">
            <div class="ad-banner" id="adBanner">
                <!-- Ad slides will be added dynamically -->
            </div>
            <div class="ad-control prev" onclick="prevAd()">❮</div>
            <div class="ad-control next" onclick="nextAd()">❯</div>
            <div class="ad-nav" id="adNav">
                <!-- Navigation dots will be added dynamically -->
            </div>
        </div>

        <!-- Create Post Section -->
        <div class="create-post">
            <div class="post-input">
                <div class="user-avatar">
                    <img src="https://ui-avatars.com/api/?name=User&background=random" alt="User" id="currentUserAvatar">
                </div>
                <input type="text" placeholder="What's on your mind?" onclick="openUploadModal()">
            </div>
            <div class="post-actions">
                <div class="post-action" onclick="prepareUpload('image')">
                    <i class="fas fa-image" style="color: #41B35D;"></i>
                    <span>Photo</span>
                </div>
                <div class="post-action" onclick="prepareUpload('video')">
                    <i class="fas fa-video" style="color: #E42645;"></i>
                    <span>Video</span>
                </div>
                <div class="post-action" onclick="showProductListing()">
                    <i class="fas fa-shopping-bag" style="color: #F3425F;"></i>
                    <span>Product</span>
                </div>
            </div>
        </div>

        <!-- Posts Container -->
        <div class="posts-container" id="posts-container">
            <!-- Posts will be dynamically added here -->
        </div>

        <!-- Products Section -->
        <div class="products-section" id="productsSection">
            <div class="section-header">
                
                
                
                
                
                
                <!--<div class="section-title">Featured Products</div>
                
                
                
                <div class="view-all" onclick="showProductListing()">View All</div>-->
                
                
                
                
                
                
                
                
                
            </div>
            <div class="products-grid" id="productsContainer">
                <!-- Products will be dynamically added here -->
            </div>
        </div>

        <!-- Earnings Section -->
        <div class="earnings-section" id="earningsSection">
            <div class="earnings-card">
                <div class="earnings-label">Total Earnings</div>
                <div class="earnings-total" id="totalEarnings">$0.00</div>
                <div class="earnings-label">Available for withdrawal</div>
            </div>
            
            <div class="earnings-stats">
                <div class="stat-item">
                    <div class="stat-value" id="availableEarnings">$0.00</div>
                    <div class="stat-label">Available</div>
                </div>
                <div class="stat-item">
                    <div class="stat-value">$0.00</div>
                    <div class="stat-label">Pending</div>
                </div>
                <div class="stat-item">
                    <div class="stat-value">$0.00</div>
                    <div class="stat-label">Total</div>
                </div>
            </div>
            
            <!-- Modified Withdrawal Section -->
            <div class="withdrawal-info">
                <div class="form-group">
                    <label for="withdrawalAmount">Amount to Withdraw</label>
                    <input type="number" id="withdrawalAmount" placeholder="Enter amount" min="1" max="1000">
                </div>
                <div class="withdrawal-phone">
                    <div class="withdrawal-phone-label">Withdrawal will be sent to:</div>
                    <div class="withdrawal-phone-value" id="withdrawalPhoneNumber">+255 000 000 000</div>
                </div>
            </div>
            
            <button class="withdraw-btn" onclick="showWithdrawalPasswordPage()">Withdraw Earnings</button>
        </div>

        <!-- Profile Section -->
        
        
       
        
        
        
        
        
        
        <div class="profile-section" id="profileSection">
            <div class="profile-header">
                <div class="profile-avatar">
                    <img src="https://ui-avatars.com/api/?name=User&background=random" alt="User" id="profileAvatar">
                    <div class="edit-overlay" onclick="showProfileSetup()">
                        <i class="fas fa-camera"></i> Edit
                    </div>
                </div>
                <div class="profile-info">
                    <h2 id="profileName">User</h2>
                    <p id="profileStatus">Member</p>
                </div>
            </div>
            
            <div class="profile-stats">
                <div class="stat-item">
                    <div class="stat-value" id="postCount">0</div>
                    <div class="stat-label">Posts</div>
                </div>
                <div class="stat-item">
                    <div class="stat-value">0</div>
                    <div class="stat-label">Followers</div>
                </div>
                <div class="stat-item">
                    <div class="stat-value">0</div>
                    <div class="stat-label">Following</div>
                </div>
            </div>
            
            <div class="profile-menu">
                <div class="menu-item" onclick="showProfileSetup()">
                    <i class="fas fa-user"></i>
                    <span>Edit Profile</span>
                    
                </div>
                    
                    
                    
                   
   
                    
                    
                    
                    
                    
                
                <div class="menu-item" onclick="showEarnings()">
                    <i class="fas fa-wallet"></i>
                    <span>Earnings</span>
                </div>
                <div class="menu-item" onclick="showWishlist()">
                    <i class="fas fa-heart"></i>
                    <span>My Wishlist</span>
                </div>
                
                
                
                
                
                
                
               
               
               
               
              
    
                
                
                
                
                
                <div class="menu-item" onclick="showSettings()">
                    <i class="fas fa-cog"></i>
                    <span>Settings</span>
                </div>
                
                
                
                
                
                
                 
    <div class="menu-item" onclick="showAdsPreview()">
        <i class="fas fa-bullhorn"></i>
        <span>My Advertisements</span>
    
                    </div>
                    
                
                
                    
               
                
                
                
                
                
                
                
                
                
                
                <div class="menu-item" onclick="showHelpSupport()">
                    <i class="fas fa-question-circle"></i>
                    <span>Help & Support</span>
                </div>
                <div class="menu-item" onclick="logout()">
                    <i class="fas fa-sign-out-alt"></i>
                    <span>Logout</span>
                </div>
            </div>
        </div>

        <!-- Friends Section -->
        <div class="friends-section" id="friendsSection">
            <div class="friends-tabs">
                <div class="friends-tab active" onclick="switchFriendsTab('find-friends')">Find Friends</div>
                <div class="friends-tab" onclick="switchFriendsTab('your-friends')">Your Friends</div>
            </div>
            
            <div class="friends-list" id="findFriendsList">
                <!-- Find Friends list will be dynamically added here -->
            </div>
            
            <div class="friends-list" id="yourFriendsList" style="display: none;">
                <!-- Your Friends list will be dynamically added here -->
            </div>
        </div>

        <!-- Messaging Container -->
        <div class="messaging-container" id="messagingContainer">
            <div class="messaging-header">
                <button class="messaging-back-btn" onclick="closeMessaging()">
                    <i class="fas fa-arrow-left"></i>
                </button>
                <div class="messaging-user-info">
                    <div class="messaging-avatar">
                        <img id="messagingAvatar" src="" alt="User">
                    </div>
                    <div class="messaging-user-name" id="messagingUserName"></div>
                </div>
            </div>
            <div class="messaging-body" id="messagingBody">
                <!-- Messages will be dynamically added here -->
            </div>
            <div class="messaging-footer">
                <input type="text" class="message-input" id="messageInput" placeholder="Type a message...">
                <button class="send-btn" onclick="sendMessage()">
                    <i class="fas fa-paper-plane"></i>
                </button>
            </div>
        </div>

        <!-- Message Notification -->
        <div class="message-notification" id="messageNotification">
            <div class="notification-avatar">
                <img id="notificationAvatar" src="" alt="User">
            </div>
            <div class="notification-content">
                <strong id="notificationName"></strong> sent you a message
            </div>
            <button class="notification-close" onclick="closeNotification()">
                <i class="fas fa-times"></i>
            </button>
        </div>

        <!-- Wishlist Page -->
        <div class="wishlist-page" id="wishlistPage">
            <div class="wishlist-header">
                <h2 class="wishlist-title">My Wishlist</h2>
                <button class="back-btn" onclick="goBackFromWishlist()">
                    <i class="fas fa-arrow-left"></i>
                </button>
            </div>
            
            <div class="wishlist-grid" id="wishlistContainer">
                <!-- Wishlist items will be dynamically added here -->
            </div>
            
            <div class="wishlist-empty" id="wishlistEmpty" style="display: none;">
                <i class="fas fa-heart"></i>
                <h3>Your wishlist is empty</h3>
                <p>Start adding products you love to your wishlist</p>
                <button class="btn btn-primary" onclick="showProducts()">Browse Products</button>
            </div>
        </div>

        <!-- Help & Support Section -->
        <div class="help-support-section" id="helpSupportSection">
            <div class="support-header">
                <h2>Help & Support</h2>
                <p>We're here to help you. Choose your preferred way to contact us.</p>
            </div>
            
            <div class="support-options">
                <div class="support-option" onclick="connectWithWhatsApp()">
                    <div class="support-icon whatsapp-icon">
                        <i class="fab fa-whatsapp"></i>
                    </div>
                    <div class="support-info">
                        <h3>Chat with us on WhatsApp</h3>
                        <p>Get quick responses to your questions via WhatsApp</p>
                    </div>
                    <i class="fas fa-chevron-right"></i>
                </div>
                
                <div class="support-option" onclick="callSupport()">
                    <div class="support-icon call-icon">
                        <i class="fas fa-phone-alt"></i>
                    </div>
                    <div class="support-info">
                        <h3>Call our support team</h3>
                        <p>Speak directly with our support team</p>
                    </div>
                    <i class="fas fa-chevron-right"></i>
                </div>
            </div>
            
            <div class="faq-section">
                <div class="faq-header">Frequently Asked Questions</div>
                <div class="faq-item">
                    <div class="faq-question" onclick="toggleFAQ(this)">
                        How do I create a post?
                        <i class="fas fa-chevron-down"></i>
                    </div>
                    <div class="faq-answer">
                        To create a post, click on the "What's on your mind?" input field at the top of the home screen. Then you can add text, photos, or videos to share with your followers.
                    </div>
                </div>
                <div class="faq-item">
                    <div class="faq-question" onclick="toggleFAQ(this)">
                        How can I sell products on the app?
                        <i class="fas fa-chevron-down"></i>
                    </div>
                    <div class="faq-answer">
                        To sell products, go to the Shop section and click on the "Sell" button. Fill out the product form with details about your item, upload images, and set a price.
                    </div>
                </div>
                <div class="faq-item">
                    <div class="faq-question" onclick="toggleFAQ(this)">
                        How do I earn money on the app?
                        <i class="fas fa-chevron-down"></i>
                    </div>
                    <div class="faq-answer">
                        You can earn money by creating engaging posts that get likes, comments, and shares. You can also sell products through the app. Your earnings will be displayed in the Earnings section.
                    </div>
                </div>
                <div class="faq-item">
                    <div class="faq-question" onclick="toggleFAQ(this)">
                        How do I withdraw my earnings?
                        <i class="fas fa-chevron-down"></i>
                    </div>
                    <div class="faq-answer">
                        To withdraw your earnings, go to the Earnings section and click on the "Withdraw Earnings" button. Follow the instructions to complete the withdrawal process.
                    </div>
                </div>
            </div>
        </div>

        <!-- Product Listing Page -->
        <div class="product-listing-page" id="productListingPage">
            <div class="product-listing-header">
                <button class="categories-btn" onclick="showCategories()">
                    <i class="fas fa-list"></i>
                    Categories
                </button>
                <button class="sell-btn" onclick="showProductForm()">
                    <i class="fas fa-plus"></i>
                    Sell
                </button>
            </div>

            <!-- Product Form -->
            <div class="product-form-container" id="productFormContainer">
                <h2 class="form-title">KEEP YOUR BUSINESS ON MARKET</h2>
                <form id="productForm">
                    <div class="form-group">
                        <input type="text" id="companyName" placeholder="Jina la Kampuni" required />
                    </div>
                    <div class="form-group">
                        <input type="text" id="productName" placeholder="Jina la Bidhaa" required />
                    </div>
                    <div class="form-group">
                        <input type="number" id="productPrice" placeholder="Bei (TZS)" required />
                    </div>
                    <div class="form-group">
                        <input type="number" id="transactionsNumber" placeholder="Namba ya muamala benki/simu" required/>
                    </div>
                    <div class="form-group">
                        <textarea id="productDesc" placeholder="Maelezo ya Bidhaa" required></textarea>
                    </div>
                    <div class="form-group">
                        <input type="text" id="contact" placeholder="Simu/Barua Pepe" required/>
                    </div>
                    <div class="form-group">
                        <select id="paymentMethod" required>
                            <option value="">Chagua Njia ya Malipo</option>
                            <option value="bank">Benki</option>
                            <option value="mobile">Malipo kwa Simu</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <input type="file" id="productImages" accept="image/*" multiple required style="display: none;" onchange="handleImageUpload(this)"/>
                        <div class="upload-btn" onclick="document.getElementById('productImages').click()">
                            <i class="fas fa-cloud-upload-alt"></i>
                            <p>Pakia Picha za Bidhaa</p>
                        </div>
                        <div class="image-preview" id="imagePreview"></div>
                    </div>

                    <button type="submit" class="submit-btn">Wasilisha Bidhaa</button>
                    <div class="loader" id="loader">Inatuma bidhaa...</div>
                    <div class="success" id="successMessage"></div>
                    <div class="error" id="errorMessage"></div>
                </form>
            </div>

            <!-- Products will be displayed here -->
            <div class="products-grid" id="userProductsContainer">
                <!-- User products will be displayed here -->
            </div>
        </div>

        <!-- Product Details Page -->
        <div class="product-details-page" id="productDetailsPage">
            <div class="product-details-header">
                <button class="back-btn" onclick="goBackToShop()">
                    <i class="fas fa-arrow-left"></i>
                </button>
                <h2>Product Details</h2>
                <div style="width: 40px;"></div> <!-- Spacer for alignment -->
            </div>

            <img class="product-details-image" id="productDetailsImage" src="" alt="Product Image">
            
            <div class="product-details-info">
                <div class="product-details-name" id="productDetailsName"></div>
                <div class="product-details-price" id="productDetailsPrice"></div>
                <div class="product-details-company" id="productDetailsCompany"></div>
                <div class="product-details-description" id="productDetailsDescription"></div>
                
                <div class="product-details-meta">
                    <div>Category: <span id="productDetailsCategory"></span></div>
                    <div>Available: <span id="productDetailsAvailability">In Stock</span></div>
                </div>
                
                <div class="product-details-actions">
                    <button class="action-btn buy-btn" onclick="buyProduct()">
                        <i class="fas fa-shopping-cart"></i>
                        Buy Now
                    </button>
                    <button class="action-btn contact-btn" onclick="contactSeller()">
                        <i class="fas fa-comment"></i>
                        Contact Seller
                    </button>
                    <button class="action-btn wishlist-btn" id="wishlistBtn" onclick="toggleWishlist()">
                        <i class="fas fa-heart"></i>
                        Wishlist
                    </button>
                </div>
            </div>
        </div>

        <!-- Categories Page -->
        <div class="categories-page" id="categoriesPage">
            <div class="categories-header">
                <h2>Categories</h2>
                <span onclick="hideCategories()" style="cursor: pointer;">×</span>
            </div>
            <div class="categories-list">
                <div class="category-item" onclick="filterProducts('all')">Bidhaa Zote</div>
                <div class="category-item" onclick="filterProducts('electronics')">Elektroniki</div>
                <div class="category-item" onclick="filterProducts('clothing')">Mavazi</div>
                <div class="category-item" onclick="filterProducts('food')">Chakula</div>
                <div class="category-item" onclick="filterProducts('furniture')">Samani</div>
                <div class="category-item" onclick="filterProducts('other')">Nyingine</div>
            </div>
        </div>

        <!-- Upload Modal -->
        <div class="modal" id="uploadModal">
            <div class="modal-content">
                <div class="modal-header">
                    <h3>Create Post</h3>
                    <span onclick="closeUploadModal()" style="cursor: pointer;">×</span>
                </div>
                <div class="modal-body">
                    <div class="preview-container" id="mediaPreviewContainer">
                        <!-- Media preview will be shown here -->
                    </div>
                    <textarea id="captionInput" placeholder="What's on your mind?"></textarea>
                    <input type="file" id="image-upload-input" accept="image/*" style="display: none;">
                    <input type="file" id="video-upload-input" accept="video/*" style="display: none;">
                </div>
                <div class="modal-footer">
                    <button class="btn btn-secondary" onclick="cancelUpload()">Cancel</button>
                    <button class="btn btn-primary" onclick="confirmUpload()">Post</button>
                </div>
            </div>
        </div>

        <!-- Profile Setup Modal -->
        <div class="modal profile-setup-modal" id="profileSetupModal">
            <div class="profile-setup-content">
                <div class="profile-setup-header">
                    <h3>Edit Profile</h3>
                    <span onclick="closeProfileSetup()" style="cursor: pointer;">×</span>
                </div>
                <div class="profile-setup-body">
                    <div class="profile-avatar-upload">
                        <div class="profile-avatar-large">
                            <img src="https://ui-avatars.com/api/?name=User&background=random" alt="Profile Picture" id="profileSetupAvatar">
                            <div class="edit-overlay" onclick="document.getElementById('profilePictureInput').click()">
                                <i class="fas fa-camera"></i> Change Photo
                            </div>
                        </div>
                        <input type="file" id="profilePictureInput" accept="image/*" style="display: none;" onchange="handleProfilePictureUpload(this)">
                    </div>
                    
                    <form id="profileSetupForm">
                        <div class="form-group">
                            <label for="fullName">Full Name</label>
                            <input type="text" id="fullName" placeholder="Enter your full name" required>
                        </div>
                        
                        <div class="form-row">
                            <div class="form-group">
                                <label for="dateOfBirth">Date of Birth</label>
                                <input type="date" id="dateOfBirth" required>
                            </div>
                            <div class="form-group">
                                <label for="country">Country</label>
                                <select id="country" required>
                                    <option value="">Select Country</option>
                                    <option value="Tanzania">Tanzania</option>
                                    <option value="Kenya">Kenya</option>
                                    <option value="Uganda">Uganda</option>
                                    <option value="Rwanda">Rwanda</option>
                                    <option value="Burundi">Burundi</option>
                                    <option value="Other">Other</option>
                                </select>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label for="phoneNumber">Phone Number</label>
                            <div class="phone-input-container">
                                <input type="tel" id="phoneNumber" placeholder="Enter phone number" required>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label for="workplace">Workplace (Optional)</label>
                            <input type="text" id="workplace" placeholder="Where do you work?">
                        </div>
                        
                        <div class="form-group">
                            <label for="education">Education (Optional)</label>
                            <input type="text" id="education" placeholder="School or academic institution">
                        </div>
                        
                        <div class="form-group">
                            <label for="bio">Bio (Optional)</label>
                            <textarea id="bio" placeholder="Tell us about yourself" rows="3"></textarea>
                        </div>
                        
                        <!-- Email section -->
                        <div class="form-group">
                            <label for="email">Email Address</label>
                            <div class="email-input-container">
                                <input type="email" id="email" placeholder="Enter your email address" required>
                                <button type="button" class="verify-btn" id="verifyEmailBtn" onclick="verifyEmail()">Verify</button>
                            </div>
                            <div class="email-options">
                                <div class="email-option google-option" onclick="showGoogleConnect()">
                                    <i class="fab fa-google"></i>
                                    <span>Use Google Account</span>
                                </div>
                                <div class="email-option create-option" onclick="createNewEmail()">
                                    <i class="fas fa-envelope"></i>
                                    <span>Create New Email</span>
                                </div>
                            </div>
                            <div class="verification-code" id="verificationCode">
                                <div class="code-inputs">
                                    <input type="text" class="code-input" maxlength="1" oninput="moveToNext(this, 1)">
                                    <input type="text" class="code-input" maxlength="1" oninput="moveToNext(this, 2)">
                                    <input type="text" class="code-input" maxlength="1" oninput="moveToNext(this, 3)">
                                    <input type="text" class="code-input" maxlength="1" oninput="moveToNext(this, 4)">
                                    <input type="text" class="code-input" maxlength="1" oninput="moveToNext(this, 5)">
                                    <input type="text" class="code-input" maxlength="1" oninput="moveToNext(this, 6)">
                                </div>
                                <div class="resend-code" onclick="resendVerificationCode()">Resend code</div>
                            </div>
                        </div>
                        
                        <!-- Next Button for Password Setup -->
                        <div class="form-group" style="text-align: center; margin-top: 20px;">
                            <button type="button" class="btn btn-primary" onclick="showPasswordSetup()" style="width: 100%;">
                                Next: Set Up Password
                            </button>
                        </div>
                    </form>
                </div>
                <div class="profile-setup-footer">
                    <button class="btn btn-secondary" onclick="closeProfileSetup()">Cancel</button>
                    <button class="btn btn-primary" onclick="saveProfile()">Save Profile</button>
                </div>
            </div>
        </div>
        
        <!-- Password Setup Page -->
        <div class="password-setup-page" id="passwordSetupPage">
            <div class="password-setup-header">
                <h2>Set Up Your Password</h2>
                <p>Create a secure password to protect your account</p>
            </div>
            
            <div class="password-form">
                <div class="form-group">
                    <label for="newPassword">New Password</label>
                    <input type="password" id="newPassword" placeholder="Enter your new password" oninput="checkPasswordStrength()" required>
                    <div class="password-strength">
                        <div class="password-strength-bar" id="passwordStrengthBar"></div>
                    </div>
                    <div class="password-strength-text" id="passwordStrengthText"></div>
                </div>
                
                <div class="form-group">
                    <label for="confirmPassword">Confirm Password</label>
                    <input type="password" id="confirmPassword" placeholder="Confirm your new password" oninput="checkPasswordMatch()" required>
                    <div id="passwordMatchMessage" style="font-size: 12px; margin-top: 5px;"></div>
                </div>
                
                <div class="password-requirements">
                    <p>Your password must contain:</p>
                    <ul>
                        <li id="reqLength">At least 8 characters</li>
                        <li id="reqUppercase">One uppercase letter</li>
                        <li id="reqLowercase">One lowercase letter</li>
                        <li id="reqNumber">One number</li>
                        <li id="reqSpecial">One special character</li>
                    </ul>
                </div>
                
                <div class="password-actions">
                    <button type="button" class="password-btn password-cancel" onclick="goBackToProfile()">Back</button>
                    <button type="button" class="password-btn password-submit" id="passwordSubmitBtn" onclick="savePassword()" disabled>Save Password</button>
                </div>
                
                <div class="forgot-password">
                    <button type="button" class="forgot-password-btn" onclick="showPasswordRecovery()">Forgot Password?</button>
                </div>
            </div>
        </div>
        
        <!-- Email Verification Page -->
        <div class="email-verification-page" id="emailVerificationPage">
            <div class="email-verification-header">
                <h2>Email Verification</h2>
                <p>Please verify your email address to complete your profile setup</p>
            </div>
            
            <div class="email-verification-form">
                <div class="form-group">
                    <label for="emailAddress">Email Address</label>
                    <input type="email" id="emailAddress" placeholder="Enter your email address" required>
                </div>
                
                <div class="success-message" id="emailSuccessMessage">
                    <i class="fas fa-check-circle"></i>
                    <h3>Email Verified Successfully!</h3>
                    <p>Your email has been verified and your profile is complete.</p>
                </div>
                
                <div class="email-actions">
                    <button type="button" class="email-btn email-cancel" onclick="goBackToPassword()">Back</button>
                    <button type="button" class="email-btn email-save" onclick="saveEmailAndComplete()">Save Profile</button>
                </div>
            </div>
        </div>
        
        <!-- Password Recovery Modal -->
        <div class="modal password-recovery-modal" id="passwordRecoveryModal">
            <div class="password-recovery-content">
                <div class="password-recovery-header">
                    <h3>Password Recovery</h3>
                    <span onclick="closePasswordRecovery()" style="cursor: pointer;">×</span>
                </div>
                <div class="password-recovery-body">
                    <div class="recovery-options">
                        <div class="recovery-option" onclick="showRecoveryForm('email')">
                            <i class="fas fa-envelope"></i>
                            <div>
                                <h4>Recover via Email</h4>
                                <p>Send a recovery link to your email</p>
                            </div>
                        </div>
                        
                        <div class="recovery-option" onclick="showRecoveryForm('phone')">
                            <i class="fas fa-mobile-alt"></i>
                            <div>
                                <h4>Recover via Phone</h4>
                                <p>Receive a verification code via SMS</p>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Email Recovery Form -->
                    <div class="recovery-form" id="emailRecoveryForm">
                        <div class="recovery-instructions">
                            Enter your email address and we'll send you a link to reset your password.
                        </div>
                        
                        <div class="form-group">
                            <label for="recoveryEmail">Email Address</label>
                            <input type="email" id="recoveryEmail" placeholder="Enter your email address">
                        </div>
                        
                        <div class="recovery-actions">
                            <button type="button" class="recovery-btn recovery-cancel" onclick="closePasswordRecovery()">Cancel</button>
                            <button type="button" class="recovery-btn recovery-submit" onclick="sendRecoveryEmail()">Send Recovery Link</button>
                        </div>
                    </div>
                    
                    <!-- Phone Recovery Form -->
                    <div class="recovery-form" id="phoneRecoveryForm">
                        <div class="recovery-instructions">
                            Enter your phone number and we'll send you a verification code to reset your password.
                        </div>
                        
                        <div class="form-group">
                            <label for="recoveryPhone">Phone Number</label>
                            <input type="tel" id="recoveryPhone" placeholder="Enter your phone number">
                        </div>
                        
                        <div class="recovery-actions">
                            <button type="button" class="recovery-btn recovery-cancel" onclick="closePasswordRecovery()">Cancel</button>
                            <button type="button" class="recovery-btn recovery-submit" onclick="sendRecoveryCode()">Send Verification Code</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Withdrawal Password Verification Page -->
        <div class="withdrawal-password-page" id="withdrawalPasswordPage">
            <div class="withdrawal-password-header">
                <h2>Confirm Withdrawal</h2>
                <p>Enter your password to confirm the withdrawal</p>
            </div>
            
            <div class="withdrawal-password-form">
                <div class="withdrawal-amount">
                    <div class="withdrawal-amount-label">Amount to Withdraw</div>
                    <div class="withdrawal-amount-value" id="withdrawalAmountValue">$0.00</div>
                </div>
                
                <div class="withdrawal-phone">
                    <div class="withdrawal-phone-label">Withdrawal will be sent to</div>
                    <div class="withdrawal-phone-value" id="withdrawalPhoneValue">+255 000 000 000</div>
                </div>
                
                <div class="form-group">
                    <label for="withdrawalPassword">Password</label>
                    <input type="password" id="withdrawalPassword" placeholder="Enter your password" required>
                </div>
                
                <div class="withdrawal-actions">
                    <button type="button" class="withdrawal-btn withdrawal-cancel" onclick="cancelWithdrawal()">Cancel</button>
                    <button type="button" class="withdrawal-btn withdrawal-confirm" onclick="confirmWithdrawal()">Confirm</button>
                </div>
            </div>
        </div>

        <!-- Google Connect Modal -->
        <div class="modal google-connect-modal" id="googleConnectModal">
            <div class="google-connect-content">
                <div class="google-connect-header">
                    <h3>Connect Google Account</h3>
                    <span onclick="closeGoogleConnect()" style="cursor: pointer;">×</span>
                </div>
                <div class="google-connect-body">
                    <div class="google-connect-icon">
                        <i class="fab fa-google"></i>
                    </div>
                    <div class="google-connect-title">Connect with Google</div>
                    <div class="google-connect-description">
                        Choose how you want to use your Google account with O.C App
                    </div>
                    <div class="google-connect-options">
                        <div class="google-connect-option" onclick="connectGoogleAccount('signin')">
                            <i class="fab fa-google"></i>
                            <span>Sign in with Google</span>
                        </div>
                        <div class="google-connect-option" onclick="connectGoogleAccount('import')">
                            <i class="fas fa-download"></i>
                            <span>Import Google contacts</span>
                        </div>
                        <div class="google-connect-option" onclick="connectGoogleAccount('sync')">
                            <i class="fas fa-sync-alt"></i>
                            <span>Sync Google Calendar</span>
                        </div>
                        <div class="google-connect-option" onclick="connectGoogleAccount('backup')">
                            <i class="fas fa-cloud-upload-alt"></i>
                            <span>Backup to Google Drive</span>
                        </div>
                    </div>
                </div>
                <div class="google-connect-footer">
                    <button class="btn btn-secondary" onclick="closeGoogleConnect()">Cancel</button>
                </div>
            </div>
        </div>                       
                        
        <!-- Payment Modal -->
        <div class="modal payment-modal" id="paymentModal">
            <div class="payment-content">
                <div class="payment-header">
                    <h3>Payment Required</h3>
                    <span onclick="closePaymentModal()" style="cursor: pointer;">×</span>
                </div>
                <div class="payment-body">
                    <div class="payment-amount">TZS 50</div>
                    <p style="text-align: center; margin-bottom: 20px;">To publish your post, please complete the payment of TZS 50</p>
                    
                    <div class="payment-instructions">
                        <h4>Payment Instructions:</h4>
                        <ol>
                            <li>Go to your mobile money app (M-Pesa, Tigo Pesa, Airtel Money, or Halotel Pesa)</li>
                            <li>Send TZS 50 to the following account:</li>
                        </ol>
                    </div>
                    
                    <div class="payment-account">
                        <div>Mobile Money Account:</div>
                        <div class="payment-account-number">+255776290901</div>
                        <div class="payment-reference">Reference: POST-<span id="paymentReference"></span></div>
                    </div>
                    
                    <div class="payment-confirmation">
                        <div class="form-group">
                            <label for="transactionId">Transaction ID:</label>
                            <input type="text" id="transactionId" placeholder="Enter your transaction ID">
                        </div>
                        
                        <div class="payment-status payment-processing" id="paymentProcessing">
                            Verifying your payment...
                        </div>
                        
                        <div class="payment-status payment-success" id="paymentSuccess">
                            Payment verified successfully! Your post will be published.
                        </div>
                        
                        <div class="payment-status payment-error" id="paymentError">
                            Payment verification failed. Please check your transaction ID and try again.
                        </div>
                    </div>
                </div>
                <div class="payment-footer">
                    <div class="payment-actions">
                        <button class="payment-btn confirm-payment-btn" onclick="verifyPayment()">Confirm Payment</button>
                        <button class="payment-btn cancel-payment-btn" onclick="closePaymentModal()">Cancel</button>
                    </div>
                </div>
            </div>
        </div>

        <!-- Share Modal -->
        <div class="modal share-modal" id="shareModal">
            <div class="share-content">
                <div class="share-header">
                    <h3>Share Post</h3>
                    <span onclick="closeShareModal()" style="cursor: pointer;">×</span>
                </div>
                <div class="share-body">
                    <div class="share-options-grid">
                        <div class="share-option" onclick="shareViaBluetooth()">
                            <div class="share-icon" style="background-color: #007AFF;">
                                <i class="fa-sharp fa-regular fa-bluetooth"></i>
                            </div>
                            <div class="share-label">Bluetooth</div>
                        </div>
                        <div class="share-option" onclick="shareViaFacebook()">
                            <div class="share-icon" style="background-color: #4267B2;">
                                <i class="fab fa-facebook-f"></i>
                            </div>
                            <div class="share-label">Facebook</div>
                        </div>
                        <div class="share-option" onclick="shareViaXender()">
                            <div class="share-icon" style="background-color: #FF6B35;">
                                <i class="fas fa-share-alt"></i>
                            </div>
                            <div class="share-label">Xender</div>
                        </div>
                        <div class="share-option" onclick="shareViaTikTok()">
                            <div class="share-icon" style="background-color: #000000;">
                                <i class="fab fa-tiktok"></i>
                            </div>
                            <div class="share-label">TikTok</div>
                        </div>
                        <div class="share-option" onclick="shareViaInstagram()">
                            <div class="share-icon" style="background: linear-gradient(45deg, #405DE6, #5851DB, #833AB4, #C13584, #E1306C, #FD1D1D);">
                                <i class="fab fa-instagram"></i>
                            </div>
                            <div class="share-label">Instagram</div>
                        </div>
                        <div class="share-option" onclick="shareViaYouTube()">
                            <div class="share-icon" style="background-color: #FF0000;">
                                <i class="fab fa-youtube"></i>
                            </div>
                            <div class="share-label">YouTube</div>
                        </div>
                        <div class="share-option" onclick="shareViaWhatsApp()">
                            <div class="share-icon" style="background-color: #25D366;">
                                <i class="fab fa-whatsapp"></i>
                            </div>
                            <div class="share-label">WhatsApp</div>
                        </div>
                        <div class="share-option" onclick="shareViaTelegram()">
                            <div class="share-icon" style="background-color: #0088cc;">
                                <i class="fab fa-telegram"></i>
                            </div>
                            <div class="share-label">Telegram</div>
                        </div>
                        <div class="share-option" onclick="shareViaTwitter()">
                            <div class="share-icon" style="background-color: #1DA1F2;">
                                <i class="fab fa-twitter"></i>
                            </div>
                            <div class="share-label">Twitter</div>
                        </div>
                        <div class="share-option" onclick="shareViaEmail()">
                            <div class="share-icon" style="background-color: #EA4335;">
                                <i class="fas fa-envelope"></i>
                            </div>
                            <div class="share-label">Email</div>
                        </div>
                        <div class="share-option" onclick="shareViaSMS()">
                            <div class="share-icon" style="background-color: #34B7F1;">
                                <i class="fas fa-comment-alt"></i>
                            </div>
                            <div class="share-label">SMS</div>
                        </div>
                        <div class="share-option" onclick="shareViaLink()">
                            <div class="share-icon" style="background-color: #6C757D;">
                                <i class="fas fa-link"></i>
                            </div>
                            <div class="share-label">Copy Link</div>
                        </div>
                    </div>
                    
                    <div class="share-post-preview" id="sharePostPreview">
                        <!-- Post preview will be dynamically added here -->
                    </div>
                    
                    <div class="share-message">
                        <textarea id="shareMessage" placeholder="Add a message (optional)" rows="2"></textarea>
                    </div>
                </div>
                <div class="share-footer">
                    <button class="btn btn-secondary" onclick="closeShareModal()">Cancel</button>
                    <button class="btn btn-primary" onclick="shareViaSystem()" id="systemShareBtn">
                        <i class="fas fa-share"></i> Share
                    </button>
                </div>
            </div>
        </div>
        
        <!-- Settings Section -->
        <div class="settings-section" id="settingsSection">
            <div class="settings-header">
                <button class="back-btn" onclick="goBackFromSettings()">
                    <i class="fas fa-arrow-left"></i>
                </button>
                <h2 class="settings-title">Settings</h2>
            </div>
            
            <div class="settings-menu">
                <div class="settings-category">Appearance</div>
                
                <div class="settings-item" onclick="toggleDarkMode()">
                    <div class="settings-item-info">
                        <div class="settings-item-title">Dark Mode</div>
                        <div class="settings-item-description">Switch between light and dark theme</div>
                    </div>
                    <div class="settings-item-action">
                        <label class="toggle-switch">
                            <input type="checkbox" id="darkModeToggle">
                            <span class="toggle-slider"></span>
                        </label>
                    </div>
                </div>
                
                <div class="settings-item" onclick="showLanguageSelection()">
                    <div class="settings-item-info">
                        <div class="settings-item-title">Language</div>
                        <div class="settings-item-description">Change app language</div>
                    </div>
                    <div class="settings-item-action">
                        <span id="currentLanguage">English</span>
                        <i class="fas fa-chevron-right chevron-right"></i>
                    </div>
                </div>
            </div>
            
            <div class="settings-menu">
                <div class="settings-category">Privacy</div>
                
                <div class="settings-item" onclick="showPrivacySettings('profile')">
                    <div class="settings-item-info">
                        <div class="settings-item-title">Profile Visibility</div>
                        <div class="settings-item-description">Control who can see your profile</div>
                    </div>
                    <div class="settings-item-action">
                        <i class="fas fa-chevron-right chevron-right"></i>
                    </div>
                </div>
                
                <div class="settings-item" onclick="showPrivacySettings('posts')">
                    <div class="settings-item-info">
                        <div class="settings-item-title">Post Visibility</div>
                        <div class="settings-item-description">Control who can see your posts</div>
                    </div>
                    <div class="settings-item-action">
                        <i class="fas fa-chevron-right chevron-right"></i>
                    </div>
                </div>
            </div>
            
            <div class="settings-menu">
                <div class="settings-category">Content</div>
                
                <div class="settings-item" onclick="showAdsCreation()">
                    <div class="settings-item-info">
                        <div class="settings-item-title">Create Ads</div>
                        <div class="settings-item-description">Create and manage your advertisements</div>
                    </div>
                    <div class="settings-item-action">
                        <i class="fas fa-chevron-right chevron-right"></i>
                    </div>
                </div>
                
                <div class="settings-item" onclick="clearCache()">
                    <div class="settings-item-info">
                        <div class="settings-item-title">Clear Cache</div>
                        <div class="settings-item-description">Free up storage space</div>
                    </div>
                    <div class="settings-item-action">
                        <i class="fas fa-chevron-right chevron-right"></i>
                    </div>
                </div>
            </div>
            
            <div class="settings-menu">
                <div class="settings-category">Account</div>
                
                <div class="settings-item" onclick="showProfileSetup()">
                    <div class="settings-item-info">
                        <div class="settings-item-title">Edit Profile</div>
                        <div class="settings-item-description">Update your personal information</div>
                    </div>
                    <div class="settings-item-action">
                        <i class="fas fa-chevron-right chevron-right"></i>
                    </div>
                </div>
                
                <div class="settings-item" onclick="changePassword()">
                    <div class="settings-item-info">
                        <div class="settings-item-title">Change Password</div>
                        <div class="settings-item-description">Update your account password</div>
                    </div>
                    <div class="settings-item-action">
                        <i class="fas fa-chevron-right chevron-right"></i>
                    </div>
                </div>
                
                <div class="settings-item" onclick="logout()">
                    <div class="settings-item-info">
                        <div class="settings-item-title">Logout</div>
                        <div class="settings-item-description">Sign out of your account</div>
                    </div>
                    <div class="settings-item-action">
                        <i class="fas fa-chevron-right chevron-right"></i>
                    </div>
                </div>
            </div>
        </div>

        <!-- Language Selection Modal -->
        <div class="modal language-modal" id="languageModal">
            <div class="language-content">
                <div class="language-header">
                    <h3>Select Language</h3>
                    <span onclick="closeLanguageSelection()" style="cursor: pointer;">×</span>
                </div>
                <div class="language-body">
                    <div class="language-option" onclick="selectLanguage('en')">
                        <span>English</span>
                        <span class="language-check" id="enCheck">✓</span>
                    </div>
                    <div class="language-option" onclick="selectLanguage('sw')">
                        <span>Kiswahili</span>
                        <span class="language-check" id="swCheck">✓</span>
                    </div>
                    <div class="language-option" onclick="selectLanguage('fr')">
                        <span>Français</span>
                        <span class="language-check" id="frCheck">✓</span>
                    </div>
                    <div class="language-option" onclick="selectLanguage('es')">
                        <span>Español</span>
                        <span class="language-check" id="esCheck">✓</span>
                    </div>
                </div>
                <div class="language-footer">
                    <button class="btn btn-secondary" onclick="closeLanguageSelection()">Cancel</button>
                </div>
            </div>
        </div>
        
        <!-- Privacy Settings Modal -->
        <div class="modal privacy-modal" id="privacyModal">
            <div class="privacy-content">
                <div class="privacy-header">
                    <h3 id="privacyModalTitle">Privacy Settings</h3>
                    <span onclick="closePrivacySettings()" style="cursor: pointer;">×</span>
                </div>
                <div class="privacy-body">
                    <div class="form-group">
                        <h4 id="privacyOptionTitle">Profile Visibility</h4>
                        <p id="privacyOptionDescription">Control who can see your profile information</p>
                        <select id="privacySetting" class="form-control">
                            <option value="public">Public</option>
                            <option value="friends">Friends Only</option>
                            <option value="private">Private</option>
                        </select>
                    </div>
                </div>
                <div class="privacy-footer">
                    <button class="btn btn-secondary" onclick="closePrivacySettings()">Cancel</button>
                    <button class="btn btn-primary" onclick="savePrivacySettings()">Save</button>
                </div>
            </div>
        </div>
        
        <!-- Ads Creation Modal -->
        <div class="modal ads-creation-modal" id="adsCreationModal">
            <div class="ads-creation-content">
                <div class="ads-creation-header">
                    <h3>Create Advertisement</h3>
                    <span onclick="closeAdsCreation()" style="cursor: pointer;">×</span>
                </div>
                <div class="ads-creation-body">
                    <div class="form-group">
                        <label for="adsTitle">Ad Title</label>
                        <input type="text" id="adsTitle" class="form-control" placeholder="Enter ad title">
                    </div>
                    
                    <div class="form-group">
                        <label for="adsDescription">Ad Description</label>
                        <textarea id="adsDescription" class="form-control" placeholder="Enter ad description" rows="3"></textarea>
                    </div>
                    
                    <div class="form-group">
                        <label for="adsTarget">Target Audience</label>
                        <select id="adsTarget" class="form-control">
                            <option value="all">All Users</option>
                            <option value="friends">Friends Only</option>
                            <option value="custom">Custom Audience</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="adsBudget">Budget (USD)</label>
                        <input type="number" id="adsBudget" class="form-control" placeholder="Enter budget">
                    </div>
                    
                    <div class="form-group">
                        <label for="adsDuration">Duration (Days)</label>
                        <input type="number" id="adsDuration" class="form-control" placeholder="Enter duration">
                    </div>
                    
                    <div class="form-group">
                        <label>Ad Image</label>
                        <div class="ads-preview" id="adsPreview">
                            <i class="fas fa-image" style="font-size: 48px; color: #ddd;"></i>
                        </div>
                        <input type="file" id="adsImageInput" accept="image/*" style="display: none;" onchange="handleAdsImageUpload(this)">
                        <button class="btn btn-secondary" onclick="document.getElementById('adsImageInput').click()" style="width: 100%;">
                            <i class="fas fa-upload"></i> Upload Image
                        </button>
                    </div>
                </div>
                <div class="ads-creation-footer">
                    <button class="btn btn-secondary" onclick="closeAdsCreation()">Cancel</button>
                    <button class="btn btn-primary" onclick="createAd()">Create Ad</button>
                    
                    
                    
                    
                    
        
        
        
        
        
    
                    
                    
                    
                    
                    
                    
                    
                    
                    
                </div>
            </div>
        </div>

        <!-- Ads Payment Page -->
        <div class="ads-payment-page" id="adsPaymentPage">
            <div class="ads-payment-header">
                <h2>Ads Payment</h2>
                <p>Complete payment to publish your advertisement</p>
            </div>
            
            <div class="ads-payment-form">
                <div class="ads-payment-summary">
                    <h3>Ad Summary</h3>
                    <div class="ads-payment-item">
                        <span class="ads-payment-label">Ad Title:</span>
                        <span class="ads-payment-value" id="adsPaymentTitle"></span>
                    </div>
                    <div class="ads-payment-item">
                        <span class="ads-payment-label">Duration:</span>
                        <span class="ads-payment-value" id="adsPaymentDuration"></span>
                    </div>
                    <div class="ads-payment-item">
                        <span class="ads-payment-label">Rate:</span>
                        <span class="ads-payment-value">TZS 1000/day</span>
                    </div>
                    <div class="ads-payment-total">
                        <span class="ads-payment-label">Total Amount:</span>
                        <span class="ads-payment-value" id="adsPaymentTotal"></span>
                    </div>
                </div>
                
                <div class="ads-payment-instructions">
                    <h4>Payment Instructions:</h4>
                    <ol>
                        <li>Go to your mobile money app (M-Pesa, Tigo Pesa, Airtel Money, or Halotel Pesa)</li>
                        <li>Send the total amount to the following account:</li>
                    </ol>
                </div>
                
                <div class="ads-payment-account">
                    <div>Mobile Money Account:</div>
                    <div class="ads-payment-account-number">+255776290901</div>
                    <div class="ads-payment-reference">Reference: ADS-<span id="adsPaymentReference"></span></div>
                </div>
                
                <div class="ads-payment-confirmation">
                    <div class="form-group">
                        <label for="adsTransactionId">Transaction ID:</label>
                        <input type="text" id="adsTransactionId" placeholder="Enter your transaction ID">
                    </div>
                    
                    <div class="ads-payment-status ads-payment-processing" id="adsPaymentProcessing">
                        Verifying your payment...
                    </div>
                    
                    <div class="ads-payment-status ads-payment-success" id="adsPaymentSuccess">
                        Payment verified successfully! Your ad will be published.
                    </div>
                    
                    <div class="ads-payment-status ads-payment-error" id="adsPaymentError">
                        Payment verification failed. Please check your transaction ID and try again.
                    </div>
                </div>
                
                <div class="ads-payment-actions">
                    <button class="ads-payment-btn confirm-ads-payment-btn" onclick="verifyAdsPayment()">Confirm Payment</button>
                    <button class="ads-payment-btn cancel-ads-payment-btn" onclick="goBackToAdsCreation()">Back to Ad Creation</button>
                </div>
            </div>
        </div>

        <!-- Bottom Navigation -->
        <div class="bottom-nav">
            <div class="nav-item active" onclick="showHome()">
                <i class="fas fa-home nav-icon"></i>
                <span class="nav-label">Home</span>
            </div>
            <div class="nav-item" onclick="showProducts()">
                <i class="fas fa-shopping-bag nav-icon"></i>
                <span class="nav-label">Shop</span>
            </div>
            <div class="nav-item" onclick="showFriends()">
                <i class="fas fa-user-friends nav-icon"></i>
                <span class="nav-label">Friends</span>
            </div>
            <div class="nav-item" onclick="showEarnings()">
                <i class="fas fa-wallet nav-icon"></i>
                <span class="nav-label">Earnings</span>
            </div>
            <div class="nav-item" onclick="showProfile()">
                <i class="fas fa-user nav-icon"></i>
                <span class="nav-label">Profile</span>
            </div>
        </div>
    </div>

        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        

        <!-- NEW: Shop Profile Page -->
        <div class="shop-profile-page" id="shopProfilePage">
            <div class="shop-profile-page-header">
                <button class="shop-profile-back-btn" onclick="goBackFromShopProfile()">
                    <i class="fas fa-arrow-left"></i>
                </button>
                <h2 class="shop-profile-page-title">Shop Profile</h2>
            </div>

            <div class="shop-profile-page-avatar">
                <img id="shopProfileAvatar" src="" alt="Shop Profile">
            </div>

            <div class="shop-profile-page-name" id="shopProfileName"></div>
            <div class="shop-profile-page-type" id="shopProfileType">Online Store</div>

            <div class="shop-profile-page-details">
                <div class="shop-profile-detail-item">
                    <div class="shop-profile-detail-label">Shop Owner</div>
                    <div class="shop-profile-detail-value" id="shopProfileOwner"></div>
                </div>
                <div class="shop-profile-detail-item">
                    <div class="shop-profile-detail-label">Contact</div>
                    <div class="shop-profile-detail-value" id="shopProfileContact"></div>
                </div>
                <div class="shop-profile-detail-item">
                    <div class="shop-profile-detail-label">Location</div>
                    <div class="shop-profile-detail-value" id="shopProfileLocation"></div>
                </div>
                <div class="shop-profile-detail-item">
                    <div class="shop-profile-detail-label">Rating</div>
                    <div class="shop-profile-detail-value">
                        <i class="fas fa-star" style="color: #FFD700;"></i>
                        <i class="fas fa-star" style="color: #FFD700;"></i>
                        <i class="fas fa-star" style="color: #FFD700;"></i>
                        <i class="fas fa-star" style="color: #FFD700;"></i>
                        <i class="fas fa-star-half-alt" style="color: #FFD700;"></i>
                        (4.5)
                    </div>
                </div>
            </div>

            <div class="shop-profile-page-products">
                <h3 class="shop-products-title">Shop Products</h3>
                <div class="shop-products-grid" id="shopProductsGrid">
                    <!-- Shop products will be dynamically added here -->
                </div>
            </div>
        </div>
    </div>

    
    
    
    
    
    
    
        
        
   
<!-- Ads Preview Page -->
<div class="ads-preview-page" id="adsPreviewPage">
    <div class="ads-preview-header">
        <button class="back-btn" onclick="goBackFromAdsPreview()">
            <i class="fas fa-arrow-left"></i>
        </button>
        <h2 class="ads-preview-title">My Advertisements</h2>
        <button class="create-ads-btn" onclick="showAdsCreation()">
            <i class="fas fa-plus"></i> Create Ad
        </button>
    </div>
    
    <div class="ads-preview-grid" id="adsPreviewContainer">
        <!-- Ads will be dynamically added here -->
    </div>
    
    <div class="ads-empty-state" id="adsEmptyState" style="display: none;">
        <i class="fas fa-bullhorn"></i>
        <h3>No advertisements yet</h3>
        <p>Create your first advertisement to reach more customers</p>
        <button class="btn btn-primary" onclick="showAdsCreation()" style="margin-top: 15px;">
            Create Your First Ad
        </button>
    </div>
</div>

<!-- Edit Ads Page -->
<div class="edit-ads-page" id="editAdsPage">
    <div class="edit-ads-header">
        <button class="back-btn" onclick="goBackToAdsPreview()">
            <i class="fas fa-arrow-left"></i>
        </button>
        <h2 class="edit-ads-title">Edit Advertisement</h2>
    </div>
    
    <div class="edit-ads-form">
        <div class="form-group">
            <label for="editAdsTitle">Ad Title</label>
            <input type="text" id="editAdsTitle" class="form-control" placeholder="Enter ad title">
        </div>
        
        <div class="form-group">
            <label for="editAdsDescription">Ad Description</label>
            <textarea id="editAdsDescription" class="form-control" placeholder="Enter ad description" rows="3"></textarea>
        </div>
        
        <div class="form-group">
            <label for="editAdsTarget">Target Audience</label>
            <select id="editAdsTarget" class="form-control">
                <option value="all">All Users</option>
                <option value="friends">Friends Only</option>
                <option value="custom">Custom Audience</option>
            </select>
        </div>
        
        <div class="form-group">
            <label for="editAdsBudget">Budget (USD)</label>
            <input type="number" id="editAdsBudget" class="form-control" placeholder="Enter budget">
        </div>
        
        <div class="form-group">
            <label for="editAdsDuration">Duration (Days)</label>
            <input type="number" id="editAdsDuration" class="form-control" placeholder="Enter duration">
        </div>
        
        <div class="form-group">
            <label>Ad Image</label>
            <div class="ads-preview" id="editAdsPreview">
                <!-- Current image will be shown here -->
            </div>
            <input type="file" id="editAdsImageInput" accept="image/*" style="display: none;" onchange="handleEditAdsImageUpload(this)">
            <button class="btn btn-secondary" onclick="document.getElementById('editAdsImageInput').click()" style="width: 100%; margin-top: 10px;">
                <i class="fas fa-upload"></i> Change Image
            </button>
        </div>
        
        <div class="form-group">
            <label for="editAdsStatus">Ad Status</label>
            <select id="editAdsStatus" class="form-control">
                <option value="active">Active</option>
                <option value="pending">Pending</option>
                <option value="paused">Paused</option>
                <option value="expired">Expired</option>
            </select>
        </div>
        
        <div class="ads-edit-actions" style="display: flex; gap: 10px; margin-top: 20px;">
            <button class="btn btn-secondary" onclick="goBackToAdsPreview()" style="flex: 1;">Cancel</button>
            <button class="btn btn-primary" onclick="saveEditedAd()" style="flex: 1;">Save Changes</button>
        </div>
        
        <div class="ads-delete-section" style="margin-top: 30px; padding-top: 20px; border-top: 1px solid #eee;">
            <h4 style="color: #e74c3c; margin-bottom: 15px;">Danger Zone</h4>
            <button class="btn btn-danger" onclick="deleteCurrentAd()" style="width: 100%;">
                <i class="fas fa-trash"></i> Delete Advertisement
            </button>
            <p style="font-size: 12px; color: #888; margin-top: 10px;">
                This action cannot be undone. Your ad will be permanently deleted.
            </p>
        </div>
    </div>
</div    
        
        
        
        
    </div>

    <script src="https://cdn.jsdelivr.net/npm/intl-tel-input@17.0.12/build/js/intlTelInput.min.js"></script>
    <script>
        
    // Data storage for the app - SINGLE DECLARATION
    let currentUser = {
        id: 1,
        name: "User",
        avatar: "https://ui-avatars.com/api/?name=User&background=random",
        earnings: {
            total: 0,
            available: 0
        },
        profile: {
            fullName: "User",
            dateOfBirth: "",
            country: "",
            phoneNumber: "",
            email: "",
            emailVerified: false,
            workplace: "",
            education: "",
            bio: "",
            status: "Member",
            password: ""
        },
        // Shop profile data
        shop: {
            hasShop: false,
            shopName: "",
            shopAvatar: "https://ui-avatars.com/api/?name=Shop&background=4267B2",
            shopType: "Online Store",
            contact: "",
            location: "",
            products: []
        }
    };

    let verificationCode = "";
    let verificationEmail = "";
    let resendTimer = null;
    let resendCountdown = 60;

    // Empty data arrays for user content
    let products = [];
    let advertisements = [];
    let userProducts = [];
    let posts = [];
    let wishlist = [];
    let allUsers = [];
    let conversations = {};
    let notifications = [];

    let currentAdIndex = 0;
    let adInterval;
    let pendingUpload = {
        type: null,
        file: null
    };
    let selectedPaymentMethod = null;
    let phoneInput;
    let currentProductDetails = null;
    let currentConversationUserId = null;
    let notificationSettings = {
        pushNotifications: true,
        sound: true,
        emailNotifications: false
    };
    let notificationInterval;
    let pushNotificationTimeout;
    
    // Payment-related variables
    let pendingPost = null;
    let paymentReference = '';

    // Ads-related variables
    let pendingAd = null;
    let adsPaymentReference = '';
    
    // Settings-related variables
    let currentLanguage = 'en';
    let darkModeEnabled = false;
    let profileVisibility = 'public';
    let postVisibility = 'public';
    
    // Share-related variables
    let currentSharePostId = null;
    let currentSharePost = null;

    // Time formatting function
    function formatTimeAgo(timestamp) {
        const now = new Date();
        const postTime = new Date(timestamp);
        const diffInSeconds = Math.floor((now - postTime) / 1000);
        
        if (diffInSeconds < 60) {
            return 'Just now';
        } else if (diffInSeconds < 3600) {
            const minutes = Math.floor(diffInSeconds / 60);
            return `${minutes} minute${minutes !== 1 ? 's' : ''} ago`;
        } else if (diffInSeconds < 86400) {
            const hours = Math.floor(diffInSeconds / 3600);
            return `${hours} hour${hours !== 1 ? 's' : ''} ago`;
        } else if (diffInSeconds < 604800) {
            const days = Math.floor(diffInSeconds / 86400);
            return `${days} day${days !== 1 ? 's' : ''} ago`;
        } else {
            return postTime.toLocaleDateString();
        }
    }



















       
            
            
            
    // Initialize the app
    function initApp() {
        // Load data from localStorage if available
        loadDataFromStorage();
        
        // Initialize settings
        initSettings();
        
        // Initialize all UI components
        renderAdBanner();
        renderPosts();
        renderProducts();
        renderUserProducts();
        updateEarnings();
        updateProfileDisplay();
        startAdSlider();
        renderFriendsLists();
        renderNotifications();
        updateNotificationBadge();


            
            
        
        // Render shop profile
        renderShopProfile();
        
        // Initialize phone input
        const phoneInputElement = document.getElementById('phoneNumber');
        if (phoneInputElement) {
            phoneInput = window.intlTelInput(phoneInputElement, {
                initialCountry: "tz",
                separateDialCode: true,
                utilsScript: "https://cdn.jsdelivr.net/npm/intl-tel-input@17.0.12/build/js/utils.js",
            });
        }
        
        // Add form submission handler
        const productForm = document.getElementById('productForm');
        if (productForm) {
            productForm.addEventListener('submit', function(e) {
                e.preventDefault();
                submitProductForm();
            });
        }
        
        // Add enter key handler for message input
        const messageInput = document.getElementById('messageInput');
        if (messageInput) {
            messageInput.addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    sendMessage();
                }
            });
        }
        
        // Close dropdowns when clicking outside
        document.addEventListener('click', function(event) {
            if (!event.target.matches('.post-menu, .post-menu *')) {
                document.querySelectorAll('.post-menu-dropdown').forEach(dropdown => {
                    dropdown.style.display = 'none';
                });
            }
            
            // Close comment options dropdowns
            if (!event.target.matches('.comment-more-options, .comment-more-options *')) {
                document.querySelectorAll('.comment-options-dropdown').forEach(dropdown => {
                    dropdown.classList.remove('show');
                });
            }
            
            // Close categories page when clicking outside
            const categoriesPage = document.getElementById('categoriesPage');
            if (categoriesPage && categoriesPage.style.display === 'block' && !event.target.closest('.categories-page') && 
                !event.target.matches('.categories-btn, .categories-btn *')) {
                categoriesPage.style.display = 'none';
            }
            
            // Close notifications panel when clicking outside
            const notificationsPanel = document.getElementById('notificationsPanel');
            if (notificationsPanel && notificationsPanel.style.display === 'flex' && !event.target.closest('.notifications-panel') && 
                !event.target.matches('.fa-bell, .fa-bell *')) {
                notificationsPanel.style.display = 'none';
            }
        });

        // Start notification simulation
        startNotificationSimulation();

            
                    // Initialize password recovery phone input
        initPasswordRecovery();
        
        // Add enter key handler for comment inputs
        document.addEventListener('keypress', function(e) {
            if (e.key === 'Enter' && e.target.type === 'text') {
                // Check if it's a comment input
                if (e.target.id && e.target.id.startsWith('comment-input-')) {
                    const postId = parseInt(e.target.id.split('-')[2]);
                    postComment(postId);
                }
                // Check if it's a reply input
                else if (e.target.id && e.target.id.startsWith('reply-text-')) {
                    const commentId = parseInt(e.target.id.split('-')[2]);
                    postReply(commentId);
                }
            }
        });
    }

    // Data persistence functions
    function saveDataToStorage() {
        const appData = {
            currentUser,
            products,
            advertisements,
            userProducts,
            posts,
            wishlist,
            allUsers,
            conversations,
            notifications,
            notificationSettings
        };
        
        localStorage.setItem('ocAppData', JSON.stringify(appData));
    }

    function loadDataFromStorage() {
        const savedData = localStorage.getItem('ocAppData');
        
        if (savedData) {
            const appData = JSON.parse(savedData);
            
            currentUser = appData.currentUser || currentUser;
            products = appData.products || products;
            advertisements = appData.advertisements || advertisements;
            userProducts = appData.userProducts || userProducts;
            posts = appData.posts || posts;
            wishlist = appData.wishlist || wishlist;
            allUsers = appData.allUsers || allUsers;
            conversations = appData.conversations || conversations;
            notifications = appData.notifications || notifications;
            notificationSettings = appData.notificationSettings || notificationSettings;
            
            // Initialize missing properties for backwards compatibility
            if (posts) {
                posts.forEach(post => {
                    if (!post.comments) post.comments = [];
                    post.comments.forEach(comment => {
                        if (!comment.likes) comment.likes = [];
                        if (!comment.parentId) comment.parentId = null;
                        if (!comment.replies) comment.replies = [];
                    });
                });
            }
            
            if (conversations) {
                Object.keys(conversations).forEach(userId => {
                    conversations[userId].forEach(message => {
                        if (!message.likes) message.likes = [];
                    });
                });
            }
            
            
            
            
            
            
            
            
            
            
            
            
            // Add click outside listener for product menus
            document.addEventListener('click', function(event) {
                // Close all product menus when clicking outside
                if (!event.target.closest('.product-menu')) {
                    document.querySelectorAll('.product-menu-dropdown').forEach(dropdown => {
                        dropdown.classList.remove('show');
                    });
                }
            });
            
            
            
                        // Initialize shop data if not exists
            if (!currentUser.shop) {
                currentUser.shop = {
                    hasShop: userProducts.length > 0,
                    shopName: userProducts.length > 0 ? userProducts[0].companyName : "",
                    shopAvatar: currentUser.avatar,
                    shopType: "Online Store",
                    contact: userProducts.length > 0 ? userProducts[0].contactInfo : currentUser.profile.phoneNumber,
                    location: currentUser.profile.country,
                    products: userProducts.filter(product => product.userId === currentUser.id)
                };
            }
        }
        
        // Update post count in profile
        updatePostCount();
    }

    // Initialize settings
    function initSettings() {
        // Load settings from localStorage
        loadSettingsFromStorage();
        
        // Apply saved settings
        applySettings();
    }

    // Load settings from localStorage
    function loadSettingsFromStorage() {
        const savedSettings = localStorage.getItem('ocAppSettings');
        
        if (savedSettings) {
            const settings = JSON.parse(savedSettings);
            
            currentLanguage = settings.currentLanguage || 'en';
            darkModeEnabled = settings.darkModeEnabled || false;
            profileVisibility = settings.profileVisibility || 'public';
            postVisibility = settings.postVisibility || 'public';
        }
    }

    // Save settings to localStorage
    function saveSettingsToStorage() {
        const settings = {
            currentLanguage,
            darkModeEnabled,
            profileVisibility,
            postVisibility
        };
        
        localStorage.setItem('ocAppSettings', JSON.stringify(settings));
    }

    // Apply settings to the app
    function applySettings() {
        // Apply dark mode
        if (darkModeEnabled) {
            document.body.classList.add('dark-mode');
            const darkModeToggle = document.getElementById('darkModeToggle');
            if (darkModeToggle) {
                darkModeToggle.checked = true;
            }
        } else {
            document.body.classList.remove('dark-mode');
        }
        
        // Apply language
        const currentLanguageElement = document.getElementById('currentLanguage');
        if (currentLanguageElement) {
            currentLanguageElement.textContent = getLanguageName(currentLanguage);
        }
        
        // Update language checkmarks
        updateLanguageCheckmarks();
    }

    // Get language name
    function getLanguageName(code) {
        switch(code) {
            case 'en': return 'English';
            case 'sw': return 'Kiswahili';
            case 'fr': return 'Français';
            case 'es': return 'Español';
            default: return 'English';
        }
    }

    // Update language checkmarks
    function updateLanguageCheckmarks() {
        // Hide all checkmarks
        document.querySelectorAll('.language-check').forEach(check => {
            check.style.display = 'none';
        });
        
        // Show checkmark for current language
        const currentCheck = document.getElementById(`${currentLanguage}Check`);
        if (currentCheck) {
            currentCheck.style.display = 'flex';
        }
    }
            
            
            
           


    // Toast notification function
    function showToast(message, type = 'success') {
        // Create toast element
        const toast = document.createElement('div');
        toast.style.cssText = `
            position: fixed;
            top: 20px;
            right: 20px;
            background-color: ${type === 'success' ? '#2ecc71' : '#e74c3c'};
            color: white;
            padding: 15px 20px;
            border-radius: 5px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
            z-index: 10000;
            max-width: 300px;
            word-wrap: break-word;
        `;
        toast.textContent = message;
        
        // Add to page
        document.body.appendChild(toast);
        
        // Remove after 3 seconds
        setTimeout(() => {
            if (toast.parentNode) {
                document.body.removeChild(toast);
            }
        }, 3000);
    }

    // Ad Banner Functions
    function renderAdBanner() {
        const adBanner = document.getElementById('adBanner');
        const adNav = document.getElementById('adNav');
        
        if (!adBanner || !adNav) return;
        
        adBanner.innerHTML = '';
        adNav.innerHTML = '';
        
        // Always show welcome ad as first slide
        const welcomeSlide = document.createElement('div');
        welcomeSlide.className = 'ad-slide';
        welcomeSlide.style.backgroundColor = '#4267B2';
        welcomeSlide.innerHTML = `
            <div class="ad-slide-content">
                <div class="ad-product-name">Welcome to O.C App</div>
                <div class="ad-product-price">Start selling today!</div>
                <div class="ad-product-company">Your marketplace</div>
            </div>
        `;
        adBanner.appendChild(welcomeSlide);
        
        const welcomeDot = document.createElement('div');
        welcomeDot.className = 'ad-dot active';
        adNav.appendChild(welcomeDot);
        
        // Show user advertisements
        if (advertisements.length > 0) {
            advertisements.forEach((ad, index) => {
                const adSlide = document.createElement('div');
                adSlide.className = 'ad-slide';
                adSlide.style.backgroundImage = `url(${ad.image})`;
                adSlide.setAttribute('data-ad-id', ad.id);
                adSlide.onclick = () => handleAdClick(ad);
                adSlide.innerHTML = `
                    <div class="ad-slide-content">
                        <div class="ad-product-name">${ad.title}</div>
                        <div class="ad-product-price">${ad.description.substring(0, 50)}...</div>
                        <div class="ad-product-company">Advertisement</div>
                    </div>
                `;
                adBanner.appendChild(adSlide);
                
                const dot = document.createElement('div');
                dot.className = `ad-dot ${index === 0 ? '' : ''}`;
                dot.onclick = () => showAd(index + 1);
                adNav.appendChild(dot);
            });
        }
    }

    function startAdSlider() {
        if (adInterval) {
            clearInterval(adInterval);
        }
        
        adInterval = setInterval(() => {
            nextAd();
        }, 5000);
    }

    function showAd(index) {
        const totalSlides = 1 + advertisements.length;
        if (totalSlides === 0) return;
        
        currentAdIndex = index;
        const adBanner = document.getElementById('adBanner');
        const dots = document.querySelectorAll('.ad-dot');
        
        if (!adBanner) return;
        
        adBanner.style.transform = `translateX(-${index * 100}%)`;
        
        dots.forEach((dot, i) => {
            dot.classList.toggle('active', i === index);
        });
    }

    function nextAd() {
        const totalSlides = 1 + advertisements.length;
        if (totalSlides === 0) return;
        
        currentAdIndex = (currentAdIndex + 1) % totalSlides;
        showAd(currentAdIndex);
    }

    function prevAd() {
        const totalSlides = 1 + advertisements.length;
        if (totalSlides === 0) return;
        
        currentAdIndex = (currentAdIndex - 1 + totalSlides) % totalSlides;
        showAd(currentAdIndex);
    }

    // Handle ad click
    function handleAdClick(ad) {
        alert(`Advertisement: ${ad.title}\n\n${ad.description}`);
    }

    // Post Functions
    function renderPosts() {
        const postsContainer = document.getElementById('posts-container');
        if (!postsContainer) return;
        
        postsContainer.innerHTML = '';
        
        if (posts.length === 0) {
            postsContainer.innerHTML = `
                <div style="text-align: center; padding: 40px 20px; color: #65676B;">
                    <i class="fas fa-newspaper" style="font-size: 64px; margin-bottom: 20px; color: #ddd;"></i>
                    <h3>No posts yet</h3>
                    <p>Be the first to create a post!</p>
                </div>
            `;
            return;
        }
        
        // Sort posts by timestamp (newest first)
        const sortedPosts = [...posts].sort((a, b) => new Date(b.timestamp) - new Date(a.timestamp));
        
        sortedPosts.forEach(post => {
            const postElement = document.createElement('div');
            postElement.className = 'post';
            postElement.innerHTML = `
                <div class="post-header">
                    <div class="user-avatar">
                        <img src="${post.user.avatar}" alt="${post.user.name}">
                    </div>
                    <div class="post-user-info">
                        <div class="name">${post.user.name}</div>
                        <div class="time">${formatTimeAgo(post.timestamp)}</div>
                    </div>
                    <div class="post-menu" onclick="togglePostMenu(this)">
                        <i class="fas fa-ellipsis-h"></i>
                        <div class="post-menu-dropdown">
                            <div onclick="deletePost(${post.id})">Delete Post</div>
                            <div onclick="editPost(${post.id})">Edit Post</div>
                            <div onclick="reportPost(${post.id})">Report Post</div>
                        </div>
                    </div>
                </div>
                <div class="post-content">
                    <div class="post-caption">${post.caption}</div>
                    ${post.caption.length > 120 ? '<div class="read-more" onclick="toggleReadMore(this)">See More</div>' : ''}
                    <div class="post-media">
                        ${post.media.type === 'image' ? 
                            `<img src="${post.media.url}" alt="Post image">` : 
                            `<video controls><source src="${post.media.url}" type="video/mp4"></video>`}
                    </div>
                </div>
                <div class="post-stats">
                    <div class="likes-count">${post.likes} likes</div>
                    <div class="comments-count">${post.comments.length} comments</div>
                    <div class="earnings">$${post.earnings.toFixed(2)} earned</div>
                </div>
                <div class="post-actions-row">
                    <div class="post-action-btn ${post.liked ? 'liked' : ''}" onclick="toggleLike(${post.id})">
                        <i class="fas fa-thumbs-up"></i>
                        <span>Like</span>
                    </div>
                    <div class="post-action-btn" onclick="toggleComment(${post.id})">
                        <i class="fas fa-comment"></i>
                        <span>Comment</span>
                    </div>
                    <div class="post-action-btn" onclick="sharePost(${post.id})">
                        <i class="fas fa-share"></i>
                        <span>Share</span>
                    </div>
                </div>
                <div class="comments-section" id="${post.id}-comments">
                    <div class="comments-list" id="comments-list-${post.id}">
                        ${renderComments(post.comments)}
                    </div>
                    <div class="add-comment">
                        <div class="user-avatar">
                            <img src="${currentUser.avatar}" alt="${currentUser.name}">
                        </div>
                        <input type="text" id="comment-input-${post.id}" placeholder="Write a comment...">
                        <button class="comment-send-btn" onclick="postComment(${post.id})">
                            <i class="fas fa-paper-plane"></i>
                        </button>
                    </div>
                </div>
            `;
            postsContainer.appendChild(postElement);
        });
    }



           
           
           
           // Add these variables at the beginning of your JavaScript
let currentEditingAdId = null;
let currentEditingAd = null;

// Add these functions to your JavaScript

// Function to show ads preview page
function showAdsPreview() {
    hideAllSections();
    document.getElementById('adsPreviewPage').style.display = 'block';
    renderAdsPreview();
}

// Function to render ads preview
function renderAdsPreview() {
    const adsContainer = document.getElementById('adsPreviewContainer');
    const emptyState = document.getElementById('adsEmptyState');
    
    if (!adsContainer || !emptyState) return;
    
    adsContainer.innerHTML = '';
    
    // Filter ads by current user
    const userAds = advertisements.filter(ad => {
        // In a real app, you'd check ad.userId === currentUser.id
        // For demo, we'll show all ads
        return true;
    });
    
    if (userAds.length === 0) {
        emptyState.style.display = 'block';
        adsContainer.style.display = 'none';
        return;
    }
    
    emptyState.style.display = 'none';
    adsContainer.style.display = 'grid';
    
    // Sort ads by timestamp (newest first)
    const sortedAds = [...userAds].sort((a, b) => new Date(b.timestamp) - new Date(a.timestamp));
    
    sortedAds.forEach(ad => {
        const adItem = document.createElement('div');
        adItem.className = 'ads-item';
        adItem.innerHTML = `
            <div class="ads-menu">
                <button class="ads-menu-btn" onclick="toggleAdsMenu(this, ${ad.id}, event)">
                    <i class="fas fa-ellipsis-v"></i>
                </button>
                <div class="ads-menu-dropdown" id="ads-menu-${ad.id}">
                    <div class="ads-menu-option edit" onclick="editAd(${ad.id}, event)">
                        <i class="fas fa-edit"></i>
                        <span>Edit</span>
                    </div>
                    <div class="ads-menu-option delete" onclick="deleteAd(${ad.id}, event)">
                        <i class="fas fa-trash"></i>
                        <span>Delete</span>
                    </div>
                </div>
            </div>
            
            <div class="ads-status ${ad.status || 'active'}">
                ${(ad.status || 'active').toUpperCase()}
            </div>
            
            <img src="${ad.image}" alt="${ad.title}" class="ads-image">
            
            <div class="ads-info">
                <div class="ads-title">${ad.title}</div>
                <div class="ads-description">${ad.description.substring(0, 100)}${ad.description.length > 100 ? '...' : ''}</div>
                <div class="ads-details">
                    <span>${formatTimeAgo(ad.timestamp)}</span>
                    <span class="ads-target">${ad.target}</span>
                </div>
                <div class="ads-details" style="margin-top: 5px;">
                    <span>Budget: $${ad.budget}</span>
                    <span>Duration: ${ad.duration} days</span>
                </div>
            </div>
        `;
        
        // Add click event to view ad details (optional)
        adItem.onclick = (e) => {
            if (!e.target.closest('.ads-menu')) {
                viewAdDetails(ad);
            }
        };
        
        adsContainer.appendChild(adItem);
    });
}

// Function to toggle ads menu
function toggleAdsMenu(button, adId, event) {
    if (event) event.stopPropagation();
    
    const dropdown = document.getElementById(`ads-menu-${adId}`);
    if (!dropdown) return;
    
    // Close all other dropdowns
    document.querySelectorAll('.ads-menu-dropdown').forEach(menu => {
        if (menu !== dropdown) {
            menu.classList.remove('show');
        }
    });
    
    // Toggle current dropdown
    dropdown.classList.toggle('show');
}

// Function to view ad details
function viewAdDetails(ad) {
    alert(`Ad Details:\n\nTitle: ${ad.title}\nDescription: ${ad.description}\nTarget: ${ad.target}\nBudget: $${ad.budget}\nDuration: ${ad.duration} days\nStatus: ${ad.status || 'active'}`);
}

// Function to edit ad
function editAd(adId, event) {
    if (event) event.stopPropagation();
    
    const ad = advertisements.find(a => a.id === adId);
    if (!ad) return;
    
    currentEditingAdId = adId;
    currentEditingAd = ad;
    
    // Populate edit form with ad data
    document.getElementById('editAdsTitle').value = ad.title;
    document.getElementById('editAdsDescription').value = ad.description;
    document.getElementById('editAdsTarget').value = ad.target || 'all';
    document.getElementById('editAdsBudget').value = ad.budget || '';
    document.getElementById('editAdsDuration').value = ad.duration || '';
    document.getElementById('editAdsStatus').value = ad.status || 'active';
    
    // Set current image preview
    const preview = document.getElementById('editAdsPreview');
    if (preview) {
        preview.innerHTML = `<img src="${ad.image}" alt="Ad Preview" style="max-width: 100%; max-height: 200px; border-radius: 5px;">`;
    }
    
    // Hide ads preview and show edit page
    document.getElementById('adsPreviewPage').style.display = 'none';
    document.getElementById('editAdsPage').style.display = 'block';
    
    // Close any open menus
    document.querySelectorAll('.ads-menu-dropdown').forEach(menu => {
        menu.classList.remove('show');
    });
}

// Function to handle edit ads image upload
function handleEditAdsImageUpload(input) {
    if (input.files && input.files[0]) {
        const reader = new FileReader();
        
        reader.onload = function(e) {
            const preview = document.getElementById('editAdsPreview');
            preview.innerHTML = `<img src="${e.target.result}" alt="Ad Preview" style="max-width: 100%; max-height: 200px; border-radius: 5px;">`;
        };
        
        reader.readAsDataURL(input.files[0]);
    }
}

// Function to save edited ad
function saveEditedAd() {
    if (!currentEditingAdId) return;
    
    const title = document.getElementById('editAdsTitle').value;
    const description = document.getElementById('editAdsDescription').value;
    const target = document.getElementById('editAdsTarget').value;
    const budget = document.getElementById('editAdsBudget').value;
    const duration = document.getElementById('editAdsDuration').value;
    const status = document.getElementById('editAdsStatus').value;
    const imageInput = document.getElementById('editAdsImageInput');
    
    // Validate required fields
    if (!title || !description || !budget || !duration) {
        alert("Please fill in all required fields");
        return;
    }
    
    // Find ad index
    const adIndex = advertisements.findIndex(a => a.id === currentEditingAdId);
    if (adIndex === -1) return;
    
    // Update ad
    advertisements[adIndex] = {
        ...advertisements[adIndex],
        title,
        description,
        target,
        budget: parseFloat(budget),
        duration: parseInt(duration),
        status,
        updatedAt: new Date().toISOString()
    };
    
    // Update image if changed
    if (imageInput.files.length > 0) {
        const newImage = URL.createObjectURL(imageInput.files[0]);
        advertisements[adIndex].image = newImage;
    }
    
    // Save data
    saveDataToStorage();
    
    // Show success message
    showToast("Advertisement updated successfully!");
    
    // Go back to ads preview
    goBackToAdsPreview();
}

// Function to delete ad
function deleteAd(adId, event) {
    if (event) event.stopPropagation();
    
    if (!confirm("Are you sure you want to delete this advertisement? This action cannot be undone.")) return;
    
    // Find ad index
    const adIndex = advertisements.findIndex(a => a.id === adId);
    if (adIndex === -1) return;
    
    // Store ad title for confirmation message
    const adTitle = advertisements[adIndex].title;
    
    // Remove ad
    advertisements.splice(adIndex, 1);
    
    // Save data
    saveDataToStorage();
    
    // Re-render ads preview
    renderAdsPreview();
    
    // Show confirmation
    showToast(`"${adTitle}" has been deleted.`);
    
    // Close any open menus
    document.querySelectorAll('.ads-menu-dropdown').forEach(menu => {
        menu.classList.remove('show');
    });
}

// Function to delete current ad from edit page
function deleteCurrentAd() {
    if (!currentEditingAdId) return;
    
    deleteAd(currentEditingAdId);
    goBackToAdsPreview();
}

// Function to go back from ads preview
function goBackFromAdsPreview() {
    document.getElementById('adsPreviewPage').style.display = 'none';
    showProfile();
}

// Function to go back to ads preview from edit page
function goBackToAdsPreview() {
    document.getElementById('editAdsPage').style.display = 'none';
    document.getElementById('adsPreviewPage').style.display = 'block';
    renderAdsPreview();
    currentEditingAdId = null;
    currentEditingAd = null;
}

// Add to hideAllSections function
function hideAllSections() {
    // ... existing sections ...
    const additionalSections = [
        'adsPreviewPage',
        'editAdsPage'
    ];
    
    additionalSections.forEach(sectionId => {
        const section = document.getElementById(sectionId);
        if (section) {
            section.style.display = 'none';
        }
    });
    
    // ... rest of the function ...
}

// Update the createAd function to set default status
function createAd() {
    // ... existing code ...
    
    // Update ad object to include status
    pendingAd = {
        id: Date.now(),
        title,
        description,
        target,
        budget: parseFloat(budget),
        duration: parseInt(duration),
        image: imageUrl,
        timestamp: new Date().toISOString(),
        status: 'pending' // Add status field
    };
    
    // ... rest of the function ...
}

// Close dropdowns when clicking outside
document.addEventListener('click', function(event) {
    // ... existing handlers ...
    
    // Close ads dropdowns when clicking outside
    if (!event.target.closest('.ads-menu, .ads-menu *')) {
        document.querySelectorAll('.ads-menu-dropdown').forEach(dropdown => {
            dropdown.classList.remove('show');
        });
    }
});
           
           
           
           
           
           
           
           

    // Function to render comments with enhanced features
    function renderComments(comments, parentId = null) {
        if (!comments || comments.length === 0) return '';
        
        // Sort comments by timestamp (newest first)
        const sortedComments = [...comments].sort((a, b) => new Date(b.timestamp) - new Date(a.timestamp));
        
        let html = '';
        sortedComments.forEach(comment => {
            // Only render top-level comments unless we're specifically rendering replies
            if (parentId === null && comment.parentId) return;
            if (parentId !== null && comment.parentId !== parentId) return;
            
            const isCurrentUser = comment.userId === currentUser.id;
            const isLiked = comment.likes && comment.likes.includes(currentUser.id);
            const replyCount = comments.filter(c => c.parentId === comment.id).length;
            
            html += `
                <div class="comment" id="comment-${comment.id}">
                    <div class="comment-avatar">
                        <img src="${comment.user.avatar}" alt="${comment.user.name}">
                    </div>
                    <div class="comment-content">
                        <div class="comment-author">${comment.user.name}</div>
                        <div class="comment-text">${comment.text}</div>
                        
                        ${comment.likes && comment.likes.length > 0 ? `
                            <div class="comment-likes-count">
                                <i class="fas fa-heart"></i>
                                <span>${comment.likes.length}</span>
                            </div>
                        ` : ''}
                        
                        <div class="comment-actions">
                            <span class="comment-time">${formatTimeAgo(comment.timestamp)}</span>
                            <span class="comment-action ${isLiked ? 'liked' : ''}" onclick="toggleCommentLike(${comment.id})">
                                <i class="fas fa-heart"></i>
                                <span>${isLiked ? 'Liked' : 'Like'}</span>
                            </span>
                            <span class="comment-action" onclick="showReplyInput(${comment.id})">
                                <i class="fas fa-reply"></i>
                                <span>Reply</span>
                            </span>
                        </div>
                        
                        <div class="comment-more-options" onclick="toggleCommentOptions(${comment.id})">
                            <i class="fas fa-ellipsis-h"></i>
                        </div>
                        
                        <div class="comment-options-dropdown" id="comment-options-${comment.id}">
                            ${isCurrentUser ? `
                                <div class="comment-option" onclick="editComment(${comment.id})">
                                    <i class="fas fa-edit"></i> Edit
                                </div>
                                <div class="comment-option delete" onclick="deleteComment(${comment.id})">
                                    <i class="fas fa-trash"></i> Delete
                                </div>
                            ` : `
                                <div class="comment-option" onclick="reportComment(${comment.id})">
                                    <i class="fas fa-flag"></i> Report
                                </div>
                            `}
                        </div>
                        
                        <div class="comment-edit-input" id="comment-edit-${comment.id}">
                            <textarea id="comment-edit-text-${comment.id}">${comment.text}</textarea>
                            <div class="comment-edit-actions">
                                <button class="comment-edit-btn comment-edit-cancel" onclick="cancelEditComment(${comment.id})">Cancel</button>
                                <button class="comment-edit-btn comment-edit-save" onclick="saveEditComment(${comment.id})">Save</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="reply-input-container" id="reply-input-${comment.id}">
                    <div class="reply-input">
                        <input type="text" id="reply-text-${comment.id}" placeholder="Write a reply...">
                        <button class="reply-send-btn" onclick="postReply(${comment.id})">
                            <i class="fas fa-paper-plane"></i>
                        </button>
                    </div>
                </div>
                
                ${replyCount > 0 ? `
                    <div class="comment-replies" id="replies-${comment.id}">
                        ${renderComments(comments, comment.id)}
                    </div>
                ` : ''}
            `;
        });
        
        return html;
    }

    function togglePostMenu(element) {
        const dropdown = element.querySelector('.post-menu-dropdown');
        dropdown.style.display = dropdown.style.display === 'block' ? 'none' : 'block';
        
        // Close other dropdowns
        document.querySelectorAll('.post-menu-dropdown').forEach(item => {
            if (item !== dropdown) {
                item.style.display = 'none';
            }
        });
    }

    function toggleReadMore(element) {
        const caption = element.previousElementSibling;
        caption.classList.toggle('expanded');
        element.textContent = caption.classList.contains('expanded') ? 'See Less' : 'See More';
    }

    function toggleLike(postId) {
        const post = posts.find(p => p.id === postId);
        if (post) {
            post.liked = !post.liked;
            post.likes += post.liked ? 1 : -1;
            
            // Update earnings when post is liked
            if (post.liked) {
                post.earnings += 0.5;
                currentUser.earnings.total += 0.5;
                currentUser.earnings.available += 0.5;
                updateEarnings();
                
                // Add notification for the post owner (if not the current user)
                if (post.userId !== currentUser.id) {
                    const newNotification = {
                        id: notifications.length + 1,
                        type: "like",
                        title: "New Like",
                        message: `${currentUser.name} liked your post`,
                        timestamp: new Date().toISOString(),
                        read: false,
                        data: { postId: postId, userId: currentUser.id }
                    };
                    addNotification(newNotification);
                    showPushNotification(newNotification);
                }
            }
            
            renderPosts();
            saveDataToStorage();
        }
    }

    function toggleComment(postId) {
        const commentsSection = document.getElementById(`${postId}-comments`);
        if (commentsSection) {
            commentsSection.style.display = commentsSection.style.display === 'none' || !commentsSection.style.display ? 'block' : 'none';
        }
    }

    function postComment(postId) {
        const commentInput = document.getElementById(`comment-input-${postId}`);
        if (!commentInput) return;
        
        const commentText = commentInput.value.trim();
        
        if (commentText) {
            const post = posts.find(p => p.id === postId);
            if (post) {
                const newComment = {
                    id: Date.now(),
                    userId: currentUser.id,
                    user: {
                        name: currentUser.name,
                        avatar: currentUser.avatar
                    },
                    text: commentText,
                    timestamp: new Date().toISOString(),
                    likes: [],
                    parentId: null,
                    replies: []
                };
                
                post.comments.push(newComment);
                
                // Add earnings for comment
                post.earnings += 0.25;
                currentUser.earnings.total += 0.25;
                currentUser.earnings.available += 0.25;
                updateEarnings();
                
                // Add notification for the post owner (if not the current user)
                if (post.userId !== currentUser.id) {
                    const newNotification = {
                        id: notifications.length + 1,
                        type: "comment",
                        title: "New Comment",
                        message: `${currentUser.name} commented on your post: '${commentText}'`,
                        timestamp: new Date().toISOString(),
                        read: false,
                        data: { postId: postId, userId: currentUser.id, commentId: newComment.id }
                    };
                    addNotification(newNotification);
                    showPushNotification(newNotification);
                }
                
                // Re-render comments
                const commentsList = document.getElementById(`comments-list-${postId}`);
                if (commentsList) {
                    commentsList.innerHTML = renderComments(post.comments);
                }
                
                // Clear input
                commentInput.value = '';
                
                // Save data
                saveDataToStorage();
            }
        }
    }

    // Function to post a reply to a comment
    function postReply(commentId) {
        const replyInput = document.getElementById(`reply-text-${commentId}`);
        if (!replyInput) return;
        
        const replyText = replyInput.value.trim();
        
        if (replyText) {
            // Find the post containing this comment
            let targetPost = null;
            let targetComment = null;
            
            for (const post of posts) {
                const comment = post.comments.find(c => c.id === commentId);
                if (comment) {
                    targetPost = post;
                    targetComment = comment;
                    break;
                }
            }
            
            if (targetPost && targetComment) {
                const newReply = {
                    id: Date.now(),
                    userId: currentUser.id,
                    user: {
                        name: currentUser.name,
                        avatar: currentUser.avatar
                    },
                    text: replyText,
                    timestamp: new Date().toISOString(),
                    likes: [],
                    parentId: commentId,
                    replies: []
                };
                
                targetPost.comments.push(newReply);
                
                // Add earnings for reply
                targetPost.earnings += 0.1;
                currentUser.earnings.total += 0.1;
                currentUser.earnings.available += 0.1;
                updateEarnings();
                
                // Add notification for the comment owner (if not the current user)
                if (targetComment.userId !== currentUser.id) {
                    const newNotification = {
                        id: notifications.length + 1,
                        type: "comment",
                        title: "New Reply",
                        message: `${currentUser.name} replied to your comment: '${replyText}'`,
                        timestamp: new Date().toISOString(),
                        read: false,
                        data: { commentId: commentId, userId: currentUser.id }
                    };
                    addNotification(newNotification);
                    showPushNotification(newNotification);
                }
                
                // Re-render comments
                const commentsList = document.getElementById(`comments-list-${targetPost.id}`);
                if (commentsList) {
                    commentsList.innerHTML = renderComments(targetPost.comments);
                }
                
                // Hide reply input
                hideReplyInput(commentId);
                
                // Clear input
                replyInput.value = '';
                
                // Save data
                saveDataToStorage();
            }
        }
    }

    // Function to show reply input
    function showReplyInput(commentId) {
        // Hide all other reply inputs
        document.querySelectorAll('.reply-input-container').forEach(input => {
            input.classList.remove('active');
        });
        
        // Show this reply input
        const replyInput = document.getElementById(`reply-input-${commentId}`);
        if (replyInput) {
            replyInput.classList.add('active');
            const textInput = document.getElementById(`reply-text-${commentId}`);
            if (textInput) {
                textInput.focus();
            }
        }
    }

    // Function to hide reply input
    function hideReplyInput(commentId) {
        const replyInput = document.getElementById(`reply-input-${commentId}`);
        if (replyInput) {
            replyInput.classList.remove('active');
        }
    }

    // Function to toggle comment like
    function toggleCommentLike(commentId) {
        // Find the post containing this comment
        for (const post of posts) {
            const comment = post.comments.find(c => c.id === commentId);
            if (comment) {
                const likedIndex = comment.likes.indexOf(currentUser.id);
                
                if (likedIndex === -1) {
                    // Like the comment
                    comment.likes.push(currentUser.id);
                    
                    // Add notification for the comment owner (if not the current user)
                    if (comment.userId !== currentUser.id) {
                        const newNotification = {
                            id: notifications.length + 1,
                            type: "like",
                            title: "Comment Liked",
                            message: `${currentUser.name} liked your comment: '${comment.text.substring(0, 50)}${comment.text.length > 50 ? '...' : ''}'`,
                            timestamp: new Date().toISOString(),
                            read: false,
                            data: { commentId: commentId, userId: currentUser.id }
                        };
                        addNotification(newNotification);
                        showPushNotification(newNotification);
                    }
                } else {
                    // Unlike the comment
                    comment.likes.splice(likedIndex, 1);
                }
                
                // Re-render comments
                const commentsList = document.getElementById(`comments-list-${post.id}`);
                if (commentsList) {
                    commentsList.innerHTML = renderComments(post.comments);
                }
                
                // Save data
                saveDataToStorage();
                break;
            }
        }
    }

    // Function to toggle comment options dropdown
    function toggleCommentOptions(commentId) {
        const dropdown = document.getElementById(`comment-options-${commentId}`);
        if (!dropdown) return;
        
        dropdown.classList.toggle('show');
        
        
        
        
        
           
           
           
           
           
        

        // Function to toggle product menu
        function toggleProductMenu(button, productId, event) {
            if (event) {
                event.stopPropagation();
            }
            
            const dropdown = document.getElementById(`product-menu-${productId}`);
            if (!dropdown) return;
            
            // Close all other product menus
            document.querySelectorAll('.product-menu-dropdown').forEach(menu => {
                if (menu !== dropdown) {
                    menu.classList.remove('show');
                }
            });
            
            // Toggle current dropdown
            dropdown.classList.toggle('show');
        }

        // Function to edit product from main products grid
        function editProduct(productId, event) {
            if (event) {
                event.stopPropagation();
            }
            
            const product = products.find(p => p.id === productId);
            if (!product) return;
            
            // Find the corresponding user product
            const userProduct = userProducts.find(p => p.id === productId);
            if (userProduct) {
                editUserProduct(productId, event);
            } else {
                alert("Product edit functionality is available only for your own products.");
            }
        }

        // Function to edit user product
        function editUserProduct(productId, event) {
            if (event) {
                event.stopPropagation();
            }
            
            const product = userProducts.find(p => p.id === productId);
            if (!product) return;
            
            // Show product listing page first
            showProductListing();
            
            // Show product form
            const productFormContainer = document.getElementById('productFormContainer');
            if (productFormContainer) {
                productFormContainer.style.display = 'block';
            }
            
            // Populate form with product data
            document.getElementById('companyName').value = product.companyName || '';
            document.getElementById('productName').value = product.productName || '';
            document.getElementById('productPrice').value = product.price || '';
            document.getElementById('transactionsNumber').value = product.transactionNumber || '';
            document.getElementById('productDesc').value = product.description || '';
            document.getElementById('contact').value = product.contactInfo || '';
            
            // Set payment method
            if (product.paymentMethod) {
                document.getElementById('paymentMethod').value = product.paymentMethod;
            }
            
            // Store the product ID for update
            const form = document.getElementById('productForm');
            if (form) {
                form.dataset.editingId = productId;
            }
            
            // Load images if available
            const imagePreview = document.getElementById('imagePreview');
            if (imagePreview && product.images && product.images.length > 0) {
                imagePreview.innerHTML = '';
                product.images.forEach(imageUrl => {
                    const img = document.createElement('img');
                    img.src = imageUrl;
                    img.style.width = '100px';
                    img.style.height = '100px';
                    img.style.objectFit = 'cover';
                    img.style.borderRadius = '5px';
                    imagePreview.appendChild(img);
                });
            }
            
            // Change submit button text
            const submitBtn = document.querySelector('.submit-btn');
            if (submitBtn) {
                submitBtn.textContent = 'Update Product';
            }
            
            // Scroll to form
            productFormContainer.scrollIntoView({ behavior: 'smooth' });
            
            // Close any open menus
            document.querySelectorAll('.product-menu-dropdown').forEach(menu => {
                menu.classList.remove('show');
            });
        }

        // Function to delete product (from main products grid)
        function deleteProduct(productId, event) {
            if (event) {
                event.stopPropagation();
            }
            
            if (!confirm("Are you sure you want to delete this product?")) return;
            
            // Find product
            const productIndex = products.findIndex(p => p.id === productId);
            if (productIndex !== -1) {
                products.splice(productIndex, 1);
            }
            
            // Also delete from user products if exists
            const userProductIndex = userProducts.findIndex(p => p.id === productId);
            if (userProductIndex !== -1) {
                userProducts.splice(userProductIndex, 1);
            }
            
            // Also delete from wishlist
            const wishlistIndex = wishlist.findIndex(p => p.id === productId);
            if (wishlistIndex !== -1) {
                wishlist.splice(wishlistIndex, 1);
            }
            
            // Update shop profile products
            if (currentUser.shop && currentUser.shop.products) {
                const shopProductIndex = currentUser.shop.products.findIndex(p => p.id === productId);
                if (shopProductIndex !== -1) {
                    currentUser.shop.products.splice(shopProductIndex, 1);
                }
            }
            
            // Re-render all views
            renderProducts();
            renderUserProducts();
            renderWishlist();
            renderShopProducts();
            
            // Save data
            saveDataToStorage();
            
            // Show confirmation
            showToast("Product deleted successfully!");
            
            // Close any open menus
            document.querySelectorAll('.product-menu-dropdown').forEach(menu => {
                menu.classList.remove('show');
            });
        }

        // Function to delete user product
        function deleteUserProduct(productId, event) {
            deleteProduct(productId, event);
        }

        // Modified renderProducts function with fixed menu
        function renderProducts() {
            const productsContainer = document.getElementById('productsContainer');
            if (!productsContainer) return;
            
            productsContainer.innerHTML = '';
            
            if (products.length === 0) {
                productsContainer.innerHTML = `
                    <div style="text-align: center; padding: 40px 20px; color: #65676B; grid-column: 1 / -1;">
                        <i class="fas fa-shopping-bag" style="font-size: 64px; margin-bottom: 20px; color: #ddd;"></i>
                        <h3>No products yet</h3>
                        <p>Start selling to see products here</p>
                    </div>
                `;
                return;
            }
            
            // Sort products by timestamp (newest first)
            const sortedProducts = [...products].sort((a, b) => new Date(b.timestamp) - new Date(a.timestamp));
            
            sortedProducts.forEach(product => {
                const isOwner = product.userId === currentUser.id;
                const productElement = document.createElement('div');
                productElement.className = 'product-item';
                productElement.innerHTML = `
                    <img src="${product.image}" alt="${product.name}" class="product-image">
                    ${isOwner ? `
                        <div class="product-menu">
                            <button class="product-menu-btn" onclick="toggleProductMenu(this, ${product.id}, event)">
                                <i class="fas fa-ellipsis-v"></i>
                            </button>
                            <div class="product-menu-dropdown" id="product-menu-${product.id}">
                                <div class="product-menu-option edit" onclick="editProduct(${product.id}, event)">
                                    <i class="fas fa-edit"></i>
                                    <span>Edit</span>
                                </div>
                                <div class="product-menu-option delete" onclick="deleteProduct(${product.id}, event)">
                                    <i class="fas fa-trash"></i>
                                    <span>Delete</span>
                                </div>
                            </div>
                        </div>
                    ` : ''}
                    <div class="product-info">
                        <div class="product-name">${product.name}</div>
                        <div class="product-price">$${product.price.toFixed(2)}</div>
                    </div>
                `;
                productElement.onclick = (e) => {
                    // Don't trigger product details if clicking on menu
                    if (!e.target.closest('.product-menu')) {
                        showProductDetails(product);
                    }
                };
                productsContainer.appendChild(productElement);
            });
        }

        // Modified renderUserProducts function with fixed menu
        function renderUserProducts() {
            const userProductsContainer = document.getElementById('userProductsContainer');
            if (!userProductsContainer) return;
            
            userProductsContainer.innerHTML = '';
            
            if (userProducts.length === 0) {
                userProductsContainer.innerHTML = `
                    <div style="text-align: center; padding: 40px 20px; color: #65676B; grid-column: 1 / -1;">
                        <i class="fas fa-box-open" style="font-size: 64px; margin-bottom: 20px; color: #ddd;"></i>
                        <h3>No products listed</h3>
                        <p>Click the "Sell" button to add your first product</p>
                    </div>
                `;
                return;
            }
            
            // Sort user products by timestamp (newest first)
            const sortedProducts = [...userProducts].sort((a, b) => new Date(b.timestamp) - new Date(a.timestamp));
            
            sortedProducts.forEach(product => {
                const productElement = document.createElement('div');
                productElement.className = 'product-item';
                productElement.innerHTML = `
                    <img src="${product.images[0]}" alt="${product.productName}" class="product-image">
                    <div class="product-menu">
                        <button class="product-menu-btn" onclick="toggleProductMenu(this, ${product.id}, event)">
                            <i class="fas fa-ellipsis-v"></i>
                        </button>
                        <div class="product-menu-dropdown" id="product-menu-${product.id}">
                            <div class="product-menu-option edit" onclick="editUserProduct(${product.id}, event)">
                                <i class="fas fa-edit"></i>
                                <span>Edit</span>
                            </div>
                            <div class="product-menu-option delete" onclick="deleteUserProduct(${product.id}, event)">
                                <i class="fas fa-trash"></i>
                                <span>Delete</span>
                            </div>
                        </div>
                    </div>
                    <div class="product-info">
                        <div class="product-name">${product.productName}</div>
                        <div class="product-price">TZS ${product.price.toLocaleString()}</div>
                        <div style="font-size: 12px; color: #65676B;">${formatTimeAgo(product.timestamp)}</div>
                    </div>
                `;
                productElement.onclick = (e) => {
                    // Don't trigger product details if clicking on menu
                    if (!e.target.closest('.product-menu')) {
                        showUserProductDetails(product);
                    }
                };
                userProductsContainer.appendChild(productElement);
            });
        }

        // Modified renderWishlist function with fixed menu
        function renderWishlist() {
            const wishlistContainer = document.getElementById('wishlistContainer');
            const wishlistEmpty = document.getElementById('wishlistEmpty');
            
            if (!wishlistContainer || !wishlistEmpty) return;
            
            wishlistContainer.innerHTML = '';
            
            if (wishlist.length === 0) {
                wishlistEmpty.style.display = 'block';
                wishlistContainer.style.display = 'none';
            } else {
                wishlistEmpty.style.display = 'none';
                wishlistContainer.style.display = 'grid';
                
                wishlist.forEach(product => {
                    const isOwner = product.userId === currentUser.id;
                    const wishlistItem = document.createElement('div');
                    wishlistItem.className = 'wishlist-item';
                    wishlistItem.innerHTML = `
                        <div class="wishlist-remove" onclick="removeFromWishlist(${product.id}, event)">
                            <i class="fas fa-times"></i>
                        </div>
                        ${isOwner ? `
                            <div class="product-menu">
                                <button class="product-menu-btn" onclick="toggleProductMenu(this, ${product.id}, event)">
                                    <i class="fas fa-ellipsis-v"></i>
                                </button>
                                <div class="product-menu-dropdown" id="product-menu-${product.id}">
                                    <div class="product-menu-option edit" onclick="editProduct(${product.id}, event)">
                                        <i class="fas fa-edit"></i>
                                        <span>Edit</span>
                                    </div>
                                    <div class="product-menu-option delete" onclick="deleteProduct(${product.id}, event)">
                                        <i class="fas fa-trash"></i>
                                        <span>Delete</span>
                                    </div>
                                </div>
                            </div>
                        ` : ''}
                        <img src="${product.image}" alt="${product.name}" class="product-image">
                        <div class="product-info">
                            <div class="product-name">${product.name}</div>
                            <div class="product-price">$${product.price.toFixed(2)}</div>
                        </div>
                    `;
                    wishlistItem.onclick = (e) => {
                        // Don't trigger product details if clicking on menu or remove button
                        if (!e.target.closest('.product-menu') && !e.target.closest('.wishlist-remove')) {
                            showProductDetails(product);
                        }
                    };
                    wishlistContainer.appendChild(wishlistItem);
                });
            }
        }

        // Modified removeFromWishlist function
        function removeFromWishlist(productId, event) {
            if (event) {
                event.stopPropagation();
            }
            
            wishlist = wishlist.filter(item => item.id !== productId);
            renderWishlist();
            
            // Save data
            saveDataToStorage();
            
            // Show confirmation message
            const product = products.find(p => p.id === productId);
            if (product) {
                showToast(`${product.name} removed from your wishlist`);
            }
        }

        // Modified renderShopProducts function with fixed menu
        function renderShopProducts() {
            const shopProductsGrid = document.getElementById('shopProductsGrid');
            if (!shopProductsGrid) return;
            
            shopProductsGrid.innerHTML = '';
            
            // Filter products by current user
            const userProductsList = userProducts.filter(product => product.userId === currentUser.id);
            
            if (userProductsList.length === 0) {
                shopProductsGrid.innerHTML = `
                    <div style="grid-column: 1 / -1; text-align: center; padding: 20px;">
                        <i class="fas fa-box-open" style="font-size: 48px; color: #ddd; margin-bottom: 10px;"></i>
                        <p>No products listed yet</p>
                        <button class="btn btn-primary" onclick="showProductListing()" style="margin-top: 10px;">
                            Add Products
                        </button>
                    </div>
                `;
                return;
            }
            
            // Display user's products
            userProductsList.forEach(product => {
                const productElement = document.createElement('div');
                productElement.className = 'shop-product-item';
                productElement.innerHTML = `
                    <img src="${product.images[0]}" alt="${product.productName}" class="shop-product-image">
                    <div class="product-menu">
                        <button class="product-menu-btn" onclick="toggleProductMenu(this, ${product.id}, event)">
                            <i class="fas fa-ellipsis-v"></i>
                        </button>
                        <div class="product-menu-dropdown" id="product-menu-${product.id}">
                            <div class="product-menu-option edit" onclick="editUserProduct(${product.id}, event)">
                                <i class="fas fa-edit"></i>
                                <span>Edit</span>
                            </div>
                            <div class="product-menu-option delete" onclick="deleteUserProduct(${product.id}, event)">
                                <i class="fas fa-trash"></i>
                                <span>Delete</span>
                            </div>
                        </div>
                    </div>
                    <div class="shop-product-info">
                        <div class="shop-product-name">${product.productName}</div>
                        <div class="shop-product-price">TZS ${product.price.toLocaleString()}</div>
                    </div>
                `;
                productElement.onclick = (e) => {
                    // Don't trigger product details if clicking on menu
                    if (!e.target.closest('.product-menu')) {
                        showUserProductDetails(product);
                    }
                };
                shopProductsGrid.appendChild(productElement);
            });
        }

        // Update submitProductForm function to handle both create and update
        function submitProductForm() {
            const companyName = document.getElementById('companyName').value;
            const productName = document.getElementById('productName').value;
            const productPrice = document.getElementById('productPrice').value;
            const transactionsNumber = document.getElementById('transactionsNumber').value;
            const productDesc = document.getElementById('productDesc').value;
            const contact = document.getElementById('contact').value;
            const paymentMethod = document.getElementById('paymentMethod').value;
            const imagesInput = document.getElementById('productImages');
            const form = document.getElementById('productForm');
            const isEditing = form.dataset.editingId;
            
            // Show loader
            const loader = document.getElementById('loader');
            const successMessage = document.getElementById('successMessage');
            const errorMessage = document.getElementById('errorMessage');
            
            if (loader) loader.style.display = 'block';
            if (successMessage) successMessage.style.display = 'none';
            if (errorMessage) errorMessage.style.display = 'none';
            
            // Validate form
            if (!companyName || !productName || !productPrice || !transactionsNumber || !productDesc || !contact || !paymentMethod || (!imagesInput.files.length && !isEditing)) {
                setTimeout(() => {
                    if (loader) loader.style.display = 'none';
                    if (errorMessage) {
                        errorMessage.style.display = 'block';
                        errorMessage.textContent = 'Tafadhali jaza sehemu zote za fomu na upakie picha';
                    }
                }, 1000);
                return;
            }
            
            // Get image URLs
            const images = [];
            if (imagesInput.files.length > 0) {
                for (let i = 0; i < imagesInput.files.length; i++) {
                    images.push(URL.createObjectURL(imagesInput.files[i]));
                }
            } else if (isEditing) {
                // Keep existing images when editing
                const existingProduct = userProducts.find(p => p.id === parseInt(isEditing));
                if (existingProduct && existingProduct.images) {
                    images.push(...existingProduct.images);
                }
            }
            
            // Simulate form submission
            setTimeout(() => {
                if (isEditing) {
                    // Update existing product
                    const productIndex = userProducts.findIndex(p => p.id === parseInt(isEditing));
                    if (productIndex !== -1) {
                        userProducts[productIndex] = {
                            ...userProducts[productIndex],
                            companyName,
                            productName,
                            price: parseInt(productPrice),
                            transactionNumber: transactionsNumber,
                            contactInfo: contact,
                            description: productDesc,
                            paymentMethod,
                            images,
                            updatedAt: new Date().toISOString()
                        };
                        
                        // Also update in main products array
                        const mainProductIndex = products.findIndex(p => p.id === parseInt(isEditing));
                        if (mainProductIndex !== -1) {
                            products[mainProductIndex] = {
                                ...products[mainProductIndex],
                                name: productName,
                                price: parseInt(productPrice),
                                image: images[0],
                                companyName,
                                description: productDesc
                            };
                        }
                        
                        // Update shop profile products
                        if (currentUser.shop && currentUser.shop.products) {
                            const shopProductIndex = currentUser.shop.products.findIndex(p => p.id === parseInt(isEditing));
                            if (shopProductIndex !== -1) {
                                currentUser.shop.products[shopProductIndex] = {
                                    ...currentUser.shop.products[shopProductIndex],
                                    name: productName,
                                    price: parseInt(productPrice),
                                    image: images[0],
                                    description: productDesc
                                };
                            }
                        }
                    }
                } else {
                    // Create new product
                    const newProduct = {
                        id: Date.now(),
                        userId: currentUser.id,
                        companyName,
                        productName,
                        price: parseInt(productPrice),
                        transactionNumber: transactionsNumber,
                        contactInfo: contact,
                        description: productDesc,
                        paymentMethod,
                        images,
                        category: "other",
                        timestamp: new Date().toISOString()
                    };
                    
                    userProducts.unshift(newProduct);
                    
                    // Update shop profile
                    updateShopProfile(companyName, contact);
                    
                    // Also add to main products array for display in shop
                    const shopProduct = {
                        id: newProduct.id,
                        name: newProduct.productName,
                        price: newProduct.price,
                        image: newProduct.images[0],
                        companyName: newProduct.companyName,
                        description: newProduct.description,
                        category: newProduct.category,
                        timestamp: newProduct.timestamp
                    };
                    products.unshift(shopProduct);
                }
                
                renderUserProducts();
                renderProducts();
                renderShopProducts();
                
                // Reset form
                if (form) {
                    form.reset();
                    delete form.dataset.editingId;
                }
                
                const imagePreview = document.getElementById('imagePreview');
                if (imagePreview) {
                    imagePreview.innerHTML = '';
                }
                
                // Reset submit button text
                const submitBtn = document.querySelector('.submit-btn');
                if (submitBtn) {
                    submitBtn.textContent = 'Wasilisha Bidhaa';
                }
                
                // Save data
                saveDataToStorage();
                
                // Show success message
                if (loader) loader.style.display = 'none';
                if (successMessage) {
                    successMessage.style.display = 'block';
                    successMessage.textContent = isEditing ? 
                        'Bidhaa yako imesasishwa kikamilifu!' : 
                        'Bidhaa yako imewasilishwa kikamilifu!';
                }
                
                // Hide success message after 3 seconds
                setTimeout(() => {
                    if (successMessage) {
                        successMessage.style.display = 'none';
                    }
                }, 3000);
            }, 2000);
        }















        // Close other dropdowns
        document.querySelectorAll('.comment-options-dropdown').forEach(item => {
            if (item !== dropdown) {
                item.classList.remove('show');
            }
        });
        
        // Close on click outside
        document.addEventListener('click', function closeDropdown(e) {
            if (!dropdown.contains(e.target) && !e.target.closest(`.comment-more-options`)) {
                dropdown.classList.remove('show');
                document.removeEventListener('click', closeDropdown);
            }
        });
    }

    // Function to edit comment
    function editComment(commentId) {
        const editInput = document.getElementById(`comment-edit-${commentId}`);
        if (editInput) {
            editInput.classList.add('active');
        }
        
        // Hide options dropdown
        const optionsDropdown = document.getElementById(`comment-options-${commentId}`);
        if (optionsDropdown) {
            optionsDropdown.classList.remove('show');
        }
    }

    // Function to save edited comment
    function saveEditComment(commentId) {
        const editText = document.getElementById(`comment-edit-text-${commentId}`);
        if (!editText) return;
        
        const newText = editText.value.trim();
        
        if (newText) {
            // Find and update the comment
            for (const post of posts) {
                const comment = post.comments.find(c => c.id === commentId);
                if (comment) {
                    comment.text = newText;
                    comment.edited = true;
                    
                    // Re-render comments
                    const commentsList = document.getElementById(`comments-list-${post.id}`);
                    if (commentsList) {
                        commentsList.innerHTML = renderComments(post.comments);
                    }
                    
                    // Save data
                    saveDataToStorage();
                    break;
                }
            }
        }
    }

    // Function to cancel comment edit
    function cancelEditComment(commentId) {
        const editInput = document.getElementById(`comment-edit-${commentId}`);
        if (editInput) {
            editInput.classList.remove('active');
        }
    }

    // Function to delete comment
    function deleteComment(commentId) {
        if (confirm("Are you sure you want to delete this comment?")) {
            // Find and remove the comment
            for (const post of posts) {
                const commentIndex = post.comments.findIndex(c => c.id === commentId);
                if (commentIndex !== -1) {
                    // Also remove any replies to this comment
                    const replies = post.comments.filter(c => c.parentId === commentId);
                    replies.forEach(reply => {
                        const replyIndex = post.comments.findIndex(c => c.id === reply.id);
                        if (replyIndex !== -1) {
                            post.comments.splice(replyIndex, 1);
                        }
                    });
                    
                    post.comments.splice(commentIndex, 1);
                    
                    // Re-render comments
                    const commentsList = document.getElementById(`comments-list-${post.id}`);
                    if (commentsList) {
                        commentsList.innerHTML = renderComments(post.comments);
                    }
                    
                    // Save data
                    saveDataToStorage();
                    break;
                }
            }
        }
    }

    // Function to report comment
    function reportComment(commentId) {
        alert("Comment has been reported. Thank you for keeping our community safe.");
    }

    function deletePost(postId) {
        if (confirm("Are you sure you want to delete this post?")) {
            const postIndex = posts.findIndex(p => p.id === postId);
            if (postIndex !== -1) {
                const post = posts[postIndex];
                // Deduct earnings from total (but not from available balance)
                currentUser.earnings.total -= post.earnings;
                posts.splice(postIndex, 1);
                renderPosts();
                updateEarnings();
                updatePostCount();
                saveDataToStorage();
            }
        }
    }

    function editPost(postId) {
        const post = posts.find(p => p.id === postId);
        if (post) {
            const newCaption = prompt("Edit your post caption:", post.caption);
            if (newCaption !== null) {
                post.caption = newCaption;
                renderPosts();
                saveDataToStorage();
            }
        }
    }

    function reportPost(postId) {
        alert(`Post ${postId} has been reported. Thank you for keeping our community safe.`);
    }

    // Upload Functions
    function openUploadModal() {
        document.getElementById('uploadModal').style.display = 'flex';
    }

    function closeUploadModal() {
        document.getElementById('uploadModal').style.display = 'none';
        cancelUpload();
    }

    function prepareUpload(type) {
        const fileInput = type === 'image' ? document.getElementById('image-upload-input') : document.getElementById('video-upload-input');
        if (!fileInput) return;
        
        fileInput.click();
        
        fileInput.onchange = function() {
            const file = fileInput.files[0];
            if (file) {
                pendingUpload.type = type;
                pendingUpload.file = file;
                
                const previewContainer = document.getElementById('mediaPreviewContainer');
                previewContainer.innerHTML = '';
                
                if (type === 'image') {
                    const img = document.createElement('img');
                    img.src = URL.createObjectURL(file);
                    img.className = 'media-preview';
                    previewContainer.appendChild(img);
                } else {
                    const video = document.createElement('video');
                    video.src = URL.createObjectURL(file);
                    video.className = 'media-preview';
                    video.controls = true;
                    previewContainer.appendChild(video);
                }
                
                openUploadModal();
            }
        };
    }

    // Modified confirmUpload function to require payment
    function confirmUpload() {
        const caption = document.getElementById('captionInput').value.trim();
        
        if (pendingUpload.file) {
            // Create a new post object but don't add it to posts yet
            pendingPost = {
                id: Date.now(),
                userId: currentUser.id,
                user: {
                    name: currentUser.name,
                    avatar: currentUser.avatar
                },
                caption: caption,
                media: {
                    type: pendingUpload.type,
                    url: URL.createObjectURL(pendingUpload.file)
                },
                timestamp: new Date().toISOString(),
                likes: 0,
                comments: [],
                shares: 0,
                earnings: 0,
                liked: false
            };
            
            // Generate payment reference
            paymentReference = generatePaymentReference();
            
            // Show payment modal instead of directly posting
            showPaymentModal();
        } else {
            alert("Please select an image or video to upload");
        }
    }

    function cancelUpload() {
        pendingUpload = {
            type: null,
            file: null
        };
        document.getElementById('image-upload-input').value = '';
        document.getElementById('video-upload-input').value = '';
        document.getElementById('captionInput').value = '';
        document.getElementById('mediaPreviewContainer').innerHTML = '';
    }







function renderProducts() {
    const productsContainer = document.getElementById('productsContainer');
    if (!productsContainer) return;
    
    productsContainer.innerHTML = '';
    
    if (products.length === 0) {
        productsContainer.innerHTML = `
            <div style="text-align: center; padding: 40px 20px; color: #65676B; grid-column: 1 / -1;">
                <i class="fas fa-shopping-bag" style="font-size: 64px; margin-bottom: 20px; color: #ddd;"></i>
                <h3>No products yet</h3>
                <p>Start selling to see products here</p>
            </div>
        `;
        return;
    }
    
    // Sort products by timestamp (newest first)
    const sortedProducts = [...products].sort((a, b) => new Date(b.timestamp) - new Date(a.timestamp));
    
    sortedProducts.forEach(product => {
        const isOwner = product.userId === currentUser.id;
        const productElement = document.createElement('div');
        productElement.className = 'product-item';
        productElement.innerHTML = `
            <img src="${product.image}" alt="${product.name}" class="product-image">
            ${isOwner ? `
                <div class="product-menu">
                    <button class="product-menu-btn" onclick="toggleProductMenu(this, ${product.id})">
                        <i class="fas fa-ellipsis-v"></i>
                    </button>
                    <div class="product-menu-dropdown" id="product-menu-${product.id}">
                        <div class="product-menu-option edit" onclick="editProduct(${product.id})">
                            <i class="fas fa-edit"></i>
                            <span>Edit</span>
                        </div>
                        <div class="product-menu-option delete" onclick="deleteProduct(${product.id})">
                            <i class="fas fa-trash"></i>
                            <span>Delete</span>
                        </div>
                    </div>
                </div>
            ` : ''}
            <div class="product-info">
                <div class="product-name">${product.name}</div>
                <div class="product-price">$${product.price.toFixed(2)}</div>
            </div>
        `;
        productElement.onclick = (e) => {
            // Don't trigger product details if clicking on menu
            if (!e.target.closest('.product-menu')) {
                showProductDetails(product);
            }
        };
        productsContainer.appendChild(productElement);
    });
}
      
      
      
      
      
      


     function renderUserProducts() {
    const userProductsContainer = document.getElementById('userProductsContainer');
    if (!userProductsContainer) return;
    
    userProductsContainer.innerHTML = '';
    
    if (userProducts.length === 0) {
        userProductsContainer.innerHTML = `
            <div style="text-align: center; padding: 40px 20px; color: #65676B; grid-column: 1 / -1;">
                <i class="fas fa-box-open" style="font-size: 64px; margin-bottom: 20px; color: #ddd;"></i>
                    <h3>No products listed</h3>
                    <p>Click the "Sell" button to add your first product</p>
                </div>
            `;
            return;
        }
        
        // Sort user products by timestamp (newest first)
        const sortedProducts = [...userProducts].sort((a, b) => new Date(b.timestamp) - new Date(a.timestamp));
        
        sortedProducts.forEach(product => {
            const productElement = document.createElement('div');
            productElement.className = 'product-item';
            productElement.innerHTML = `
                <img src="${product.images[0]}" alt="${product.productName}" class="product-image">
                <div class="product-menu">
                    <button class="product-menu-btn" onclick="toggleProductMenu(this, ${product.id})">
                        <i class="fas fa-ellipsis-v"></i>
                    </button>
                    <div class="product-menu-dropdown" id="product-menu-${product.id}">
                        <div class="product-menu-option edit" onclick="editUserProduct(${product.id})">
                            <i class="fas fa-edit"></i>
                            <span>Edit</span>
                        </div>
                        <div class="product-menu-option delete" onclick="deleteUserProduct(${product.id})">
                            <i class="fas fa-trash"></i>
                            <span>Delete</span>
                        </div>
                    </div>
                </div>
                <div class="product-info">
                    <div class="product-name">${product.productName}</div>
                    <div class="product-price">TZS ${product.price.toLocaleString()}</div>
                    <div style="font-size: 12px; color: #65676B;">${formatTimeAgo(product.timestamp)}</div>
                </div>
            `;
            productElement.onclick = (e) => {
                // Don't trigger product details if clicking on menu
                if (!e.target.closest('.product-menu')) {
                    showUserProductDetails(product);
                }
            };
            userProductsContainer.appendChild(productElement);
        });
    }







    // Show user product details
    function showUserProductDetails(product) {
        currentProductDetails = product;
        
        // Update product details page with product information
        document.getElementById('productDetailsImage').src = product.images[0];
        document.getElementById('productDetailsName').textContent = product.productName;
        document.getElementById('productDetailsPrice').textContent = `TZS ${product.price.toLocaleString()}`;
        document.getElementById('productDetailsCompany').textContent = `By ${product.companyName}`;
        document.getElementById('productDetailsDescription').textContent = product.description;
        document.getElementById('productDetailsCategory').textContent = product.category || 'Other';
        
        // Show product details page and hide other sections
        hideAllSections();
        document.getElementById('productDetailsPage').style.display = 'block';
    }

    // Show product details page
    function showProductDetails(product) {
        currentProductDetails = product;
        
        // Update product details page with product information
        document.getElementById('productDetailsImage').src = product.image;
        document.getElementById('productDetailsName').textContent = product.name;
        document.getElementById('productDetailsPrice').textContent = `$${product.price.toFixed(2)}`;
        document.getElementById('productDetailsCompany').textContent = `By ${product.companyName}`;
        document.getElementById('productDetailsDescription').textContent = product.description;
        document.getElementById('productDetailsCategory').textContent = product.category;
        
        // Update wishlist button state
        const wishlistBtn = document.getElementById('wishlistBtn');
        const isInWishlist = wishlist.some(item => item.id === product.id);
        if (wishlistBtn) {
            if (isInWishlist) {
                wishlistBtn.classList.add('active');
                wishlistBtn.innerHTML = '<i class="fas fa-heart"></i> In Wishlist';
            } else {
                wishlistBtn.classList.remove('active');
                wishlistBtn.innerHTML = '<i class="fas fa-heart"></i> Wishlist';
            }
        }
        
        // Show product details page and hide other sections
        hideAllSections();
        document.getElementById('productDetailsPage').style.display = 'block';
    }

    // Go back to shop from product details
    function goBackToShop() {
        document.getElementById('productDetailsPage').style.display = 'none';
        showProducts();
    }

    // Product action functions
    function buyProduct() {
        if (currentProductDetails) {
            alert(`You are about to purchase: ${currentProductDetails.name}\nPrice: $${currentProductDetails.price.toFixed(2)}\n\nProceeding to checkout...`);
        }
    }

    function contactSeller() {
        if (currentProductDetails) {
            alert(`Contacting seller for: ${currentProductDetails.name}\n\nSeller: ${currentProductDetails.companyName}\n\nThis would open a chat interface in a real app.`);
        }
    }

    // Wishlist functions
    function toggleWishlist() {
        if (!currentProductDetails) return;
        
        const wishlistBtn = document.getElementById('wishlistBtn');
        const isInWishlist = wishlist.some(item => item.id === currentProductDetails.id);
        
        if (isInWishlist) {
            // Remove from wishlist
            wishlist = wishlist.filter(item => item.id !== currentProductDetails.id);
            if (wishlistBtn) {
                wishlistBtn.classList.remove('active');
                wishlistBtn.innerHTML = '<i class="fas fa-heart"></i> Wishlist';
            }
        } else {
            // Add to wishlist
            wishlist.push(currentProductDetails);
            if (wishlistBtn) {
                wishlistBtn.classList.add('active');
                wishlistBtn.innerHTML = '<i class="fas fa-heart"></i> In Wishlist';
            }
        }
        
        // Save data
        saveDataToStorage();
        
        // Show confirmation message
        alert(isInWishlist ? 
            `${currentProductDetails.name} removed from your wishlist` : 
            `${currentProductDetails.name} added to your wishlist`);
    }

    function showWishlist() {
        hideAllSections();
        document.getElementById('wishlistPage').style.display = 'block';
        renderWishlist();
    }







function renderWishlist() {
    const wishlistContainer = document.getElementById('wishlistContainer');
    const wishlistEmpty = document.getElementById('wishlistEmpty');
    
    if (!wishlistContainer || !wishlistEmpty) return;
    
    wishlistContainer.innerHTML = '';
    
    if (wishlist.length === 0) {
        wishlistEmpty.style.display = 'block';
        wishlistContainer.style.display = 'none';
    } else {
        wishlistEmpty.style.display = 'none';
        wishlistContainer.style.display = 'grid';
        
        wishlist.forEach(product => {
            const isOwner = product.userId === currentUser.id;
            const wishlistItem = document.createElement('div');
            wishlistItem.className = 'wishlist-item';
            wishlistItem.innerHTML = `
                <div class="wishlist-remove" onclick="removeFromWishlist(${product.id})">
                    <i class="fas fa-times"></i>
                </div>
                ${isOwner ? `
                    <div class="product-menu">
                        <button class="product-menu-btn" onclick="toggleProductMenu(this, ${product.id})">
                            <i class="fas fa-ellipsis-v"></i>
                        </button>
                        <div class="product-menu-dropdown" id="product-menu-${product.id}">
                            <div class="product-menu-option edit" onclick="editProduct(${product.id})">
                                <i class="fas fa-edit"></i>
                                <span>Edit</span>
                            </div>
                            <div class="product-menu-option delete" onclick="deleteProduct(${product.id})">
                                <i class="fas fa-trash"></i>
                                <span>Delete</span>
                            </div>
                        </div>
                    </div>
                ` : ''}
                <img src="${product.image}" alt="${product.name}" class="product-image">
                <div class="product-info">
                    <div class="product-name">${product.name}</div>
                    <div class="product-price">$${product.price.toFixed(2)}</div>
                </div>
            `;
            wishlistItem.onclick = (e) => {
                // Don't trigger product details if clicking on menu or remove button
                if (!e.target.closest('.product-menu') && !e.target.closest('.wishlist-remove')) {
                    showProductDetails(product);
                }
            };
            wishlistContainer.appendChild(wishlistItem);
        });
    }
}










    function removeFromWishlist(productId) {
        // Stop event propagation to prevent triggering the product details view
        event.stopPropagation();
        
        wishlist = wishlist.filter(item => item.id !== productId);
        renderWishlist();
        
        // Save data
        saveDataToStorage();
        
        // Show confirmation message
        const product = products.find(p => p.id === productId);
        if (product) {
            alert(`${product.name} removed from your wishlist`);
        }
    }

    function goBackFromWishlist() {
        document.getElementById('wishlistPage').style.display = 'none';
        showProfile();
    }

    // Product Listing Functions
    function showProductListing() {
        hideAllSections();
        document.getElementById('productListingPage').style.display = 'block';
    }

    function showProductForm() {
        const productFormContainer = document.getElementById('productFormContainer');
        if (productFormContainer) {
            productFormContainer.style.display = 'block';
        }
    }

    function handleImageUpload(input) {
        const previewContainer = document.getElementById('imagePreview');
        if (!previewContainer) return;
        
        previewContainer.innerHTML = '';
        
        if (input.files && input.files.length > 0) {
            for (let i = 0; i < input.files.length; i++) {
                const file = input.files[i];
                const img = document.createElement('img');
                img.src = URL.createObjectURL(file);
                previewContainer.appendChild(img);
            }
        }
    }

    function submitProductForm() {
        const companyName = document.getElementById('companyName').value;
        const productName = document.getElementById('productName').value;
        const productPrice = document.getElementById('productPrice').value;
        const transactionsNumber = document.getElementById('transactionsNumber').value;
        const productDesc = document.getElementById('productDesc').value;
        const contact = document.getElementById('contact').value;
        const paymentMethod = document.getElementById('paymentMethod').value;
        const imagesInput = document.getElementById('productImages');
        
        // Show loader
        document.getElementById('loader').style.display = 'block';
        document.getElementById('successMessage').style.display = 'none';
        document.getElementById('errorMessage').style.display = 'none';
        
        // Validate form
        if (!companyName || !productName || !productPrice || !transactionsNumber || !productDesc || !contact || !paymentMethod || !imagesInput.files.length) {
            setTimeout(() => {
                document.getElementById('loader').style.display = 'none';
                document.getElementById('errorMessage').style.display = 'block';
                document.getElementById('errorMessage').textContent = 'Tafadhali jaza sehemu zote za fomu na upakie picha';
            }, 1000);
            return;
        }
        
        // Get image URLs
        const images = [];
        for (let i = 0; i < imagesInput.files.length; i++) {
            images.push(URL.createObjectURL(imagesInput.files[i]));
        }
        
        // Simulate form submission
        setTimeout(() => {
            // Create new product
            const newProduct = {
                id: Date.now(),
                userId: currentUser.id,
                companyName,
                productName,
                price: parseInt(productPrice),
                transactionNumber: transactionsNumber,
                contactInfo: contact,
                description: productDesc,
                paymentMethod,
                images,
                category: "other",
                timestamp: new Date().toISOString()
            };
            
            userProducts.unshift(newProduct);
            
            // Update shop profile
            updateShopProfile(companyName, contact);
            
            // Also add to main products array for display in shop
            const shopProduct = {
                id: newProduct.id,
                name: newProduct.productName,
                price: newProduct.price,
                image: newProduct.images[0],
                companyName: newProduct.companyName,
                description: newProduct.description,
                category: newProduct.category,
                timestamp: newProduct.timestamp
            };
            products.unshift(shopProduct);
            
            renderUserProducts();
            renderProducts();
            renderShopProfile();
            
            // Reset form
            document.getElementById('productForm').reset();
            document.getElementById('imagePreview').innerHTML = '';
            
            // Save data
            saveDataToStorage();
            
            // Show success message
            document.getElementById('loader').style.display = 'none';
            document.getElementById('successMessage').style.display = 'block';
            document.getElementById('successMessage').textContent = 'Bidhaa yako imewasilishwa kikamilifu!';
            
            // Hide success message after 3 seconds
            setTimeout(() => {
                document.getElementById('successMessage').style.display = 'none';
            }, 3000);
        }, 2000);
    }

    function showCategories() {
        document.getElementById('categoriesPage').style.display = 'block';
    }

    function hideCategories() {
        document.getElementById('categoriesPage').style.display = 'none';
    }

    function filterProducts(category) {
        alert("Inafanya uchaguzi wa bidhaa za: " + category);
        hideCategories();
    }

    // Navigation Functions
    function showHome() {
        hideAllSections();
        document.getElementById('posts-container').style.display = 'block';
        updateNavActive(0);
    }

    function showProducts() {
        hideAllSections();
        document.getElementById('productsSection').style.display = 'block';
        updateNavActive(1);
    }

    function showFriends() {
        hideAllSections();
        document.getElementById('friendsSection').style.display = 'block';
        updateNavActive(2);
    }

    function showEarnings() {
        hideAllSections();
        document.getElementById('earningsSection').style.display = 'block';
        updateNavActive(3);
        
        // Update withdrawal phone number
        updateWithdrawalPhoneNumber();
    }

    function showProfile() {
        hideAllSections();
        document.getElementById('profileSection').style.display = 'block';
        updateNavActive(4);
    }

    function updateNavActive(index) {
        document.querySelectorAll('.nav-item').forEach((item, i) => {
            if (i === index) {
                item.classList.add('active');
            } else {
                item.classList.remove('active');
            }
        });
    }

    function updateEarnings() {
        document.getElementById('totalEarnings').textContent = `$${currentUser.earnings.total.toFixed(2)}`;
        document.getElementById('availableEarnings').textContent = `$${currentUser.earnings.available.toFixed(2)}`;
    }

    function updatePostCount() {
        const userPostCount = posts.filter(post => post.userId === currentUser.id).length;
        document.getElementById('postCount').textContent = userPostCount;
    }

    // Helper function to hide all sections
    function hideAllSections() {
        const sections = [
            'posts-container',
            'productsSection',
            'earningsSection',
            'profileSection',
            'productListingPage',
            'helpSupportSection',
            'wishlistPage',
            'friendsSection',
            'productDetailsPage',
            'settingsSection',
            'adsPaymentPage',
            'shopProfilePage'
        ];
        
        sections.forEach(sectionId => {
            const section = document.getElementById(sectionId);
            if (section) {
                section.style.display = 'none';
            }
        });
        
        // Also hide modals
        const modals = [
            'uploadModal',
            'profileSetupModal',
            'passwordRecoveryModal',
            'googleConnectModal',
            'paymentModal',
            'shareModal',
            'languageModal',
            'privacyModal',
            'adsCreationModal'
        ];
        
        modals.forEach(modalId => {
            const modal = document.getElementById(modalId);
            if (modal) {
                modal.style.display = 'none';
            }
        });
    }

    // Profile Setup Functions
    function showProfileSetup() {
        document.getElementById('profileSetupModal').style.display = 'flex';
        
        // Populate form with current user data
        document.getElementById('fullName').value = currentUser.profile.fullName;
        document.getElementById('dateOfBirth').value = currentUser.profile.dateOfBirth;
        document.getElementById('country').value = currentUser.profile.country;
        document.getElementById('email').value = currentUser.profile.email;
        document.getElementById('workplace').value = currentUser.profile.workplace;
        document.getElementById('education').value = currentUser.profile.education;
        document.getElementById('bio').value = currentUser.profile.bio;
        
        // Set phone number
        if (phoneInput) {
            phoneInput.setNumber(currentUser.profile.phoneNumber);
        }
        
        // Set profile picture
        document.getElementById('profileSetupAvatar').src = currentUser.avatar;
        
        // Update verify button state
        updateVerifyButton();
        
        // Reset verification code section
        document.getElementById('verificationCode').classList.remove('active');
        document.getElementById('verifyEmailBtn').disabled = false;
        document.getElementById('verifyEmailBtn').textContent = "Verify";
        
        // Clear any existing timer
        if (resendTimer) {
            clearInterval(resendTimer);
            resendTimer = null;
        }
    }

    function closeProfileSetup() {
        document.getElementById('profileSetupModal').style.display = 'none';

        // Clear any existing timer
        if (resendTimer) {
            clearInterval(resendTimer);
            resendTimer = null;
        }
    }

    function handleProfilePictureUpload(input) {
        if (input.files && input.files[0]) {
            const reader = new FileReader();
            
            reader.onload = function(e) {
                document.getElementById('profileSetupAvatar').src = e.target.result;
            };
            
            reader.readAsDataURL(input.files[0]);
        }
    }

    function saveProfile() {
        // Get form values
        const fullName = document.getElementById('fullName').value;
        const dateOfBirth = document.getElementById('dateOfBirth').value;
        const country = document.getElementById('country').value;
        const workplace = document.getElementById('workplace').value;
        const education = document.getElementById('education').value;
        const bio = document.getElementById('bio').value;
        const email = document.getElementById('email').value;
        
        // Get phone number with country code
        const phoneNumber = phoneInput.getNumber();
        
        // Validate required fields
        if (!fullName || !dateOfBirth || !country || !phoneNumber || !email) {
            alert("Please fill in all required fields");
            return;
        }
        
        // Update current user profile
        currentUser.profile.fullName = fullName;
        currentUser.profile.dateOfBirth = dateOfBirth;
        currentUser.profile.country = country;
        currentUser.profile.phoneNumber = phoneNumber;
        currentUser.profile.email = email;
        currentUser.profile.workplace = workplace;
        currentUser.profile.education = education;
        currentUser.profile.bio = bio;
        
        // Update user name
        currentUser.name = fullName;
        
        // Update profile picture if changed
        const newAvatar = document.getElementById('profileSetupAvatar').src;
        if (newAvatar !== currentUser.avatar) {
            currentUser.avatar = newAvatar;
        }
        
        // Update profile display
        updateProfileDisplay();
        
        // Save data
        saveDataToStorage();
        
        // Close modal
        closeProfileSetup();
        
        // Show success message
        alert("Profile updated successfully!");
    }

    function updateProfileDisplay() {
        document.getElementById('profileName').textContent = currentUser.profile.fullName;
        document.getElementById('profileStatus').textContent = currentUser.profile.status;
        document.getElementById('profileAvatar').src = currentUser.avatar;
        document.getElementById('currentUserAvatar').src = currentUser.avatar;
        updatePostCount();
    }

    // Withdrawal Functions
    function updateWithdrawalPhoneNumber() {
        const phoneNumber = currentUser.profile.phoneNumber || "+255 000 000 000";
        document.getElementById('withdrawalPhoneNumber').textContent = phoneNumber;
    }

    function showWithdrawalPasswordPage() {
        const withdrawalAmount = document.getElementById('withdrawalAmount').value;
        
        if (!withdrawalAmount || withdrawalAmount <= 0) {
            alert("Please enter a valid withdrawal amount");
            return;
        }
        
        if (parseFloat(withdrawalAmount) > currentUser.earnings.available) {
            alert("You don't have enough available earnings for this withdrawal");
            return;
        }
        
        // Update withdrawal password page with amount and phone number
        document.getElementById('withdrawalAmountValue').textContent = `$${parseFloat(withdrawalAmount).toFixed(2)}`;
        document.getElementById('withdrawalPhoneValue').textContent = currentUser.profile.phoneNumber || "+255 000 000 000";
        
        // Clear password field
        document.getElementById('withdrawalPassword').value = '';
        
        // Hide earnings section and show withdrawal password page
        document.getElementById('earningsSection').style.display = 'none';
        document.getElementById('withdrawalPasswordPage').style.display = 'block';
    }

    function cancelWithdrawal() {
        // Hide withdrawal password page and show earnings section
        document.getElementById('withdrawalPasswordPage').style.display = 'none';
        document.getElementById('earningsSection').style.display = 'block';
    }

    function confirmWithdrawal() {
        const withdrawalPassword = document.getElementById('withdrawalPassword').value;
        const withdrawalAmount = document.getElementById('withdrawalAmount').value;
        
        if (!withdrawalPassword) {
            alert("Please enter your password");
            return;
        }
        
        // Check if password matches (in a real app, this would be hashed and verified securely)
        if (withdrawalPassword !== currentUser.profile.password) {
            alert("Incorrect password. Please try again.");
            return;
        }
        
        // Process withdrawal
        const amount = parseFloat(withdrawalAmount);
        currentUser.earnings.available -= amount;
        updateEarnings();
        
        // Save data
        saveDataToStorage();
        
        // Show success message
        alert(`Withdrawal of $${amount.toFixed(2)} has been processed successfully! The funds will be sent to ${currentUser.profile.phoneNumber}`);
        
        // Hide withdrawal password page and show earnings section
        document.getElementById('withdrawalPasswordPage').style.display = 'none';
        document.getElementById('earningsSection').style.display = 'block';
        
        // Reset withdrawal amount
        document.getElementById('withdrawalAmount').value = '';
    }

    // Search Functions
    function toggleSearch() {
        const searchBar = document.getElementById('searchBar');
        searchBar.style.display = searchBar.style.display === 'none' || !searchBar.style.display ? 'block' : 'none';
    }

    function searchMedia() {
        const searchTerm = document.getElementById('media-search').value.toLowerCase();
        const postsContainer = document.getElementById('posts-container');
        const allPosts = postsContainer.querySelectorAll('.post');
        
        allPosts.forEach(post => {
            const caption = post.querySelector('.post-caption').textContent.toLowerCase();
            const userName = post.querySelector('.name').textContent.toLowerCase();
            post.style.display = caption.includes(searchTerm) || userName.includes(searchTerm) ? 'block' : 'none';
        });
    }

    // Payment Functions
    function showPaymentModal() {
        document.getElementById('paymentModal').style.display = 'flex';
        document.getElementById('paymentReference').textContent = paymentReference;
        
        // Reset payment status
        document.getElementById('paymentProcessing').style.display = 'none';
        document.getElementById('paymentSuccess').style.display = 'none';
        document.getElementById('paymentError').style.display = 'none';
        document.getElementById('transactionId').value = '';
    }
    
    function closePaymentModal() {
        document.getElementById('paymentModal').style.display = 'none';
        // Reset pending post if user cancels
        pendingPost = null;
    }
    
    function generatePaymentReference() {
        const timestamp = new Date().getTime();
        const random = Math.floor(Math.random() * 1000);
        return `POST-${timestamp}-${random}`;
    }
    
    function verifyPayment() {
        const transactionId = document.getElementById('transactionId').value.trim();
        
        if (!transactionId) {
            alert("Please enter your transaction ID");
            return;
        }
        
        // Show processing status
        document.getElementById('paymentProcessing').style.display = 'block';
        document.getElementById('paymentSuccess').style.display = 'none';
        document.getElementById('paymentError').style.display = 'none';
        
        // Simulate payment verification (in a real app, this would call your backend)
        setTimeout(() => {
            // For demo purposes, we'll accept any transaction ID that's not empty
            // In a real app, you would verify with the payment gateway
            if (transactionId.length > 0) {
                // Payment successful
                document.getElementById('paymentProcessing').style.display = 'none';
                document.getElementById('paymentSuccess').style.display = 'block';
                
                // Add the pending post to the posts array
                if (pendingPost) {
                    posts.unshift(pendingPost);
                    renderPosts();
                    updatePostCount();
                    
                    // Save data
                    saveDataToStorage();
                    
                    // Show success message
                    setTimeout(() => {
                        closePaymentModal();
                        cancelUpload();
                        closeUploadModal();
                        alert("Post published successfully! Thank you for your payment.");
                    }, 1500);
                }
            } else {
                // Payment failed
                document.getElementById('paymentProcessing').style.display = 'none';
                document.getElementById('paymentError').style.display = 'block';
            }
        }, 2000);
    }
    
    // Email Verification Functions
    function verifyEmail() {
        const email = document.getElementById('email').value;
        
        if (!email) {
            showToast("Please enter your email address", "error");
            return;
        }
        
        if (!isValidEmail(email)) {
            showToast("Please enter a valid email address", "error");
            return;
        }
        
        // Show verification code input
        document.getElementById('verificationCode').classList.add('active');
        
        // Disable verify button
        document.getElementById('verifyEmailBtn').disabled = true;
        document.getElementById('verifyEmailBtn').textContent = "Sending...";
        
        // Store the email being verified
        verificationEmail = email;
        
        // Send verification code via email
        sendVerificationCode(email);
    }

    function sendVerificationCode(email) {
        // Generate a 6-digit random code
        verificationCode = generateVerificationCode();
        
        // In a real application, you would send this code to the user's email
        // For this demo, we'll simulate the process
        console.log(`Verification code for ${email}: ${verificationCode}`);
        
        // Simulate API call to send email
        setTimeout(() => {
            // Show success message
            showToast(`Verification code sent to ${email}`);
            
            // Update button text
            document.getElementById('verifyEmailBtn').textContent = "Verifying...";
            
            // Start resend countdown
            startResendCountdown();
            
            // Focus first code input
            document.querySelector('.code-input').focus();
        }, 1500);
    }

    function isValidEmail(email) {
        const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
        return emailRegex.test(email);
    }

    function generateVerificationCode() {
        // Generate a 6-digit random code
        return Math.floor(100000 + Math.random() * 900000).toString();
    }

    function moveToNext(input, nextIndex) {
        const value = input.value;
        
        if (value.length === 1) {
            const inputs = document.querySelectorAll('.code-input');
            
            if (nextIndex < inputs.length) {
                inputs[nextIndex].focus();
            } else {
                // All inputs filled, verify the code
                verifyCode();
            }
        }
    }

    function verifyCode() {
        const inputs = document.querySelectorAll('.code-input');
        let enteredCode = "";
        
        inputs.forEach(input => {
            enteredCode += input.value;
        });
        
        if (enteredCode === verificationCode) {
            // Code is correct
            showToast("Email verified successfully!");
            currentUser.profile.emailVerified = true;
            
            // Hide verification code input
            document.getElementById('verificationCode').classList.remove('active');
            
            // Reset inputs
            inputs.forEach(input => {
                input.value = "";
            });
            
            // Enable verify button with new text
            document.getElementById('verifyEmailBtn').disabled = false;
            document.getElementById('verifyEmailBtn').textContent = "Verified";
            
            // Clear any existing timer
            if (resendTimer) {
                clearInterval(resendTimer);
                resendTimer = null;
            }
            
            // Save data
            saveDataToStorage();
        } else {
            // Code is incorrect
            showToast("Invalid verification code. Please try again.", "error");
            
            // Clear inputs
            inputs.forEach(input => {
                input.value = "";
            });
            
            // Focus first input
            inputs[0].focus();
        }
    }

    function resendVerificationCode() {
        const resendElement = document.querySelector('.resend-code');
        
        // Check if we're still in the countdown period
        if (resendElement.textContent !== "Resend code") {
            return;
        }
        
        // Send new verification code
        sendVerificationCode(verificationEmail);
    }

    function startResendCountdown() {
        const resendElement = document.querySelector('.resend-code');
        resendCountdown = 60;
        
        resendElement.textContent = `Resend code in ${resendCountdown}s`;
        resendElement.style.cursor = 'default';
        resendElement.style.color = '#999';
        
        resendTimer = setInterval(() => {
            resendCountdown--;
            
            if (resendCountdown <= 0) {
                clearInterval(resendTimer);
                resendElement.textContent = "Resend code";
                resendElement.style.cursor = 'pointer';
                resendElement.style.color = '#4267B2';
            } else {
                resendElement.textContent = `Resend code in ${resendCountdown}s`;
            }
        }, 1000);
    }

    function updateVerifyButton() {
        const email = document.getElementById('email').value;
        const verifyBtn = document.getElementById('verifyEmailBtn');
        
        if (currentUser.profile.emailVerified && email === currentUser.profile.email) {
            verifyBtn.disabled = true;
            verifyBtn.textContent = "Verified";
        } else {
            verifyBtn.disabled = false;
            verifyBtn.textContent = "Verify";
        }
    }

    // Email Options Functions
    function showGoogleConnect() {
        document.getElementById('googleConnectModal').style.display = 'flex';
    }

    function closeGoogleConnect() {
        document.getElementById('googleConnectModal').style.display = 'none';
    }

    function createNewEmail() {
        // In a real app, this would redirect to an email provider
        showToast("This would redirect to an email provider to create a new account");
    }

    function connectGoogleAccount(option) {
        switch(option) {
            case 'signin':
                showToast("Signing in with Google...");
                // In a real app, this would initiate Google OAuth flow
                break;
            case 'import':
                showToast("Importing Google contacts...");
                // In a real app, this would request permission to access Google contacts
                break;
            case 'sync':
                showToast("Syncing Google Calendar...");
                // In a real app, this would request permission to access Google Calendar
                break;
            case 'backup':
                showToast("Setting up Google Drive backup...");
                // In a real app, this would request permission to access Google Drive
                break;
        }
        
        // Close the modal
        closeGoogleConnect();
        
        // Set the email field with a placeholder Google email
        document.getElementById('email').value = "user@gmail.com";
        // Update verify button
        updateVerifyButton();
    }

    // Password and Email Verification Variables
    let recoveryPhoneInput;
    let passwordStrength = 0;
    let passwordRequirements = {
        length: false,
        uppercase: false,
        lowercase: false,
        number: false,
        special: false
    };
    
    // Initialize password recovery phone input
    function initPasswordRecovery() {
        const recoveryPhoneElement = document.getElementById('recoveryPhone');
        if (recoveryPhoneElement) {
            recoveryPhoneInput = window.intlTelInput(recoveryPhoneElement, {
                initialCountry: "tz",
                separateDialCode: true,
                utilsScript: "https://cdn.jsdelivr.net/npm/intl-tel-input@17.0.12/build/js/utils.js",
            });
        }
    }
    
    // Show password setup page
    function showPasswordSetup() {
        // First save the profile data
        if (!saveProfileData()) {
            return;
        }
        
        // Hide all sections and show password setup page
        hideAllSections();
        
        // Show password setup page
        document.getElementById('passwordSetupPage').style.display = 'block';
        
        // Reset password fields
        document.getElementById('newPassword').value = '';
        document.getElementById('confirmPassword').value = '';
        document.getElementById('passwordStrengthBar').style.width = '0%';
        document.getElementById('passwordStrengthText').textContent = '';
        document.getElementById('passwordMatchMessage').textContent = '';
        document.getElementById('passwordSubmitBtn').disabled = true;
        
        // Reset requirement indicators
        resetPasswordRequirements();
    }
    
    // Save profile data without closing the modal
    function saveProfileData() {
        // Get form values
        const fullName = document.getElementById('fullName').value;
        const dateOfBirth = document.getElementById('dateOfBirth').value;
        const country = document.getElementById('country').value;
        const workplace = document.getElementById('workplace').value;
        const education = document.getElementById('education').value;
        const bio = document.getElementById('bio').value;
        const email = document.getElementById('email').value;
        
        // Get phone number with country code
        const phoneNumber = phoneInput.getNumber();
        
        // Validate required fields
        if (!fullName || !dateOfBirth || !country || !phoneNumber || !email) {
            alert("Please fill in all required fields");
            return false;
        }
        
        // Update current user profile
        currentUser.profile.fullName = fullName;
        currentUser.profile.dateOfBirth = dateOfBirth;
        currentUser.profile.country = country;
        currentUser.profile.phoneNumber = phoneNumber;
        currentUser.profile.email = email;
        currentUser.profile.workplace = workplace;
        currentUser.profile.education = education;
        currentUser.profile.bio = bio;
        
        // Update user name
        currentUser.name = fullName;
        
        // Update profile picture if changed
        const newAvatar = document.getElementById('profileSetupAvatar').src;
        if (newAvatar !== currentUser.avatar) {
            currentUser.avatar = newAvatar;
        }
        
        return true;
    }
    
    // Check password strength
    function checkPasswordStrength() {
        const password = document.getElementById('newPassword').value;
        const strengthBar = document.getElementById('passwordStrengthBar');
        const strengthText = document.getElementById('passwordStrengthText');
        
        // Reset requirements
        resetPasswordRequirements();
        
        if (password.length === 0) {
            strengthBar.style.width = '0%';
            strengthBar.style.backgroundColor = '#f0f0f0';
            strengthText.textContent = '';
            return;
        }
        
        // Check requirements
        passwordRequirements.length = password.length >= 8;
        passwordRequirements.uppercase = /[A-Z]/.test(password);
        passwordRequirements.lowercase = /[a-z]/.test(password);
        passwordRequirements.number = /[0-9]/.test(password);
        passwordRequirements.special = /[!@#$%^&*()_+\-=\[\]{};':"\\|,.<>\/?]/.test(password);
        
        // Update requirement indicators
        updateRequirementIndicator('reqLength', passwordRequirements.length);
        updateRequirementIndicator('reqUppercase', passwordRequirements.uppercase);
        updateRequirementIndicator('reqLowercase', passwordRequirements.lowercase);
        updateRequirementIndicator('reqNumber', passwordRequirements.number);
        updateRequirementIndicator('reqSpecial', passwordRequirements.special);
        
        // Calculate strength score
        let strength = 0;
        if (passwordRequirements.length) strength += 20;
        if (passwordRequirements.uppercase) strength += 20;
        if (passwordRequirements.lowercase) strength += 20;
        if (passwordRequirements.number) strength += 20;
        if (passwordRequirements.special) strength += 20;
        
        // Update strength bar
        strengthBar.style.width = strength + '%';
        
        // Set color based on strength
        if (strength < 40) {
            strengthBar.style.backgroundColor = '#e74c3c';
            strengthText.textContent = 'Weak';
            strengthText.style.color = '#e74c3c';
        } else if (strength < 80) {
            strengthBar.style.backgroundColor = '#f39c12';
            strengthText.textContent = 'Medium';
            strengthText.style.color = '#f39c12';
        } else {
            strengthBar.style.backgroundColor = '#2ecc71';
            strengthText.textContent = 'Strong';
            strengthText.style.color = '#2ecc71';
        }
        
        // Check if all requirements are met
        const allRequirementsMet = Object.values(passwordRequirements).every(Boolean);
        
        // Enable/disable submit button based on requirements and password match
        const confirmPassword = document.getElementById('confirmPassword').value;
        const passwordsMatch = password === confirmPassword && password.length > 0;
        
        document.getElementById('passwordSubmitBtn').disabled = !(allRequirementsMet && passwordsMatch);
    }
    
    // Check password match
    function checkPasswordMatch() {
        const password = document.getElementById('newPassword').value;
        const confirmPassword = document.getElementById('confirmPassword').value;
        const matchMessage = document.getElementById('passwordMatchMessage');
        
        if (confirmPassword.length === 0) {
            matchMessage.textContent = '';
            return;
        }
        
        if (password === confirmPassword) {
            matchMessage.textContent = 'Passwords match';
            matchMessage.style.color = '#2ecc71';
        } else {
            matchMessage.textContent = 'Passwords do not match';
            matchMessage.style.color = '#e74c3c';
        }
        
        // Check if all requirements are met
        const allRequirementsMet = Object.values(passwordRequirements).every(Boolean);
        
        // Enable/disable submit button based on requirements and password match
        const passwordsMatch = password === confirmPassword && password.length > 0;
        
        document.getElementById('passwordSubmitBtn').disabled = !(allRequirementsMet && passwordsMatch);
    }
    
    // Reset password requirements
    function resetPasswordRequirements() {
        passwordRequirements = {
            length: false,
            uppercase: false,
            lowercase: false,
            number: false,
            special: false
        };
        
        updateRequirementIndicator('reqLength', false);
        updateRequirementIndicator('reqUppercase', false);
        updateRequirementIndicator('reqLowercase', false);
        updateRequirementIndicator('reqNumber', false);
        updateRequirementIndicator('reqSpecial', false);
    }
    
    // Update requirement indicator
    function updateRequirementIndicator(elementId, isValid) {
        const element = document.getElementById(elementId);
        if (element) {
            if (isValid) {
                element.classList.add('valid');
            } else {
                element.classList.remove('valid');
            }
        }
    }
    
    // Save password and proceed to email verification
    function savePassword() {
        const password = document.getElementById('newPassword').value;
        const confirmPassword = document.getElementById('confirmPassword').value;
        
        if (password !== confirmPassword) {
            alert("Passwords do not match");
            return;
        }
        
        // Save password to user profile (in a real app, this would be hashed)
        currentUser.profile.password = password;
        
        // Hide password setup and show email verification
        document.getElementById('passwordSetupPage').style.display = 'none';
        document.getElementById('emailVerificationPage').style.display = 'block';
        
        // Pre-fill email address if available
        if (currentUser.profile.email) {
            document.getElementById('emailAddress').value = currentUser.profile.email;
        }
        
        // Hide success message initially
        document.getElementById('emailSuccessMessage').style.display = 'none';
    }
    
    // Go back to profile setup from password page
    function goBackToProfile() {
        document.getElementById('passwordSetupPage').style.display = 'none';
        document.getElementById('profileSetupModal').style.display = 'flex';
    }
    
    // Go back to password setup from email page
    function goBackToPassword() {
        document.getElementById('emailVerificationPage').style.display = 'none';
        document.getElementById('passwordSetupPage').style.display = 'block';
    }
    
    // Save email and complete profile setup
    function saveEmailAndComplete() {
        const email = document.getElementById('emailAddress').value;
        
        if (!email) {
            alert("Please enter your email address");
            return;
        }
        
        if (!isValidEmail(email)) {
            alert("Please enter a valid email address");
            return;
        }
        
        // Update email in profile
        currentUser.profile.email = email;
        
        // Show success message
        document.getElementById('emailSuccessMessage').style.display = 'block';
        
        // Save complete profile data
        setTimeout(() => {
            // Update profile display
            updateProfileDisplay();
            
            // Save data
            saveDataToStorage();
            
            // Close all modals and pages
            document.getElementById('emailVerificationPage').style.display = 'none';
            document.getElementById('profileSetupModal').style.display = 'none';
            
            // Show profile section
            showProfile();
            
            // Show success message
            alert("Profile setup completed successfully!");
        }, 2000);
    }
    
    // Show password recovery modal
    function showPasswordRecovery() {
        document.getElementById('passwordRecoveryModal').style.display = 'flex';
        
        // Hide all recovery forms initially
        document.getElementById('emailRecoveryForm').classList.remove('active');
        document.getElementById('phoneRecoveryForm').classList.remove('active');
        
        // Initialize phone input if not already done
        if (!recoveryPhoneInput) {
            initPasswordRecovery();
        }
    }
    
    // Close password recovery modal
    function closePasswordRecovery() {
        document.getElementById('passwordRecoveryModal').style.display = 'none';
        
        // Reset forms
        document.getElementById('recoveryEmail').value = '';
        if (recoveryPhoneInput) {
            recoveryPhoneInput.setNumber('');
        }
    }
    
    // Show recovery form based on selection
    function showRecoveryForm(type) {
        // Hide all forms
        document.getElementById('emailRecoveryForm').classList.remove('active');
        document.getElementById('phoneRecoveryForm').classList.remove('active');
        
        // Show selected form
        if (type === 'email') {
            document.getElementById('emailRecoveryForm').classList.add('active');
        } else if (type === 'phone') {
            document.getElementById('phoneRecoveryForm').classList.add('active');
        }
    }
    
    // Send recovery email
    function sendRecoveryEmail() {
        const email = document.getElementById('recoveryEmail').value;
        
        if (!email) {
            alert("Please enter your email address");
            return;
        }
        
        if (!isValidEmail(email)) {
            alert("Please enter a valid email address");
            return;
        }
        
        // In a real app, this would send a recovery email
        // For this demo, we'll just show a success message
        alert(`Recovery link sent to ${email}`);
        closePasswordRecovery();
    }
    
    // Send recovery code via SMS
    function sendRecoveryCode() {
        const phoneNumber = recoveryPhoneInput.getNumber();
        
        if (!phoneNumber) {
            alert("Please enter your phone number");
            return;
        }
        
        // In a real app, this would send an SMS with a verification code
        // For this demo, we'll just show a success message
        alert(`Verification code sent to ${phoneNumber}`);
        closePasswordRecovery();
    }

    // Friends Functions
    function renderFriendsLists() {
        renderFindFriendsList();
        renderYourFriendsList();
    }

    function renderFindFriendsList() {
        const findFriendsList = document.getElementById('findFriendsList');
        if (!findFriendsList) return;
        
        findFriendsList.innerHTML = '';
        
        const nonFriends = allUsers.filter(user => !user.isFriend && user.id !== currentUser.id);
        
        if (nonFriends.length === 0) {
            findFriendsList.innerHTML = `
                <div class="empty-state">
                    <i class="fas fa-user-friends"></i>
                    <h3>No new people to add</h3>
                    <p>You've sent friend requests to everyone or there are no more users to add.</p>
                </div>
            `;
            return;
        }
        
        nonFriends.forEach(user => {
            const friendItem = document.createElement('div');
            friendItem.className = 'friend-item';
            friendItem.innerHTML = `
                <div class="friend-avatar">
                    <img src="${user.avatar}" alt="${user.name}">
                </div>
                <div class="friend-info">
                    <div class="friend-name">${user.name}</div>
                    <div class="friend-mutual">${user.mutualFriends} mutual friends</div>
                </div>
                <div class="friend-actions">
                    ${user.friendRequestSent ? 
                        `<button class="friend-action-btn cancel-request-btn" onclick="cancelFriendRequest(${user.id})">Cancel Request</button>
                         <div class="friend-status">Request Sent</div>` :
                        `<button class="friend-action-btn add-friend-btn" onclick="sendFriendRequest(${user.id})">Add Friend</button>`
                    }
                </div>
            `;
            findFriendsList.appendChild(friendItem);
        });
    }

    function renderYourFriendsList() {
        const yourFriendsList = document.getElementById('yourFriendsList');
        if (!yourFriendsList) return;
        
        yourFriendsList.innerHTML = '';
        
        const friends = allUsers.filter(user => user.isFriend && user.id !== currentUser.id);
        
        if (friends.length === 0) {
            yourFriendsList.innerHTML = `
                <div class="empty-state">
                    <i class="fas fa-user-friends"></i>
                    <h3>No friends yet</h3>
                    <p>Start adding friends to see them here.</p>
                    <button class="btn btn-primary" onclick="switchFriendsTab('find-friends')">Find Friends</button>
                </div>
            `;
            return;
        }
        
        friends.forEach(user => {
            const friendItem = document.createElement('div');
            friendItem.className = 'friend-item';
            friendItem.innerHTML = `
                <div class="friend-avatar">
                    <img src="${user.avatar}" alt="${user.name}">
                </div>
                <div class="friend-info">
                    <div class="friend-name">${user.name}</div>
                    <div class="friend-mutual">${user.mutualFriends} mutual friends</div>
                </div>
                <div class="friend-actions">
                    <button class="friend-action-btn message-btn" onclick="messageFriend(${user.id})">Message</button>
                    <button class="friend-action-btn cancel-request-btn" onclick="removeFriend(${user.id})">Remove</button>
                </div>
            `;
            yourFriendsList.appendChild(friendItem);
        });
    }

    function switchFriendsTab(tab) {
        // Update active tab
        document.querySelectorAll('.friends-tab').forEach(tabElement => {
            tabElement.classList.remove('active');
        });
        
        if (tab === 'find-friends') {
            document.querySelectorAll('.friends-tab')[0].classList.add('active');
            document.getElementById('findFriendsList').style.display = 'flex';
            document.getElementById('yourFriendsList').style.display = 'none';
        } else {
            document.querySelectorAll('.friends-tab')[1].classList.add('active');
            document.getElementById('findFriendsList').style.display = 'none';
            document.getElementById('yourFriendsList').style.display = 'flex';
        }
    }

    function sendFriendRequest(userId) {
        const user = allUsers.find(u => u.id === userId);
        if (user) {
            user.friendRequestSent = true;
            renderFindFriendsList();
            
            // Save data
            saveDataToStorage();
            
            // Show confirmation
            alert(`Friend request sent to ${user.name}`);
        }
    }

    function cancelFriendRequest(userId) {
        const user = allUsers.find(u => u.id === userId);
        if (user) {
            user.friendRequestSent = false;
            renderFindFriendsList();
            
            // Save data
            saveDataToStorage();
            
            // Show confirmation
            alert(`Friend request to ${user.name} has been canceled`);
        }
    }

    function removeFriend(userId) {
        if (confirm("Are you sure you want to remove this friend?")) {
            const user = allUsers.find(u => u.id === userId);
            if (user) {
                user.isFriend = false;
                user.friendRequestSent = false;
                renderYourFriendsList();
                renderFindFriendsList();
                
                // Save data
                saveDataToStorage();
                
                // Show confirmation
                alert(`${user.name} has been removed from your friends list`);
            }
        }
    }

    // Messaging Functions
    function messageFriend(userId) {
        currentConversationUserId = userId;
        const user = allUsers.find(u => u.id === userId);
        
        if (user) {
            // Update messaging header
            document.getElementById('messagingAvatar').src = user.avatar;
            document.getElementById('messagingUserName').textContent = user.name;
            
            // Render messages
            renderMessages();
            
            // Show messaging container
            document.getElementById('messagingContainer').style.display = 'flex';
            
            // Hide all other sections
            hideAllSections();
            
            // Scroll to bottom of messages
            setTimeout(() => {
                const messagingBody = document.getElementById('messagingBody');
                messagingBody.scrollTop = messagingBody.scrollHeight;
            }, 100);
        }
    }

    function renderMessages() {
        const messagingBody = document.getElementById('messagingBody');
        if (!messagingBody) return;
        
        messagingBody.innerHTML = '';
        
        if (currentConversationUserId && conversations[currentConversationUserId]) {
            const messages = conversations[currentConversationUserId];
            
            // Sort messages by timestamp (oldest first)
            const sortedMessages = [...messages].sort((a, b) => new Date(a.timestamp) - new Date(b.timestamp));
            
            sortedMessages.forEach(message => {
                const isCurrentUser = message.senderId === currentUser.id;
                const isLiked = message.likes && message.likes.includes(currentUser.id);
                
                const messageElement = document.createElement('div');
                messageElement.className = `message ${isCurrentUser ? 'sent' : 'received'}`;
                messageElement.innerHTML = `
                    <div class="message-text">${message.text}</div>
                    ${message.likes && message.likes.length > 0 ? `
                        <div class="comment-likes-count">
                            <i class="fas fa-heart"></i>
                            <span>${message.likes.length}</span>
                        </div>
                    ` : ''}
                    <div class="message-actions">
                        <span class="message-time">${formatTimeAgo(message.timestamp)}</span>
                        <button class="message-like-btn ${isLiked ? 'liked' : ''}" onclick="toggleMessageLike('${message.id}')">
                            <i class="fas fa-heart"></i>
                            <span>${isLiked ? 'Liked' : 'Like'}</span>
                        </button>
                    </div>
                `;
                messagingBody.appendChild(messageElement);
            });
            
            // Scroll to bottom
            messagingBody.scrollTop = messagingBody.scrollHeight;
        }
    }

    // Function to toggle message like
    function toggleMessageLike(messageId) {
        if (currentConversationUserId && conversations[currentConversationUserId]) {
            const messages = conversations[currentConversationUserId];
            const message = messages.find(m => m.id === messageId);
            
            if (message) {
                if (!message.likes) message.likes = [];
                
                const likedIndex = message.likes.indexOf(currentUser.id);
                
                if (likedIndex === -1) {
                    // Like the message
                    message.likes.push(currentUser.id);
                    
                    // Add notification if the sender is not current user
                    if (message.senderId !== currentUser.id) {
                        const newNotification = {
                            id: notifications.length + 1,
                            type: "like",
                            title: "Message Liked",
                            message: `${currentUser.name} liked your message`,
                            timestamp: new Date().toISOString(),
                            read: false,
                            data: { userId: currentUser.id, messageId: messageId }
                        };
                        addNotification(newNotification);
                        showPushNotification(newNotification);
                    }
                } else {
                    // Unlike the message
                    message.likes.splice(likedIndex, 1);
                }
                
                // Re-render messages
                renderMessages();
                
                // Save data
                saveDataToStorage();
            }
        }
    }

    function sendMessage() {
        const messageInput = document.getElementById('messageInput');
        const text = messageInput.value.trim();
        
        if (text && currentConversationUserId) {
            // Create new message
            const newMessage = {
                id: Date.now().toString(),
                senderId: currentUser.id,
                text: text,
                timestamp: new Date().toISOString(),
                likes: []
            };
            
            // Add message to conversation
            if (!conversations[currentConversationUserId]) {
                conversations[currentConversationUserId] = [];
            }
            conversations[currentConversationUserId].push(newMessage);
            
            // Clear input
            messageInput.value = '';
            
            // Re-render messages
            renderMessages();
            
            // Save data
            saveDataToStorage();
            
            // Add notification for the receiver
            const user = allUsers.find(u => u.id === currentConversationUserId);
            if (user) {
                const newNotification = {
                    id: notifications.length + 1,
                    type: "message",
                    title: "New Message",
                    message: `${currentUser.name} sent you a message`,
                    timestamp: new Date().toISOString(),
                    read: false,
                    data: { userId: currentUser.id, messageId: newMessage.id }
                };
                addNotification(newNotification);
                showPushNotification(newNotification);
            }
        }
    }

    function closeMessaging() {
        document.getElementById('messagingContainer').style.display = 'none';
        showFriends();
    }

    // Notification System Functions
    function renderNotifications() {
        const notificationsList = document.getElementById('notificationsList');
        if (!notificationsList) return;
        
        notificationsList.innerHTML = '';
        
        if (notifications.length === 0) {
            notificationsList.innerHTML = `
                <div class="notifications-empty">
                    <i class="fas fa-bell-slash"></i>
                    <h3>No notifications</h3>
                    <p>You're all caught up!</p>
                </div>
            `;
            return;
        }
        
        // Sort notifications by timestamp (newest first)
        const sortedNotifications = [...notifications].sort((a, b) => new Date(b.timestamp) - new Date(a.timestamp));
        
        sortedNotifications.forEach(notification => {
            const notificationItem = document.createElement('div');
            notificationItem.className = `notification-item ${notification.read ? '' : 'unread'}`;
            notificationItem.onclick = () => handleNotificationClick(notification);
            notificationItem.innerHTML = `
                <div class="notification-icon ${notification.type}">
                    <i class="${getNotificationIcon(notification.type)}"></i>
                </div>
                <div class="notification-content">
                    <div class="notification-text">${notification.message}</div>
                    <div class="notification-time">${formatTimeAgo(notification.timestamp)}</div>
                </div>
                ${notification.read ? '' : '<div class="notification-dot"></div>'}
            `;
            notificationsList.appendChild(notificationItem);
        });
    }

    function getNotificationIcon(type) {
        switch(type) {
            case 'like': return 'fas fa-heart';
            case 'comment': return 'fas fa-comment';
            case 'friend': return 'fas fa-user-plus';
            case 'message': return 'fas fa-envelope';
            case 'system': return 'fas fa-info-circle';
            default: return 'fas fa-bell';
        }
    }

    function handleNotificationClick(notification) {
        // Mark as read
        markNotificationAsRead(notification.id);
        
        // Handle different notification types
        switch(notification.type) {
            case 'like':
            case 'comment':
                // Navigate to the post
                showHome();
                // In a real app, you would scroll to the specific post
                break;
            case 'friend':
                // Navigate to friends section
                showFriends();
                break;
            case 'message':
                // Navigate to messages
                if (notification.data && notification.data.userId) {
                    messageFriend(notification.data.userId);
                }
                break;
            case 'system':
                // Show system notification details
                alert(`System Notification: ${notification.message}`);
                break;
        }
        
        // Close notifications panel
        document.getElementById('notificationsPanel').style.display = 'none';
    }

    function markNotificationAsRead(notificationId) {
        const notification = notifications.find(n => n.id === notificationId);
        if (notification && !notification.read) {
            notification.read = true;
            renderNotifications();
            updateNotificationBadge();
            saveDataToStorage();
        }
    }

    function markAllAsRead() {
        notifications.forEach(notification => {
            notification.read = true;
        });
        renderNotifications();
        updateNotificationBadge();
        saveDataToStorage();
    }

    function updateNotificationBadge() {
        const unreadCount = notifications.filter(n => !n.read).length;
        const badge = document.getElementById('notificationBadge');
        
        if (badge) {
            if (unreadCount > 0) {
                badge.textContent = unreadCount > 99 ? '99+' : unreadCount;
                badge.style.display = 'flex';
            } else {
                badge.style.display = 'none';
            }
        }
    }

    function toggleNotifications() {
        const panel = document.getElementById('notificationsPanel');
        if (panel.style.display === 'flex') {
            panel.style.display = 'none';
        } else {
            panel.style.display = 'flex';
            // Hide settings if visible
            document.getElementById('notificationSettings').style.display = 'none';
        }
    }

    function showNotificationSettings() {
        document.getElementById('notificationSettings').style.display = 'block';
        
        // Set current settings
        document.getElementById('pushNotificationsToggle').checked = notificationSettings.pushNotifications;
        document.getElementById('soundToggle').checked = notificationSettings.sound;
        document.getElementById('emailNotificationsToggle').checked = notificationSettings.emailNotifications;
    }

    function saveNotificationSettings() {
        notificationSettings.pushNotifications = document.getElementById('pushNotificationsToggle').checked;
        notificationSettings.sound = document.getElementById('soundToggle').checked;
        notificationSettings.emailNotifications = document.getElementById('emailNotificationsToggle').checked;
        
        // Hide settings
        document.getElementById('notificationSettings').style.display = 'none';
        
        // Save to storage
        saveDataToStorage();
        
        // Show confirmation
        alert('Notification settings saved!');
    }

    // Push Notification Functions
    function showPushNotification(notification) {
        if (!notificationSettings.pushNotifications) return;
        
        const pushNotification = document.getElementById('pushNotification');
        const title = document.getElementById('pushNotificationTitle');
        const body = document.getElementById('pushNotificationBody');
        const actionBtn = document.getElementById('pushNotificationAction');
        
        // Set notification content
        title.textContent = notification.title;
        body.textContent = notification.message;
        
        // Set action button behavior
        actionBtn.onclick = function() {
            handleNotificationClick(notification);
            closePushNotification();
        };
        
        // Show notification
        pushNotification.style.display = 'block';
        
        // Auto hide after 5 seconds
        if (pushNotificationTimeout) {
            clearTimeout(pushNotificationTimeout);
        }
        pushNotificationTimeout = setTimeout(() => {
            closePushNotification();
        }, 5000);
        
        // Play sound if enabled
        if (notificationSettings.sound) {
            playNotificationSound();
        }
    }

    function closePushNotification() {
        const pushNotification = document.getElementById('pushNotification');
        pushNotification.style.animation = 'slideOutRight 0.3s ease-out';
        
        setTimeout(() => {
            pushNotification.style.display = 'none';
            pushNotification.style.animation = 'slideInRight 0.3s ease-out';
        }, 300);
        
        if (pushNotificationTimeout) {
            clearTimeout(pushNotificationTimeout);
        }
    }

    function playNotificationSound() {
        // In a real app, this would play a sound file
        // For this demo, we'll just log to console
        console.log("Playing notification sound");
    }

    function addNotification(notification) {
        notifications.unshift(notification);
        renderNotifications();
        updateNotificationBadge();
        saveDataToStorage();
    }

    function startNotificationSimulation() {
        // Check for new notifications every 30 seconds
        notificationInterval = setInterval(() => {
            checkForNewNotifications();
        }, 30000);
        
        // Also check immediately
        checkForNewNotifications();
    }

    function checkForNewNotifications() {
        console.log("Checking for new notifications...");
    }

    // Help & Support Functions
    function showHelpSupport() {
        hideAllSections();
        document.getElementById('helpSupportSection').style.display = 'block';
    }

    function connectWithWhatsApp() {
        // Open WhatsApp Business link
        window.open('https://chat.whatsapp.com/Lwfe2Dx4BiuDoXjQYmYhP8?mode=ems_copy_t');
    }

    function callSupport() {
        // Initiate a phone call to the support number
        window.location.href = 'tel:+255776290901';
    }

    function toggleFAQ(element) {
        const faqItem = element.parentElement;
        faqItem.classList.toggle('active');
    }

    // Settings Functions
    function showSettings() {
        hideAllSections();
        document.getElementById('settingsSection').style.display = 'block';
    }

    function goBackFromSettings() {
        document.getElementById('settingsSection').style.display = 'none';
        showProfile();
    }

    // Toggle dark mode
    function toggleDarkMode() {
        darkModeEnabled = !darkModeEnabled;
        
        if (darkModeEnabled) {
            document.body.classList.add('dark-mode');
        } else {
            document.body.classList.remove('dark-mode');
        }
        
        // Save settings
        saveSettingsToStorage();
    }

    // Show language selection modal
    function showLanguageSelection() {
        document.getElementById('languageModal').style.display = 'flex';
    }

    // Close language selection modal
    function closeLanguageSelection() {
        document.getElementById('languageModal').style.display = 'none';
    }

    // Select language
    function selectLanguage(language) {
        currentLanguage = language;
        
        // Update UI
        document.getElementById('currentLanguage').textContent = getLanguageName(language);
        updateLanguageCheckmarks();
        
        // Save settings
        saveSettingsToStorage();
        
        // Show confirmation (in a real app, you would reload the content in the selected language)
        showToast(`Language changed to ${getLanguageName(language)}`);
    }

    // Show ads creation modal
    function showAdsCreation() {
        document.getElementById('adsCreationModal').style.display = 'flex';
    }

    // Close ads creation modal
    function closeAdsCreation() {
        document.getElementById('adsCreationModal').style.display = 'none';
        
        // Reset form
        document.getElementById('adsTitle').value = '';
        document.getElementById('adsDescription').value = '';
        document.getElementById('adsTarget').value = 'all';
        document.getElementById('adsBudget').value = '';
        document.getElementById('adsDuration').value = '';
        document.getElementById('adsPreview').innerHTML = '<i class="fas fa-image" style="font-size: 48px; color: #ddd;"></i>';
    }

    // Handle ads image upload
    function handleAdsImageUpload(input) {
        if (input.files && input.files[0]) {
            const reader = new FileReader();
            
            reader.onload = function(e) {
                const preview = document.getElementById('adsPreview');
                preview.innerHTML = `<img src="${e.target.result}" alt="Ad Preview">`;
            };
            
            reader.readAsDataURL(input.files[0]);
        }
    }

    // Create ad
    function createAd() {
        const title = document.getElementById('adsTitle').value;
        const description = document.getElementById('adsDescription').value;
        const target = document.getElementById('adsTarget').value;
        const budget = document.getElementById('adsBudget').value;
        const duration = document.getElementById('adsDuration').value;
        const imageInput = document.getElementById('adsImageInput');
        
        if (!title || !description || !budget || !duration || !imageInput.files.length) {
            alert("Please fill in all fields and upload an image");
            return;
        }
        
        // Create ad object
        const adImage = imageInput.files[0];
        const imageUrl = URL.createObjectURL(adImage);
        
        pendingAd = {
            id: Date.now(),
            title,
            description,
            target,
            budget: parseFloat(budget),
            duration: parseInt(duration),
            image: imageUrl,
            timestamp: new Date().toISOString(),
            status: 'pending'
        };
        
        // Generate payment reference
        adsPaymentReference = generateAdsPaymentReference();
        
        // Calculate total amount
        const totalAmount = pendingAd.duration * 1000; // TZS 1000 per day
        
        // Update payment page with ad details
        document.getElementById('adsPaymentTitle').textContent = pendingAd.title;
        document.getElementById('adsPaymentDuration').textContent = `${pendingAd.duration} day(s)`;
        document.getElementById('adsPaymentTotal').textContent = `TZS ${totalAmount.toLocaleString()}`;
        document.getElementById('adsPaymentReference').textContent = adsPaymentReference;
        
        // Reset transaction ID and status
        document.getElementById('adsTransactionId').value = '';
        document.getElementById('adsPaymentProcessing').style.display = 'none';
        document.getElementById('adsPaymentSuccess').style.display = 'none';
        document.getElementById('adsPaymentError').style.display = 'none';
        
        // Hide ads creation modal and show payment page
        document.getElementById('adsCreationModal').style.display = 'none';
        document.getElementById('adsPaymentPage').style.display = 'block';
    }
    
    // Generate unique payment reference for ads
    function generateAdsPaymentReference() {
        const timestamp = new Date().getTime();
        const random = Math.floor(Math.random() * 1000);
        return `ADS-${timestamp}-${random}`;
    }
    
    // Verify ads payment
    function verifyAdsPayment() {
        const transactionId = document.getElementById('adsTransactionId').value.trim();
        
        if (!transactionId) {
            alert("Please enter your transaction ID");
            return;
        }
        
        // Show processing status
        document.getElementById('adsPaymentProcessing').style.display = 'block';
        document.getElementById('adsPaymentSuccess').style.display = 'none';
        document.getElementById('adsPaymentError').style.display = 'none';
        
        // Simulate payment verification (in a real app, this would call your backend)
        setTimeout(() => {
            // For demo purposes, we'll accept any transaction ID that's not empty
            // In a real app, you would verify with the payment gateway
            if (transactionId.length > 0) {
                // Payment successful
                document.getElementById('adsPaymentProcessing').style.display = 'none';
                document.getElementById('adsPaymentSuccess').style.display = 'block';
                
                // Add the pending ad to the advertisements array
                if (pendingAd) {
                    advertisements.push(pendingAd);
                    renderAdBanner();
                    
                    // Save data
                    saveDataToStorage();
                    
                    // Show success message and redirect
                    setTimeout(() => {
                        document.getElementById('adsPaymentPage').style.display = 'none';
                        showSettings();
                        alert("Ad published successfully! Thank you for your payment.");
                        
                        // Reset pending ad
                        pendingAd = null;
                    }, 1500);
                }
            } else {
                // Payment failed
                document.getElementById('adsPaymentProcessing').style.display = 'none';
                document.getElementById('adsPaymentError').style.display = 'block';
            }
        }, 2000);
    }
    
    // Go back to ad creation from payment page
    function goBackToAdsCreation() {
        document.getElementById('adsPaymentPage').style.display = 'none';
        document.getElementById('adsCreationModal').style.display = 'flex';
    }

    // Show privacy settings modal
    function showPrivacySettings(type) {
        const modal = document.getElementById('privacyModal');
        const title = document.getElementById('privacyModalTitle');
        const optionTitle = document.getElementById('privacyOptionTitle');
        const optionDescription = document.getElementById('privacyOptionDescription');
        const setting = document.getElementById('privacySetting');
        
        if (type === 'profile') {
            title.textContent = 'Profile Privacy';
            optionTitle.textContent = 'Profile Visibility';
            optionDescription.textContent = 'Control who can see your profile information';
            setting.value = profileVisibility;
        } else if (type === 'posts') {
            title.textContent = 'Post Privacy';
            optionTitle.textContent = 'Post Visibility';
            optionDescription.textContent = 'Control who can see your posts';
            setting.value = postVisibility;
        }
        
        // Store the current setting type
        modal.dataset.settingType = type;
        
        // Show modal
        modal.style.display = 'flex';
    }

    // Close privacy settings modal
    function closePrivacySettings() {
        document.getElementById('privacyModal').style.display = 'none';
    }

    // Save privacy settings
    function savePrivacySettings() {
        const modal = document.getElementById('privacyModal');
        const type = modal.dataset.settingType;
        const value = document.getElementById('privacySetting').value;
        
        if (type === 'profile') {
            profileVisibility = value;
        } else if (type === 'posts') {
            postVisibility = value;
        }
        
        // Save settings
        saveSettingsToStorage();
        
        // Show confirmation
        showToast("Privacy settings updated successfully!");
        
        // Close modal
        closePrivacySettings();
    }

    // Clear cache
    function clearCache() {
        if (confirm("Are you sure you want to clear the cache? This will free up storage space but may slow down the app temporarily.")) {
            // In a real app, this would clear cached data
            // For this demo, we'll just show a success message
            showToast("Cache cleared successfully!");
        }
    }

    // Change password
    function changePassword() {
        // In a real app, this would open a password change form
        // For this demo, we'll redirect to the password setup page
        showPasswordSetup();
    }

    function logout() {
        if (confirm("Are you sure you want to logout?")) {
            alert("You have been logged out successfully!");
            // In a real app, this would redirect to login page
            // For demo, just reload the page
            location.reload();
        }
    }

    // Share Functions
    function sharePost(postId) {
        currentSharePostId = postId;
        currentSharePost = posts.find(p => p.id === postId);
        
        if (currentSharePost) {
            // Update share count
            currentSharePost.shares += 1;
            renderPosts();
            
            // Show share modal
            showShareModal();
        }
    }

    function showShareModal() {
        if (!currentSharePost) return;
        
        const modal = document.getElementById('shareModal');
        const preview = document.getElementById('sharePostPreview');
        
        // Create post preview
        preview.innerHTML = `
            <div class="share-preview-content">
                <div class="share-preview-user">
                    <div class="share-preview-avatar">
                        <img src="${currentSharePost.user.avatar}" alt="${currentSharePost.user.name}">
                    </div>
                    <div class="share-preview-info">
                        <div class="share-preview-name">${currentSharePost.user.name}</div>
                        <div class="share-preview-time">${formatTimeAgo(currentSharePost.timestamp)}</div>
                    </div>
                </div>
                <div class="share-preview-caption">${currentSharePost.caption}</div>
                ${currentSharePost.media.url ? `
                    ${currentSharePost.media.type === 'image' 
                        ? `<img src="${currentSharePost.media.url}" alt="Post media" class="share-preview-media">`
                        : `<video src="${currentSharePost.media.url}" class="share-preview-media" controls></video>`}
                ` : ''}
            </div>
        `;
        
        // Clear share message
        document.getElementById('shareMessage').value = '';
        
        // Show modal
        modal.style.display = 'flex';
    }

    function closeShareModal() {
        document.getElementById('shareModal').style.display = 'none';
        currentSharePostId = null;
        currentSharePost = null;
    }

    // Individual sharing functions
    function shareViaBluetooth() {
        if (!currentSharePost) return;
        alert("This would share via Bluetooth. Note: Web Bluetooth API requires HTTPS and user permission.");
        simulateShare("Bluetooth");
    }

    function shareViaFacebook() {
        if (!currentSharePost) return;
        
        const shareMessage = document.getElementById('shareMessage').value;
        const shareText = shareMessage || `${currentSharePost.user.name}: ${currentSharePost.caption}`;
        const shareUrl = `https://your-app.com/post/${currentSharePost.id}`;
        
        // Facebook share URL
        const facebookShareUrl = `https://www.facebook.com/sharer/sharer.php?u=${encodeURIComponent(shareUrl)}"e=${encodeURIComponent(shareText)}`;
        
        window.open(facebookShareUrl, '_blank', 'width=600,height=400');
        simulateShare("Facebook");
    }

    function shareViaXender() {
        if (!currentSharePost) return;
        alert("Xender is a file-sharing app. To share via Xender, the post content would be converted to a file and shared via local network.");
        simulateShare("Xender");
    }

    function shareViaTikTok() {
        if (!currentSharePost) return;
        alert("To share on TikTok:\n1. Save the post image/video\n2. Open TikTok app\n3. Create new post\n4. Upload the saved media");
        simulateShare("TikTok");
    }

    function shareViaInstagram() {
        if (!currentSharePost) return;
        
        if (currentSharePost.media.type === 'image') {
            alert("To share on Instagram:\n1. Save the post image\n2. Open Instagram app\n3. Create new post\n4. Select the saved image\n5. Add caption and share");
        } else {
            alert("Instagram Reels/Stories would be the best option for video content.");
        }
        simulateShare("Instagram");
    }

    function shareViaYouTube() {
        if (!currentSharePost) return;
        
        const shareMessage = document.getElementById('shareMessage').value;
        const shareText = shareMessage || `${currentSharePost.user.name}: ${currentSharePost.caption}`;
        
        // Basic video URL
        let shareUrl = `https://www.youtube.com/watch?v=YOUR_VIDEO_ID_HERE`;
        
        // Optional: Add a timestamp
        const startTime = "1m30s";
        shareUrl += `&t=${startTime}`;
        
        // Combine text and URL
        const fullShareText = `${shareText} ${shareUrl}`;
                    
        alert(`https://youtube.com:\n${fullShareText}`);
        simulateShare("YouTube");
    }

    function shareViaWhatsApp() {
        if (!currentSharePost) return;
        
        const shareMessage = document.getElementById('shareMessage').value;
        const shareText = shareMessage || `${currentSharePost.user.name}: ${currentSharePost.caption}`;
        const shareUrl = `https://your-app.com/post/${currentSharePost.id}`;
        
        // WhatsApp share URL
        const whatsappShareUrl = `https://wa.me/?text=${encodeURIComponent(shareText + ' ' + shareUrl)}`;
        
        window.open(whatsappShareUrl, '_blank', 'width=600,height=400');
        simulateShare("WhatsApp");
    }

    function shareViaTelegram() {
        if (!currentSharePost) return;
        
        const shareMessage = document.getElementById('shareMessage').value;
        const shareText = shareMessage || `${currentSharePost.user.name}: ${currentSharePost.caption}`;
        const shareUrl = `https://your-app.com/post/${currentSharePost.id}`;
        
        // Telegram share URL
        const telegramShareUrl = `https://t.me/share/url?url=${encodeURIComponent(shareUrl)}&text=${encodeURIComponent(shareText)}`;
        
        window.open(telegramShareUrl, '_blank', 'width=600,height=400');
        simulateShare("Telegram");
    }

    function shareViaTwitter() {
        if (!currentSharePost) return;
        
        const shareMessage = document.getElementById('shareMessage').value;
        const shareText = shareMessage || `${currentSharePost.user.name}: ${currentSharePost.caption}`;
        const shareUrl = `https://your-app.com/post/${currentSharePost.id}`;
        
        // Twitter share URL
        const twitterShareUrl = `https://twitter.com/intent/tweet?text=${encodeURIComponent(shareText)}&url=${encodeURIComponent(shareUrl)}`;
        
        window.open(twitterShareUrl, '_blank', 'width=600,height=400');
        simulateShare("Twitter");
    }

    function shareViaEmail() {
        if (!currentSharePost) return;
        
        const shareMessage = document.getElementById('shareMessage').value;
        const subject = `Check out this post from ${currentSharePost.user.name}`;
        const body = `${shareMessage || currentSharePost.caption}\n\nView post: https://your-app.com/post/${currentSharePost.id}`;
        
        // Mailto link
        const mailtoLink = `mailto:?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;
        
        window.location.href = mailtoLink;
        simulateShare("Email");
    }

    function shareViaSMS() {
        if (!currentSharePost) return;
        
        const shareMessage = document.getElementById('shareMessage').value;
        const text = `${shareMessage || currentSharePost.caption}\nView post: https://your-app.com/post/${currentSharePost.id}`;
        
        // SMS link
        const smsLink = `sms:?body=${encodeURIComponent(text)}`;
        
        window.location.href = smsLink;
        simulateShare("SMS");
    }

    function shareViaLink() {
        if (!currentSharePost) return;
        
        const shareUrl = `https://your-app.com/post/${currentSharePost.id}`;
        
        // Copy to clipboard
        navigator.clipboard.writeText(shareUrl).then(() => {
            alert("Link copied to clipboard!");
            simulateShare("Link");
        }).catch(err => {
            console.error('Failed to copy link: ', err);
            alert("Failed to copy link. Please try again.");
        });
    }

    function shareViaSystem() {
        if (!currentSharePost) return;
        
        const shareMessage = document.getElementById('shareMessage').value;
        const shareText = shareMessage || `${currentSharePost.user.name}: ${currentSharePost.caption}`;
        const shareUrl = `https://your-app.com/post/${currentSharePost.id}`;
        
        // Check if Web Share API is available
        if (navigator.share) {
            navigator.share({
                title: `Post by ${currentSharePost.user.name}`,
                text: shareText,
                url: shareUrl,
            })
            .then(() => {
                console.log('Share successful');
                simulateShare("System Share");
            })
            .catch((error) => {
                console.log('Error sharing:', error);
                alert("System sharing failed. Please try another method.");
            });
        } else {
            // Fallback: Show all options
            alert("System sharing not supported. Please use one of the other options.");
        }
    }

    function simulateShare(platform) {
        // Show success message
        const message = document.getElementById('shareMessage').value;
        alert(`Shared to ${platform} successfully!${message ? '\n\nMessage: ' + message : ''}`);
        
        // Add earnings for sharing (if it's your own post)
        if (currentSharePost && currentSharePost.userId === currentUser.id) {
            currentSharePost.earnings += 0.1;
            currentUser.earnings.total += 0.1;
            currentUser.earnings.available += 0.1;
            updateEarnings();
            
            // Add notification
            const newNotification = {
                id: notifications.length + 1,
                type: "system",
                title: "Post Shared",
                message: `Your post was shared via ${platform}`,
                timestamp: new Date().toISOString(),
                read: false,
                data: { postId: currentSharePostId, platform: platform }
            };
            addNotification(newNotification);
        }
        
        // Close modal
        closeShareModal();
        
        // Save data
        saveDataToStorage();
    }

    // NEW: Function to render shop profile in products section
    function renderShopProfile() {
        const productsSection = document.getElementById('productsSection');
        if (!productsSection) return;
        
        // Check if shop profile section already exists
        let shopProfileSection = productsSection.querySelector('.shop-profile-section');
        
        if (!shopProfileSection) {
            // Create shop profile section
            shopProfileSection = document.createElement('div');
            shopProfileSection.className = 'shop-profile-section';
            shopProfileSection.onclick = showShopProfilePage;
            
            // Insert shop profile at the beginning of products section
            productsSection.insertBefore(shopProfileSection, productsSection.firstChild);
        }
        
        // Update shop profile content
        shopProfileSection.innerHTML = `
            <div class="shop-profile-header">
                <div class="shop-profile-avatar">
                    <img src="${currentUser.shop.shopAvatar}" alt="Shop Avatar">
                </div>
                <div class="shop-profile-info">
                    <div class="shop-profile-name">${currentUser.shop.shopName || "My Shop"}</div>
                    <div class="shop-profile-type">${currentUser.shop.shopType}</div>
                </div>
            </div>
            <div class="shop-profile-stats">
                <div class="shop-profile-stat">
                    <div class="shop-profile-stat-value">${currentUser.shop.products.length}</div>
                    <div class="shop-profile-stat-label">Products</div>
                </div>
                <div class="shop-profile-stat">
                    <div class="shop-profile-stat-value">${getShopRating()}</div>
                    <div class="shop-profile-stat-label">Rating</div>
                </div>
                <div class="shop-profile-stat">
                    <div class="shop-profile-stat-value">${getShopSales()}</div>
                    <div class="shop-profile-stat-label">Sales</div>
                </div>
            </div>
        `;
    }

    // NEW: Function to get shop rating
    function getShopRating() {
        return "4.5★"; // In a real app, this would be calculated from reviews
    }

    // NEW: Function to get shop sales
    function getShopSales() {
        return "0"; // In a real app, this would be calculated from sales data
    }

    // NEW: Function to show shop profile page
    function showShopProfilePage() {
        // Hide all sections
        hideAllSections();
        
        // Show shop profile page
        document.getElementById('shopProfilePage').style.display = 'block';
        
        // Update shop profile page content
        updateShopProfilePage();
    }

    // NEW: Function to update shop profile page
    function updateShopProfilePage() {
        // Set shop profile avatar
        document.getElementById('shopProfileAvatar').src = currentUser.shop.shopAvatar;
        
        // Set shop name (use company name from first product if available)
        const shopName = currentUser.shop.shopName || 
                       (userProducts.length > 0 ? userProducts[0].companyName : "My Shop");
        document.getElementById('shopProfileName').textContent = shopName;
        
        // Set shop owner name
        document.getElementById('shopProfileOwner').textContent = currentUser.name;
        
        // Set contact info
        const contact = currentUser.shop.contact || 
                      (userProducts.length > 0 ? userProducts[0].contactInfo : currentUser.profile.phoneNumber);
        document.getElementById('shopProfileContact').textContent = contact || "Not provided";
        
        // Set location
        const location = currentUser.shop.location || currentUser.profile.country;
        document.getElementById('shopProfileLocation').textContent = location || "Not specified";
        
        // Render shop products
        renderShopProducts();
    }

    // NEW: Function to render shop products
    
    
    
    
    
    
    
    
    
    
    function renderShopProducts() {
    const shopProductsGrid = document.getElementById('shopProductsGrid');
    if (!shopProductsGrid) return;
    
    shopProductsGrid.innerHTML = '';
    
    // Filter products by current user
    const userProductsList = userProducts.filter(product => product.userId === currentUser.id);
    
    if (userProductsList.length === 0) {
        shopProductsGrid.innerHTML = `
            <div style="grid-column: 1 / -1; text-align: center; padding: 20px;">
                <i class="fas fa-box-open" style="font-size: 48px; color: #ddd; margin-bottom: 10px;"></i>
                <p>No products listed yet</p>
                <button class="btn btn-primary" onclick="showProductListing()" style="margin-top: 10px;">
                    Add Products
                </button>
            </div>
        `;
        return;
    }
    
    // Display user's products
    userProductsList.forEach(product => {
        const productElement = document.createElement('div');
        productElement.className = 'shop-product-item';
        productElement.innerHTML = `
            <img src="${product.images[0]}" alt="${product.productName}" class="shop-product-image">
            <div class="product-menu">
                <button class="product-menu-btn" onclick="toggleProductMenu(this, ${product.id})">
                    <i class="fas fa-ellipsis-v"></i>
                </button>
                <div class="product-menu-dropdown" id="product-menu-${product.id}">
                    <div class="product-menu-option edit" onclick="editUserProduct(${product.id})">
                        <i class="fas fa-edit"></i>
                        <span>Edit</span>
                    </div>
                    <div class="product-menu-option delete" onclick="deleteUserProduct(${product.id})">
                        <i class="fas fa-trash"></i>
                        <span>Delete</span>
                    </div>
                </div>
            </div>
            <div class="shop-product-info">
                <div class="shop-product-name">${product.productName}</div>
                <div class="shop-product-price">TZS ${product.price.toLocaleString()}</div>
            </div>
        `;
        productElement.onclick = (e) => {
            // Don't trigger product details if clicking on menu
            if (!e.target.closest('.product-menu')) {
                showUserProductDetails(product);
            }
        };
        shopProductsGrid.appendChild(productElement);
    });
}





    // NEW: Function to go back from shop profile
    function goBackFromShopProfile() {
        document.getElementById('shopProfilePage').style.display = 'none';
        showProducts();
    }

    // NEW: Function to update shop profile
    function updateShopProfile(companyName, contact) {
        // Update shop profile data
        currentUser.shop.hasShop = true;
        currentUser.shop.shopName = companyName;
        currentUser.shop.contact = contact;
        currentUser.shop.location = currentUser.profile.country;
        currentUser.shop.shopAvatar = currentUser.avatar; // Use user's profile picture as shop avatar
        
        // Add product to shop products
        const shopProduct = {
            id: Date.now(),
            name: document.getElementById('productName').value,
            price: parseInt(document.getElementById('productPrice').value),
            image: document.getElementById('productImages').files[0] ? 
                   URL.createObjectURL(document.getElementById('productImages').files[0]) : '',
            description: document.getElementById('productDesc').value
        };
        
        currentUser.shop.products.push(shopProduct);
    }

    // Initialize the app when the page loads
    window.onload = function() {
        initApp();
    };
    // Close product menus when clicking outside
document.addEventListener('click', function(event) {
    // Close product menus
    if (!event.target.closest('.product-menu-btn')) {
        document.querySelectorAll('.product-menu-dropdown').forEach(dropdown => {
            dropdown.classList.remove('show');
        });
    }
    
    // ... (other existing click handlers)
});
    

     




        

        // Toast notification function
        function showToast(message, type = 'success') {
            // Create toast element
            const toast = document.createElement('div');
            toast.style.cssText = `
                position: fixed;
                top: 20px;
                right: 20px;
                background-color: ${type === 'success' ? '#2ecc71' : '#e74c3c'};
                color: white;
                padding: 15px 20px;
                border-radius: 5px;
                box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
                z-index: 10000;
                max-width: 300px;
                word-wrap: break-word;
            `;
            toast.textContent = message;
            
            // Add to page
            document.body.appendChild(toast);
            
            // Remove after 3 seconds
            setTimeout(() => {
                if (toast.parentNode) {
                    document.body.removeChild(toast);
                }
            }, 3000);
        }

        // Update shop profile function
        function updateShopProfile(companyName, contact) {
            // Update shop profile data
            currentUser.shop = currentUser.shop || {
                hasShop: false,
                shopName: "",
                shopAvatar: "https://ui-avatars.com/api/?name=Shop&background=4267B2",
                shopType: "Online Store",
                contact: "",
                location: "",
                products: []
            };
            
            currentUser.shop.hasShop = true;
            currentUser.shop.shopName = companyName;
            currentUser.shop.contact = contact;
            currentUser.shop.location = currentUser.profile.country || "";
            currentUser.shop.shopAvatar = currentUser.avatar;
            
            // Add product to shop products
            const shopProduct = {
                id: Date.now(),
                name: document.getElementById('productName').value,
                price: parseInt(document.getElementById('productPrice').value),
                image: document.getElementById('productImages').files[0] ? 
                       URL.createObjectURL(document.getElementById('productImages').files[0]) : '',
                description: document.getElementById('productDesc').value
            };
            
            if (!currentUser.shop.products) {
                currentUser.shop.products = [];
            }
            currentUser.shop.products.push(shopProduct);
        }

        // Initialize the app when the page loads
        window.onload = function() {
            initApp();
        };
    </script>
</html>
