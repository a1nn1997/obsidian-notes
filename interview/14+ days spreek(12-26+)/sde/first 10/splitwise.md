Splitwise is an application that allows friends and groups to keep track of shared expenses, making it easier to settle up amounts owed in a transparent manner. Designing such a system involves a number of considerations, from data modeling to transactional integrity.

### High-Level Components:

1. **User Management**
   - Registration
   - Authentication & Authorization
   - Profile Management

2. **Groups Management**
   - Creation of a group
   - Adding/removing members

3. **Expenses Management**
   - Add an expense
   - Split expense (equally, percentage-wise, exact amounts, etc.)
   - Settle up/clear dues

4. **Notifications and Reminders**
   - Notify users of added expenses
   - Remind users of pending dues

5. **Activity Feed/History**
   - Log of all expenses and settlements

6. **Data Storage**

### Detailed Design:

1. **User Management**:
   - Use JWT or OAuth for token-based authentication.
   - Store user profiles with details like name, email, phone number, etc.

2. **Groups Management**:
   - Every group will have a unique ID, a list of user IDs, and related expenses.
   - Users can be added/removed from a group by the creator or by majority approval (for fairness).

3. **Expenses Management**:
   - When an expense is added:
     - The payer reports the total amount.
     - Specifies the split (can be equal or based on exact amounts/percentages).
     - System calculates the owed amounts and updates the user balances.
   - Users can settle up:
     - Directly specify an amount to a friend.
     - Use integrated payment systems to clear dues.
   - Balances can be viewed per friend or per group.

4. **Notifications and Reminders**:
   - Use WebSockets for real-time notifications.
   - Scheduled jobs for sending email/SMS reminders.

5. **Activity Feed**:
   - Every action (expense added, payment made, group joined, etc.) is logged.
   - Users can view their activity feed to see all past actions.

6. **Data Storage**:
   - Relational databases would be apt for this kind of application because of the structured nature of the data.
   - Use tables for users, groups, expenses, payments, etc.
   - Maintain a `balances` table to keep track of the amount owed between each pair of users.

### Scalability:

1. **Horizontal Scaling**: As the number of users grows, the backend servers and databases can be scaled out.

2. **Caching**: Use caching mechanisms like Redis for frequently accessed data like user profiles, recent expenses, and notifications.

3. **Database Sharding**: If the user base becomes extremely large, sharding can be implemented. One approach could be to shard based on user IDs or geographic locations.

### Other Considerations:

- **Transactional Integrity**: When updating the balance between users, ensure that the operation is atomic to avoid inconsistencies.

- **Security**: Ensure that users can only see and modify their data. Use HTTPS for data in transit, and encrypt sensitive data at rest.

- **Backup and Recovery**: Implement regular backups of the database and ensure there's a disaster recovery plan in place.

- **Integrations**: For settling up, there might be integrations with payment gateways or banks.

- **Internationalization and Localization**: If the app is to be used worldwide, consider currency conversions, multi-language support, etc.

This design is a foundational blueprint. In a real-world scenario, there will be more complexities, edge cases, and features to consider.