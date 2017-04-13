---
title: "Navigationseigenschaft | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Navigationseigenschaft
Eine *Navigationseigenschaft* ist eine optionale Eigenschaft für einen [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md), die die Navigation von einem [Ende](../../../../docs/framework/data/adonet/association-end.md) einer [Zuordnung](../../../../docs/framework/data/adonet/association-type.md) zum anderen Ende ermöglicht.  Im Gegensatz zu anderen [Eigenschaften](../../../../docs/framework/data/adonet/property.md) enthalten Navigationseigenschaften keine Daten.  
  
 Die Definition einer Navigationseigenschaft enthält Folgendes:  
  
-   Einen Namen.  \(erforderlich\)  
  
-   Die Zuordnung, in der sie navigiert.  \(erforderlich\)  
  
-   Die Enden der Zuordnung, in der sie navigiert.  \(erforderlich\)  
  
 Beachten Sie, dass Navigationseigenschaften für beide Entitätstypen an den Enden einer Zuordnung optional sind.  Wenn Sie für einen Entitätstyp am Ende einer Zuordnung eine Navigationseigenschaft definieren, muss keine Navigationseigenschaft für den Entitätstyp am anderen Ende der Zuordnung definiert werden.  
  
 Der Datentyp einer Navigationseigenschaft wird von der [Multiplizität](../../../../docs/framework/data/adonet/association-end-multiplicity.md) des [Remotezuordnungsendes](../../../../docs/framework/data/adonet/association-end.md) bestimmt.  Angenommen, eine Navigationseigenschaft, `OrdersNavProp`, ist für einen `Customer`\-Entitätstyp vorhanden und navigiert eine 1:n\-Zuordnung zwischen `Customer` und `Order`.  Da das Remotezuordnungsende für die Navigationseigenschaft eine Multiplizität von n \(\*\) aufweist, ist sein Datentyp eine Auflistung \(von `Order`\).  Ist eine Navigationseigenschaft, `CustomerNavProp`, für den `Order`\-Entitätstyp vorhanden, wäre sein Datentyp dementsprechend `Customer`, da die Multiplizität des Remoteendes "eins" \(1\) beträgt.  
  
## Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.  Die Navigationseigenschaften `Publisher` und `Authors` werden für den Book\-Entitätstyp definiert.  Die Navigationseigenschaft `Books` wird sowohl für den Publisher\-Entitätstyp als auch den `Author`\-Entitätstyp definiert.  
  
 ![Modell mit Navigationseigenschaften](../../../../docs/framework/data/adonet/media/modelwithnavprops.gif "ModelWithNavProps")  
  
 Das [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache \(DSL\) mit der Bezeichnung konzeptionelle Schemadefinitionssprache \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\), um konzeptionelle Modelle zu definieren.  Die folgende CSDL definiert den in der Abbildung oben gezeigten `Book`\-Entitätstyp:  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 Beachten Sie, dass XML\-Attribute verwendet werden, um die zum Definieren einer Navigationseigenschaft erforderlichen Informationen zu übermitteln: Das Attribut `Name` enthält den Namen der Eigenschaft, `Relationship` enthält den Namen der Zuordnung, in der sie navigiert, und `FromRole` sowie `ToRole` enthalten die Enden der Zuordnung.  
  
## Siehe auch  
 [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)