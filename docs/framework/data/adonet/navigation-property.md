---
title: Navigationseigenschaft
ms.date: 03/30/2017
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
ms.openlocfilehash: b6c286e63322a66be0407c864295a20685df2b7f
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980157"
---
# <a name="navigation-property"></a>Navigationseigenschaft

Eine *Navigations Eigenschaft* ist eine optionale Eigenschaft für einen [Entitätstyp](entity-type.md) , der die Navigation von einem [Ende](association-end.md) einer [Zuordnung zum anderen](association-type.md) Ende ermöglicht. Im Gegensatz zu anderen [Eigenschaften](property.md)werden von Navigations Eigenschaften keine Daten übertragen.

Die Definition einer Navigationseigenschaft enthält Folgendes:

- Einen Namen. (erforderlich)

- Die Zuordnung, in der sie navigiert. (erforderlich)

- Die Enden der Zuordnung, in der sie navigiert. (erforderlich)

Beachten Sie, dass Navigationseigenschaften für beide Entitätstypen an den Enden einer Zuordnung optional sind. Wenn Sie für einen Entitätstyp am Ende einer Zuordnung eine Navigationseigenschaft definieren, muss keine Navigationseigenschaft für den Entitätstyp am anderen Ende der Zuordnung definiert werden.

Der Datentyp einer Navigations Eigenschaft wird von der Multiplizität [des Remote](association-end-multiplicity.md) Zuordnungs [Endes](association-end.md)bestimmt. Angenommen, eine Navigationseigenschaft, `OrdersNavProp`, ist für einen `Customer`-Entitätstyp vorhanden und navigiert eine 1:n-Zuordnung zwischen `Customer` und `Order`. Da das Remote Zuordnungs Ende für die Navigations Eigenschaft eine Multiplizität von vielen (\*) aufweist, ist sein Datentyp eine Auflistung (of `Order`). Ist eine Navigationseigenschaft, `CustomerNavProp`, für den `Order`-Entitätstyp vorhanden, wäre sein Datentyp dementsprechend `Customer`, da die Multiplizität des Remoteendes "eins" (1) beträgt.

## <a name="example"></a>Beispiel

Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`. Die Navigationseigenschaften `Publisher` und `Authors` werden für den Book-Entitätstyp definiert. Die Navigationseigenschaft `Books` wird sowohl für den Publisher-Entitätstyp als auch den `Author`-Entitätstyp definiert.

 ![Das Diagramm zeigt ein konzeptionelles Modell mit drei Entitäts Typen.](./media/navigation-property/conceptual-model-entity-types-associations.gif)  

Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert den in der Abbildung oben gezeigten `Book`-Entitätstyp:

[!code-xml[EDM_Example_Model#EntityExample](~/samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]

Beachten Sie, dass XML-Attribute verwendet werden, um die zum Definieren einer Navigationseigenschaft erforderlichen Informationen zu übermitteln: Das Attribut `Name` enthält den Namen der Eigenschaft, `Relationship` enthält den Namen der Zuordnung, in der sie navigiert, und `FromRole` sowie `ToRole` enthalten die Enden der Zuordnung.

## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
- [Beziehungen, Navigations Eigenschaften und Fremdschlüssel](/ef/ef6/fundamentals/relationships)
