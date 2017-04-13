---
title: "Zuordnungssatz | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a65247b6-ce59-44ea-974c-14ae20a7995f
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Zuordnungssatz
Ein *Zuordnungssatz* ist ein logischer Container für [Zuordnungsinstanzen](../../../../docs/framework/data/adonet/association-type.md) des gleichen Typs.  Ein Zuordnungssatz ist keine Datenmodellkonstruktion; das heißt, er beschreibt nicht die Struktur von Daten oder Beziehungen.  Vielmehr stellt ein Zuordnungssatz eine Konstruktion für eine Hosting\- oder Speicherumgebung \(z. B. die Common Language Runtime oder eine SQL Server\-Datenbank\) zum Gruppieren von Zuordnungsinstanzen bereit, damit diese einem Datenspeicher zugeordnet werden können.  
  
 Ein Zuordnungssatz wird innerhalb eines [Entitätscontainers](../../../../docs/framework/data/adonet/entity-container.md) definiert, einer logischen Gruppierung von [Entitätenmengen](../../../../docs/framework/data/adonet/entity-set.md) und Zuordnungssätzen.  
  
 Eine Definition für einen Zuordnungssatz enthält die folgenden Informationen:  
  
-   Den Namen des Zuordnungssatzes.  \(erforderlich\)  
  
-   Die Zuordnung, von der er Instanzen enthält.  \(erforderlich\)  
  
-   Zwei [Zuordnungssatzenden](../../../../docs/framework/data/adonet/association-set-end.md).  
  
## Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `PublishedBy` und `WrittenBy`.  Obwohl die Abbildung keine Informationen zu Zuordnungssätzen bereitstellt, zeigt die nächste Abbildung ein Beispiel für Zuordnungssätze und Entitätenmengen auf Grundlage dieses Modells.  
  
 ![Beispielmodell](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Das folgende Beispiel zeigt einen Zuordnungssatz \(`PublishedBy`\) und zwei Entitätenmengen \(`Books` und `Publishers`\), basierend auf dem oben gezeigten Modell.  Bi in der Entitätenmenge `Books` stellt eine Instanz des Entitätstyps `Book` zur Laufzeit dar.  Ebenso stellt Pj eine `Publisher`\-Instanz in der Entitätenmenge `Publishers` dar.  BiPj stellt eine Instanz der `PublishedBy`\-Zuordnung im `PublishedBy`\-Zuordnungssatz dar.  
  
 ![Festlegungsbeispiel](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")  
  
 Das [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache \(DSL\) mit der Bezeichnung konzeptionelle Schemadefinitionssprache \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\), um konzeptionelle Modelle zu definieren.  Die folgende CSDL definiert einen Entitätscontainer mit einem Zuordnungssatz für jede Zuordnung in der oben gezeigten Abbildung.  Beachten Sie, dass der Name und die Zuordnung für jeden Zuordnungssatz mit XML\-Attributen definiert werden.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 Es ist möglich, mehrere Zuordnungssätze pro Zuordnung zu definieren, solange sich nicht zwei Zuordnungssätze ein [Zuordnungssatzende](../../../../docs/framework/data/adonet/association-set-end.md) teilen.  Die folgende CSDL definiert einen Entitätscontainer mit zwei Zuordnungssätzen für die `WrittenBy`\-Zuordnung.  Beachten Sie, dass mehrere Entitätssätze für die Entitätstypen `Book` und `Author` definiert wurden, und dass sich kein Zuordnungssatz ein Zuordnungssatzende teilt.  
  
 [!code-xml[EDM_Example_Model#MultipleAssociationSets](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#multipleassociationsets)]  
  
## Siehe auch  
 [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)   
 [Fremdschlüsseleigenschaft](../../../../docs/framework/data/adonet/foreign-key-property.md)