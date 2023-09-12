## Uniform Reasoner Interface
{:#interface}

The second challenge mentioned in [](#reasoning) is that no single use case is the same.
Some reasoning steps may be computationally intensive, while others are not, but need to be done fast without many dependencies.
Therefore, we should be able to dynamically change how we execute the reasoning without a lot of work, based on the exact use case at that moment.
A *uniform reasoner interface* is designed to abstract away the differences between the different reasoners, allowing one to easily switch between them.
This can mean switching between reasoning in the browser or remotely, or between reasoner implementations to improve performance.

First, the `data` and `query` parameters are needed.
The `data` parameter is used to pass the data to the reasoner together with any inference rules that should be applied.
The `query` parameter is optional and defines the pattern of the data that should be returned by the reasoner.
Furthermore, the interface is designed with extensibility in mind by using a single object that contains all the additional options.

The proposed interface is implemented in the client-side [EYE-JS](cite:cites eye-js) reasoner package.
Furthermore, an [`eye-mock` library](cite:cites eye-mock) is implemented with the same interface allowing one to execute the reasoning on a remote server.
Finally, a Reasoner app implementation demonstrates the use of the interface by allowing one to easily switch between the different reasoners.
