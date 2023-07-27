---
title: Design Decisions
author:  
---

## Implementing Inferfaces Early On

Implementing interfaces early in the development process was a beneficial strategic decision that allowed for more modularity and abstracion in our code organization. Interfaces also defined formal contracts, promoting collaboration among team members and enabled parallel development. This simplified testing, reduced coupling, and enhanced code flexibility for future changes. By adhering to interfaces, we achieved high level of achieve extensibility and reusability, while also provided effective documentation and facilitated efficient communication among our group members. Overall, this approach set a strong foundation for building scalable, maintainable, and agile approach to our project development this summer.

## Design Patterns Usage Examples

### Façade

* `Services.get(Class<T>)`

`Services.get(Class<T>)` is a **façade** for all our factory methods used to create our various logic layer services.

The method search for a suitable method defined within itself that returns something assignable to the requested interface, and which takes 0 parameters. It then calls this method to supply the service.

The `Services` class can be considered as a **facade design pattern** because it provides a simplified interface for accessing various logic manager objects in the application.

This simplifies the client code's interaction with the logic managers by hiding the complexity of object instantiation and configuration.The get() method uses reflection to dynamically locate and invoke the appropriate factory method for the requested manager class.

This approach allowed for flexibility and extensibility, as the get method will never need to change. Simply add a new factory method to have access to a new service.

### Adapter

* `InventoryLogisticsManager``

This class acts as a simple wrapper that adapts **`InventoryLogisticsDao`** to **`IInventoryLogisticsManager`** so that the UI was not dependent on anything in the Data Access Layer. It encapsulated the lower-level data access details and provided a higher-level interface for the logic layer to interact with.
