---
title: "Beispiele für die Abfrageausdruckssyntax: Joinoperatoren"
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
ms.assetid: 343e8dda-70b2-409d-9334-ce9a880c3cea
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bea82d01c2eea5e9aa892f9ab7cee95944329849
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="query-expression-syntax-examples-join-operators"></a>Beispiele für die Abfrageausdruckssyntax: Joinoperatoren
Das Verknüpfen (JOIN) ist eine wichtige Operation bei Abfragen von Daten aus Datenquellen, bei denen es untereinander keine navigierbaren Beziehungen, wie Tabellen in relationalen Datenbanken, gibt. Bei einer JOIN-Operation für zwei Datenquellen werden Objekte in einer Datenquelle mit Objekten in der anderen Datenquelle, die über ein gemeinsames Attribut verfügen, miteinander verknüpft. Weitere Informationen finden Sie unter [Übersicht über Standard Standardabfrageoperatoren](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).  
  
 In den Beispielen in diesem Thema wird gezeigt, wie mithilfe der <xref:System.Linq.Enumerable.GroupJoin%2A> und <xref:System.Linq.Enumerable.Join%2A> Methoden zum Abfragen der [AdventureWorks Sales-Modell](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) mithilfe der Abfrageausdruckssyntax Abfragen. Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.  
  
 In den Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a>GroupJoin  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Linq.Enumerable.GroupJoin%2A> zwischen der SalesOrderHeader-Tabelle und der SalesOrderDetail-Tabelle durchgeführt, um nach der Anzahl der Aufträge pro Kunde zu suchen. Eine Gruppenverknüpfung ist das Äquivalent zu einer linken äußeren Verknüpfung, die jedes Element der ersten (linken) Datenquelle zurückgibt, selbst wenn die andere Datenquelle keine zugehörigen Elemente enthält.  
  
 [!code-csharp[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Linq.Enumerable.GroupJoin%2A> zwischen der Contact-Tabelle und der SalesOrderHeader-Tabelle durchgeführt, um nach der Anzahl der Aufträge pro Kontakt zu suchen. Die Anzahl der Aufträge und die IDs für alle Kontakte werden angezeigt.  
  
 [!code-csharp[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Linq.Enumerable.GroupJoin%2A> zwischen der Contact-Tabelle und der SalesOrderHeader-Tabelle durchgeführt. Eine Gruppenverknüpfung ist das Äquivalent zu einer linken äußeren Verknüpfung, die jedes Element der ersten (linken) Datenquelle zurückgibt, selbst wenn die andere Datenquelle keine zugehörigen Elemente enthält.  
  
 [!code-csharp[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin)]  
  
## <a name="join"></a>Join  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die SalesOrderHeader-Tabelle und die SalesOrderDetail-Tabelle miteinander verknüpft, um die Onlinebestellungen für den Monat August abzurufen.  
  
 [!code-csharp[DP L2E Examples#Join](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#join)]
 [!code-vb[DP L2E Examples#Join](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a>Siehe auch  
 [Abfragen in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
