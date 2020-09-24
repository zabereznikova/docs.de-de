---
title: Kompilierte Abfragen (LINQ to Entities)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8025ba1d-29c7-4407-841b-d5a3bed40b7a
ms.openlocfilehash: b8bed63cda505ad8c26c9c69d880a077053b8d2e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153052"
---
# <a name="compiled-queries--linq-to-entities"></a>Kompilierte Abfragen (LINQ to Entities)

Wenn eine Anwendung im Entity Framework häufig strukturell ähnliche Abfragen ausführt, kann in vielen Fällen die Leistung gesteigert werden, indem die Abfrage einmal kompiliert und anschließend mehrmals mit verschiedenen Parametern ausgeführt wird. So können beispielsweise mithilfe einer Anwendung alle Kunden in einer bestimmten Stadt abgerufen werden, wobei die Stadt zur Laufzeit vom Benutzer in einem Formular festgelegt wird. Für derartige Aufgaben unterstützt LINQ to Entities die Verwendung kompilierter Abfragen.  
  
 Ab .NET Framework 4,5 werden LINQ-Abfragen automatisch zwischengespeichert. Sie können jedoch weiterhin kompilierte LINQ-Abfragen verwenden, um diesen Aufwand in späteren Ausführungen zu reduzieren. Kompilierte Abfragen können effizienter als LINQ-Abfragen sein, die automatisch zwischengespeichert werden. LINQ to Entities Abfragen, die den- `Enumerable.Contains` Operator auf Auflistungen im Arbeitsspeicher anwenden, werden nicht automatisch zwischengespeichert. Außerdem ist die Parametrisierung von in-Memory-Auflistungen in kompilierten LINQ-Abfragen nicht zulässig.  
  
 Die <xref:System.Data.Objects.CompiledQuery>-Klasse ermöglicht das Kompilieren und Zwischenspeichern von Abfragen zur Wiederverwendung. Diese Klasse enthält eine <xref:System.Data.Objects.CompiledQuery>-Methode einer `Compile` mit mehreren Überladungen. Rufen Sie die `Compile`-Methode auf, um einen neuen Delegaten für die Darstellung der kompilierten Abfrage zu erstellen. Die mit einem `Compile` und Parameterwerten ausgestatteten <xref:System.Data.Objects.ObjectContext>-Methoden geben einen Delegat zurück, der ein Ergebnis ausgibt (z. B. eine <xref:System.Linq.IQueryable%601>-Instanz). Die Abfrage wird nur einmal während der ersten Ausführung kompiliert. Die für die Abfrage zur Kompilierungszeit festgelegten Mergeoptionen können später nicht geändert werden. Nachdem die Abfrage kompiliert wurde, können Sie nur Parameter des primitiven Typs angeben, aber Sie können keine Teile der Abfrage ersetzen, die das generierte SQL ändern würden. Weitere Informationen finden Sie unter [EF-mergeoptionen und kompilierte Abfragen](/archive/blogs/dsimmons/ef-merge-options-and-compiled-queries).
  
 Der LINQ to Entities Abfrage Ausdruck, der <xref:System.Data.Objects.CompiledQuery> von der-Methode der- `Compile` Methode kompiliert wird, wird durch einen der generischen Delegaten `Func` wie dargestellt <xref:System.Func%605> . Der Abfrageausdruck kann höchstens einen `ObjectContext`-Parameter, einen Rückgabeparameter und 16 Abfrageparameter kapseln. Sind mehr als 16 Abfrageparameter erforderlich, können Sie eine Struktur erstellen, deren Eigenschaften Abfrageparameter darstellen. Sie können anschließend die Eigenschaften für die Struktur im Abfrageausdruck verwenden, nachdem die Eigenschaften festgelegt wurden.  
  
## <a name="example-1"></a>Beispiel 1  

 Im folgenden Beispiel wird eine Abfrage kompiliert und anschließend aufgerufen, die einen <xref:System.Decimal>-Eingabeparameter akzeptiert und eine Auftragssequenz zurückgibt, in der der fällige Gesamtbetrag 200,00 US-Dollar oder mehr beträgt:  
  
 [!code-csharp[DP L2E Conceptual Examples - compiled query 2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery2)]
 [!code-vb[DP L2E Conceptual Examples - compiled query2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery2)]  
  
