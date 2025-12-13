# Lobola Africa

A secure, culturally respectful platform for tracking and finalizing lobola negotiations between families—guided workflows, tribe-specific templates, and permanent records.

## Live links
- 🌍 Website: https://lobola.africa
- 📱 Android: Google Play Store (Built with Capacitor, in production)
  [![Website](https://img.shields.io/website?url=https%3A%2F%2Flobola.africa)](https://lobola.africa)

## Highlights
- ✅ **Full-stack application** with authentication, role-based workflows, audit trails, and PDF exports
- 🌐 **Tribe templates** for Ndebele, Zulu, Pedi, Shona, Xhosa, Tswana (customizable line items)
- 🔔 **Real-time notifications** via email using Nodemailer
- 🔒 **Security & Privacy** with JWT authentication, role-based access control, encrypted sensitive fields, and consent flows
- 📱 **Cross-platform mobile** deployment using Capacitor (Android)

## Why it matters
Miscommunication and missing records create tension in traditional lobola negotiations. Lobola Africa standardizes expectations, preserves agreements digitally, and respects cultural practices while adding modern convenience and security.

## Architecture

### **Frontend**
- **Framework:** Next.js 15 (React 18) with App Router
- **Language:** TypeScript for type safety
- **UI Components:** Material-UI (MUI) v5 with custom themes
- **Styling:** Tailwind CSS for utility-first styling
- **State Management:** React Query (TanStack Query) for server state, React Hooks for local state
- **HTTP Client:** Axios for API communication
- **Mobile:** Capacitor for cross-platform Android deployment

### **Backend**
- **Runtime:** Node.js
- **Framework:** Express.js REST API
- **Authentication:** JSON Web Tokens (JWT) with bcryptjs password hashing
- **Database ORM:** Mongoose ODM for MongoDB
- **File Uploads:** Multer for handling document uploads
- **Email Service:** Nodemailer for invitation and notification emails
- **Security:** CORS enabled, environment variables via dotenv

### **Database**
- **Primary Database:** MongoDB Atlas (Cloud)
- **Models:** Users, Families, Tribes, Negotiations, LineItems, Invitations, Events (audit trail), Messages
- **Data Protection:** Sensitive fields encrypted, role-based data access

### **Infrastructure & Deployment**
- **Hosting:** Google Cloud Platform (App Engine/Compute Engine)
- **CI/CD:** GitHub Actions for automated testing and deployment
- **Monitoring:** Application logging and error tracking
- **Domain:** Custom domain (lobola.africa) with SSL/TLS encryption

## Data Model (Simplified)
- **Users:** Authentication profiles with roles (Admin, Family Representative, Mediator)
- **Families:** Family groups participating in negotiations
- **Tribes:** Cultural templates with predefined negotiation line items
- **Negotiations:** Core negotiation sessions with status tracking
- **LineItems:** Individual negotiation items (cattle, money, gifts)
- **Invitations:** Tokenized invites for family members
- **Events:** Audit trail for all negotiation activities
- **Messages:** Communication between parties

## Development Setup

### **Prerequisites**
- Node.js 18+ and npm
- MongoDB Atlas account or local MongoDB instance
- Google Cloud Platform account (for deployment)

### **Installation**
```bash
# Clone repository
git clone https://github.com/Talic10/lobola-africa.git

# Install backend dependencies
cd lobola-backend
npm install

# Install frontend dependencies
cd ../lobola-frontend
npm install

# Set up environment variables
cp .env.example .env.local
# Configure your environment variables
