---
title: Stark typisierte Delegate
description: Informationen zur Verwendung von generischen Delegattypen zum Deklarieren von benutzerdefinierten Typen beim Erstellen eines Features, das Delegaten erfordert.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 564a683d-352b-4e57-8bac-b466529daf6b
ms.openlocfilehash: 798e8b597389bc99d10e587ec417a4e717f28abc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146202"
---
# <a name="strongly-typed-delegates"></a><span data-ttu-id="a4150-103">Stark typisierte Delegate</span><span class="sxs-lookup"><span data-stu-id="a4150-103">Strongly Typed Delegates</span></span>

[<span data-ttu-id="a4150-104">Zurück</span><span class="sxs-lookup"><span data-stu-id="a4150-104">Previous</span></span>](delegate-class.md)

<span data-ttu-id="a4150-105">Im vorherigen Artikel haben Sie gesehen, dass bestimmte Delegaten mithilfe des `delegate`-Schlüsselworts erstellen.</span><span class="sxs-lookup"><span data-stu-id="a4150-105">In the previous article, you saw that you create specific delegate types using the `delegate` keyword.</span></span>

<span data-ttu-id="a4150-106">Die abstrakte Klasse für den Delegaten stellt die Infrastruktur für die lose Kopplung und den losen Aufruf bereit.</span><span class="sxs-lookup"><span data-stu-id="a4150-106">The abstract Delegate class provide the infrastructure for loose coupling and invocation.</span></span> <span data-ttu-id="a4150-107">Konkrete Delegattypen werden durch die Einführung und das Erzwingen von Typsicherheit für die Methoden, die zur Aufrufliste für ein Delegatobjekt hinzugefügt werden, viel nützlicher.</span><span class="sxs-lookup"><span data-stu-id="a4150-107">Concrete Delegate types become much more useful by embracing and enforcing type safety for the methods that are added to the invocation list for a delegate object.</span></span> <span data-ttu-id="a4150-108">Wenn Sie das `delegate`-Schlüsselwort verwenden und einen konkreten Delegattyp definieren, generiert der Compiler diese Methoden.</span><span class="sxs-lookup"><span data-stu-id="a4150-108">When you use the `delegate` keyword and define a concrete delegate type, the compiler generates those methods.</span></span>

<span data-ttu-id="a4150-109">In der Praxis würde dies zur Erstellung neuer Delegattypen führen, wann immer Sie eine andere Methodensignatur benötigen.</span><span class="sxs-lookup"><span data-stu-id="a4150-109">In practice, this would lead to creating new delegate types whenever you need a different method signature.</span></span> <span data-ttu-id="a4150-110">Diese Arbeit könnte mit der Zeit ermüdend werden.</span><span class="sxs-lookup"><span data-stu-id="a4150-110">This work could get tedious after a time.</span></span> <span data-ttu-id="a4150-111">Jede neue Funktion erfordert neue Delegattypen.</span><span class="sxs-lookup"><span data-stu-id="a4150-111">Every new feature requires new delegate types.</span></span>

<span data-ttu-id="a4150-112">Glücklicherweise ist dies nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a4150-112">Thankfully, this isn't necessary.</span></span> <span data-ttu-id="a4150-113">Der .NET Core Framework enthält verschiedene Typen, die Sie wiederverwenden können, wenn Sie Delegattypen benötigen.</span><span class="sxs-lookup"><span data-stu-id="a4150-113">The .NET Core framework contains several types that you can reuse whenever you need delegate types.</span></span> <span data-ttu-id="a4150-114">Dies sind [generische](programming-guide/generics/index.md) Definitionen, damit Sie Anpassungen deklarieren können, wenn Sie neue Methodendeklarationen benötigen.</span><span class="sxs-lookup"><span data-stu-id="a4150-114">These are [generic](programming-guide/generics/index.md) definitions so you can declare customizations when you need new method declarations.</span></span>

