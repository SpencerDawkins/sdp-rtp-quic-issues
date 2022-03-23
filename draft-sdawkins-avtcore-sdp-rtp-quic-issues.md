---
title: SDP Offer/Answer for RTP using QUIC as Transport - Design Issues
abbrev: SDP O/A for RTP over QUIC Issues 
docname: draft-dawkins-avtcore-sdp-rtp-quic-issues-latest
date:
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

informative:

  I-D.dawkins-avtcore-sdp-rtp-quic:
  I-D.dawkins-sdp-rtp-quic-questions:
  I-D.gruessing-moq-requirements:

--- abstract

This document is a companion document to "SDP Offer/Answer for RTP using QUIC as Transport". That document focuses on the description and registration of SDP "proto" attribute parameters with IANA, to allow applications that rely on SDP Offer/Answer to negotiate the QUIC protocol as an encapsulation for RTP.

The author learned through some experience that it would be really good to collect questions and issues about "RTP over QUIC", or even "Media Over QUIC", in one place, because trying to track what was being discussed in two different venues was a recipe for brain damange, especially when a topic would come up under the "Media Over QUIC" banner, and then seem to be useful for "RTP over QUIC", so potentially signaled in SDP. 

This document is intended to keep at least one person, and possibly more than one person, sane. 

--- middle

# Introduction {#intro}

This document is a companion document to "SDP Offer/Answer for RTP using QUIC as Transport" ({{I-D.dawkins-avtcore-sdp-rtp-quic}}). That document focuses on the description and registration of SDP ({{RFC8866}}) "proto" attribute parameters with IANA ({{SDP-parameters}}), to allow applications that rely on SDP Offer/Answer ({{RFC3264}}) to negotiate the QUIC protocol({{RFC9000}}) as an encapsulation for RTP ({{RFC3550}}).

The author learned through some experience that it would be really good to collect questions and issues about "RTP over QUIC", or even "Media Over QUIC", in one place, because trying to track what was being discussed in two different venues was a recipe for brain damange, especially when a topic would come up under the "Media Over QUIC" banner, and then seem to be useful for "RTP over QUIC", so potentially signaled in SDP.

This document is intended to keep at least one person, and possibly more than one person, sane. 

## Notes for Readers {#readernotes}

(Note to RFC Editor - if this document ever reaches you, please remove this section)

This document is intended to stimulate discussion about how proponents of "RTP over QUIC" expect that to work, recognizing that not everyone has the same goals in mind, but it understanding what the choices are will likely be helpful in making those choices, especially when the results of a choice provide direction that will allow implementers to agree on strategies and reuse as much code as possible.

## Relationship with other documents

{{I-D.dawkins-avtcore-sdp-rtp-quic}} will almost certainly reflect answers  to the questions contained in this document, but the discussion material in this document will not be appropriate for inclusion in a draft that focuses on SDP description and IANA registration. This document might be worth publishing on its own, but is primarily intended to guide discussion that will feed into {{I-D.dawkins-avtcore-sdp-rtp-quic}}.

{{I-D.dawkins-sdp-rtp-quic-questions}} will not be maintained, although issues and questions from that draft will appear here for reasons alluded to in {{intro}}.

## Contribution and Discussion Venues for this draft. {#contrib}

(Note to RFC Editor - if this document ever reaches you, something has gone terribly wrong. Please notify your local IESG for guidance)

With the concurrence of the AVTCORE and MMUSIC working group co-chairs, this document should be discussed in the AVTCORE working group, in the same venue where RTP over QUIC proposals are being discussed. When proposals for RTP over SIP have stablized in AVTCORE, this document will be sent to the MMUSIC working group for review by SDP experts, but SDP-specific comments are welcomed at any time.

Readers are also invited to open issues and send pull requests with contributed text for this document in the GitHub repository at https://github.com/SpencerDawkins/sdp-rtp-quic. The direct link to the list of issues is https://github.com/SpencerDawkins/sdp-rtp-quic/issues.

# Methodology {#methods}

Because a large percentage of active members of the "Media over QUIC" community are comfortable using Github, the author will be maintaining the issues in Github at https://github.com/SpencerDawkins/sdp-rtp-quic/issues, with pointers from this document (use the HTML version of this document for best results, of course). 

# IANA Considerations

This document makes no requests of IANA.

# Security Considerations

This document is intended as the basis for discussion about protocol mechanisms that will be described in other documents. As a discussion paper, this document introduces no new security considerations, and any new security considerations resulting from those discussions should be included in the documents that actually describe protocol mechanisms.

# Acknowledgments

(Your name also could appear here. You are invited to comment and contribute, as described in "Contribution and Discussion Venues for this draft" above)
