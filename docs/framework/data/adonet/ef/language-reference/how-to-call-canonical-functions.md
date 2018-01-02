---
title: 'Gewusst wie: Aufrufen von kanonischen Funktionen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b3d84873-7403-4957-8e20-b4ae39f50214
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 2c33bd80635d2bcfb98421c37860596b1367c86b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-call-canonical-functions"></a>Gewusst wie: Aufrufen von kanonischen Funktionen
Die <xref:System.Data.Objects.EntityFunctions>-Klasse enthält Methoden, mit denen kanonische Funktionen in LINQ to Entities-Abfragen verwendet werden können. Weitere Informationen zur kanonischen Funktionen finden Sie unter [Kanonische Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).  
  
> [!NOTE]
>  Die Methoden <xref:System.Data.Objects.EntityFunctions.AsUnicode%2A> und <xref:System.Data.Objects.EntityFunctions.AsNonUnicode%2A> der <xref:System.Data.Objects.EntityFunctions>-Klasse verfügen über keine kanonischen Funktionsentsprechungen.  
  
 Kanonische Funktionen, die eine Berechnung für einen Satz von Werten ausführen und einen einzelnen Wert (auch bekannt als aggregierte kanonische Funktionen) zurückgeben, können direkt aufgerufen werden. Andere kanonische Funktionen können nur als Teil einer LINQ to Entities-Abfrage aufgerufen werden. Zum direkten Aufrufen einer Aggregatfunktion muss eine <xref:System.Data.Objects.ObjectQuery%601> an die Funktion übergeben werden. Weitere Informationen finden Sie unten im zweiten Beispiel.  
  
 Sie können einige kanonische Funktionen mit Common Language Runtime (CLR)-Methoden in LINQ to Entities-Abfragen aufrufen. Eine Liste der CLR-Methoden, die die kanonischen Funktionen zugeordnet sind, finden Sie unter [CLR-Methoden zu kanonischen Funktionszuordnung](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die [AdventureWorks Sales-Modell](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832). Im Beispiel wird eine die <xref:System.Data.Objects.EntityFunctions.DiffDays%2A>-Methode verwendende LINQ to Entities-Abfrage zum Zurückgeben aller Produkte ausgeführt, für die die Differenz zwischen `SellEndDate` und `SellStartDate` weniger als 365 Tage beträgt:  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#1)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#1)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die [AdventureWorks Sales-Modell](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832). Im Beispiel wird die <xref:System.Data.Objects.EntityFunctions.StandardDeviation%2A>-Aggregatmethode aufgerufen, um die Standardabweichung von `SalesOrderHeader`-Teilergebnissen direkt zurückzugeben. Eine <xref:System.Data.Objects.ObjectQuery%601> wird an die Funktion übergeben, durch die sie aufgerufen werden kann, ohne Teil einer LINQ to Entities-Abfrage sein zu müssen.  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#2)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufen von Funktionen in LINQ to Entities-Abfragen](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [Abfragen in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
