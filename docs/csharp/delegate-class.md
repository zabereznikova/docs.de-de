---
title: "System.Delegate und das Schlüsselwort „delegate“"
description: "Informationen zu den Klassen in .NET Framework, die Delegaten unterstützen, und wie diese zum Schlüsselwort „delegate“ zugeordnet werden."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: f3742fda-13c2-4283-8966-9e21c2674393
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 465326fe520d6a062609e0c4c471135ef88b0dd6
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="systemdelegate-and-the-delegate-keyword"></a><span data-ttu-id="bac04-104">System.Delegate und das `delegate`-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="bac04-104">System.Delegate and the `delegate` keyword</span></span>

[<span data-ttu-id="bac04-105">Zurück</span><span class="sxs-lookup"><span data-stu-id="bac04-105">Previous</span></span>](delegates-overview.md)

<span data-ttu-id="bac04-106">Dieser Artikel behandelt die Klassen in .NET Framework, die Delegaten unterstützen, und wie diese zum `delegate`-Schlüsselwort zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="bac04-106">This article will cover the classes in the .NET framework that support delegates, and how those map to the `delegate` keyword.</span></span>

## <a name="defining-delegate-types"></a><span data-ttu-id="bac04-107">Definieren von Delegattypen</span><span class="sxs-lookup"><span data-stu-id="bac04-107">Defining Delegate Types</span></span>

<span data-ttu-id="bac04-108">Wir beginnen mit dem Schlüsselwort „delegate“, da Sie dieses beim Arbeiten mit Delegaten hauptsächlich verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="bac04-108">Let's start with the 'delegate' keyword, because that's primarily what you will use as you work with delegates.</span></span> <span data-ttu-id="bac04-109">Der Code, der vom Compiler bei Verwendung des `delegate`-Schlüsselworts generiert wird, verweist auf Methodenaufrufe, die Member der Klassen @System.Delegate und @System.MulticastDelegate aufrufen.</span><span class="sxs-lookup"><span data-stu-id="bac04-109">The code that the compiler generates when you use the `delegate` keyword will map to method calls that invoke members of the @System.Delegate and @System.MulticastDelegate classes.</span></span> 

<span data-ttu-id="bac04-110">Sie definieren einen Delegattyp, der Syntax verwendet, die dem Definieren einer Methodensignatur ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="bac04-110">You define a delegate type using syntax that is similar to defining a method signature.</span></span> <span data-ttu-id="bac04-111">Sie fügen das `delegate`-Schlüsselwort einfach der Definition hinzu.</span><span class="sxs-lookup"><span data-stu-id="bac04-111">You just add the `delegate` keyword to the definition.</span></span>

<span data-ttu-id="bac04-112">Wir verwenden die List.Sort()-Methode weiterhin als Beispiel.</span><span class="sxs-lookup"><span data-stu-id="bac04-112">Let's continue to use the List.Sort() method as our example.</span></span> <span data-ttu-id="bac04-113">Der erste Schritt ist die Erstellung eines Typs für den Vergleichsdelegaten:</span><span class="sxs-lookup"><span data-stu-id="bac04-113">The first step is to create a type for the comparison delegate:</span></span>

```csharp
// From the .NET Core library

// Define the delegate type:
public delegate int Comparison<in T>(T left, T right);
```

<span data-ttu-id="bac04-114">Der Compiler generiert eine von `System.Delegate` abgeleitete Klasse, die der verwendeten Signatur entspricht (in diesem Fall eine Methode, die eine ganze Zahl zurückgibt und über zwei Argumente verfügt).</span><span class="sxs-lookup"><span data-stu-id="bac04-114">The compiler generates a class, derived from `System.Delegate` that matches the signature used (in this case, a method that returns an integer, and has two arguments).</span></span> <span data-ttu-id="bac04-115">Der Typ des Delegaten ist `Comparison`.</span><span class="sxs-lookup"><span data-stu-id="bac04-115">The type of that delegate is `Comparison`.</span></span> <span data-ttu-id="bac04-116">Der Delegattyp `Comparison` ist ein generischer Typ.</span><span class="sxs-lookup"><span data-stu-id="bac04-116">The `Comparison` delegate type is a generic type.</span></span> <span data-ttu-id="bac04-117">Weitere Informationen zu Generika finden Sie [hier](generics.md).</span><span class="sxs-lookup"><span data-stu-id="bac04-117">For details on generics see [here](generics.md).</span></span>

