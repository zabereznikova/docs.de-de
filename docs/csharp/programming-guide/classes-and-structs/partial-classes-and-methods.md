---
title: Partielle Klassen und Methoden – C#-Programmierhandbuch
description: Partielle Klassen und Methoden in C# teilen die Definition einer Klasse, einer Struktur, einer Schnittstelle oder einer Methode auf zwei oder mehr Quelldateien auf.
ms.date: 07/20/2015
helpviewer_keywords:
- partial methods [C#]
- partial classes [C#]
- C# language, partial classes and methods
ms.assetid: 804cecb7-62db-4f97-a99f-60975bd59fa1
ms.openlocfilehash: 792159786131654d6ee0363f7ab7b87ac50d32bb
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864747"
---
# <a name="partial-classes-and-methods-c-programming-guide"></a><span data-ttu-id="ff089-103">Partielle Klassen und Methoden (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ff089-103">Partial Classes and Methods (C# Programming Guide)</span></span>

<span data-ttu-id="ff089-104">Es ist möglich, die Definition einer [Klasse](../../language-reference/keywords/class.md), einer [Struktur](../../language-reference/builtin-types/struct.md), einer [Schnittstelle](../../language-reference/keywords/interface.md) oder einer Methode auf zwei oder mehr Quelldateien aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="ff089-104">It is possible to split the definition of a [class](../../language-reference/keywords/class.md), a [struct](../../language-reference/builtin-types/struct.md), an [interface](../../language-reference/keywords/interface.md) or a method over two or more source files.</span></span> <span data-ttu-id="ff089-105">Jede Quelldatei enthält einen Abschnitt der Typ- oder Methodendefinition. Die Teile werden bei der Kompilierung der Anwendung miteinander kombiniert.</span><span class="sxs-lookup"><span data-stu-id="ff089-105">Each source file contains a section of the type or method definition, and all parts are combined when the application is compiled.</span></span>

## <a name="partial-classes"></a><span data-ttu-id="ff089-106">Teilklassen</span><span class="sxs-lookup"><span data-stu-id="ff089-106">Partial Classes</span></span>

<span data-ttu-id="ff089-107">Es gibt mehrere Situationen, bei denen das Aufteilen einer Klassendefinition wünschenswert ist:</span><span class="sxs-lookup"><span data-stu-id="ff089-107">There are several situations when splitting a class definition is desirable:</span></span>

- <span data-ttu-id="ff089-108">Wenn Sie an großen Projekten arbeiten, können durch das Verteilen einer Klasse auf mehrere Dateien mehrere Programmierer gleichzeitig daran arbeiten.</span><span class="sxs-lookup"><span data-stu-id="ff089-108">When working on large projects, spreading a class over separate files enables multiple programmers to work on it at the same time.</span></span>

- <span data-ttu-id="ff089-109">Wenn Sie mit automatisch erzeugten Quellen arbeiten, kann Code einer Klasse hinzugefügt werden, ohne die Quelldatei neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff089-109">When working with automatically generated source, code can be added to the class without having to recreate the source file.</span></span> <span data-ttu-id="ff089-110">Visual Studio verwendet diesen Ansatz, wenn es Windows Forms, Webdienst-Wrappercode usw. erstellt.</span><span class="sxs-lookup"><span data-stu-id="ff089-110">Visual Studio uses this approach when it creates Windows Forms, Web service wrapper code, and so on.</span></span> <span data-ttu-id="ff089-111">Sie können Code erstellen, der diese Klassen verwendet, ohne die von Visual Studio erstellte Datei ändern zu müssen.</span><span class="sxs-lookup"><span data-stu-id="ff089-111">You can create code that uses these classes without having to modify the file created by Visual Studio.</span></span>

- <span data-ttu-id="ff089-112">Um eine Klassendefinition aufzuteilen, verwenden Sie den Schlüsselwortmodifizierer [partial](../../language-reference/keywords/partial-type.md), wie hier gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="ff089-112">To split a class definition, use the [partial](../../language-reference/keywords/partial-type.md) keyword modifier, as shown here:</span></span>

  [!code-csharp[csProgGuideObjects#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#26)]

<span data-ttu-id="ff089-113">Das Schlüsselwort `partial` gibt an, dass andere Teile der Klasse, Struktur oder Schnittstelle im Namespace definiert werden können.</span><span class="sxs-lookup"><span data-stu-id="ff089-113">The `partial` keyword indicates that other parts of the class, struct, or interface can be defined in the namespace.</span></span> <span data-ttu-id="ff089-114">Alle Teile müssen das Schlüsselwort `partial` verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff089-114">All the parts must use the `partial` keyword.</span></span> <span data-ttu-id="ff089-115">Alle Teile müssen zur Kompilierzeit verfügbar sein, um den endgültigen Typ zu bilden.</span><span class="sxs-lookup"><span data-stu-id="ff089-115">All the parts must be available at compile time to form the final type.</span></span> <span data-ttu-id="ff089-116">Alle Teile müssen die gleiche Zugriffsebene haben, z.B. `public`, `private` usw.</span><span class="sxs-lookup"><span data-stu-id="ff089-116">All the parts must have the same accessibility, such as `public`, `private`, and so on.</span></span>

<span data-ttu-id="ff089-117">Wenn ein beliebiger Teil als abstrakt deklariert wird, wird anschließend der ganze Typ als abstrakt betrachtet.</span><span class="sxs-lookup"><span data-stu-id="ff089-117">If any part is declared abstract, then the whole type is considered abstract.</span></span> <span data-ttu-id="ff089-118">Wenn ein beliebiges Teil als versiegelt deklariert wird, wird anschließend der ganze Typ als versiegelt betrachtet.</span><span class="sxs-lookup"><span data-stu-id="ff089-118">If any part is declared sealed, then the whole type is considered sealed.</span></span> <span data-ttu-id="ff089-119">Wenn ein beliebiger Teil einen Basistyp deklariert, erbt der ganze Typ diese Klasse.</span><span class="sxs-lookup"><span data-stu-id="ff089-119">If any part declares a base type, then the whole type inherits that class.</span></span>

<span data-ttu-id="ff089-120">Alle Teile, die eine Basisklasse angeben, müssen übereinstimmen, aber Teile, die eine Basisklasse auslassen, erben weiterhin den Basistyp.</span><span class="sxs-lookup"><span data-stu-id="ff089-120">All the parts that specify a base class must agree, but parts that omit a base class still inherit the base type.</span></span> <span data-ttu-id="ff089-121">Teile können unterschiedliche Basisschnittstellen angeben, und der letzte Typ implementiert alle Schnittstellen, die von allen Teildeklarationen aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="ff089-121">Parts can specify different base interfaces, and the final type implements all the interfaces listed by all the partial declarations.</span></span> <span data-ttu-id="ff089-122">Alle Klassen-, Struktur- und Schnittstellenmember, die in einer Teildefinition deklariert wurden, sind für alle anderen Teile verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ff089-122">Any class, struct, or interface members declared in a partial definition are available to all the other parts.</span></span> <span data-ttu-id="ff089-123">Der endgültige Typ besteht aus allen Teilen zur Kompilierzeit.</span><span class="sxs-lookup"><span data-stu-id="ff089-123">The final type is the combination of all the parts at compile time.</span></span>

> [!NOTE]
> <span data-ttu-id="ff089-124">Der `partial`-Modifizierer ist nicht für Delegat- oder Enumerationsdeklarationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ff089-124">The `partial` modifier is not available on delegate or enumeration declarations.</span></span>

<span data-ttu-id="ff089-125">Im folgenden Beispiel wird gezeigt, dass geschachtelte Typen eine Teilausführung sein können, selbst wenn der Typ, in dem sie geschachtelt sind, selbst keine ist.</span><span class="sxs-lookup"><span data-stu-id="ff089-125">The following example shows that nested types can be partial, even if the type they are nested within is not partial itself.</span></span>

[!code-csharp[csProgGuideObjects#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#25)]

<span data-ttu-id="ff089-126">Zur Kompilierzeit werden Attribute von partiellen Typdefinitionen zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="ff089-126">At compile time, attributes of partial-type definitions are merged.</span></span> <span data-ttu-id="ff089-127">Betrachten Sie beispielsweise die folgenden Deklarationen:</span><span class="sxs-lookup"><span data-stu-id="ff089-127">For example, consider the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#23)]

<span data-ttu-id="ff089-128">Sie entsprechen den folgenden Deklarationen:</span><span class="sxs-lookup"><span data-stu-id="ff089-128">They are equivalent to the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#24)]

<span data-ttu-id="ff089-129">Die folgenden werden aus allen partiellen Typdefinitionen zusammengeführt:</span><span class="sxs-lookup"><span data-stu-id="ff089-129">The following are merged from all the partial-type definitions:</span></span>

- <span data-ttu-id="ff089-130">XML-Kommentare</span><span class="sxs-lookup"><span data-stu-id="ff089-130">XML comments</span></span>

- <span data-ttu-id="ff089-131">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ff089-131">interfaces</span></span>

- <span data-ttu-id="ff089-132">Generische Parameterattribute</span><span class="sxs-lookup"><span data-stu-id="ff089-132">generic-type parameter attributes</span></span>

- <span data-ttu-id="ff089-133">Klassenattribute</span><span class="sxs-lookup"><span data-stu-id="ff089-133">class attributes</span></span>

- <span data-ttu-id="ff089-134">Member</span><span class="sxs-lookup"><span data-stu-id="ff089-134">members</span></span>

<span data-ttu-id="ff089-135">Betrachten Sie beispielsweise die folgenden Deklarationen:</span><span class="sxs-lookup"><span data-stu-id="ff089-135">For example, consider the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#21)]

<span data-ttu-id="ff089-136">Sie entsprechen den folgenden Deklarationen:</span><span class="sxs-lookup"><span data-stu-id="ff089-136">They are equivalent to the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#22)]

### <a name="restrictions"></a><span data-ttu-id="ff089-137">Beschränkungen</span><span class="sxs-lookup"><span data-stu-id="ff089-137">Restrictions</span></span>

<span data-ttu-id="ff089-138">Es sind mehrere Regeln zu beachten, wenn Sie partielle Klassendefinitionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="ff089-138">There are several rules to follow when you are working with partial class definitions:</span></span>

- <span data-ttu-id="ff089-139">Alle partiellen Typdefinitionen, die als Teile des gleichen Typs vorgesehen sind, müssen mit `partial` geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ff089-139">All partial-type definitions meant to be parts of the same type must be modified with `partial`.</span></span> <span data-ttu-id="ff089-140">Die folgenden Klassendeklarationen erzeugen z.B. einen Fehler:</span><span class="sxs-lookup"><span data-stu-id="ff089-140">For example, the following class declarations generate an error:</span></span>

  [!code-csharp[csProgGuideObjects#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#20)]

- <span data-ttu-id="ff089-141">Der `partial`-Modifizierer kann nur unmittelbar vor den Schlüsselwörtern `class`, `struct` oder `interface` erscheinen.</span><span class="sxs-lookup"><span data-stu-id="ff089-141">The `partial` modifier can only appear immediately before the keywords `class`, `struct`, or `interface`.</span></span>

- <span data-ttu-id="ff089-142">Geschachtelte partielle Typen sind in partiellen Typdefinitionen zulässig, wie im folgenden Beispiel dargestellt wird:</span><span class="sxs-lookup"><span data-stu-id="ff089-142">Nested partial types are allowed in partial-type definitions as illustrated in the following example:</span></span>

  [!code-csharp[csProgGuideObjects#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#19)]

- <span data-ttu-id="ff089-143">Alle partiellen Typdefinitionen, die als Teile des gleichen Typs vorgesehen sind, müssen in der gleichen Assembly und demselben Modul (EXE- oder DLL-Datei) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="ff089-143">All partial-type definitions meant to be parts of the same type must be defined in the same assembly and the same module (.exe or .dll file).</span></span> <span data-ttu-id="ff089-144">Partielle Definitionen können nicht mehrere Module umfassen.</span><span class="sxs-lookup"><span data-stu-id="ff089-144">Partial definitions cannot span multiple modules.</span></span>

- <span data-ttu-id="ff089-145">Der Klassenname und die generischen Typparameter müssen mit allen partiellen Typdefinitionen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="ff089-145">The class name and generic-type parameters must match on all partial-type definitions.</span></span> <span data-ttu-id="ff089-146">Generische Typen können partiell sein.</span><span class="sxs-lookup"><span data-stu-id="ff089-146">Generic types can be partial.</span></span> <span data-ttu-id="ff089-147">Jede partielle Definition muss die gleichen Parameternamen in der gleichen Reihenfolge aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ff089-147">Each partial declaration must use the same parameter names in the same order.</span></span>

- <span data-ttu-id="ff089-148">Die nachfolgenden Schlüsselwörter für eine partielle Typdefinition sind optional, wenn sie aber für eine partielle Definition vorhanden sind, können sie nicht mit anderen Schlüsselwörtern in Konflikt treten, die in anderen partiellen Definitionen desselben Typs angegeben wurden:</span><span class="sxs-lookup"><span data-stu-id="ff089-148">The following keywords on a partial-type definition are optional, but if present on one partial-type definition, cannot conflict with the keywords specified on another partial definition for the same type:</span></span>

  - [<span data-ttu-id="ff089-149">public</span><span class="sxs-lookup"><span data-stu-id="ff089-149">public</span></span>](../../language-reference/keywords/public.md)

  - [<span data-ttu-id="ff089-150">private</span><span class="sxs-lookup"><span data-stu-id="ff089-150">private</span></span>](../../language-reference/keywords/private.md)

  - [<span data-ttu-id="ff089-151">protected</span><span class="sxs-lookup"><span data-stu-id="ff089-151">protected</span></span>](../../language-reference/keywords/protected.md)

  - [<span data-ttu-id="ff089-152">internal</span><span class="sxs-lookup"><span data-stu-id="ff089-152">internal</span></span>](../../language-reference/keywords/internal.md)

  - [<span data-ttu-id="ff089-153">abstract</span><span class="sxs-lookup"><span data-stu-id="ff089-153">abstract</span></span>](../../language-reference/keywords/abstract.md)

  - [<span data-ttu-id="ff089-154">sealed</span><span class="sxs-lookup"><span data-stu-id="ff089-154">sealed</span></span>](../../language-reference/keywords/sealed.md)

  - <span data-ttu-id="ff089-155">Basisklasse</span><span class="sxs-lookup"><span data-stu-id="ff089-155">base class</span></span>

  - <span data-ttu-id="ff089-156">[new](../../language-reference/keywords/new-modifier.md)-Modifizierer (geschachtelte Teile)</span><span class="sxs-lookup"><span data-stu-id="ff089-156">[new](../../language-reference/keywords/new-modifier.md) modifier (nested parts)</span></span>

  - <span data-ttu-id="ff089-157">Generische Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="ff089-157">generic constraints</span></span>

<span data-ttu-id="ff089-158">Weitere Informationen finden Sie unter [Einschränkungen für Typparameter](../generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="ff089-158">For more information, see [Constraints on Type Parameters](../generics/constraints-on-type-parameters.md).</span></span>

## <a name="example-1"></a><span data-ttu-id="ff089-159">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="ff089-159">Example 1</span></span>

### <a name="description"></a><span data-ttu-id="ff089-160">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff089-160">Description</span></span>

<span data-ttu-id="ff089-161">Im folgenden Beispiel werden die Felder und der Konstruktor der Klasse (`Coords`) in einer partiellen Klassendefinition deklariert, und der Member (`PrintCoords`) wird in einer anderen partiellen Klassendefinition deklariert.</span><span class="sxs-lookup"><span data-stu-id="ff089-161">In the following example, the fields and the constructor of the class, `Coords`, are declared in one partial class definition, and the member, `PrintCoords`, is declared in another partial class definition.</span></span>

### <a name="code"></a><span data-ttu-id="ff089-162">Code</span><span class="sxs-lookup"><span data-stu-id="ff089-162">Code</span></span>

[!code-csharp[csProgGuideObjects#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#17)]

## <a name="example-2"></a><span data-ttu-id="ff089-163">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="ff089-163">Example 2</span></span>

### <a name="description"></a><span data-ttu-id="ff089-164">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff089-164">Description</span></span>

<span data-ttu-id="ff089-165">Im folgenden Beispiel wird gezeigt, dass Sie auch partielle Strukturen und Schnittstellen entwickeln können.</span><span class="sxs-lookup"><span data-stu-id="ff089-165">The following example shows that you can also develop partial structs and interfaces.</span></span>

### <a name="code"></a><span data-ttu-id="ff089-166">Code</span><span class="sxs-lookup"><span data-stu-id="ff089-166">Code</span></span>

[!code-csharp[csProgGuideObjects#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#18)]

## <a name="partial-methods"></a><span data-ttu-id="ff089-167">Partielle Methoden</span><span class="sxs-lookup"><span data-stu-id="ff089-167">Partial Methods</span></span>

<span data-ttu-id="ff089-168">Eine partielle Klasse oder Struktur kann eine partielle Methode enthalten.</span><span class="sxs-lookup"><span data-stu-id="ff089-168">A partial class or struct may contain a partial method.</span></span> <span data-ttu-id="ff089-169">Ein Teil der Klasse enthält die Signatur der Methode.</span><span class="sxs-lookup"><span data-stu-id="ff089-169">One part of the class contains the signature of the method.</span></span> <span data-ttu-id="ff089-170">Eine optionale Implementierung kann im gleichen oder in einem anderen Teil definiert werden.</span><span class="sxs-lookup"><span data-stu-id="ff089-170">An optional implementation may be defined in the same part or another part.</span></span> <span data-ttu-id="ff089-171">Wenn die Implementierung nicht bereitgestellt wird, werden anschließend die Methode sowie alle Aufrufe an die Methode zur Kompilierzeit entfernt.</span><span class="sxs-lookup"><span data-stu-id="ff089-171">If the implementation is not supplied, then the method and all calls to the method are removed at compile time.</span></span>

<span data-ttu-id="ff089-172">Mit partiellen Methoden kann der Implementierer des einen Teils einer Klasse eine Methode definieren, die einem Ereignis ähnelt.</span><span class="sxs-lookup"><span data-stu-id="ff089-172">Partial methods enable the implementer of one part of a class to define a method, similar to an event.</span></span> <span data-ttu-id="ff089-173">Der Implementierer des anderen Teils der Klasse kann entscheiden, ob die Methode implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="ff089-173">The implementer of the other part of the class can decide whether to implement the method or not.</span></span> <span data-ttu-id="ff089-174">Wenn die Methode nicht implementiert wird, kann der Compiler anschließend die Methodensignatur und alle Aufrufe an die Methode entfernen.</span><span class="sxs-lookup"><span data-stu-id="ff089-174">If the method is not implemented, then the compiler removes the method signature and all calls to the method.</span></span> <span data-ttu-id="ff089-175">Die Aufrufe an die Methode, einschließlich Ergebnissen, die bei der Auswertung eines Arguments im Aufruf auftreten würden, haben zur Laufzeit keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="ff089-175">The calls to the method, including any results that would occur from evaluation of arguments in the calls, have no effect at run time.</span></span> <span data-ttu-id="ff089-176">Deshalb kann jeder Code in der partiellen Klasse eine partielle Methode frei verwenden, selbst wenn die Implementation nicht bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ff089-176">Therefore, any code in the partial class can freely use a partial method, even if the implementation is not supplied.</span></span> <span data-ttu-id="ff089-177">Es ergeben sich keine Laufzeit- oder Kompilierzeitfehler, wenn die Methode aufgerufen, aber nicht implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="ff089-177">No compile-time or run-time errors will result if the method is called but not implemented.</span></span>

<span data-ttu-id="ff089-178">Partielle Methoden sind besonders nützlich, um generierten Code anzupassen.</span><span class="sxs-lookup"><span data-stu-id="ff089-178">Partial methods are especially useful as a way to customize generated code.</span></span> <span data-ttu-id="ff089-179">Sie ermöglichen, dass Methodenname und -signatur reserviert werden können, sodass generierter Code die Methode aufrufen kann, aber der Entwickler über die Implementierung der Methode entscheiden kann.</span><span class="sxs-lookup"><span data-stu-id="ff089-179">They allow for a method name and signature to be reserved, so that generated code can call the method but the developer can decide whether to implement the method.</span></span> <span data-ttu-id="ff089-180">Wie partielle Klassen ermöglichen partielle Methoden, dass Code, der von einem Codegenerator erstellt wurde, zusammen mit Code, der von einem menschlichen Entwickler erstellt wurde, ohne Laufzeitkosten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ff089-180">Much like partial classes, partial methods enable code created by a code generator and code created by a human developer to work together without run-time costs.</span></span>

<span data-ttu-id="ff089-181">Eine partielle Methodendeklaration besteht aus zwei Teilen: der Definition und der Implementierung.</span><span class="sxs-lookup"><span data-stu-id="ff089-181">A partial method declaration consists of two parts: the definition, and the implementation.</span></span> <span data-ttu-id="ff089-182">Diese können in separaten Teilen einer partiellen Klasse oder im gleichen Teil sein.</span><span class="sxs-lookup"><span data-stu-id="ff089-182">These may be in separate parts of a partial class, or in the same part.</span></span> <span data-ttu-id="ff089-183">Wenn es keine Implementierungsdeklaration gibt, optimiert der Compiler anschließend sowohl die definierende Deklaration als auch alle Aufrufe an die Methode.</span><span class="sxs-lookup"><span data-stu-id="ff089-183">If there is no implementation declaration, then the compiler optimizes away both the defining declaration and all calls to the method.</span></span>

```csharp
// Definition in file1.cs
partial void onNameChanged();

// Implementation in file2.cs
partial void onNameChanged()
{
  // method body
}
```

- <span data-ttu-id="ff089-184">Partielle Methodendeklarationen müssen mit dem Kontextschlüsselwort [partial](../../language-reference/keywords/partial-type.md) beginnen, und die Methode muss [void](../../language-reference/builtin-types/void.md) zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="ff089-184">Partial method declarations must begin with the contextual keyword [partial](../../language-reference/keywords/partial-type.md) and the method must return [void](../../language-reference/builtin-types/void.md).</span></span>

- <span data-ttu-id="ff089-185">Partielle Methoden können [in](../../language-reference/keywords/in-parameter-modifier.md)- oder [ref](../../language-reference/keywords/ref.md)-Parameter, aber keine [out](../../language-reference/keywords/out-parameter-modifier.md)-Parameter besitzen.</span><span class="sxs-lookup"><span data-stu-id="ff089-185">Partial methods can have [in](../../language-reference/keywords/in-parameter-modifier.md) or [ref](../../language-reference/keywords/ref.md) but not [out](../../language-reference/keywords/out-parameter-modifier.md) parameters.</span></span>

- <span data-ttu-id="ff089-186">Partielle Methoden sind implizit [privat](../../language-reference/keywords/private.md) und können daher nicht [virtuell](../../language-reference/keywords/virtual.md) sein.</span><span class="sxs-lookup"><span data-stu-id="ff089-186">Partial methods are implicitly [private](../../language-reference/keywords/private.md), and therefore they cannot be [virtual](../../language-reference/keywords/virtual.md).</span></span>

- <span data-ttu-id="ff089-187">Partielle Methoden können nicht [extern](../../language-reference/keywords/extern.md) sein, da das Vorhandensein des Texts bestimmt, ob sie definierend oder implementierend sind.</span><span class="sxs-lookup"><span data-stu-id="ff089-187">Partial methods cannot be [extern](../../language-reference/keywords/extern.md), because the presence of the body determines whether they are defining or implementing.</span></span>

- <span data-ttu-id="ff089-188">Partielle Methoden können [statische](../../language-reference/keywords/static.md) und [unsichere](../../language-reference/keywords/unsafe.md) Modifizierer besitzen.</span><span class="sxs-lookup"><span data-stu-id="ff089-188">Partial methods can have [static](../../language-reference/keywords/static.md) and [unsafe](../../language-reference/keywords/unsafe.md) modifiers.</span></span>

- <span data-ttu-id="ff089-189">Partielle Methoden können generisch sein.</span><span class="sxs-lookup"><span data-stu-id="ff089-189">Partial methods can be generic.</span></span> <span data-ttu-id="ff089-190">Einschränkungen gelten für die definierende partielle Methodendeklaration und können optional für die implementierende wiederholt werden.</span><span class="sxs-lookup"><span data-stu-id="ff089-190">Constraints are put on the defining partial method declaration, and may optionally be repeated on the implementing one.</span></span> <span data-ttu-id="ff089-191">Parameter- und Typparameternamen müssen in der implementierenden und definierenden Deklaration nicht gleich sein.</span><span class="sxs-lookup"><span data-stu-id="ff089-191">Parameter and type parameter names do not have to be the same in the implementing declaration as in the defining one.</span></span>

- <span data-ttu-id="ff089-192">Sie können einen [Delegaten](../../language-reference/builtin-types/reference-types.md) für eine partielle Methode erstellen, die definiert und implementiert wurde. Dies geht jedoch nicht für partielle Methoden, die nur definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ff089-192">You can make a [delegate](../../language-reference/builtin-types/reference-types.md) to a partial method that has been defined and implemented, but not to a partial method that has only been defined.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ff089-193">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="ff089-193">C# Language Specification</span></span>

<span data-ttu-id="ff089-194">Weitere Informationen finden Sie unter [Partielle Datentypen](~/_csharplang/spec/classes.md#partial-types) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="ff089-194">For more information, see [Partial types](~/_csharplang/spec/classes.md#partial-types) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="ff089-195">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="ff089-195">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff089-196">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff089-196">See also</span></span>

- [<span data-ttu-id="ff089-197">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ff089-197">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ff089-198">Klassen</span><span class="sxs-lookup"><span data-stu-id="ff089-198">Classes</span></span>](./classes.md)
- [<span data-ttu-id="ff089-199">Strukturtypen</span><span class="sxs-lookup"><span data-stu-id="ff089-199">Structure types</span></span>](../../language-reference/builtin-types/struct.md)
- [<span data-ttu-id="ff089-200">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ff089-200">Interfaces</span></span>](../interfaces/index.md)
- [<span data-ttu-id="ff089-201">partial (Typ)</span><span class="sxs-lookup"><span data-stu-id="ff089-201">partial (Type)</span></span>](../../language-reference/keywords/partial-type.md)
