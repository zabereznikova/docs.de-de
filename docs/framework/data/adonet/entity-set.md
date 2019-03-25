---
title: Entitätenmenge
ms.date: 03/30/2017
ms.assetid: 59ec6ab0-88e5-4d25-b112-7a4eccbe61f0
ms.openlocfilehash: d75002d4a5ac55538f76e6bace0fc16095a9ef74
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412187"
---
# <a name="entity-set"></a>Entitätenmenge
Ein *Entitätenmenge* ist ein logischer Container für Instanzen von einem [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) und Instanzen eines beliebigen Typs, der von diesem Entitätstyp abgeleitet. (Weitere Informationen zu abgeleiteten Typen finden Sie unter [Entity Data Model: Vererbung](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md).) Die Beziehung zwischen einem Entitätstyp und einer Entitätenmenge ist analog zur Beziehung zwischen einer Zeile und eine Tabelle in einer relationalen Datenbank: Wie eine Zeile beschreibt ein Entitätstyp Datenstruktur, und wie eine Tabelle enthält ein Entitätssatz Instanzen einer bestimmten Struktur. Eine Entitätenmenge ist keine Datenmodellkonstruktion, sie beschreibt keine Datenstruktur. Vielmehr stellt eine Entitätenmenge eine Konstruktion für eine Hosting- oder Speicherumgebung (z. B. die Common Language Runtime oder eine SQL Server-Datenbank) zum Gruppieren von Entitätstypinstanzen bereit, damit diese einem Datenspeicher zugeordnet werden können.  
  
 Eine Entitätenmenge wird definiert, innerhalb einer [Entitätscontainer](../../../../docs/framework/data/adonet/entity-container.md), dies ist eine logische Gruppierung von Entitätenmengen und [Zuordnungssätze](../../../../docs/framework/data/adonet/association-set.md).  
  
 Die folgenden Voraussetzungen müssen erfüllt sein, damit eine Entitätstypinstanz in einer Entitätenmenge existiert:  
  
-   Der Typ der Instanz stimmt entweder mit dem Entitätstyp überein, auf dem die Entitätenmenge basiert, oder der Typ der Instanz ist ein Untertyp des Entitätstyps.  
  
-   Die [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md) für die Instanz innerhalb der Entitätenmenge eindeutig ist.  
  
-   Die Instanz ist in keiner anderen Entitätenmenge vorhanden.  
  
    > [!NOTE]
    >  Mehrere Entitätenmengen können mit dem gleichen Entitätstyp definiert werden, aber eine Instanz eines bestimmten Entitätstyps kann nur in einer Entitätenmenge vorhanden sein.  
  
 Sie müssen nicht für jeden Entitätstyp in einem konzeptionellen Modell eine Entitätenmenge definieren.  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.  
  
 ![Beispielmodell mit drei Entitätstypen](./media/entity-set/example-model-three-entity-types.gif)  
  
 Die folgende Abbildung zeigt zwei Entitätenmengen (`Books` und `Publishers`) und einen Zuordnungssatz (`PublishedBy`) auf Grundlage des oben gezeigten konzeptionellen Modells. BI in der `Books` Entitätenmenge stellt eine Instanz von der `Book` Entitätstyp zur Laufzeit. Auf ähnliche Weise darstellen von Pj eine `Publisher` -Instanz der `Publishers` Entitätenmenge. BiPj stellt eine Instanz von der `PublishedBy` Zuordnung in der `PublishedBy` Zuordnungssatz.  
  
 ![Screenshot, ein Beispiel für Gruppen zeigt.](./media/entity-set/sets-example-association.gif)  
  
 Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)), konzeptionelle Modelle zu definieren. Die folgende CSDL definiert einen Entitätscontainer mit einer Entitätenmenge für jeden Entitätstyp im oben gezeigten konzeptionellen Modell. Beachten Sie, dass der Name und der Entitätstyp für jede Entitätenmenge mit XML-Attributen definiert werden.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 Pro Typ (MEST) können mehrere Entitätssätze definiert werden. Die folgende CSDL definiert einen Entitätscontainer mit zwei Entitätenmengen für den `Book`-Entitätstyp:  
  
 [!code-xml[EDM_Example_Model#MESTExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#mestexample)]  
  
## <a name="see-also"></a>Siehe auch
- [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
