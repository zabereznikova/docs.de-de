---
title: Bekannte Probleme von und Überlegungen zu LINQ to Entities
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: acd71129-5ff0-4b4e-b266-c72cc0c53601
ms.openlocfilehash: 0d36461cea68383e070db80d85f596151bd9c2ae
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161957"
---
# <a name="known-issues-and-considerations-in-linq-to-entities"></a>Bekannte Probleme von und Überlegungen zu LINQ to Entities

Dieser Abschnitt enthält Informationen zu bekannten Problemen bei LINQ to Entities-Abfragen.  
  
- [LINQ-Abfragen, die nicht zwischengespeichert werden können](#LINQQueriesThatAreNotCached)  
  
- [Fehlende Sortierung](#OrderingInfoLost)  
  
- [Keine Unterstützung von ganzen Zahlen ohne Vorzeichen](#UnsignedIntsUnsupported)  
  
- [Typkonvertierungsfehler](#TypeConversionErrors)  
  
- [Keine Unterstützung von Verweisen auf nicht skalare Variablen](#RefNonScalarClosures)  
  
- [Geschachtelte Abfragen schlagen mit SQL Server 2000 möglicherweise fehl](#NestedQueriesSQL2000)  
  
- [Projizieren auf einen anonymen Typ](#ProjectToAnonymousType)  
  
<a name="LINQQueriesThatAreNotCached"></a>

## <a name="linq-queries-that-cannot-be-cached"></a>LINQ-Abfragen, die nicht zwischengespeichert werden können  

 Ab .NET Framework 4.5 werden LINQ to Entities-Abfragen automatisch zwischengespeichert. LINQ to Entities-Abfragen, die den `Enumerable.Contains`-Operator auf Auflistungen im Arbeitsspeicher anwenden, werden jedoch nicht automatisch zwischengespeichert. Darüber hinaus ist das Parametrisieren von Auflistungen im Arbeitsspeicher in kompilierten LINQ-Abfragen nicht zulässig.  
  
<a name="OrderingInfoLost"></a>

## <a name="ordering-information-lost"></a>Fehlende Sortierung  

 Das Projizieren von Spalten in einen anonymen Typ bewirkt, dass die Bestellinformationen in einigen Abfragen verloren gehen, die für eine SQL Server 2005-Datenbank mit dem Kompatibilitäts Grad "80" ausgeführt werden.  Dies kann vorkommen, wenn ein Spaltenname in der Sortierliste einem Spaltennamen im Selektor entspricht, wie im folgenden Beispiel dargestellt:  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt543840)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt543840)]  
  
<a name="UnsignedIntsUnsupported"></a>

## <a name="unsigned-integers-not-supported"></a>Keine Unterstützung von ganzen Zahlen ohne Vorzeichen  

 Das Angeben eines ganzzahligen Typs ohne Vorzeichen in einer LINQ to Entities Abfrage wird nicht unterstützt, da die Entity Framework keine Ganzzahlen ohne Vorzeichen unterstützt. Wenn Sie eine ganze Zahl ohne Vorzeichen angeben, <xref:System.ArgumentException> wird während der Übersetzung des Abfrage Ausdrucks eine Ausnahme ausgelöst, wie im folgenden Beispiel gezeigt. In diesem Beispiel wird die Bestellung mit der ID 48000 abgefragt.  
  
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
> Verweise auf eine Auflistung von skalaren Variablen werden unterstützt.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [LINQ to Entities](linq-to-entities.md)
