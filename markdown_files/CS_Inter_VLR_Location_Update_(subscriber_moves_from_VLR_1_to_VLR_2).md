<img src="images/CS_Inter_VLR_Location_Update_(subscriber_moves_from_VLR_1_to_VLR 2).png" style="width:6.64167in;height:4.05in"
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
