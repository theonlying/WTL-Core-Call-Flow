<img src="images/CS_Mobile_Mobile_Call_with_Call_Completion_to_Busy_Subscriber.png" style="width:6.62535in;height:4.9586in"
alt="A diagram of a computer AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| CCBS service active in HLR, MSC supports CCBS signaling | Calling MS, Called MS, MSC/VLR, HLR |

- **HLR/HSS:** Both the originating and terminating subscribers must
  have the CCBS supplementary service provisioned in their HLR profiles.

- **MSC:** The MSCs must be configured to support the CCBS signaling
  procedures, including setting timers to monitor when a busy subscriber
  becomes idle and initiating the recall procedure.
