---
title: Zuordnungsende
ms.date: 03/30/2017
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
ms.openlocfilehash: 489802ca18708e076c0cd5dd380ad1361916ad5f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732359"
---
# <a name="association-end"></a>Zuordnungsende
Ein *Assoziationsende* identifiziert den [Entitätstyp](entity-type.md) an einem [Ende einer Zuordnung und die](association-type.md) Anzahl der Entitätstyp Instanzen, die an diesem Ende einer Zuordnung vorhanden sein können. Zuordnungsenden werden als Teil einer Zuordnung definiert. Eine Zuordnung muss genau zwei Zuordnungsenden aufweisen. [Navigations Eigenschaften](navigation-property.md) ermöglichen die Navigation von einem Zuordnungs Ende zum anderen.  
  
 Eine Zuordnungsendedefinition enthält die folgenden Informationen:  
  
- Einen der Entitätstypen der Zuordnung. (erforderlich)  
  
    > [!NOTE]
    > Für eine bestimmte Zuordnung kann der für jedes Zuordnungsende angegebene Entitätstyp gleich sein. Dadurch wird eine Selbstzuordnung erstellt.  
  
- Eine Multiplizität des Zuordnungs [Endes](association-end-multiplicity.md) , die die Anzahl von Entitätstyp Instanzen angibt, die an einem Ende der Zuordnung liegen können. Eine Multiplizität des Zuordnungs Endes kann über einen Wert von eins (1), NULL oder eins (0.. 1) oder viele (\*) verfügen.  
  
- Der Name für das Zuordnungsende. (Optional)  
  
- Informationen zu Vorgängen, die für das Zuordnungsende ausgeführt werden, z. B. ON DELETE CASCADE. (Optional)  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `PublishedBy` und `WrittenBy`. Die Zuordnungsenden für die `PublishedBy`-Zuordnung sind die Entitätstypen `Book` und `Publisher`. Die Multiplizität des `Publisher` Endes ist eins (1), und die Multiplizität des `Book` enden ist n (\*), was darauf hinweist, dass ein Verleger viele Bücher veröffentlicht und ein Buch von einem Verleger veröffentlicht wird.  
  
 ![Beispielmodell mit drei Entitäts Typen](./media/association-end/example-model-three-entity-types.gif)  
  
 Der ADO.NET-Entity Framework verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren. Die nachfolgende CSDL definiert die in der Abbildung oben gezeigte `PublishedBy`-Zuordnung. Beachten Sie, dass Typ, Name und Multiplizität jedes Zuordnungsendes von XML-Attributen (den Attribute `Type`, `Role` bzw. `Multiplicity`) angegeben werden. Optionale Informationen zu für ein Ende ausgeführten Vorgängen werden in einem XML-Element (dem `OnDelete`-Element) angegeben. In diesem Fall werden beim Löschen eines Verlegers auch alle zugeordneten Bücher gelöscht.  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
