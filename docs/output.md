1.  CS Mobile Originated Call

<img src="media/media/image1.png"
style="width:5.25721in;height:0.67365in"
alt="A close up of text AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| Subscriber provisioned in HLR, MO call service active, MSC routing configured | MS, BTS/BSC/NodeB/RNC, MSC/VLR, HLR |

- **HLR/HSS:** A subscriber profile must be defined, including the
  International Mobile Subscriber Identity (IMSI) and the Mobile Station
  International Subscriber Directory Number (MSISDN).

- **VLR:** The VLR must have a record of the subscriber's location,
  including the Location Area Identity (LAI) and a temporary subscriber
  identifier (TMSI).

- **MSC:** Must be configured with routing tables and digit analysis to
  interpret the dialed number and route the call to its destination.

- **BSC/RNC:** Must be configured with radio channel definitions,
  including frequencies and timeslots, for the serving cells.

2.  CS Mobile Terminating Call

<img src="media/media/image2.png"
style="width:5.84058in;height:1.15284in"
alt="A close-up of a map AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| MT call service active, GMSC routing to MSC, subscriber reachable in VLR | MS, BTS/BSC/NodeB/RNC, GMSC, MSC/VLR, HLR |

- **HLR/HSS:** The HLR must contain the subscriber's profile and be
  addressable by the Gateway MSC (GMSC) to provide routing information.
  It must be able to provide the address of the serving VLR.

- **GMSC:** Must be configured to query the HLR for the called
  subscriber's routing information.

- **VLR:** Must have a valid location record for the subscriber.

- **MSC:** Must be configured to receive the call from the GMSC and
  initiate the paging process to locate the mobile station.

3.  CS Mobile Mobile Call

<img src="media/media/image3.png" style="width:6.09059in;height:1.132in"
alt="A close-up of a computer screen AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| Both subscribers active in HLR/VLR, MSC-MSC routing/trunks configured | Calling MS, Called MS, MSCs, HLR, VLR |

**Definitions:** This is a combination of MO and MT definitions. Both
the originating and terminating subscribers must have their respective
profiles and location data defined in the network.

4.  CS Prepaid Mobile Originated Call

<img src="media/media/image4.png"
style="width:6.19476in;height:1.29868in"
alt="A close-up of a computer screen AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| CAMEL trigger in HLR, prepaid profile in SCP, CAP signaling enabled | MS, MSC/VLR, HLR, SCP/IN |

- **HLR/HSS:** The subscriber's profile must be flagged to indicate that
  they are a prepaid subscriber. This flag triggers a routing
  instruction to the Intelligent Network (IN) platform.

- **MSC/SSP:** The Mobile Switching Center (MSC) must be provisioned as
  a Service Switching Point (SSP) and configured with an Initial
  Detection Point (IDP) trigger for prepaid subscribers.

- **SCP:** The Service Control Point (SCP) must be provisioned with the
  subscriber's account balance, tariff plan, and the logic to approve
  the call and a granted duration.

5.  CS Prepaid Terminating Call

<img src="media/media/image5.png"
style="width:6.04198in;height:1.88204in"
alt="A diagram of a diagram AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| CAMEL trigger in HLR, prepaid SCP routing for incoming calls | MS, GMSC, MSC/VLR, HLR, SCP/IN |

**Definitions:** For a terminating call to have prepaid logic (e.g., for
certain forwarded calls or premium services), the HLR profile and the
MSC/SSP must have specific triggers defined for Mobile Terminating calls
to initiate an IN query to the SCP.

6.  CS Prepaid Mobile Mobile Call

<img src="media/media/image6.png"
style="width:4.77108in;height:4.02798in"
alt="A diagram of a call center AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| Both subs prepaid-enabled, CAMEL triggers in HLR, MSC-IN connectivity | Calling MS, Called MS, MSCs, HLR, SCP/IN |

**Definitions:** This scenario combines the definitions of prepaid MO
and MT calls for both the originating and terminating legs of the call,
as applicable.

