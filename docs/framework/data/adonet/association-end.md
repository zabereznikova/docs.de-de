---
title: "Zuordnungsende | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Zuordnungsende
Ein *Zuordnungsende* identifiziert den [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) an einem Ende einer [Zuordnung](../../../../docs/framework/data/adonet/association-type.md) und die Anzahl von Entitätstypinstanzen, die an diesem Ende einer Zuordnung vorhanden sein können.  Zuordnungsenden werden als Teil einer Zuordnung definiert. Eine Zuordnung muss genau zwei Zuordnungsenden aufweisen.  [Navigationseigenschaften](../../../../docs/framework/data/adonet/navigation-property.md) ermöglichen die Navigation zwischen den Zuordnungsenden.  
  
 Eine Zuordnungsendedefinition enthält die folgenden Informationen:  
  
-   Einen der Entitätstypen der Zuordnung.  \(erforderlich\)  
  
    > [!NOTE]
    >  Für eine bestimmte Zuordnung kann der für jedes Zuordnungsende angegebene Entitätstyp gleich sein.  Dadurch wird eine Selbstzuordnung erstellt.  
  
-   Eine [Multiplizität des Zuordnungsendes](../../../../docs/framework/data/adonet/association-end-multiplicity.md), die die Anzahl möglicher Entitätstypinstanzen an einem Ende der Zuordnung angibt.  Die Multiplizität eines Zuordnungsendes kann über einen Wert von eins \(1\), null oder eins \(0..1\) oder n \(\*\) verfügen.  
  
-   Der Name für das Zuordnungsende.  \(Optional\)  
  
-   Informationen zu Vorgängen, die für das Zuordnungsende ausgeführt werden, z. B. ON DELETE CASCADE.  \(Optional\)  
  
## Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `PublishedBy` und `WrittenBy`.  Die Zuordnungsenden für die `PublishedBy`\-Zuordnung sind die Entitätstypen `Book` und `Publisher`.  Die Multiplizität des `Publisher`\-Endes ist eins \(1\), und die Multiplizität des `Book`\-Endes ist n \(\*\), wodurch angegeben wird, dass ein Verleger viele Bücher veröffentlicht und ein Buch von einem Verleger veröffentlicht wird.  
  
 ![Beispielmodell](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Das ADO.NET Entity Framework verwendet eine domänenspezifische Sprache \(DSL\) mit der Bezeichnung konzeptionelle Schemadefinitionssprache \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\), um konzeptionelle Modelle zu definieren.  Die nachfolgende CSDL definiert die in der Abbildung oben gezeigte `PublishedBy`\-Zuordnung.  Beachten Sie, dass Typ, Name und Multiplizität jedes Zuordnungsendes von XML\-Attributen \(den Attribute `Type`, `Role` bzw. `Multiplicity`\) angegeben werden.  Optionale Informationen zu für ein Ende ausgeführten Vorgängen werden in einem XML\-Element \(dem `OnDelete`\-Element\) angegeben.  In diesem Fall werden beim Löschen eines Verlegers auch alle zugeordneten Bücher gelöscht.  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## Siehe auch  
 [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)