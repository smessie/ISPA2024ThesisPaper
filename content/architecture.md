## High-Level Architecture
{:#architecture}

<figure id="fig:eaen-currently-to-goal">
<img src="img/currently-to-goal.png" alt="[Figure of shift from single structure to a three-part view]" />
<figcaption markdown="block">
Transition from the traditional single structure where all the data is defined using a single vocabulary, to a three-part view, consisting of a form (for display), shape (for validation), and footprint (for reasoning) part.
</figcaption>
</figure>

A common way how web applications store their data is by using only one fixed structure.
Because of that, it is not possible to use the data with another application that uses a different structure.
This is even the case for many Solid apps that assume the data is stored in a fixed location in the pod with only one vocabulary.
This paper proposes a solution to this problem by using a three-part view on Solid web forms.
This shift from a single structure to a three-part view is shown schematically in [](#fig:eaen-currently-to-goal).
The left part is the current situation where the data is stored in a single structure and the application is built on top of this structure.
The right part is the goal of this research where the data is divided into three parts: a form (for display), shape (for validation), and footprint (for reasoning) part.

The high-level architecture can also be viewed from a different angle.
In traditional centralized web applications, different users interact with the same centralized web server using different interfaces.
These web interfaces are written for that server and only work for that single web server.
Additionally, the data is stored on the server of the application, outside the user's control.
The [Solid protocol](cite:cites solid-protocol) provides a standardized interface, but still many apps are being built with assumptions about the data that is stored in the pod.
The app is designed for one specific use case and the data is most of the time stored in a specific way.

<figure id="fig:eaen-stage-2">
<img src="img/stage-2.svg" alt="[Figure of high level architecture of declarative Solid apps]" />
<figcaption markdown="block">
Users interact with a dynamically generated app built by a form renderer using the 3 inputs displayed on the right.
This generic renderer app can build for multiple viewing environments without making assumptions about the interface and app itself.
It uses a reasoner to apply the schema alignment and footprint tasks.
The user can use the generated app to interact with one or more Solid pods.
</figcaption>
</figure>

This paper pushes this decentralized architecture a step further with the introduction of a declarative Solid app that makes no assumptions about the interface and app itself.
The previous problem of needing a separate app for each use case is solved by describing the user interface in a declarative way: the *form description resource*.
A schematic overview of the architecture is shown in [](#fig:eaen-stage-2).
The app still needs to understand the ontology of the form description.
This problem is overcome with the use of *schema alignment tasks* translating it into an ontology the app understands.
The third input as shown in [](#fig:eaen-stage-2), the *N3 conversion rules resource*, is used by the renderer app to perform this mapping.
Data stored in the provided *data resource* can be used to prefill the form.
Next, reasoning is also used to apply *footprint tasks*: the execution of policies when a certain action occurs, such as submission.
A remote or local reasoner can be used to perform these tasks.
Lastly, no assumptions should be made about the app itself or the interface used to interact with this app.
This declaratively generated app built by the renderer app can then be used to interact with one or more Solid pods.
This concept of having a display part that is unrelated to the viewing environment is discussed in [](#environments).