<span data-ttu-id="bac04-118">Beachten Sie, dass es so scheinen kann, als ob die Syntax eine Variable deklariert, aber tatsächlich deklariert sie einen *Typ*.</span><span class="sxs-lookup"><span data-stu-id="bac04-118">Notice that the syntax may appear as though it is declaring a variable, but it is actually declaring a *type*.</span></span> <span data-ttu-id="bac04-119">Sie können Delegattypen innerhalb von Klassen, direkt in Namespaces oder sogar im globalen Namespace definieren.</span><span class="sxs-lookup"><span data-stu-id="bac04-119">You can define delegate types inside classes, directly inside namespaces, or even in the global namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="bac04-120">Es wird nicht empfohlen, Delegattypen (oder andere Typen) direkt im globalen Namespace zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="bac04-120">Declaring delegate types (or other types) directly in the global namespace is not recommended.</span></span> 

<span data-ttu-id="bac04-121">Der Compiler generiert auch Handler zum Hinzufügen und Entfernen für diesen neuen Typ, damit Clients dieser Klasse Methoden der Aufrufliste einer Instanz hinzufügen und entfernen können.</span><span class="sxs-lookup"><span data-stu-id="bac04-121">The compiler also generates add and remove handlers for this new type so that clients of this class can add and remove methods from an instance's invocation list.</span></span> <span data-ttu-id="bac04-122">Der Compiler erzwingt, dass die Signatur der Methode, die hinzugefügt oder entfernt wird, der Signatur bei der Deklaration der Methode entspricht.</span><span class="sxs-lookup"><span data-stu-id="bac04-122">The compiler will enforce that the signature of the method being added or removed matches the signature used when declaring the method.</span></span> 

## <a name="declaring-instances-of-delegates"></a><span data-ttu-id="bac04-123">Deklarieren von Instanzen von Delegaten</span><span class="sxs-lookup"><span data-stu-id="bac04-123">Declaring instances of delegates</span></span>

<span data-ttu-id="bac04-124">Nach dem Definieren des Delegats können Sie eine Instanz dieses Typs erstellen.</span><span class="sxs-lookup"><span data-stu-id="bac04-124">After defining the delegate, you can create an instance of that type.</span></span>
<span data-ttu-id="bac04-125">Wie alle Variablen in C# können Sie Delegatinstanzen nicht direkt in einem Namespace oder im globalen Namespace deklarieren.</span><span class="sxs-lookup"><span data-stu-id="bac04-125">Like all variables in C#, you cannot declare delegate instances directly in a namespace, or in the global namespace.</span></span>

```csharp
// inside a class definition:

// Declare an instance of that type:
public Comparison<T> comparator;
```

<span data-ttu-id="bac04-126">Der Typ der Variable ist `Comparison<T>`, der zuvor definierte Delegattyp.</span><span class="sxs-lookup"><span data-stu-id="bac04-126">The type of the variable is `Comparison<T>`, the delegate type defined earlier.</span></span> <span data-ttu-id="bac04-127">Der Name der Variablen ist `comparator`.</span><span class="sxs-lookup"><span data-stu-id="bac04-127">The name of the variable is `comparator`.</span></span>
 
 <span data-ttu-id="bac04-128">Dieser obenstehende Codeausschnitt hat eine Membervariable innerhalb einer Klasse deklariert.</span><span class="sxs-lookup"><span data-stu-id="bac04-128">That code snippet above declared a member variable inside a class.</span></span> <span data-ttu-id="bac04-129">Sie können auch Delegatvariablen deklarieren, die lokale Variablen oder Argumente von Methoden sind.</span><span class="sxs-lookup"><span data-stu-id="bac04-129">You can also declare delegate variables that are local variables, or arguments to methods.</span></span>

## <a name="invoking-delegates"></a><span data-ttu-id="bac04-130">Aufrufen von Delegaten</span><span class="sxs-lookup"><span data-stu-id="bac04-130">Invoking Delegates</span></span>