<span data-ttu-id="a4150-115">Der erste dieser Typen ist der <xref:System.Action>-Typ, und verschiedene Varianten:</span><span class="sxs-lookup"><span data-stu-id="a4150-115">The first of these types is the <xref:System.Action> type, and several variations:</span></span>

```csharp
public delegate void Action();
public delegate void Action<in T>(T arg);
public delegate void Action<in T1, in T2>(T1 arg1, T2 arg2);
// Other variations removed for brevity.
```

<span data-ttu-id="a4150-116">Die `in`-Modifizierer im generischen Typargument wird in diesem Artikel in Kovarianz behandelt.</span><span class="sxs-lookup"><span data-stu-id="a4150-116">The `in` modifier on the generic type argument is covered in the article on covariance.</span></span>

<span data-ttu-id="a4150-117">Es gibt Variationen des `Action`-Delegaten, der bis zu 16 Argumente enthält, wie z.B. <xref:System.Action%6016>.</span><span class="sxs-lookup"><span data-stu-id="a4150-117">There are variations of the `Action` delegate that contain up to 16 arguments such as <xref:System.Action%6016>.</span></span>
<span data-ttu-id="a4150-118">Es ist wichtig, dass diese Definitionen andere generische Argumente für jeden der Delegatargumente verwenden: Das bietet Ihnen maximale Flexibilität.</span><span class="sxs-lookup"><span data-stu-id="a4150-118">It's important that these definitions use different generic arguments for each of the delegate arguments: That gives you maximum flexibility.</span></span> <span data-ttu-id="a4150-119">Die Methodenargumente müssen nicht, aber können der gleiche Typ sein.</span><span class="sxs-lookup"><span data-stu-id="a4150-119">The method arguments need not be, but may be, the same type.</span></span>

<span data-ttu-id="a4150-120">Verwenden Sie einen der `Action`-Typen für jeden Delegattyp, der über einen void-Rückgabetyp verfügt.</span><span class="sxs-lookup"><span data-stu-id="a4150-120">Use one of the `Action` types for any delegate type that has a void return type.</span></span>

<span data-ttu-id="a4150-121">Das Framework enthält auch mehrere generische Delegattypen, die Sie für Delegattypen verwenden können, die Werte zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="a4150-121">The framework also includes several generic delegate types that you can use for delegate types that return values:</span></span>

```csharp
public delegate TResult Func<out TResult>();
public delegate TResult Func<in T1, out TResult>(T1 arg);
public delegate TResult Func<in T1, in T2, out TResult>(T1 arg1, T2 arg2);
// Other variations removed for brevity
```

<span data-ttu-id="a4150-122">Der `out`-Modifizierer im Ergebnisargument des generischen Typs wird in diesem Artikel in Kovarianz behandelt.</span><span class="sxs-lookup"><span data-stu-id="a4150-122">The `out` modifier on the result generic type argument is covered in the article on covariance.</span></span>

<span data-ttu-id="a4150-123">Es gibt Variationen des `Func`-Delegaten mit bis zu 16 Eingabeargumenten, wie z.B. <xref:System.Func%6017>.</span><span class="sxs-lookup"><span data-stu-id="a4150-123">There are variations of the `Func` delegate with up to 16 input arguments such as <xref:System.Func%6017>.</span></span>
<span data-ttu-id="a4150-124">Der Typ des Ergebnisses ist immer der letzte Typparameter in allen `Func`-Deklarationen, gemäß der Konvention.</span><span class="sxs-lookup"><span data-stu-id="a4150-124">The type of the result is always the last type parameter in all the `Func` declarations, by convention.</span></span>

<span data-ttu-id="a4150-125">Verwenden Sie einen der `Func`-Typen für jeden Delegattyp, der einen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a4150-125">Use one of the `Func` types for any delegate type that returns a value.</span></span>

