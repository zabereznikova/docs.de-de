---
title: System.Delegate und das `delegate`-Schlüsselwort
description: Informationen zu den Klassen in .NET, die Delegaten unterstützen, und wie diese zum Schlüsselwort „delegate“ zugeordnet werden.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: f3742fda-13c2-4283-8966-9e21c2674393
ms.openlocfilehash: 9df8ad68f6bfa62863ee047875b6419fc81ad779
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062462"
---
# <a name="systemdelegate-and-the-delegate-keyword"></a><span data-ttu-id="9ae4f-103">System.Delegate und das `delegate`-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="9ae4f-103">System.Delegate and the `delegate` keyword</span></span>

[<span data-ttu-id="9ae4f-104">Zurück</span><span class="sxs-lookup"><span data-stu-id="9ae4f-104">Previous</span></span>](delegates-overview.md)

<span data-ttu-id="9ae4f-105">Dieser Artikel enthält Informationen zu den Klassen in .NET, die Delegaten unterstützen, und wie diese dem Schlüsselwort `delegate` zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-105">This article covers the classes in .NET that support delegates, and how those map to the `delegate` keyword.</span></span>

## <a name="define-delegate-types"></a><span data-ttu-id="9ae4f-106">Definieren von Delegattypen</span><span class="sxs-lookup"><span data-stu-id="9ae4f-106">Define delegate types</span></span>

<span data-ttu-id="9ae4f-107">Wir beginnen mit dem Schlüsselwort „delegate“, da Sie dieses beim Arbeiten mit Delegaten hauptsächlich verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-107">Let's start with the 'delegate' keyword, because that's primarily what you will use as you work with delegates.</span></span> <span data-ttu-id="9ae4f-108">Der Code, der vom Compiler bei Verwendung des `delegate`-Schlüsselworts generiert wird, verweist auf Methodenaufrufe, die Member der Klassen <xref:System.Delegate> und <xref:System.MulticastDelegate> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-108">The code that the compiler generates when you use the `delegate` keyword will map to method calls that invoke members of the <xref:System.Delegate> and <xref:System.MulticastDelegate> classes.</span></span>

<span data-ttu-id="9ae4f-109">Sie definieren einen Delegattyp, der Syntax verwendet, die dem Definieren einer Methodensignatur ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-109">You define a delegate type using syntax that is similar to defining a method signature.</span></span> <span data-ttu-id="9ae4f-110">Sie fügen das `delegate`-Schlüsselwort einfach der Definition hinzu.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-110">You just add the `delegate` keyword to the definition.</span></span>

<span data-ttu-id="9ae4f-111">Wir verwenden die List.Sort()-Methode weiterhin als Beispiel.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-111">Let's continue to use the List.Sort() method as our example.</span></span> <span data-ttu-id="9ae4f-112">Der erste Schritt ist die Erstellung eines Typs für den Vergleichsdelegaten:</span><span class="sxs-lookup"><span data-stu-id="9ae4f-112">The first step is to create a type for the comparison delegate:</span></span>

```csharp
// From the .NET Core library

// Define the delegate type:
public delegate int Comparison<in T>(T left, T right);
```

