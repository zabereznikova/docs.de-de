---
title: 'Gewusst wie: Implementieren und Aufrufen einer benutzerdefinierten Erweiterungsmethode (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e73ccee84c35678a4923347ab04619bb6017aca5
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a><span data-ttu-id="b722c-102">Gewusst wie: Implementieren und Aufrufen einer benutzerdefinierten Erweiterungsmethode (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b722c-102">How to: Implement and Call a Custom Extension Method (C# Programming Guide)</span></span>
<span data-ttu-id="b722c-103">In diesem Artikel wird das Implementieren Ihrer eigenen Erweiterungsmethoden für jeden .NET-Typ behandelt.</span><span class="sxs-lookup"><span data-stu-id="b722c-103">This topic shows how to implement your own extension methods for any .NET type.</span></span> <span data-ttu-id="b722c-104">Der Clientcode kann Ihre Erweiterungsmethoden verwenden, wenn ein Verweis auf die DLL, die die Methoden enthält, und eine [using](../../../csharp/language-reference/keywords/using-directive.md)-Direktive hinzugefügt werden, die den Namespace angibt, in dem die Erweiterungsmethoden definiert sind.</span><span class="sxs-lookup"><span data-stu-id="b722c-104">Client code can use your extension methods by adding a reference to the DLL that contains them, and adding a [using](../../../csharp/language-reference/keywords/using-directive.md) directive that specifies the namespace in which the extension methods are defined.</span></span>  
  
## <a name="to-define-and-call-the-extension-method"></a><span data-ttu-id="b722c-105">So definieren Sie die Erweiterungsmethode und rufen Sie auf</span><span class="sxs-lookup"><span data-stu-id="b722c-105">To define and call the extension method</span></span>  
  
1.  <span data-ttu-id="b722c-106">Definieren Sie eine statische [Klasse](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md), die die Erweiterungsmethode enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="b722c-106">Define a static [class](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) to contain the extension method.</span></span>  
  
     <span data-ttu-id="b722c-107">Die Klasse muss für den Clientcode sichtbar sein.</span><span class="sxs-lookup"><span data-stu-id="b722c-107">The class must be visible to client code.</span></span> <span data-ttu-id="b722c-108">Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="b722c-108">For more information about accessibility rules, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
2.  <span data-ttu-id="b722c-109">Implementieren Sie die Erweiterungsmethode als statische Methode mit mindestens die gleichen Sichtbarkeit wie die enthaltende Klasse.</span><span class="sxs-lookup"><span data-stu-id="b722c-109">Implement the extension method as a static method with at least the same visibility as the containing class.</span></span>  
  
3.  <span data-ttu-id="b722c-110">Der erste Parameter der Methode gibt den Typ an, auf den die Methode angewendet wird. Ihm muss ein [this](../../../csharp/language-reference/keywords/this.md)-Modifizierer vorangehen.</span><span class="sxs-lookup"><span data-stu-id="b722c-110">The first parameter of the method specifies the type that the method operates on; it must be preceded with the [this](../../../csharp/language-reference/keywords/this.md) modifier.</span></span>  
  
4.  <span data-ttu-id="b722c-111">Fügen Sie im aufrufenden Code eine `using`-Direktive hinzu, um den [Namespace](../../../csharp/language-reference/keywords/namespace.md) anzugeben, der die Erweiterungsklassemethode enthält.</span><span class="sxs-lookup"><span data-stu-id="b722c-111">In the calling code, add a `using` directive to specify the [namespace](../../../csharp/language-reference/keywords/namespace.md) that contains the extension method class.</span></span>  
  
5.  <span data-ttu-id="b722c-112">Rufen Sie die Methoden auf, als wären sie Instanzmethoden für den Typ.</span><span class="sxs-lookup"><span data-stu-id="b722c-112">Call the methods as if they were instance methods on the type.</span></span>  
  
     <span data-ttu-id="b722c-113">Beachten Sie, dass der erste Parameter nicht durch einen Aufruf von Code angegeben wird, da er den Typ darstellt, auf den der Operator angewendet wird, und der Compiler bereits den Typ des Objekts kennt.</span><span class="sxs-lookup"><span data-stu-id="b722c-113">Note that the first parameter is not specified by calling code because it represents the type on which the operator is being applied, and the compiler already knows the type of your object.</span></span> <span data-ttu-id="b722c-114">Sie müssen nur Argumente für Parameter 2 bis `n` bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b722c-114">You only have to provide arguments for parameters 2 through `n`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b722c-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b722c-115">Example</span></span>  
 <span data-ttu-id="b722c-116">Im folgenden Beispiel wird eine Erweiterungsmethode namens `WordCount` in der `CustomExtensions.StringExtension`-Klasse implementiert.</span><span class="sxs-lookup"><span data-stu-id="b722c-116">The following example implements an extension method named `WordCount` in the `CustomExtensions.StringExtension` class.</span></span> <span data-ttu-id="b722c-117">Die Methode wird auf die <xref:System.String>-Klasse angewendet, die als erster Methodenparameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b722c-117">The method operates on the <xref:System.String> class, which is specified as the first method parameter.</span></span> <span data-ttu-id="b722c-118">Der `CustomExtensions`-Namespace wird in den Anwendungsnamespace importiert, und die Methode wird in der `Main`-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b722c-118">The `CustomExtensions` namespace is imported into the application namespace, and the method is called inside the `Main` method.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-and-call-a-custom-extension-method_1.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b722c-119">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b722c-119">Compiling the Code</span></span>  
 <span data-ttu-id="b722c-120">Kopieren Sie diesen Code, und fügen Sie ihn in ein Visual C#-Konsolenanwendungsprojekt ein, das in Visual Studio erstellt wurde, um den Code auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b722c-120">To run this code, copy and paste it into a Visual C# console application project that has been created in Visual Studio.</span></span> <span data-ttu-id="b722c-121">Standardmäßig wird dieses Projekt mit Version 3.5 von [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verwendet und verfügt über einen Verweis auf „System.Core.dll“ und eine `using`-Anweisung für „System.Linq“.</span><span class="sxs-lookup"><span data-stu-id="b722c-121">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a `using` directive for System.Linq.</span></span> <span data-ttu-id="b722c-122">Wenn mindestens eine dieser Anforderungen im Projekt nicht vorhanden sind, können Sie sie manuell hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b722c-122">If one or more of these requirements are missing from the project, you can add them manually.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="b722c-123">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b722c-123">.NET Framework Security</span></span>  
 <span data-ttu-id="b722c-124">Erweiterungsmethoden enthalten keine speziellen Sicherheitslücken.</span><span class="sxs-lookup"><span data-stu-id="b722c-124">Extension methods present no specific security vulnerabilities.</span></span> <span data-ttu-id="b722c-125">Sie können nicht dazu verwendet werden, die Identität vorhandener Methoden für einen Typ anzunehmen, da alle Namenskonflikte zugunsten der Instanz oder eine statische Methode gelöst werden, die der Typ selbst definiert.</span><span class="sxs-lookup"><span data-stu-id="b722c-125">They can never be used to impersonate existing methods on a type, because all name collisions are resolved in favor of the instance or static method defined by the type itself.</span></span> <span data-ttu-id="b722c-126">Erweiterungsmethoden können in der erweiterten Klasse nicht auf private Daten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b722c-126">Extension methods cannot access any private data in the extended class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b722c-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b722c-127">See Also</span></span>  
 [<span data-ttu-id="b722c-128">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b722c-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b722c-129">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="b722c-129">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)  
 [<span data-ttu-id="b722c-130">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="b722c-130">LINQ (Language-Integrated Query)</span></span>](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [<span data-ttu-id="b722c-131">Statische Klassen und statische Klassenmember</span><span class="sxs-lookup"><span data-stu-id="b722c-131">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)  
 [<span data-ttu-id="b722c-132">protected</span><span class="sxs-lookup"><span data-stu-id="b722c-132">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="b722c-133">internal</span><span class="sxs-lookup"><span data-stu-id="b722c-133">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
 [<span data-ttu-id="b722c-134">public</span><span class="sxs-lookup"><span data-stu-id="b722c-134">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="b722c-135">this</span><span class="sxs-lookup"><span data-stu-id="b722c-135">this</span></span>](../../../csharp/language-reference/keywords/this.md)  
 [<span data-ttu-id="b722c-136">namespace</span><span class="sxs-lookup"><span data-stu-id="b722c-136">namespace</span></span>](../../../csharp/language-reference/keywords/namespace.md)
