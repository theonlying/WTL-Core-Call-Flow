<img src="images/CS_Mobile_Terminating_Call_with_Unconditional_Forwarding.png" style="width:6.525in;height:3.95833in"
alt="A diagram of a machine AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| CFU provisioned in HLR, MSC routes directly to forwarding number | MS, MSC/VLR, HLR, Forwarding Number |

**HLR/HSS:** The subscriber's HLR profile must be defined with the
"unconditional forwarding" flag and the number to which all calls should
be forwarded. This setting bypasses the standard location query to the
VLR.
