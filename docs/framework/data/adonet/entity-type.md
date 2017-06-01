---
title: "Entit&#228;tstyp | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Entit&#228;tstyp
Der *Entitätstyp* ist der wesentliche Baustein zum Beschreiben der Datenstruktur mit dem Entity Data Model \(EDM\).  In einem konzeptionellen Modell stellt ein Entitätstyp die Struktur von Konzepten der obersten Ebene dar, z. B. Kunden oder Bestellungen.  Ein Entitätstyp ist eine Vorlage für Entitätstypinstanzen.  Jede Vorlage enthält die folgenden Informationen:  
  
-   Eine eindeutige Bezeichnung.  \(Erforderlich.\)  
  
-   Einen durch eine oder mehrere Eigenschaften definierten [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md).  \(Erforderlich.\)  
  
-   Daten in Form von [Eigenschaften](../../../../docs/framework/data/adonet/property.md).  \(Optional\)  
  
-   [Navigationseigenschaften](../../../../docs/framework/data/adonet/navigation-property.md), die die Navigation von einem [Ende](../../../../docs/framework/data/adonet/association-end.md) einer [Zuordnung](../../../../docs/framework/data/adonet/association-type.md) zum anderen Ende ermöglichen.  \(Optional\)  
  
 In einer Anwendung stellt eine Instanz eines Entitätstyps ein spezielles Objekt dar, wie etwa einen bestimmten Kunden oder eine Bestellung.  Jede Instanz eines Entitätstyps muss über einen eindeutigen [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md) innerhalb einer [Entitätenmenge](../../../../docs/framework/data/adonet/entity-set.md) verfügen.  
  
 Zwei Instanzen eines Entitätstyps werden nur dann als gleich betrachtet, wenn sie vom selben Typ sind und die Werte ihrer Entitätsschlüssel übereinstimmen.  
  
## Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`:  
  
 ![Beispielmodell](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Beachten Sie, dass die Eigenschaften jedes Entitätstyps, die den entsprechenden Entitätsschlüssel bilden, mit "\(Schlüssel\)" angegeben werden.  
  
 Das [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache \(DSL\) mit der Bezeichnung konzeptionelle Schemadefinitionssprache \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\), um konzeptionelle Modelle zu definieren.  Die folgende CSDL definiert den in der Abbildung oben gezeigten `Book`\-Entitätstyp:  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## Siehe auch  
 [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)   
 [Facet](../../../../docs/framework/data/adonet/facet.md)