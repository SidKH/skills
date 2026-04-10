# Sneaking

- Link: https://www.deceptive.design/types/sneaking

## Definition

Quietly introduce an extra item, cost, or consequence into a transaction so the user proceeds under a mistaken understanding of what they are accepting.

## Audit Cues

- cart or checkout logic that adds optional products or fees without an explicit opt-in
- terms, charges, or side effects disclosed late or outside the main action path
- hidden defaults that alter the transaction unless the user removes them
- code paths that mutate the cart or agreement set automatically
- copy that describes the primary purchase while leaving the secondary consequence obscure

## Generic Example

During checkout, an optional add-on is inserted into the cart automatically, and the user must notice and remove it to avoid being charged.