7.  CS Mobile Terminating Call with Conditional Forwarding

<img src="media/media/image7.png"
style="width:6.2781in;height:4.08354in"
alt="A diagram of a system AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| Conditional forwarding (CFB/CFNRy) provisioned in HLR with valid target number | MS, MSC/VLR, HLR, Forwarding Number |

**HLR/HSS:** The subscriber's HLR profile must have the conditional
forwarding flag enabled and the forwarded-to number stored. The profile
must also specify the conditions for forwarding, such as "Forward on
Busy," "Forward on No Reply," or "Forward on Not Reachable."

8.  CS Mobile Mobile Call with Conditional Forwarding

<img src="media/media/image8.png" style="width:6.3in;height:3.425in"
alt="A diagram of a network AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| Forwarding active for called MS, MSC routes to forwarding number | Calling MS, Called MS, MSCs, HLR |

**Definitions:** Similar to the previous item, the called subscriber's
HLR profile must define the conditional forwarding criteria. The MSC
handling the terminating leg must recognize the busy or no-reply
condition and initiate the forwarding procedure.

9.  CS Mobile Terminating Call with Unconditional Forwarding

<img src="media/media/image9.png" style="width:6.3in;height:3.52917in"
alt="A diagram of a machine AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| CFU provisioned in HLR, MSC routes directly to forwarding number | MS, MSC/VLR, HLR, Forwarding Number |

**HLR/HSS:** The subscriber's HLR profile must be defined with the
"unconditional forwarding" flag and the number to which all calls should
be forwarded. This setting bypasses the standard location query to the
VLR.

10. CS Mobile Mobile Call with Unconditional Forwarding
    <img src="media/media/image10.png"
    style="width:6.23643in;height:3.48629in"
    alt="A diagram of a network AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| CFU active, called subscriber always forwarded to defined number | Calling MS, Called MS, MSCs, HLR |

**Definitions:** The HLR profile of the called subscriber must be
defined with unconditional forwarding. The originating MSC's query to
the HLR for the called party's location will be redirected to the
forwarded number.

11. CS VMS Retrieval

<img src="media/media/image11.png"
style="width:5.17388in;height:1.23617in"
alt="A black and white image of a map AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| VMS number provisioned in HLR, MSC routes to VMS system | MS, MSC/VLR, HLR, Voice Mail System (VMS) |

- **MSC:** The MSC's digit analysis and routing tables must have a
  specific entry that routes calls to the Voice Mail System (VMS)
  platform based on the dialled VMS retrieval short Code (e.g., \*123).

- **VMS:** The VMS platform must be configured to receive calls and
  authenticate the subscriber based on their CLI (Calling Line
  Identity).

12. CS PPS VMS Retrieval

<img src="media/media/image12.png"
style="width:4.86136in;height:1.75704in"
alt="A screenshot of a computer screen AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| Prepaid profile provisioned, CAMEL routing to VMS | MS, MSC/VLR, SCP/IN, VMS |

**Definitions:** Similar to prepaid calls, the VMS short Code in the MSC
must be configured with an IN trigger to query the SCP for the
subscriber's balance before allowing access to the voicemail service.

13. CS Inter MSC Handover

<img src="media/media/image13.png"
style="width:5.48639in;height:1.90288in" />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| Inter-MSC trunks configured, MAP/ISUP for HO signaling | MS, Source MSC, Target MSC, BTS/BSC, RNC |

- **MSC:** Both the Source and Target MSCs must have a defined
  signalling route (ISUP/SS7) between them. The MSCs must also be
  configured to accept and process Handover Required and Handover
  Request messages.

- **BSC/RNC:** The BSC/RNCs must be configured with a list of
  neighbouring cells and the MSCs that serve them.

14. CS Inter VLR Location Update (subscriber moves from VLR 1 to VLR 2)

