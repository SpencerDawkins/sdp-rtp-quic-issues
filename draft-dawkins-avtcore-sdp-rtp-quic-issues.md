---
title: SDP Offer/Answer for RTP using QUIC as Transport - Design Issues
abbrev: SDP O/A for RTP over QUIC Issues
docname: draft-dawkins-avtcore-sdp-rtp-quic-issues-latest
date:
stream: IETF
category: info

ipr: trust200902
area: applications
workgroup: AVTCORE Working Group
keyword: Internet-Draft QUIC RTP SDP

stand_alone: yes
pi: [toc, sortrefs, symrefs]

author:
 -
  ins: S. Dawkins
  name: Spencer Dawkins
  organization: Tencent America LLC
  country: United States of America
  email: spencerdawkins.ietf@gmail.com

normative:
  I-D.engelbart-rtp-over-quic:

informative:

  I-D.dawkins-avtcore-sdp-rtp-quic:

  RFC3264:
  RFC3711:
  RFC3550:
  RFC7667:
  RFC8866:
  RFC9000:

  SDP-parameters:
    target: https://www.iana.org/assignments/sdp-parameters/sdp-parameters.xhtml#sdp-parameters-2
    title: "SDP Parameters - Proto"
    date: September 2021

--- abstract

This document is intended to capture SDP aspects of RTP over QUIC design issues that have arisen, been discussed by the AVTCORE working group, and have reached a resolution that can be included in "SDP Offer/Answer for RTP using QUIC as Transport".

This document is a companion document to "SDP Offer/Answer for RTP using QUIC as Transport". That document focuses on the description and registration of SDP "proto" attribute parameters with IANA, to allow applications that rely on SDP Offer/Answer to negotiate the QUIC protocol as an encapsulation for RTP.

"SDP Offer/Answer for RTP using QUIC as Transport" is itself a companion document to "RTP over QUIC", and follows the lead of the latter specification as it evolves.

--- middle

# Introduction {#intro}

This document is intended to capture SDP ({{RFC8866}}) aspects of RTP ({{RFC3550}}) over QUIC ({{RFC9000}}) design issues that have arisen, been discussed by one or more IETF working groups, and have reached a resolution that can be included in "SDP Offer/Answer for RTP using QUIC as Transport" {{I-D.dawkins-avtcore-sdp-rtp-quic}}.

This document is a companion document to "SDP Offer/Answer for RTP using QUIC as Transport" ({{I-D.dawkins-avtcore-sdp-rtp-quic}}). That document focuses on the description and registration of SDP ({{RFC8866}}) "proto" attribute parameters with IANA ({{SDP-parameters}}), to allow applications that rely on SDP Offer/Answer ({{RFC3264}}) to negotiate the QUIC protocol({{RFC9000}}) as an encapsulation for RTP ({{RFC3550}}).

"SDP Offer/Answer for RTP using QUIC as Transport" ({{I-D.dawkins-avtcore-sdp-rtp-quic}}) is itself a companion document to "RTP over QUIC" ({{I-D.engelbart-rtp-over-quic}}), and follows the lead of follows the lead of the latter specification as it evolves.

## Notes for Readers {#readernotes}

(Note to RFC Editor - if this document ever reaches you, please remove this section)

This document is intended to stimulate discussion about how proponents of "RTP over QUIC" expect that to work, recognizing that not everyone has the same goals in mind, but it understanding what the choices are will likely be helpful in making those choices, especially when the results of a choice provide direction that will allow implementers to agree on strategies and reuse as much code as possible.

The author learned through some experience that it would be really good to collect questions and design issues about "RTP over QUIC", or even "Media Over QUIC", in one place, because trying to track what was being discussed in multiple and partially overlapping venues was a recipe for brain damange, especially when a topic would come up under the "Media Over QUIC" banner, and then seem to be useful for "RTP over QUIC", so potentially signaled in SDP.

This document is intended to keep at least one person sane. If it keeps more than one person sane, I've made the world a slightly better place.

## Relationship with other documents

Design issues relevant for {{I-D.dawkins-avtcore-sdp-rtp-quic}} may arise in a variety of venues. At this time, AVTCORE is actively considering adoption of "RTP over QUIC" ({{I-D.engelbart-rtp-over-quic}}), so this document will reflect those issues, but protocol specifications adopted by any other IETF working group relying on RTP-over-QUIC connections that are established using SDP would also be a candidate to be tracked.

{{I-D.dawkins-avtcore-sdp-rtp-quic}} will reflect answers  to the questions contained in this document, but the discussion material in this document would not be appropriate for inclusion in a draft that focuses on SDP description and IANA registration. This document might be worth publishing on its own, but is primarily intended to guide discussion that will feed into {{I-D.dawkins-avtcore-sdp-rtp-quic}}.

## Discussion and Contribution Venues for this draft. {#contrib}

(Note to RFC Editor - if this document ever reaches you, something has gone terribly wrong. Please notify your local IESG for guidance)

With the concurrence of the AVTCORE and MMUSIC working group co-chairs, SDP aspects of RTP over QUIC protoposals should be discussed in the AVTCORE working group, in the same venue where RTP over QUIC proposals are being discussed. When proposals for RTP over SIP have stablized in AVTCORE, this document will be sent to the MMUSIC working group for review by SDP experts, but SDP-specific comments are welcomed at any time.

Readers are invited to open issues and send pull requests with contributed text for this document in the GitHub repository at https://github.com/SpencerDawkins/sdp-rtp-quic-issues. The direct link to the list of issues is https://github.com/SpencerDawkins/sdp-rtp-quic-issues/issues.

# Design Issues Resolutions Ready to be Reflected in {{I-D.dawkins-avtcore-sdp-rtp-quic}} {#issue-resolved}

## What AVP Profiles to Register

This design issue was surprisingly difficult to resolve at first. The first design choice was between

* Registering "insecure" AVP profiles, such as "QUIC/RTP/AVPF", because "secure AVP profiles, such as "QUIC/RTP/SAVPF", mean that the RTP payloads are encrypted using "Secure Real-time Transport Protocol (SRTP)" ({{RFC3711}}), which isn't necessary because RTP over QUIC payloads will already be encrypted by QUIC, and
* Also registering "secure" AVP profiles, such as "QUIC/RTP/SAVPF", for various reasons, including
    * allowing "double encryption", using both SRTP and QUIC to encrypt the RTP payload
    * giving RTP middleboxes ({{RFC7667}}) a hint, whether to forward RTP over QUIC packets to non-RTP over QUIC endpoints using SRTP



# Design Issue Resolutions Under Discussion in IETF Working Groups {#under-discuss}

# Design Issue "Parking Lot", for Design Issues That Have Not Been Discussed {#parking-lot}



# IANA Considerations

This document makes no requests of IANA.

# Security Considerations

This document is intended as the basis for discussion about protocol mechanisms that will be described in other documents. As a discussion paper, this document introduces no new security considerations, and any new security considerations resulting from those discussions should be included in the documents that actually describe protocol mechanisms.

# Acknowledgments

(Your name also could appear here. You are invited to comment and contribute, as described in "Contribution and Discussion Venues for this draft" above)
