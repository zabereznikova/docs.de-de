---
title: Zuordnungsende
ms.date: 03/30/2017
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
ms.openlocfilehash: 33cc2e10d9b72ef7f5f024905938c41fcc4a9755
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785045"
---
# <a name="association-end"></a>Zuordnungsende
Ein *Assoziationsende* identifiziert den [Entitätstyp](entity-type.md) an einem [Ende einer Zuordnung und die](association-type.md) Anzahl der Entitätstyp Instanzen, die an diesem Ende einer Zuordnung vorhanden sein können. Zuordnungsenden werden als Teil einer Zuordnung definiert. Eine Zuordnung muss genau zwei Zuordnungsenden aufweisen. [Navigations Eigenschaften](navigation-property.md) ermöglichen die Navigation von einem Zuordnungs Ende zum anderen.  
  
 Eine Zuordnungsendedefinition enthält die folgenden Informationen:  
  
- Einen der Entitätstypen der Zuordnung. (erforderlich)  
  
    > [!NOTE]
    > Für eine bestimmte Zuordnung kann der für jedes Zuordnungsende angegebene Entitätstyp gleich sein. Dadurch wird eine Selbstzuordnung erstellt.  
  
- Eine Multiplizität des Zuordnungs [Endes](association-end-multiplicity.md) , die die Anzahl von Entitätstyp Instanzen angibt, die an einem Ende der Zuordnung liegen können. Die Multiplizität eines Zuordnungs Endes kann einen Wert von eins (1), NULL oder eins (0.. 1) oder viele\*() haben.  
  
- Der Name für das Zuordnungsende. (Optional)  
  
- Informationen zu Vorgängen, die für das Zuordnungsende ausgeführt werden, z. B. ON DELETE CASCADE. (Optional)  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `PublishedBy` und `WrittenBy`. Die Zuordnungsenden für die `PublishedBy`-Zuordnung sind die Entitätstypen `Book` und `Publisher`. Die Multiplizität des `Publisher` Endes ist eins (1), und die Multiplizität `Book` des Endes ist "\*many ()", was bedeutet, dass ein Verleger viele Bücher veröffentlicht und ein Buch von einem Verleger veröffentlicht wird.  
  
 ![Beispielmodell mit drei Entitäts Typen](./media/association-end/example-model-three-entity-types.gif)  
  
 Der ADO.NET-Entity Framework verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](./ef/language-reference/csdl-specification.md)), um konzeptionelle Modelle zu definieren. Die nachfolgende CSDL definiert die in der Abbildung oben gezeigte `PublishedBy`-Zuordnung. Beachten Sie, dass Typ, Name und Multiplizität jedes Zuordnungsendes von XML-Attributen (den Attribute `Type`, `Role` bzw. `Multiplicity`) angegeben werden. Optionale Informationen zu für ein Ende ausgeführten Vorgängen werden in einem XML-Element (dem `OnDelete`-Element) angegeben. In diesem Fall werden beim Löschen eines Verlegers auch alle zugeordneten Bücher gelöscht.  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
