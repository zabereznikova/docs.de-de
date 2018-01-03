---
title: "Hinzufügen von Geschäftslogik durch Verwenden partieller Methoden"
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
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 8c2ff5818aaa22aa51781d09952432fc91a8163c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="adding-business-logic-by-using-partial-methods"></a>Hinzufügen von Geschäftslogik durch Verwenden partieller Methoden
Sie können anpassen, [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] und c# erzeugten Code in Ihrem [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projekte mit *partielle Methoden*. Der von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erzeugte Code definiert Signaturen als einen Teil einer partiellen Methode. Wenn Sie die Methode implementieren möchten, können Sie eine eigene partielle Methode hinzufügen. Wenn Sie keine eigene Implementierung hinzufügen, verwirft der Compiler die partielle Methodensignatur und ruft die Standardmethoden in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] auf.  
  
> [!NOTE]
>  Bei der Verwendung von [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] können mit [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] Validierungen und andere Anpassungen in die Entitätsklasse eingefügt werden.  
  
 Die Standardzuordnung der `Customer`-Klasse in der Beispieldatenbank Northwind enthält beispielsweise die folgende partielle Methode:  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 Sie können auch eine eigene Methode implementieren, indem Sie Code wie den folgenden in Ihre eigene partielle `Customer`-Klasse einfügen:  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 Dieser Ansatz wird normalerweise verwendet, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Überschreiben von Standardmethoden für `Insert`, `Update`, `Delete`, und Eigenschaften während des Lebenszyklus Objektereignisse zu überprüfen.  
  
 Weitere Informationen finden Sie unter [partielle Methoden](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md) ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) oder [Partial (Methode) (C#-Referenz)](~/docs/csharp/language-reference/keywords/partial-method.md) (c#).  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel zeigt zunächst `ExampleClass` nach der möglichen Definition durch ein codeerzeugendes Tool wie SQLMetal. Anschließend wird gezeigt, wie Sie nur eine der beiden Methoden implementieren können.  
  
### <a name="code"></a>Code  
 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel verwendet die Beziehung zwischen der `Shipper`-Entität und der `Order`-Entität. Beachten Sie bei den Methoden die partielle `InsertShipper`-Methode und die partielle `DeleteShipper`-Methode. Diese Methoden überschreiben die standardmäßigen partiellen Methoden von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Zuordnung.  
  
### <a name="code"></a>Code  
 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [Vornehmen und Übergeben von Datenänderungen](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [Anpassen von Insert-, Update- und Delete-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
