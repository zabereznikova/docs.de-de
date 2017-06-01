---
title: "Hinzuf&#252;gen von Gesch&#228;ftslogik durch das Verwenden partieller Methoden | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Hinzuf&#252;gen von Gesch&#228;ftslogik durch das Verwenden partieller Methoden
Sie können den von [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] und C\# erzeugten Code in Ihren [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Projekten anpassen, indem Sie *partielle Methoden* verwenden.  Der von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erzeugte Code definiert Signaturen als einen Teil einer partiellen Methode.  Wenn Sie die Methode implementieren möchten, können Sie eine eigene partielle Methode hinzufügen.  Wenn Sie keine eigene Implementierung hinzufügen, verwirft der Compiler die partielle Methodensignatur und ruft die Standardmethoden in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] auf.  
  
> [!NOTE]
>  Bei der Verwendung von [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] können mit [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] Validierungen und andere Anpassungen in die Entitätsklasse eingefügt werden.  
  
 Die Standardzuordnung der `Customer`\-Klasse in der Beispieldatenbank Northwind enthält beispielsweise die folgende partielle Methode:  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 Sie können auch eine eigene Methode implementieren, indem Sie Code wie den folgenden in Ihre eigene partielle `Customer`\-Klasse einfügen:  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 Dieser Ansatz wird normalerweise in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwendet, um Standardmethoden für `Insert`, `Update` und `Delete` zu überschreiben und Eigenschaften während der Lebenszyklusereignissen von Objekten zu validieren.  
  
 Weitere Informationen finden Sie unter [Partial Methods](../Topic/Partial%20Methods%20\(Visual%20Basic\).md) \([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]\) oder [partial \(Methode\) \(C\#\-Referenz\)](../Topic/partial%20\(Method\)%20\(C%23%20Reference\).md) \(C\#\-Referenz\).  
  
## Beispiel  
  
### Beschreibung  
 Das folgende Beispiel zeigt zunächst `ExampleClass` nach der möglichen Definition durch ein codeerzeugendes Tool wie SQLMetal. Anschließend wird gezeigt, wie Sie nur eine der beiden Methoden implementieren können.  
  
### Code  
 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## Beispiel  
  
### Beschreibung  
 Das folgende Beispiel verwendet die Beziehung zwischen der `Shipper`\-Entität und der `Order`\-Entität.  Beachten Sie bei den Methoden die partielle `InsertShipper`\-Methode und die partielle `DeleteShipper`\-Methode.  Diese Methoden überschreiben die standardmäßigen partiellen Methoden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Zuordnung.  
  
### Code  
 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## Siehe auch  
 [Vornehmen und Übergeben von Datenänderungen](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)   
 [Anpassen von Insert\-, Update\- und Delete\-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)