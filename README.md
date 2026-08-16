BPMN Process Modeling Assignment(ALL BPMN files are inside bpmn folder and the screenshots are in readme and in images folder)

Scenario 1: Employee Leave Approval
<img width="1643" height="462" alt="leave-approval png" src="https://github.com/user-attachments/assets/e7c55dd4-4166-47cc-9cb4-2a85bc78ef7f" />



Process Description : 
An employee applies for leave through the HR system. The system first checks whether the employee has enough leave balance before routing the request to a manager for a decision.

Flow Logic
Start Event – "Employee Submits Leave Request" triggers the process.
Task – "Check Leave Balance": the HR system verifies available balance.
Exclusive Gateway – "Sufficient Balance?"
No → Task "Send Insufficient Balance Notification" → End Event "Insufficient Balance".
Yes → Task "Send Request to Manager for Approval".
Exclusive Gateway – "Manager Approves?"
Approved → Task "Update Employee Leave Balance" → Task "Send Approval Notification" → End Event "Leave Approved".
Rejected → Task "Send Rejection Notification" → End Event "Leave Rejected".

Scenario 2: Online Purchase Order Processing
<img width="1395" height="581" alt="purchase-order png" src="https://github.com/user-attachments/assets/e93782f8-17f0-43f9-815d-8ebed7b38018" />



Process Description :
A customer places an online order. The system checks stock availability and processes payment before confirming and shipping the order.

Flow Logic
Start Event – "Customer Places Order".
Task – "Check Product Availability".
Exclusive Gateway – "Product Available?"
No → Task "Notify Customer - Out of Stock" → End Event "Out of Stock" (process ends here).
Yes → Task "Process Payment".
Exclusive Gateway – "Payment Successful?"
No → Task "Notify Customer - Payment Failed" → End Event "Payment Failed" (process ends here).
Yes → Task "Confirm Order" → Task "Prepare Product for Shipment" → Task "Ship Order" → Task "Send Shipping Confirmation" → End Event "Order Completed".

Scenario 3 - IT Service Request
<img width="1022" height="570" alt="it-" src="https://github.com/user-attachments/assets/adc9acdf-3ca4-43ad-8fbf-9644607b0307" />


Process Description :
An employee reports an IT problem. The help desk registers and triages it by severity, assigns it to the right technician tier, and routes it internally or externally depending on whether it can be resolved in-house.

Flow Logic
Start Event – "Employee Reports IT Problem".
Task – "Submit IT Support Request".
Task – "Register Request" (help desk logs the ticket).
Task – "Check Severity of the Problem".
Exclusive Gateway – "Severity Level?"
Low Severity → Task "Assign to Support Technician".
High Severity → Task "Assign to Senior Technician".
Both paths converge at a merging Exclusive Gateway before continuing (a technician has now been assigned, regardless of tier).
Task – "Investigate the Problem".
Exclusive Gateway – "Resolvable Internally?"
Yes → Task "Fix the Problem".
No → Task "Escalate to External Service Provider".
Both paths converge again at a second merging Exclusive Gateway (resolution has been reached either way).
Task – "Update Request Status".
Task – "Send Resolution Notification to Employee".
End Event – "Request Resolved".
