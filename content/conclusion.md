## Conclusion
{:#conclusion}

This paper demonstrates a three-part view on Solid web forms.
Our first 2 contributions, the implementations of the FormRenderer and FormCli prove that the display part is not tight to one rendering environment.
With our third contribution, the FormGenerator, we show how such declarative form descriptions can be produced, answering the first research question.
The user evaluation made clear the SHACL ontology is not ideal for the display part.
It is now empirically shown that the Solid-UI ontology is more natural for the display part.

Furthermore, with our fourth contribution, schema alignment and footprint tasks were successfully introduced allowing one to use different vocabularies than the app understands and allowing one to execute declaratively defined policies on the occurrence of events.
This successfully answers the second research question.
Nonetheless, the results of these applications show the need for further research to further improve the perceived accessibility issues regarding bindings in order to make these technologies optimally available to all people without expecting them to have prior technical knowledge.
After all, the user evaluation showed that the FormGenerator and FormRenderer apps are for different types of people.
Future research on how bindings could be automatically suggested to the user could be a solution to this problem.
Additionally, a standardized way of defining policies would be interesting for future work.

Finally, our fifth contribution, the uniform reasoner interface, was introduced to allow one to easily switch between different reasoning implementations.
With our sixth contribution, the implementation of the Reasoner app, we show how this abstraction can be used to run reasoning in the browser or remotely, answering the third and final research question.
As future work, it would be interesting to see this interface implemented in other reasoning libraries, especially in a library that implements a different algorithm than the EYE reasoner.
An HTTP server version of this interface with the same parameters would also be interesting for future work.
