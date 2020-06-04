---
title: Refactoring in reine Funktionen
ms.date: 07/20/2015
ms.assetid: 99e7d27b-a3ff-4577-bdb2-5a8278d6d7af
ms.openlocfilehash: 415b088661eca347330f4776901d68ee514d8dad
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413478"
---
# <a name="refactoring-into-pure-functions-visual-basic"></a><span data-ttu-id="c6039-102">Refactoring in reine Funktionen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6039-102">Refactoring Into Pure Functions (Visual Basic)</span></span>

<span data-ttu-id="c6039-103">Ein wichtiger Aspekt bei dem Studium reiner funktionaler Transformationen besteht darin zu lernen, wie Code mit reinen Funktionen umgestaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c6039-103">An important aspect of pure functional transformations is learning how to refactor code using pure functions.</span></span>

<span data-ttu-id="c6039-104">Wie bereits weiter oben erwähnt, besitzt eine reine Funktion zwei nützliche Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="c6039-104">As noted previously in this section, a pure function has two useful characteristics:</span></span>

- <span data-ttu-id="c6039-105">Sie hat keine Nebenwirkungen.</span><span class="sxs-lookup"><span data-stu-id="c6039-105">It has no side effects.</span></span> <span data-ttu-id="c6039-106">Die Funktion ändert keine Variablen oder Daten irgendeines Typs außerhalb der Funktion.</span><span class="sxs-lookup"><span data-stu-id="c6039-106">The function does not change any variables or the data of any type outside of the function.</span></span>

- <span data-ttu-id="c6039-107">Sie ist konsistent.</span><span class="sxs-lookup"><span data-stu-id="c6039-107">It is consistent.</span></span> <span data-ttu-id="c6039-108">Bei identischen Eingabedaten gibt die Funktion immer denselben Ausgabewert zurück.</span><span class="sxs-lookup"><span data-stu-id="c6039-108">Given the same set of input data, it will always return the same output value.</span></span>

 <span data-ttu-id="c6039-109">Eine Möglichkeit des Umstiegs auf die funktionale Programmierung besteht darin, vorhandenen Code umzugestalten und so unnötige Nebenwirkungen und externe Abhängigkeiten abzuschaffen.</span><span class="sxs-lookup"><span data-stu-id="c6039-109">One way of transitioning to functional programming is to refactor existing code to eliminate unnecessary side effects and external dependencies.</span></span> <span data-ttu-id="c6039-110">Auf diese Weise können Sie Versionen von reinen Funktionen von vorhandenem Code erstellen.</span><span class="sxs-lookup"><span data-stu-id="c6039-110">In this way, you can create pure function versions of existing code.</span></span>