## <a name="example-2"></a>Beispiel 2  

 Im folgenden Beispiel wird eine Abfrage kompiliert und anschließend aufgerufen, die eine <xref:System.Data.Objects.ObjectQuery%601>-Instanz zurückgibt:  
  
 [!code-csharp[DP L2E Conceptual Examples - compiled query1_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery1_mq)]
 [!code-vb[DP L2E Conceptual Examples - compiled query1_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery1_mq)]  
  
## <a name="example-3"></a>Beispiel 3  

 Im folgenden Beispiel wird eine Abfrage kompiliert und anschließend aufgerufen, die den Durchschnitt der Produktlistenpreise als <xref:System.Decimal>-Wert zurückgibt:  
  
 [!code-csharp[DP L2E Conceptual Examples - compiled query3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery3_mq)]
 [!code-vb[DP L2E Conceptual Examples - compiled query3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery3_mq)]  
  
## <a name="example-4"></a>Beispiel 4  

 Im folgenden Beispiel wird eine Abfrage kompiliert und anschließend aufgerufen, die einen <xref:System.String> Eingabeparameter akzeptiert. Anschließend wird ein-Wert zurückgegeben, `Contact` dessen e-Mail-Adresse mit der angegebenen Zeichenfolge beginnt:  
  
 [!code-csharp[DP L2E Conceptual Examples - compiled query4_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery4_mq)]
 [!code-vb[DP L2E Conceptual Examples - compiled query4_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery4_mq)]  
  
## <a name="example-5"></a>Beispiel 5  

 Im folgenden Beispiel wird eine Abfrage kompiliert und anschließend aufgerufen, der ein <xref:System.DateTime>-Eingabeparameter und ein <xref:System.Decimal>-Eingabeparameter übergeben wird und die eine Sequenz von Aufträgen zurückgibt, in denen das Auftragsdatum nach dem 3. März 2008 liegt und der fällige Gesamtbetrag weniger als 300,00 Dollar beträgt:  
  
 [!code-csharp[DP L2E Conceptual Examples - compiled query5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery5)]
 [!code-vb[DP L2E Conceptual Examples - compiled query5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery5)]  
  
## <a name="example-6"></a>Beispiel 6  

 Im folgenden Beispiel wird eine Abfrage kompiliert und anschließend aufgerufen, der ein <xref:System.DateTime>-Eingabeparameter übergeben wird und die eine Sequenz von Aufträgen zurückgibt, in denen das Bestelldatum nach dem 8. März 2004 liegt: Diese Abfrage gibt die Bestellinformationen als Sequenz anonymer Typen zurück. Anonyme Typen werden vom Compiler abgeleitet, sodass in der <xref:System.Data.Objects.CompiledQuery>-Methode von `Compile` keine Typparameter angegeben werden können. Der Typ wird in der Abfrage selbst definiert.  
  
 [!code-csharp[DP L2E Conceptual Examples - compiled query6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery6)]
 [!code-vb[DP L2E Conceptual Examples - compiled query6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery6)]  
  
## <a name="example-7"></a>Beispiel 7  

 Im folgenden Beispiel wird eine Abfrage kompiliert und anschließend aufgerufen, die einen Eingabeparameter mit einer benutzerdefinierten Struktur akzeptiert und eine Sequenz von Aufträgen zurückgibt. Die Struktur definiert die Abfrageparameter für Startdatum, Enddatum und den fälligen Gesamtbetrag. Die Abfrage gibt die zwischen dem 3. und 8. März 2003 versendeten Bestellungen mit einem fälligen Gesamtbetrag von über 700,00 US-Dollar zurück.  
  
 [!code-csharp[DP L2E Conceptual Examples - compiled query7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery7)]
 [!code-vb[DP L2E Conceptual Examples - compiled query7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery7)]  
  
 Die Struktur, die die Abfrageparameter definiert:  
  
 [!code-csharp[DP L2E Conceptual Examples - MyParamsStruct](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myparamsstruct)]
 [!code-vb[DP L2E Conceptual Examples - MyParamsStruct](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myparamsstruct)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ADO.NET Entity Framework](../index.md)
- [LINQ to Entities](linq-to-entities.md)
- [EF-mergeoptionen und kompilierte Abfragen](/archive/blogs/dsimmons/ef-merge-options-and-compiled-queries)
