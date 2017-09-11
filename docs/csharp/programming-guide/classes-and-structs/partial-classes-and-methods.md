---
title: Partielle Klassen und Methoden (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- partial methods [C#]
- partial classes [C#]
- C# language, partial classes and methods
ms.assetid: 804cecb7-62db-4f97-a99f-60975bd59fa1
caps.latest.revision: 35
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
ms.openlocfilehash: 41b07af83faa6af23695f3719aae29183c35a417
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="partial-classes-and-methods-c-programming-guide"></a><span data-ttu-id="11461-102">Partielle Klassen und Methoden (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="11461-102">Partial Classes and Methods (C# Programming Guide)</span></span>
<span data-ttu-id="11461-103">Es ist möglich, die Definition einer [Klasse](../../../csharp/language-reference/keywords/class.md) oder einer [Struktur](../../../csharp/language-reference/keywords/struct.md), einer [Schnittstelle](../../../csharp/language-reference/keywords/interface.md) oder einer Methode auf zwei oder mehr Quelldateien aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="11461-103">It is possible to split the definition of a [class](../../../csharp/language-reference/keywords/class.md) or a [struct](../../../csharp/language-reference/keywords/struct.md), an [interface](../../../csharp/language-reference/keywords/interface.md) or a method over two or more source files.</span></span> <span data-ttu-id="11461-104">Jede Quelldatei enthält einen Abschnitt der Typ- oder Methodendefinition. Die Teile werden bei der Kompilierung der Anwendung miteinander kombiniert.</span><span class="sxs-lookup"><span data-stu-id="11461-104">Each source file contains a section of the type or method definition, and all parts are combined when the application is compiled.</span></span>  
  
## <a name="partial-classes"></a><span data-ttu-id="11461-105">Teilklassen</span><span class="sxs-lookup"><span data-stu-id="11461-105">Partial Classes</span></span>  
 <span data-ttu-id="11461-106">Es gibt mehrere Situationen, bei denen das Aufteilen einer Klassendefinition wünschenswert ist:</span><span class="sxs-lookup"><span data-stu-id="11461-106">There are several situations when splitting a class definition is desirable:</span></span>  
  
-   <span data-ttu-id="11461-107">Wenn Sie an großen Projekten arbeiten, können durch das Verteilen einer Klasse auf mehrere Dateien mehrere Programmierer gleichzeitig daran arbeiten.</span><span class="sxs-lookup"><span data-stu-id="11461-107">When working on large projects, spreading a class over separate files enables multiple programmers to work on it at the same time.</span></span>  
  
-   <span data-ttu-id="11461-108">Wenn Sie mit automatisch erzeugten Quellen arbeiten, kann Code einer Klasse hinzugefügt werden, ohne die Quelldatei neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="11461-108">When working with automatically generated source, code can be added to the class without having to recreate the source file.</span></span> <span data-ttu-id="11461-109">Visual Studio verwendet diesen Ansatz, wenn es Windows Forms, Webdienst-Wrappercode usw. erstellt.</span><span class="sxs-lookup"><span data-stu-id="11461-109">Visual Studio uses this approach when it creates Windows Forms, Web service wrapper code, and so on.</span></span> <span data-ttu-id="11461-110">Sie können Code erstellen, der diese Klassen verwendet, ohne die von Visual Studio erstellte Datei ändern zu müssen.</span><span class="sxs-lookup"><span data-stu-id="11461-110">You can create code that uses these classes without having to modify the file created by Visual Studio.</span></span>  
  
-   <span data-ttu-id="11461-111">Um eine Klassendefinition aufzuteilen, verwenden Sie den Schlüsselwortmodifizierer [partial](../../../csharp/language-reference/keywords/partial-type.md), wie hier gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="11461-111">To split a class definition, use the [partial](../../../csharp/language-reference/keywords/partial-type.md) keyword modifier, as shown here:</span></span>  
  
 <span data-ttu-id="11461-112">[!code-cs[csProgGuideObjects#26](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="11461-112">[!code-cs[csProgGuideObjects#26](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_1.cs)]</span></span>  
  
 <span data-ttu-id="11461-113">Das Schlüsselwort `partial` gibt an, dass andere Teile der Klasse, Struktur oder Schnittstelle im Namespace definiert werden können.</span><span class="sxs-lookup"><span data-stu-id="11461-113">The `partial` keyword indicates that other parts of the class, struct, or interface can be defined in the namespace.</span></span> <span data-ttu-id="11461-114">Alle Teile müssen das Schlüsselwort `partial` verwenden.</span><span class="sxs-lookup"><span data-stu-id="11461-114">All the parts must use the `partial` keyword.</span></span> <span data-ttu-id="11461-115">Alle Teile müssen zur Kompilierzeit verfügbar sein, um den endgültigen Typ zu bilden.</span><span class="sxs-lookup"><span data-stu-id="11461-115">All the parts must be available at compile time to form the final type.</span></span> <span data-ttu-id="11461-116">Alle Teile müssen die gleiche Zugriffsebene haben, z.B. `public`, `private` usw.</span><span class="sxs-lookup"><span data-stu-id="11461-116">All the parts must have the same accessibility, such as `public`, `private`, and so on.</span></span>  
  
 <span data-ttu-id="11461-117">Wenn ein beliebiger Teil als abstrakt deklariert wird, wird anschließend der ganze Typ als abstrakt betrachtet.</span><span class="sxs-lookup"><span data-stu-id="11461-117">If any part is declared abstract, then the whole type is considered abstract.</span></span> <span data-ttu-id="11461-118">Wenn ein beliebiges Teil als versiegelt deklariert wird, wird anschließend der ganze Typ als versiegelt betrachtet.</span><span class="sxs-lookup"><span data-stu-id="11461-118">If any part is declared sealed, then the whole type is considered sealed.</span></span> <span data-ttu-id="11461-119">Wenn ein beliebiger Teil einen Basistyp deklariert, erbt der ganze Typ diese Klasse.</span><span class="sxs-lookup"><span data-stu-id="11461-119">If any part declares a base type, then the whole type inherits that class.</span></span>  
  
 <span data-ttu-id="11461-120">Alle Teile, die eine Basisklasse angeben, müssen übereinstimmen, aber Teile, die eine Basisklasse auslassen, erben weiterhin den Basistyp.</span><span class="sxs-lookup"><span data-stu-id="11461-120">All the parts that specify a base class must agree, but parts that omit a base class still inherit the base type.</span></span> <span data-ttu-id="11461-121">Teile können unterschiedliche Basisschnittstellen angeben, und der letzte Typ implementiert alle Schnittstellen, die von allen Teildeklarationen aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="11461-121">Parts can specify different base interfaces, and the final type implements all the interfaces listed by all the partial declarations.</span></span> <span data-ttu-id="11461-122">Alle Klassen-, Struktur- und Schnittstellenmember, die in einer Teildefinition deklariert wurden, sind für alle anderen Teile verfügbar.</span><span class="sxs-lookup"><span data-stu-id="11461-122">Any class, struct, or interface members declared in a partial definition are available to all the other parts.</span></span> <span data-ttu-id="11461-123">Der endgültige Typ besteht aus allen Teilen zur Kompilierzeit.</span><span class="sxs-lookup"><span data-stu-id="11461-123">The final type is the combination of all the parts at compile time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11461-124">Der `partial`-Modifizierer ist nicht für Delegat- oder Enumerationsdeklarationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="11461-124">The `partial` modifier is not available on delegate or enumeration declarations.</span></span>  
  
 <span data-ttu-id="11461-125">Im folgenden Beispiel wird gezeigt, dass geschachtelte Typen eine Teilausführung sein können, selbst wenn der Typ, in dem sie geschachtelt sind, selbst keine ist.</span><span class="sxs-lookup"><span data-stu-id="11461-125">The following example shows that nested types can be partial, even if the type they are nested within is not partial itself.</span></span>  
  
 <span data-ttu-id="11461-126">[!code-cs[csProgGuideObjects#25](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="11461-126">[!code-cs[csProgGuideObjects#25](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_2.cs)]</span></span>  
  
 <span data-ttu-id="11461-127">Zur Kompilierzeit werden Attribute von partiellen Typdefinitionen zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="11461-127">At compile time, attributes of partial-type definitions are merged.</span></span> <span data-ttu-id="11461-128">Betrachten Sie beispielsweise die folgenden Deklarationen:</span><span class="sxs-lookup"><span data-stu-id="11461-128">For example, consider the following declarations:</span></span>  
  
 <span data-ttu-id="11461-129">[!code-cs[csProgGuideObjects#23](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="11461-129">[!code-cs[csProgGuideObjects#23](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_3.cs)]</span></span>  
  
 <span data-ttu-id="11461-130">Sie entsprechen den folgenden Deklarationen:</span><span class="sxs-lookup"><span data-stu-id="11461-130">They are equivalent to the following declarations:</span></span>  
  
 <span data-ttu-id="11461-131">[!code-cs[csProgGuideObjects#24](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="11461-131">[!code-cs[csProgGuideObjects#24](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_4.cs)]</span></span>  
  
 <span data-ttu-id="11461-132">Die folgenden werden aus allen partiellen Typdefinitionen zusammengeführt:</span><span class="sxs-lookup"><span data-stu-id="11461-132">The following are merged from all the partial-type definitions:</span></span>  
  
-   <span data-ttu-id="11461-133">XML-Kommentare</span><span class="sxs-lookup"><span data-stu-id="11461-133">XML comments</span></span>  
  
-   <span data-ttu-id="11461-134">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="11461-134">interfaces</span></span>  
  
-   <span data-ttu-id="11461-135">Generische Parameterattribute</span><span class="sxs-lookup"><span data-stu-id="11461-135">generic-type parameter attributes</span></span>  
  
-   <span data-ttu-id="11461-136">Klassenattribute</span><span class="sxs-lookup"><span data-stu-id="11461-136">class attributes</span></span>  
  
-   <span data-ttu-id="11461-137">Member</span><span class="sxs-lookup"><span data-stu-id="11461-137">members</span></span>  
  
 <span data-ttu-id="11461-138">Betrachten Sie beispielsweise die folgenden Deklarationen:</span><span class="sxs-lookup"><span data-stu-id="11461-138">For example, consider the following declarations:</span></span>  
  
 <span data-ttu-id="11461-139">[!code-cs[csProgGuideObjects#21](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="11461-139">[!code-cs[csProgGuideObjects#21](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_5.cs)]</span></span>  
  
 <span data-ttu-id="11461-140">Sie entsprechen den folgenden Deklarationen:</span><span class="sxs-lookup"><span data-stu-id="11461-140">They are equivalent to the following declarations:</span></span>  
  
 <span data-ttu-id="11461-141">[!code-cs[csProgGuideObjects#22](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="11461-141">[!code-cs[csProgGuideObjects#22](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_6.cs)]</span></span>  
  
### <a name="restrictions"></a><span data-ttu-id="11461-142">Beschränkungen</span><span class="sxs-lookup"><span data-stu-id="11461-142">Restrictions</span></span>  
 <span data-ttu-id="11461-143">Es sind mehrere Regeln zu beachten, wenn Sie partielle Klassendefinitionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="11461-143">There are several rules to follow when you are working with partial class definitions:</span></span>  
  
-   <span data-ttu-id="11461-144">Alle partiellen Typdefinitionen, die als Teile des gleichen Typs vorgesehen sind, müssen mit `partial` geändert werden.</span><span class="sxs-lookup"><span data-stu-id="11461-144">All partial-type definitions meant to be parts of the same type must be modified with `partial`.</span></span> <span data-ttu-id="11461-145">Die folgenden Klassendeklarationen erzeugen z.B. einen Fehler:</span><span class="sxs-lookup"><span data-stu-id="11461-145">For example, the following class declarations generate an error:</span></span>  
  
     <span data-ttu-id="11461-146">[!code-cs[csProgGuideObjects#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="11461-146">[!code-cs[csProgGuideObjects#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_7.cs)]</span></span>  
  
-   <span data-ttu-id="11461-147">Der `partial`-Modifizierer kann nur unmittelbar vor den Schlüsselwörtern `class`, `struct` oder `interface` erscheinen.</span><span class="sxs-lookup"><span data-stu-id="11461-147">The `partial` modifier can only appear immediately before the keywords `class`, `struct`, or `interface`.</span></span>  
  
-   <span data-ttu-id="11461-148">Geschachtelte partielle Typen sind in partiellen Typdefinitionen zulässig, wie im folgenden Beispiel dargestellt wird:</span><span class="sxs-lookup"><span data-stu-id="11461-148">Nested partial types are allowed in partial-type definitions as illustrated in the following example:</span></span>  
  
     <span data-ttu-id="11461-149">[!code-cs[csProgGuideObjects#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="11461-149">[!code-cs[csProgGuideObjects#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_8.cs)]</span></span>  
  
-   <span data-ttu-id="11461-150">Alle partiellen Typdefinitionen, die als Teile des gleichen Typs vorgesehen sind, müssen in der gleichen Assembly und demselben Modul (EXE- oder DLL-Datei) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="11461-150">All partial-type definitions meant to be parts of the same type must be defined in the same assembly and the same module (.exe or .dll file).</span></span> <span data-ttu-id="11461-151">Partielle Definitionen können nicht mehrere Module umfassen.</span><span class="sxs-lookup"><span data-stu-id="11461-151">Partial definitions cannot span multiple modules.</span></span>  
  
-   <span data-ttu-id="11461-152">Der Klassenname und die generischen Typparameter müssen mit allen partiellen Typdefinitionen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="11461-152">The class name and generic-type parameters must match on all partial-type definitions.</span></span> <span data-ttu-id="11461-153">Generische Typen können partiell sein.</span><span class="sxs-lookup"><span data-stu-id="11461-153">Generic types can be partial.</span></span> <span data-ttu-id="11461-154">Jede partielle Definition muss die gleichen Parameternamen in der gleichen Reihenfolge aufweisen.</span><span class="sxs-lookup"><span data-stu-id="11461-154">Each partial declaration must use the same parameter names in the same order.</span></span>  
  
-   <span data-ttu-id="11461-155">Die nachfolgenden Schlüsselwörter für eine partielle Typdefinition sind optional, wenn sie aber für eine partielle Definition vorhanden sind, können sie nicht mit anderen Schlüsselwörtern in Konflikt treten, die in anderen partiellen Definitionen desselben Typs angegeben wurden:</span><span class="sxs-lookup"><span data-stu-id="11461-155">The following keywords on a partial-type definition are optional, but if present on one partial-type definition, cannot conflict with the keywords specified on another partial definition for the same type:</span></span>  
  
    -   [<span data-ttu-id="11461-156">public</span><span class="sxs-lookup"><span data-stu-id="11461-156">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
  
    -   [<span data-ttu-id="11461-157">private</span><span class="sxs-lookup"><span data-stu-id="11461-157">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
  
    -   [<span data-ttu-id="11461-158">protected</span><span class="sxs-lookup"><span data-stu-id="11461-158">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
  
    -   [<span data-ttu-id="11461-159">internal</span><span class="sxs-lookup"><span data-stu-id="11461-159">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
  
    -   [<span data-ttu-id="11461-160">abstract</span><span class="sxs-lookup"><span data-stu-id="11461-160">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)  
  
    -   [<span data-ttu-id="11461-161">sealed</span><span class="sxs-lookup"><span data-stu-id="11461-161">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)  
  
    -   <span data-ttu-id="11461-162">Basisklasse</span><span class="sxs-lookup"><span data-stu-id="11461-162">base class</span></span>  
  
    -   <span data-ttu-id="11461-163">[new](../../../csharp/language-reference/keywords/new.md)-Modifizierer (geschachtelte Teile)</span><span class="sxs-lookup"><span data-stu-id="11461-163">[new](../../../csharp/language-reference/keywords/new.md) modifier (nested parts)</span></span>  
  
    -   <span data-ttu-id="11461-164">Generische Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="11461-164">generic constraints</span></span>  
  
         <span data-ttu-id="11461-165">Weitere Informationen finden Sie unter [Einschränkungen für Typparameter](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="11461-165">For more information, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="11461-166">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="11461-166">Example 1</span></span>  
  
### <a name="description"></a><span data-ttu-id="11461-167">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11461-167">Description</span></span>  
 <span data-ttu-id="11461-168">Im folgenden Beispiel werden die Felder und der Konstruktor der Klasse (`CoOrds`) in einer partiellen Klassendefinition deklariert, und der Member (`PrintCoOrds`) wird in einer anderen partiellen Klassendefinition deklariert.</span><span class="sxs-lookup"><span data-stu-id="11461-168">In the following example, the fields and the constructor of the class, `CoOrds`, are declared in one partial class definition, and the member, `PrintCoOrds`, is declared in another partial class definition.</span></span>  
  
### <a name="code"></a><span data-ttu-id="11461-169">Code</span><span class="sxs-lookup"><span data-stu-id="11461-169">Code</span></span>  
 <span data-ttu-id="11461-170">[!code-cs[csProgGuideObjects#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="11461-170">[!code-cs[csProgGuideObjects#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_9.cs)]</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="11461-171">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="11461-171">Example 2</span></span>  
  
### <a name="description"></a><span data-ttu-id="11461-172">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11461-172">Description</span></span>  
 <span data-ttu-id="11461-173">Im folgenden Beispiel wird gezeigt, dass Sie auch partielle Strukturen und Schnittstellen entwickeln können.</span><span class="sxs-lookup"><span data-stu-id="11461-173">The following example shows that you can also develop partial structs and interfaces.</span></span>  
  
### <a name="code"></a><span data-ttu-id="11461-174">Code</span><span class="sxs-lookup"><span data-stu-id="11461-174">Code</span></span>  
 <span data-ttu-id="11461-175">[!code-cs[csProgGuideObjects#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="11461-175">[!code-cs[csProgGuideObjects#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_10.cs)]</span></span>  
  
## <a name="partial-methods"></a><span data-ttu-id="11461-176">Partielle Methoden</span><span class="sxs-lookup"><span data-stu-id="11461-176">Partial Methods</span></span>  
 <span data-ttu-id="11461-177">Eine partielle Klasse oder Struktur kann eine partielle Methode enthalten.</span><span class="sxs-lookup"><span data-stu-id="11461-177">A partial class or struct may contain a partial method.</span></span> <span data-ttu-id="11461-178">Ein Teil der Klasse enthält die Signatur der Methode.</span><span class="sxs-lookup"><span data-stu-id="11461-178">One part of the class contains the signature of the method.</span></span> <span data-ttu-id="11461-179">Eine optionale Implementierung kann im gleichen oder in einem anderen Teil definiert werden.</span><span class="sxs-lookup"><span data-stu-id="11461-179">An optional implementation may be defined in the same part or another part.</span></span> <span data-ttu-id="11461-180">Wenn die Implementierung nicht bereitgestellt wird, werden anschließend die Methode sowie alle Aufrufe an die Methode zur Kompilierzeit entfernt.</span><span class="sxs-lookup"><span data-stu-id="11461-180">If the implementation is not supplied, then the method and all calls to the method are removed at compile time.</span></span>  
  
 <span data-ttu-id="11461-181">Mit partiellen Methoden kann der Implementierer des einen Teils einer Klasse eine Methode definieren, die einem Ereignis ähnelt.</span><span class="sxs-lookup"><span data-stu-id="11461-181">Partial methods enable the implementer of one part of a class to define a method, similar to an event.</span></span> <span data-ttu-id="11461-182">Der Implementierer des anderen Teils der Klasse kann entscheiden, ob die Methode implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="11461-182">The implementer of the other part of the class can decide whether to implement the method or not.</span></span> <span data-ttu-id="11461-183">Wenn die Methode nicht implementiert wird, kann der Compiler anschließend die Methodensignatur und alle Aufrufe an die Methode entfernen.</span><span class="sxs-lookup"><span data-stu-id="11461-183">If the method is not implemented, then the compiler removes the method signature and all calls to the method.</span></span> <span data-ttu-id="11461-184">Die Aufrufe an die Methode, einschließlich Ergebnissen, die bei der Auswertung eines Arguments im Aufruf auftreten würden, haben zur Laufzeit keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="11461-184">The calls to the method, including any results that would occur from evaluation of arguments in the calls, have no effect at run time.</span></span> <span data-ttu-id="11461-185">Deshalb kann jeder Code in der partiellen Klasse eine partielle Methode frei verwenden, selbst wenn die Implementation nicht bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="11461-185">Therefore, any code in the partial class can freely use a partial method, even if the implementation is not supplied.</span></span> <span data-ttu-id="11461-186">Es ergeben sich keine Laufzeit- oder Kompilierzeitfehler, wenn die Methode aufgerufen, aber nicht implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="11461-186">No compile-time or run-time errors will result if the method is called but not implemented.</span></span>  
  
 <span data-ttu-id="11461-187">Partielle Methoden sind besonders nützlich, um generierten Code anzupassen.</span><span class="sxs-lookup"><span data-stu-id="11461-187">Partial methods are especially useful as a way to customize generated code.</span></span> <span data-ttu-id="11461-188">Sie ermöglichen, dass Methodenname und -signatur reserviert werden können, sodass generierter Code die Methode aufrufen kann, aber der Entwickler über die Implementierung der Methode entscheiden kann.</span><span class="sxs-lookup"><span data-stu-id="11461-188">They allow for a method name and signature to be reserved, so that generated code can call the method but the developer can decide whether to implement the method.</span></span> <span data-ttu-id="11461-189">Wie partielle Klassen ermöglichen partielle Methoden, dass Code, der von einem Codegenerator erstellt wurde, zusammen mit Code, der von einem menschlichen Entwickler erstellt wurde, ohne Laufzeitkosten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="11461-189">Much like partial classes, partial methods enable code created by a code generator and code created by a human developer to work together without run-time costs.</span></span>  
  
 <span data-ttu-id="11461-190">Eine partielle Methodendeklaration besteht aus zwei Teilen: der Definition und der Implementierung.</span><span class="sxs-lookup"><span data-stu-id="11461-190">A partial method declaration consists of two parts: the definition, and the implementation.</span></span> <span data-ttu-id="11461-191">Diese können in separaten Teilen einer partiellen Klasse oder im gleichen Teil sein.</span><span class="sxs-lookup"><span data-stu-id="11461-191">These may be in separate parts of a partial class, or in the same part.</span></span> <span data-ttu-id="11461-192">Wenn es keine Implementierungsdeklaration gibt, optimiert der Compiler anschließend sowohl die definierende Deklaration als auch alle Aufrufe an die Methode.</span><span class="sxs-lookup"><span data-stu-id="11461-192">If there is no implementation declaration, then the compiler optimizes away both the defining declaration and all calls to the method.</span></span>  
  
```  
// Definition in file1.cs  
partial void onNameChanged();  
  
// Implementation in file2.cs  
partial void onNameChanged()  
{  
  // method body  
}  
```  
  
-   <span data-ttu-id="11461-193">Partielle Methodendeklarationen müssen mit dem Kontextschlüsselwort [partial](../../../csharp/language-reference/keywords/partial-type.md) beginnen, und die Methode muss [void](../../../csharp/language-reference/keywords/void.md) zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="11461-193">Partial method declarations must begin with the contextual keyword [partial](../../../csharp/language-reference/keywords/partial-type.md) and the method must return [void](../../../csharp/language-reference/keywords/void.md).</span></span>  
  
-   <span data-ttu-id="11461-194">Partielle Methoden können [ref](../../../csharp/language-reference/keywords/ref.md)-Parameter, aber keine [out](../../../csharp/language-reference/keywords/out.md)-Parameter besitzen.</span><span class="sxs-lookup"><span data-stu-id="11461-194">Partial methods can have [ref](../../../csharp/language-reference/keywords/ref.md) but not [out](../../../csharp/language-reference/keywords/out.md) parameters.</span></span>  
  
-   <span data-ttu-id="11461-195">Partielle Methoden sind implizit [privat](../../../csharp/language-reference/keywords/private.md) und können daher nicht [virtuell](../../../csharp/language-reference/keywords/virtual.md) sein.</span><span class="sxs-lookup"><span data-stu-id="11461-195">Partial methods are implicitly [private](../../../csharp/language-reference/keywords/private.md), and therefore they cannot be [virtual](../../../csharp/language-reference/keywords/virtual.md).</span></span>  
  
-   <span data-ttu-id="11461-196">Partielle Methoden können nicht [extern](../../../csharp/language-reference/keywords/extern.md) sein, da das Vorhandensein des Texts bestimmt, ob sie definierend oder implementierend sind.</span><span class="sxs-lookup"><span data-stu-id="11461-196">Partial methods cannot be [extern](../../../csharp/language-reference/keywords/extern.md), because the presence of the body determines whether they are defining or implementing.</span></span>  
  
-   <span data-ttu-id="11461-197">Partielle Methoden können [statische](../../../csharp/language-reference/keywords/static.md) und [unsichere](../../../csharp/language-reference/keywords/unsafe.md) Modifizierer besitzen.</span><span class="sxs-lookup"><span data-stu-id="11461-197">Partial methods can have [static](../../../csharp/language-reference/keywords/static.md) and [unsafe](../../../csharp/language-reference/keywords/unsafe.md) modifiers.</span></span>  
  
-   <span data-ttu-id="11461-198">Partielle Methoden können generisch sein.</span><span class="sxs-lookup"><span data-stu-id="11461-198">Partial methods can be generic.</span></span> <span data-ttu-id="11461-199">Einschränkungen gelten für die definierende partielle Methodendeklaration und können optional für die implementierende wiederholt werden.</span><span class="sxs-lookup"><span data-stu-id="11461-199">Constraints are put on the defining partial method declaration, and may optionally be repeated on the implementing one.</span></span> <span data-ttu-id="11461-200">Parameter- und Typparameternamen müssen in der implementierenden und definierenden Deklaration nicht gleich sein.</span><span class="sxs-lookup"><span data-stu-id="11461-200">Parameter and type parameter names do not have to be the same in the implementing declaration as in the defining one.</span></span>  
  
-   <span data-ttu-id="11461-201">Sie können einen [Delegaten](../../../csharp/language-reference/keywords/delegate.md) für eine partielle Methode erstellen, die definiert und implementiert wurde. Dies geht jedoch nicht für partielle Methoden, die nur definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="11461-201">You can make a [delegate](../../../csharp/language-reference/keywords/delegate.md) to a partial method that has been defined and implemented, but not to a partial method that has only been defined.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="11461-202">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="11461-202">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="11461-203">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11461-203">See Also</span></span>  
 <span data-ttu-id="11461-204">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="11461-204">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="11461-205">[Klassen](../../../csharp/programming-guide/classes-and-structs/classes.md) </span><span class="sxs-lookup"><span data-stu-id="11461-205">[Classes](../../../csharp/programming-guide/classes-and-structs/classes.md) </span></span>  
 <span data-ttu-id="11461-206">[Strukturen](../../../csharp/programming-guide/classes-and-structs/structs.md) </span><span class="sxs-lookup"><span data-stu-id="11461-206">[Structs](../../../csharp/programming-guide/classes-and-structs/structs.md) </span></span>  
 <span data-ttu-id="11461-207">[Schnittstellen](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="11461-207">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 [<span data-ttu-id="11461-208">partial (Typ)</span><span class="sxs-lookup"><span data-stu-id="11461-208">partial (Type)</span></span>](../../../csharp/language-reference/keywords/partial-type.md)

