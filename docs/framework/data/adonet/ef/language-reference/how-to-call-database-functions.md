---
title: 'Gewusst wie: Aufrufen von Datenbankfunktionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79038efa-15bf-464a-83e2-35fe145252ce
ms.openlocfilehash: b885cedbb324ee0a076990bceb28bf256814bb26
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760647"
---
# <a name="how-to-call-database-functions"></a>Gewusst wie: Aufrufen von Datenbankfunktionen
Die <xref:System.Data.Objects.SqlClient.SqlFunctions>-Klasse enthält Methoden, mit denen SQL Server-Funktionen in LINQ to Entities-Abfragen verwendet werden können. Beim Verwenden von <xref:System.Data.Objects.SqlClient.SqlFunctions>-Methoden in LINQ to Entities-Abfragen werden die entsprechenden Datenbankfunktionen in der Datenbank ausgeführt.  
  
> [!NOTE]
>  Datenbankfunktionen, die eine Berechnung für einen Satz von Werten ausführen und einen einzelnen Wert (auch bekannt als aggregierte Datenbankfunktionen) zurückgeben, können direkt aufgerufen werden. Andere kanonische Funktionen können nur als Teil einer LINQ to Entities-Abfrage aufgerufen werden. Zum direkten Aufrufen einer Aggregatfunktion muss eine <xref:System.Data.Objects.ObjectQuery%601> an die Funktion übergeben werden. Weitere Informationen finden Sie unten im zweiten Beispiel.  
  
> [!NOTE]
>  Die Methoden in der <xref:System.Data.Objects.SqlClient.SqlFunctions>-Klasse sind spezifisch für SQL Server-Funktionen. Ähnliche Klassen, die Datenbankfunktionen verfügbar machen, sind möglicherweise über andere Anbieter verfügbar.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die [AdventureWorks Sales-Modell](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832). Im Beispiel wird eine LINQ to Entities-Abfrage ausgeführt, die die <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A>-Methode zur Rückgabe aller Kontakte verwendet, deren Nachname mit "Si" beginnt:  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#3)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#3)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die [AdventureWorks Sales-Modell](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832). Im Beispiel wird die aggregierte <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A>-Methode direkt aufgerufen. Eine <xref:System.Data.Objects.ObjectQuery%601> wird an die Funktion übergeben, durch die sie aufgerufen werden kann, ohne Teil einer LINQ to Entities-Abfrage sein zu müssen.  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#4)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#4)]  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufen von Funktionen in LINQ to Entities-Abfragen](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [Abfragen in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