<span data-ttu-id="c6039-111">In diesem Thema wird erläutert, was eine reine Funktion ist und was nicht.</span><span class="sxs-lookup"><span data-stu-id="c6039-111">This topic discusses what a pure function is and what it is not.</span></span> <span data-ttu-id="c6039-112">Im [Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (Visual Basic)](tutorial-manipulating-content-in-a-wordprocessingml-document.md) erfahren Sie, wie Sie ein WordprocessingML-Dokument bearbeiten können. Außerdem enthält es zwei Beispiele für das Umgestalten mithilfe einer reinen Funktion.</span><span class="sxs-lookup"><span data-stu-id="c6039-112">The [Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial shows how to manipulate a WordprocessingML document, and includes two examples of how to refactor using a pure function.</span></span>

## <a name="eliminating-side-effects-and-external-dependencies"></a><span data-ttu-id="c6039-113">Beseitigen von Nebenwirkungen und externen Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="c6039-113">Eliminating Side Effects and External Dependencies</span></span>

<span data-ttu-id="c6039-114">In den folgenden Beispielen werden zwei nicht reine Funktionen einer reinen Funktion gegenübergestellt.</span><span class="sxs-lookup"><span data-stu-id="c6039-114">The following examples contrast two non-pure functions and a pure function.</span></span>

### <a name="non-pure-function-that-changes-a-class-member"></a><span data-ttu-id="c6039-115">Nicht reine Funktion, die einen Klassenmember ändert</span><span class="sxs-lookup"><span data-stu-id="c6039-115">Non-Pure Function that Changes a Class Member</span></span>

<span data-ttu-id="c6039-116">Im folgenden Code ist die `HyphenatedConcat`-Funktion keine reine Funktion, da sie den `aMember`-Datenmember in der Klasse ändert:</span><span class="sxs-lookup"><span data-stu-id="c6039-116">In the following code, the `HyphenatedConcat` function is not a pure function, because it modifies the `aMember` data member in the class:</span></span>

```vb
Module Module1
    Dim aMember As String = "StringOne"

    Public Sub HyphenatedConcat(ByVal appendStr As String)
        aMember = aMember & "-" & appendStr
    End Sub

    Sub Main()
        HyphenatedConcat("StringTwo")
        Console.WriteLine(aMember)
    End Sub
End Module
```

<span data-ttu-id="c6039-117">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="c6039-117">This code produces the following output:</span></span>

```console
StringOne-StringTwo
```

<span data-ttu-id="c6039-118">Beachten Sie, dass es unerheblich ist, ob die geänderten Daten über oder zugreifen oder ob es `public` `private` sich um einen `shared` Member oder einen Instanzmember handelt.</span><span class="sxs-lookup"><span data-stu-id="c6039-118">Note that it is irrelevant whether the data being modified has `public` or `private` access, or is a  `shared` member or an instance member.</span></span> <span data-ttu-id="c6039-119">Reine Funktionen führen zu keinerlei Änderungen an Daten außerhalb der Funktion.</span><span class="sxs-lookup"><span data-stu-id="c6039-119">A pure function does not change any data outside of the function.</span></span>

### <a name="non-pure-function-that-changes-an-argument"></a><span data-ttu-id="c6039-120">Nicht reine Funktion, die ein Argument ändert</span><span class="sxs-lookup"><span data-stu-id="c6039-120">Non-Pure Function that Changes an Argument</span></span>

<span data-ttu-id="c6039-121">Außerdem ist die folgende Version derselben Funktion keine reine Funktion, weil sie den Inhalt ihres Parameters, `sb`, ändert.</span><span class="sxs-lookup"><span data-stu-id="c6039-121">Furthermore, the following version of this same function is not pure because it modifies the contents of its parameter, `sb`.</span></span>

```vb
Module Module1
    Public Sub HyphenatedConcat(ByVal sb As StringBuilder, ByVal appendStr As String)
        sb.Append("-" & appendStr)
    End Sub

    Sub Main()
        Dim sb1 As StringBuilder = New StringBuilder("StringOne")
        HyphenatedConcat(sb1, "StringTwo")
        Console.WriteLine(sb1)
    End Sub
End Module
```

<span data-ttu-id="c6039-122">Diese Version des Programms produziert dieselbe Ausgabe wie die erste Version, weil die `HyphenatedConcat`-Funktion durch Aufrufen der <xref:System.Text.StringBuilder.Append%2A>-Memberfunktion den Wert (Status) ihres ersten Parameters geändert hat.</span><span class="sxs-lookup"><span data-stu-id="c6039-122">This version of the program produces the same output as the first version, because the `HyphenatedConcat` function has changed the value (state) of its first parameter by invoking the <xref:System.Text.StringBuilder.Append%2A> member function.</span></span> <span data-ttu-id="c6039-123">Beachten Sie, dass diese Änderung trotz der Tatsache auftritt, dass `HyphenatedConcat` mit Wertparameterübergabe arbeitet.</span><span class="sxs-lookup"><span data-stu-id="c6039-123">Note that this alteration occurs despite that fact that `HyphenatedConcat` uses call-by-value parameter passing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6039-124">Wenn Sie bei Verweistypen einen Parameter nach Wert übergeben, führt dies zu einer Kopie des Verweises auf ein zu übergebendes Objekt.</span><span class="sxs-lookup"><span data-stu-id="c6039-124">For reference types, if you pass a parameter by value, it results in a copy of the reference to an object being passed.</span></span> <span data-ttu-id="c6039-125">Diese Kopie ist weiterhin mit denselben Instanzdaten wie der ursprüngliche Verweis verknüpft (so lange, bis die Verweisvariable einem neuen Objekt zugewiesen wird).</span><span class="sxs-lookup"><span data-stu-id="c6039-125">This copy is still associated with the same instance data as the original reference (until the reference variable is assigned to a new object).</span></span> <span data-ttu-id="c6039-126">Für das Ändern eines Parameters durch einen Parameter ist die Referenzparameterübergabe nicht unbedingt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c6039-126">Call-by-reference is not necessarily required for a function to modify a parameter.</span></span>

### <a name="pure-function"></a><span data-ttu-id="c6039-127">Reine Funktion</span><span class="sxs-lookup"><span data-stu-id="c6039-127">Pure Function</span></span>

<span data-ttu-id="c6039-128">Die nächste Version des Programms zeigt, wie die `HyphenatedConcat`-Funktion als reine Funktion implementiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c6039-128">This next version of the program hows how to implement the `HyphenatedConcat` function as a pure function.</span></span>

```vb
Module Module1
    Public Function HyphenatedConcat(ByVal s As String, ByVal appendStr As String) As String
        Return (s & "-" & appendStr)
    End Function

    Sub Main()
        Dim s1 As String = "StringOne"
        Dim s2 As String = HyphenatedConcat(s1, "StringTwo")
        Console.WriteLine(s2)
    End Sub
End Module
```

<span data-ttu-id="c6039-129">Auch diese Version erzeugt dieselbe Zeile in der Ausgabe: `StringOne-StringTwo`.</span><span class="sxs-lookup"><span data-stu-id="c6039-129">Again, this version produces the same line of output: `StringOne-StringTwo`.</span></span> <span data-ttu-id="c6039-130">Um den verketteten Wert beizubehalten, wird er in der Zwischenvariable `s2` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c6039-130">Note that to retain the concatenated value, it is stored in the intermediate variable `s2`.</span></span>

<span data-ttu-id="c6039-131">Ein Ansatz, der sich als sehr hilfreich erweisen kann, besteht darin, Funktionen zu schreiben, die zwar lokal unrein (also lokale Variablen deklarieren und ändern), global aber rein sind.</span><span class="sxs-lookup"><span data-stu-id="c6039-131">One approach that can be very useful is to write functions that are locally impure (that is, they declare and modify local variables) but are globally pure.</span></span> <span data-ttu-id="c6039-132">Solche Funktionen besitzen viele der wünschenswerten Zusammensetzbarkeitseigenschaften, vermeiden dabei aber einige der komplizierteren Idiome der funktionalen Programmierung, z. B. die Notwendigkeit der Verwendung der Rekursion, wenn eine einfache Schleife dasselbe Ziel erreichen würde.</span><span class="sxs-lookup"><span data-stu-id="c6039-132">Such functions have many of the desirable composability characteristics, but avoid some of the more convoluted functional programming idioms, such as having to use recursion when a simple loop would accomplish the same thing.</span></span>

## <a name="standard-query-operators"></a><span data-ttu-id="c6039-133">Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="c6039-133">Standard Query Operators</span></span>

<span data-ttu-id="c6039-134">Ein wichtiges Merkmal der Standardabfrageoperatoren besteht darin, dass sie als reine Funktionen implementiert sind.</span><span class="sxs-lookup"><span data-stu-id="c6039-134">An important characteristic of the standard query operators is that they are implemented as pure functions.</span></span>

<span data-ttu-id="c6039-135">Weitere Informationen finden Sie unter [Übersicht über Standard Abfrage Operatoren (Visual Basic)](standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c6039-135">For more information, see [Standard Query Operators Overview (Visual Basic)](standard-query-operators-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c6039-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6039-136">See also</span></span>

- [<span data-ttu-id="c6039-137">Einführung in reine funktionale Transformationen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6039-137">Introduction to Pure Functional Transformations (Visual Basic)</span></span>](introduction-to-pure-functional-transformations.md)
- [<span data-ttu-id="c6039-138">Funktionale Programmierung im Vergleich zu imperativer Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6039-138">Functional Programming vs. Imperative Programming (Visual Basic)</span></span>](functional-programming-vs-imperative-programming.md)