<img src="media/media/image14.png" style="width:6.3in;height:3.73819in"
alt="A screenshot of a computer AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| MAP LU procedures enabled, HLR updates subscriber location | MS, Old VLR/MSC, New VLR/MSC, HLR |

- **HLR/HSS:** The HLR must be configured to maintain a record of the
  serving VLR's address.

- **VLR:** The VLRs must be configured with SS7 links to the HLR and
  other VLRs to exchange location update and cancellation messages.

- **MS/UE:** The mobile device must be configured to detect a change in
  the Location Area Identity (LAI) and initiate a new Location Update
  procedure.

15. CS Mobile Originated Short Message Service

<img src="media/media/image15.png"
style="width:6.18782in;height:0.81254in"
alt="A close up of a computer screen AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| SMSC routing configured in MSC, MO-SMS subscription active in HLR | MS, MSC/VLR, SMSC, HLR |

- **VLR/MSC:** Must have a signaling route to the SMSC.

- **HLR/HSS:** The subscriber's profile must include the address of
  their home SMSC.

- **SMSC:** The SMSC must be configured to receive and store messages
  and forward them to their destination.

16. CS Mobile Terminated Short Message Service

<img src="media/media/image16.png"
style="width:5.93781in;height:0.96533in"
alt="A close-up of a map AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| MT-SMS subscription active, SMSC delivery to MSC configured | MS, SMSC, MSC/VLR, HLR |

- **SMSC:** The SMSC must be configured with a signaling route to the
  HLR to query the subscriber's serving VLR.

- **HLR/HSS:** Must be able to provide the serving VLR address to the
  SMSC in response to a Send Routing Info for SM (SRI-SM) query.

17. CS Subscriber Controlled Input

<img src="media/media/image17.png"
style="width:4.88219in;height:0.48614in"
alt="A close up of text AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| USSD service provisioned in HLR, USSD gateway or IN node configured | MS, MSC/VLR, HLR, SCP/IN |

**MSC:** The MSC's digit analysis must be configured to recognize
specific USSD codes (e.g., \*#100#) and route them to the relevant
application server or gateway.

18. CS Authentication

<img src="media/media/image18.png"
style="width:5.36139in;height:0.6042in"
alt="A black text on a white background AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| Authentication vectors in AuC, IMSI/Ki provisioned, RAND/SRES exchange enabled | MS, MSC/VLR, HLR, AuC |

- **AuC:** The Authentication Center (AuC) is co-located with or
  securely linked to the HLR. It is the repository for the subscriber's
  secret authentication key (Ki) and the algorithm for generating
  authentication triplets (RAND, SRES, Kc).

- **VLR:** The VLR is configured to request authentication triplets from
  the HLR/AuC and perform the authentication challenge with the mobile
  station.

19. CS IMEI Check

<img src="media/media/image19.png"
style="width:4.22938in;height:0.4653in"
alt="A white background with black and white clouds AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| IMEI database in EIR configured, MSC query to EIR enabled | MS, MSC/VLR, EIR |

- **MSC:** The MSC must have a signaling route to the Equipment Identity
  Register (EIR).

- **EIR:** The EIR database must contain the white list, black list, and
  grey list of IMEIs. The MSC sends a query to the EIR to check the
  status of the mobile device's IMEI.

20. CS Mobile Mobile Call with Call Completion to Busy Subscriber

<img src="media/media/image20.png"
style="width:5.19471in;height:3.98632in"
alt="A diagram of a computer AI-generated content may be incorrect." />

| **Key Configurations** | **Required Network Elements** |
|----|----|
| CCBS service active in HLR, MSC supports CCBS signaling | Calling MS, Called MS, MSC/VLR, HLR |

- **HLR/HSS:** Both the originating and terminating subscribers must
  have the CCBS supplementary service provisioned in their HLR profiles.

- **MSC:** The MSCs must be configured to support the CCBS signaling
  procedures, including setting timers to monitor when a busy subscriber
  becomes idle and initiating the recall procedure.
