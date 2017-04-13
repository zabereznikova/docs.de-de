---
title: "Modelldefinierte Funktion | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Modelldefinierte Funktion
Eine *modelldefinierte Funktion* ist eine Funktion, die in einem konzeptionellen Modell definiert wird.  Der Text einer modelldefinierten Funktion wird in [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) ausgedrückt, sodass die Funktion unabhängig von in der Datenquelle unterstützten Regeln oder Sprachen ausgedrückt werden kann.  
  
 Eine Definition für eine modelldefinierte Funktion enthält die folgenden Informationen:  
  
-   Einen Funktionsnamen.  \(erforderlich\)  
  
-   Den Typ des Rückgabewerts.  \(Optional\)  
  
    > [!NOTE]
    >  Wenn kein Rückgabetyp angegeben wird, ist der Rückgabewert leer.  
  
-   Parameterinformationen.  \(Optional\)  
  
-   Ein [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)\-Ausdruck, der den Text der Funktion definiert.  
  
 Beachten Sie, dass modelldefinierte Funktionen keine Ausgabeparameter unterstützen.  Diese Einschränkung ist vorhanden, damit modelldefinierte Funktionen verfasst werden können.  
  
## Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.  
  
 ![Model mit Datum der Veröffentlichung](../../../../docs/framework/data/adonet/media/modelwithpublisheddate.gif "ModelWithPublishedDate")  
  
 Das [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache \(DSL\) mit der Bezeichnung konzeptionelle Schemadefinitionssprache \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\), um konzeptionelle Modelle zu definieren.  Die folgende CSDL definiert eine Funktion im konzeptionellen Modell, das die Anzahl der Jahre zurückgibt, seit eine Instanz eines `Book` \(in der Abbildung oben\) veröffentlicht wurde.  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## Siehe auch  
 [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)   
 [Entity Data Model: Primitive Datentypen](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)