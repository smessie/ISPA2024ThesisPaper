## Conclusion
{:#conclusion}

This paper demonstrates a three-part view on Solid web forms.
Our first 2 contributions, the implementations of the FormRenderer and FormCli prove that the display part is not tight to one rendering environment.
With our third contribution, the FormGenerator, we show how such declarative form descriptions can be produced, answering RQ1.
The user evaluation made clear the SHACL ontology is not ideal for the display part.
It is now empirically shown that the Solid-UI ontology is more natural for the display part.

Furthermore, with our fourth contribution, schema alignment and footprint tasks were successfully introduced allowing one to use different vocabularies than the app understands and allowing one to execute declaratively defined policies on the occurrence of events.
This successfully answers RQ2.
Future research on how bindings could be automatically suggested to the user and a standardized way of defining policies would be interesting.

Finally, our fifth contribution, the uniform reasoner interface, was introduced to allow one to easily switch between different reasoning implementations.
With our sixth contribution, the implementation of the Reasoner app, we show how this abstraction can be used to run reasoning in the browser or remotely, answering RQ3.
As future work, it would be interesting to see this interface implemented in other reasoning libraries or as an HTTP server version.
