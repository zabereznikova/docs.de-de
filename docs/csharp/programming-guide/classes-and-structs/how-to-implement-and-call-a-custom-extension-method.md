---
title: 'Gewusst wie: Implementieren und Aufrufen einer benutzerdefinierten Erweiterungsmethode – C#-Programmierhandbuch'
description: Informationen zum Implementieren von Erweiterungsmethoden für einen .NET-Typ Clientcode kann Ihre Methoden verwenden, indem ein Verweis auf eine DLL und eine using-Anweisung hinzugefügt werden.
ms.date: 07/20/2015
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
ms.openlocfilehash: de4cc423e1823351305a23f331b082aa66add1a6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190435"
---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a><span data-ttu-id="70bf0-104">Gewusst wie: Implementieren und Aufrufen einer benutzerdefinierten Erweiterungsmethode (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="70bf0-104">How to implement and call a custom extension method (C# Programming Guide)</span></span>

<span data-ttu-id="70bf0-105">In diesem Artikel wird das Implementieren Ihrer eigenen Erweiterungsmethoden für jeden .NET-Typ behandelt.</span><span class="sxs-lookup"><span data-stu-id="70bf0-105">This topic shows how to implement your own extension methods for any .NET type.</span></span> <span data-ttu-id="70bf0-106">Der Clientcode kann Ihre Erweiterungsmethoden verwenden, wenn ein Verweis auf die DLL, die die Methoden enthält, und eine [using](../../language-reference/keywords/using-directive.md)-Direktive hinzugefügt werden, die den Namespace angibt, in dem die Erweiterungsmethoden definiert sind.</span><span class="sxs-lookup"><span data-stu-id="70bf0-106">Client code can use your extension methods by adding a reference to the DLL that contains them, and adding a [using](../../language-reference/keywords/using-directive.md) directive that specifies the namespace in which the extension methods are defined.</span></span>  
  
## <a name="to-define-and-call-the-extension-method"></a><span data-ttu-id="70bf0-107">So definieren Sie die Erweiterungsmethode und rufen Sie auf</span><span class="sxs-lookup"><span data-stu-id="70bf0-107">To define and call the extension method</span></span>  
  
1. <span data-ttu-id="70bf0-108">Definieren Sie eine statische [Klasse](./static-classes-and-static-class-members.md), die die Erweiterungsmethode enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="70bf0-108">Define a static [class](./static-classes-and-static-class-members.md) to contain the extension method.</span></span>  
  
     <span data-ttu-id="70bf0-109">Die Klasse muss für den Clientcode sichtbar sein.</span><span class="sxs-lookup"><span data-stu-id="70bf0-109">The class must be visible to client code.</span></span> <span data-ttu-id="70bf0-110">Weitere Informationen finden Sie unter [Zugriffsmodifizierer](./access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="70bf0-110">For more information about accessibility rules, see [Access Modifiers](./access-modifiers.md).</span></span>  
  
2. <span data-ttu-id="70bf0-111">Implementieren Sie die Erweiterungsmethode als statische Methode mit mindestens die gleichen Sichtbarkeit wie die enthaltende Klasse.</span><span class="sxs-lookup"><span data-stu-id="70bf0-111">Implement the extension method as a static method with at least the same visibility as the containing class.</span></span>  
  
3. <span data-ttu-id="70bf0-112">Der erste Parameter der Methode gibt den Typ an, auf den die Methode angewendet wird. Ihm muss ein [this](../../language-reference/keywords/this.md)-Modifizierer vorangehen.</span><span class="sxs-lookup"><span data-stu-id="70bf0-112">The first parameter of the method specifies the type that the method operates on; it must be preceded with the [this](../../language-reference/keywords/this.md) modifier.</span></span>  
  
4. <span data-ttu-id="70bf0-113">Fügen Sie im aufrufenden Code eine `using`-Direktive hinzu, um den [Namespace](../../language-reference/keywords/namespace.md) anzugeben, der die Erweiterungsklassemethode enthält.</span><span class="sxs-lookup"><span data-stu-id="70bf0-113">In the calling code, add a `using` directive to specify the [namespace](../../language-reference/keywords/namespace.md) that contains the extension method class.</span></span>  
  
5. <span data-ttu-id="70bf0-114">Rufen Sie die Methoden auf, als wären sie Instanzmethoden für den Typ.</span><span class="sxs-lookup"><span data-stu-id="70bf0-114">Call the methods as if they were instance methods on the type.</span></span>  
  
     <span data-ttu-id="70bf0-115">Beachten Sie, dass der erste Parameter nicht durch einen Aufruf von Code angegeben wird, da er den Typ darstellt, auf den der Operator angewendet wird, und der Compiler bereits den Typ des Objekts kennt.</span><span class="sxs-lookup"><span data-stu-id="70bf0-115">Note that the first parameter is not specified by calling code because it represents the type on which the operator is being applied, and the compiler already knows the type of your object.</span></span> <span data-ttu-id="70bf0-116">Sie müssen nur Argumente für Parameter 2 bis `n` bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="70bf0-116">You only have to provide arguments for parameters 2 through `n`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70bf0-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70bf0-117">Example</span></span>  

 <span data-ttu-id="70bf0-118">Im folgenden Beispiel wird eine Erweiterungsmethode namens `WordCount` in der `CustomExtensions.StringExtension`-Klasse implementiert.</span><span class="sxs-lookup"><span data-stu-id="70bf0-118">The following example implements an extension method named `WordCount` in the `CustomExtensions.StringExtension` class.</span></span> <span data-ttu-id="70bf0-119">Die Methode wird auf die <xref:System.String>-Klasse angewendet, die als erster Methodenparameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="70bf0-119">The method operates on the <xref:System.String> class, which is specified as the first method parameter.</span></span> <span data-ttu-id="70bf0-120">Der `CustomExtensions`-Namespace wird in den Anwendungsnamespace importiert, und die Methode wird in der `Main`-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="70bf0-120">The `CustomExtensions` namespace is imported into the application namespace, and the method is called inside the `Main` method.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#1)]  
  
## <a name="net-security"></a><span data-ttu-id="70bf0-121">.NET-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="70bf0-121">.NET Security</span></span>  

 <span data-ttu-id="70bf0-122">Erweiterungsmethoden enthalten keine speziellen Sicherheitslücken.</span><span class="sxs-lookup"><span data-stu-id="70bf0-122">Extension methods present no specific security vulnerabilities.</span></span> <span data-ttu-id="70bf0-123">Sie können nicht dazu verwendet werden, die Identität vorhandener Methoden für einen Typ anzunehmen, da alle Namenskonflikte zugunsten der Instanz oder eine statische Methode gelöst werden, die der Typ selbst definiert.</span><span class="sxs-lookup"><span data-stu-id="70bf0-123">They can never be used to impersonate existing methods on a type, because all name collisions are resolved in favor of the instance or static method defined by the type itself.</span></span> <span data-ttu-id="70bf0-124">Erweiterungsmethoden können in der erweiterten Klasse nicht auf private Daten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="70bf0-124">Extension methods cannot access any private data in the extended class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70bf0-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70bf0-125">See also</span></span>

- [<span data-ttu-id="70bf0-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="70bf0-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="70bf0-127">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="70bf0-127">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="70bf0-128">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="70bf0-128">LINQ (Language-Integrated Query)</span></span>](../../linq/linq-in-csharp.md)
- [<span data-ttu-id="70bf0-129">Statische Klassen und statische Klassenmember</span><span class="sxs-lookup"><span data-stu-id="70bf0-129">Static Classes and Static Class Members</span></span>](./static-classes-and-static-class-members.md)
- [<span data-ttu-id="70bf0-130">protected</span><span class="sxs-lookup"><span data-stu-id="70bf0-130">protected</span></span>](../../language-reference/keywords/protected.md)
- [<span data-ttu-id="70bf0-131">internal</span><span class="sxs-lookup"><span data-stu-id="70bf0-131">internal</span></span>](../../language-reference/keywords/internal.md)
- [<span data-ttu-id="70bf0-132">public</span><span class="sxs-lookup"><span data-stu-id="70bf0-132">public</span></span>](../../language-reference/keywords/public.md)
- [<span data-ttu-id="70bf0-133">this</span><span class="sxs-lookup"><span data-stu-id="70bf0-133">this</span></span>](../../language-reference/keywords/this.md)
- [<span data-ttu-id="70bf0-134">namespace</span><span class="sxs-lookup"><span data-stu-id="70bf0-134">namespace</span></span>](../../language-reference/keywords/namespace.md)
