<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>California Regional Shipping Company | Global Shipping & Logistics</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700;800;900&family=Open+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        /* ========== COMPLETE PROFESSIONAL STYLES ========== */
        
        /* Global Variables */
        :root {
            --primary: #0a2540;
            --secondary: #1c3d5a;
            --accent: #ff6b35;
            --accent-light: #ff8c5a;
            --accent-dark: #e55a2b;
            --light: #f8f9fa;
            --lighter: #ffffff;
            --dark: #0a1929;
            --darker: #061121;
            --success: #2ecc71;
            --warning: #f39c12;
            --danger: #e74c3c;
            --info: #3498db;
            --border: #e1e8ed;
            --border-light: #f0f4f8;
            --shadow-lg: 0 20px 40px rgba(0, 0, 0, 0.12);
            --shadow-md: 0 10px 25px rgba(0, 0, 0, 0.08);
            --shadow-sm: 0 5px 15px rgba(0, 0, 0, 0.05);
            --radius: 16px;
            --radius-sm: 8px;
            --transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.1);
            --transition-fast: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Open Sans', sans-serif;
            line-height: 1.8;
            color: #444;
            background: linear-gradient(135deg, #f8f9fa 0%, #f0f4f8 100%);
            min-height: 100vh;
            overflow-x: hidden;
        }

        h1, h2, h3, h4, h5, h6 {
            font-family: 'Montserrat', sans-serif;
            font-weight: 800;
            color: var(--primary);
            letter-spacing: -0.5px;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 30px;
        }

        /* ========== ADMIN PANEL ========== */
        .admin-panel {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 9999;
            background: linear-gradient(135deg, var(--darker) 0%, var(--dark) 100%);
            color: white;
            padding: 12px;
            border-radius: var(--radius);
            box-shadow: var(--shadow-lg);
            border: 2px solid var(--accent);
            display: none; /* Hidden by default - only visible to you */
        }

        .admin-toggle {
            background: linear-gradient(135deg, var(--accent) 0%, var(--accent-dark) 100%);
            color: white;
            border: none;
            padding: 12px 24px;
            border-radius: var(--radius-sm);
            font-weight: 700;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 10px;
            transition: var(--transition);
            letter-spacing: 0.5px;
        }

        .admin-toggle:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(255, 107, 53, 0.25);
        }

        .admin-panel-content {
            display: none;
            position: absolute;
            top: calc(100% + 15px);
            right: 0;
            width: 550px;
            background: white;
            color: var(--dark);
            padding: 35px;
            border-radius: var(--radius);
            box-shadow: var(--shadow-lg);
            border: 2px solid var(--accent);
            max-height: 80vh;
            overflow-y: auto;
        }

        .admin-panel.active .admin-panel-content {
            display: block;
            animation: slideDown 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .admin-section {
            margin-bottom: 35px;
            padding-bottom: 25px;
            border-bottom: 2px solid var(--border-light);
        }

        .admin-section:last-child {
            border-bottom: none;
            margin-bottom: 0;
            padding-bottom: 0;
        }

        .admin-section h4 {
            color: var(--primary);
            margin-bottom: 20px;
            padding-bottom: 12px;
            border-bottom: 3px solid var(--accent);
            font-size: 1.3rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .admin-input {
            width: 100%;
            padding: 14px;
            border: 2px solid var(--border);
            border-radius: var(--radius-sm);
            font-size: 1rem;
            margin-bottom: 15px;
            font-family: 'Open Sans', sans-serif;
            background: var(--lighter);
            transition: var(--transition-fast);
        }

        .admin-input:focus {
            border-color: var(--accent);
            outline: none;
            box-shadow: 0 0 0 4px rgba(255, 107, 53, 0.15);
        }

        .admin-btn {
            background: linear-gradient(135deg, var(--accent) 0%, var(--accent-dark) 100%);
            color: white;
            border: none;
            padding: 12px 24px;
            border-radius: var(--radius-sm);
            cursor: pointer;
            font-weight: 700;
            margin-right: 10px;
            margin-bottom: 10px;
            transition: var(--transition);
            display: inline-flex;
            align-items: center;
            gap: 8px;
            font-size: 0.95rem;
        }

        .admin-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(255, 107, 53, 0.25);
        }

        .admin-btn.danger {
            background: linear-gradient(135deg, var(--danger) 0%, #c0392b 100%);
        }

        .admin-btn.success {
            background: linear-gradient(135deg, var(--success) 0%, #27ae60 100%);
        }

        .admin-btn.info {
            background: linear-gradient(135deg, var(--info) 0%, #2980b9 100%);
        }

        .admin-btn.warning {
            background: linear-gradient(135deg, var(--warning) 0%, #d68910 100%);
        }

        .admin-stats {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
            margin-top: 20px;
        }

        .admin-stat-card {
            background: var(--light);
            padding: 15px;
            border-radius: var(--radius-sm);
            text-align: center;
            border: 1px solid var(--border);
        }

        .admin-stat-number {
            font-size: 1.8rem;
            font-weight: 800;
            color: var(--primary);
            margin-bottom: 5px;
        }

        .admin-stat-label {
            font-size: 0.85rem;
            color: #666;
        }

        /* Package Stage Status Colors */
        .status-processing { color: var(--warning); background: rgba(243, 156, 18, 0.1); }
        .status-confirmed { color: var(--info); background: rgba(52, 152, 219, 0.1); }
        .status-pickedup { color: #9b59b6; background: rgba(155, 89, 182, 0.1); }
        .status-intransit { color: var(--primary); background: rgba(10, 37, 64, 0.1); }
        .status-outfordelivery { color: var(--accent); background: rgba(255, 107, 53, 0.1); }
        .status-delivered { color: var(--success); background: rgba(46, 204, 113, 0.1); }
        .status-cancelled { color: var(--danger); background: rgba(231, 76, 60, 0.1); }

        .status-badge {
            display: inline-block;
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 700;
            margin: 2px;
        }

        /* Stage Control Dropdown */
        .stage-control {
            display: flex;
            gap: 10px;
            margin-top: 10px;
        }

        .stage-select {
            flex: 1;
            padding: 8px;
            border: 2px solid var(--border);
            border-radius: var(--radius-sm);
            font-size: 0.9rem;
        }

        /* Date Picker Styling */
        .date-picker {
            width: 100%;
            padding: 14px;
            border: 2px solid var(--border);
            border-radius: var(--radius-sm);
            font-size: 1rem;
            margin-bottom: 15px;
            font-family: 'Open Sans', sans-serif;
            background: var(--lighter);
        }

        .date-picker:focus {
            border-color: var(--accent);
            outline: none;
        }

        /* Transaction History */
        .transaction-history {
            max-height: 200px;
            overflow-y: auto;
            margin-top: 10px;
            padding: 10px;
            background: var(--light);
            border-radius: var(--radius-sm);
            border: 1px solid var(--border);
        }

        .transaction-item {
            padding: 8px;
            border-bottom: 1px solid var(--border-light);
            font-size: 0.85rem;
        }

        .transaction-item:last-child {
            border-bottom: none;
        }

        /* ========== MESSAGING SYSTEM ========== */
        .messaging-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.85);
            backdrop-filter: blur(10px);
            z-index: 10002;
            align-items: center;
            justify-content: center;
            padding: 30px;
            animation: fadeIn 0.5s ease;
        }

        .messaging-modal.active {
            display: flex;
        }

        .messaging-content {
            background: white;
            padding: 40px;
            border-radius: var(--radius);
            max-width: 700px;
            width: 100%;
            position: relative;
            animation: slideUpModal 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            border: 3px solid var(--accent);
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.3);
            max-height: 90vh;
            overflow-y: auto;
        }

        .messaging-header {
            text-align: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 2px solid var(--border);
        }

        .messaging-icon {
            font-size: 3rem;
            color: var(--accent);
            margin-bottom: 15px;
        }

        .message-list {
            max-height: 300px;
            overflow-y: auto;
            margin: 20px 0;
            padding: 15px;
            background: var(--light);
            border-radius: var(--radius-sm);
            border: 1px solid var(--border);
        }

        .message-item {
            padding: 10px;
            margin-bottom: 10px;
            border-radius: var(--radius-sm);
            background: white;
            border: 1px solid var(--border-light);
        }

        .message-item.admin {
            background: rgba(255, 107, 53, 0.05);
            border-left: 4px solid var(--accent);
        }

        .message-item.user {
            background: rgba(52, 152, 219, 0.05);
            border-left: 4px solid var(--info);
        }

        .message-sender {
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 5px;
        }

        .message-text {
            color: #555;
        }

        .message-time {
            font-size: 0.8rem;
            color: #888;
            text-align: right;
            margin-top: 5px;
        }

        /* ========== CODE ENTRY MODAL (FOR MOBILE) ========== */
        .code-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.9);
            backdrop-filter: blur(10px);
            z-index: 10003;
            align-items: center;
            justify-content: center;
            padding: 20px;
            animation: fadeIn 0.3s ease;
        }

        .code-modal.active {
            display: flex;
        }

        .code-content {
            background: white;
            padding: 30px;
            border-radius: var(--radius);
            max-width: 400px;
            width: 100%;
            text-align: center;
            border: 3px solid var(--accent);
            box-shadow: var(--shadow-lg);
        }

        .code-title {
            font-size: 1.5rem;
            color: var(--primary);
            margin-bottom: 10px;
        }

        .code-subtitle {
            color: #666;
            margin-bottom: 20px;
        }

        .code-display {
            font-family: monospace;
            font-size: 2rem;
            letter-spacing: 10px;
            background: var(--light);
            padding: 15px;
            border-radius: var(--radius-sm);
            margin-bottom: 20px;
            border: 2px solid var(--border);
            color: var(--primary);
        }

        .code-keypad {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
            margin-bottom: 20px;
        }

        .code-key {
            background: var(--light);
            border: 2px solid var(--border);
            border-radius: var(--radius-sm);
            padding: 20px;
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
            cursor: pointer;
            transition: var(--transition-fast);
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .code-key:active {
            background: var(--accent);
            color: white;
            transform: scale(0.95);
        }

        .code-key.wide {
            grid-column: span 2;
            background: var(--accent);
            color: white;
            border-color: var(--accent-dark);
        }

        .code-key.wide:active {
            background: var(--accent-dark);
        }

        .code-actions {
            display: flex;
            gap: 10px;
        }

        .code-btn {
            flex: 1;
            padding: 15px;
            border: none;
            border-radius: var(--radius-sm);
            font-weight: 700;
            cursor: pointer;
            transition: var(--transition-fast);
        }

        .code-btn.clear {
            background: var(--danger);
            color: white;
        }

        .code-btn.clear:active {
            background: #c0392b;
        }

        .code-btn.cancel {
            background: #666;
            color: white;
        }

        .code-btn.cancel:active {
            background: #555;
        }

        /* ========== PAYMENT MODAL ========== */
        .payment-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.85);
            backdrop-filter: blur(10px);
            z-index: 10001;
            align-items: center;
            justify-content: center;
            padding: 30px;
            animation: fadeIn 0.5s ease;
        }

        .payment-modal.active {
            display: flex;
        }

        .payment-content {
            background: white;
            padding: 60px;
            border-radius: var(--radius);
            max-width: 700px;
            width: 100%;
            position: relative;
            animation: slideUpModal 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            border: 3px solid var(--accent);
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.3);
            max-height: 90vh;
            overflow-y: auto;
        }

        .payment-header {
            text-align: center;
            margin-bottom: 40px;
            position: relative;
        }

        .payment-header::after {
            content: '';
            position: absolute;
            bottom: -20px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, var(--accent), var(--accent-light));
            border-radius: 2px;
        }

        .payment-icon {
            font-size: 4rem;
            color: var(--accent);
            margin-bottom: 20px;
        }

        .payment-title {
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 15px;
        }

        .payment-subtitle {
            color: #666;
            font-size: 1.2rem;
            margin-bottom: 30px;
        }

        /* ========== PAYMENT OPTIONS ========== */
        .payment-options {
            display: grid;
            grid-template-columns: 1fr;
            gap: 25px;
            margin: 40px 0;
            max-width: 400px;
            margin-left: auto;
            margin-right: auto;
        }

        .payment-option {
            background: var(--light);
            border: 2px solid var(--border);
            border-radius: var(--radius);
            padding: 30px;
            cursor: pointer;
            transition: var(--transition);
            text-align: center;
            position: relative;
        }

        .payment-option:hover {
            transform: translateY(-5px);
            border-color: var(--accent);
            box-shadow: var(--shadow-md);
        }

        .payment-option.selected {
            border-color: var(--accent);
            background: linear-gradient(135deg, rgba(255, 107, 53, 0.05), transparent);
            box-shadow: 0 10px 25px rgba(255, 107, 53, 0.1);
        }

        .payment-option-icon {
            font-size: 3rem;
            margin-bottom: 20px;
            color: var(--accent);
        }

        .payment-option-title {
            font-size: 1.4rem;
            color: var(--primary);
            margin-bottom: 10px;
        }

        .payment-option-desc {
            color: #666;
            font-size: 0.95rem;
            margin-bottom: 20px;
        }

        .payment-option-badge {
            position: absolute;
            top: 15px;
            right: 15px;
            background: var(--accent);
            color: white;
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 700;
        }

        /* ========== PAYMENT DETAILS ========== */
        .payment-details {
            background: linear-gradient(135deg, var(--light) 0%, #f0f4f8 100%);
            padding: 30px;
            border-radius: var(--radius);
            margin: 30px 0;
            border: 2px solid var(--border-light);
        }

        .payment-summary {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 25px;
        }

        .summary-item {
            background: white;
            padding: 20px;
            border-radius: var(--radius-sm);
            border: 1px solid var(--border);
        }

        .summary-label {
            font-size: 0.9rem;
            color: #666;
            margin-bottom: 8px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .summary-value {
            font-weight: 800;
            font-size: 1.4rem;
            color: var(--primary);
        }

        .summary-value.shipping-cost {
            color: var(--accent);
            font-size: 1.8rem;
        }

        .total-amount {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            padding: 25px;
            border-radius: var(--radius);
            text-align: center;
            margin-top: 30px;
        }

        .total-label {
            font-size: 1rem;
            opacity: 0.9;
            margin-bottom: 10px;
        }

        .total-value {
            font-size: 3rem;
            font-weight: 900;
            color: var(--accent);
        }

        /* ========== GIFT CARD PAYMENT SECTION ========== */
        .giftcard-section {
            display: none;
            margin-top: 30px;
            padding: 30px;
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
            border-radius: var(--radius);
            border: 2px solid var(--border);
        }

        .giftcard-section.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }

        .giftcard-header {
            text-align: center;
            margin-bottom: 25px;
        }

        .giftcard-header h3 {
            color: var(--primary);
            font-size: 1.5rem;
        }

        .giftcard-options {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 25px 0;
        }

        .giftcard-option {
            background: white;
            padding: 25px;
            border-radius: var(--radius);
            border: 2px solid var(--border);
            cursor: pointer;
            transition: var(--transition);
            text-align: center;
        }

        .giftcard-option:hover {
            transform: translateY(-5px);
            border-color: var(--accent);
            box-shadow: var(--shadow-md);
        }

        .giftcard-option.selected {
            border-color: var(--accent);
            background: linear-gradient(135deg, rgba(255, 107, 53, 0.05), transparent);
        }

        .giftcard-icon {
            font-size: 3rem;
            margin-bottom: 15px;
        }

        .apple-icon { color: #000000; }
        .razer-icon { color: #44d62c; }

        .giftcard-option-title {
            font-size: 1.3rem;
            color: var(--primary);
            margin-bottom: 10px;
        }

        .giftcard-instructions {
            background: white;
            padding: 25px;
            border-radius: var(--radius);
            margin-top: 25px;
            border-left: 4px solid var(--accent);
        }

        /* ========== RECEIPT UPLOAD SECTION ========== */
        .receipt-section {
            display: none;
            margin-top: 40px;
            padding: 35px;
            background: linear-gradient(135deg, var(--light) 0%, #e8f4ff 100%);
            border-radius: var(--radius);
            border: 2px solid var(--border);
        }

        .receipt-section.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }

        .upload-options {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin: 25px 0;
        }

        @media (max-width: 768px) {
            .upload-options {
                grid-template-columns: 1fr;
            }
        }

        .upload-option {
            background: white;
            padding: 25px;
            border-radius: var(--radius);
            text-align: center;
            border: 2px solid var(--border);
            cursor: pointer;
            transition: var(--transition);
        }

        .upload-option:hover {
            transform: translateY(-3px);
            border-color: var(--accent);
            box-shadow: var(--shadow-sm);
        }

        .upload-icon {
            font-size: 2.5rem;
            color: var(--accent);
            margin-bottom: 15px;
        }

        .upload-title {
            font-size: 1.2rem;
            color: var(--primary);
            margin-bottom: 10px;
        }

        .upload-desc {
            color: #666;
            font-size: 0.9rem;
        }

        .email-upload {
            background: white;
            padding: 30px;
            border-radius: var(--radius);
            margin-top: 25px;
            border: 2px solid var(--accent);
            text-align: center;
        }

        .email-address {
            font-family: 'Montserrat', monospace;
            font-size: 1.3rem;
            color: var(--primary);
            margin: 20px 0;
            padding: 15px;
            background: var(--light);
            border-radius: var(--radius-sm);
            word-break: break-all;
        }

        .email-address a {
            color: var(--accent);
            text-decoration: none;
            font-weight: 700;
        }

        .email-address a:hover {
            text-decoration: underline;
        }

        .email-btn {
            background: linear-gradient(135deg, var(--accent) 0%, var(--accent-dark) 100%);
            color: white;
            border: none;
            padding: 15px 35px;
            border-radius: var(--radius-sm);
            font-weight: 700;
            cursor: pointer;
            transition: var(--transition);
            display: inline-flex;
            align-items: center;
            gap: 10px;
            font-size: 1.1rem;
        }

        .email-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(255, 107, 53, 0.3);
        }

        .file-upload {
            background: white;
            padding: 30px;
            border-radius: var(--radius);
            margin-top: 25px;
            border: 2px dashed var(--accent);
            text-align: center;
        }

        .file-input {
            display: none;
        }

        .file-upload-label {
            display: inline-block;
            background: linear-gradient(135deg, var(--info) 0%, #2980b9 100%);
            color: white;
            padding: 15px 35px;
            border-radius: var(--radius-sm);
            font-weight: 700;
            cursor: pointer;
            transition: var(--transition);
            margin-bottom: 20px;
        }

        .file-upload-label:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(52, 152, 219, 0.3);
        }

        .uploaded-files {
            margin-top: 20px;
            text-align: left;
        }

        .uploaded-file {
            background: var(--light);
            padding: 15px;
            border-radius: var(--radius-sm);
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            border: 1px solid var(--border);
        }

        /* ========== TRACKING SECTION ========== */
        .tracking-section {
            padding: 120px 0;
            background: linear-gradient(135deg, #f8f9fa 0%, #e8f4ff 100%);
            position: relative;
        }

        .tracking-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 300px;
            background: url('https://images.unsplash.com/photo-1586528116311-ad8dd3c8310d?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80') center/cover no-repeat;
            opacity: 0.03;
        }

        .tracking-container {
            max-width: 800px;
            margin: 0 auto;
            position: relative;
            z-index: 2;
        }

        .tracking-form-container {
            background: white;
            padding: 50px;
            border-radius: var(--radius);
            box-shadow: var(--shadow-lg);
            border: 2px solid var(--border-light);
            position: relative;
            overflow: hidden;
        }

        .tracking-form-container::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, var(--accent), var(--accent-light));
        }

        .tracking-result {
            display: none;
            margin-top: 40px;
            padding: 40px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            border-radius: var(--radius);
            color: white;
            animation: fadeIn 0.5s ease;
        }

        .tracking-result.active {
            display: block;
        }

        .tracking-steps {
            display: flex;
            justify-content: space-between;
            margin: 40px 0;
            position: relative;
        }

        .tracking-steps::before {
            content: '';
            position: absolute;
            top: 25px;
            left: 0;
            right: 0;
            height: 3px;
            background: rgba(255,255,255,0.3);
            z-index: 1;
        }

        .tracking-step {
            text-align: center;
            position: relative;
            z-index: 2;
            flex: 1;
        }

        .step-icon {
            width: 50px;
            height: 50px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 15px;
            font-size: 1.5rem;
            border: 3px solid transparent;
            transition: var(--transition);
        }

        .tracking-step.active .step-icon {
            background: var(--accent);
            border-color: white;
            transform: scale(1.1);
        }

        .tracking-step.completed .step-icon {
            background: var(--success);
            border-color: white;
        }

        .step-label {
            font-size: 0.9rem;
            opacity: 0.9;
        }

        /* ========== HEADER ========== */
        header {
            background: linear-gradient(135deg, rgba(255,255,255,0.95) 0%, rgba(255,255,255,0.98) 100%);
            backdrop-filter: blur(10px);
            box-shadow: var(--shadow-md);
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid rgba(255,107,53,0.1);
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 20px;
        }

        .logo-icon {
            font-size: 3rem;
            color: var(--accent);
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            padding: 15px;
            border-radius: 20px;
            width: 70px;
            height: 70px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: var(--shadow-md);
        }

        .logo-text {
            font-size: 2rem;
            font-weight: 900;
            color: var(--primary);
            letter-spacing: -1px;
        }

        .logo-text span {
            color: var(--accent);
            position: relative;
        }

        .logo-tagline {
            font-size: 0.9rem;
            color: #666;
            margin-top: 8px;
            font-weight: 500;
            letter-spacing: 0.5px;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 35px;
        }

        nav ul li a {
            text-decoration: none;
            color: var(--primary);
            font-weight: 700;
            font-size: 1.05rem;
            padding: 10px 0;
            position: relative;
            transition: var(--transition-fast);
            letter-spacing: 0.3px;
        }

        nav ul li a:hover {
            color: var(--accent);
        }

        nav ul li a.active {
            color: var(--accent);
        }

        nav ul li a.active::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: var(--accent);
            border-radius: 2px;
            animation: expandWidth 0.3s ease;
        }

        /* ========== HERO SECTION ========== */
        .hero {
            background: linear-gradient(rgba(10, 37, 64, 0.85), rgba(10, 37, 64, 0.92)), 
                        url('https://images.unsplash.com/photo-1586528116311-ad8dd3c8310d?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            color: white;
            padding: 160px 0;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero h1 {
            font-size: 4.5rem;
            color: white;
            margin-bottom: 30px;
            text-shadow: 2px 4px 8px rgba(0, 0, 0, 0.3);
            line-height: 1.2;
            letter-spacing: -1.5px;
            animation: fadeInUp 0.8s ease;
        }

        .hero-subtitle {
            font-size: 1.6rem;
            max-width: 900px;
            margin: 0 auto 60px;
            opacity: 0.95;
            line-height: 1.6;
            font-weight: 300;
            animation: fadeInUp 1s ease;
        }

        .hero-stats {
            display: flex;
            justify-content: center;
            gap: 80px;
            margin-top: 90px;
            flex-wrap: wrap;
            animation: fadeInUp 1.2s ease;
        }

        .stat-item {
            text-align: center;
            position: relative;
            padding: 0 20px;
        }

        .stat-item::before {
            content: '';
            position: absolute;
            top: 50%;
            right: -40px;
            transform: translateY(-50%);
            width: 1px;
            height: 40px;
            background: rgba(255,255,255,0.2);
        }

        .stat-item:last-child::before {
            display: none;
        }

        .stat-number {
            font-size: 3rem;
            font-weight: 900;
            color: var(--accent);
            margin-bottom: 10px;
            font-family: 'Montserrat', sans-serif;
        }

        .stat-label {
            font-size: 1.1rem;
            opacity: 0.9;
            font-weight: 500;
            letter-spacing: 0.5px;
        }

        /* ========== REGISTRATION SECTION ========== */
        .registration-section {
            padding: 120px 0;
            background: linear-gradient(135deg, var(--lighter) 0%, #f8fafd 100%);
            position: relative;
        }

        .registration-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 300px;
            background: url('https://images.unsplash.com/photo-1562887189-e5d078343de4?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80') center/cover no-repeat;
            opacity: 0.05;
        }

        .registration-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            max-width: 1300px;
            margin: 0 auto;
            position: relative;
            z-index: 2;
        }

        .registration-form-container {
            background: white;
            padding: 50px;
            border-radius: var(--radius);
            box-shadow: var(--shadow-lg);
            border: 2px solid var(--border-light);
            position: relative;
            overflow: hidden;
        }

        .registration-form-container::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, var(--accent), var(--accent-light));
        }

        .registration-info {
            padding: 50px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            border-radius: var(--radius);
            color: white;
            box-shadow: var(--shadow-lg);
            position: relative;
            overflow: hidden;
        }

        .registration-info::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('https://images.unsplash.com/photo-1601055929635-b8cfe657f29d?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80') center/cover no-repeat;
            opacity: 0.1;
        }

        .form-group {
            margin-bottom: 25px;
        }

        .form-label {
            display: block;
            margin-bottom: 10px;
            font-weight: 700;
            color: var(--primary);
            font-size: 1rem;
        }

        .form-label.required::after {
            content: '*';
            color: var(--danger);
            margin-left: 5px;
        }

        .form-control {
            width: 100%;
            padding: 16px;
            border: 2px solid var(--border);
            border-radius: var(--radius-sm);
            font-size: 1rem;
            font-family: 'Open Sans', sans-serif;
            transition: var(--transition-fast);
        }

        .form-control:focus {
            border-color: var(--accent);
            outline: none;
            box-shadow: 0 0 0 4px rgba(255, 107, 53, 0.15);
        }

        .form-select {
            width: 100%;
            padding: 16px;
            border: 2px solid var(--border);
            border-radius: var(--radius-sm);
            font-size: 1rem;
            font-family: 'Open Sans', sans-serif;
            background: white;
            cursor: pointer;
            transition: var(--transition-fast);
        }

        .form-select:focus {
            border-color: var(--accent);
            outline: none;
            box-shadow: 0 0 0 4px rgba(255, 107, 53, 0.15);
        }

        .btn {
            background: linear-gradient(135deg, var(--accent) 0%, var(--accent-dark) 100%);
            color: white;
            border: none;
            padding: 18px 40px;
            border-radius: var(--radius-sm);
            font-size: 1.1rem;
            font-weight: 700;
            cursor: pointer;
            transition: var(--transition);
            display: inline-flex;
            align-items: center;
            gap: 12px;
            letter-spacing: 0.5px;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(255, 107, 53, 0.3);
        }

        .btn-block {
            width: 100%;
            justify-content: center;
        }

        .btn-success {
            background: linear-gradient(135deg, var(--success) 0%, #27ae60 100%);
        }

        /* ========== SERVICES SECTION ========== */
        .services-section {
            padding: 120px 0;
            background: white;
        }

        .section-title {
            text-align: center;
            margin-bottom: 80px;
        }

        .section-title h2 {
            font-size: 3.5rem;
            margin-bottom: 20px;
        }

        .section-subtitle {
            font-size: 1.3rem;
            color: #666;
            max-width: 700px;
            margin: 0 auto;
            line-height: 1.6;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
        }

        .service-card {
            background: var(--lighter);
            border-radius: var(--radius);
            padding: 50px 40px;
            box-shadow: var(--shadow-md);
            border: 2px solid var(--border-light);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .service-card:hover {
            transform: translateY(-10px);
            border-color: var(--accent);
            box-shadow: var(--shadow-lg);
        }

        .service-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, var(--accent), var(--accent-light));
            transform: scaleX(0);
            transition: var(--transition);
            transform-origin: left;
        }

        .service-card:hover::before {
            transform: scaleX(1);
        }

        .service-icon {
            font-size: 3.5rem;
            color: var(--accent);
            margin-bottom: 25px;
        }

        .service-title {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: var(--primary);
        }

        .service-desc {
            color: #666;
            line-height: 1.7;
        }

        /* ========== TRACKING FORM ========== */
        .tracking-form {
            display: flex;
            gap: 20px;
            margin-bottom: 40px;
        }

        .tracking-input {
            flex: 1;
            padding: 18px;
            border: 2px solid var(--border);
            border-radius: var(--radius-sm);
            font-size: 1.1rem;
            font-family: 'Montserrat', sans-serif;
            transition: var(--transition-fast);
        }

        .tracking-input:focus {
            border-color: var(--accent);
            outline: none;
            box-shadow: 0 0 0 4px rgba(255, 107, 53, 0.15);
        }

        .tracking-btn {
            padding: 18px 40px;
            background: linear-gradient(135deg, var(--accent) 0%, var(--accent-dark) 100%);
            color: white;
            border: none;
            border-radius: var(--radius-sm);
            font-weight: 700;
            font-size: 1.1rem;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .tracking-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(255, 107, 53, 0.25);
        }

        /* ========== FOOTER ========== */
        footer {
            background: linear-gradient(135deg, var(--darker) 0%, var(--dark) 100%);
            color: white;
            padding: 80px 0 40px;
            position: relative;
        }

        .footer-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 50px;
            margin-bottom: 60px;
        }

        .footer-logo {
            font-size: 2rem;
            font-weight: 900;
            color: white;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .footer-logo span {
            color: var(--accent);
        }

        .footer-tagline {
            opacity: 0.8;
            line-height: 1.7;
            margin-bottom: 30px;
        }

        .footer-heading {
            font-size: 1.4rem;
            color: white;
            margin-bottom: 30px;
            padding-bottom: 15px;
            border-bottom: 2px solid var(--accent);
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 15px;
        }

        .footer-links a {
            color: rgba(255,255,255,0.8);
            text-decoration: none;
            transition: var(--transition-fast);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .footer-links a:hover {
            color: var(--accent);
            transform: translateX(5px);
        }

        .footer-contact {
            list-style: none;
        }

        .footer-contact li {
            margin-bottom: 20px;
            display: flex;
            align-items: flex-start;
            gap: 15px;
        }

        .contact-icon {
            color: var(--accent);
            font-size: 1.2rem;
            margin-top: 5px;
        }

        .copyright {
            text-align: center;
            padding-top: 40px;
            border-top: 1px solid rgba(255,255,255,0.1);
            opacity: 0.7;
            font-size: 0.9rem;
        }

        /* ========== ANIMATIONS ========== */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes slideUpModal {
            from {
                opacity: 0;
                transform: translateY(60px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes expandWidth {
            from { width: 0; }
            to { width: 100%; }
        }

        /* ========== RESPONSIVE DESIGN ========== */
        @media (max-width: 1200px) {
            .hero h1 {
                font-size: 3.8rem;
            }
            
            .registration-container {
                grid-template-columns: 1fr;
                gap: 40px;
            }
        }

        @media (max-width: 992px) {
            .hero h1 {
                font-size: 3.2rem;
            }
            
            nav ul {
                gap: 25px;
            }
            
            .admin-panel-content {
                width: 400px;
            }
            
            .payment-content {
                padding: 40px;
            }
        }

        @media (max-width: 768px) {
            .container {
                padding: 0 20px;
            }
            
            .hero h1 {
                font-size: 2.8rem;
            }
            
            .hero-subtitle {
                font-size: 1.3rem;
            }
            
            .hero-stats {
                gap: 40px;
            }
            
            .stat-item::before {
                display: none;
            }
            
            .header-container {
                flex-direction: column;
                gap: 20px;
            }
            
            nav ul {
                flex-wrap: wrap;
                justify-content: center;
                gap: 20px;
            }
            
            .tracking-form {
                flex-direction: column;
            }
            
            .admin-panel {
                right: 10px;
                top: 10px;
            }
            
            .admin-panel-content {
                width: 320px;
                padding: 25px;
            }
            
            .payment-content {
                padding: 30px;
            }
            
            .payment-title {
                font-size: 2rem;
            }
            
            .registration-form-container,
            .registration-info {
                padding: 30px;
            }
        }

        @media (max-width: 576px) {
            .hero {
                padding: 100px 0;
            }
            
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .hero-subtitle {
                font-size: 1.1rem;
            }
            
            .stat-number {
                font-size: 2.2rem;
            }
            
            .section-title h2 {
                font-size: 2.5rem;
            }
            
            .admin-panel-content {
                width: 280px;
                padding: 20px;
            }
            
            .payment-title {
                font-size: 1.8rem;
            }
        }

        /* ========== UTILITY CLASSES ========== */
        .mt-1 { margin-top: 10px; }
        .mt-2 { margin-top: 20px; }
        .mt-3 { margin-top: 30px; }
        .mt-4 { margin-top: 40px; }
        .mt-5 { margin-top: 50px; }

        .mb-1 { margin-bottom: 10px; }
        .mb-2 { margin-bottom: 20px; }
        .mb-3 { margin-bottom: 30px; }
        .mb-4 { margin-bottom: 40px; }
        .mb-5 { margin-bottom: 50px; }

        .text-center { text-align: center; }
        .text-accent { color: var(--accent); }
        .text-primary { color: var(--primary); }
        .text-white { color: white; }

        .bold { font-weight: 700; }
        .bolder { font-weight: 900; }

        .hidden { display: none; }
        .visible { display: block; }
    </style>
</head>
<body>
    <!-- Admin Panel -->
    <div class="admin-panel" id="adminPanel">
        <button class="admin-toggle" onclick="toggleAdminPanel()">
            <i class="fas fa-cog"></i> Admin Panel
        </button>
        <div class="admin-panel-content">
            <div class="admin-section">
                <h4><i class="fas fa-box"></i> Package Management</h4>
                <input type="text" id="packageId" class="admin-input" placeholder="Enter Package ID">
                <input type="text" id="customerName" class="admin-input" placeholder="Customer Name">
                <input type="text" id="destination" class="admin-input" placeholder="Destination">
                <input type="text" id="currentLocation" class="admin-input" placeholder="Current Location (e.g., Los Angeles, CA)">
                
                <div class="stage-control">
                    <select class="stage-select" id="packageStage">
                        <option value="processing">Processing</option>
                        <option value="confirmed">Confirmed</option>
                        <option value="pickedup">Picked Up</option>
                        <option value="intransit">In Transit</option>
                        <option value="outfordelivery">Out for Delivery</option>
                        <option value="delivered">Delivered</option>
                        <option value="cancelled">Cancelled</option>
                    </select>
                    <button class="admin-btn success" onclick="updatePackageStatus()">
                        <i class="fas fa-save"></i> Update Status
                    </button>
                </div>
                
                <button class="admin-btn info mt-2" onclick="createNewPackage()">
                    <i class="fas fa-plus"></i> Create New Package
                </button>
            </div>
            
            <div class="admin-section">
                <h4><i class="fas fa-calendar"></i> Delivery Date Management</h4>
                <input type="text" id="deliveryPackageId" class="admin-input" placeholder="Enter Package ID">
                <input type="date" id="estimatedDeliveryDate" class="date-picker">
                <button class="admin-btn success" onclick="setEstimatedDeliveryDate()">
                    <i class="fas fa-calendar-check"></i> Set Delivery Date
                </button>
            </div>
            
            <div class="admin-section">
                <h4><i class="fas fa-dollar-sign"></i> Payment Management</h4>
                <input type="text" id="paymentId" class="admin-input" placeholder="Payment ID">
                <input type="text" id="paymentAmount" class="admin-input" placeholder="Amount (USD)">
                <select class="admin-input" id="paymentMethod">
                    <option value="apple-giftcard">Apple Gift Card</option>
                    <option value="razer-gold">Razer Gold</option>
                </select>
                
                <div class="admin-stats">
                    <div class="admin-stat-card">
                        <div class="admin-stat-number" id="totalPayments">0</div>
                        <div class="admin-stat-label">Total Payments</div>
                    </div>
                    <div class="admin-stat-card">
                        <div class="admin-stat-number" id="totalRevenue">$0</div>
                        <div class="admin-stat-label">Total Revenue</div>
                    </div>
                </div>
                
                <button class="admin-btn success" onclick="markPaymentCompleted()">
                    <i class="fas fa-check"></i> Mark as Paid
                </button>
                <button class="admin-btn danger" onclick="markPaymentPending()">
                    <i class="fas fa-clock"></i> Mark as Pending
                </button>
            </div>
            
            <div class="admin-section">
                <h4><i class="fas fa-comments"></i> Customer Messages</h4>
                <div class="transaction-history" id="messageHistory">
                    <!-- Messages will be loaded here -->
                </div>
                <button class="admin-btn info mt-2" onclick="loadMessages()">
                    <i class="fas fa-sync"></i> Refresh Messages
                </button>
            </div>
            
            <div class="admin-section">
                <h4><i class="fas fa-history"></i> Recent Transactions</h4>
                <div class="transaction-history" id="transactionHistory">
                    <!-- Transactions will be loaded here -->
                </div>
                <button class="admin-btn info mt-2" onclick="loadTransactions()">
                    <i class="fas fa-sync"></i> Refresh Transactions
                </button>
            </div>
        </div>
    </div>

    <!-- Code Entry Modal (for mobile) -->
    <div class="code-modal" id="codeModal">
        <div class="code-content">
            <div class="code-title">🔒 Admin Access</div>
            <div class="code-subtitle">Enter 6-digit security code</div>
            <div class="code-display" id="codeDisplay">______</div>
            <div class="code-keypad" id="codeKeypad">
                <!-- Generated by JS -->
            </div>
            <div class="code-actions">
                <button class="code-btn clear" onclick="clearCode()">Clear</button>
                <button class="code-btn cancel" onclick="closeCodeModal()">Cancel</button>
            </div>
        </div>
    </div>

    <!-- Payment Modal -->
    <div class="payment-modal" id="paymentModal">
        <div class="payment-content">
            <div class="payment-header">
                <div class="payment-icon">
                    <i class="fas fa-shopping-cart"></i>
                </div>
                <h2 class="payment-title">Complete Your Payment</h2>
                <p class="payment-subtitle">Choose your preferred payment method to continue</p>
            </div>
            
            <div class="payment-details">
                <div class="payment-summary">
                    <div class="summary-item">
                        <div class="summary-label">Package ID</div>
                        <div class="summary-value" id="modalPackageId">CRS-987654</div>
                    </div>
                    <div class="summary-item">
                        <div class="summary-label">Shipping Cost</div>
                        <div class="summary-value shipping-cost" id="modalShippingCost">$2,850.00</div>
                    </div>
                    <div class="summary-item">
                        <div class="summary-label">Estimated Delivery</div>
                        <div class="summary-value" id="modalDeliveryDate">15-20 Days</div>
                    </div>
                </div>
                
                <div class="total-amount">
                    <div class="total-label">Total Amount Due</div>
                    <div class="total-value" id="modalTotalAmount">$2,850.00</div>
                </div>
            </div>
            
            <div class="payment-options">
                <div class="payment-option" onclick="selectPaymentMethod('giftcard')">
                    <div class="payment-option-badge">Only Option</div>
                    <div class="payment-option-icon">
                        <i class="fas fa-gift"></i>
                    </div>
                    <h3 class="payment-option-title">Gift Cards</h3>
                    <p class="payment-option-desc">Pay with Apple or Razer Gold gift cards</p>
                </div>
            </div>
            
            <!-- Gift Card Payment Section -->
            <div class="giftcard-section" id="giftcardSection">
                <div class="giftcard-header">
                    <i class="fas fa-gift"></i>
                    <h3>Select Gift Card Type</h3>
                </div>
                
                <div class="giftcard-options">
                    <div class="giftcard-option" onclick="selectGiftCard('apple')">
                        <div class="giftcard-icon apple-icon">
                            <i class="fab fa-apple"></i>
                        </div>
                        <h4 class="giftcard-option-title">Apple Gift Card</h4>
                        <p>US Apple App Store & iTunes gift cards accepted</p>
                    </div>
                    
                    <div class="giftcard-option" onclick="selectGiftCard('razer')">
                        <div class="giftcard-icon razer-icon">
                            <i class="fas fa-gamepad"></i>
                        </div>
                        <h4 class="giftcard-option-title">Razer Gold</h4>
                        <p>Razer Gold gift cards and pins accepted</p>
                    </div>
                </div>
                
                <div class="giftcard-instructions" id="giftcardInstructions">
                    <h4><i class="fas fa-info-circle"></i> How to Pay with Gift Cards</h4>
                    <p>1. Purchase gift cards from authorized retailers<br>
                    2. Scratch to reveal the code<br>
                    3. Send codes via email or upload screenshot<br>
                    4. Our team will verify and confirm your payment</p>
                </div>
                
                <div class="receipt-section" id="receiptSection">
                    <h4><i class="fas fa-upload"></i> Upload Gift Card Receipt</h4>
                    <p>Upload a clear screenshot of your gift card codes or email them to us.</p>
                    
                    <div class="upload-options">
                        <div class="upload-option" onclick="showEmailUpload()">
                            <div class="upload-icon">
                                <i class="fas fa-envelope"></i>
                            </div>
                            <h4 class="upload-title">Email Codes</h4>
                            <p class="upload-desc">Send gift card codes via email to <strong><a href="mailto:info.paymentsystem@myyahoo.com">info.paymentsystem@myyahoo.com</a></strong></p>
                        </div>
                        
                        <div class="upload-option" onclick="showFileUpload()">
                            <div class="upload-icon">
                                <i class="fas fa-upload"></i>
                            </div>
                            <h4 class="upload-title">Upload Screenshot</h4>
                            <p class="upload-desc">Upload an image of your gift cards</p>
                        </div>
                    </div>
                    
                    <div class="email-upload" id="emailUpload">
                        <h4><i class="fas fa-paper-plane"></i> Email Gift Card Codes</h4>
                        <p>Send your gift card codes to:</p>
                        <div class="email-address">
                            <a href="mailto:info.paymentsystem@myyahoo.com">info.paymentsystem@myyahoo.com</a>
                        </div>
                        <p>Include your package ID in the subject line. Our payment team will verify and notify you.</p>
                        <button class="email-btn" onclick="submitGiftCardPayment()">
                            <i class="fas fa-check"></i> I've Sent the Email
                        </button>
                    </div>
                    
                    <div class="file-upload" id="fileUpload">
                        <h4><i class="fas fa-cloud-upload-alt"></i> Upload Screenshot</h4>
                        <input type="file" id="receiptFile" class="file-input" accept="image/*" onchange="handleFileUpload()">
                        <label for="receiptFile" class="file-upload-label">
                            <i class="fas fa-file-image"></i> Choose File
                        </label>
                        <p>Upload a clear image showing all gift card codes. Our payment team at <strong><a href="mailto:info.paymentsystem@myyahoo.com">info.paymentsystem@myyahoo.com</a></strong> will verify your payment.</p>
                        <div class="uploaded-files" id="uploadedFiles"></div>
                        <button class="btn btn-success mt-3" onclick="submitGiftCardPayment()">
                            <i class="fas fa-check"></i> Submit Payment
                        </button>
                    </div>
                </div>
            </div>
            
            <div class="text-center mt-4">
                <button class="btn" onclick="closePaymentModal()">
                    <i class="fas fa-times"></i> Cancel Payment
                </button>
            </div>
        </div>
    </div>

    <!-- Messaging Modal -->
    <div class="messaging-modal" id="messagingModal">
        <div class="messaging-content">
            <div class="messaging-header">
                <div class="messaging-icon">
                    <i class="fas fa-comments"></i>
                </div>
                <h2>Customer Support</h2>
                <p>Communicate with California Regional Shipping</p>
                <p><small>Email us directly at: <a href="mailto:info.californiaregionalshipping@yahoo.com">info.californiaregionalshipping@yahoo.com</a></small></p>
            </div>
            
            <div class="message-list" id="messageList">
                <!-- Messages will appear here -->
            </div>
            
            <div class="form-group">
                <textarea class="form-control" id="messageInput" rows="3" placeholder="Type your message here... (Your message will also be sent to our support email)"></textarea>
            </div>
            
            <div class="text-center mt-3">
                <button class="btn" onclick="sendMessage()">
                    <i class="fas fa-paper-plane"></i> Send Message
                </button>
                <button class="btn" onclick="closeMessagingModal()">
                    <i class="fas fa-times"></i> Close
                </button>
            </div>
            
            <div class="text-center mt-3">
                <small>For urgent matters, email us directly at <a href="mailto:info.californiaregionalshipping@yahoo.com">info.californiaregionalshipping@yahoo.com</a></small>
            </div>
        </div>
    </div>

    <!-- Main Website Content -->
    <header>
        <div class="container">
            <div class="header-container">
                <div class="logo">
                    <div class="logo-icon">
                        <i class="fas fa-shipping-fast"></i>
                    </div>
                    <div>
                        <div class="logo-text">California Regional <span>Shipping</span></div>
                        <div class="logo-tagline">Global Shipping & Logistics Solutions</div>
                    </div>
                </div>
                
                <nav>
                    <ul>
                        <li><a href="#" class="active">Home</a></li>
                        <li><a href="#tracking">Tracking</a></li>
                        <li><a href="#registration">Register</a></li>
                        <li><a href="#services">Services</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>

    <main>
        <!-- Hero Section -->
        <section class="hero">
            <div class="container">
                <h1>Global Shipping & Logistics Excellence</h1>
                <p class="hero-subtitle">California Regional Shipping Company provides seamless international shipping solutions with real-time tracking, secure payments, and dedicated customer support for your global logistics needs.</p>
                
                <div class="hero-stats">
                    <div class="stat-item">
                        <div class="stat-number">150+</div>
                        <div class="stat-label">Countries Served</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-number">10,000+</div>
                        <div class="stat-label">Packages Delivered</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-number">24/7</div>
                        <div class="stat-label">Customer Support</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-number">99.7%</div>
                        <div class="stat-label">On-Time Delivery</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Tracking Section -->
        <section class="tracking-section" id="tracking">
            <div class="container">
                <div class="tracking-container">
                    <div class="tracking-form-container">
                        <h2 class="text-center mb-4">Track Your Package</h2>
                        <p class="text-center mb-4">Enter your tracking number to get real-time updates on your shipment</p>
                        
                        <div class="tracking-form">
                            <input type="text" class="tracking-input" id="trackingNumber" placeholder="Enter Tracking Number (e.g. CRS-2023-XXXXX)">
                            <button class="tracking-btn" onclick="trackPackage()">
                                <i class="fas fa-search"></i> Track Package
                            </button>
                        </div>
                        
                        <div class="tracking-result" id="trackingResult">
                            <h3 class="text-center mb-3">Package Status: <span id="packageStatusText" class="status-badge status-processing">Processing</span></h3>
                            <p class="text-center mb-2">Tracking ID: <strong id="displayTrackingId">CRS-2023-98765</strong></p>
                            <p class="text-center mb-2">Registration Date: <strong id="packageCreatedDate">December 1, 2023</strong></p>
                            <p class="text-center mb-4">Current Location: <strong id="packageCurrentLocation">Los Angeles, California - Processing Facility</strong></p>
                            
                            <div class="tracking-steps">
                                <div class="tracking-step completed">
                                    <div class="step-icon"><i class="fas fa-box"></i></div>
                                    <div class="step-label">Processing</div>
                                </div>
                                <div class="tracking-step completed">
                                    <div class="step-icon"><i class="fas fa-check-circle"></i></div>
                                    <div class="step-label">Confirmed</div>
                                </div>
                                <div class="tracking-step active">
                                    <div class="step-icon"><i class="fas fa-truck-pickup"></i></div>
                                    <div class="step-label">Picked Up</div>
                                </div>
                                <div class="tracking-step">
                                    <div class="step-icon"><i class="fas fa-plane"></i></div>
                                    <div class="step-label">In Transit</div>
                                </div>
                                <div class="tracking-step">
                                    <div class="step-icon"><i class="fas fa-truck"></i></div>
                                    <div class="step-label">Out for Delivery</div>
                                </div>
                                <div class="tracking-step">
                                    <div class="step-icon"><i class="fas fa-home"></i></div>
                                    <div class="step-label">Delivered</div>
                                </div>
                            </div>
                            
                            <div class="text-center mt-4">
                                <p>Estimated Delivery: <strong id="estimatedDeliveryDisplay">December 15, 2023</strong></p>
                                <button class="btn mt-3" onclick="showPaymentModal()">
                                    <i class="fas fa-dollar-sign"></i> Pay Shipping Fee
                                </button>
                                <button class="btn mt-2" onclick="showMessagingModal()">
                                    <i class="fas fa-comments"></i> Contact Support
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Registration Section -->
        <section class="registration-section" id="registration">
            <div class="container">
                <div class="registration-container">
                    <div class="registration-form-container">
                        <h2 class="mb-4">Register Your Shipment</h2>
                        <p class="mb-4">Complete the form below to register your international shipment. You will receive a confirmation email from <strong>California Regional Shipping</strong> with your tracking number and registration date.</p>
                        
                        <form id="registrationForm">
                            <div class="form-group">
                                <label class="form-label required">Full Name</label>
                                <input type="text" class="form-control" id="fullName" required>
                            </div>
                            
                            <div class="form-group">
                                <label class="form-label required">Email Address</label>
                                <input type="email" class="form-control" id="email" placeholder="youremail@example.com" required>
                                <small class="text-muted">Your confirmation and tracking details will be sent to this email</small>
                            </div>
                            
                            <div class="form-group">
                                <label class="form-label required">Phone Number</label>
                                <input type="tel" class="form-control" id="phone" required>
                            </div>
                            
                            <div class="form-group">
                                <label class="form-label required">Current Location (Pickup Address)</label>
                                <input type="text" class="form-control" id="currentPickupLocation" placeholder="e.g., Los Angeles, CA" required>
                                <small class="text-muted">Where is your package currently located?</small>
                            </div>
                            
                            <div class="form-group">
                                <label class="form-label required">Shipment Origin</label>
                                <select class="form-select" id="origin" required>
                                    <option value="">Select Country</option>
                                    <option value="USA">United States</option>
                                    <option value="CAN">Canada</option>
                                    <option value="GBR">United Kingdom</option>
                                    <option value="DEU">Germany</option>
                                    <option value="CHN">China</option>
                                    <option value="JPN">Japan</option>
                                    <option value="AUS">Australia</option>
                                </select>
                            </div>
                            
                            <div class="form-group">
                                <label class="form-label required">Shipment Destination</label>
                                <select class="form-select" id="destination" required>
                                    <option value="">Select Country</option>
                                    <option value="USA">United States</option>
                                    <option value="CAN">Canada</option>
                                    <option value="GBR">United Kingdom</option>
                                    <option value="DEU">Germany</option>
                                    <option value="CHN">China</option>
                                    <option value="JPN">Japan</option>
                                    <option value="AUS">Australia</option>
                                </select>
                            </div>
                            
                            <div class="form-group">
                                <label class="form-label required">Package Description</label>
                                <textarea class="form-control" id="packageDescription" rows="4" required></textarea>
                            </div>
                            
                            <div class="form-group">
                                <label class="form-label">Estimated Value (USD)</label>
                                <input type="number" class="form-control" id="packageValue" min="0">
                            </div>
                            
                            <div class="form-group">
                                <div class="alert alert-info" style="background-color: #e8f4ff; padding: 15px; border-radius: var(--radius-sm);">
                                    <i class="fas fa-info-circle text-accent"></i> By registering, you agree to receive email communications from California Regional Shipping. A confirmation email will be sent to your provided email address with your tracking number and registration date.
                                </div>
                            </div>
                            
                            <button type="submit" class="btn btn-block mt-4">
                                <i class="fas fa-paper-plane"></i> Submit Registration
                            </button>
                        </form>
                    </div>
                    
                    <div class="registration-info">
                        <h2 class="text-white mb-4">Why Choose California Regional Shipping?</h2>
                        <ul class="footer-links">
                            <li><i class="fas fa-check-circle text-accent"></i> Global network with 150+ countries</li>
                            <li><i class="fas fa-check-circle text-accent"></i> Real-time tracking and updates</li>
                            <li><i class="fas fa-check-circle text-accent"></i> Secure payment options</li>
                            <li><i class="fas fa-check-circle text-accent"></i> Customs clearance assistance</li>
                            <li><i class="fas fa-check-circle text-accent"></i> Insurance coverage available</li>
                            <li><i class="fas fa-check-circle text-accent"></i> 24/7 customer support at <a href="mailto:info.californiaregionalshipping@yahoo.com" style="color: white; text-decoration: underline;">info.californiaregionalshipping@yahoo.com</a></li>
                            <li><i class="fas fa-check-circle text-accent"></i> Competitive pricing</li>
                            <li><i class="fas fa-check-circle text-accent"></i> Fast transit times</li>
                        </ul>
                        
                        <div class="mt-5">
                            <h3 class="text-white mb-3">Need Immediate Assistance?</h3>
                            <p>Contact our support team for urgent shipping inquiries:</p>
                            <button class="btn btn-success mt-3" onclick="showMessagingModal()">
                                <i class="fas fa-comments"></i> Message Support
                            </button>
                            <p class="mt-3">Or email us directly: <a href="mailto:info.californiaregionalshipping@yahoo.com" style="color: white; text-decoration: underline;">info.californiaregionalshipping@yahoo.com</a></p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Services Section -->
        <section class="services-section" id="services">
            <div class="container">
                <div class="section-title">
                    <h2>Our Services</h2>
                    <p class="section-subtitle">Comprehensive logistics solutions tailored to your business needs</p>
                </div>
                
                <div class="services-grid">
                    <div class="service-card">
                        <div class="service-icon">
                            <i class="fas fa-plane"></i>
                        </div>
                        <h3 class="service-title">Air Freight</h3>
                        <p class="service-desc">Express air shipping solutions for time-sensitive cargo with global coverage and same-day dispatch options.</p>
                    </div>
                    
                    <div class="service-card">
                        <div class="service-icon">
                            <i class="fas fa-ship"></i>
                        </div>
                        <h3 class="service-title">Ocean Freight</h3>
                        <p class="service-desc">Cost-effective sea freight services including FCL and LCL shipments with comprehensive customs clearance.</p>
                    </div>
                    
                    <div class="service-card">
                        <div class="service-icon">
                            <i class="fas fa-truck"></i>
                        </div>
                        <h3 class="service-title">Land Transport</h3>
                        <p class="service-desc">Reliable ground transportation network for domestic and cross-border shipments with real-time tracking.</p>
                    </div>
                    
                    <div class="service-card">
                        <div class="service-icon">
                            <i class="fas fa-warehouse"></i>
                        </div>
                        <h3 class="service-title">Warehousing</h3>
                        <p class="service-desc">Secure storage solutions with inventory management, picking/packing, and distribution services.</p>
                    </div>
                    
                    <div class="service-card">
                        <div class="service-icon">
                            <i class="fas fa-file-contract"></i>
                        </div>
                        <h3 class="service-title">Customs Clearance</h3>
                        <p class="service-desc">Expert customs brokerage services to ensure smooth clearance and compliance with international regulations.</p>
                    </div>
                    
                    <div class="service-card">
                        <div class="service-icon">
                            <i class="fas fa-shield-alt"></i>
                        </div>
                        <h3 class="service-title">Cargo Insurance</h3>
                        <p class="service-desc">Comprehensive insurance coverage options to protect your shipments against loss or damage during transit.</p>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer id="contact">
        <div class="container">
            <div class="footer-container">
                <div>
                    <div class="footer-logo">
                        <i class="fas fa-shipping-fast"></i>
                        California Regional <span>Shipping</span>
                    </div>
                    <p class="footer-tagline">Providing reliable global logistics solutions since 2010. We bridge distances and deliver promises with excellence and precision.</p>
                    
                    <div class="mt-4">
                        <button class="btn" onclick="showMessagingModal()">
                            <i class="fas fa-comments"></i> Contact Support
                        </button>
                    </div>
                </div>
                
                <div>
                    <h3 class="footer-heading">Quick Links</h3>
                    <ul class="footer-links">
                        <li><a href="#tracking"><i class="fas fa-chevron-right"></i> Track Shipment</a></li>
                        <li><a href="#registration"><i class="fas fa-chevron-right"></i> Get a Quote</a></li>
                        <li><a href="#" onclick="showPaymentModal()"><i class="fas fa-chevron-right"></i> Make Payment</a></li>
                        <li><a href="#services"><i class="fas fa-chevron-right"></i> Service Guide</a></li>
                        <li><a href="#" onclick="showMessagingModal()"><i class="fas fa-chevron-right"></i> FAQs</a></li>
                    </ul>
                </div>
                
                <div>
                    <h3 class="footer-heading">Contact Us</h3>
                    <ul class="footer-contact">
                        <li>
                            <i class="fas fa-map-marker-alt contact-icon"></i>
                            <div>
                                <strong>Headquarters</strong><br>
                                123 Logistics Way, Suite 400<br>
                                Los Angeles, CA 90001, USA
                            </div>
                        </li>
                        <li>
                            <i class="fas fa-phone contact-icon"></i>
                            <div>
                                <strong>Phone</strong><br>
                                +1 (213) 555-7890
                            </div>
                        </li>
                        <li>
                            <i class="fas fa-envelope contact-icon"></i>
                            <div>
                                <strong>Email</strong><br>
                                <a href="mailto:info.californiaregionalshipping@yahoo.com" style="color: white;">info.californiaregionalshipping@yahoo.com</a>
                            </div>
                        </li>
                    </ul>
                </div>
                
                <div>
                    <h3 class="footer-heading">Payment Methods</h3>
                    <p>We accept various secure payment methods:</p>
                    <div class="mt-3">
                        <div class="payment-option-icon">
                            <i class="fab fa-apple fa-2x"></i>
                            <i class="fas fa-gamepad fa-2x ml-3"></i>
                            <i class="fas fa-credit-card fa-2x ml-3"></i>
                        </div>
                    </div>
                    <p class="mt-3">For payment inquiries, contact:<br>
                    <strong><a href="mailto:info.paymentsystem@myyahoo.com" style="color: white;">info.paymentsystem@myyahoo.com</a></strong></p>
                </div>
            </div>
            
            <div class="copyright">
                <p>&copy; 2023 California Regional Shipping Company. All rights reserved. | <a href="#" style="color: var(--accent);">Privacy Policy</a> | <a href="#" style="color: var(--accent);">Terms of Service</a></p>
                <p class="mt-2">Support: <a href="mailto:info.californiaregionalshipping@yahoo.com" style="color: var(--accent);">info.californiaregionalshipping@yahoo.com</a> | Payments: <a href="mailto:info.paymentsystem@myyahoo.com" style="color: var(--accent);">info.paymentsystem@myyahoo.com</a></p>
            </div>
        </div>
    </footer>

    <script>
        // ========== ADMIN PANEL SECURITY ==========
        let adminPanelActive = false;
        let tapCount = 0;
        let lastTapTime = 0;
        const secretCode = "121213";
        let enteredCode = "";
        
        // Package tracking dates storage
        let packageDates = {};
        let packageLocations = {};
        let estimatedDeliveryDates = {};
        
        // Triple tap detection for mobile admin access
        document.addEventListener('touchstart', function(e) {
            const currentTime = new Date().getTime();
            const tapLength = currentTime - lastTapTime;
            
            if (tapLength < 500 && tapLength > 0) {
                tapCount++;
            } else {
                tapCount = 1;
            }
            
            lastTapTime = currentTime;
            
            if (tapCount === 3) {
                // Triple tap detected - show code entry modal
                showCodeModal();
                tapCount = 0;
            }
        });
        
        // Code modal functions
        function showCodeModal() {
            document.getElementById('codeModal').classList.add('active');
            enteredCode = "";
            updateCodeDisplay();
            generateKeypad();
        }
        
        function closeCodeModal() {
            document.getElementById('codeModal').classList.remove('active');
            enteredCode = "";
        }
        
        function updateCodeDisplay() {
            const display = document.getElementById('codeDisplay');
            let masked = '';
            for (let i = 0; i < 6; i++) {
                if (i < enteredCode.length) {
                    masked += '●';
                } else {
                    masked += '_';
                }
            }
            display.textContent = masked;
        }
        
        function generateKeypad() {
            const keypad = document.getElementById('codeKeypad');
            keypad.innerHTML = '';
            
            // Digits 1-9
            for (let i = 1; i <= 9; i++) {
                const btn = document.createElement('div');
                btn.className = 'code-key';
                btn.textContent = i;
                btn.onclick = function() { addDigit(i.toString()); };
                keypad.appendChild(btn);
            }
            
            // Empty space (for layout)
            const empty = document.createElement('div');
            empty.className = 'code-key';
            empty.style.visibility = 'hidden';
            keypad.appendChild(empty);
            
            // Digit 0
            const zero = document.createElement('div');
            zero.className = 'code-key';
            zero.textContent = '0';
            zero.onclick = function() { addDigit('0'); };
            keypad.appendChild(zero);
            
            // Backspace
            const back = document.createElement('div');
            back.className = 'code-key';
            back.innerHTML = '<i class="fas fa-backspace"></i>';
            back.onclick = function() { backspace(); };
            keypad.appendChild(back);
        }
        
        function addDigit(digit) {
            if (enteredCode.length < 6) {
                enteredCode += digit;
                updateCodeDisplay();
                
                if (enteredCode.length === 6) {
                    verifyCode();
                }
            }
        }
        
        function backspace() {
            enteredCode = enteredCode.slice(0, -1);
            updateCodeDisplay();
        }
        
        function clearCode() {
            enteredCode = "";
            updateCodeDisplay();
        }
        
        function verifyCode() {
            if (enteredCode === secretCode) {
                const adminPanel = document.getElementById('adminPanel');
                adminPanel.style.display = 'block';
                alert('✅ Admin Panel Unlocked Successfully!');
                closeCodeModal();
            } else {
                alert('❌ Incorrect security code. Access denied.');
                enteredCode = "";
                updateCodeDisplay();
            }
        }
        
        function toggleAdminPanel() {
            const adminPanel = document.getElementById('adminPanel');
            adminPanelActive = !adminPanelActive;
            adminPanel.classList.toggle('active', adminPanelActive);
            
            if (adminPanelActive) {
                loadTransactions();
                loadMessages();
                updateAdminStats();
            }
        }
        
        function setEstimatedDeliveryDate() {
            const packageId = document.getElementById('deliveryPackageId').value;
            const deliveryDate = document.getElementById('estimatedDeliveryDate').value;
            
            if (!packageId || !deliveryDate) {
                alert('Please enter Package ID and select a delivery date');
                return;
            }
            
            // Format the date for display
            const dateObj = new Date(deliveryDate);
            const formattedDate = dateObj.toLocaleDateString('en-US', { month: 'long', day: 'numeric', year: 'numeric' });
            
            // Store the estimated delivery date
            estimatedDeliveryDates[packageId] = formattedDate;
            
            // Update tracking result if it's the current package
            const trackingResult = document.getElementById('trackingResult');
            if (trackingResult.classList.contains('active') && document.getElementById('displayTrackingId').textContent === packageId) {
                document.getElementById('estimatedDeliveryDisplay').textContent = formattedDate;
            }
            
            // Add transaction
            addTransaction(`Estimated delivery date set for package ${packageId}: ${formattedDate}`, 'success');
            
            alert(`Estimated delivery date set for package ${packageId}: ${formattedDate}`);
            
            // Clear inputs
            document.getElementById('deliveryPackageId').value = '';
            document.getElementById('estimatedDeliveryDate').value = '';
        }
        
        function updatePackageStatus() {
            const packageId = document.getElementById('packageId').value;
            const stage = document.getElementById('packageStage').value;
            const customerName = document.getElementById('customerName').value;
            const location = document.getElementById('currentLocation').value;
            
            if (!packageId) {
                alert('Please enter a Package ID');
                return;
            }
            
            // Update location if provided
            if (location) {
                packageLocations[packageId] = location;
            }
            
            // Update tracking result display if it's visible
            const trackingResult = document.getElementById('trackingResult');
            if (trackingResult.classList.contains('active') && document.getElementById('displayTrackingId').textContent === packageId) {
                const statusText = document.getElementById('packageStatusText');
                statusText.textContent = stage.charAt(0).toUpperCase() + stage.slice(1);
                statusText.className = `status-badge status-${stage}`;
                
                // Update location display
                if (location) {
                    document.getElementById('packageCurrentLocation').textContent = location;
                }
                
                // Update tracking steps
                updateTrackingSteps(stage);
            }
            
            // Add to transaction history with date
            const now = new Date();
            const dateStr = now.toLocaleDateString('en-US', { month: 'long', day: 'numeric', year: 'numeric' });
            let updateText = `Package ${packageId} status updated to ${stage} for ${customerName || 'customer'} on ${dateStr}`;
            if (location) {
                updateText += ` - Location: ${location}`;
            }
            addTransaction(updateText, 'admin');
            
            alert(`Package ${packageId} status updated to ${stage}${location ? ' at ' + location : ''}`);
            
            // Clear form
            document.getElementById('packageId').value = '';
            document.getElementById('customerName').value = '';
            document.getElementById('currentLocation').value = '';
        }
        
        function createNewPackage() {
            const customerName = document.getElementById('customerName').value;
            const destination = document.getElementById('destination').value;
            const location = document.getElementById('currentLocation').value || 'Los Angeles, CA - Processing Facility';
            
            if (!customerName || !destination) {
                alert('Please enter customer name and destination');
                return;
            }
            
            const packageId = 'CRS-' + new Date().getFullYear() + '-' + Math.floor(10000 + Math.random() * 90000);
            
            // Store creation date
            const now = new Date();
            const dateStr = now.toLocaleDateString('en-US', { month: 'long', day: 'numeric', year: 'numeric' });
            packageDates[packageId] = dateStr;
            packageLocations[packageId] = location;
            
            addTransaction(`New package created: ${packageId} for ${customerName} to ${destination} on ${dateStr} - Location: ${location}`, 'success');
            
            alert(`New package created: ${packageId} on ${dateStr} at ${location}`);
            
            // Clear form
            document.getElementById('customerName').value = '';
            document.getElementById('destination').value = '';
            document.getElementById('currentLocation').value = '';
        }
        
        function markPaymentCompleted() {
            const paymentId = document.getElementById('paymentId').value;
            const amount = document.getElementById('paymentAmount').value;
            const method = document.getElementById('paymentMethod').value;
            
            if (!paymentId || !amount) {
                alert('Please enter payment ID and amount');
                return;
            }
            
            // Generate shipping code when admin verifies payment
            const shippingCode = 'SHIP-' + Math.random().toString(36).substr(2, 8).toUpperCase();
            
            const now = new Date();
            const dateStr = now.toLocaleDateString('en-US', { month: 'long', day: 'numeric', year: 'numeric' });
            
            addTransaction(`Payment ${paymentId} verified and marked as completed: $${amount} via ${method} on ${dateStr}. Shipping code: ${shippingCode}`, 'success');
            updateAdminStats();
            
            // Send notification to user
            addMessage('System', `Your payment has been verified on ${dateStr}! Shipping Code: ${shippingCode}. Your package will be dispatched within 24 hours.`, 'admin');
            
            // Also send email notification (simulated)
            window.location.href = `mailto:info.paymentsystem@myyahoo.com?subject=Payment%20Verified%20-%20${paymentId}&body=Payment%20${paymentId}%20has%20been%20verified%20on%20${dateStr}.%20Shipping%20Code:%20${shippingCode}`;
            
            alert(`Payment ${paymentId} verified! Shipping code generated: ${shippingCode}`);
            
            // Clear form
            document.getElementById('paymentId').value = '';
            document.getElementById('paymentAmount').value = '';
        }
        
        function markPaymentPending() {
            const paymentId = document.getElementById('paymentId').value;
            const amount = document.getElementById('paymentAmount').value;
            
            if (!paymentId) {
                alert('Please enter payment ID');
                return;
            }
            
            const now = new Date();
            const dateStr = now.toLocaleDateString('en-US', { month: 'long', day: 'numeric', year: 'numeric' });
            
            addTransaction(`Payment ${paymentId} marked as pending: $${amount} on ${dateStr}`, 'warning');
            
            alert(`Payment ${paymentId} marked as pending`);
        }
        
        function loadTransactions() {
            const transactionHistory = document.getElementById('transactionHistory');
            
            // Sample transactions with dates
            const transactions = [
                { text: 'Package CRS-2023-98765 status updated to pickedup - Location: Los Angeles, CA', type: 'admin', time: 'December 5, 2023' },
                { text: 'Payment PKG-789 verified and completed: $2,850 via Apple Gift Card. Shipping code: SHIP-ABC123', type: 'success', time: 'December 4, 2023' },
                { text: 'New package created: CRS-2023-54321 for John Smith to Germany - Location: San Francisco, CA', type: 'success', time: 'December 3, 2023' },
                { text: 'Estimated delivery date set for package CRS-2023-54321: December 20, 2023', type: 'info', time: 'December 3, 2023' },
                { text: 'Payment TRX-456 marked as pending: $1,250', type: 'warning', time: 'December 2, 2023' },
                { text: 'Package CRS-2023-12345 delivered successfully', type: 'success', time: 'December 1, 2023' }
            ];
            
            transactionHistory.innerHTML = '';
            
            transactions.forEach(transaction => {
                const item = document.createElement('div');
                item.className = `transaction-item ${transaction.type}`;
                item.innerHTML = `
                    <div><strong>${transaction.text}</strong></div>
                    <small>${transaction.time}</small>
                `;
                transactionHistory.appendChild(item);
            });
        }
        
        function loadMessages() {
            const messageHistory = document.getElementById('messageHistory');
            
            // Sample messages
            const messages = [
                { text: 'Customer John: When will my package arrive?', type: 'info', time: 'December 5, 2023' },
                { text: 'Customer Sarah: I sent the gift card payment, please verify', type: 'info', time: 'December 4, 2023' },
                { text: 'Customer Mike: Need shipping code for package CRS-2023-456', type: 'warning', time: 'December 3, 2023' },
                { text: 'System: Payment verified for CRS-2023-123. Shipping code sent.', type: 'success', time: 'December 2, 2023' }
            ];
            
            messageHistory.innerHTML = '';
            
            messages.forEach(message => {
                const item = document.createElement('div');
                item.className = `transaction-item ${message.type}`;
                item.innerHTML = `
                    <div><strong>${message.text}</strong></div>
                    <small>${message.time}</small>
                `;
                messageHistory.appendChild(item);
            });
        }
        
        function addTransaction(text, type) {
            const transactionHistory = document.getElementById('transactionHistory');
            const now = new Date();
            const dateStr = now.toLocaleDateString('en-US', { month: 'long', day: 'numeric', year: 'numeric' });
            
            const item = document.createElement('div');
            item.className = `transaction-item ${type}`;
            item.innerHTML = `
                <div><strong>${text}</strong></div>
                <small>${dateStr}</small>
            `;
            
            transactionHistory.insertBefore(item, transactionHistory.firstChild);
            
            // Keep only last 10 transactions
            if (transactionHistory.children.length > 10) {
                transactionHistory.removeChild(transactionHistory.lastChild);
            }
            
            updateAdminStats();
        }
        
        function updateAdminStats() {
            // Update total payments count
            const totalPayments = document.getElementById('totalPayments');
            const currentCount = parseInt(totalPayments.textContent) || 0;
            totalPayments.textContent = currentCount + 1;
            
            // Update total revenue
            const totalRevenue = document.getElementById('totalRevenue');
            const currentRevenue = parseFloat(totalRevenue.textContent.replace('$', '')) || 0;
            const paymentAmount = parseFloat(document.getElementById('paymentAmount').value) || 2850;
            totalRevenue.textContent = '$' + (currentRevenue + paymentAmount).toLocaleString();
        }
        
        // ========== MESSAGING SYSTEM ==========
        let messages = [];
        
        function showMessagingModal() {
            const modal = document.getElementById('messagingModal');
            modal.classList.add('active');
            document.body.style.overflow = 'hidden';
            loadMessageList();
        }
        
        function closeMessagingModal() {
            const modal = document.getElementById('messagingModal');
            modal.classList.remove('active');
            document.body.style.overflow = 'auto';
        }
        
        function loadMessageList() {
            const messageList = document.getElementById('messageList');
            messageList.innerHTML = '';
            
            if (messages.length === 0) {
                messageList.innerHTML = '<p class="text-center">No messages yet. Start the conversation!</p>';
                return;
            }
            
            messages.forEach(message => {
                const item = document.createElement('div');
                item.className = `message-item ${message.sender === 'admin' ? 'admin' : 'user'}`;
                item.innerHTML = `
                    <div class="message-sender">${message.sender === 'admin' ? 'California Regional Shipping' : 'You'}</div>
                    <div class="message-text">${message.text}</div>
                    <div class="message-time">${message.time}</div>
                `;
                messageList.appendChild(item);
            });
            
            // Scroll to bottom
            messageList.scrollTop = messageList.scrollHeight;
        }
        
        function addMessage(sender, text, type = 'info') {
            const now = new Date();
            const dateStr = now.toLocaleDateString('en-US', { month: 'long', day: 'numeric', year: 'numeric' });
            const timeStr = now.toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' });
            
            messages.push({
                sender: sender,
                text: text,
                time: `${dateStr} at ${timeStr}`,
                type: type
            });
            
            // Update message list if modal is open
            if (document.getElementById('messagingModal').classList.contains('active')) {
                loadMessageList();
            }
            
            // If message is from user, also add to admin panel
            if (sender === 'user') {
                const messageHistory = document.getElementById('messageHistory');
                const item = document.createElement('div');
                item.className = `transaction-item ${type}`;
                item.innerHTML = `
                    <div><strong>Customer: ${text}</strong></div>
                    <small>${dateStr}</small>
                `;
                messageHistory.insertBefore(item, messageHistory.firstChild);
                
                // Keep only last 10 messages in admin panel
                if (messageHistory.children.length > 10) {
                    messageHistory.removeChild(messageHistory.lastChild);
                }
                
                // Also send email notification (simulated)
                window.location.href = `mailto:info.californiaregionalshipping@yahoo.com?subject=New%20Customer%20Message%20-%20${dateStr}&body=Customer%20message%20on%20${dateStr}:%20${text}`;
            }
        }
        
        function sendMessage() {
            const messageInput = document.getElementById('messageInput');
            const text = messageInput.value.trim();
            
            if (!text) {
                alert('Please enter a message');
                return;
            }
            
            // Add user message
            addMessage('user', text, 'info');
            
            // Auto-reply from admin (simulated)
            setTimeout(() => {
                const replies = [
                    "Thank you for your message. Our team will respond within 24 hours.",
                    "We have received your inquiry. Please check your email for updates.",
                    "Your message has been forwarded to our shipping department.",
                    "Thank you for contacting California Regional Shipping. How can we assist you further?"
                ];
                const randomReply = replies[Math.floor(Math.random() * replies.length)];
                addMessage('admin', randomReply, 'success');
            }, 1000);
            
            // Clear input
            messageInput.value = '';
            messageInput.focus();
        }
        
        // ========== PAYMENT MODAL FUNCTIONS ==========
        let selectedPaymentMethod = '';
        let selectedGiftCardType = '';
        
        function showPaymentModal() {
            const modal = document.getElementById('paymentModal');
            modal.classList.add('active');
            document.body.style.overflow = 'hidden';
            
            // Reset selections
            selectedPaymentMethod = '';
            selectedGiftCardType = '';
            
            // Hide all payment sections
            document.getElementById('giftcardSection').classList.remove('active');
            document.getElementById('receiptSection').classList.remove('active');
            document.getElementById('emailUpload').style.display = 'none';
            document.getElementById('fileUpload').style.display = 'none';
            
            // Reset selected states
            document.querySelectorAll('.payment-option').forEach(option => {
                option.classList.remove('selected');
            });
        }
        
        function closePaymentModal() {
            const modal = document.getElementById('paymentModal');
            modal.classList.remove('active');
            document.body.style.overflow = 'auto';
        }
        
        function selectPaymentMethod(method) {
            selectedPaymentMethod = method;
            
            // Update UI
            document.querySelectorAll('.payment-option').forEach(option => {
                option.classList.remove('selected');
            });
            event.currentTarget.classList.add('selected');
            
            // Show appropriate section
            if (method === 'giftcard') {
                document.getElementById('giftcardSection').classList.add('active');
            }
        }
        
        function selectGiftCard(type) {
            selectedGiftCardType = type;
            
            // Update UI
            document.querySelectorAll('.giftcard-option').forEach(option => {
                option.classList.remove('selected');
            });
            event.currentTarget.classList.add('selected');
            
            // Show receipt section
            document.getElementById('receiptSection').classList.add('active');
        }
        
        function submitGiftCardPayment() {
            const now = new Date();
            const dateStr = now.toLocaleDateString('en-US', { month: 'long', day: 'numeric', year: 'numeric' });
            
            addTransaction(`Gift card payment submitted for package CRS-2023-98765 on ${dateStr} - Awaiting verification`, 'warning');
            addMessage('System', `Gift card payment submitted on ${dateStr}. Awaiting admin verification. You will receive your shipping code once payment is confirmed.`, 'info');
            
            // Send email notification to payment system
            window.location.href = `mailto:info.paymentsystem@myyahoo.com?subject=Gift%20Card%20Payment%20Submitted%20-%20CRS-2023-98765%20-%20${dateStr}&body=A%20gift%20card%20payment%20has%20been%20submitted%20on%20${dateStr}%20for%20package%20CRS-2023-98765.%20Please%20verify%20the%20codes.`;
            
            alert(`Thank you! Your gift card payment has been submitted on ${dateStr}. Our admin team will verify the codes and approve your payment within 24 hours.`);
            closePaymentModal();
        }
        
        function showEmailUpload() {
            document.getElementById('emailUpload').style.display = 'block';
            document.getElementById('fileUpload').style.display = 'none';
        }
        
        function showFileUpload() {
            document.getElementById('fileUpload').style.display = 'block';
            document.getElementById('emailUpload').style.display = 'none';
        }
        
        function handleFileUpload() {
            const fileInput = document.getElementById('receiptFile');
            const uploadedFiles = document.getElementById('uploadedFiles');
            
            if (fileInput.files.length > 0) {
                uploadedFiles.innerHTML = '';
                
                Array.from(fileInput.files).forEach(file => {
                    const fileDiv = document.createElement('div');
                    fileDiv.className = 'uploaded-file';
                    fileDiv.innerHTML = `
                        <div>
                            <i class="fas fa-file-image text-accent"></i>
                            ${file.name}
                        </div>
                        <div>
                            <i class="fas fa-check-circle text-success"></i>
                        </div>
                    `;
                    uploadedFiles.appendChild(fileDiv);
                });
            }
        }
        
        // ========== TRACKING FUNCTIONS ==========
        function trackPackage() {
            const trackingNumber = document.getElementById('trackingNumber').value;
            
            if (!trackingNumber) {
                alert('Please enter a tracking number');
                return;
            }
            
            // Show tracking result
            const trackingResult = document.getElementById('trackingResult');
            trackingResult.classList.add('active');
            
            // Update displayed tracking ID
            document.getElementById('displayTrackingId').textContent = trackingNumber;
            
            // Check if package has a stored date
            if (packageDates[trackingNumber]) {
                document.getElementById('packageCreatedDate').textContent = packageDates[trackingNumber];
            } else {
                document.getElementById('packageCreatedDate').textContent = 'December 1, 2023';
            }
            
            // Check if package has a stored location
            if (packageLocations[trackingNumber]) {
                document.getElementById('packageCurrentLocation').textContent = packageLocations[trackingNumber];
            } else {
                document.getElementById('packageCurrentLocation').textContent = 'Los Angeles, California - Processing Facility';
            }
            
            // Check if package has estimated delivery date
            if (estimatedDeliveryDates[trackingNumber]) {
                document.getElementById('estimatedDeliveryDisplay').textContent = estimatedDeliveryDates[trackingNumber];
            } else {
                document.getElementById('estimatedDeliveryDisplay').textContent = 'December 15, 2023';
            }
            
            // Scroll to tracking result
            trackingResult.scrollIntoView({ behavior: 'smooth' });
            
            // Add to admin transactions
            addTransaction(`Package tracked: ${trackingNumber}`, 'info');
        }
        
        function updateTrackingSteps(stage) {
            const steps = document.querySelectorAll('.tracking-step');
            const stageIndex = {
                'processing': 0,
                'confirmed': 1,
                'pickedup': 2,
                'intransit': 3,
                'outfordelivery': 4,
                'delivered': 5
            };
            
            const currentIndex = stageIndex[stage] || 0;
            
            steps.forEach((step, index) => {
                step.classList.remove('active', 'completed');
                
                if (index < currentIndex) {
                    step.classList.add('completed');
                } else if (index === currentIndex) {
                    step.classList.add('active');
                }
            });
        }
        
        // ========== REGISTRATION FORM ==========
        document.getElementById('registrationForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Get form values
            const formData = {
                name: document.getElementById('fullName').value,
                email: document.getElementById('email').value,
                phone: document.getElementById('phone').value,
                currentLocation: document.getElementById('currentPickupLocation').value,
                origin: document.getElementById('origin').value,
                destination: document.getElementById('destination').value,
                description: document.getElementById('packageDescription').value,
                value: document.getElementById('packageValue').value || 'Not specified'
            };
            
            // Generate tracking ID
            const trackingId = 'CRS-' + new Date().getFullYear() + '-' + Math.floor(10000 + Math.random() * 90000);
            
            // Store creation date and location
            const now = new Date();
            const dateStr = now.toLocaleDateString('en-US', { month: 'long', day: 'numeric', year: 'numeric' });
            packageDates[trackingId] = dateStr;
            packageLocations[trackingId] = formData.currentLocation;
            
            // Set default estimated delivery (15 days from now)
            const deliveryDate = new Date(now);
            deliveryDate.setDate(now.getDate() + 15);
            const defaultDeliveryStr = deliveryDate.toLocaleDateString('en-US', { month: 'long', day: 'numeric', year: 'numeric' });
            estimatedDeliveryDates[trackingId] = defaultDeliveryStr;
            
            // Create email content for customer
            const customerEmailSubject = encodeURIComponent(`Shipment Registration Confirmation - ${trackingId} - California Regional Shipping`);
            const customerEmailBody = encodeURIComponent(
`Dear ${formData.name},

Thank you for registering your shipment with California Regional Shipping Company.

📦 REGISTRATION DETAILS:
─────────────────────
Tracking Number: ${trackingId}
Registration Date: ${dateStr}
Current Location: ${formData.currentLocation}
Origin: ${formData.origin}
Destination: ${formData.destination}
Package Description: ${formData.description}
Estimated Value: $${formData.value}
Estimated Delivery: ${defaultDeliveryStr}

🔍 TRACK YOUR PACKAGE:
You can track your package anytime at: https://www.californiaregionalshipping.com/track?code=${trackingId}

📧 WHAT HAPPENS NEXT:
1. Our team will review your shipment details within 24 hours
2. You will receive a custom shipping quote via email
3. After payment confirmation, your package will be scheduled for pickup

📞 NEED ASSISTANCE?
Contact our support team:
Email: info.californiaregionalshipping@yahoo.com
Phone: +1 (213) 555-7890

We appreciate your business and look forward to shipping with you!

Best regards,
California Regional Shipping Company
Global Shipping & Logistics Solutions
`);
            
            // Create email content for admin
            const adminEmailSubject = encodeURIComponent(`New Shipment Registration - ${trackingId} - ${formData.name}`);
            const adminEmailBody = encodeURIComponent(
`NEW SHIPMENT REGISTRATION
─────────────────────

Customer: ${formData.name}
Email: ${formData.email}
Phone: ${formData.phone}
Tracking ID: ${trackingId}
Registration Date: ${dateStr}
Current Location: ${formData.currentLocation}

SHIPMENT DETAILS:
Origin: ${formData.origin}
Destination: ${formData.destination}
Description: ${formData.description}
Value: $${formData.value}
Estimated Delivery: ${defaultDeliveryStr}

This registration requires a shipping quote to be prepared within 24 hours.
`);
            
            // Send email to customer (opens default email client)
            window.location.href = `mailto:${formData.email}?subject=${customerEmailSubject}&body=${customerEmailBody}`;
            
            // Send email to admin (opens in new window/tab)
            setTimeout(() => {
                window.open(`mailto:info.californiaregionalshipping@yahoo.com?subject=${adminEmailSubject}&body=${adminEmailBody}`, '_blank');
            }, 500);
            
            // Show success message
            alert(`✅ Thank you, ${formData.name}! Your shipment has been registered.\n\nA confirmation email has been sent to: ${formData.email}\n\nYour Tracking ID: ${trackingId}\nRegistration Date: ${dateStr}\nCurrent Location: ${formData.currentLocation}\n\nOur team will contact you within 24 hours with a custom quote.`);
            
            // Add to admin transactions
            addTransaction(`New registration: ${formData.name} - ${trackingId} from ${formData.origin} to ${formData.destination} on ${dateStr} - Location: ${formData.currentLocation}`, 'success');
            
            // Send welcome message in chat
            addMessage('admin', `Welcome ${formData.name}! Your package ${trackingId} has been registered on ${dateStr} from ${formData.currentLocation}. We'll contact you soon with shipping details. A confirmation email has been sent to ${formData.email}.`, 'success');
            
            // Reset form
            this.reset();
            
            // Update tracking input with new ID
            document.getElementById('trackingNumber').value = trackingId;
            
            // Scroll to tracking section
            document.getElementById('tracking').scrollIntoView({ behavior: 'smooth' });
        });
        
        // ========== INITIALIZATION ==========
        document.addEventListener('DOMContentLoaded', function() {
            // Initialize with sample data
            updateTrackingSteps('pickedup');
            
            // Set sample package data
            packageDates['CRS-2023-98765'] = 'December 1, 2023';
            packageLocations['CRS-2023-98765'] = 'Los Angeles, California - Processing Facility';
            estimatedDeliveryDates['CRS-2023-98765'] = 'December 15, 2023';
            
            // Set modal data
            document.getElementById('modalPackageId').textContent = 'CRS-2023-98765';
            document.getElementById('modalShippingCost').textContent = '$2,850.00';
            document.getElementById('modalTotalAmount').textContent = '$2,850.00';
            document.getElementById('modalDeliveryDate').textContent = 'December 15, 2023';
            
            // Close modals when clicking outside
            document.getElementById('paymentModal').addEventListener('click', function(e) {
                if (e.target === this) {
                    closePaymentModal();
                }
            });
            
            document.getElementById('messagingModal').addEventListener('click', function(e) {
                if (e.target === this) {
                    closeMessagingModal();
                }
            });
            
            document.getElementById('codeModal').addEventListener('click', function(e) {
                if (e.target === this) {
                    closeCodeModal();
                }
            });
            
            // Initialize admin stats
            updateAdminStats();
            
            // Add some sample messages
            setTimeout(() => {
                addMessage('admin', 'Welcome to California Regional Shipping! How can we assist you today?', 'success');
            }, 1000);
            
            // Keyboard shortcut for admin panel (Ctrl+Shift+A)
            document.addEventListener('keydown', function(e) {
                if (e.ctrlKey && e.shiftKey && e.key === 'A') {
                    // Show code entry modal
                    showCodeModal();
                    e.preventDefault();
                }
            });
        });
        
        // ========== SMOOTH SCROLLING ==========
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if (targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if (targetElement) {
                    targetElement.scrollIntoView({
                        behavior: 'smooth'
                    });
                    
                    // Update active nav link
                    document.querySelectorAll('nav a').forEach(link => {
                        link.classList.remove('active');
                    });
                    this.classList.add('active');
                }
            });
        });
        
        // Update active nav on scroll
        window.addEventListener('scroll', function() {
            const sections = document.querySelectorAll('section');
            const navLinks = document.querySelectorAll('nav a');
            
            let current = '';
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                if (scrollY >= (sectionTop - 200)) {
                    current = section.getAttribute('id');
                }
            });
            
            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href') === `#${current}`) {
                    link.classList.add('active');
                }
            });
        });
    </script>
</body>
</html>
