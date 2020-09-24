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
# <a name="adding-business-logic-by-using-partial-methods"></a><span data-ttu-id="9e587-102">Hinzufügen von Geschäftslogik durch Verwenden partieller Methoden</span><span class="sxs-lookup"><span data-stu-id="9e587-102">Adding Business Logic By Using Partial Methods</span></span>

<span data-ttu-id="9e587-103">Sie können Visual Basic und c#-generierten Code in Ihren [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projekten anpassen, indem Sie *partielle Methoden*verwenden.</span><span class="sxs-lookup"><span data-stu-id="9e587-103">You can customize Visual Basic and C# generated code in your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects by using *partial methods*.</span></span> <span data-ttu-id="9e587-104">Der von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erzeugte Code definiert Signaturen als einen Teil einer partiellen Methode.</span><span class="sxs-lookup"><span data-stu-id="9e587-104">The code that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates defines signatures as one part of a partial method.</span></span> <span data-ttu-id="9e587-105">Wenn Sie die Methode implementieren möchten, können Sie eine eigene partielle Methode hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9e587-105">If you want to implement the method, you can add your own partial method.</span></span> <span data-ttu-id="9e587-106">Wenn Sie keine eigene Implementierung hinzufügen, verwirft der Compiler die partielle Methodensignatur und ruft die Standardmethoden in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] auf.</span><span class="sxs-lookup"><span data-stu-id="9e587-106">If you do not add your own implementation, the compiler discards the partial methods signature and calls the default methods in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e587-107">Wenn Sie Visual Studio verwenden, können Sie die objektrelationaler Designer verwenden, um Entitäts Klassen Validierung und andere Anpassungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9e587-107">If you are using Visual Studio, you can use the Object Relational Designer to add validation and other customizations to entity classes.</span></span>  
  
 <span data-ttu-id="9e587-108">Die Standardzuordnung der `Customer`-Klasse in der Beispieldatenbank Northwind enthält beispielsweise die folgende partielle Methode:</span><span class="sxs-lookup"><span data-stu-id="9e587-108">For example, the default mapping for the `Customer` class in the Northwind sample database includes the following partial method:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 <span data-ttu-id="9e587-109">Sie können auch eine eigene Methode implementieren, indem Sie Code wie den folgenden in Ihre eigene partielle `Customer`-Klasse einfügen:</span><span class="sxs-lookup"><span data-stu-id="9e587-109">You can implement your own method by adding code such as the following to your own partial `Customer` class:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 <span data-ttu-id="9e587-110">Dieser Ansatz wird in der Regel in verwendet, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] um Standardmethoden für `Insert` , `Update` , `Delete` und zu überschreiben, um Eigenschaften während Objekt Lebenszyklus-Ereignissen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9e587-110">This approach is typically used in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to override default methods for `Insert`, `Update`, `Delete`, and to validate properties during object life-cycle events.</span></span>  
  
 <span data-ttu-id="9e587-111">Weitere Informationen finden Sie unter [partielle Methoden](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) oder [partielle (Methode) (c#-Referenz) (c#](../../../../../csharp/language-reference/keywords/partial-method.md) ).</span><span class="sxs-lookup"><span data-stu-id="9e587-111">For more information, see [Partial Methods](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) or [partial (Method) (C# Reference)](../../../../../csharp/language-reference/keywords/partial-method.md) (C#).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e587-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9e587-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9e587-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e587-113">Description</span></span>  

 <span data-ttu-id="9e587-114">Das folgende Beispiel zeigt zunächst `ExampleClass` nach der möglichen Definition durch ein codeerzeugendes Tool wie SQLMetal. Anschließend wird gezeigt, wie Sie nur eine der beiden Methoden implementieren können.</span><span class="sxs-lookup"><span data-stu-id="9e587-114">The following example shows `ExampleClass` first as it might be defined by a code-generating tool such as SQLMetal, and then how you might implement only one of the two methods.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9e587-115">Code</span><span class="sxs-lookup"><span data-stu-id="9e587-115">Code</span></span>  

 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="9e587-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9e587-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9e587-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e587-117">Description</span></span>  

 <span data-ttu-id="9e587-118">Das folgende Beispiel verwendet die Beziehung zwischen der `Shipper`-Entität und der `Order`-Entität.</span><span class="sxs-lookup"><span data-stu-id="9e587-118">The following example uses the relationship between `Shipper` and `Order` entities.</span></span> <span data-ttu-id="9e587-119">Beachten Sie bei den Methoden die partielle `InsertShipper`-Methode und die partielle `DeleteShipper`-Methode.</span><span class="sxs-lookup"><span data-stu-id="9e587-119">Note among the methods the partial methods, `InsertShipper` and `DeleteShipper`.</span></span> <span data-ttu-id="9e587-120">Diese Methoden überschreiben die von der Zuordnung bereitgestellten standardmäßigen partiellen Methoden [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9e587-120">These methods override the default partial methods supplied by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mapping.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9e587-121">Code</span><span class="sxs-lookup"><span data-stu-id="9e587-121">Code</span></span>  

 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="9e587-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e587-122">See also</span></span>

- [<span data-ttu-id="9e587-123">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="9e587-123">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
- [<span data-ttu-id="9e587-124">Anpassen von Insert-, Update- und Delete-Operationen</span><span class="sxs-lookup"><span data-stu-id="9e587-124">Customizing Insert, Update, and Delete Operations</span></span>](customizing-insert-update-and-delete-operations.md)
