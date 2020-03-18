---
title: 'Vorgehensweise: Deklarieren, Instanziieren und Verwenden von Delegaten (C#-Programmierleitfaden)'
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], declaring and instantiating
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
ms.openlocfilehash: 7ac1d736e19c4dcf1c8408db944505c399762778
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712363"
---
# <a name="how-to-declare-instantiate-and-use-a-delegate-c-programming-guide"></a><span data-ttu-id="83542-102">Vorgehensweise: Deklarieren, Instanziieren und Verwenden von Delegaten (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="83542-102">How to declare, instantiate, and use a Delegate (C# Programming Guide)</span></span>
<span data-ttu-id="83542-103">In C# 1.0 und höher können Delegaten wie im folgenden Beispiel gezeigt deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="83542-103">In C# 1.0 and later, delegates can be declared as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#13)]  
  
 [!code-csharp[csProgGuideDelegates#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#14)]  
  
 <span data-ttu-id="83542-104">C# 2.0 bietet eine einfachere Möglichkeit zum Schreiben der vorangegangenen Deklaration, siehe folgendes Beispiel.</span><span class="sxs-lookup"><span data-stu-id="83542-104">C# 2.0 provides a simpler way to write the previous declaration, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#32)]  
  
 <span data-ttu-id="83542-105">In C# 2.0 und höher ist es außerdem möglich, eine anonyme Methode zum Deklarieren und Initialisieren eines [Delegaten](../../language-reference/builtin-types/reference-types.md) zu verwenden. Dies wird im nachstehenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="83542-105">In C# 2.0 and later, it is also possible to use an anonymous method to declare and initialize a [delegate](../../language-reference/builtin-types/reference-types.md), as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#15)]  
  
 <span data-ttu-id="83542-106">In C# 3.0 und höher können Delegaten auch mithilfe eines Lamdaausdrucks deklariert und instanziiert werden, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="83542-106">In C# 3.0 and later, delegates can also be declared and instantiated by using a lambda expression, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#31)]  
  
 <span data-ttu-id="83542-107">Weitere Informationen finden Sie unter [Lambda Expressions (Lambdaausdrücke)](../statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="83542-107">For more information, see [Lambda Expressions](../statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="83542-108">Im folgenden Beispiel wird verdeutlicht, wie Sie einen Delegaten deklarieren, instanziieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="83542-108">The following example illustrates declaring, instantiating, and using a delegate.</span></span> <span data-ttu-id="83542-109">In der `BookDB`-Klasse ist eine Buchhandlungsdatenbank gekapselt, die eine Buchtiteldatenbank enthält.</span><span class="sxs-lookup"><span data-stu-id="83542-109">The `BookDB` class encapsulates a bookstore database that maintains a database of books.</span></span> <span data-ttu-id="83542-110">Sie stellt eine `ProcessPaperbackBooks`-Methode zur Verfügung, durch die alle Taschenbücher in der Datenbank gefunden werden und für jedes Taschenbuch ein Delegat aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="83542-110">It exposes a method, `ProcessPaperbackBooks`, which finds all paperback books in the database and calls a delegate for each one.</span></span> <span data-ttu-id="83542-111">Der verwendete `delegate`-Typ hat den Namen `ProcessBookDelegate`.</span><span class="sxs-lookup"><span data-stu-id="83542-111">The `delegate` type that is used is named `ProcessBookDelegate`.</span></span> <span data-ttu-id="83542-112">Die `Test`-Klasse verwendet diese Klasse, um die Buchtitel und Durchschnittspreise der Taschenbücher auszugeben.</span><span class="sxs-lookup"><span data-stu-id="83542-112">The `Test` class uses this class to print the titles and average price of the paperback books.</span></span>  
  
 <span data-ttu-id="83542-113">Die Verwendung von Delegaten beinhaltet eine sinnvolle Trennung der Funktionalitäten von Buchhandlungsdatenbank und Clientcode.</span><span class="sxs-lookup"><span data-stu-id="83542-113">The use of delegates promotes good separation of functionality between the bookstore database and the client code.</span></span> <span data-ttu-id="83542-114">Der Clientcode hat keine Kenntnis darüber, wie die Bücher archiviert werden oder wie der Buchhandlungscode Taschenbücher sucht.</span><span class="sxs-lookup"><span data-stu-id="83542-114">The client code has no knowledge of how the books are stored or how the bookstore code finds paperback books.</span></span> <span data-ttu-id="83542-115">Der Buchhandlungscode wiederum hat keine Kenntnis darüber, wie ein Taschenbuchtitel weiterverarbeitet wird, nachdem er gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="83542-115">The bookstore code has no knowledge of what processing is performed on the paperback books after it finds them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83542-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="83542-116">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#12)]  
  
## <a name="robust-programming"></a><span data-ttu-id="83542-117">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="83542-117">Robust Programming</span></span>  
  
- <span data-ttu-id="83542-118">Deklarieren von Delegaten</span><span class="sxs-lookup"><span data-stu-id="83542-118">Declaring a delegate.</span></span>  
  
     <span data-ttu-id="83542-119">Mit der folgenden Anweisung wird ein neuer Delegattyp deklariert.</span><span class="sxs-lookup"><span data-stu-id="83542-119">The following statement declares a new delegate type.</span></span>  
  
     [!code-csharp[csProgGuideDelegates#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#16)]  
  
     <span data-ttu-id="83542-120">Durch die einzelnen Delegattypen werden Anzahl und Typen von Argumenten sowie Rückgabewerte von Methoden beschrieben, die gekapselt werden können.</span><span class="sxs-lookup"><span data-stu-id="83542-120">Each delegate type describes the number and types of the arguments, and the type of the return value of methods that it can encapsulate.</span></span> <span data-ttu-id="83542-121">Sobald neue Argumenttypen benötigt werden oder ein neuer Rückgabewerttyp erforderlich ist, muss ein neuer Delegattyp deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="83542-121">Whenever a new set of argument types or return value type is needed, a new delegate type must be declared.</span></span>  
  
- <span data-ttu-id="83542-122">Instanziieren von Delegaten</span><span class="sxs-lookup"><span data-stu-id="83542-122">Instantiating a delegate.</span></span>  
  
     <span data-ttu-id="83542-123">Nachdem ein Delegattyp deklariert wurde, muss ein Delegatobjekt erstellt und einer bestimmten Methode zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="83542-123">After a delegate type has been declared, a delegate object must be created and associated with a particular method.</span></span> <span data-ttu-id="83542-124">Im vorherigen Beispiel übergeben Sie dazu die `PrintTitle`-Methode an die `ProcessPaperbackBooks`-Methode, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="83542-124">In the previous example, you do this by passing the `PrintTitle` method to the `ProcessPaperbackBooks` method as in the following example:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#17)]  
  
     <span data-ttu-id="83542-125">Hierdurch wird ein neues Delegatobjekt erstellt, das der [statischen](../../language-reference/keywords/static.md) Methode `Test.PrintTitle` zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="83542-125">This creates a new delegate object associated with the [static](../../language-reference/keywords/static.md) method `Test.PrintTitle`.</span></span> <span data-ttu-id="83542-126">Auf ähnliche Weise wird die nicht statische Methode `AddBookToTotal` für das Objekt `totaller` übergeben, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="83542-126">Similarly, the non-static method `AddBookToTotal` on the object `totaller` is passed as in the following example:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#18)]  
  
     <span data-ttu-id="83542-127">In beiden Fällen wird ein neues Delegatobjekt an die `ProcessPaperbackBooks`-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="83542-127">In both cases a new delegate object is passed to the `ProcessPaperbackBooks` method.</span></span>  
  
     <span data-ttu-id="83542-128">Nach der Erstellung eines Delegaten wird die diesem zugeordnete Methode nicht mehr geändert. Delegatobjekte sind unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="83542-128">After a delegate is created, the method it is associated with never changes; delegate objects are immutable.</span></span>  
  
- <span data-ttu-id="83542-129">Aufrufen von Delegaten</span><span class="sxs-lookup"><span data-stu-id="83542-129">Calling a delegate.</span></span>  
  
     <span data-ttu-id="83542-130">Nachdem ein Delegatobjekt erstellt wurde, wird es normalerweise an anderen Code übergeben, durch den der Delegat aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="83542-130">After a delegate object is created, the delegate object is typically passed to other code that will call the delegate.</span></span> <span data-ttu-id="83542-131">Ein Delegatobjekt wird über seinen Namen aufgerufen. Auf den Namen folgen (in Klammern gesetzte) Argumente, die an den Delegaten übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="83542-131">A delegate object is called by using the name of the delegate object, followed by the parenthesized arguments to be passed to the delegate.</span></span> <span data-ttu-id="83542-132">Es folgt ein Beispiel für einen Delegataufruf:</span><span class="sxs-lookup"><span data-stu-id="83542-132">Following is an example of a delegate call:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#19)]  
  
     <span data-ttu-id="83542-133">Ein Delegat kann entweder (wie in diesem Beispiel) synchron oder mithilfe der `BeginInvoke`-Methode und der `EndInvoke`-Methode asynchron aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="83542-133">A delegate can be either called synchronously, as in this example, or asynchronously by using `BeginInvoke` and `EndInvoke` methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83542-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="83542-134">See also</span></span>

- [<span data-ttu-id="83542-135">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="83542-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="83542-136">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="83542-136">Events</span></span>](../events/index.md)
- [<span data-ttu-id="83542-137">Delegaten</span><span class="sxs-lookup"><span data-stu-id="83542-137">Delegates</span></span>](./index.md)
