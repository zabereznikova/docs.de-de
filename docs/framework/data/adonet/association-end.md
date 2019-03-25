---
title: Zuordnungsende
ms.date: 03/30/2017
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
ms.openlocfilehash: 7fb9b48c5ed832e83f2a1e344d17d9a9797d393b
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410328"
---
# <a name="association-end"></a>Zuordnungsende
Ein *Zuordnungsende* identifiziert die [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) an einem Ende einer [Zuordnung](../../../../docs/framework/data/adonet/association-type.md) und die Anzahl der Entität geben an diesem Ende einer Zuordnung-Instanzen, die vorhanden sein können. Zuordnungsenden werden als Teil einer Zuordnung definiert. Eine Zuordnung muss genau zwei Zuordnungsenden aufweisen. [Navigationseigenschaften](../../../../docs/framework/data/adonet/navigation-property.md) ermöglichen die Navigation von einem Zuordnungsende zum anderen.  
  
 Eine Zuordnungsendedefinition enthält die folgenden Informationen:  
  
-   Einen der Entitätstypen der Zuordnung. (erforderlich)  
  
    > [!NOTE]
    >  Für eine bestimmte Zuordnung kann der für jedes Zuordnungsende angegebene Entitätstyp gleich sein. Dadurch wird eine Selbstzuordnung erstellt.  
  
-   Ein [zuordnungsendes](../../../../docs/framework/data/adonet/association-end-multiplicity.md) , der die Anzahl der Instanzen eines Entitätstyps, die an einem Ende der Zuordnung angibt. Ein zuordnungsendes kann einen Wert von eins (1), NULL oder eins (0.. 1) oder viele haben (\*).  
  
-   Der Name für das Zuordnungsende. (Optional)  
  
-   Informationen zu Vorgängen, die für das Zuordnungsende ausgeführt werden, z. B. ON DELETE CASCADE. (Optional)  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `PublishedBy` und `WrittenBy`. Die Zuordnungsenden für die `PublishedBy`-Zuordnung sind die Entitätstypen `Book` und `Publisher`. Die Multiplizität des der `Publisher` -Endes ist eins (1), und die Multiplizität des der `Book` End kann viele (\*), gibt an, dass ein Verleger viele Bücher veröffentlicht und ein Buch von einem Verleger veröffentlicht wird.  
  
 ![Beispielmodell mit drei Entitätstypen](./media/association-end/example-model-three-entity-types.gif)  
  
 Das ADO.NET Entity Framework verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)), konzeptionelle Modelle zu definieren. Die nachfolgende CSDL definiert die in der Abbildung oben gezeigte `PublishedBy`-Zuordnung. Beachten Sie, dass Typ, Name und Multiplizität jedes Zuordnungsendes von XML-Attributen (den Attribute `Type`, `Role` bzw. `Multiplicity`) angegeben werden. Optionale Informationen zu für ein Ende ausgeführten Vorgängen werden in einem XML-Element (dem `OnDelete`-Element) angegeben. In diesem Fall werden beim Löschen eines Verlegers auch alle zugeordneten Bücher gelöscht.  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a>Siehe auch
- [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
