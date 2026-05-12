# Vokto - Hyper-local Handyman Marketplace

Vokto is a serverless, event-driven service marketplace designed to connect local customers with service providers (mechanics/mistris) in real-time.

## 🚀 Architecture Overview
The project is built using a **Zero-Infrastructure Cost** model, leveraging cloud automation and serverless tools.

- **Frontend:** HTML5, CSS3, JavaScript (Hosted on Netlify).
- **Domain:** Godaddy
- **Automation Hub:** Make.com (formerly Integromat).
- **Database:** Google Sheets API (for CRM and record-keeping).
- **Real-time Notifications:** Telegram Bot API (for instant lead alerts).
- **Email Infrastructure:** Cloudflare Email Routing + Brevo SMTP for custom @vokto.in domain.

## 🛠️ How it Works
1. **Lead Generation:** Customers fill a booking form with their service type and pincode.
2. **Data Orchestration:** Make.com captures the webhook and logs the data into Google Sheets.
3. **Logic-Based Matching:** The system compares the customer's pincode and service requirements with the registered provider database.
4. **Instant Dispatch:** - If a match is found, the **VoktoBot** sends a message to the Telegram Group with customer details.
   - If no match is found, an urgent notification is sent to the admin.
5. **Confirmation:** Booking numbers and registration IDs are dynamically generated and displayed to users.

## 📈 Technical Highlights
- **Cost Optimization:** Achieved 100% functionality using free-tier cloud services.
- **Serverless Backend:** No dedicated server maintenance required.
- **Scalability:** The logic can be easily expanded to other cities and service categories.

## 🖥️ ## 🚀 Deployment
The site is live at: [https://vokto.in](https://vokto.in)


**"System Workflow"**

**1) Workflow Breakdown:**

**User Layer:** Customer/Mistry interacts with the Frontend (HTML/JS) on Netlify.

**API Gateway:** Form submission triggers a Webhook to Make.com.

**2) Data Processing Layer:**

**Node A:** Data is logged into Google Sheets (The Database).

**Node B (Router):** Logic matching starts (Condition: Customer Pincode == Mistry Pincode AND Service Type == Expertise).

**3) Notification Layer:**

**Match Found:** Telegram Bot triggers a notification to the "Booking Group".

**No Match:** Admin receives an "Urgent: Provider Not Found" alert.

**4) Communication Layer:** Confirmation emails are sent via Brevo SMTP through the Cloudflare routed custom email.
