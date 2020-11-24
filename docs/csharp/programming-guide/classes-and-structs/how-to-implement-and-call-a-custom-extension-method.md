---
title: 'Gewusst wie: Implementieren und Aufrufen einer benutzerdefinierten Erweiterungsmethode – C#-Programmierhandbuch'
description: Informationen zum Implementieren von Erweiterungsmethoden für einen .NET-Typ Clientcode kann Ihre Methoden verwenden, indem ein Verweis auf eine DLL und eine using-Anweisung hinzugefügt werden.
ms.date: 07/20/2015
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
ms.openlocfilehash: d344489e88ddc2c8cac51afeb5bbc76bc7b42913
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099073"
---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a><span data-ttu-id="6f71b-104">Gewusst wie: Implementieren und Aufrufen einer benutzerdefinierten Erweiterungsmethode (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="6f71b-104">How to implement and call a custom extension method (C# Programming Guide)</span></span>

<span data-ttu-id="6f71b-105">In diesem Artikel wird das Implementieren Ihrer eigenen Erweiterungsmethoden für jeden .NET-Typ behandelt.</span><span class="sxs-lookup"><span data-stu-id="6f71b-105">This topic shows how to implement your own extension methods for any .NET type.</span></span> <span data-ttu-id="6f71b-106">Der Clientcode kann Ihre Erweiterungsmethoden verwenden, wenn ein Verweis auf die DLL, die die Methoden enthält, und eine [using](../../language-reference/keywords/using-directive.md)-Direktive hinzugefügt werden, die den Namespace angibt, in dem die Erweiterungsmethoden definiert sind.</span><span class="sxs-lookup"><span data-stu-id="6f71b-106">Client code can use your extension methods by adding a reference to the DLL that contains them, and adding a [using](../../language-reference/keywords/using-directive.md) directive that specifies the namespace in which the extension methods are defined.</span></span>  
  
## <a name="to-define-and-call-the-extension-method"></a><span data-ttu-id="6f71b-107">So definieren Sie die Erweiterungsmethode und rufen Sie auf</span><span class="sxs-lookup"><span data-stu-id="6f71b-107">To define and call the extension method</span></span>  
  
1. <span data-ttu-id="6f71b-108">Definieren Sie eine statische [Klasse](./static-classes-and-static-class-members.md), die die Erweiterungsmethode enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="6f71b-108">Define a static [class](./static-classes-and-static-class-members.md) to contain the extension method.</span></span>  
  
     <span data-ttu-id="6f71b-109">Die Klasse muss für den Clientcode sichtbar sein.</span><span class="sxs-lookup"><span data-stu-id="6f71b-109">The class must be visible to client code.</span></span> <span data-ttu-id="6f71b-110">Weitere Informationen finden Sie unter [Zugriffsmodifizierer](./access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="6f71b-110">For more information about accessibility rules, see [Access Modifiers](./access-modifiers.md).</span></span>  
  
2. <span data-ttu-id="6f71b-111">Implementieren Sie die Erweiterungsmethode als statische Methode mit mindestens die gleichen Sichtbarkeit wie die enthaltende Klasse.</span><span class="sxs-lookup"><span data-stu-id="6f71b-111">Implement the extension method as a static method with at least the same visibility as the containing class.</span></span>  
  
3. <span data-ttu-id="6f71b-112">Der erste Parameter der Methode gibt den Typ an, auf den die Methode angewendet wird. Ihm muss ein [this](../../language-reference/keywords/this.md)-Modifizierer vorangehen.</span><span class="sxs-lookup"><span data-stu-id="6f71b-112">The first parameter of the method specifies the type that the method operates on; it must be preceded with the [this](../../language-reference/keywords/this.md) modifier.</span></span>  
  
4. <span data-ttu-id="6f71b-113">Fügen Sie im aufrufenden Code eine `using`-Direktive hinzu, um den [Namespace](../../language-reference/keywords/namespace.md) anzugeben, der die Erweiterungsklassemethode enthält.</span><span class="sxs-lookup"><span data-stu-id="6f71b-113">In the calling code, add a `using` directive to specify the [namespace](../../language-reference/keywords/namespace.md) that contains the extension method class.</span></span>  
  
5. <span data-ttu-id="6f71b-114">Rufen Sie die Methoden auf, als wären sie Instanzmethoden für den Typ.</span><span class="sxs-lookup"><span data-stu-id="6f71b-114">Call the methods as if they were instance methods on the type.</span></span>  
  
     <span data-ttu-id="6f71b-115">Beachten Sie, dass der erste Parameter nicht durch einen Aufruf von Code angegeben wird, da er den Typ darstellt, auf den der Operator angewendet wird, und der Compiler bereits den Typ des Objekts kennt.</span><span class="sxs-lookup"><span data-stu-id="6f71b-115">Note that the first parameter is not specified by calling code because it represents the type on which the operator is being applied, and the compiler already knows the type of your object.</span></span> <span data-ttu-id="6f71b-116">Sie müssen nur Argumente für Parameter 2 bis `n` bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6f71b-116">You only have to provide arguments for parameters 2 through `n`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f71b-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6f71b-117">Example</span></span>  

 <span data-ttu-id="6f71b-118">Im folgenden Beispiel wird eine Erweiterungsmethode namens `WordCount` in der `CustomExtensions.StringExtension`-Klasse implementiert.</span><span class="sxs-lookup"><span data-stu-id="6f71b-118">The following example implements an extension method named `WordCount` in the `CustomExtensions.StringExtension` class.</span></span> <span data-ttu-id="6f71b-119">Die Methode wird auf die <xref:System.String>-Klasse angewendet, die als erster Methodenparameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6f71b-119">The method operates on the <xref:System.String> class, which is specified as the first method parameter.</span></span> <span data-ttu-id="6f71b-120">Der `CustomExtensions`-Namespace wird in den Anwendungsnamespace importiert, und die Methode wird in der `Main`-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="6f71b-120">The `CustomExtensions` namespace is imported into the application namespace, and the method is called inside the `Main` method.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#1)]  
  
## <a name="net-security"></a><span data-ttu-id="6f71b-121">.NET-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6f71b-121">.NET Security</span></span>  

 <span data-ttu-id="6f71b-122">Erweiterungsmethoden enthalten keine speziellen Sicherheitslücken.</span><span class="sxs-lookup"><span data-stu-id="6f71b-122">Extension methods present no specific security vulnerabilities.</span></span> <span data-ttu-id="6f71b-123">Sie können nicht dazu verwendet werden, die Identität vorhandener Methoden für einen Typ anzunehmen, da alle Namenskonflikte zugunsten der Instanz oder eine statische Methode gelöst werden, die der Typ selbst definiert.</span><span class="sxs-lookup"><span data-stu-id="6f71b-123">They can never be used to impersonate existing methods on a type, because all name collisions are resolved in favor of the instance or static method defined by the type itself.</span></span> <span data-ttu-id="6f71b-124">Erweiterungsmethoden können in der erweiterten Klasse nicht auf private Daten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="6f71b-124">Extension methods cannot access any private data in the extended class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f71b-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f71b-125">See also</span></span>

- [<span data-ttu-id="6f71b-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6f71b-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6f71b-127">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="6f71b-127">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="6f71b-128">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="6f71b-128">LINQ (Language-Integrated Query)</span></span>](../../linq/linq-in-csharp.md)
- [<span data-ttu-id="6f71b-129">Statische Klassen und statische Klassenmember</span><span class="sxs-lookup"><span data-stu-id="6f71b-129">Static Classes and Static Class Members</span></span>](./static-classes-and-static-class-members.md)
- [<span data-ttu-id="6f71b-130">protected</span><span class="sxs-lookup"><span data-stu-id="6f71b-130">protected</span></span>](../../language-reference/keywords/protected.md)
- [<span data-ttu-id="6f71b-131">internal</span><span class="sxs-lookup"><span data-stu-id="6f71b-131">internal</span></span>](../../language-reference/keywords/internal.md)
- [<span data-ttu-id="6f71b-132">public</span><span class="sxs-lookup"><span data-stu-id="6f71b-132">public</span></span>](../../language-reference/keywords/public.md)
- [<span data-ttu-id="6f71b-133">this</span><span class="sxs-lookup"><span data-stu-id="6f71b-133">this</span></span>](../../language-reference/keywords/this.md)
- [<span data-ttu-id="6f71b-134">namespace</span><span class="sxs-lookup"><span data-stu-id="6f71b-134">namespace</span></span>](../../language-reference/keywords/namespace.md)
