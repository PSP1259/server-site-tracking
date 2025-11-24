# 02_server-side Test Cases

## Purpose
Execute identical flows as in the client side baseline to ensure fair comparison.

The following test cases are repeated without modification.

---

| Test ID | User Flow | Expected Events |
|---------|-----------|-----------------|
| T01 | Open product page | view_item |
| T02 | Add item to cart | add_to_cart |
| T03 | Start checkout | begin_checkout |
| T04 | Complete example purchase | purchase |
| T05 | Click primary CTA | cta_click |
| T06 | Header navigation click | navigation_click |
| T07 | Form submission | form_submit |

---

## Validation Targets
For each test run, verify:

1. Event appears in analytics destination via server transport  
2. Event count equals baseline under unrestricted browsers  
3. Parameter completeness equals baseline  
4. Delivery latency is recorded  
5. Deduplication works if client and server both send data
