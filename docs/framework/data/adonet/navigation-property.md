---
title: Navigationseigenschaft
ms.date: 03/30/2017
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
ms.openlocfilehash: eaf22ad4dd24b4bf046f14ccabd435a9ecd1776f
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094383"
---
# <a name="navigation-property"></a>Navigationseigenschaft

Eine *Navigations Eigenschaft* ist eine optionale Eigenschaft für einen [Entitätstyp](entity-type.md) , der die Navigation von einem [Ende](association-end.md) einer [Zuordnung zum anderen](association-type.md) Ende ermöglicht. Im Gegensatz zu anderen [Eigenschaften](property.md)werden von Navigations Eigenschaften keine Daten übertragen.

Die Definition einer Navigationseigenschaft enthält Folgendes:

- Einen Namen (Erforderlich)

- Die Zuordnung, in der sie navigiert. (Erforderlich)

- Die Enden der Zuordnung, in der sie navigiert. (Erforderlich)

Navigations Eigenschaften sind bei beiden Entitäts Typen an den Enden einer Zuordnung optional. Wenn Sie für einen Entitätstyp am Ende einer Zuordnung eine Navigationseigenschaft definieren, muss keine Navigationseigenschaft für den Entitätstyp am anderen Ende der Zuordnung definiert werden.

Der Datentyp einer Navigations Eigenschaft wird von der Multiplizität [des Remote](association-end-multiplicity.md) Zuordnungs [Endes](association-end.md)bestimmt. Angenommen, eine Navigationseigenschaft, `OrdersNavProp`, ist für einen `Customer`-Entitätstyp vorhanden und navigiert eine 1:n-Zuordnung zwischen `Customer` und `Order`. Da das Remote Zuordnungs Ende für die Navigations Eigenschaft eine Multiplizität von vielen (\*) aufweist, ist sein Datentyp eine Auflistung (of `Order`). Ist eine Navigationseigenschaft, `CustomerNavProp`, für den `Order`-Entitätstyp vorhanden, wäre sein Datentyp dementsprechend `Customer`, da die Multiplizität des Remoteendes "eins" (1) beträgt.

## <a name="example"></a>Beispiel

Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`. Die Navigations Eigenschaften `Publisher` und `Authors` werden für den Book-Entitätstyp definiert. Die Navigationseigenschaft `Books` wird sowohl für den Publisher-Entitätstyp als auch den `Author`-Entitätstyp definiert.

![Das Diagramm zeigt ein konzeptionelles Modell mit drei Entitäts Typen.](./media/navigation-property/conceptual-model-entity-types-associations.gif)  

Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert den in der Abbildung oben gezeigten `Book`-Entitätstyp:

[!code-xml[EDM_Example_Model#EntityExample](~/samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]

XML-Attribute werden verwendet, um die zum Definieren einer Navigations Eigenschaft erforderlichen Informationen zu übermitteln: das Attribut `Name` das den Namen der Eigenschaft enthält, `Relationship` den Namen der Zuordnung enthält, die er navigiert, und `FromRole` und `ToRole` die Enden der Zuordnung enthalten.

## <a name="see-also"></a>Weitere Informationen

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
- [Beziehungen, Navigations Eigenschaften und Fremdschlüssel](/ef/ef6/fundamentals/relationships)