<span data-ttu-id="bac04-131">Sie rufen die Methoden in der Aufrufliste eines Delegaten auf, indem Sie diesen Delegaten aufrufen.</span><span class="sxs-lookup"><span data-stu-id="bac04-131">You invoke the methods that are in the invocation list of a delegate by calling that delegate.</span></span> <span data-ttu-id="bac04-132">In der `Sort()`-Methode ruft der Code die Vergleichsmethode an, um zu bestimmen, in welcher Reihenfolge er die Objekte anordnet:</span><span class="sxs-lookup"><span data-stu-id="bac04-132">Inside the `Sort()` method, the code will call the comparison method to determine which order to place objects:</span></span>

```csharp
int result = comparator(left, right);
```

<span data-ttu-id="bac04-133">In der Zeile darüber *ruft* der Code die Methode auf, die an den Delegaten angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="bac04-133">In the line above, the code *invokes* the method attached to the delegate.</span></span>
<span data-ttu-id="bac04-134">Sie behandeln die Variable als Methodenname und rufen sie mit der üblichen Syntax für Methodenaufrufe auf.</span><span class="sxs-lookup"><span data-stu-id="bac04-134">You treat the variable as a method name, and invoke it using normal method call syntax.</span></span>

<span data-ttu-id="bac04-135">Diese Codezeile macht eine unsichere Annahme: Es gibt keine Garantie, dass dem Delegaten ein Ziel hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="bac04-135">That line of code makes an unsafe assumption: There's no guarantee that a target has been added to the delegate.</span></span> <span data-ttu-id="bac04-136">Wenn keine Ziele angehängt wurden, löst die Zeile darüber eine `NullReferenceException` aus.</span><span class="sxs-lookup"><span data-stu-id="bac04-136">If no targets have been attached, the line above would cause a `NullReferenceException` to be thrown.</span></span> <span data-ttu-id="bac04-137">Die Ausdrücke, die verwendet werden, um dieses Problem zu beheben, sind komplizierter als eine einfache NULL-Überprüfung und werden später in dieser [Reihe](delegates-patterns.md) behandelt.</span><span class="sxs-lookup"><span data-stu-id="bac04-137">The idioms used to address this problem are more complicated than a simple null-check, and are covered later in this [series](delegates-patterns.md).</span></span>

## <a name="assigning-adding-and-removing-invocation-targets"></a><span data-ttu-id="bac04-138">Zuweisen, Hinzufügen und Entfernen von Aufrufzielen</span><span class="sxs-lookup"><span data-stu-id="bac04-138">Assigning, Adding and removing Invocation Targets</span></span>

<span data-ttu-id="bac04-139">So werden Delegattypen definiert und Delegatinstanzen deklariert und aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bac04-139">That's how a delegate type is defined, and how delegate instances are declared and invoked.</span></span>

<span data-ttu-id="bac04-140">Entwickler, die die `List.Sort()`-Methode verwenden möchten, müssen eine Methode definieren, deren Signatur der Definition des Delegattypen entspricht, und diese dem Delegaten zuweisen, der von der sort-Methode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bac04-140">Developers that want to use the `List.Sort()` method need to define a method whose signature matches the delegate type definition, and assign it to the delegate used by the sort method.</span></span> <span data-ttu-id="bac04-141">Diese Zuordnung fügt die Methode der Aufrufliste des Delegatobjekts hinzu.</span><span class="sxs-lookup"><span data-stu-id="bac04-141">This assignment adds the method to the invocation list of that delegate object.</span></span>

<span data-ttu-id="bac04-142">Nehmen wir an, Sie möchten eine Liste von Zeichenfolgen nach Länge sortieren.</span><span class="sxs-lookup"><span data-stu-id="bac04-142">Suppose you wanted to sort a list of strings by their length.</span></span> <span data-ttu-id="bac04-143">Die Vergleichsfunktion kann folgende sein:</span><span class="sxs-lookup"><span data-stu-id="bac04-143">Your comparison function might be the following:</span></span>

```csharp
private static int CompareLength(string left, string right)
{
    return left.Length.CompareTo(right.Length);
}
```

