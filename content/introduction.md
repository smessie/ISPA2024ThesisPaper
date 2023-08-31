## Introduction
{:#introduction}

Current web forms are meant to be used against one endpoint (1), often used for one (web) display (2), with one particular workflow in mind (3), without a means to send and receive the data in another way (4).
We all use a kind of web form once in a while, that is because you take part in a survey, or maybe because you have to fill in some kind of request. 
When one need a similar form to one that already exists, they will have to develop a new application from scratch, without the possibility to start from that existing one and adapt it to their needs.
Furthermore, the data will almost always be stored on the server of the service provider, and the user will not be able to access it again or choose to store it somewhere else (footprint).

To tackle this problem, this thesis introduces a solution by looking at Solid web forms as a whole of 3 separate parts: *display*, *validation*, and *reasoning*.
With the use of [Solid](cite:cites solid) and Linked Data, several solutions have already been proposed, but none of them consider web forms as a whole of 3 separate parts, except for the [Design Issue by Berners-Lee](cite:cites berners-lee_linked_2019) and the [blog post on *Shaping Linked Data apps* by Verborgh](cite:cites shapes).
In addition, to fully decouple the description from the application, schema alignment is required to map the description to the vocabulary of the application.
This makes it possible to use the same description for different applications, even if they use different vocabularies.
This, along with the execution of the footprint tasks, is done using reasoning.

Therefore, we propose an architecture that splits the Solid web forms into 3 parts and implement proof-of-concept applications to show how this can be done in practice.
In this paper, the following three research questions are examined:

- How can machines be controlled in a declarative way to create forms for producing RDF in **multiple viewing environments** (such as the web and text-based via a command line)?

- How can machines be controlled in a declarative way to perform **schema alignment and footprint tasks** by the use of reasoning?

- How can an **abstraction** be made to **run reasoning** in the browser or remotely?

In [](#architecture), the high-level architecture of the proposed three-part view is discussed after which each research question is answered in [](#environments), [](#reasoning), and [](#interface).
Next, an evaluation is done with the help of a user-experience evaluation in [](#evaluation).
Finally, in [](#conclusion), the conclusion is given.
