---
title: Hinzufügen von Geschäftslogik durch Verwenden partieller Methoden
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
ms.openlocfilehash: 9ad3329c621b8bf8eaa0fd5f986ac7e8cff97d9e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156159"
---
# <a name="adding-business-logic-by-using-partial-methods"></a>Hinzufügen von Geschäftslogik durch Verwenden partieller Methoden

Sie können Visual Basic und c#-generierten Code in Ihren [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projekten anpassen, indem Sie *partielle Methoden*verwenden. Der von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erzeugte Code definiert Signaturen als einen Teil einer partiellen Methode. Wenn Sie die Methode implementieren möchten, können Sie eine eigene partielle Methode hinzufügen. Wenn Sie keine eigene Implementierung hinzufügen, verwirft der Compiler die partielle Methodensignatur und ruft die Standardmethoden in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] auf.  
  
> [!NOTE]
> Wenn Sie Visual Studio verwenden, können Sie die objektrelationaler Designer verwenden, um Entitäts Klassen Validierung und andere Anpassungen hinzuzufügen.  
  
 Die Standardzuordnung der `Customer`-Klasse in der Beispieldatenbank Northwind enthält beispielsweise die folgende partielle Methode:  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 Sie können auch eine eigene Methode implementieren, indem Sie Code wie den folgenden in Ihre eigene partielle `Customer`-Klasse einfügen:  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 Dieser Ansatz wird in der Regel in verwendet, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] um Standardmethoden für `Insert` , `Update` , `Delete` und zu überschreiben, um Eigenschaften während Objekt Lebenszyklus-Ereignissen zu überprüfen.  
  
 Weitere Informationen finden Sie unter [partielle Methoden](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) oder [partielle (Methode) (c#-Referenz) (c#](../../../../../csharp/language-reference/keywords/partial-method.md) ).  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  

 Das folgende Beispiel zeigt zunächst `ExampleClass` nach der möglichen Definition durch ein codeerzeugendes Tool wie SQLMetal. Anschließend wird gezeigt, wie Sie nur eine der beiden Methoden implementieren können.  
  
### <a name="code"></a>Code  

 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  

 Das folgende Beispiel verwendet die Beziehung zwischen der `Shipper`-Entität und der `Order`-Entität. Beachten Sie bei den Methoden die partielle `InsertShipper`-Methode und die partielle `DeleteShipper`-Methode. Diese Methoden überschreiben die von der Zuordnung bereitgestellten standardmäßigen partiellen Methoden [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .  
  
### <a name="code"></a>Code  

 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Vornehmen und Übergeben von Datenänderungen](making-and-submitting-data-changes.md)
- [Anpassen von Insert-, Update- und Delete-Operationen](customizing-insert-update-and-delete-operations.md)
