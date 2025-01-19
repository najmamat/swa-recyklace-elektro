# Software Architecture Course Assignment (4IT575)

**Authors:** Štěpán Beran, Matouš Najman, Josef Fiedler, and Michael Veis

## Tasks
1. Based on the requirements described below, design two suitable architectures for implementing the application.
2. Document the proposed architectures.
3. In conclusion, evaluate which of the selected architectures is more suitable and why.

## Note
If any requirement is not explicitly stated in the assignment, discuss within the team and define it yourself, as you would inquire with the client.

## Application Description
A large electronics retailer wants to start a business in electronics recycling and needs a new system. Customers can send their small personal electronic devices or use local kiosks in shopping centers and potentially receive money for their used device if it is in working condition.

### Users
Hundreds, potentially thousands to millions...

### Requirements
- Customers can receive offers for used personal electronic equipment (phones, cameras, etc.) either through the website or a kiosk in a shopping center.
- Customers receive a box by mail, send their electronic device, and if it's in good condition, they get paid.
- Upon receiving the device, it is assessed/checked whether it can be recycled/safely disposed of or sold (eBay, etc.).
- The company expects to add 5-10 new types of electronics each month that they will accept.

### Additional Context
- This is a highly competitive activity and a new business area for us.
- If we haven't received a certain type of electronic device even once in the past year, we remove it from our system.
- We need to maintain a list of electronic devices we are willing to accept, as it changes frequently.
- Each device has its own assessment/checking rules.
- We have the right to change the original price offer to the customer if the product is not in the condition declared by the customer.

### Additional Information
Following consultation, these points were clarified:

#### Shipping
- The system will be integrated with carriers Zásilkovna and PPL
- These carriers will handle both sending empty boxes to customers and receiving devices for recycling

#### Payments
- The system will automatically process payments to customers
- Final payment is initiated by the technician after device inspection as the last step of the process

#### Device Sales
- Functional devices will be sold through eBay and Aukro platforms
- Sales will be managed by a dedicated sales manager
- The system will include integration with these sales platforms

#### System Administration
- The system will include an administrative interface for managing:
  - Catalog of accepted devices
  - Device assessment rules
  - User accounts and roles
  - Pricing policies
  - Integrations with carriers and sales platforms

#### Shipment Tracking
- Customers will be able to track their order status in real-time
- Tracking will be integrated with carrier APIs