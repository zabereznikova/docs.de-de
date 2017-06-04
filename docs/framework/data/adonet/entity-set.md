---
title: "Entit&#228;tenmenge | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 59ec6ab0-88e5-4d25-b112-7a4eccbe61f0
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Entit&#228;tenmenge
Eine *Entitätenmenge* ist ein logischer Container für Instanzen eines [Entitätstyps](../../../../docs/framework/data/adonet/entity-type.md) und für Instanzen eines von diesem Entitätstyp abgeleiteten Typs.  \(Informationen zu abgeleiteten Typen finden Sie unter [Entity Data Model: Vererbung](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md).\) Die Beziehung zwischen einem Entitätstyp und einer Entitätenmenge entspricht der Beziehung zwischen einer Zeile und einer Tabelle in einer relationalen Datenbank: Wie eine Zeile beschreibt ein Entitätstyp Datenstruktur, und eine Entitätenmenge enthält wie eine Tabelle Instanzen einer bestimmten Struktur.  Eine Entitätenmenge ist keine Datenmodellkonstruktion, sie beschreibt keine Datenstruktur.  Vielmehr stellt eine Entitätenmenge eine Konstruktion für eine Hosting\- oder Speicherumgebung \(z. B. die Common Language Runtime oder eine SQL Server\-Datenbank\) zum Gruppieren von Entitätstypinstanzen bereit, damit diese einem Datenspeicher zugeordnet werden können.  
  
 Eine Entitätenmenge wird innerhalb eines [Entitätscontainers](../../../../docs/framework/data/adonet/entity-container.md) definiert, einer logischen Gruppierung von Entitätenmengen und [Zuordnungssätzen](../../../../docs/framework/data/adonet/association-set.md).  
  
 Die folgenden Voraussetzungen müssen erfüllt sein, damit eine Entitätstypinstanz in einer Entitätenmenge existiert:  
  
-   Der Typ der Instanz stimmt entweder mit dem Entitätstyp überein, auf dem die Entitätenmenge basiert, oder der Typ der Instanz ist ein Untertyp des Entitätstyps.  
  
-   Der [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md) für die Instanz ist innerhalb der Entitätenmenge eindeutig.  
  
-   Die Instanz ist in keiner anderen Entitätenmenge vorhanden.  
  
    > [!NOTE]
    >  Mehrere Entitätenmengen können mit dem gleichen Entitätstyp definiert werden, aber eine Instanz eines bestimmten Entitätstyps kann nur in einer Entitätenmenge vorhanden sein.  
  
 Sie müssen nicht für jeden Entitätstyp in einem konzeptionellen Modell eine Entitätenmenge definieren.  
  
## Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.  
  
 ![Beispielmodell](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Die folgende Abbildung zeigt zwei Entitätenmengen \(`Books` und `Publishers`\) und einen Zuordnungssatz \(`PublishedBy`\) auf Grundlage des oben gezeigten konzeptionellen Modells.  Bi in der Entitätenmenge `Books` stellt eine Instanz des Entitätstyps `Book` zur Laufzeit dar.  Ebenso stellt Pj eine `Publisher`\-Instanz in der Entitätenmenge `Publishers` dar.  BiPj stellt eine Instanz der `PublishedBy`\-Zuordnung im `PublishedBy`\-Zuordnungssatz dar.  
  
 ![Festlegungsbeispiel](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")  
  
 Das [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache \(DSL\) mit der Bezeichnung konzeptionelle Schemadefinitionssprache \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\), um konzeptionelle Modelle zu definieren.  Die folgende CSDL definiert einen Entitätscontainer mit einer Entitätenmenge für jeden Entitätstyp im oben gezeigten konzeptionellen Modell.  Beachten Sie, dass der Name und der Entitätstyp für jede Entitätenmenge mit XML\-Attributen definiert werden.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 Pro Typ \(MEST\) können mehrere Entitätssätze definiert werden.  Die folgende CSDL definiert einen Entitätscontainer mit zwei Entitätenmengen für den `Book`\-Entitätstyp:  
  
 [!code-xml[EDM_Example_Model#MESTExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#mestexample)]  
  
## Siehe auch  
 [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)