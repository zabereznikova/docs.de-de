---
title: Navigationseigenschaft – ADO.NET
ms.date: 03/30/2017
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
ms.openlocfilehash: b57ecf9329aa9ea8afc07507613c9e3961bfd0a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772263"
---
# <a name="navigation-property"></a>Navigationseigenschaft

Ein *Navigationseigenschaft* ist eine optionale Eigenschaft auf eine [Entitätstyp](entity-type.md) ermöglicht, die die Navigation von einer [End](association-end.md) von einer [Zuordnung](association-type.md) auf das andere Ende. Im Gegensatz zu anderen [Eigenschaften](property.md), Navigationseigenschaften werden keine Daten enthalten.

Die Definition einer Navigationseigenschaft enthält Folgendes:

- Einen Namen. (erforderlich)

- Die Zuordnung, in der sie navigiert. (erforderlich)

- Die Enden der Zuordnung, in der sie navigiert. (erforderlich)

Beachten Sie, dass Navigationseigenschaften für beide Entitätstypen an den Enden einer Zuordnung optional sind. Wenn Sie für einen Entitätstyp am Ende einer Zuordnung eine Navigationseigenschaft definieren, muss keine Navigationseigenschaft für den Entitätstyp am anderen Ende der Zuordnung definiert werden.

Der Datentyp einer Navigationseigenschaft richtet sich nach der [Multiplizität](association-end-multiplicity.md) von dessen Remote [Zuordnungsende](association-end.md). Angenommen, eine Navigationseigenschaft, `OrdersNavProp`, ist für einen `Customer`-Entitätstyp vorhanden und navigiert eine 1:n-Zuordnung zwischen `Customer` und `Order`. Da das remotezuordnungsende für die Navigationseigenschaft eine Multiplizität von vielen aufweist (\*), der Datentyp ist eine Sammlung (der `Order`). Ist eine Navigationseigenschaft, `CustomerNavProp`, für den `Order`-Entitätstyp vorhanden, wäre sein Datentyp dementsprechend `Customer`, da die Multiplizität des Remoteendes "eins" (1) beträgt.

## <a name="example"></a>Beispiel

Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`. Die Navigationseigenschaften `Publisher` und `Authors` werden für den Book-Entitätstyp definiert. Die Navigationseigenschaft `Books` wird sowohl für den Publisher-Entitätstyp als auch den `Author`-Entitätstyp definiert.

 ![Das Diagramm zeigt ein konzeptionelles Modell mit drei Entitätstypen.](./media/navigation-property/conceptual-model-entity-types-associations.gif)  

Die [ADO.NET Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](./ef/language-reference/csdl-specification.md)), konzeptionelle Modelle zu definieren. Die folgende CSDL definiert den in der Abbildung oben gezeigten `Book`-Entitätstyp:

[!code-xml[EDM_Example_Model#EntityExample](~/samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]

Beachten Sie, dass XML-Attribute verwendet werden, um die erforderlichen Informationen zum Definieren einer Navigationseigenschaft zu kommunizieren: Das Attribut `Name` enthält den Namen der Eigenschaft, die `Relationship` enthält den Namen der sie navigiert, Zuordnung und `FromRole` und `ToRole` enthalten die Enden der Zuordnung.

## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
- [Beziehungen, Navigationseigenschaften und Fremdschlüssel](/ef/ef6/fundamentals/relationships)
