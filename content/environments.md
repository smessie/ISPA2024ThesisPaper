## Multiple Viewing Environments
{:#environments}

<figure id="fig:eaen-FormRenderer">
<img src="img/FormRenderer.png" alt="[Screenshot of FormRenderer application]" />
<figcaption markdown="block">
Screenshot of the implemented FormRenderer.
</figcaption>
</figure>

The form description will provide the decoupling of the three parts: display, validation, and reasoning.
The display part is the part that is responsible for rendering the form to the user.
There already exist ontologies that can be used for this purpose, such as [SHACL](cite:cites shacl), [Solid-UI](cite:cites solid-ui), and [RDF-Form](cite:cites rdf-form).

By declaratively describing the form in RDF, it should be possible to render the form in any environment.
Web forms are typically HTML, while RDF represents the semantics of the form, not how you represent it in HTML.
To prove that the display part is unrelated to the viewing environment, two proof-of-concept applications are implemented that can render the same form description in multiple viewing environments.
The first app is the *FormRenderer* which renders the form description in a web browser using HTML.
A screenshot of this app is shown in [](#fig:eaen-FormRenderer).
The second app is the *FormCli* which renders the form description in a text-based command-line interface.
The architecture and implementation of these apps are very similar to each other.
The main difference is that the FormCli app does not have a graphical user interface and uses a text-based terminal instead.

The implementation of these apps provides us with proof that the display part is unrelated to the viewing environment as the same form description can be rendered with the two apps.
Everything about how to render the form can be derived from the RDF form description, making it declarative.
By making form descriptions portable and not tight to one rendering environment or one rendering logic, machines can be controlled to create forms for producing RDF in multiple viewing environments.