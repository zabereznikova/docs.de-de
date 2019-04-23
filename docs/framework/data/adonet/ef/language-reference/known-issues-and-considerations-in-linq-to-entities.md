---
title: Bekannte Probleme von und Überlegungen zu LINQ to Entities
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: acd71129-5ff0-4b4e-b266-c72cc0c53601
ms.openlocfilehash: 3945d4fc92bea2c4212da0507618203603ae8aba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191327"
---
# <a name="known-issues-and-considerations-in-linq-to-entities"></a>Bekannte Probleme von und Überlegungen zu LINQ to Entities
Dieser Abschnitt enthält Informationen zu bekannten Problemen bei [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]-Abfragen.  
  
-   [LINQ-Abfragen, können nicht zwischengespeichert werden](#LINQQueriesThatAreNotCached)  
  
-   [Fehlende Sortierung](#OrderingInfoLost)  
  
-   [Ganzzahlen ohne Vorzeichen, die nicht unterstützt](#UnsignedIntsUnsupported)  
  
-   [Fehler bei der Datentypkonvertierung](#TypeConversionErrors)  
  
-   [Verweisen auf nicht skalare Variablen werden nicht unterstützt](#RefNonScalarClosures)  
  
-   [Geschachtelte Abfragen schlagen möglicherweise mit SQLServer 2000 fehl.](#NestedQueriesSQL2000)  
  
-   [Projizieren auf einen anonymen Typ](#ProjectToAnonymousType)  
  
<a name="LINQQueriesThatAreNotCached"></a>   
## <a name="linq-queries-that-cannot-be-cached"></a>LINQ-Abfragen, die nicht zwischengespeichert werden können  
 Ab .NET Framework 4.5 werden LINQ to Entities-Abfragen automatisch zwischengespeichert. LINQ to Entities-Abfragen, die den `Enumerable.Contains`-Operator auf Auflistungen im Arbeitsspeicher anwenden, werden jedoch nicht automatisch zwischengespeichert. Darüber hinaus ist das Parametrisieren von Auflistungen im Arbeitsspeicher in kompilierten LINQ-Abfragen nicht zulässig.  
  
<a name="OrderingInfoLost"></a>   
## <a name="ordering-information-lost"></a>Fehlende Sortierung  
 Beim Projizieren von Spalten in einen anonymen Typ geht die Sortierung in einigen Abfragen verloren, die für eine [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)]-Datenbank mit dem Kompatibilitätsgrad "80" ausgeführt werden.  Dies kann vorkommen, wenn ein Spaltenname in der Sortierliste einem Spaltennamen im Selektor entspricht, wie im folgenden Beispiel dargestellt:  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt543840)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt543840)]  
  
<a name="UnsignedIntsUnsupported"></a>   
## <a name="unsigned-integers-not-supported"></a>Keine Unterstützung von ganzen Zahlen ohne Vorzeichen  
 Sie können in einer [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]-Abfrage keine ganze Zahl ohne Vorzeichen angeben, da das [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] keine ganzen Zahlen ohne Vorzeichen unterstützt. Wenn Sie eine Ganzzahl ohne Vorzeichen angeben einer <xref:System.ArgumentException> Ausnahme aus, während der Übersetzung des Abfrageausdrucks, wie im folgenden Beispiel gezeigt. In diesem Beispiel wird die Bestellung mit der ID 48000 abgefragt.  
  
 [!code-csharp[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#uintasqueryparam)]
 [!code-vb[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#uintasqueryparam)]  
  
<a name="TypeConversionErrors"></a>   
## <a name="type-conversion-errors"></a>Typkonvertierungsfehler  
 Wenn Sie in Visual Basic einer Eigenschaft mithilfe der `CByte`-Funktion eine Spalte des SQL Server-Bittyps mit dem Wert 1 zuordnen, wird eine <xref:System.Data.SqlClient.SqlException> mit der Meldung "Arithmetischer Überlauffehler" ausgelöst. Im folgenden Beispiel wird in der AdventureWorks-Beispieldatenbank die `Product.MakeFlag`-Spalte abgefragt, und beim Durchlaufen der Abfrageergebnisse wird eine Ausnahme ausgelöst.  
  
 [!code-vb[DP L2E Conceptual Examples#SBUDT544355](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt544355)]  
  
<a name="RefNonScalarClosures"></a>   
## <a name="referencing-non-scalar-variables-not-supported"></a>Keine Unterstützung von Verweisen auf nicht skalare Variablen  
 Verweise auf eine nicht skalare Variable, beispielsweise eine Entität, in einer Abfrage werden nicht unterstützt. Bei der Ausführung einer solchen Abfrage wird eine <xref:System.NotSupportedException>-Ausnahme mit der Meldung ausgelöst, dass ein konstanter Wert des Typs `EntityType` nicht erstellt werden kann, weil im gegebenen Kontext nur primitive Typen, beispielsweise Int32, Zeichenfolge und Guid unterstützt werden.  
  
> [!NOTE]
>  Verweise auf eine Auflistung von skalaren Variablen werden unterstützt.  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt555877)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt555877)]  
  
<a name="NestedQueriesSQL2000"></a>   
## <a name="nested-queries-may-fail-with-sql-server-2000"></a>Geschachtelte Abfragen schlagen mit SQL Server 2000 möglicherweise fehl  
 Mit SQL Server 2000 schlagen LINQ to Entities-Abfragen möglicherweise fehl, wenn sie geschachtelte Transact-SQL-Abfragen erzeugen, die drei oder mehr Ebenen tief sind.  
  
<a name="ProjectToAnonymousType"></a>   
## <a name="projecting-to-an-anonymous-type"></a>Projizieren auf einen anonymen Typ  
 Wenn Sie den anfänglichen Abfragepfad so definieren, dass mithilfe der <xref:System.Data.Objects.ObjectQuery%601.Include%2A>-Methode verknüpfte Objekte in <xref:System.Data.Objects.ObjectQuery%601> eingeschlossen werden, und dann LINQ verwenden, um die zurückgegebenen Objekte auf einen anonymen Typ zu projizieren, werden die in der Include-Methode angegebenen Objekte nicht in die Abfrageergebnisse eingeschlossen.  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype1)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype1)]  
  
 Um verknüpfte Objekte abzurufen, projizieren Sie die zurückgegebenen Typen nicht auf einen anonymen Typ.  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype2)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype2)]  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)
