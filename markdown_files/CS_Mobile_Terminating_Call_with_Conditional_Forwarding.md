<img src="images/CS_Mobile_Terminating_Call_with_Conditional_Forwarding.png" style="width:6.60034in;height:4.81692in"
alt="A diagram of a system AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| Conditional forwarding (CFB/CFNRy) provisioned in HLR with valid target number | MS, MSC/VLR, HLR, Forwarding Number |

**HLR/HSS:** The subscriber's HLR profile must have the conditional
forwarding flag enabled and the forwarded-to number stored. The profile
must also specify the conditions for forwarding, such as "Forward on
Busy," "Forward on No Reply," or "Forward on Not Reachable."
