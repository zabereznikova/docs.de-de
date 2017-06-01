---
title: "CAST (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 07b6d750-dfd4-48a9-b86c-3badcbba6f70
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# CAST (Entity SQL)
Konvertiert einen Ausdruck von einem Datentyp in einen anderen.  
  
## Syntax  
  
```  
  
CAST ( expression AS data_type)  
```  
  
## Argumente  
 `expression`  
 Ein gültiger Ausdruck, der zu `data_type` konvertierbar ist.  
  
 `data_type`  
 Der vom Zielsystem bereitgestellte Datentyp. Dabei muss es sich um einen primitiven \(skalaren\) Typ handeln. Der verwendete `data_type` hängt von der Abfrageumgebung ab. Wird eine Abfrage mit dem <xref:System.Data.EntityClient.EntityCommand> ausgeführt, ist der Datentyp ein im konzeptionellen Modell definierter Typ. Weitere Informationen finden Sie unter [CSDL\-Spezifikation](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md). Wenn eine Abfrage mit <xref:System.Data.Objects.ObjectQuery%601> ausgeführt wird, ist der Datentyp ein CLR\-Typ.  
  
## Rückgabewert  
 Gibt denselben Wert zurück wie `data_type`.  
  
## Hinweise  
 Der CAST\-Ausdruck verfügt über eine ähnliche Semantik wie der CONVERT\-Ausdruck von [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]. Der CAST\-Ausdruck wird zum Konvertieren eines Werts von einem Typ in einen Wert von einem anderen Typ verwendet.  
  
```  
CAST( e as T )  
```  
  
 Wenn "e" vom Typ "S" ist und "S" zu "T" konvertierbar ist, ist der obige Ausdruck ein gültiger Umwandlungsausdruck. "T" muss dabei ein primitiver \(skalarer\) Typ sein.  
  
 Beim Umwandeln in `Edm.Decimal` können Werte für die Facets der Genauigkeit und der Dezimalstellenanzahl bereitgestellt werden. Werden keine expliziten Angaben gemacht, sind die Standardwerte für Genauigkeit und Dezimalstellenanzahl 18 bzw. 0. Insbesondere werden folgende Überladungen von `Decimal` unterstützt:  
  
-   `CAST( d as Edm.Decimal );`  
  
-   `CAST( d as Edm.Decimal(precision) );`  
  
-   `CAST( d as Edm.Decimal(precision, scale) );`  
  
 Die Verwendung eines Umwandlungsausdrucks wird als explizite Konvertierung aufgefasst. Explizite Konvertierungen können Daten abschneiden oder zu Genauigkeitsverlust führen.  
  
> [!NOTE]
>  CAST wird nur für primitive Typen und Enumerationsmembertypen unterstützt.  
  
## Beispiel  
 In der folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Abfrage wird der CAST\-Operator zum Umwandeln des Datentyps eines Ausdrucks in einen anderen verwendet. Diese Abfrage beruht auf dem "AdventureWorks Sales"\-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren unter [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType\-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery`\-Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#CAST](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#cast)]  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)