BPMN Process Modeling Assignment(ALL BPMN files are inside bpmn folder and the screenshots are in readme and in images folder)
Scenario 1: Employee Leave Approval
<img width="1643" height="462" alt="leave-approval png" src="https://github.com/user-attachments/assets/92cdcd42-bc0c-4a48-a0f1-26678bb095d4" />
Process Description
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
<img width="1395" height="581" alt="purchase-order png" src="https://github.com/user-attachments/assets/f3f7770e-08bb-4151-8549-d7224a97dac4" />

Process Description
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
<img width="1022" height="570" alt="it-" src="https://github.com/user-attachments/assets/a8fdc9b2-37ae-47f8-9e24-26b828ce2cca" />


Process Description
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
