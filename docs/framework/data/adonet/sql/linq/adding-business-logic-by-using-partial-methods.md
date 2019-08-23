---
title: Hinzufügen von Geschäftslogik durch Verwenden partieller Methoden
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
ms.openlocfilehash: e3f82c260a2cab85270a9f33a87eb9a9f04b72c7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964142"
---
# <a name="adding-business-logic-by-using-partial-methods"></a><span data-ttu-id="ea29b-102">Hinzufügen von Geschäftslogik durch Verwenden partieller Methoden</span><span class="sxs-lookup"><span data-stu-id="ea29b-102">Adding Business Logic By Using Partial Methods</span></span>
<span data-ttu-id="ea29b-103">Sie können Visual Basic und C# generierten Code in Ihren [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projekten anpassen, indem Sie *partielle Methoden*verwenden.</span><span class="sxs-lookup"><span data-stu-id="ea29b-103">You can customize Visual Basic and C# generated code in your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects by using *partial methods*.</span></span> <span data-ttu-id="ea29b-104">Der von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erzeugte Code definiert Signaturen als einen Teil einer partiellen Methode.</span><span class="sxs-lookup"><span data-stu-id="ea29b-104">The code that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates defines signatures as one part of a partial method.</span></span> <span data-ttu-id="ea29b-105">Wenn Sie die Methode implementieren möchten, können Sie eine eigene partielle Methode hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ea29b-105">If you want to implement the method, you can add your own partial method.</span></span> <span data-ttu-id="ea29b-106">Wenn Sie keine eigene Implementierung hinzufügen, verwirft der Compiler die partielle Methodensignatur und ruft die Standardmethoden in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] auf.</span><span class="sxs-lookup"><span data-stu-id="ea29b-106">If you do not add your own implementation, the compiler discards the partial methods signature and calls the default methods in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea29b-107">Wenn Sie Visual Studio verwenden, können Sie die objektrelationaler Designer verwenden, um Entitäts Klassen Validierung und andere Anpassungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ea29b-107">If you are using Visual Studio, you can use the Object Relational Designer to add validation and other customizations to entity classes.</span></span>  
  
 <span data-ttu-id="ea29b-108">Die Standardzuordnung der `Customer`-Klasse in der Beispieldatenbank Northwind enthält beispielsweise die folgende partielle Methode:</span><span class="sxs-lookup"><span data-stu-id="ea29b-108">For example, the default mapping for the `Customer` class in the Northwind sample database includes the following partial method:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 <span data-ttu-id="ea29b-109">Sie können auch eine eigene Methode implementieren, indem Sie Code wie den folgenden in Ihre eigene partielle `Customer`-Klasse einfügen:</span><span class="sxs-lookup"><span data-stu-id="ea29b-109">You can implement your own method by adding code such as the following to your own partial `Customer` class:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 <span data-ttu-id="ea29b-110">Dieser Ansatz wird in der Regel [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in verwendet, um Standard `Insert`Methoden `Update`für `Delete`,, und zu überschreiben, um Eigenschaften während Objekt Lebenszyklus-Ereignissen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ea29b-110">This approach is typically used in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to override default methods for `Insert`, `Update`, `Delete`, and to validate properties during object life-cycle events.</span></span>  
  
 <span data-ttu-id="ea29b-111">Weitere Informationen finden Sie unter [partielle Methoden](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) oder [partielle (MethodeC# ) (Referenz)](../../../../../csharp/language-reference/keywords/partial-method.md) (C#).</span><span class="sxs-lookup"><span data-stu-id="ea29b-111">For more information, see [Partial Methods](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) or [partial (Method) (C# Reference)](../../../../../csharp/language-reference/keywords/partial-method.md) (C#).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea29b-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ea29b-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="ea29b-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea29b-113">Description</span></span>  
 <span data-ttu-id="ea29b-114">Das folgende Beispiel zeigt zunächst `ExampleClass` nach der möglichen Definition durch ein codeerzeugendes Tool wie SQLMetal. Anschließend wird gezeigt, wie Sie nur eine der beiden Methoden implementieren können.</span><span class="sxs-lookup"><span data-stu-id="ea29b-114">The following example shows `ExampleClass` first as it might be defined by a code-generating tool such as SQLMetal, and then how you might implement only one of the two methods.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ea29b-115">Code</span><span class="sxs-lookup"><span data-stu-id="ea29b-115">Code</span></span>  
 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="ea29b-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ea29b-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="ea29b-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea29b-117">Description</span></span>  
 <span data-ttu-id="ea29b-118">Das folgende Beispiel verwendet die Beziehung zwischen der `Shipper`-Entität und der `Order`-Entität.</span><span class="sxs-lookup"><span data-stu-id="ea29b-118">The following example uses the relationship between `Shipper` and `Order` entities.</span></span> <span data-ttu-id="ea29b-119">Beachten Sie bei den Methoden die partielle `InsertShipper`-Methode und die partielle `DeleteShipper`-Methode.</span><span class="sxs-lookup"><span data-stu-id="ea29b-119">Note among the methods the partial methods, `InsertShipper` and `DeleteShipper`.</span></span> <span data-ttu-id="ea29b-120">Diese Methoden überschreiben die von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] der Zuordnung bereitgestellten standardmäßigen partiellen Methoden.</span><span class="sxs-lookup"><span data-stu-id="ea29b-120">These methods override the default partial methods supplied by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mapping.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ea29b-121">Code</span><span class="sxs-lookup"><span data-stu-id="ea29b-121">Code</span></span>  
 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ea29b-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea29b-122">See also</span></span>

- [<span data-ttu-id="ea29b-123">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="ea29b-123">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [<span data-ttu-id="ea29b-124">Anpassen von Insert-, Update- und Delete-Operationen</span><span class="sxs-lookup"><span data-stu-id="ea29b-124">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
