---
title: "Einschr&#228;nkung der referenziellen Integrit&#228;t | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3d3ba44b-4302-40d8-a7a9-62932e0395e5
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Einschr&#228;nkung der referenziellen Integrit&#228;t
Eine *Einschränkung der referenziellen Integrität* im Entity Data Model \(EDM\) ähnelt einer Einschränkung der referenziellen Integrität in einer relationalen Datenbank.  So wie eine Spalte \(oder Spalten\) einer Datenbanktabelle auf den Primärschlüssel einer anderen Tabelle verweisen kann, kann eine [Eigenschaft](../../../../docs/framework/data/adonet/property.md) \(oder Eigenschaften\) eines [Entitätstyps](../../../../docs/framework/data/adonet/entity-type.md) auf den [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md) eines anderen Entitätstyps verweisen.  Der Entitätstyp, auf den verwiesen wird, wird als *Prinzipalende* der Einschränkung bezeichnet.  Der Entitätstyp, der auf das Prinzipalende verweist, wird als *abhängiges Ende* der Einschränkung bezeichnet.  
  
 Eine Einschränkung der referenziellen Integrität wird als Teil einer [Zuordnung](../../../../docs/framework/data/adonet/association-type.md) zwischen zwei Entitätstypen definiert.  Die Definition für eine Einschränkung der referenziellen Integrität gibt die folgenden Informationen an:  
  
-   Das Prinzipalende der Einschränkung.  \(Ein Entitätstyp, auf dessen Entitätsschlüssel durch das abhängige Ende verwiesen wird.\)  
  
-   Den Entitätsschlüssel des Prinzipalendes.  
  
-   Das abhängige Ende der Einschränkung.  \(Ein Entitätstyp, der über eine Eigenschaft oder Eigenschaften verfügt, die auf den Entitätsschlüssel des Prinzipalendes verweisen.\)  
  
-   Die verweisende Eigenschaft oder Eigenschaften des abhängigen Endes.  
  
 Mit Einschränkungen der referenziellen Integrität im EDM soll sichergestellt werden, dass gültige Zuordnungen immer vorhanden sind.  Weitere Informationen finden Sie unter [Fremdschlüsseleigenschaft](../../../../docs/framework/data/adonet/foreign-key-property.md).  
  
## Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `WrittenBy` und `PublishedBy`.  Der `Book`\-Entitätstyp verfügt über die Eigenschaft `PublisherId`, die auf den Entitätsschlüssel des `Publisher`\-Entitätstyps verweist, wenn Sie eine Einschränkung der referenziellen Integrität für die `PublishedBy`\-Zuordnung definieren.  
  
 ![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")  
  
 Das [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache \(DSL\) mit der Bezeichnung konzeptionelle Schemadefinitionssprache \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\), um konzeptionelle Modelle zu definieren.  Die folgende CSDL definiert eine Einschränkung der referenziellen Integrität für die oben im konzeptionellen Modell gezeigte `PublishedBy`\-Zuordnung.  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## Siehe auch  
 [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)