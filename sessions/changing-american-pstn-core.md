# The changing American PSTN core

https://www.socallinuxexpo.org/scale/23x/presentations/changing-american-pstn-core

- **Date**: Thursday, March 5, 2026
- **Time**: 10:45 - 11:30
- **Location**: Room 106
- **Speaker(s)**: Alex Balashov, Principal Consultant at Evariste Systems

> Balashov examines the transformation of the US Public Switched Telephone Network's core infrastructure. He notes that "the much-vaunted move to IP peering in the core of the PSTN itself has finally happened" after years of skepticism, fundamentally reshaping how telecommunications networks operate. The presentation updates outdated mental models of the PSTN by addressing major changes in ILEC tandems, modern authentication standards like STIR/SHAKEN, and SIP peering arrangements with carriers.

## Overview

## Key Points

- Speaker is on the operator side of things
- Thought SIP wouldn't take off at first, until 2007-2008 📈
- AT&T breakup 1982-1984
- LATAs: Local Access and Transport Areas
- Tandems connect between LATAs, can have multiple Tandems per LATA
- Telecommunications act 1996
  - Required LATAs to open traffic for interconnection
  - Number portability
  - Broadband competition
- CLECs (Competitive Local Exchange Carrier) became VoIP backbone
- Lots of dial-ups connecting straight to Level 3
- ILEC (Incumbent Local Exchange Carrier) tandem became default for inter-LATA calls
- More E2E IP world instead of ILEC tandem in 2026

## Questions
- STIR/SHAKEN problems, spoofing
  - Complicated, things going through traditional networks makes harder to fix
  - Smaller companies could charge more, led to conference calling traffic pumping
  - STIR/SHAKEN has not delivered, technically, related to implementation-specific details
