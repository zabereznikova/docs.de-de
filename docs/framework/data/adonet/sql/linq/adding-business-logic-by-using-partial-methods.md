---
title: Hinzufügen von Geschäftslogik durch Verwenden partieller Methoden
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
ms.openlocfilehash: db18c48d697ae79f8c33c1674544f81cdd1c426a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361450"
---
# <a name="adding-business-logic-by-using-partial-methods"></a><span data-ttu-id="e0a2d-102">Hinzufügen von Geschäftslogik durch Verwenden partieller Methoden</span><span class="sxs-lookup"><span data-stu-id="e0a2d-102">Adding Business Logic By Using Partial Methods</span></span>
<span data-ttu-id="e0a2d-103">Sie können anpassen, Visual Basic- und c# erzeugten Code in Ihrem [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projekte mit *partielle Methoden*.</span><span class="sxs-lookup"><span data-stu-id="e0a2d-103">You can customize Visual Basic and C# generated code in your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects by using *partial methods*.</span></span> <span data-ttu-id="e0a2d-104">Der von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erzeugte Code definiert Signaturen als einen Teil einer partiellen Methode.</span><span class="sxs-lookup"><span data-stu-id="e0a2d-104">The code that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates defines signatures as one part of a partial method.</span></span> <span data-ttu-id="e0a2d-105">Wenn Sie die Methode implementieren möchten, können Sie eine eigene partielle Methode hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e0a2d-105">If you want to implement the method, you can add your own partial method.</span></span> <span data-ttu-id="e0a2d-106">Wenn Sie keine eigene Implementierung hinzufügen, verwirft der Compiler die partielle Methodensignatur und ruft die Standardmethoden in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] auf.</span><span class="sxs-lookup"><span data-stu-id="e0a2d-106">If you do not add your own implementation, the compiler discards the partial methods signature and calls the default methods in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0a2d-107">Wenn Sie Visual Studio verwenden, können Sie mithilfe der [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] Entitätsklassen Validierungen und andere Anpassungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="e0a2d-107">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to add validation and other customizations to entity classes.</span></span>  
  
 <span data-ttu-id="e0a2d-108">Die Standardzuordnung der `Customer`-Klasse in der Beispieldatenbank Northwind enthält beispielsweise die folgende partielle Methode:</span><span class="sxs-lookup"><span data-stu-id="e0a2d-108">For example, the default mapping for the `Customer` class in the Northwind sample database includes the following partial method:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 <span data-ttu-id="e0a2d-109">Sie können auch eine eigene Methode implementieren, indem Sie Code wie den folgenden in Ihre eigene partielle `Customer`-Klasse einfügen:</span><span class="sxs-lookup"><span data-stu-id="e0a2d-109">You can implement your own method by adding code such as the following to your own partial `Customer` class:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 <span data-ttu-id="e0a2d-110">Dieser Ansatz wird normalerweise verwendet, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Überschreiben von Standardmethoden für `Insert`, `Update`, `Delete`, und Eigenschaften während des Lebenszyklus Objektereignisse zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e0a2d-110">This approach is typically used in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to override default methods for `Insert`, `Update`, `Delete`, and to validate properties during object life-cycle events.</span></span>  
  
 <span data-ttu-id="e0a2d-111">Weitere Informationen finden Sie unter [partielle Methoden](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) oder [Partial (Methode) (C#-Referenz)](~/docs/csharp/language-reference/keywords/partial-method.md) (c#).</span><span class="sxs-lookup"><span data-stu-id="e0a2d-111">For more information, see [Partial Methods](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) or [partial (Method) (C# Reference)](~/docs/csharp/language-reference/keywords/partial-method.md) (C#).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0a2d-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0a2d-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="e0a2d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0a2d-113">Description</span></span>  
 <span data-ttu-id="e0a2d-114">Das folgende Beispiel zeigt zunächst `ExampleClass` nach der möglichen Definition durch ein codeerzeugendes Tool wie SQLMetal. Anschließend wird gezeigt, wie Sie nur eine der beiden Methoden implementieren können.</span><span class="sxs-lookup"><span data-stu-id="e0a2d-114">The following example shows `ExampleClass` first as it might be defined by a code-generating tool such as SQLMetal, and then how you might implement only one of the two methods.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e0a2d-115">Code</span><span class="sxs-lookup"><span data-stu-id="e0a2d-115">Code</span></span>  
 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="e0a2d-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0a2d-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="e0a2d-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0a2d-117">Description</span></span>  
 <span data-ttu-id="e0a2d-118">Das folgende Beispiel verwendet die Beziehung zwischen der `Shipper`-Entität und der `Order`-Entität.</span><span class="sxs-lookup"><span data-stu-id="e0a2d-118">The following example uses the relationship between `Shipper` and `Order` entities.</span></span> <span data-ttu-id="e0a2d-119">Beachten Sie bei den Methoden die partielle `InsertShipper`-Methode und die partielle `DeleteShipper`-Methode.</span><span class="sxs-lookup"><span data-stu-id="e0a2d-119">Note among the methods the partial methods, `InsertShipper` and `DeleteShipper`.</span></span> <span data-ttu-id="e0a2d-120">Diese Methoden überschreiben die standardmäßigen partiellen Methoden von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="e0a2d-120">These methods override the default partial methods supplied by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mapping.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e0a2d-121">Code</span><span class="sxs-lookup"><span data-stu-id="e0a2d-121">Code</span></span>  
 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e0a2d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0a2d-122">See Also</span></span>  
 [<span data-ttu-id="e0a2d-123">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="e0a2d-123">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [<span data-ttu-id="e0a2d-124">Anpassen von Insert-, Update- und Delete-Operationen</span><span class="sxs-lookup"><span data-stu-id="e0a2d-124">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
