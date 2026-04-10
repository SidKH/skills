# Fake Scarcity

- Link: https://www.deceptive.design/types/fake-scarcity

## Definition

Create artificial pressure by implying that stock, seats, or availability are limited when the limitation is misleading, fabricated, or not grounded in real inventory.

## Audit Cues

- hard-coded low-stock messages with no real inventory dependency
- randomized or manually configurable inventory counters
- templates like `Only X left` without trustworthy stock data inputs
- demand or stock widgets powered by arbitrary constants, timers, or mock generators
- admin settings that let operators display scarcity cues independently of real availability

## Generic Example

A product page shows `Only 3 left`, but the code reveals that the number is drawn from a configurable marketing widget rather than the inventory system.