<span data-ttu-id="bac04-144">Die Methode wird als private Methode deklariert.</span><span class="sxs-lookup"><span data-stu-id="bac04-144">The method is declared as a private method.</span></span> <span data-ttu-id="bac04-145">Das ist in Ordnung.</span><span class="sxs-lookup"><span data-stu-id="bac04-145">That's fine.</span></span> <span data-ttu-id="bac04-146">Möglicherweise möchten Sie nicht, dass diese Methode Teil der öffentlichen Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="bac04-146">You may not want this method to be part of your public interface.</span></span> <span data-ttu-id="bac04-147">Sie kann dennoch als Vergleichsmethode verwendet werden, wenn sie an einen Delegaten angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="bac04-147">It can still be used as the comparison method when attached to a delegate.</span></span> <span data-ttu-id="bac04-148">Der aufrufende Code wird diese Methode an die Zielliste des Delegatobjekts anfügen lassen und kann über diesen Delegaten darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="bac04-148">The calling code will have this method attached to the target list of the delegate object, and can access it through that delegate.</span></span>

<span data-ttu-id="bac04-149">Sie erstellen diese Beziehung durch Übergeben dieser Methode an die `List.Sort()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="bac04-149">You create that relationship by passing that method to the `List.Sort()` method:</span></span>

```csharp
phrases.Sort(CompareLength);
```

<span data-ttu-id="bac04-150">Beachten Sie, dass der Name der Methode ohne Klammern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bac04-150">Notice that the method name is used, without parentheses.</span></span> <span data-ttu-id="bac04-151">Das Verwenden der Methode als Argument teilt dem Compiler mit, dass er den Methodenverweis in einen Verweis konvertieren soll, der als Delegataufrufziel verwendet werden kann, und diese Methode als Aufrufziel anfügen soll.</span><span class="sxs-lookup"><span data-stu-id="bac04-151">Using the method as an argument tells the compiler to convert the method reference into a reference that can be used as a delegate invocation target, and attach that method as an invocation target.</span></span>

<span data-ttu-id="bac04-152">Sie könnten auch explizit eine Variable vom Typ „Comparison<string>“ deklarieren und diese in der Zuordnung verwenden:</span><span class="sxs-lookup"><span data-stu-id="bac04-152">You could also have been explicit by declaring a variable of type 'Comparison<string>\` and doing an assignment:</span></span>

```csharp
Comparison<string> comparer = CompareLength;
phrases.Sort(comparer);
```

<span data-ttu-id="bac04-153">Wenn es sich bei der als Delegatziel verwendeten Methode um eine kleine Methode handelt, wird gewöhnlich die [Lambda-Ausdruck](lambda-expressions.md)-Syntax für die Durchführung der Zuweisung verwendet:</span><span class="sxs-lookup"><span data-stu-id="bac04-153">In uses where the method being used as a delegate target is a small method, it's common to use [Lambda Expression](lambda-expressions.md) syntax to perform the assignment:</span></span>

```csharp
Comparison<string> comparer = (left, right) => left.Length.CompareTo(right.Length);
phrases.Sort(comparer);
```

<span data-ttu-id="bac04-154">Die Verwendung von Lambda-Ausdrücken für Delegatziele wird in einem [späteren Abschnitt](delegates-patterns.md) ausführlicher behandelt.</span><span class="sxs-lookup"><span data-stu-id="bac04-154">Using Lambda Expressions for delegate targets is covered more in a [later section](delegates-patterns.md).</span></span>

<span data-ttu-id="bac04-155">Das Sort()-Beispiel fügt dem Delegaten typischerweise eine einzelne Zielmethode an.</span><span class="sxs-lookup"><span data-stu-id="bac04-155">The Sort() example typically attaches a single target method to the delegate.</span></span> <span data-ttu-id="bac04-156">Allerdings unterstützen Delegatobjekte Aufruflisten mit mehreren Zielmethoden, die an ein Delegatobjekt angefügt sind.</span><span class="sxs-lookup"><span data-stu-id="bac04-156">However, delegate objects do support invocation lists that have multiple target methods attached to a delegate object.</span></span>

## <a name="delegate-and-multicastdelegate-classes"></a><span data-ttu-id="bac04-157">Delegatklassen und MulticastDelegate-Klassen</span><span class="sxs-lookup"><span data-stu-id="bac04-157">Delegate and MulticastDelegate classes</span></span>

<span data-ttu-id="bac04-158">Die oben beschriebene Sprachunterstützung bietet die Funktionen und Unterstützung, die Sie in der Regel bei der Arbeit mit Delegaten benötigen.</span><span class="sxs-lookup"><span data-stu-id="bac04-158">The language support described above provides the features and support you'll typically need to work with delegates.</span></span> <span data-ttu-id="bac04-159">Diese Funktionen beruhen auf zwei Klassen in .NET Core Framework: @System.Delegate und @„System.MulticastDelegate“.</span><span class="sxs-lookup"><span data-stu-id="bac04-159">These features are built on two classes in the .NET Core framework: @System.Delegate and @"System.MulticastDelegate".</span></span>

<span data-ttu-id="bac04-160">Die `System.Delegate`-Klasse und ihre einzige direkte untergeordnete Klasse `System.MulticastDelegate` bieten die Framework-Unterstützung für das Erstellen von Delegaten, das Registrieren von Methoden als Delegatziele und das Aufrufen aller Methoden, die als Delegatziel registriert sind.</span><span class="sxs-lookup"><span data-stu-id="bac04-160">The `System.Delegate` class, and its single direct sub-class, `System.MulticastDelegate`, provide the framework support for creating delegates, registering methods as delegate targets, and invoking all methods that are registered as a delegate target.</span></span> 

<span data-ttu-id="bac04-161">Interessanterweise sind die Klassen `System.Delegate` und `System.MulticastDelegate` selbst keine Delegattypen.</span><span class="sxs-lookup"><span data-stu-id="bac04-161">Interestingly, the `System.Delegate` and `System.MulticastDelegate` classes are not themselves delegate types.</span></span> <span data-ttu-id="bac04-162">Sie bieten die Grundlage für alle spezifischen Delegattypen.</span><span class="sxs-lookup"><span data-stu-id="bac04-162">They do provide the basis for all specific delegate types.</span></span> <span data-ttu-id="bac04-163">Derselbe Sprachentwurfsprozess verlangte, dass keine Klasse deklariert werden kann, die von `Delegate` oder `MulticastDelegate` abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="bac04-163">That same language design process mandated that you cannot declare a class that derives from `Delegate` or `MulticastDelegate`.</span></span> <span data-ttu-id="bac04-164">Die C#-Sprachregeln verbieten dies.</span><span class="sxs-lookup"><span data-stu-id="bac04-164">The C# language rules prohibit it.</span></span>
 
<span data-ttu-id="bac04-165">Stattdessen erstellt der C#-Compiler Instanzen einer von `MulticastDelegate` abgeleiteten Klasse, wenn Sie das C#-Schlüsselwort verwenden, um Delegattypen zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="bac04-165">Instead, the C# compiler creates instances of a class derived from `MulticastDelegate` when you use the C# language keyword to declare delegate types.</span></span>

<span data-ttu-id="bac04-166">Dieser Entwurf hat seinen Ursprung in der ersten Version von C# und .NET.</span><span class="sxs-lookup"><span data-stu-id="bac04-166">This design has its roots in the first release of C# and .NET.</span></span> <span data-ttu-id="bac04-167">Ein Ziel des Entwurfsteams war sicherzustellen, dass die Sprache bei der Verwendung von Delegaten Typsicherheit erzwingt.</span><span class="sxs-lookup"><span data-stu-id="bac04-167">One goal for the design team was to ensure that the language enforced type safety when using delegates.</span></span> <span data-ttu-id="bac04-168">Dies bedeutete sicherzustellen, dass Delegaten mit dem richtigen Typ und der richtigen Anzahl von Argumenten aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bac04-168">That meant ensuring that delegates were invoked with the right type and number of arguments.</span></span> <span data-ttu-id="bac04-169">Zudem sollte jeder Rückgabetyp zur Kompilierzeit richtig angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bac04-169">And, that any return type was correctly indicated at compile time.</span></span> <span data-ttu-id="bac04-170">Delegaten waren Teil von .NET Version 1.0, die es vor Generika gab.</span><span class="sxs-lookup"><span data-stu-id="bac04-170">Delegates were part of the 1.0 .NET release, which was before generics.</span></span>

<span data-ttu-id="bac04-171">Die beste Möglichkeit, diese Typsicherheit zu erzwingen, bestand darin, dass der Compiler die konkreten Delegatklassen erstellt, die die verwendete Methodensignatur darstellten.</span><span class="sxs-lookup"><span data-stu-id="bac04-171">The best way to enforce this type safety was for the compiler to create the concrete delegate classes that represented the method signature being used.</span></span>

<span data-ttu-id="bac04-172">Obwohl Sie abgeleitete Klassen nicht direkt erstellen können, verwenden Sie die Methoden, die auf diesen Klassen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="bac04-172">Even though you cannot create derived classes directly, you will use the methods defined on these classes.</span></span> <span data-ttu-id="bac04-173">Nun sehen wir uns die am häufigsten verwendeten Methoden an, die Sie beim Arbeiten mit Delegaten verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="bac04-173">Let's go through the most common methods that you will use when you work with delegates.</span></span>

<span data-ttu-id="bac04-174">An erster Stelle müssen Sie beachten, dass jeder Delegat, mit dem Sie arbeiten, von `MulticastDelegate` abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="bac04-174">The first, most important fact to remember is that every delegate you work with is derived from `MulticastDelegate`.</span></span> <span data-ttu-id="bac04-175">Ein Multicastdelegat bedeutet, dass mehr als ein Methodenziel beim Aufrufen über einen Delegaten aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="bac04-175">A multicast delegate means that more than one method target can be invoked when invoking through a delegate.</span></span> <span data-ttu-id="bac04-176">Der ursprüngliche Entwurf sah eine Unterscheidung vor zwischen Delegaten, bei denen nur eine Zielmethode angefügt und aufgerufen werden konnte, und Delegaten, bei denen mehrere Zielmethoden angefügt und aufgerufen werden konnten.</span><span class="sxs-lookup"><span data-stu-id="bac04-176">The original design considered making a distinction between delegates where only one target method could be attached and invoked, and delegates where multiple target methods could be attached and invoked.</span></span> <span data-ttu-id="bac04-177">Diese Unterscheidung erwies sich in der Praxis jedoch als weniger nützlich als ursprünglich gedacht.</span><span class="sxs-lookup"><span data-stu-id="bac04-177">That distinction proved to be less useful in practice than originally thought.</span></span> <span data-ttu-id="bac04-178">Die zwei verschiedenen Klassen wurden bereits erstellt und befinden sich seit der ersten Veröffentlichung im Framework.</span><span class="sxs-lookup"><span data-stu-id="bac04-178">The two different classes were already created, and have been in the framework since its initial public release.</span></span>

<span data-ttu-id="bac04-179">Die Methoden, die Sie bei der Arbeit mit Delegaten am häufigsten verwenden, sind `Invoke()` und `BeginInvoke()` / `EndInvoke()`.</span><span class="sxs-lookup"><span data-stu-id="bac04-179">The methods that you will use the most with delegates are `Invoke()` and `BeginInvoke()` / `EndInvoke()`.</span></span> <span data-ttu-id="bac04-180">`Invoke()` ruft alle Methoden auf, die an eine bestimmte Delegatinstanz angefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="bac04-180">`Invoke()` will invoke all the methods that have been attached to a particular delegate instance.</span></span> <span data-ttu-id="bac04-181">Wie oben gezeigt, werden Delegaten in der Regel mit der Aufrufsyntax-Methode auf der Delegatvariablen aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bac04-181">As you saw above, you typically invoke delegates using the method call syntax on the delegate variable.</span></span> <span data-ttu-id="bac04-182">Wie Sie [später in dieser Reihe](delegates-patterns.md) sehen werden, gibt es Muster, die direkt mit diesen Methoden arbeiten.</span><span class="sxs-lookup"><span data-stu-id="bac04-182">As you'll see [later in this series](delegates-patterns.md), there are patterns that work directly with these methods.</span></span>

<span data-ttu-id="bac04-183">Nun haben Sie die Sprachsyntax und die Klassen gesehen, die Delegaten unterstützen. Als Nächstes untersuchen wir, wie stark typisierte Delegaten verwendet, erstellt und aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bac04-183">Now that you've seen the language syntax and the classes that support delegates, let's examine how strongly typed delegates are used, created and invoked.</span></span>

[<span data-ttu-id="bac04-184">Weiter</span><span class="sxs-lookup"><span data-stu-id="bac04-184">Next</span></span>](delegates-strongly-typed.md)

