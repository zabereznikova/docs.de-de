---
title: Aggregatabfragen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d4aa6c0a9103bc4a906ecdfb51a55069e6b8b790
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="aggregate-queries"></a>Aggregatabfragen
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt die Aggregatoperatoren `Average`, `Count`, `Max`, `Min` und `Sum`. Beachten Sie die folgenden Eigenschaften von Aggregatoperatoren in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:  
  
-   Aggregatabfragen werden sofort ausgeführt.  
  
     Weitere Informationen finden Sie unter [Introduction to LINQ queries (C#) (Einführung in LINQ-Abfragen (C#))](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
-   Aggregatabfragen geben i. d. R. eine Zahl statt einer Auflistung zurück.  
  
     Weitere Informationen finden Sie unter [Aggregationsvorgänge](http://msdn.microsoft.com/library/36d97c83-5de5-457d-971d-10a69365e7c4).  
  
-   Sie können keine Aggregate für anonyme Typen aufrufen.  
  
 Die Beispiele in den folgenden Abschnitten leiten sich von der Beispieldatenbank Northwind ab. Weitere Informationen finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Zurückgeben des Durchschnittswerts aus einer numerischen Sequenz](../../../../../../docs/framework/data/adonet/sql/linq/return-the-average-value-from-a-numeric-sequence.md)  
 Zeigt die Verwendung des <xref:System.Linq.Enumerable.Average%2A>-Operators.  
  
 [Zählen der Anzahl von Elementen in einer Sequenz](../../../../../../docs/framework/data/adonet/sql/linq/count-the-number-of-elements-in-a-sequence.md)  
 Zeigt die Verwendung des <xref:System.Linq.Enumerable.Count%2A>-Operators.  
  
 [Suchen des maximalen Werts in einer numerischen Sequenz](../../../../../../docs/framework/data/adonet/sql/linq/find-the-maximum-value-in-a-numeric-sequence.md)  
 Zeigt die Verwendung des <xref:System.Linq.Enumerable.Max%2A>-Operators.  
  
 [Suchen des minimalen Werts in einer numerischen Sequenz](../../../../../../docs/framework/data/adonet/sql/linq/find-the-minimum-value-in-a-numeric-sequence.md)  
 Zeigt die Verwendung des <xref:System.Linq.Enumerable.Min%2A>-Operators.  
  
 [Berechnen der Summe von Werten in einer numerischen Sequenz](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)  
 Zeigt die Verwendung des <xref:System.Linq.Enumerable.Sum%2A>-Operators.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Abfragebeispiele](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 Stellt Links zu [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfragen in Visual Basic und C# bereit.  
  
 [Abfragekonzepte](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 Stellt Links zu Themen bereit, die Konzepte für das Entwickeln von [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]-Abfragen in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erläutern.  
  
 [Introduction to LINQ Queries (C#) (Einführung in LINQ-Abfragen (C#))](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 Erklärt, wie Abfragen in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] funktionieren.
