---
title: 'Gewusst wie: Deklarieren, Instanziieren und Verwenden von Delegaten (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- delegates [C#], declaring and instantiating
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5a16fe4c627989f701ba523769cd87839d074849
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-declare-instantiate-and-use-a-delegate-c-programming-guide"></a><span data-ttu-id="1a11f-102">Gewusst wie: Deklarieren, Instanziieren und Verwenden von Delegaten (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="1a11f-102">How to: Declare, Instantiate, and Use a Delegate (C# Programming Guide)</span></span>
<span data-ttu-id="1a11f-103">In C# 1.0 und höher können Delegaten wie im folgenden Beispiel gezeigt deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="1a11f-103">In C# 1.0 and later, delegates can be declared as shown in the following example.</span></span>  
  
 <span data-ttu-id="1a11f-104">[!code-cs[csProgGuideDelegates#13](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a11f-104">[!code-cs[csProgGuideDelegates#13](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_1.cs)]</span></span>  
  
 <span data-ttu-id="1a11f-105">[!code-cs[csProgGuideDelegates#14](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a11f-105">[!code-cs[csProgGuideDelegates#14](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_2.cs)]</span></span>  
  
 <span data-ttu-id="1a11f-106">C# 2.0 bietet eine einfachere Möglichkeit zum Schreiben der vorangegangenen Deklaration, siehe folgendes Beispiel.</span><span class="sxs-lookup"><span data-stu-id="1a11f-106">C# 2.0 provides a simpler way to write the previous declaration, as shown in the following example.</span></span>  
  
 <span data-ttu-id="1a11f-107">[!code-cs[csProgGuideDelegates#32](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a11f-107">[!code-cs[csProgGuideDelegates#32](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_3.cs)]</span></span>  
  
 <span data-ttu-id="1a11f-108">In C# 2.0 und höher ist es außerdem möglich, eine anonyme Methode zum Deklarieren und Initialisieren eines [Delegaten](../../../csharp/language-reference/keywords/delegate.md) zu verwenden. Dies wird im nachstehenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a11f-108">In C# 2.0 and later, it is also possible to use an anonymous method to declare and initialize a [delegate](../../../csharp/language-reference/keywords/delegate.md), as shown in the following example.</span></span>  
  
 <span data-ttu-id="1a11f-109">[!code-cs[csProgGuideDelegates#15](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a11f-109">[!code-cs[csProgGuideDelegates#15](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_4.cs)]</span></span>  
  
 <span data-ttu-id="1a11f-110">In C# 3.0 und höher können Delegaten auch mithilfe eines Lamdaausdrucks deklariert und instanziiert werden, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1a11f-110">In C# 3.0 and later, delegates can also be declared and instantiated by using a lambda expression, as shown in the following example.</span></span>  
  
 <span data-ttu-id="1a11f-111">[!code-cs[csProgGuideDelegates#31](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a11f-111">[!code-cs[csProgGuideDelegates#31](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_5.cs)]</span></span>  
  
 <span data-ttu-id="1a11f-112">Weitere Informationen finden Sie unter [Lambdaausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="1a11f-112">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="1a11f-113">Im folgenden Beispiel wird verdeutlicht, wie Sie einen Delegaten deklarieren, instanziieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a11f-113">The following example illustrates declaring, instantiating, and using a delegate.</span></span> <span data-ttu-id="1a11f-114">In der `BookDB`-Klasse ist eine Buchhandlungsdatenbank gekapselt, die eine Buchtiteldatenbank enthält.</span><span class="sxs-lookup"><span data-stu-id="1a11f-114">The `BookDB` class encapsulates a bookstore database that maintains a database of books.</span></span> <span data-ttu-id="1a11f-115">Sie stellt eine `ProcessPaperbackBooks`-Methode zur Verfügung, durch die alle Taschenbücher in der Datenbank gefunden werden und für jedes Taschenbuch ein Delegat aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="1a11f-115">It exposes a method, `ProcessPaperbackBooks`, which finds all paperback books in the database and calls a delegate for each one.</span></span> <span data-ttu-id="1a11f-116">Der verwendete `delegate`-Typ hat den Namen `ProcessBookDelegate`.</span><span class="sxs-lookup"><span data-stu-id="1a11f-116">The `delegate` type that is used is named `ProcessBookDelegate`.</span></span> <span data-ttu-id="1a11f-117">Die `Test`-Klasse verwendet diese Klasse, um die Buchtitel und Durchschnittspreise der Taschenbücher auszugeben.</span><span class="sxs-lookup"><span data-stu-id="1a11f-117">The `Test` class uses this class to print the titles and average price of the paperback books.</span></span>  
  
 <span data-ttu-id="1a11f-118">Die Verwendung von Delegaten beinhaltet eine sinnvolle Trennung der Funktionalitäten von Buchhandlungsdatenbank und Clientcode.</span><span class="sxs-lookup"><span data-stu-id="1a11f-118">The use of delegates promotes good separation of functionality between the bookstore database and the client code.</span></span> <span data-ttu-id="1a11f-119">Der Clientcode hat keine Kenntnis darüber, wie die Bücher archiviert werden oder wie der Buchhandlungscode Taschenbücher sucht.</span><span class="sxs-lookup"><span data-stu-id="1a11f-119">The client code has no knowledge of how the books are stored or how the bookstore code finds paperback books.</span></span> <span data-ttu-id="1a11f-120">Der Buchhandlungscode wiederum hat keine Kenntnis darüber, wie ein Taschenbuchtitel weiterverarbeitet wird, nachdem er gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="1a11f-120">The bookstore code has no knowledge of what processing is performed on the paperback books after it finds them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a11f-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1a11f-121">Example</span></span>  
 <span data-ttu-id="1a11f-122">[!code-cs[csProgGuideDelegates#12](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a11f-122">[!code-cs[csProgGuideDelegates#12](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_6.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="1a11f-123">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="1a11f-123">Robust Programming</span></span>  
  
-   <span data-ttu-id="1a11f-124">Deklarieren von Delegaten</span><span class="sxs-lookup"><span data-stu-id="1a11f-124">Declaring a delegate.</span></span>  
  
     <span data-ttu-id="1a11f-125">Mit der folgenden Anweisung wird ein neuer Delegattyp deklariert.</span><span class="sxs-lookup"><span data-stu-id="1a11f-125">The following statement declares a new delegate type.</span></span>  
  
     <span data-ttu-id="1a11f-126">[!code-cs[csProgGuideDelegates#16](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a11f-126">[!code-cs[csProgGuideDelegates#16](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_7.cs)]</span></span>  
  
     <span data-ttu-id="1a11f-127">Durch die einzelnen Delegattypen werden Anzahl und Typen von Argumenten sowie Rückgabewerte von Methoden beschrieben, die gekapselt werden können.</span><span class="sxs-lookup"><span data-stu-id="1a11f-127">Each delegate type describes the number and types of the arguments, and the type of the return value of methods that it can encapsulate.</span></span> <span data-ttu-id="1a11f-128">Sobald neue Argumenttypen benötigt werden oder ein neuer Rückgabewerttyp erforderlich ist, muss ein neuer Delegattyp deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="1a11f-128">Whenever a new set of argument types or return value type is needed, a new delegate type must be declared.</span></span>  
  
-   <span data-ttu-id="1a11f-129">Instanziieren von Delegaten</span><span class="sxs-lookup"><span data-stu-id="1a11f-129">Instantiating a delegate.</span></span>  
  
     <span data-ttu-id="1a11f-130">Nachdem ein Delegattyp deklariert wurde, muss ein Delegatobjekt erstellt und einer bestimmten Methode zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="1a11f-130">After a delegate type has been declared, a delegate object must be created and associated with a particular method.</span></span> <span data-ttu-id="1a11f-131">Im vorherigen Beispiel übergeben Sie dazu die `PrintTitle`-Methode an die `ProcessPaperbackBooks`-Methode, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1a11f-131">In the previous example, you do this by passing the `PrintTitle` method to the `ProcessPaperbackBooks` method as in the following example:</span></span>  
  
     <span data-ttu-id="1a11f-132">[!code-cs[csProgGuideDelegates#17](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a11f-132">[!code-cs[csProgGuideDelegates#17](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_8.cs)]</span></span>  
  
     <span data-ttu-id="1a11f-133">Hierdurch wird ein neues Delegatobjekt erstellt, das der [statischen](../../../csharp/language-reference/keywords/static.md) Methode `Test.PrintTitle` zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1a11f-133">This creates a new delegate object associated with the [static](../../../csharp/language-reference/keywords/static.md) method `Test.PrintTitle`.</span></span> <span data-ttu-id="1a11f-134">Auf ähnliche Weise wird die nicht statische Methode `AddBookToTotal` für das Objekt `totaller` übergeben, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1a11f-134">Similarly, the non-static method `AddBookToTotal` on the object `totaller` is passed as in the following example:</span></span>  
  
     <span data-ttu-id="1a11f-135">[!code-cs[csProgGuideDelegates#18](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a11f-135">[!code-cs[csProgGuideDelegates#18](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_9.cs)]</span></span>  
  
     <span data-ttu-id="1a11f-136">In beiden Fällen wird ein neues Delegatobjekt an die `ProcessPaperbackBooks`-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="1a11f-136">In both cases a new delegate object is passed to the `ProcessPaperbackBooks` method.</span></span>  
  
     <span data-ttu-id="1a11f-137">Nach der Erstellung eines Delegaten wird die diesem zugeordnete Methode nicht mehr geändert. Delegatobjekte sind unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="1a11f-137">After a delegate is created, the method it is associated with never changes; delegate objects are immutable.</span></span>  
  
-   <span data-ttu-id="1a11f-138">Aufrufen von Delegaten</span><span class="sxs-lookup"><span data-stu-id="1a11f-138">Calling a delegate.</span></span>  
  
     <span data-ttu-id="1a11f-139">Nachdem ein Delegatobjekt erstellt wurde, wird es normalerweise an anderen Code übergeben, durch den der Delegat aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="1a11f-139">After a delegate object is created, the delegate object is typically passed to other code that will call the delegate.</span></span> <span data-ttu-id="1a11f-140">Ein Delegatobjekt wird über seinen Namen aufgerufen. Auf den Namen folgen (in Klammern gesetzte) Argumente, die an den Delegaten übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1a11f-140">A delegate object is called by using the name of the delegate object, followed by the parenthesized arguments to be passed to the delegate.</span></span> <span data-ttu-id="1a11f-141">Es folgt ein Beispiel für einen Delegataufruf:</span><span class="sxs-lookup"><span data-stu-id="1a11f-141">Following is an example of a delegate call:</span></span>  
  
     <span data-ttu-id="1a11f-142">[!code-cs[csProgGuideDelegates#19](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a11f-142">[!code-cs[csProgGuideDelegates#19](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_10.cs)]</span></span>  
  
     <span data-ttu-id="1a11f-143">Ein Delegat kann entweder (wie in diesem Beispiel) synchron oder mithilfe der `BeginInvoke`-Methode und der `EndInvoke`-Methode asynchron aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1a11f-143">A delegate can be either called synchronously, as in this example, or asynchronously by using `BeginInvoke` and `EndInvoke` methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a11f-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a11f-144">See Also</span></span>  
 <span data-ttu-id="1a11f-145">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1a11f-145">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1a11f-146">[Ereignisse](../../../csharp/programming-guide/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="1a11f-146">[Events](../../../csharp/programming-guide/events/index.md) </span></span>  
 [<span data-ttu-id="1a11f-147">Delegaten</span><span class="sxs-lookup"><span data-stu-id="1a11f-147">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)

