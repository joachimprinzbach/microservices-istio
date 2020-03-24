# microservices-istio

Use case for a MircoService REST API with a [client](./pizza-inventory/pizza-inventory-api/src/main/java/io/joachimprinzbach/pizzainventory/api/PizzaInventoryClient.java) that can be consumed by a [consumer application](./pizza-order/src/main/java/io/joachimprinzbach/pizzaorder/PizzaOrderRestController.java).

## Modules

### Pizza-Order
The "WebAppliation" that provides a [Frontend](https://joachim-pizza-order-test.apps.origin.baloise.dev/) and a Backend for the Frontend with a REST API.

The [REST-API]([client](./pizza-order/src/main/java/io/joachimprinzbach/pizzaorder/PizzaOrderRestController.java)) gets its data from a microservice called `pizza-inventory`. 


### Pizza-Inventory
The MicroService provides a simple [REST-API](./pizza-inventory/pizza-inventory-impl/src/main/java/io/joachimprinzbach/pizzainventory/PizzaInventoryRestController.java).

Besides the API, a [Client Stub](./pizza-inventory/pizza-inventory-api/src/main/java/io/joachimprinzbach/pizzainventory/api/PizzaInventoryClient.java) and a [DTO](./pizza-inventory/pizza-inventory-api/src/main/java/io/joachimprinzbach/pizzainventory/api/PizzaInventoryItemDto.java) is provided as jar File that can be used by consumers.

he service environment is derived from the current env of the consumer, but can be overriden by setting a property.  