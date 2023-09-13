Designing a system like Gmail, which serves billions of users worldwide, is a comprehensive task. Here's a high-level architecture followed by a more granulated low-level design:

### High-Level Design:

1. **User Interface (Frontend)**:
    - **Web Application**: Using frameworks like React or Angular.
    - **Mobile Application**: Native apps for Android and iOS.

2. **Backend Servers**:
    - **API Servers**: Handle requests from clients and deliver email content.
    - **SMTP Servers**: Handle sending and receiving emails using the Simple Mail Transfer Protocol.

3. **Data Storage**:
    - **Databases**: Store user information, email metadata, contacts, etc.
        - Relational DBs (e.g., MySQL, PostgreSQL) for structured data.
        - NoSQL DBs (e.g., Bigtable) for email content, logs, etc.
    - **File Storage**: Store attachments and large email contents.

4. **Other Components**:
    - **Search Engine**: Elasticsearch or similar for searching through emails efficiently.
    - **Notification Service**: Notify users of new emails.
    - **Spam Detection Service**: Machine Learning-based system for detecting spam emails.

5. **Infrastructure**:
    - **Load Balancers**: Distribute incoming traffic.
    - **Caching**: Cache frequent queries and reduce database load.
    - **CDN**: Distribute media and assets.

### Low-Level Design:

1. **User Management**:
    - **Registration**: Secure sign-up via email/password.
    - **Authentication**: OAuth tokens, 2-factor authentication, and security keys.
    - **Profile Management**: Allow users to manage their profile, signature, out-of-office replies, etc.

2. **Email Flow**:
    - **Receiving Emails**: SMTP servers receive emails and store them in the database.
    - **Sending Emails**: SMTP servers handle sending emails. Emails to be sent are stored in a queue and sent asynchronously.
    - **Email Storage**: Each email is assigned a unique ID, and the email's metadata (like subject, sender, timestamp) and body are stored separately to optimize for read operations.
    - **Attachments**: These are stored in a distributed file storage. Only references to these attachments are stored with the email metadata.

3. **Email Features**:
    - **Threads**: Emails are grouped by subject to create threads/conversations.
    - **Labels & Categories**: Users can assign labels. Incoming emails are categorized (e.g., Primary, Social, Promotions).
    - **Filters & Rules**: Users can set up rules to auto-sort emails.

4. **Search**:
    - Emails and attachments are indexed.
    - Provide capabilities to search by various parameters (from, to, date range, containing attachments, etc.).

5. **Spam & Security**:
    - **Spam Detection**: ML models trained on spam patterns. User feedback refines this model.
    - **Malware Scanning**: Attachments are scanned for malware and viruses.
    - **HTTPS**: All data in transit is encrypted.
    - **End-to-End Encryption**: While Gmail currently does not offer E2E encryption like some other providers, it could be implemented for added security.

6. **Scalability & Performance**:
    - **Horizontal Scaling**: Add more servers during high loads.
    - **Sharding**: Distribute database to ensure quick read/write.
    - **Replication**: Ensure data availability and durability.

7. **Backup & Recovery**:
    - **Data Backup**: Regular backups of email data.
    - **Disaster Recovery**: Mechanisms to restore service after catastrophic failures.

8. **Monitoring & Analytics**:
    - **Monitoring Tools**: Monitor system health and performance.
    - **User Analytics**: Understand user behavior and improve the system accordingly.

Again, this is a simplified overview. Gmail's actual architecture has evolved over many years and would have numerous optimizations, additional features, and systems in place. The design mentioned above is intended as a starting point, showing the kind of systems and considerations that would go into building a global-scale email service.