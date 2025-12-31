---
title: Flow
---
flowchart LR

&nbsp;&nbsp;subgraph Sales\["Sales"\]

&nbsp;&nbsp;&nbsp;&nbsp;OM01\["OM-01 Receive quote request"\]

&nbsp;&nbsp;&nbsp;&nbsp;OM02\["OM-02 Build price & lead time"\]

&nbsp;&nbsp;&nbsp;&nbsp;OM03\["OM-03 Send quote + internal visibility trigger"\]

&nbsp;&nbsp;&nbsp;&nbsp;OM04\["OM-04 Quote logging & master data updates"\]

&nbsp;&nbsp;&nbsp;&nbsp;OM05\["OM-05 Order entry + print Yellow/Pink"\]

&nbsp;&nbsp;&nbsp;&nbsp;OM07{"OM-07 Stock vs produce?"}

&nbsp;&nbsp;&nbsp;&nbsp;OM08\["OM-08 Material check / PO / job release / print pages"\]

&nbsp;&nbsp;end

&nbsp;&nbsp;subgraph Office\["Office"\]

&nbsp;&nbsp;&nbsp;&nbsp;OM06\["OM-06 Order check / contract review"\]

&nbsp;&nbsp;&nbsp;&nbsp;OM09\["OM-09 Assemble job packet"\]

&nbsp;&nbsp;&nbsp;&nbsp;OM14\["OM-14 Enter labor in Syteline"\]

&nbsp;&nbsp;&nbsp;&nbsp;OM23\["OM-23 Production close out"\]

&nbsp;&nbsp;end

&nbsp;&nbsp;subgraph Engineering\["Engineering"\]

&nbsp;&nbsp;&nbsp;&nbsp;OM10\["OM-10 Review job packet (routing/drawing updates)"\]

&nbsp;&nbsp;&nbsp;&nbsp;OM21\["OM-21 Cert package"\]

&nbsp;&nbsp;end

&nbsp;&nbsp;subgraph Production\["Production"\]

&nbsp;&nbsp;&nbsp;&nbsp;OM11\["OM-11 Dispatch / schedule first operation"\]

&nbsp;&nbsp;&nbsp;&nbsp;OM12\["OM-12 Manufacturing operations"\]

&nbsp;&nbsp;&nbsp;&nbsp;OM13\["OM-13 Operator labor tickets"\]

&nbsp;&nbsp;end

&nbsp;&nbsp;subgraph Quality\["Quality"\]

&nbsp;&nbsp;&nbsp;&nbsp;OM18\["OM-18 Inspection report retrieve/create"\]

&nbsp;&nbsp;&nbsp;&nbsp;OM19\["OM-19 Inspection execution"\]

&nbsp;&nbsp;end

&nbsp;&nbsp;subgraph Shipping\["Shipping"\]

&nbsp;&nbsp;&nbsp;&nbsp;OM20\["OM-20 Fulfill & ship"\]

&nbsp;&nbsp;end

&nbsp;&nbsp;subgraph Finance\["Finance"\]

&nbsp;&nbsp;&nbsp;&nbsp;OM22\["OM-22 Invoice"\]

&nbsp;&nbsp;end

&nbsp;&nbsp;OM01 --> OM02 --> OM03 --> OM04 --> OM05 --> OM06 --> OM07

&nbsp;&nbsp;OM07 -- "stock" --> OM20

&nbsp;&nbsp;OM07 -- "produce" --> OM08 --> OM09 --> OM10 --> OM11 --> OM12 --> OM13 --> OM14

&nbsp;&nbsp;OM12 --> OM18 --> OM19 --> OM20

&nbsp;&nbsp;OM20 --> OM21 --> OM22

&nbsp;&nbsp;OM14 --> OM23

&nbsp;&nbsp;OM20 --> OM23

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBVGl0YW4tT3JkZXItTWFwJTNBJTNBZWxpYndoaXR0bGU=" repo-name="Titan-Order-Map"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
