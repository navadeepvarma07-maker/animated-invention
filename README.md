<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arnama Connect - Community Bulletin Board</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Existing CSS remains the same */
        body {
            background-color: #f5f7fa;
            color: #333;
            line-height: 1.6;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        .hidden {
            display: none !important;
        }
        
        /* Header Styles */
        header {
            background: linear-gradient(135deg, #4e54c8, #8a64d0);
            color: white;
            padding: 1.5rem 0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: relative;
            overflow: hidden;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: relative;
            z-index: 2;
        }
        
        .logo-container {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .logo-icon {
            font-size: 2.5rem;
            color: #ffde59;
        }
        
        .logo-text {
            display: flex;
            flex-direction: column;
        }
        
        h1 {
            font-size: 2.2rem;
            font-weight: 700;
            line-height: 1.1;
        }
        
        .tagline {
            font-size: 0.9rem;
            opacity: 0.9;
            margin-top: 5px;
        }
        
        .highlight {
            color: #ffde59;
        }
        
        .auth-buttons {
            display: flex;
            gap: 10px;
        }
        
        .auth-btn {
            background: rgba(255, 255, 255, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.3);
            color: white;
            padding: 8px 15px;
            border-radius: 4px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .auth-btn:hover {
            background: rgba(255, 255, 255, 0.3);
        }
        
        #user-greeting {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .notification-bell {
            position: relative;
            cursor: pointer;
            font-size: 1.2rem;
        }
        
        .notification-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: #ff4757;
            color: white;
            border-radius: 50%;
            width: 18px;
            height: 18px;
            font-size: 0.7rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        /* Navigation Styles */
        nav {
            background-color: #fff;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
        }
        
        nav ul {
            display: flex;
            list-style: none;
            padding: 1rem 0;
        }
        
        nav li {
            margin-right: 1.5rem;
        }
        
        nav a {
            text-decoration: none;
            color: #4e54c8;
            font-weight: 500;
            transition: color 0.3s ease;
            display: flex;
            align-items: center;
            gap: 5px;
        }
        
        nav a:hover {
            color: #8a64d0;
        }
        
        /* Section Styles */
        .section {
            padding: 3rem 0;
        }
        
        h2 {
            font-size: 2rem;
            margin-bottom: 1.5rem;
            color: #4e54c8;
            text-align: center;
        }
        
        h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: #6c6c6c;
        }
        
        /* Bulletin Board Styles */
        .bulletin-prompt {
            text-align: center;
            padding: 2rem;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
            margin-bottom: 2rem;
        }
        
        .cta-button {
            background-color: #4e54c8;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 500;
            margin-top: 1rem;
            transition: background-color 0.3s ease;
        }
        
        .cta-button:hover {
            background-color: #3a3fb3;
        }
        
        /* Form Styles */
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }
        
        input, textarea, select {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
        }
        
        textarea {
            resize: vertical;
            min-height: 120px;
        }
        
        .submit-btn {
            background-color: #4e54c8;
            color: white;
            border: none;
            padding: 12px 24px;
            border-radius: 4px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 500;
            transition: background-color 0.3s ease;
        }
        
        .submit-btn:hover {
            background-color: #3a3fb3;
        }
        
        /* Media Upload Styles */
        .media-upload {
            margin-bottom: 1.5rem;
        }
        
        .upload-area {
            border: 2px dashed #ccc;
            border-radius: 8px;
            padding: 20px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-bottom: 15px;
        }
        
        .upload-area:hover {
            border-color: #4e54c8;
            background-color: #f9f9ff;
        }
        
        .upload-icon {
            font-size: 3rem;
            color: #4e54c8;
            margin-bottom: 10px;
        }
        
        .media-preview {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 15px;
        }
        
        .preview-item {
            position: relative;
            width: 100px;
            height: 100px;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        
        .preview-item img, .preview-item video {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .remove-media {
            position: absolute;
            top: 5px;
            right: 5px;
            background: rgba(255, 255, 255, 0.8);
            border: none;
            border-radius: 50%;
            width: 24px;
            height: 24px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        /* Posts Grid */
        .posts-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 2rem;
        }
        
        .post-card {
            background: white;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
            padding: 1.5rem;
            transition: transform 0.3s ease;
            position: relative;
        }
        
        .post-card:hover {
            transform: translateY(-5px);
        }
        
        .post-title {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: #4e54c8;
        }
        
        .post-content {
            margin-bottom: 1rem;
            color: #555;
        }
        
        .post-media {
            margin-bottom: 1rem;
        }
        
        .post-media img, .post-media video {
            width: 100%;
            border-radius: 8px;
            max-height: 300px;
            object-fit: cover;
        }
        
        .post-meta {
            display: flex;
            justify-content: space-between;
            font-size: 0.9rem;
            color: #888;
        }
        
        .post-category {
            display: inline-block;
            padding: 3px 8px;
            border-radius: 12px;
            font-size: 0.8rem;
            font-weight: 500;
        }
        
        .category-general {
            background-color: #e0e0e0;
            color: #424242;
        }
        
        .category-help {
            background-color: #ffebee;
            color: #c62828;
        }
        
        .category-offer {
            background-color: #e8f5e9;
            color: #2e7d32;
        }
        
        .category-event {
            background-color: #e3f2fd;
            color: #1565c0;
        }
        
        .category-sale {
            background-color: #fff8e1;
            color: #f57f17;
        }
        
        .message-author-btn {
            background-color: #8a64d0;
            color: white;
            border: none;
            padding: 6px 12px;
            border-radius: 4px;
            cursor: pointer;
            font-size: 0.8rem;
            margin-top: 10px;
            transition: background-color 0.3s ease;
        }
        
        .message-author-btn:hover {
            background-color: #6a4ca8;
        }
        
        /* Post Actions */
        .post-actions {
            display: flex;
            justify-content: space-between;
            margin-top: 15px;
            padding-top: 15px;
            border-top: 1px solid #eee;
        }
        
        .action-btn {
            background: none;
            border: none;
            color: #666;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 5px;
            font-size: 0.9rem;
            transition: color 0.3s ease;
        }
        
        .action-btn:hover {
            color: #4e54c8;
        }
        
        .action-btn.liked {
            color: #ff4757;
        }
        
        .action-btn.saved {
            color: #ffa502;
        }
        
        .action-btn.delete-btn {
            color: #ff4757;
        }
        
        .comments-section {
            margin-top: 15px;
            padding-top: 15px;
            border-top: 1px solid #eee;
        }
        
        .comment {
            margin-bottom: 10px;
            padding-bottom: 10px;
            border-bottom: 1px solid #f5f5f5;
            position: relative;
        }
        
        .comment-author {
            font-weight: 600;
            font-size: 0.9rem;
        }
        
        .comment-content {
            margin-top: 5px;
            font-size: 0.9rem;
        }
        
        .comment-actions {
            position: absolute;
            top: 0;
            right: 0;
        }
        
        .delete-comment-btn {
            background: none;
            border: none;
            color: #ff4757;
            cursor: pointer;
            font-size: 0.8rem;
        }
        
        .comment-input {
            display: flex;
            margin-top: 10px;
        }
        
        .comment-input input {
            flex: 1;
            padding: 8px 12px;
            border: 1px solid #ddd;
            border-radius: 20px;
            font-size: 0.9rem;
        }
        
        .comment-btn {
            background: none;
            border: none;
            color: #4e54c8;
            cursor: pointer;
            margin-left: 5px;
        }
        
        /* Share Modal */
        .share-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }
        
        .share-modal-content {
            background-color: white;
            padding: 2rem;
            border-radius: 8px;
            width: 90%;
            max-width: 500px;
            position: relative;
        }
        
        .share-options {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
            margin-top: 1rem;
        }
        
        .share-option {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 15px;
            border-radius: 8px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .share-option:hover {
            background-color: #f5f5f5;
        }
        
        .share-icon {
            font-size: 2rem;
            margin-bottom: 8px;
        }
        
        .whatsapp {
            color: #25D366;
        }
        
        .facebook {
            color: #1877F2;
        }
        
        .twitter {
            color: #1DA1F2;
        }
        
        .instagram {
            color: #E4405F;
        }
        
        .telegram {
            color: #0088cc;
        }
        
        .linkedin {
            color: #0A66C2;
        }
        
        .copy-link {
            color: #4e54c8;
        }
        
        /* Dashboard Styles */
        .dashboard-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
        }
        
        .dashboard-card {
            background: white;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
            padding: 1.5rem;
        }
        
        .dashboard-btn {
            background-color: #8a64d0;
            color: white;
            border: none;
            padding: 8px 16px;
            border-radius: 4px;
            cursor: pointer;
            margin-top: 1rem;
        }
        
        /* Messaging Styles */
        .messaging-container {
            display: flex;
            height: 500px;
            background: white;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
            overflow: hidden;
        }
        
        .conversations-list {
            width: 30%;
            border-right: 1px solid #eee;
            overflow-y: auto;
        }
        
        .conversation-item {
            padding: 15px;
            border-bottom: 1px solid #eee;
            cursor: pointer;
            transition: background-color 0.2s;
            position: relative;
        }
        
        .conversation-item:hover {
            background-color: #f9f9ff;
        }
        
        .conversation-item.active {
            background-color: #eef2ff;
        }
        
        .conversation-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 5px;
        }
        
        .conversation-name {
            font-weight: 600;
        }
        
        .conversation-time {
            font-size: 0.8rem;
            color: #888;
        }
        
        .conversation-preview {
            font-size: 0.9rem;
            color: #666;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        
        .unread-indicator {
            position: absolute;
            top: 15px;
            right: 15px;
            width: 10px;
            height: 10px;
            background-color: #ff4757;
            border-radius: 50%;
        }
        
        .chat-area {
            width: 70%;
            display: flex;
            flex-direction: column;
        }
        
        .chat-header {
            padding: 15px;
            border-bottom: 1px solid #eee;
            background-color: #f9f9ff;
        }
        
        .chat-messages {
            flex: 1;
            padding: 15px;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        
        .message {
            max-width: 70%;
            padding: 10px 15px;
            border-radius: 18px;
            position: relative;
        }
        
        .message.sent {
            align-self: flex-end;
            background-color: #4e54c8;
            color: white;
            border-bottom-right-radius: 5px;
        }
        
        .message.received {
            align-self: flex-start;
            background-color: #f0f0f0;
            color: #333;
            border-bottom-left-radius: 5px;
        }
        
        .message-time {
            font-size: 0.7rem;
            opacity: 0.7;
            margin-top: 5px;
            text-align: right;
        }
        
        .chat-input {
            display: flex;
            padding: 15px;
            border-top: 1px solid #eee;
            gap: 10px;
        }
        
        .chat-input input {
            flex: 1;
            padding: 10px 15px;
            border: 1px solid #ddd;
            border-radius: 20px;
        }
        
        .send-btn {
            background-color: #4e54c8;
            color: white;
            border: none;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        /* User Directory Styles */
        .user-directory {
            background: white;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
            padding: 1.5rem;
            margin-bottom: 2rem;
        }
        
        .user-search {
            display: flex;
            gap: 10px;
            margin-bottom: 1rem;
        }
        
        .user-search input {
            flex: 1;
        }
        
        .users-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 15px;
        }
        
        .user-card {
            background: #f9f9ff;
            border-radius: 8px;
            padding: 1rem;
            text-align: center;
            transition: transform 0.2s;
        }
        
        .user-card:hover {
            transform: translateY(-3px);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        
        .user-avatar {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: linear-gradient(135deg, #4e54c8, #8a64d0);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            margin: 0 auto 10px;
        }
        
        .user-name {
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .user-email {
            font-size: 0.8rem;
            color: #666;
            margin-bottom: 10px;
        }
        
        .message-user-btn {
            background-color: #8a64d0;
            color: white;
            border: none;
            padding: 5px 10px;
            border-radius: 4px;
            cursor: pointer;
            font-size: 0.8rem;
            width: 100%;
        }
        
        /* Modal Styles */
        .modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }
        
        .modal-content {
            background-color: white;
            padding: 2rem;
            border-radius: 8px;
            width: 90%;
            max-width: 500px;
            position: relative;
            max-height: 90vh;
            overflow-y: auto;
        }
        
        .close-modal {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 1.5rem;
            cursor: pointer;
            color: #888;
        }
        
        /* Confirmation Modal */
        .confirmation-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }
        
        .confirmation-content {
            background-color: white;
            padding: 2rem;
            border-radius: 8px;
            width: 90%;
            max-width: 400px;
            text-align: center;
        }
        
        .confirmation-buttons {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 20px;
        }
        
        .confirm-btn {
            background-color: #ff4757;
            color: white;
            border: none;
            padding: 8px 16px;
            border-radius: 4px;
            cursor: pointer;
        }
        
        .cancel-btn {
            background-color: #ddd;
            color: #333;
            border: none;
            padding: 8px 16px;
            border-radius: 4px;
            cursor: pointer;
        }
        
        /* Notifications Panel */
        .notifications-panel {
            position: absolute;
            top: 100%;
            right: 0;
            width: 350px;
            background: white;
            border-radius: 8px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.15);
            z-index: 100;
            max-height: 400px;
            overflow-y: auto;
            display: none;
            border: 1px solid #e0e0e0;
        }
        
        .notifications-panel.active {
            display: block;
        }
        
        .notification-header {
            padding: 15px;
            border-bottom: 1px solid #eee;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: #f9f9ff;
            border-radius: 8px 8px 0 0;
        }
        
        .notification-header h4 {
            margin: 0;
            color: #4e54c8;
        }
        
        .clear-notifications {
            background: none;
            border: none;
            color: #8a64d0;
            cursor: pointer;
            font-size: 0.8rem;
        }
        
        .notification-item {
            padding: 15px;
            border-bottom: 1px solid #eee;
            cursor: pointer;
            transition: background-color 0.2s;
        }
        
        .notification-item:hover {
            background-color: #f5f5f5;
        }
        
        .notification-item.unread {
            background-color: #f0f7ff;
        }
        
        .notification-message {
            font-size: 0.9rem;
            margin-bottom: 5px;
            color: #333;
            font-weight: 500;
        }
        
        .notification-time {
            font-size: 0.7rem;
            color: #666;
        }
        
        .notification-type {
            display: inline-block;
            padding: 2px 6px;
            border-radius: 10px;
            font-size: 0.6rem;
            font-weight: 600;
            margin-right: 5px;
        }
        
        .type-message {
            background-color: #e3f2fd;
            color: #1565c0;
        }
        
        .type-post {
            background-color: #e8f5e9;
            color: #2e7d32;
        }
        
        .type-comment {
            background-color: #fff3e0;
            color: #e65100;
        }
        
        .type-like {
            background-color: #ffebee;
            color: #c62828;
        }
        
        /* Footer Styles */
        footer {
            background-color: #333;
            color: white;
            padding: 2rem 0;
            text-align: center;
        }
        
        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        .footer-nav {
            display: flex;
            gap: 20px;
            margin: 1rem 0;
        }
        
        .footer-nav a {
            color: #ddd;
            text-decoration: none;
        }
        
        .footer-nav a:hover {
            color: white;
        }
        
        /* Mobile Menu */
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        .mobile-nav {
            display: none;
            background-color: #fff;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
            position: absolute;
            top: 100%;
            left: 0;
            width: 100%;
            z-index: 100;
        }
        
        .mobile-nav.active {
            display: block;
        }
        
        .mobile-nav ul {
            list-style: none;
            padding: 0;
            margin: 0;
        }
        
        .mobile-nav li {
            border-bottom: 1px solid #eee;
        }
        
        .mobile-nav a {
            display: block;
            padding: 15px;
            text-decoration: none;
            color: #4e54c8;
            font-weight: 500;
        }
        
        /* Responsive Design */
        @media (max-width: 1024px) {
            .posts-grid {
                grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            }
            
            .users-grid {
                grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
            }
        }
        
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                text-align: center;
                gap: 15px;
            }
            
            .mobile-menu-btn {
                display: block;
                position: absolute;
                top: 20px;
                right: 15px;
            }
            
            nav ul {
                display: none;
            }
            
            .posts-grid {
                grid-template-columns: 1fr;
            }
            
            .dashboard-grid {
                grid-template-columns: 1fr;
            }
            
            .media-preview {
                justify-content: center;
            }
            
            .messaging-container {
                flex-direction: column;
                height: 600px;
            }
            
            .conversations-list, .chat-area {
                width: 100%;
            }
            
            .conversations-list {
                height: 40%;
            }
            
            .chat-area {
                height: 60%;
            }
            
            .users-grid {
                grid-template-columns: 1fr 1fr;
            }
            
            .notifications-panel {
                width: 300px;
                right: -50px;
            }
            
            .share-options {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .post-actions {
                flex-wrap: wrap;
                gap: 10px;
            }
            
            .action-btn {
                font-size: 0.8rem;
            }
        }
        
        @media (max-width: 480px) {
            h1 {
                font-size: 1.8rem;
            }
            
            h2 {
                font-size: 1.5rem;
            }
            
            .post-card {
                padding: 1rem;
            }
            
            .users-grid {
                grid-template-columns: 1fr;
            }
            
            .user-search {
                flex-direction: column;
            }
            
            .notifications-panel {
                width: 280px;
                right: -70px;
            }
            
            .share-options {
                grid-template-columns: 1fr;
            }
            
            .message {
                max-width: 85%;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo-container">
                    <div class="logo-icon">
                        <i class="fas fa-users"></i>
                    </div>
                    <div class="logo-text">
                        <h1>Arnama <span class="highlight">Connect</span></h1>
                        <p class="tagline">Your community hub for sharing and connecting</p>
                    </div>
                </div>
                <div class="auth-buttons">
                    <button id="login-btn" class="auth-btn">Login</button>
                    <button id="register-btn" class="auth-btn">Register</button>
                    <div id="user-greeting" class="hidden">
                        <span>Hello, <span id="username-display"></span></span>
                        <div class="notification-bell" id="notification-bell">
                            <i class="fas fa-bell"></i>
                            <span class="notification-count hidden" id="notification-count">0</span>
                        </div>
                        <button id="logout-btn" class="auth-btn">Logout</button>
                    </div>
                </div>
                <button class="mobile-menu-btn" id="mobile-menu-btn">
                    <i class="fas fa-bars"></i>
                </button>
            </div>
        </div>
        <div class="mobile-nav" id="mobile-nav">
            <ul>
                <li><a href="#bulletin"><i class="fas fa-bullhorn"></i> Community Bulletin</a></li>
                <li id="dashboard-link-mobile" class="hidden"><a href="#dashboard"><i class="fas fa-tachometer-alt"></i> My Dashboard</a></li>
                <li id="messages-link-mobile" class="hidden"><a href="#messages"><i class="fas fa-comments"></i> Messages</a></li>
                <li id="users-link-mobile" class="hidden"><a href="#users"><i class="fas fa-user-friends"></i> Find Users</a></li>
            </ul>
        </div>
        <div class="notifications-panel" id="notifications-panel">
            <div class="notification-header">
                <h4>Notifications</h4>
                <button class="clear-notifications" id="clear-notifications">Clear All</button>
            </div>
            <!-- Notifications will be loaded here dynamically -->
        </div>
    </header>

    <nav>
        <div class="container">
            <ul>
                <li><a href="#bulletin"><i class="fas fa-bullhorn"></i> Community Bulletin</a></li>
                <li id="dashboard-link" class="hidden"><a href="#dashboard"><i class="fas fa-tachometer-alt"></i> My Dashboard</a></li>
                <li id="messages-link" class="hidden"><a href="#messages"><i class="fas fa-comments"></i> Messages</a></li>
                <li id="users-link" class="hidden"><a href="#users"><i class="fas fa-user-friends"></i> Find Users</a></li>
            </ul>
        </div>
    </nav>

    <section id="bulletin" class="section">
        <div class="container">
            <h2>Community Bulletin</h2>
            <div id="post-form-container" class="hidden">
                <h3>Create a New Post</h3>
                <form id="post-form">
                    <div class="form-group">
                        <label for="post-title">Title</label>
                        <input type="text" id="post-title" required>
                    </div>
                    <div class="form-group">
                        <label for="post-content">Content</label>
                        <textarea id="post-content" rows="5" required></textarea>
                    </div>
                    <div class="form-group">
                        <label for="post-category">Category</label>
                        <select id="post-category">
                            <option value="general">General</option>
                            <option value="help">Help Needed</option>
                            <option value="offer">Offering Help</option>
                            <option value="event">Event</option>
                            <option value="sale">For Sale</option>
                        </select>
                    </div>
                    
                    <!-- Media Upload Section -->
                    <div class="media-upload">
                        <label>Add Photos or Videos</label>
                        <div class="upload-area" id="media-drop-area">
                            <div class="upload-icon">
                                <i class="fas fa-cloud-upload-alt"></i>
                            </div>
                            <p>Drag & drop files here or click to browse</p>
                            <input type="file" id="media-upload" multiple accept="image/*,video/*" style="display: none;">
                        </div>
                        <div class="media-preview" id="media-preview"></div>
                    </div>
                    
                    <button type="submit" class="submit-btn">Post to Community</button>
                </form>
            </div>
            <div id="login-prompt" class="bulletin-prompt">
                <p>Want to share something with the community?</p>
                <button id="prompt-login-btn" class="cta-button">Login to Post</button>
            </div>
            <div id="posts-container" class="posts-grid">
                <!-- Posts will be loaded here dynamically -->
            </div>
        </div>
    </section>

    <section id="dashboard" class="section hidden">
        <div class="container">
            <h2>My Dashboard</h2>
            <div class="dashboard-grid">
                <div class="dashboard-card">
                    <h3>My Profile</h3>
                    <div id="profile-info">
                        <p><strong>Name:</strong> <span id="profile-name"></span></p>
                        <p><strong>Email:</strong> <span id="profile-email"></span></p>
                        <p><strong>Member since:</strong> <span id="join-date"></span></p>
                        <p><strong>Posts:</strong> <span id="post-count">0</span></p>
                        <p><strong>Messages:</strong> <span id="message-count">0</span></p>
                    </div>
                    <button id="edit-profile-btn" class="dashboard-btn">Edit Profile</button>
                </div>
                <div class="dashboard-card">
                    <h3>My Posts</h3>
                    <div id="user-posts">
                        <!-- User's posts will be loaded here -->
                    </div>
                </div>
                <div class="dashboard-card">
                    <h3>Saved Posts</h3>
                    <div id="saved-posts">
                        <!-- Saved posts will be loaded here -->
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="messages" class="section hidden">
        <div class="container">
            <h2>Messages</h2>
            <div class="messaging-container">
                <div class="conversations-list" id="conversations-list">
                    <!-- Conversations will be loaded here -->
                </div>
                <div class="chat-area">
                    <div class="chat-header" id="chat-header">
                        <p>Select a conversation to start messaging</p>
                    </div>
                    <div class="chat-messages" id="chat-messages">
                        <!-- Messages will be loaded here -->
                    </div>
                    <div class="chat-input hidden" id="chat-input">
                        <input type="text" id="message-input" placeholder="Type a message...">
                        <button class="send-btn" id="send-message-btn">
                            <i class="fas fa-paper-plane"></i>
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="users" class="section hidden">
        <div class="container">
            <h2>Find Community Members</h2>
            <div class="user-directory">
                <div class="user-search">
                    <input type="text" id="user-search-input" placeholder="Search for users by name...">
                    <button id="user-search-btn" class="cta-button">Search</button>
                </div>
                <div class="users-grid" id="users-grid">
                    <!-- Users will be loaded here -->
                </div>
            </div>
        </div>
    </section>

    <div id="auth-modal" class="modal hidden">
        <div class="modal-content">
            <span class="close-modal">&times;</span>
            <div id="login-form">
                <h3>Login</h3>
                <form id="login-form-data">
                    <div class="form-group">
                        <label for="login-email">Email</label>
                        <input type="email" id="login-email" required>
                    </div>
                    <div class="form-group">
                        <label for="login-password">Password</label>
                        <input type="password" id="login-password" required>
                    </div>
                    <button type="submit" class="submit-btn">Login</button>
                </form>
                <p>Don't have an account? <a href="#" id="switch-to-register">Register here</a></p>
            </div>
            <div id="register-form" class="hidden">
                <h3>Register</h3>
                <form id="register-form-data">
                    <div class="form-group">
                        <label for="register-name">Full Name</label>
                        <input type="text" id="register-name" required>
                    </div>
                    <div class="form-group">
                        <label for="register-email">Email</label>
                        <input type="email" id="register-email" required>
                    </div>
                    <div class="form-group">
                        <label for="register-password">Password</label>
                        <input type="password" id="register-password" required>
                    </div>
                    <div class="form-group">
                        <label for="register-address">Street Address (optional)</label>
                        <input type="text" id="register-address">
                    </div>
                    <button type="submit" class="submit-btn">Register</button>
                </form>
                <p>Already have an account? <a href="#" id="switch-to-login">Login here</a></p>
            </div>
        </div>
    </div>

    <!-- Share Modal -->
    <div id="share-modal" class="share-modal hidden">
        <div class="share-modal-content">
            <span class="close-modal" id="close-share-modal">&times;</span>
            <h3>Share this post</h3>
            <div class="share-options">
                <div class="share-option whatsapp" data-platform="whatsapp">
                    <i class="fab fa-whatsapp share-icon"></i>
                    <span>WhatsApp</span>
                </div>
                <div class="share-option facebook" data-platform="facebook">
                    <i class="fab fa-facebook share-icon"></i>
                    <span>Facebook</span>
                </div>
                <div class="share-option twitter" data-platform="twitter">
                    <i class="fab fa-twitter share-icon"></i>
                    <span>Twitter</span>
                </div>
                <div class="share-option instagram" data-platform="instagram">
                    <i class="fab fa-instagram share-icon"></i>
                    <span>Instagram</span>
                </div>
                <div class="share-option telegram" data-platform="telegram">
                    <i class="fab fa-telegram share-icon"></i>
                    <span>Telegram</span>
                </div>
                <div class="share-option linkedin" data-platform="linkedin">
                    <i class="fab fa-linkedin share-icon"></i>
                    <span>LinkedIn</span>
                </div>
                <div class="share-option copy-link" data-platform="copy">
                    <i class="fas fa-link share-icon"></i>
                    <span>Copy Link</span>
                </div>
            </div>
        </div>
    </div>

    <!-- Confirmation Modal -->
    <div id="confirmation-modal" class="confirmation-modal hidden">
        <div class="confirmation-content">
            <h3 id="confirmation-title">Confirm Action</h3>
            <p id="confirmation-message">Are you sure you want to perform this action?</p>
            <div class="confirmation-buttons">
                <button id="confirm-action" class="confirm-btn">Yes, Delete</button>
                <button id="cancel-action" class="cancel-btn">Cancel</button>
            </div>
        </div>
    </div>

    <footer>
        <div class="container">
            <div class="footer-content">
                <h3>Arnama Connect</h3>
                <div class="footer-nav">
                    <a href="#bulletin">Community Bulletin</a>
                    <a href="#">About Us</a>
                    <a href="#">Contact</a>
                    <a href="#">Privacy Policy</a>
                </div>
                <p>&copy; 2023 Arnama Connect. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // DOM Elements
        const loginBtn = document.getElementById('login-btn');
        const registerBtn = document.getElementById('register-btn');
        const logoutBtn = document.getElementById('logout-btn');
        const userGreeting = document.getElementById('user-greeting');
        const usernameDisplay = document.getElementById('username-display');
        const dashboardLink = document.getElementById('dashboard-link');
        const messagesLink = document.getElementById('messages-link');
        const usersLink = document.getElementById('users-link');
        const dashboardLinkMobile = document.getElementById('dashboard-link-mobile');
        const messagesLinkMobile = document.getElementById('messages-link-mobile');
        const usersLinkMobile = document.getElementById('users-link-mobile');
        const dashboardSection = document.getElementById('dashboard');
        const messagesSection = document.getElementById('messages');
        const usersSection = document.getElementById('users');
        const authModal = document.getElementById('auth-modal');
        const closeModalBtn = document.querySelector('.close-modal');
        const switchToRegister = document.getElementById('switch-to-register');
        const switchToLogin = document.getElementById('switch-to-login');
        const loginForm = document.getElementById('login-form');
        const registerForm = document.getElementById('register-form');
        const loginFormData = document.getElementById('login-form-data');
        const registerFormData = document.getElementById('register-form-data');
        const postFormContainer = document.getElementById('post-form-container');
        const loginPrompt = document.getElementById('login-prompt');
        const promptLoginBtn = document.getElementById('prompt-login-btn');
        const postForm = document.getElementById('post-form');
        const postsContainer = document.getElementById('posts-container');
        const profileName = document.getElementById('profile-name');
        const profileEmail = document.getElementById('profile-email');
        const joinDate = document.getElementById('join-date');
        const userPostsContainer = document.getElementById('user-posts');
        const savedPostsContainer = document.getElementById('saved-posts');
        const editProfileBtn = document.getElementById('edit-profile-btn');
        const mobileMenuBtn = document.getElementById('mobile-menu-btn');
        const mobileNav = document.getElementById('mobile-nav');
        
        // Messaging elements
        const conversationsList = document.getElementById('conversations-list');
        const chatHeader = document.getElementById('chat-header');
        const chatMessages = document.getElementById('chat-messages');
        const chatInput = document.getElementById('chat-input');
        const messageInput = document.getElementById('message-input');
        const sendMessageBtn = document.getElementById('send-message-btn');
        
        // User directory elements
        const userSearchInput = document.getElementById('user-search-input');
        const userSearchBtn = document.getElementById('user-search-btn');
        const usersGrid = document.getElementById('users-grid');
        
        // Notification elements
        const notificationBell = document.getElementById('notification-bell');
        const notificationCount = document.getElementById('notification-count');
        const notificationsPanel = document.getElementById('notifications-panel');
        const clearNotificationsBtn = document.getElementById('clear-notifications');
        
        // Media upload elements
        const mediaDropArea = document.getElementById('media-drop-area');
        const mediaUpload = document.getElementById('media-upload');
        const mediaPreview = document.getElementById('media-preview');
        
        // Share modal elements
        const shareModal = document.getElementById('share-modal');
        const closeShareModal = document.getElementById('close-share-modal');
        const shareOptions = document.querySelectorAll('.share-option');
        
        // Confirmation modal elements
        const confirmationModal = document.getElementById('confirmation-modal');
        const confirmationTitle = document.getElementById('confirmation-title');
        const confirmationMessage = document.getElementById('confirmation-message');
        const confirmActionBtn = document.getElementById('confirm-action');
        const cancelActionBtn = document.getElementById('cancel-action');

        // Current user state
        let currentUser = null;
        let mediaFiles = [];
        let currentConversationId = null;
        let currentPostToShare = null;
        let pendingDeleteAction = null;

        // Event Listeners
        document.addEventListener('DOMContentLoaded', function() {
            // Check if user is logged in (from localStorage)
            const savedUser = localStorage.getItem('currentUser');
            if (savedUser) {
                currentUser = JSON.parse(savedUser);
                updateUIForLoggedInUser();
            }
            
            // Load posts
            loadPosts();
            
            // Set up event listeners
            setupEventListeners();
            
            // Initialize sample data
            initializeSampleData();
        });

        function setupEventListeners() {
            // Auth buttons
            loginBtn.addEventListener('click', showLoginModal);
            registerBtn.addEventListener('click', showRegisterModal);
            logoutBtn.addEventListener('click', logout);
            promptLoginBtn.addEventListener('click', showLoginModal);
            
            // Modal interactions
            closeModalBtn.addEventListener('click', closeAuthModal);
            switchToRegister.addEventListener('click', switchToRegisterForm);
            switchToLogin.addEventListener('click', switchToLoginForm);
            
            // Form submissions
            loginFormData.addEventListener('submit', handleLogin);
            registerFormData.addEventListener('submit', handleRegister);
            postForm.addEventListener('submit', handlePostSubmit);
            
            // Navigation
            dashboardLink.addEventListener('click', showDashboard);
            messagesLink.addEventListener('click', showMessages);
            usersLink.addEventListener('click', showUsers);
            dashboardLinkMobile.addEventListener('click', showDashboard);
            messagesLinkMobile.addEventListener('click', showMessages);
            usersLinkMobile.addEventListener('click', showUsers);
            
            // Mobile menu
            mobileMenuBtn.addEventListener('click', toggleMobileMenu);
            
            // Media upload
            mediaDropArea.addEventListener('click', () => mediaUpload.click());
            mediaUpload.addEventListener('change', handleMediaUpload);
            mediaDropArea.addEventListener('dragover', (e) => {
                e.preventDefault();
                mediaDropArea.style.borderColor = '#4e54c8';
                mediaDropArea.style.backgroundColor = '#f9f9ff';
            });
            mediaDropArea.addEventListener('dragleave', () => {
                mediaDropArea.style.borderColor = '#ccc';
                mediaDropArea.style.backgroundColor = 'transparent';
            });
            mediaDropArea.addEventListener('drop', handleMediaDrop);
            
            // Messaging
            sendMessageBtn.addEventListener('click', sendMessage);
            messageInput.addEventListener('keypress', (e) => {
                if (e.key === 'Enter') {
                    sendMessage();
                }
            });
            
            // User directory
            userSearchBtn.addEventListener('click', searchUsers);
            userSearchInput.addEventListener('keypress', (e) => {
                if (e.key === 'Enter') {
                    searchUsers();
                }
            });
            
            // Notifications
            notificationBell.addEventListener('click', toggleNotifications);
            clearNotificationsBtn.addEventListener('click', clearAllNotifications);
            
            // Share modal
            closeShareModal.addEventListener('click', () => shareModal.classList.add('hidden'));
            shareOptions.forEach(option => {
                option.addEventListener('click', handleShare);
            });
            
            // Confirmation modal
            confirmActionBtn.addEventListener('click', executePendingDelete);
            cancelActionBtn.addEventListener('click', () => confirmationModal.classList.add('hidden'));
            
            // Close modals when clicking outside
            window.addEventListener('click', function(event) {
                if (event.target === authModal) {
                    closeAuthModal();
                }
                if (event.target === shareModal) {
                    shareModal.classList.add('hidden');
                }
                if (event.target === confirmationModal) {
                    confirmationModal.classList.add('hidden');
                }
                if (!notificationBell.contains(event.target)) {
                    notificationsPanel.classList.remove('active');
                }
                if (!mobileMenuBtn.contains(event.target) && !mobileNav.contains(event.target)) {
                    mobileNav.classList.remove('active');
                }
            });
        }

        function initializeSampleData() {
            // Check if we need to create sample data
            const posts = JSON.parse(localStorage.getItem('posts')) || [];
            
            // If no posts exist, create a sample post
            if (posts.length === 0) {
                const samplePost = {
                    id: Date.now(),
                    title: "Welcome to Arnama Connect!",
                    content: "Welcome to our community hub! This is a place where neighbors can connect, share resources, and support each other. Feel free to post about events, items for sale, or ask for help.",
                    category: "general",
                    author: "MNV",
                    authorId: 1,
                    date: new Date().toLocaleDateString(),
                    likes: 0,
                    likedBy: [],
                    comments: [],
                    media: []
                };
                
                posts.push(samplePost);
                localStorage.setItem('posts', JSON.stringify(posts));
            }
            
            // Check if we need to create sample users
            const users = JSON.parse(localStorage.getItem('users')) || [];
            if (users.length === 0) {
                const sampleUser = {
                    id: 1,
                    name: "MNV",
                    email: "mnv@example.com",
                    password: "password",
                    joinDate: new Date().toLocaleDateString()
                };
                
                users.push(sampleUser);
                localStorage.setItem('users', JSON.stringify(users));
            }
        }

        function showLoginModal() {
            authModal.classList.remove('hidden');
            loginForm.classList.remove('hidden');
            registerForm.classList.add('hidden');
        }

        function showRegisterModal() {
            authModal.classList.remove('hidden');
            registerForm.classList.remove('hidden');
            loginForm.classList.add('hidden');
        }

        function closeAuthModal() {
            authModal.classList.add('hidden');
            // Clear form fields
            document.getElementById('login-email').value = '';
            document.getElementById('login-password').value = '';
            document.getElementById('register-name').value = '';
            document.getElementById('register-email').value = '';
            document.getElementById('register-password').value = '';
            document.getElementById('register-address').value = '';
        }

        function switchToRegisterForm(e) {
            e.preventDefault();
            loginForm.classList.add('hidden');
            registerForm.classList.remove('hidden');
        }

        function switchToLoginForm(e) {
            e.preventDefault();
            registerForm.classList.add('hidden');
            loginForm.classList.remove('hidden');
        }

        function handleLogin(e) {
            e.preventDefault();
            const email = document.getElementById('login-email').value;
            const password = document.getElementById('login-password').value;
            
            // Simple validation
            if (!email || !password) {
                alert('Please fill in all fields');
                return;
            }
            
            // Check if user exists in localStorage
            const users = JSON.parse(localStorage.getItem('users') || '[]');
            const user = users.find(u => u.email === email && u.password === password);
            
            if (user) {
                // Login successful
                currentUser = user;
                localStorage.setItem('currentUser', JSON.stringify(currentUser));
                updateUIForLoggedInUser();
                closeAuthModal();
                alert('Login successful!');
            } else {
                alert('Invalid email or password');
            }
        }

        function handleRegister(e) {
            e.preventDefault();
            const name = document.getElementById('register-name').value;
            const email = document.getElementById('register-email').value;
            const password = document.getElementById('register-password').value;
            const address = document.getElementById('register-address').value;
            
            // Simple validation
            if (!name || !email || !password) {
                alert('Please fill in all required fields');
                return;
            }
            
            // Check if user already exists
            const users = JSON.parse(localStorage.getItem('users') || '[]');
            if (users.some(user => user.email === email)) {
                alert('User with this email already exists');
                return;
            }
            
            // Create new user
            const newUser = {
                id: Date.now(),
                name,
                email,
                password,
                address,
                joinDate: new Date().toLocaleDateString()
            };
            
            // Save user
            users.push(newUser);
            localStorage.setItem('users', JSON.stringify(users));
            
            // Auto login
            currentUser = newUser;
            localStorage.setItem('currentUser', JSON.stringify(currentUser));
            updateUIForLoggedInUser();
            closeAuthModal();
            alert('Registration successful! You are now logged in.');
        }

        function logout() {
            currentUser = null;
            localStorage.removeItem('currentUser');
            updateUIForLoggedOutUser();
            alert('You have been logged out');
        }

        function updateUIForLoggedInUser() {
            // Update auth buttons
            loginBtn.classList.add('hidden');
            registerBtn.classList.add('hidden');
            userGreeting.classList.remove('hidden');
            usernameDisplay.textContent = currentUser.name;
            
            // Show post form and hide login prompt
            postFormContainer.classList.remove('hidden');
            loginPrompt.classList.add('hidden');
            
            // Show dashboard and messages links
            dashboardLink.classList.remove('hidden');
            messagesLink.classList.remove('hidden');
            usersLink.classList.remove('hidden');
            dashboardLinkMobile.classList.remove('hidden');
            messagesLinkMobile.classList.remove('hidden');
            usersLinkMobile.classList.remove('hidden');
            
            // Update dashboard if visible
            if (window.location.hash === '#dashboard') {
                showDashboard();
            }
            
            // Load user's posts
            loadUserPosts();
            
            // Load conversations
            loadConversations();
            
            // Load users directory
            loadUsers();
            
            // Check for notifications
            checkNotifications();
        }

        function updateUIForLoggedOutUser() {
            // Update auth buttons
            loginBtn.classList.remove('hidden');
            registerBtn.classList.remove('hidden');
            userGreeting.classList.add('hidden');
            
            // Hide post form and show login prompt
            postFormContainer.classList.add('hidden');
            loginPrompt.classList.remove('hidden');
            
            // Hide dashboard and messages links
            dashboardLink.classList.add('hidden');
            messagesLink.classList.add('hidden');
            usersLink.classList.add('hidden');
            dashboardLinkMobile.classList.add('hidden');
            messagesLinkMobile.classList.add('hidden');
            usersLinkMobile.classList.add('hidden');
            
            // Hide dashboard and messages if visible
            dashboardSection.classList.add('hidden');
            messagesSection.classList.add('hidden');
            usersSection.classList.add('hidden');
            
            // Hide mobile menu
            mobileNav.classList.remove('active');
        }

        function toggleMobileMenu() {
            mobileNav.classList.toggle('active');
        }

        function handleMediaUpload(e) {
            const files = e.target.files;
            handleFiles(files);
        }

        function handleMediaDrop(e) {
            e.preventDefault();
            mediaDropArea.style.borderColor = '#ccc';
            mediaDropArea.style.backgroundColor = 'transparent';
            
            const files = e.dataTransfer.files;
            handleFiles(files);
        }

        function handleFiles(files) {
            for (let i = 0; i < files.length; i++) {
                const file = files[i];
                const fileType = file.type.split('/')[0];
                
                if (fileType === 'image' || fileType === 'video') {
                    mediaFiles.push(file);
                    
                    const reader = new FileReader();
                    reader.onload = function(e) {
                        const previewItem = document.createElement('div');
                        previewItem.className = 'preview-item';
                        
                        if (fileType === 'image') {
                            previewItem.innerHTML = `
                                <img src="${e.target.result}" alt="Preview">
                                <button class="remove-media" data-index="${mediaFiles.length - 1}">&times;</button>
                            `;
                        } else {
                            previewItem.innerHTML = `
                                <video src="${e.target.result}" controls></video>
                                <button class="remove-media" data-index="${mediaFiles.length - 1}">&times;</button>
                            `;
                        }
                        
                        mediaPreview.appendChild(previewItem);
                        
                        // Add event listener to remove button
                        previewItem.querySelector('.remove-media').addEventListener('click', function() {
                            const index = parseInt(this.getAttribute('data-index'));
                            mediaFiles.splice(index, 1);
                            mediaPreview.removeChild(previewItem);
                            
                            // Update data-index for remaining items
                            const removeButtons = mediaPreview.querySelectorAll('.remove-media');
                            removeButtons.forEach((btn, idx) => {
                                btn.setAttribute('data-index', idx);
                            });
                        });
                    };
                    
                    reader.readAsDataURL(file);
                } else {
                    alert('Please only upload images or videos');
                }
            }
        }

        function loadPosts() {
            // Clear posts container
            postsContainer.innerHTML = '';
            
            // Get posts from localStorage
            const posts = JSON.parse(localStorage.getItem('posts')) || [];
            
            if (posts.length === 0) {
                postsContainer.innerHTML = '<p>No posts yet. Be the first to share something with the community!</p>';
                return;
            }
            
            // Display each post
            posts.forEach(post => {
                const postElement = createPostElement(post);
                postsContainer.appendChild(postElement);
            });
        }

        function createPostElement(post) {
            const postDiv = document.createElement('div');
            postDiv.className = 'post-card';
            
            const categoryClass = `category-${post.category}`;
            
            let mediaHTML = '';
            if (post.media && post.media.length > 0) {
                mediaHTML = '<div class="post-media">';
                post.media.forEach(media => {
                    if (media.type === 'image') {
                        mediaHTML += `<img src="${media.url}" alt="Post image">`;
                    } else if (media.type === 'video') {
                        mediaHTML += `<video src="${media.url}" controls></video>`;
                    }
                });
                mediaHTML += '</div>';
            }
            
            // Check if current user is the author
            const isCurrentUserAuthor = currentUser && post.authorId === currentUser.id;
            
            // Check if current user has liked the post
            const isLiked = currentUser && post.likedBy && post.likedBy.includes(currentUser.id);
            
            // Check if current user has saved the post
            const savedPosts = JSON.parse(localStorage.getItem(`savedPosts_${currentUser ? currentUser.id : ''}`)) || [];
            const isSaved = savedPosts.includes(post.id);
            
            postDiv.innerHTML = `
                <h3 class="post-title">${post.title}</h3>
                ${mediaHTML}
                <p class="post-content">${post.content}</p>
                <div class="post-meta">
                    <span class="post-author">By ${post.author}</span>
                    <span class="post-date">${post.date}</span>
                </div>
                <span class="post-category ${categoryClass}">${post.category}</span>
                
                <!-- Post Actions -->
                <div class="post-actions">
                    <button class="action-btn like-btn ${isLiked ? 'liked' : ''}" data-post-id="${post.id}">
                        <i class="fas fa-heart"></i>
                        <span class="like-count">${post.likes || 0}</span>
                    </button>
                    <button class="action-btn comment-btn" data-post-id="${post.id}">
                        <i class="fas fa-comment"></i>
                        <span class="comment-count">${post.comments ? post.comments.length : 0}</span>
                    </button>
                    <button class="action-btn save-btn ${isSaved ? 'saved' : ''}" data-post-id="${post.id}">
                        <i class="fas fa-bookmark"></i>
                        <span>Save</span>
                    </button>
                    <button class="action-btn share-btn" data-post-id="${post.id}">
                        <i class="fas fa-share-alt"></i>
                        <span>Share</span>
                    </button>
                    ${isCurrentUserAuthor ? `
                        <button class="action-btn delete-btn" data-post-id="${post.id}">
                            <i class="fas fa-trash"></i>
                            <span>Delete</span>
                        </button>
                    ` : ''}
                </div>
                
                <!-- Comments Section -->
                <div class="comments-section" id="comments-${post.id}" style="display: none;">
                    ${post.comments && post.comments.length > 0 ? 
                        post.comments.map(comment => `
                            <div class="comment">
                                <div class="comment-author">${comment.author}</div>
                                <div class="comment-content">${comment.content}</div>
                                ${currentUser && (currentUser.id === comment.authorId || currentUser.id === post.authorId) ? `
                                    <div class="comment-actions">
                                        <button class="delete-comment-btn" data-post-id="${post.id}" data-comment-id="${comment.id}">
                                            <i class="fas fa-trash"></i>
                                        </button>
                                    </div>
                                ` : ''}
                            </div>
                        `).join('') : 
                        '<p>No comments yet.</p>'
                    }
                    ${currentUser ? `
                        <div class="comment-input">
                            <input type="text" placeholder="Add a comment..." id="comment-input-${post.id}">
                            <button class="comment-btn" data-post-id="${post.id}">
                                <i class="fas fa-paper-plane"></i>
                            </button>
                        </div>
                    ` : ''}
                </div>
                
                ${!isCurrentUserAuthor && currentUser ? `<button class="message-author-btn" data-author-id="${post.authorId}" data-author-name="${post.author}">Message ${post.author}</button>` : ''}
            `;
            
            // Add event listeners to action buttons
            if (currentUser) {
                // Like button
                const likeBtn = postDiv.querySelector('.like-btn');
                likeBtn.addEventListener('click', function() {
                    const postId = parseInt(this.getAttribute('data-post-id'));
                    toggleLike(postId);
                });
                
                // Comment button
                const commentBtn = postDiv.querySelector('.comment-btn');
                commentBtn.addEventListener('click', function() {
                    const postId = parseInt(this.getAttribute('data-post-id'));
                    const commentsSection = document.getElementById(`comments-${postId}`);
                    commentsSection.style.display = commentsSection.style.display === 'none' ? 'block' : 'none';
                });
                
                // Save button
                const saveBtn = postDiv.querySelector('.save-btn');
                saveBtn.addEventListener('click', function() {
                    const postId = parseInt(this.getAttribute('data-post-id'));
                    toggleSavePost(postId);
                });
                
                // Share button
                const shareBtn = postDiv.querySelector('.share-btn');
                shareBtn.addEventListener('click', function() {
                    const postId = parseInt(this.getAttribute('data-post-id'));
                    showShareModal(postId);
                });
                
                // Delete button (if present)
                const deleteBtn = postDiv.querySelector('.delete-btn');
                if (deleteBtn) {
                    deleteBtn.addEventListener('click', function() {
                        const postId = parseInt(this.getAttribute('data-post-id'));
                        showDeleteConfirmation('post', postId);
                    });
                }
                
                // Comment input
                const commentInput = postDiv.querySelector(`#comment-input-${post.id}`);
                if (commentInput) {
                    const commentSubmitBtn = postDiv.querySelector('.comment-btn[data-post-id]');
                    commentSubmitBtn.addEventListener('click', function() {
                        const postId = parseInt(this.getAttribute('data-post-id'));
                        const content = commentInput.value.trim();
                        if (content) {
                            addComment(postId, content);
                            commentInput.value = '';
                        }
                    });
                    
                    commentInput.addEventListener('keypress', function(e) {
                        if (e.key === 'Enter') {
                            const postId = parseInt(this.getAttribute('data-post-id'));
                            const content = this.value.trim();
                            if (content) {
                                addComment(postId, content);
                                this.value = '';
                            }
                        }
                    });
                }
                
                // Delete comment buttons
                const deleteCommentBtns = postDiv.querySelectorAll('.delete-comment-btn');
                deleteCommentBtns.forEach(btn => {
                    btn.addEventListener('click', function() {
                        const postId = parseInt(this.getAttribute('data-post-id'));
                        const commentId = parseInt(this.getAttribute('data-comment-id'));
                        showDeleteConfirmation('comment', postId, commentId);
                    });
                });
            }
            
            // Add event listener to message button
            if (!isCurrentUserAuthor && currentUser) {
                const messageBtn = postDiv.querySelector('.message-author-btn');
                messageBtn.addEventListener('click', function() {
                    const authorId = this.getAttribute('data-author-id');
                    const authorName = this.getAttribute('data-author-name');
                    startNewConversation(authorId, authorName);
                });
            }
            
            return postDiv;
        }

        function showDeleteConfirmation(type, postId, commentId = null) {
            confirmationModal.classList.remove('hidden');
            
            if (type === 'post') {
                confirmationTitle.textContent = 'Delete Post';
                confirmationMessage.textContent = 'Are you sure you want to delete this post? This action cannot be undone.';
                pendingDeleteAction = { type: 'post', postId };
            } else if (type === 'comment') {
                confirmationTitle.textContent = 'Delete Comment';
                confirmationMessage.textContent = 'Are you sure you want to delete this comment?';
                pendingDeleteAction = { type: 'comment', postId, commentId };
            }
        }

        function executePendingDelete() {
            if (!pendingDeleteAction) return;
            
            if (pendingDeleteAction.type === 'post') {
                deletePost(pendingDeleteAction.postId);
            } else if (pendingDeleteAction.type === 'comment') {
                deleteComment(pendingDeleteAction.postId, pendingDeleteAction.commentId);
            }
            
            confirmationModal.classList.add('hidden');
            pendingDeleteAction = null;
        }

        function deletePost(postId) {
            // Get posts from localStorage
            const posts = JSON.parse(localStorage.getItem('posts')) || [];
            
            // Find and remove the post
            const postIndex = posts.findIndex(p => p.id === postId);
            if (postIndex === -1) return;
            
            // Remove the post
            posts.splice(postIndex, 1);
            
            // Save updated posts
            localStorage.setItem('posts', JSON.stringify(posts));
            
            // Remove from saved posts of all users
            const users = JSON.parse(localStorage.getItem('users')) || [];
            users.forEach(user => {
                const savedPosts = JSON.parse(localStorage.getItem(`savedPosts_${user.id}`)) || [];
                const savedIndex = savedPosts.indexOf(postId);
                if (savedIndex !== -1) {
                    savedPosts.splice(savedIndex, 1);
                    localStorage.setItem(`savedPosts_${user.id}`, JSON.stringify(savedPosts));
                }
            });
            
            // Reload posts
            loadPosts();
            
            // Update user's posts in dashboard
            if (dashboardSection.classList.contains('hidden') === false) {
                loadUserPosts();
            }
            
            alert('Post deleted successfully!');
        }

        function deleteComment(postId, commentId) {
            // Get posts from localStorage
            const posts = JSON.parse(localStorage.getItem('posts')) || [];
            
            // Find the post
            const postIndex = posts.findIndex(p => p.id === postId);
            if (postIndex === -1) return;
            
            const post = posts[postIndex];
            
            // Find and remove the comment
            if (post.comments) {
                const commentIndex = post.comments.findIndex(c => c.id === commentId);
                if (commentIndex !== -1) {
                    post.comments.splice(commentIndex, 1);
                    
                    // Save updated posts
                    localStorage.setItem('posts', JSON.stringify(posts));
                    
                    // Reload posts
                    loadPosts();
                    
                    alert('Comment deleted successfully!');
                }
            }
        }

        function toggleLike(postId) {
            if (!currentUser) return;
            
            const posts = JSON.parse(localStorage.getItem('posts')) || [];
            const postIndex = posts.findIndex(p => p.id === postId);
            
            if (postIndex === -1) return;
            
            const post = posts[postIndex];
            
            // Initialize likes and likedBy if they don't exist
            if (!post.likes) post.likes = 0;
            if (!post.likedBy) post.likedBy = [];
            
            // Check if user already liked the post
            const userIndex = post.likedBy.indexOf(currentUser.id);
            
            if (userIndex === -1) {
                // Like the post
                post.likes++;
                post.likedBy.push(currentUser.id);
                
                // Create notification for post author
                if (post.authorId !== currentUser.id) {
                    createNotification(post.authorId, 'like', `${currentUser.name} liked your post: "${post.title}"`, postId);
                }
            } else {
                // Unlike the post
                post.likes--;
                post.likedBy.splice(userIndex, 1);
            }
            
            // Save updated posts
            localStorage.setItem('posts', JSON.stringify(posts));
            
            // Reload posts
            loadPosts();
            
            // Update notifications
            checkNotifications();
        }

        function toggleSavePost(postId) {
            if (!currentUser) return;
            
            const savedPosts = JSON.parse(localStorage.getItem(`savedPosts_${currentUser.id}`)) || [];
            const postIndex = savedPosts.indexOf(postId);
            
            if (postIndex === -1) {
                // Save the post
                savedPosts.push(postId);
            } else {
                // Unsave the post
                savedPosts.splice(postIndex, 1);
            }
            
            // Save updated saved posts
            localStorage.setItem(`savedPosts_${currentUser.id}`, JSON.stringify(savedPosts));
            
            // Reload posts
            loadPosts();
            
            // Update saved posts in dashboard
            if (dashboardSection.classList.contains('hidden') === false) {
                loadSavedPosts();
            }
        }

        function showShareModal(postId) {
            currentPostToShare = postId;
            shareModal.classList.remove('hidden');
        }

        function handleShare(e) {
            const platform = e.currentTarget.getAttribute('data-platform');
            const posts = JSON.parse(localStorage.getItem('posts')) || [];
            const post = posts.find(p => p.id === currentPostToShare);
            
            if (!post) return;
            
            const postUrl = `${window.location.origin}${window.location.pathname}#post-${post.id}`;
            const text = `Check out this post on Arnama Connect: "${post.title}"`;
            
            let shareUrl = '';
            
            switch(platform) {
                case 'whatsapp':
                    shareUrl = `https://wa.me/?text=${encodeURIComponent(text + ' ' + postUrl)}`;
                    break;
                case 'facebook':
                    shareUrl = `https://www.facebook.com/sharer/sharer.php?u=${encodeURIComponent(postUrl)}`;
                    break;
                case 'twitter':
                    shareUrl = `https://twitter.com/intent/tweet?text=${encodeURIComponent(text)}&url=${encodeURIComponent(postUrl)}`;
                    break;
                case 'instagram':
                    // Instagram doesn't support direct sharing via URL
                    alert('To share on Instagram, copy the link and paste it in your Instagram post');
                    copyToClipboard(postUrl);
                    shareModal.classList.add('hidden');
                    return;
                case 'telegram':
                    shareUrl = `https://t.me/share/url?url=${encodeURIComponent(postUrl)}&text=${encodeURIComponent(text)}`;
                    break;
                case 'linkedin':
                    shareUrl = `https://www.linkedin.com/sharing/share-offsite/?url=${encodeURIComponent(postUrl)}`;
                    break;
                case 'copy':
                    copyToClipboard(postUrl);
                    alert('Link copied to clipboard!');
                    shareModal.classList.add('hidden');
                    return;
            }
            
            if (shareUrl) {
                window.open(shareUrl, '_blank', 'width=600,height=400');
            }
            
            shareModal.classList.add('hidden');
        }

        function copyToClipboard(text) {
            const textarea = document.createElement('textarea');
            textarea.value = text;
            document.body.appendChild(textarea);
            textarea.select();
            document.execCommand('copy');
            document.body.removeChild(textarea);
        }

        function addComment(postId, content) {
            if (!currentUser) return;
            
            const posts = JSON.parse(localStorage.getItem('posts')) || [];
            const postIndex = posts.findIndex(p => p.id === postId);
            
            if (postIndex === -1) return;
            
            const post = posts[postIndex];
            
            // Initialize comments if they don't exist
            if (!post.comments) post.comments = [];
            
            // Add new comment
            const newComment = {
                id: Date.now(),
                author: currentUser.name,
                authorId: currentUser.id,
                content: content,
                date: new Date().toLocaleDateString()
            };
            
            post.comments.push(newComment);
            
            // Save updated posts
            localStorage.setItem('posts', JSON.stringify(posts));
            
            // Create notification for post author
            if (post.authorId !== currentUser.id) {
                createNotification(post.authorId, 'comment', `${currentUser.name} commented on your post: "${post.title}"`, postId);
            }
            
            // Reload posts
            loadPosts();
            
            // Update notifications
            checkNotifications();
        }

        function createNotification(userId, type, message, postId) {
            const notifications = JSON.parse(localStorage.getItem(`notifications_${userId}`)) || [];
            
            const newNotification = {
                id: Date.now(),
                type: type,
                message: message,
                postId: postId,
                read: false,
                time: new Date().toISOString()
            };
            
            notifications.unshift(newNotification);
            localStorage.setItem(`notifications_${userId}`, JSON.stringify(notifications));
        }

        function handlePostSubmit(e) {
            e.preventDefault();
            
            if (!currentUser) {
                alert('Please log in to post');
                return;
            }
            
            const title = document.getElementById('post-title').value;
            const content = document.getElementById('post-content').value;
            const category = document.getElementById('post-category').value;
            
            // Create new post
            const newPost = {
                id: Date.now(),
                title,
                content,
                category,
                author: currentUser.name,
                authorId: currentUser.id,
                date: new Date().toLocaleDateString(),
                likes: 0,
                likedBy: [],
                comments: [],
                media: []
            };
            
            // Process media files
            if (mediaFiles.length > 0) {
                // In a real app, you would upload these to a server
                // For this demo, we'll just use placeholder URLs
                mediaFiles.forEach(file => {
                    const fileType = file.type.split('/')[0];
                    newPost.media.push({
                        type: fileType,
                        url: URL.createObjectURL(file)
                    });
                });
            }
            
            // Save post
            const posts = JSON.parse(localStorage.getItem('posts') || '[]');
            posts.unshift(newPost); // Add to beginning of array
            localStorage.setItem('posts', JSON.stringify(posts));
            
            // Reload posts
            loadPosts();
            
            // Clear form and media
            postForm.reset();
            mediaFiles = [];
            mediaPreview.innerHTML = '';
            
            // Add to user's posts
            loadUserPosts();
            
            alert('Your post has been published!');
        }

        function showDashboard() {
            // Show dashboard section
            dashboardSection.classList.remove('hidden');
            
            // Hide messages section
            messagesSection.classList.add('hidden');
            usersSection.classList.add('hidden');
            
            // Scroll to dashboard
            dashboardSection.scrollIntoView({ behavior: 'smooth' });
            
            // Update profile info
            if (currentUser) {
                profileName.textContent = currentUser.name;
                profileEmail.textContent = currentUser.email;
                joinDate.textContent = currentUser.joinDate;
                
                // Update post count
                const posts = JSON.parse(localStorage.getItem('posts') || '[]');
                const userPosts = posts.filter(post => post.authorId === currentUser.id);
                document.getElementById('post-count').textContent = userPosts.length;
                
                // Update message count
                const conversations = JSON.parse(localStorage.getItem(`conversations_${currentUser.id}`)) || [];
                document.getElementById('message-count').textContent = conversations.length;
            }
            
            // Load user's posts
            loadUserPosts();
            
            // Load saved posts
            loadSavedPosts();
            
            // Hide mobile menu
            mobileNav.classList.remove('active');
        }

        function showMessages() {
            // Show messages section
            messagesSection.classList.remove('hidden');
            
            // Hide dashboard section
            dashboardSection.classList.add('hidden');
            usersSection.classList.add('hidden');
            
            // Scroll to messages
            messagesSection.scrollIntoView({ behavior: 'smooth' });
            
            // Load conversations
            loadConversations();
            
            // Hide mobile menu
            mobileNav.classList.remove('active');
        }

        function showUsers() {
            // Show users section
            usersSection.classList.remove('hidden');
            
            // Hide dashboard section
            dashboardSection.classList.add('hidden');
            messagesSection.classList.add('hidden');
            
            // Scroll to users
            usersSection.scrollIntoView({ behavior: 'smooth' });
            
            // Load users
            loadUsers();
            
            // Hide mobile menu
            mobileNav.classList.remove('active');
        }

        function loadUserPosts() {
            if (!currentUser) return;
            
            // Clear user posts container
            userPostsContainer.innerHTML = '';
            
            // Get posts from localStorage
            const posts = JSON.parse(localStorage.getItem('posts') || '[]');
            
            // Filter user's posts
            const userPosts = posts.filter(post => post.authorId === currentUser.id);
            
            if (userPosts.length === 0) {
                userPostsContainer.innerHTML = '<p>You haven\'t made any posts yet.</p>';
                return;
            }
            
            // Display user's posts
            userPosts.forEach(post => {
                const postElement = createPostElement(post);
                userPostsContainer.appendChild(postElement);
            });
        }

        function loadSavedPosts() {
            if (!currentUser) return;
            
            // Clear saved posts container
            savedPostsContainer.innerHTML = '';
            
            // Get saved posts from localStorage
            const savedPosts = JSON.parse(localStorage.getItem(`savedPosts_${currentUser.id}`)) || [];
            
            if (savedPosts.length === 0) {
                savedPostsContainer.innerHTML = '<p>You haven\'t saved any posts yet.</p>';
                return;
            }
            
            // Get all posts
            const posts = JSON.parse(localStorage.getItem('posts') || '[]');
            
            // Filter saved posts
            const savedPostObjects = posts.filter(post => savedPosts.includes(post.id));
            
            // Display saved posts
            savedPostObjects.forEach(post => {
                const postElement = createPostElement(post);
                savedPostsContainer.appendChild(postElement);
            });
        }

        function loadConversations() {
            if (!currentUser) return;
            
            // Clear conversations list
            conversationsList.innerHTML = '';
            
            // Get conversations from localStorage
            const conversations = JSON.parse(localStorage.getItem(`conversations_${currentUser.id}`)) || [];
            
            if (conversations.length === 0) {
                conversationsList.innerHTML = '<p>No conversations yet. Message someone to start a conversation!</p>';
                return;
            }
            
            // Display each conversation
            conversations.forEach(conversation => {
                const conversationElement = document.createElement('div');
                conversationElement.className = 'conversation-item';
                conversationElement.setAttribute('data-id', conversation.id);
                
                conversationElement.innerHTML = `
                    <div class="conversation-header">
                        <span class="conversation-name">${conversation.otherUserName}</span>
                        <span class="conversation-time">${formatTime(conversation.lastMessageTime)}</span>
                    </div>
                    <div class="conversation-preview">${conversation.lastMessage}</div>
                `;
                
                // Add click event to load conversation
                conversationElement.addEventListener('click', () => {
                    loadConversation(conversation.id);
                    // Remove active class from all conversations
                    document.querySelectorAll('.conversation-item').forEach(item => {
                        item.classList.remove('active');
                    });
                    // Add active class to clicked conversation
                    conversationElement.classList.add('active');
                });
                
                conversationsList.appendChild(conversationElement);
            });
        }

        function loadUsers() {
            if (!currentUser) return;
            
            // Clear users grid
            usersGrid.innerHTML = '';
            
            // Get users from localStorage
            const users = JSON.parse(localStorage.getItem('users') || '[]');
            
            // Filter out current user
            const otherUsers = users.filter(user => user.id !== currentUser.id);
            
            if (otherUsers.length === 0) {
                usersGrid.innerHTML = '<p>No other users found.</p>';
                return;
            }
            
            // Display each user
            otherUsers.forEach(user => {
                const userElement = document.createElement('div');
                userElement.className = 'user-card';
                
                userElement.innerHTML = `
                    <div class="user-avatar">
                        ${user.name.charAt(0).toUpperCase()}
                    </div>
                    <div class="user-name">${user.name}</div>
                    <div class="user-email">${user.email}</div>
                    <button class="message-user-btn" data-user-id="${user.id}" data-user-name="${user.name}">Message</button>
                `;
                
                // Add event listener to message button
                const messageBtn = userElement.querySelector('.message-user-btn');
                messageBtn.addEventListener('click', function() {
                    const userId = this.getAttribute('data-user-id');
                    const userName = this.getAttribute('data-user-name');
                    startNewConversation(userId, userName);
                });
                
                usersGrid.appendChild(userElement);
            });
        }

        function searchUsers() {
            const searchTerm = userSearchInput.value.toLowerCase().trim();
            
            if (!searchTerm) {
                loadUsers();
                return;
            }
            
            // Get users from localStorage
            const users = JSON.parse(localStorage.getItem('users') || '[]');
            
            // Filter users based on search term
            const filteredUsers = users.filter(user => 
                user.id !== currentUser.id && 
                (user.name.toLowerCase().includes(searchTerm) || 
                 user.email.toLowerCase().includes(searchTerm))
            );
            
            // Clear users grid
            usersGrid.innerHTML = '';
            
            if (filteredUsers.length === 0) {
                usersGrid.innerHTML = '<p>No users found matching your search.</p>';
                return;
            }
            
            // Display filtered users
            filteredUsers.forEach(user => {
                const userElement = document.createElement('div');
                userElement.className = 'user-card';
                
                userElement.innerHTML = `
                    <div class="user-avatar">
                        ${user.name.charAt(0).toUpperCase()}
                    </div>
                    <div class="user-name">${user.name}</div>
                    <div class="user-email">${user.email}</div>
                    <button class="message-user-btn" data-user-id="${user.id}" data-user-name="${user.name}">Message</button>
                `;
                
                // Add event listener to message button
                const messageBtn = userElement.querySelector('.message-user-btn');
                messageBtn.addEventListener('click', function() {
                    const userId = this.getAttribute('data-user-id');
                    const userName = this.getAttribute('data-user-name');
                    startNewConversation(userId, userName);
                });
                
                usersGrid.appendChild(userElement);
            });
        }

        function startNewConversation(userId, userName) {
            // Check if conversation already exists
            const conversations = JSON.parse(localStorage.getItem(`conversations_${currentUser.id}`)) || [];
            const existingConversation = conversations.find(c => c.otherUserId == userId);
            
            if (existingConversation) {
                // Load existing conversation
                loadConversation(existingConversation.id);
                showMessages();
                return;
            }
            
            // Create new conversation
            const newConversation = {
                id: Date.now(),
                otherUserId: userId,
                otherUserName: userName,
                lastMessage: "Start a conversation",
                lastMessageTime: new Date().toISOString()
            };
            
            // Save conversation
            conversations.push(newConversation);
            localStorage.setItem(`conversations_${currentUser.id}`, JSON.stringify(conversations));
            
            // Also create conversation for the other user
            const otherUserConversations = JSON.parse(localStorage.getItem(`conversations_${userId}`)) || [];
            otherUserConversations.push({
                id: newConversation.id,
                otherUserId: currentUser.id,
                otherUserName: currentUser.name,
                lastMessage: "Start a conversation",
                lastMessageTime: new Date().toISOString()
            });
            localStorage.setItem(`conversations_${userId}`, JSON.stringify(otherUserConversations));
            
            // Initialize empty messages for this conversation
            localStorage.setItem(`messages_${newConversation.id}`, JSON.stringify([]));
            
            // Load the new conversation
            loadConversation(newConversation.id);
            showMessages();
        }

        function loadConversation(conversationId) {
            currentConversationId = conversationId;
            
            // Get messages from localStorage
            const messages = JSON.parse(localStorage.getItem(`messages_${conversationId}`)) || [];
            
            // Clear chat messages
            chatMessages.innerHTML = '';
            
            // Find the conversation to get participant info
            const conversations = JSON.parse(localStorage.getItem(`conversations_${currentUser.id}`)) || [];
            const conversation = conversations.find(c => c.id === conversationId);
            
            if (!conversation) return;
            
            // Update chat header
            chatHeader.innerHTML = `<h3>${conversation.otherUserName}</h3>`;
            
            // Show chat input
            chatInput.classList.remove('hidden');
            
            // Display each message
            messages.forEach(message => {
                const messageElement = document.createElement('div');
                messageElement.className = `message ${message.senderId === currentUser.id ? 'sent' : 'received'}`;
                
                messageElement.innerHTML = `
                    <div class="message-content">${message.content}</div>
                    <div class="message-time">${formatTime(message.time)}</div>
                `;
                
                chatMessages.appendChild(messageElement);
            });
            
            // Scroll to bottom of chat
            chatMessages.scrollTop = chatMessages.scrollHeight;
        }

        function sendMessage() {
            if (!currentConversationId || !messageInput.value.trim()) return;
            
            const messageContent = messageInput.value.trim();
            
            // Create new message
            const newMessage = {
                senderId: currentUser.id,
                senderName: currentUser.name,
                content: messageContent,
                time: new Date().toISOString()
            };
            
            // Get existing messages
            const messages = JSON.parse(localStorage.getItem(`messages_${currentConversationId}`)) || [];
            
            // Add new message
            messages.push(newMessage);
            
            // Save messages
            localStorage.setItem(`messages_${currentConversationId}`, JSON.stringify(messages));
            
            // Update conversation last message
            const conversations = JSON.parse(localStorage.getItem(`conversations_${currentUser.id}`)) || [];
            const conversationIndex = conversations.findIndex(c => c.id === currentConversationId);
            if (conversationIndex !== -1) {
                conversations[conversationIndex].lastMessage = messageContent;
                conversations[conversationIndex].lastMessageTime = newMessage.time;
                localStorage.setItem(`conversations_${currentUser.id}`, JSON.stringify(conversations));
            }
            
            // Also update for the other user
            const otherUserId = conversations[conversationIndex].otherUserId;
            const otherUserConversations = JSON.parse(localStorage.getItem(`conversations_${otherUserId}`)) || [];
            const otherUserConversationIndex = otherUserConversations.findIndex(c => c.id === currentConversationId);
            if (otherUserConversationIndex !== -1) {
                otherUserConversations[otherUserConversationIndex].lastMessage = messageContent;
                otherUserConversations[otherUserConversationIndex].lastMessageTime = newMessage.time;
                localStorage.setItem(`conversations_${otherUserId}`, JSON.stringify(otherUserConversations));
                
                // Create notification for the other user
                createNotification(otherUserId, 'message', `${currentUser.name} sent you a message`, null);
            }
            
            // Reload conversation
            loadConversation(currentConversationId);
            
            // Clear input
            messageInput.value = '';
            
            // Update notifications
            checkNotifications();
        }

        function checkNotifications() {
            if (!currentUser) return;
            
            // Get user's notifications
            const notifications = JSON.parse(localStorage.getItem(`notifications_${currentUser.id}`)) || [];
            
            // Count unread notifications
            const unreadCount = notifications.filter(notification => !notification.read).length;
            
            // Update notification count
            if (unreadCount > 0) {
                notificationCount.textContent = unreadCount;
                notificationCount.classList.remove('hidden');
                
                // Update notifications panel
                updateNotificationsPanel(notifications);
            } else {
                notificationCount.classList.add('hidden');
                notificationsPanel.innerHTML = `
                    <div class="notification-header">
                        <h4>Notifications</h4>
                        <button class="clear-notifications" id="clear-notifications">Clear All</button>
                    </div>
                    <div class="notification-item">
                        <p>No new notifications</p>
                    </div>
                `;
            }
        }

        function updateNotificationsPanel(notifications) {
            let notificationsHTML = `
                <div class="notification-header">
                    <h4>Notifications</h4>
                    <button class="clear-notifications" id="clear-notifications">Clear All</button>
                </div>
            `;
            
            notifications.forEach(notification => {
                const typeClass = `type-${notification.type}`;
                const unreadClass = notification.read ? '' : 'unread';
                
                notificationsHTML += `
                    <div class="notification-item ${unreadClass}" data-id="${notification.id}">
                        <span class="notification-type ${typeClass}">${notification.type}</span>
                        <div class="notification-message">${notification.message}</div>
                        <div class="notification-time">${formatTime(notification.time)}</div>
                    </div>
                `;
            });
            
            notificationsPanel.innerHTML = notificationsHTML;
            
            // Re-add event listener to clear button
            document.getElementById('clear-notifications').addEventListener('click', clearAllNotifications);
            
            // Add event listeners to notification items
            document.querySelectorAll('.notification-item').forEach(item => {
                item.addEventListener('click', function() {
                    const notificationId = parseInt(this.getAttribute('data-id'));
                    markNotificationAsRead(notificationId);
                });
            });
        }

        function markNotificationAsRead(notificationId) {
            if (!currentUser) return;
            
            const notifications = JSON.parse(localStorage.getItem(`notifications_${currentUser.id}`)) || [];
            const notificationIndex = notifications.findIndex(n => n.id === notificationId);
            
            if (notificationIndex !== -1) {
                notifications[notificationIndex].read = true;
                localStorage.setItem(`notifications_${currentUser.id}`, JSON.stringify(notifications));
                checkNotifications();
            }
        }

        function toggleNotifications() {
            notificationsPanel.classList.toggle('active');
        }

        function clearAllNotifications() {
            if (!currentUser) return;
            
            // Get user's notifications
            const notifications = JSON.parse(localStorage.getItem(`notifications_${currentUser.id}`)) || [];
            
            // Mark all as read
            notifications.forEach(notification => {
                notification.read = true;
            });
            
            // Save updated notifications
            localStorage.setItem(`notifications_${currentUser.id}`, JSON.stringify(notifications));
            
            // Update UI
            checkNotifications();
            
            // Close notifications panel
            notificationsPanel.classList.remove('active');
        }

        function formatTime(timeString) {
            const date = new Date(timeString);
            return date.toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' });
        }

        // Initialize the page
        window.addEventListener('load', function() {
            // Check if user is logged in
            const savedUser = localStorage.getItem('currentUser');
            if (savedUser) {
                currentUser = JSON.parse(savedUser);
                updateUIForLoggedInUser();
            }
            
            // Load posts
            loadPosts();
        });
    </script>
</body>
</html>
