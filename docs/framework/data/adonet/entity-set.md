---
title: Entitätenmenge
ms.date: 03/30/2017
ms.assetid: 59ec6ab0-88e5-4d25-b112-7a4eccbe61f0
ms.openlocfilehash: 6286d3707a8506e7a389359a5aa361c152e75212
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194791"
---
# <a name="entity-set"></a>Entitätenmenge

Eine *Entitätenmenge* ist ein logischer Container für Instanzen eines [Entitäts Typs](entity-type.md) und Instanzen eines beliebigen Typs, der von diesem Entitätstyp abgeleitet wird. (Informationen zu abgeleiteten Typen finden Sie unter [Entity Data Model: Vererbung](entity-data-model-inheritance.md).) Die Beziehung zwischen einem Entitätstyp und einer Entitätenmenge entspricht der Beziehung zwischen einer Zeile und einer Tabelle in einer relationalen Datenbank: wie eine Zeile beschreibt ein Entitätstyp die Datenstruktur, und wie eine Tabelle enthält eine Entitätenmenge Instanzen einer bestimmten Struktur. Eine Entitätenmenge ist keine Datenmodellkonstruktion, sie beschreibt keine Datenstruktur. Vielmehr stellt eine Entitätenmenge eine Konstruktion für eine Hosting- oder Speicherumgebung (z. B. die Common Language Runtime oder eine SQL Server-Datenbank) zum Gruppieren von Entitätstypinstanzen bereit, damit diese einem Datenspeicher zugeordnet werden können.  
  
 Eine Entitätenmenge wird innerhalb eines [Entitätencontainers](entity-container.md)definiert, einer logischen Gruppierung von Entitätenmengen und Zuordnungs [Sätzen](association-set.md).  
  
 Die folgenden Voraussetzungen müssen erfüllt sein, damit eine Entitätstypinstanz in einer Entitätenmenge existiert:  
  
- Der Typ der Instanz stimmt entweder mit dem Entitätstyp überein, auf dem die Entitätenmenge basiert, oder der Typ der Instanz ist ein Untertyp des Entitätstyps.  
  
- Der [Entitäts Schlüssel](entity-key.md) für die-Instanz ist innerhalb der Entitätenmenge eindeutig.  
  
- Die Instanz ist in keiner anderen Entitätenmenge vorhanden.  
  
    > [!NOTE]
    > Mehrere Entitätenmengen können mit dem gleichen Entitätstyp definiert werden, aber eine Instanz eines bestimmten Entitätstyps kann nur in einer Entitätenmenge vorhanden sein.  
  
 Sie müssen nicht für jeden Entitätstyp in einem konzeptionellen Modell eine Entitätenmenge definieren.  
  
## <a name="example"></a>Beispiel  

 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.  
  
 ![Beispielmodell mit drei Entitäts Typen](./media/entity-set/example-model-three-entity-types.gif)  
  
 Die folgende Abbildung zeigt zwei Entitätenmengen (`Books` und `Publishers`) und einen Zuordnungssatz (`PublishedBy`) auf Grundlage des oben gezeigten konzeptionellen Modells. BI in der `Books` Entitätenmenge stellt zur Laufzeit eine Instanz des `Book` Entitäts Typs dar. Ebenso stellt PJ eine- `Publisher` Instanz in der `Publishers` Entitätenmenge dar. Bipj stellt eine Instanz der Zuordnung `PublishedBy` im Zuordnungs `PublishedBy` Satz dar.  
  
 ![Screenshot, der ein Beispiel für eine Reihe anzeigt.](./media/entity-set/sets-example-association.gif)  
  
 Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert einen Entitätscontainer mit einer Entitätenmenge für jeden Entitätstyp im oben gezeigten konzeptionellen Modell. Beachten Sie, dass der Name und der Entitätstyp für jede Entitätenmenge mit XML-Attributen definiert werden.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 Pro Typ (MEST) können mehrere Entitätssätze definiert werden. Die folgende CSDL definiert einen Entitätscontainer mit zwei Entitätenmengen für den `Book`-Entitätstyp:  
  
 [!code-xml[EDM_Example_Model#MESTExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#mestexample)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
