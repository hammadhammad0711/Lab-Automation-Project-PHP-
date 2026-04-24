# Lab Automation System

A comprehensive web-based testing management system for SRS Electrical Appliances, designed to streamline the testing workflow from manufacturing to CPRI approval and market release.

## Features

### Core Functionality
- **Product Management**: 10-digit unique product IDs with manufacturing details
- **Testing Records**: 12-digit auto-generated test IDs with comprehensive tracking
- **Role-Based Access**: Admin, Technician, and Officer roles with appropriate permissions
- **Advanced Search**: Powerful search functionality for products and test records
- **CPRI Integration**: Seamless workflow for sending products to CPRI for approval
- **Real-time Analytics**: Comprehensive dashboards with statistics and trends

### User Roles
1. **Admin**: Full system access, product management, user management
2. **Technician**: Conduct tests, manage testing workflow, record results
3. **Officer**: Monitor system, view analytics, manage CPRI submissions

## Installation

### Prerequisites
- XAMPP/WAMP/MAMP server stack
- PHP 7.4 or higher
- MySQL/MariaDB database
- Modern web browser

### Setup Instructions

1. **Extract the Files**
   - Place all files in your web server's root directory (e.g., `htdocs/lab_automation`)

2. **Database Setup**
   - Start your MySQL server
   - Create a new database named `lab_automation1`
   - Import the database schema from `database/schema.sql`
   - Update database connection in `config/db.php` if needed

3. **Web Server Configuration**
   - Ensure Apache is running
   - Navigate to `http://localhost/lab_automation` in your browser

## Default Login

**Admin Credentials:**
- Username: `admin`
- Password: `admin123`

## System Workflow

### 1. Product Management
- Admin adds products with 10-digit IDs
- Products categorized by type (Switch Gears, Fuses, Capacitors, etc.)
- Status tracking: Manufactured → Testing → Approved/Rejected

### 2. Testing Process
- Technicians select products for testing
- Choose appropriate test types (Voltage, Insulation, Temperature, etc.)
- Record test criteria, expected output, and actual results
- Auto-generate 12-digit test IDs

### 3. CPRI Integration
- Approved products sent to CPRI for final approval
- Track CPRI reference numbers and results
- Complete workflow from manufacturing to market release

### 4. Analytics & Reporting
- Real-time dashboards for all user roles
- Testing statistics and trends
- Technician performance metrics
- Monthly testing reports

## File Structure

```
lab_automation/
├── admin/
│   ├── dashboard.php          # Admin dashboard with analytics
│   └── products.php           # Product management interface
├── technician/
│   ├── dashboard.php          # Technician testing interface
│   └── test_process.php       # Test processing logic
├── officer/
│   ├── dashboard.php          # Officer monitoring dashboard
│   └── cpri_process.php       # CPRI submission handling
├── auth/
│   ├── login.php              # Login interface
│   ├── login_process.php      # Authentication logic
│   └── logout.php             # Logout functionality
├── includes/
│   ├── header.php             # Common header with navigation
│   ├── footer.php             # Common footer
│   └── auth_check.php         # Authentication middleware
├── ajax/
│   └── get_product.php        # AJAX product data retrieval
├── assets/
│   ├── css/style.css          # Custom styling
│   └── js/custom.js          # Custom JavaScript
├── config/
│   └── db.php                 # Database configuration
├── database/
│   └── schema.sql             # Database schema
├── search.php                 # Advanced search interface
└── index.php                  # Main landing page
```

## Database Schema

### Key Tables
- `users` - User authentication and roles
- `products` - Product information with 10-digit IDs
- `testing_records` - Test records with 12-digit IDs
- `testing_types` - Available test types
- `product_categories` - Product categorization
- `cpri_testing` - CPRI submission tracking
- `activity_log` - System activity tracking

## Usage Instructions

### For Administrators
1. Login with admin credentials
2. Add products and categories
3. Manage user accounts
4. Monitor system statistics
5. View comprehensive analytics

### For Technicians
1. Login with assigned credentials
2. Select products for testing
3. Conduct various types of tests
4. Record detailed test results
5. Track testing progress

### For Officers
1. Login with officer credentials
2. Monitor testing statistics
3. Review technician performance
4. Send approved products to CPRI
5. Generate reports

## Test ID Generation

The system automatically generates 12-digit test IDs using the format:
- **First 6 digits**: Product code (from product ID)
- **Next 4 digits**: Test type code
- **Last 2 digits**: Roll number (01-99)

Example: `123456VT00101`

## Security Features

- Password hashing using PHP's `password_hash()`
- SQL injection prevention with prepared statements
- Session-based authentication
- Role-based access control
- Activity logging for audit trails

## Browser Compatibility

- Chrome 80+
- Firefox 75+
- Safari 13+
- Edge 80+

## Support

For technical support or questions about the system:
1. Check the error logs in your web server
2. Verify database connection settings
3. Ensure all PHP extensions are enabled
4. Review browser console for JavaScript errors

## Future Enhancements

- Email notifications for test results
- File attachment support for test documents
- Advanced reporting with PDF export
- Mobile-responsive application
- API integration for external systems

---

**Developed for SRS Electrical Appliances**
*Version 1.0 - 2024*