<span data-ttu-id="9ae4f-113">Der Compiler generiert eine von `System.Delegate` abgeleitete Klasse, die der verwendeten Signatur entspricht (in diesem Fall eine Methode, die eine ganze Zahl zurückgibt und über zwei Argumente verfügt).</span><span class="sxs-lookup"><span data-stu-id="9ae4f-113">The compiler generates a class, derived from `System.Delegate` that matches the signature used (in this case, a method that returns an integer, and has two arguments).</span></span> <span data-ttu-id="9ae4f-114">Der Typ des Delegaten ist `Comparison`.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-114">The type of that delegate is `Comparison`.</span></span> <span data-ttu-id="9ae4f-115">Der Delegattyp `Comparison` ist ein generischer Typ.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-115">The `Comparison` delegate type is a generic type.</span></span> <span data-ttu-id="9ae4f-116">Weitere Informationen zu Generics finden Sie [hier](programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="9ae4f-116">For details on generics see [here](programming-guide/generics/index.md).</span></span>

<span data-ttu-id="9ae4f-117">Beachten Sie, dass es so scheinen kann, als ob die Syntax eine Variable deklariert, aber tatsächlich deklariert sie einen *Typ*.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-117">Notice that the syntax may appear as though it is declaring a variable, but it is actually declaring a *type*.</span></span> <span data-ttu-id="9ae4f-118">Sie können Delegattypen innerhalb von Klassen, direkt in Namespaces oder sogar im globalen Namespace definieren.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-118">You can define delegate types inside classes, directly inside namespaces, or even in the global namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="9ae4f-119">Es wird nicht empfohlen, Delegattypen (oder andere Typen) direkt im globalen Namespace zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-119">Declaring delegate types (or other types) directly in the global namespace is not recommended.</span></span>

<span data-ttu-id="9ae4f-120">Der Compiler generiert auch Handler zum Hinzufügen und Entfernen für diesen neuen Typ, damit Clients dieser Klasse Methoden der Aufrufliste einer Instanz hinzufügen und entfernen können.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-120">The compiler also generates add and remove handlers for this new type so that clients of this class can add and remove methods from an instance's invocation list.</span></span> <span data-ttu-id="9ae4f-121">Der Compiler erzwingt, dass die Signatur der Methode, die hinzugefügt oder entfernt wird, der Signatur bei der Deklaration der Methode entspricht.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-121">The compiler will enforce that the signature of the method being added or removed matches the signature used when declaring the method.</span></span>

## <a name="declare-instances-of-delegates"></a><span data-ttu-id="9ae4f-122">Deklarieren von Instanzen von Delegaten</span><span class="sxs-lookup"><span data-stu-id="9ae4f-122">Declare instances of delegates</span></span>

<span data-ttu-id="9ae4f-123">Nach dem Definieren des Delegats können Sie eine Instanz dieses Typs erstellen.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-123">After defining the delegate, you can create an instance of that type.</span></span>
<span data-ttu-id="9ae4f-124">Wie alle Variablen in C# können Sie Delegatinstanzen nicht direkt in einem Namespace oder im globalen Namespace deklarieren.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-124">Like all variables in C#, you cannot declare delegate instances directly in a namespace, or in the global namespace.</span></span>

```csharp
// inside a class definition:

// Declare an instance of that type:
public Comparison<T> comparator;
```

<span data-ttu-id="9ae4f-125">Der Typ der Variable ist `Comparison<T>`, der zuvor definierte Delegattyp.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-125">The type of the variable is `Comparison<T>`, the delegate type defined earlier.</span></span> <span data-ttu-id="9ae4f-126">Der Name der Variablen ist `comparator`.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-126">The name of the variable is `comparator`.</span></span>

 <span data-ttu-id="9ae4f-127">Dieser obenstehende Codeausschnitt hat eine Membervariable innerhalb einer Klasse deklariert.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-127">That code snippet above declared a member variable inside a class.</span></span> <span data-ttu-id="9ae4f-128">Sie können auch Delegatvariablen deklarieren, die lokale Variablen oder Argumente von Methoden sind.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-128">You can also declare delegate variables that are local variables, or arguments to methods.</span></span>

## <a name="invoke-delegates"></a><span data-ttu-id="9ae4f-129">Aufrufen von Delegaten</span><span class="sxs-lookup"><span data-stu-id="9ae4f-129">Invoke delegates</span></span>

<span data-ttu-id="9ae4f-130">Sie rufen die Methoden in der Aufrufliste eines Delegaten auf, indem Sie diesen Delegaten aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-130">You invoke the methods that are in the invocation list of a delegate by calling that delegate.</span></span> <span data-ttu-id="9ae4f-131">In der `Sort()`-Methode ruft der Code die Vergleichsmethode an, um zu bestimmen, in welcher Reihenfolge er die Objekte anordnet:</span><span class="sxs-lookup"><span data-stu-id="9ae4f-131">Inside the `Sort()` method, the code will call the comparison method to determine which order to place objects:</span></span>

```csharp
int result = comparator(left, right);
```

<span data-ttu-id="9ae4f-132">In der Zeile darüber *ruft* der Code die Methode auf, die an den Delegaten angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-132">In the line above, the code *invokes* the method attached to the delegate.</span></span>
<span data-ttu-id="9ae4f-133">Sie behandeln die Variable als Methodenname und rufen sie mit der üblichen Syntax für Methodenaufrufe auf.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-133">You treat the variable as a method name, and invoke it using normal method call syntax.</span></span>

<span data-ttu-id="9ae4f-134">Diese Codezeile macht eine unsichere Annahme: Es gibt keine Garantie, dass dem Delegaten ein Ziel hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-134">That line of code makes an unsafe assumption: There's no guarantee that a target has been added to the delegate.</span></span> <span data-ttu-id="9ae4f-135">Wenn keine Ziele angehängt wurden, löst die Zeile darüber eine `NullReferenceException` aus.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-135">If no targets have been attached, the line above would cause a `NullReferenceException` to be thrown.</span></span> <span data-ttu-id="9ae4f-136">Die Ausdrücke, die verwendet werden, um dieses Problem zu beheben, sind komplizierter als eine einfache NULL-Überprüfung und werden später in dieser [Reihe](delegates-patterns.md) behandelt.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-136">The idioms used to address this problem are more complicated than a simple null-check, and are covered later in this [series](delegates-patterns.md).</span></span>

## <a name="assign-add-and-remove-invocation-targets"></a><span data-ttu-id="9ae4f-137">Zuweisen, Hinzufügen und Entfernen von Aufrufzielen</span><span class="sxs-lookup"><span data-stu-id="9ae4f-137">Assign, add, and remove invocation targets</span></span>

<span data-ttu-id="9ae4f-138">So werden Delegattypen definiert und Delegatinstanzen deklariert und aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-138">That's how a delegate type is defined, and how delegate instances are declared and invoked.</span></span>

<span data-ttu-id="9ae4f-139">Entwickler, die die `List.Sort()`-Methode verwenden möchten, müssen eine Methode definieren, deren Signatur der Definition des Delegattypen entspricht, und diese dem Delegaten zuweisen, der von der sort-Methode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-139">Developers that want to use the `List.Sort()` method need to define a method whose signature matches the delegate type definition, and assign it to the delegate used by the sort method.</span></span> <span data-ttu-id="9ae4f-140">Diese Zuordnung fügt die Methode der Aufrufliste des Delegatobjekts hinzu.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-140">This assignment adds the method to the invocation list of that delegate object.</span></span>

<span data-ttu-id="9ae4f-141">Nehmen wir an, Sie möchten eine Liste von Zeichenfolgen nach Länge sortieren.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-141">Suppose you wanted to sort a list of strings by their length.</span></span> <span data-ttu-id="9ae4f-142">Die Vergleichsfunktion kann folgende sein:</span><span class="sxs-lookup"><span data-stu-id="9ae4f-142">Your comparison function might be the following:</span></span>

```csharp
private static int CompareLength(string left, string right) =>
    left.Length.CompareTo(right.Length);
```

<span data-ttu-id="9ae4f-143">Die Methode wird als private Methode deklariert.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-143">The method is declared as a private method.</span></span> <span data-ttu-id="9ae4f-144">Das ist in Ordnung.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-144">That's fine.</span></span> <span data-ttu-id="9ae4f-145">Möglicherweise möchten Sie nicht, dass diese Methode Teil der öffentlichen Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-145">You may not want this method to be part of your public interface.</span></span> <span data-ttu-id="9ae4f-146">Sie kann dennoch als Vergleichsmethode verwendet werden, wenn sie an einen Delegaten angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-146">It can still be used as the comparison method when attached to a delegate.</span></span> <span data-ttu-id="9ae4f-147">Der aufrufende Code wird diese Methode an die Zielliste des Delegatobjekts anfügen lassen und kann über diesen Delegaten darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-147">The calling code will have this method attached to the target list of the delegate object, and can access it through that delegate.</span></span>

<span data-ttu-id="9ae4f-148">Sie erstellen diese Beziehung durch Übergeben dieser Methode an die `List.Sort()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="9ae4f-148">You create that relationship by passing that method to the `List.Sort()` method:</span></span>

```csharp
phrases.Sort(CompareLength);
```

<span data-ttu-id="9ae4f-149">Beachten Sie, dass der Name der Methode ohne Klammern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-149">Notice that the method name is used, without parentheses.</span></span> <span data-ttu-id="9ae4f-150">Das Verwenden der Methode als Argument teilt dem Compiler mit, dass er den Methodenverweis in einen Verweis konvertieren soll, der als Delegataufrufziel verwendet werden kann, und diese Methode als Aufrufziel anfügen soll.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-150">Using the method as an argument tells the compiler to convert the method reference into a reference that can be used as a delegate invocation target, and attach that method as an invocation target.</span></span>

<span data-ttu-id="9ae4f-151">Sie könnten auch explizit eine Variable vom Typ `Comparison<string>` deklarieren und diese zuweisen:</span><span class="sxs-lookup"><span data-stu-id="9ae4f-151">You could also have been explicit by declaring a variable of type `Comparison<string>` and doing an assignment:</span></span>

```csharp
Comparison<string> comparer = CompareLength;
phrases.Sort(comparer);
```

<span data-ttu-id="9ae4f-152">Wenn es sich bei der als Delegatziel verwendeten Methode um eine kleine Methode handelt, wird gewöhnlich die [Lambdaausdruck](language-reference/operators/lambda-expressions.md)-Syntax für die Durchführung der Zuweisung verwendet:</span><span class="sxs-lookup"><span data-stu-id="9ae4f-152">In uses where the method being used as a delegate target is a small method, it's common to use [lambda expression](language-reference/operators/lambda-expressions.md) syntax to perform the assignment:</span></span>

```csharp
Comparison<string> comparer = (left, right) => left.Length.CompareTo(right.Length);
phrases.Sort(comparer);
```

<span data-ttu-id="9ae4f-153">Die Verwendung von Lambdaausdrücken für Delegatziele wird in einem [späteren Abschnitt](delegates-patterns.md) ausführlicher behandelt.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-153">Using lambda expressions for delegate targets is covered more in a [later section](delegates-patterns.md).</span></span>

<span data-ttu-id="9ae4f-154">Das Sort()-Beispiel fügt dem Delegaten typischerweise eine einzelne Zielmethode an.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-154">The Sort() example typically attaches a single target method to the delegate.</span></span> <span data-ttu-id="9ae4f-155">Allerdings unterstützen Delegatobjekte Aufruflisten mit mehreren Zielmethoden, die an ein Delegatobjekt angefügt sind.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-155">However, delegate objects do support invocation lists that have multiple target methods attached to a delegate object.</span></span>

## <a name="delegate-and-multicastdelegate-classes"></a><span data-ttu-id="9ae4f-156">Delegatklassen und MulticastDelegate-Klassen</span><span class="sxs-lookup"><span data-stu-id="9ae4f-156">Delegate and MulticastDelegate classes</span></span>

<span data-ttu-id="9ae4f-157">Die oben beschriebene Sprachunterstützung bietet die Funktionen und Unterstützung, die Sie in der Regel bei der Arbeit mit Delegaten benötigen.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-157">The language support described above provides the features and support you'll typically need to work with delegates.</span></span> <span data-ttu-id="9ae4f-158">Diese Features beruhen auf zwei Klassen im .NET Core Framework: <xref:System.Delegate> und <xref:System.MulticastDelegate>.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-158">These features are built on two classes in the .NET Core framework: <xref:System.Delegate> and <xref:System.MulticastDelegate>.</span></span>

<span data-ttu-id="9ae4f-159">Die `System.Delegate`-Klasse und ihre einzige direkte untergeordnete Klasse `System.MulticastDelegate` bieten die Framework-Unterstützung für das Erstellen von Delegaten, das Registrieren von Methoden als Delegatziele und das Aufrufen aller Methoden, die als Delegatziel registriert sind.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-159">The `System.Delegate` class and its single direct subclass, `System.MulticastDelegate`, provide the framework support for creating delegates, registering methods as delegate targets, and invoking all methods that are registered as a delegate target.</span></span>

<span data-ttu-id="9ae4f-160">Interessanterweise sind die Klassen `System.Delegate` und `System.MulticastDelegate` selbst keine Delegattypen.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-160">Interestingly, the `System.Delegate` and `System.MulticastDelegate` classes are not themselves delegate types.</span></span> <span data-ttu-id="9ae4f-161">Sie bieten die Grundlage für alle spezifischen Delegattypen.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-161">They do provide the basis for all specific delegate types.</span></span> <span data-ttu-id="9ae4f-162">Derselbe Sprachentwurfsprozess verlangte, dass keine Klasse deklariert werden kann, die von `Delegate` oder `MulticastDelegate` abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-162">That same language design process mandated that you cannot declare a class that derives from `Delegate` or `MulticastDelegate`.</span></span> <span data-ttu-id="9ae4f-163">Die C#-Sprachregeln verbieten dies.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-163">The C# language rules prohibit it.</span></span>

<span data-ttu-id="9ae4f-164">Stattdessen erstellt der C#-Compiler Instanzen einer von `MulticastDelegate` abgeleiteten Klasse, wenn Sie das C#-Schlüsselwort verwenden, um Delegattypen zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-164">Instead, the C# compiler creates instances of a class derived from `MulticastDelegate` when you use the C# language keyword to declare delegate types.</span></span>

<span data-ttu-id="9ae4f-165">Dieser Entwurf hat seinen Ursprung in der ersten Version von C# und .NET.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-165">This design has its roots in the first release of C# and .NET.</span></span> <span data-ttu-id="9ae4f-166">Ein Ziel des Entwurfsteams war sicherzustellen, dass die Sprache bei der Verwendung von Delegaten Typsicherheit erzwingt.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-166">One goal for the design team was to ensure that the language enforced type safety when using delegates.</span></span> <span data-ttu-id="9ae4f-167">Dies bedeutete sicherzustellen, dass Delegaten mit dem richtigen Typ und der richtigen Anzahl von Argumenten aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-167">That meant ensuring that delegates were invoked with the right type and number of arguments.</span></span> <span data-ttu-id="9ae4f-168">Zudem sollte jeder Rückgabetyp zur Kompilierzeit richtig angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-168">And, that any return type was correctly indicated at compile time.</span></span> <span data-ttu-id="9ae4f-169">Delegaten waren Teil von .NET Version 1.0, die es vor Generics gab.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-169">Delegates were part of the 1.0 .NET release, which was before generics.</span></span>

<span data-ttu-id="9ae4f-170">Die beste Möglichkeit, diese Typsicherheit zu erzwingen, bestand darin, dass der Compiler die konkreten Delegatklassen erstellt, die die verwendete Methodensignatur darstellten.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-170">The best way to enforce this type safety was for the compiler to create the concrete delegate classes that represented the method signature being used.</span></span>

<span data-ttu-id="9ae4f-171">Obwohl Sie abgeleitete Klassen nicht direkt erstellen können, verwenden Sie die Methoden, die auf diesen Klassen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-171">Even though you cannot create derived classes directly, you will use the methods defined on these classes.</span></span> <span data-ttu-id="9ae4f-172">Nun sehen wir uns die am häufigsten verwendeten Methoden an, die Sie beim Arbeiten mit Delegaten verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-172">Let's go through the most common methods that you will use when you work with delegates.</span></span>

<span data-ttu-id="9ae4f-173">An erster Stelle müssen Sie beachten, dass jeder Delegat, mit dem Sie arbeiten, von `MulticastDelegate` abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-173">The first, most important fact to remember is that every delegate you work with is derived from `MulticastDelegate`.</span></span> <span data-ttu-id="9ae4f-174">Ein Multicastdelegat bedeutet, dass mehr als ein Methodenziel beim Aufrufen über einen Delegaten aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-174">A multicast delegate means that more than one method target can be invoked when invoking through a delegate.</span></span> <span data-ttu-id="9ae4f-175">Der ursprüngliche Entwurf sah eine Unterscheidung vor zwischen Delegaten, bei denen nur eine Zielmethode angefügt und aufgerufen werden konnte, und Delegaten, bei denen mehrere Zielmethoden angefügt und aufgerufen werden konnten.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-175">The original design considered making a distinction between delegates where only one target method could be attached and invoked, and delegates where multiple target methods could be attached and invoked.</span></span> <span data-ttu-id="9ae4f-176">Diese Unterscheidung erwies sich in der Praxis jedoch als weniger nützlich als ursprünglich gedacht.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-176">That distinction proved to be less useful in practice than originally thought.</span></span> <span data-ttu-id="9ae4f-177">Die zwei verschiedenen Klassen wurden bereits erstellt und befinden sich seit der ersten Veröffentlichung im Framework.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-177">The two different classes were already created, and have been in the framework since its initial public release.</span></span>

<span data-ttu-id="9ae4f-178">Die Methoden, die Sie bei der Arbeit mit Delegaten am häufigsten verwenden, sind `Invoke()` und `BeginInvoke()` / `EndInvoke()`.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-178">The methods that you will use the most with delegates are `Invoke()` and `BeginInvoke()` / `EndInvoke()`.</span></span> <span data-ttu-id="9ae4f-179">`Invoke()` ruft alle Methoden auf, die an eine bestimmte Delegatinstanz angefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-179">`Invoke()` will invoke all the methods that have been attached to a particular delegate instance.</span></span> <span data-ttu-id="9ae4f-180">Wie oben gezeigt, werden Delegaten in der Regel mit der Aufrufsyntax-Methode auf der Delegatvariablen aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-180">As you saw above, you typically invoke delegates using the method call syntax on the delegate variable.</span></span> <span data-ttu-id="9ae4f-181">Wie Sie [später in dieser Reihe](delegates-patterns.md) sehen werden, gibt es Muster, die direkt mit diesen Methoden arbeiten.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-181">As you'll see [later in this series](delegates-patterns.md), there are patterns that work directly with these methods.</span></span>

<span data-ttu-id="9ae4f-182">Nun haben Sie die Sprachsyntax und die Klassen gesehen, die Delegaten unterstützen. Als Nächstes untersuchen wir, wie stark typisierte Delegaten verwendet, erstellt und aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9ae4f-182">Now that you've seen the language syntax and the classes that support delegates, let's examine how strongly typed delegates are used, created, and invoked.</span></span>

[<span data-ttu-id="9ae4f-183">Nächste</span><span class="sxs-lookup"><span data-stu-id="9ae4f-183">Next</span></span>](delegates-strongly-typed.md)
