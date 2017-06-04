---
title: "Entity Data Model: Vererbung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 42c7ef24-710a-4af9-8493-cd41c399ecb0
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Entity Data Model: Vererbung
Das Entity Data Model \(EDM\) unterstützt Vererbung für [Entitätstypen](../../../../docs/framework/data/adonet/entity-type.md).  Vererbung im EDM ist ähnlich wie Vererbung für Klassen in objektorientierten Programmiersprachen.  Wie mit Klassen in objektorientierten Sprachen können Sie in einem konzeptionellen Modell einen Entitätstyp \(einen *abgeleiteten Typ*\) definieren, der von einem anderen Entitätstyp \(dem *Basistyp*\) erbt.  Im Gegensatz zu Klassen in objektorientierter Programmierung erbt jedoch in einem konzeptionellen Modell der abgeleitete Typ immer alle [Eigenschaften](../../../../docs/framework/data/adonet/property.md) und [Navigationseigenschaften](../../../../docs/framework/data/adonet/navigation-property.md) des Basistyps.  Geerbte Eigenschaften in einem abgeleiteten Typ können nicht überschrieben werden.  
  
 In einem konzeptionellen Modell können Sie Vererbungshierarchien erstellen, in denen ein abgeleiteter Typ von einem anderen abgeleiteten Typ erbt.  Der Typ am Anfang der Hierarchie \(der eine Typ in der Hierarchie, die kein abgeleiteter Typ ist\) wird als *Stammtyp* bezeichnet.  In einer Vererbungshierarchie muss der [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md) für den Stammtyp definiert sein.  
  
 Sie können keine Vererbungshierarchien erstellen, in denen ein abgeleiteter Typ von mehr als einem Typ erbt.  In einem konzeptionellen Modell mit einem `Book`\-Entitätstyp könnten Sie z. B. die abgeleiteten Typen `FictionBook` und `NonFictionBook` definieren, die jeweils von `Book` erben.  Sie könnten dann jedoch keinen Typ definieren, der vom Typ `FictionBook` und vom Typ `NonFictionBook` erbt.  
  
## Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit vier Entitätstypen: `Book`, `FictionBook`, `Publisher` und `Author`.  Der `FictionBook`\-Entitätstyp ist ein abgeleiteter Typ, der vom `Book`\-Entitätstyp erbt.  Der `FictionBook`\-Typ erbt die Eigenschaften `ISBN (Key)`, `Title` und `Revision`, und definiert die zusätzliche Eigenschaft `Genre`.  
  
 ![Vererbung](../../../../docs/framework/data/adonet/media/inheritanceexample.gif "InheritanceExample")  
  
 Das [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache \(DSL\) mit der Bezeichnung konzeptionelle Schemadefinitionssprache \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\), um konzeptionelle Modelle zu definieren.  Die folgende CSDL definiert den Entitätstyp `FictionBook`, der vom `Book`\-Typ \(wie in der Abbildung oben\) erbt:  
  
 [!code-xml[EDM_Example_Model#DerivedType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books5.edmx#derivedtype)]  
  
## Siehe auch  
 [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)