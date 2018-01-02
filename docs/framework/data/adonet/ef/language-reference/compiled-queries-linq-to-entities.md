---
title: Kompilierte Abfragen (LINQ to Entities)
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
ms.assetid: 8025ba1d-29c7-4407-841b-d5a3bed40b7a
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 7ca9848d4640fe9d941b3bfc15a7762135871861
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="compiled-queries--linq-to-entities"></a>Kompilierte Abfragen (LINQ to Entities)
Wenn eine Anwendung im Entity Framework häufig strukturell ähnliche Abfragen ausführt, kann in vielen Fällen die Leistung gesteigert werden, indem die Abfrage einmal kompiliert und anschließend mehrmals mit verschiedenen Parametern ausgeführt wird. So können beispielsweise mithilfe einer Anwendung alle Kunden in einer bestimmten Stadt abgerufen werden, wobei die Stadt zur Laufzeit vom Benutzer in einem Formular festgelegt wird. Für derartige Aufgaben unterstützt LINQ to Entities die Verwendung kompilierter Abfragen.  
  
 Ab .NET Framework 4.5 werden LINQ-Abfragen automatisch zwischengespeichert. Sie können jedoch weiterhin kompilierte LINQ-Abfragen verwenden, um diesen Aufwand in späteren Ausführungen zu reduzieren. Kompilierte Abfragen können effizienter als LINQ-Abfragen sein, die automatisch zwischengespeichert werden. Beachten Sie, dass LINQ to Entities-Abfragen, die den `Enumerable.Contains`-Operator auf Auflistungen im Arbeitsspeicher anwenden, nicht automatisch zwischengespeichert werden. Darüber hinaus ist das Parametrisieren von Auflistungen im Arbeitsspeicher in kompilierten LINQ-Abfragen nicht zulässig.  
  
 Die <xref:System.Data.Objects.CompiledQuery>-Klasse ermöglicht das Kompilieren und Zwischenspeichern von Abfragen zur Wiederverwendung. Diese Klasse enthält eine <xref:System.Data.Objects.CompiledQuery>-Methode einer `Compile` mit mehreren Überladungen. Rufen Sie die `Compile`-Methode auf, um einen neuen Delegaten für die Darstellung der kompilierten Abfrage zu erstellen. Die mit einem `Compile` und Parameterwerten ausgestatteten <xref:System.Data.Objects.ObjectContext>-Methoden geben einen Delegat zurück, der ein Ergebnis ausgibt (z. B. eine <xref:System.Linq.IQueryable%601>-Instanz). Die Abfrage wird nur einmal während der ersten Ausführung kompiliert. Die für die Abfrage zur Kompilierungszeit festgelegten Zusammenführungsoptionen können später nicht geändert werden. Nachdem die Abfrage kompiliert ist, können Sie nur Parameter mit einem primitiven Typ angeben. Sie können keine Teile der Abfrage ersetzen, die das generierte SQL ändern. Weitere Informationen finden Sie unter [Entity Framework-Zusammenführungsoptionen und kompilierte Abfragen](http://go.microsoft.com/fwlink/?LinkId=199591)  
  
 Die [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] Abfrageausdruck, der <xref:System.Data.Objects.CompiledQuery>des `Compile` Methode kompiliert wird durch eine der generischen repräsentiert `Func` Delegaten, z. B. <xref:System.Func%605>. Der Abfrageausdruck kann höchstens einen `ObjectContext`-Parameter, einen Rückgabeparameter und 16 Abfrageparameter kapseln. Sind mehr als 16 Abfrageparameter erforderlich, können Sie eine Struktur erstellen, deren Eigenschaften Abfrageparameter darstellen. Sie können anschließend die Eigenschaften für die Struktur im Abfrageausdruck verwenden, nachdem die Eigenschaften festgelegt wurden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Abfrage kompiliert und anschließend aufgerufen, die einen <xref:System.Decimal>-Eingabeparameter akzeptiert und eine Auftragssequenz zurückgibt, in der der fällige Gesamtbetrag 200,00 US-Dollar oder mehr beträgt:  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery2)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery2)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Abfrage kompiliert und anschließend aufgerufen, die eine <xref:System.Data.Objects.ObjectQuery%601>-Instanz zurückgibt:  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery1_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery1_mq)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery1_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery1_mq)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Abfrage kompiliert und anschließend aufgerufen, die den Durchschnitt der Produktlistenpreise als <xref:System.Decimal>-Wert zurückgibt:  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery3_mq)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery3_mq)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Abfrage kompiliert und anschließend aufgerufen, der ein <xref:System.String>-Eingabeparameter übergeben wird und die einen `Contact` zurückgibt, dessen E-Mail-Adresse mit der angegebenen Zeichenfolge beginnt:  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery4_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery4_mq)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery4_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery4_mq)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Abfrage kompiliert und anschließend aufgerufen, der ein <xref:System.DateTime>-Eingabeparameter und ein <xref:System.Decimal>-Eingabeparameter übergeben wird und die eine Sequenz von Aufträgen zurückgibt, in denen das Auftragsdatum nach dem 3. März 2008 liegt und der fällige Gesamtbetrag weniger als 300,00 Dollar beträgt:  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery5)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery5)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Abfrage kompiliert und anschließend aufgerufen, der ein <xref:System.DateTime>-Eingabeparameter übergeben wird und die eine Sequenz von Aufträgen zurückgibt, in denen das Bestelldatum nach dem 8. März 2004 liegt: Diese Abfrage gibt die Bestellinformationen als Sequenz anonymer Typen zurück. Anonyme Typen werden vom Compiler abgeleitet, sodass in der <xref:System.Data.Objects.CompiledQuery>-Methode von `Compile` keine Typenparameter angegeben werden können. Der Typ wird in der Abfrage selbst definiert.  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery6)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery6)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Abfrage kompiliert und anschließend aufgerufen, die einen Eingabeparameter mit einer benutzerdefinierten Struktur akzeptiert und eine Sequenz von Aufträgen zurückgibt. Die Struktur definiert die Abfrageparameter für Startdatum, Enddatum und den fälligen Gesamtbetrag. Die Abfrage gibt die zwischen dem 3. und 8. März 2003 versendeten Bestellungen mit einem fälligen Gesamtbetrag von über 700,00 US-Dollar zurück.  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery7)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery7)]  
  
 Die Struktur, die die Abfrageparameter definiert:  
  
 [!code-csharp[DP L2E Conceptual Examples#MyParamsStruct](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myparamsstruct)]
 [!code-vb[DP L2E Conceptual Examples#MyParamsStruct](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myparamsstruct)]  
  
## <a name="see-also"></a>Siehe auch  
 [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)  
 [LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)  
 [Entity Framework-Zusammenführungsoptionen und kompilierte Abfragen](http://go.microsoft.com/fwlink/?LinkId=199591)
