## Uniform Reasoner Interface
{:#interface}

The second challenge that was mentioned in [](#reasoning) is that no single use case is the same.
Some reasoning steps may be computationally intensive, while others are not, but need to be done fast without many dependencies.
This leads to the idea that we should be able to dynamically change how we execute the reasoning without a lot of work, based on the exact use case at that moment.
A *uniform reasoner interface* is designed to abstract away the differences between the different reasoners, allowing one to easily switch between them.
Switching between reasoners can mean switching between reasoning in the browser or remotely, or it can mean switching between reasoner implementations to improve performance.

First, the `data` and `query` parameters are needed.
The `data` parameter is used to pass the data to the reasoner together with any inference rules that should be applied.
The `query` parameter is optional and defines the pattern of the data that should be returned by the reasoner.
When passed as a string, the data should be formatted in the Notation3 syntax.
Furthermore, the interface is designed with extensibility in mind by using a single object that contains all the additional options.
This object can be extended by other reasoners, allowing them to add their options.
By default, the output type should be the same as the input type.
However, by passing the `outputType` option, the user can specify the output type.
This option must support at least the `string` value, it should also support the `quads` value, which will return the output as an array of RDF/JS Quads.
When the query parameter is left undefined, the user should have the option to execute implicit queries.
This is expressed in the options object by the `output` option by defining what to output with implicit queries.
Last, the option `blogic` can be defined to use blogic [](cite:cites hayes_blogic_2009), used to support RDF Surfaces [](cite:cites rdf-surfaces).

The proposed interface is implemented in the client-side [EYE-JS](cite:cites eye-js) reasoner package.
Furthermore, an [`eye-mock` library](cite:cites eye-mock) is implemented with the same interface allowing one to execute the reasoning on a remote server.
Finally, a Reasoner app is implemented to demonstrate the use of the interface and to allow one to easily switch between the different reasoners.
The user can use the toggle to switch easily between the two implementations to fit their needs.
Under the hood, this is done by just changing the import statement of the reasoner package.