<span data-ttu-id="a4150-126">Außerdem gibt es einen spezialisierten <xref:System.Predicate%601>-Typ</span><span class="sxs-lookup"><span data-stu-id="a4150-126">There's also a specialized <xref:System.Predicate%601></span></span>
<span data-ttu-id="a4150-127">für einen Delegaten, der einen Test für einen einzelnen Wert zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="a4150-127">type for a delegate that returns a test on a single value:</span></span>

```csharp
public delegate bool Predicate<in T>(T obj);
```

<span data-ttu-id="a4150-128">Möglicherweise haben Sie bemerkt, dass für jeden `Predicate`-Typ ein strukturell äquivalenter `Func`-Typ vorhanden ist, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="a4150-128">You may notice that for any `Predicate` type, a structurally equivalent `Func` type exists For example:</span></span>

```csharp
Func<string, bool> TestForString;
Predicate<string> AnotherTestForString;
```

<span data-ttu-id="a4150-129">Sie denken möglicherweise, dass diese beiden Typen äquivalent sind.</span><span class="sxs-lookup"><span data-stu-id="a4150-129">You might think these two types are equivalent.</span></span> <span data-ttu-id="a4150-130">Das sind sie nicht.</span><span class="sxs-lookup"><span data-stu-id="a4150-130">They are not.</span></span>
<span data-ttu-id="a4150-131">Diese beiden Variablen sind nicht austauschbar.</span><span class="sxs-lookup"><span data-stu-id="a4150-131">These two variables cannot be used interchangeably.</span></span> <span data-ttu-id="a4150-132">Eine Variable eines Typs kann dem anderen Typ nicht zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="a4150-132">A variable of one type cannot be assigned the other type.</span></span> <span data-ttu-id="a4150-133">Das C#-Typsystem verwendet die Namen der definierten Typen, nicht die Struktur.</span><span class="sxs-lookup"><span data-stu-id="a4150-133">The C# type system uses the names of the defined types, not the structure.</span></span>

<span data-ttu-id="a4150-134">Alle diese Definitionen von Delegattypen in der .NET Core-Bibliothek sollten bedeuten, dass Sie keinen neuen Delegattypen für jede neue Funktion, die Sie erstellen und die Delegaten erfordert, definieren müssen.</span><span class="sxs-lookup"><span data-stu-id="a4150-134">All these delegate type definitions in the .NET Core Library should mean that you do not need to define a new delegate type for any new feature you create that requires delegates.</span></span> <span data-ttu-id="a4150-135">Diese generischen Definitionen sollten alle Delegattypen bereitstellen, die Sie in den meisten Fällen benötigen.</span><span class="sxs-lookup"><span data-stu-id="a4150-135">These generic definitions should provide all the delegate types you need under most situations.</span></span> <span data-ttu-id="a4150-136">Sie können einen dieser Typen mit den erforderlichen Parametern einfach instanziieren.</span><span class="sxs-lookup"><span data-stu-id="a4150-136">You can simply instantiate one of these types with the required type parameters.</span></span> <span data-ttu-id="a4150-137">Im Falle von Algorithmen, die generisch vorgenommen werden können, können diese Delegaten als generische Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4150-137">In the case of algorithms that can be made generic, these delegates can be used as generic types.</span></span>

<span data-ttu-id="a4150-138">Dies sollte Zeit sparen und die Anzahl neuer Typen minimieren, die Sie erstellen müssen, um mit Delegaten zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="a4150-138">This should save time, and minimize the number of new types that you need to create in order to work with delegates.</span></span>

<span data-ttu-id="a4150-139">Im nächsten Artikel sehen Sie einige allgemeine Muster für die praktische Arbeit mit Delegaten.</span><span class="sxs-lookup"><span data-stu-id="a4150-139">In the next article, you'll see several common patterns for working with delegates in practice.</span></span>

[<span data-ttu-id="a4150-140">Nächste</span><span class="sxs-lookup"><span data-stu-id="a4150-140">Next</span></span>](delegates-patterns.md)
