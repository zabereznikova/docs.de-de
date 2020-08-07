---
title: Refactoring in reine Funktionen (C#)
description: Erfahren Sie, wie Sie Code mithilfe von reinen Funktionen umgestalten. Hier finden Sie Codebeispiele und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
ms.assetid: 2944a0d4-fd33-4e2e-badd-abb0f9be2fcc
ms.openlocfilehash: cc5dd26923e2edaed34c8f1b742b3dfa1e935e68
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87300227"
---
# <a name="refactoring-into-pure-functions-c"></a><span data-ttu-id="80add-104">Refactoring in reine Funktionen (C#)</span><span class="sxs-lookup"><span data-stu-id="80add-104">Refactoring Into Pure Functions (C#)</span></span>

<span data-ttu-id="80add-105">Ein wichtiger Aspekt bei dem Studium reiner funktionaler Transformationen besteht darin zu lernen, wie Code mit reinen Funktionen umgestaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="80add-105">An important aspect of pure functional transformations is learning how to refactor code using pure functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80add-106">Nach der allgemeinen Nomenklatur bei der funktionalen Programmierung werden Programme mit reinen Funktionen umgestaltet.</span><span class="sxs-lookup"><span data-stu-id="80add-106">The common nomenclature in functional programming is that you refactor programs using pure functions.</span></span> <span data-ttu-id="80add-107">In Visual Basic und C++ geht dies mit der Verwendung von Funktionen in den jeweiligen Sprachen einher.</span><span class="sxs-lookup"><span data-stu-id="80add-107">In Visual Basic and C++, this aligns with the use of functions in the respective languages.</span></span> <span data-ttu-id="80add-108">In C# werden Funktionen aber als Methoden bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="80add-108">However, in C#, functions are called methods.</span></span> <span data-ttu-id="80add-109">Im Rahmen dieser Erläuterung ist die reine Funktion als C#-Methode implementiert.</span><span class="sxs-lookup"><span data-stu-id="80add-109">For the purposes of this discussion, a pure function is implemented as a method in C#.</span></span>  
  
 <span data-ttu-id="80add-110">Wie bereits weiter oben erwähnt, besitzt eine reine Funktion zwei nützliche Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="80add-110">As noted previously in this section, a pure function has two useful characteristics:</span></span>  
  
- <span data-ttu-id="80add-111">Sie hat keine Nebenwirkungen.</span><span class="sxs-lookup"><span data-stu-id="80add-111">It has no side effects.</span></span> <span data-ttu-id="80add-112">Die Funktion ändert keine Variablen oder Daten irgendeines Typs außerhalb der Funktion.</span><span class="sxs-lookup"><span data-stu-id="80add-112">The function does not change any variables or the data of any type outside of the function.</span></span>  
  
- <span data-ttu-id="80add-113">Sie ist konsistent.</span><span class="sxs-lookup"><span data-stu-id="80add-113">It is consistent.</span></span> <span data-ttu-id="80add-114">Bei identischen Eingabedaten gibt die Funktion immer denselben Ausgabewert zurück.</span><span class="sxs-lookup"><span data-stu-id="80add-114">Given the same set of input data, it will always return the same output value.</span></span>  
  
 <span data-ttu-id="80add-115">Eine Möglichkeit des Umstiegs auf die funktionale Programmierung besteht darin, vorhandenen Code umzugestalten und so unnötige Nebenwirkungen und externe Abhängigkeiten abzuschaffen.</span><span class="sxs-lookup"><span data-stu-id="80add-115">One way of transitioning to functional programming is to refactor existing code to eliminate unnecessary side effects and external dependencies.</span></span> <span data-ttu-id="80add-116">Auf diese Weise können Sie Versionen von reinen Funktionen von vorhandenem Code erstellen.</span><span class="sxs-lookup"><span data-stu-id="80add-116">In this way, you can create pure function versions of existing code.</span></span>  
  
 <span data-ttu-id="80add-117">In diesem Thema wird erläutert, was eine reine Funktion ist und was nicht.</span><span class="sxs-lookup"><span data-stu-id="80add-117">This topic discusses what a pure function is and what it is not.</span></span> <span data-ttu-id="80add-118">Im [Tutorial: Manipulating Content in a WordprocessingML Document (C#) (Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (C#))](./shape-of-wordprocessingml-documents.md) wird gezeigt, wie Sie ein WordprocessingML-Dokument bearbeiten können. Außerdem enthält dieses Tutorial zwei Beispiele für das Umgestalten mithilfe einer reinen Funktion.</span><span class="sxs-lookup"><span data-stu-id="80add-118">The [Tutorial: Manipulating Content in a WordprocessingML Document (C#)](./shape-of-wordprocessingml-documents.md) tutorial shows how to manipulate a WordprocessingML document, and includes two examples of how to refactor using a pure function.</span></span>  
  
## <a name="eliminating-side-effects-and-external-dependencies"></a><span data-ttu-id="80add-119">Beseitigen von Nebenwirkungen und externen Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="80add-119">Eliminating Side Effects and External Dependencies</span></span>  
 <span data-ttu-id="80add-120">In den folgenden Beispielen werden zwei nicht reine Funktionen einer reinen Funktion gegenübergestellt.</span><span class="sxs-lookup"><span data-stu-id="80add-120">The following examples contrast two non-pure functions and a pure function.</span></span>  
  
### <a name="non-pure-function-that-changes-a-class-member"></a><span data-ttu-id="80add-121">Nicht reine Funktion, die einen Klassenmember ändert</span><span class="sxs-lookup"><span data-stu-id="80add-121">Non-Pure Function that Changes a Class Member</span></span>  
 <span data-ttu-id="80add-122">Im folgenden Code ist die `HyphenatedConcat`-Funktion keine reine Funktion, da sie den `aMember`-Datenmember in der Klasse ändert:</span><span class="sxs-lookup"><span data-stu-id="80add-122">In the following code, the `HyphenatedConcat` function is not a pure function, because it modifies the `aMember` data member in the class:</span></span>  
  
```csharp  
public class Program  
{  
    private static string aMember = "StringOne";  
  
    public static void HyphenatedConcat(string appendStr)  
    {  
        aMember += '-' + appendStr;  
    }  
  
    public static void Main()  
    {  
        HyphenatedConcat("StringTwo");  
        Console.WriteLine(aMember);  
    }  
}  
```  
  
 <span data-ttu-id="80add-123">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="80add-123">This code produces the following output:</span></span>  
  
```output  
StringOne-StringTwo  
```  
  
 <span data-ttu-id="80add-124">Ob die zu ändernden Daten `public`-Zugriff oder `private`-Zugriff besitzen oder ein `static`-Member bzw. ein Instanzmember sind, spielt keine Rolle.</span><span class="sxs-lookup"><span data-stu-id="80add-124">Note that it is irrelevant whether the data being modified has `public` or `private` access, or is a `static` member or an instance member.</span></span> <span data-ttu-id="80add-125">Reine Funktionen führen zu keinerlei Änderungen an Daten außerhalb der Funktion.</span><span class="sxs-lookup"><span data-stu-id="80add-125">A pure function does not change any data outside of the function.</span></span>  
  
### <a name="non-pure-function-that-changes-an-argument"></a><span data-ttu-id="80add-126">Nicht reine Funktion, die ein Argument ändert</span><span class="sxs-lookup"><span data-stu-id="80add-126">Non-Pure Function that Changes an Argument</span></span>  
 <span data-ttu-id="80add-127">Außerdem ist die folgende Version derselben Funktion keine reine Funktion, weil sie den Inhalt ihres Parameters, `sb`, ändert.</span><span class="sxs-lookup"><span data-stu-id="80add-127">Furthermore, the following version of this same function is not pure because it modifies the contents of its parameter, `sb`.</span></span>  
  
```csharp  
public class Program  
{  
    public static void HyphenatedConcat(StringBuilder sb, String appendStr)  
    {  
        sb.Append('-' + appendStr);  
    }  
  
    public static void Main()  
    {  
        StringBuilder sb1 = new StringBuilder("StringOne");  
        HyphenatedConcat(sb1, "StringTwo");  
        Console.WriteLine(sb1);  
    }  
}  
```  
  
 <span data-ttu-id="80add-128">Diese Version des Programms produziert dieselbe Ausgabe wie die erste Version, weil die `HyphenatedConcat`-Funktion durch Aufrufen der <xref:System.Text.StringBuilder.Append%2A>-Memberfunktion den Wert (Status) ihres ersten Parameters geändert hat.</span><span class="sxs-lookup"><span data-stu-id="80add-128">This version of the program produces the same output as the first version, because the `HyphenatedConcat` function has changed the value (state) of its first parameter by invoking the <xref:System.Text.StringBuilder.Append%2A> member function.</span></span> <span data-ttu-id="80add-129">Beachten Sie, dass diese Änderung trotz der Tatsache auftritt, dass `HyphenatedConcat` mit Wertparameterübergabe arbeitet.</span><span class="sxs-lookup"><span data-stu-id="80add-129">Note that this alteration occurs despite that fact that `HyphenatedConcat` uses call-by-value parameter passing.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="80add-130">Wenn Sie bei Verweistypen einen Parameter nach Wert übergeben, führt dies zu einer Kopie des Verweises auf ein zu übergebendes Objekt.</span><span class="sxs-lookup"><span data-stu-id="80add-130">For reference types, if you pass a parameter by value, it results in a copy of the reference to an object being passed.</span></span> <span data-ttu-id="80add-131">Diese Kopie ist weiterhin mit denselben Instanzdaten wie der ursprüngliche Verweis verknüpft (so lange, bis die Verweisvariable einem neuen Objekt zugewiesen wird).</span><span class="sxs-lookup"><span data-stu-id="80add-131">This copy is still associated with the same instance data as the original reference (until the reference variable is assigned to a new object).</span></span> <span data-ttu-id="80add-132">Für das Ändern eines Parameters durch einen Parameter ist die Referenzparameterübergabe nicht unbedingt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="80add-132">Call-by-reference is not necessarily required for a function to modify a parameter.</span></span>  
  
### <a name="pure-function"></a><span data-ttu-id="80add-133">Reine Funktion</span><span class="sxs-lookup"><span data-stu-id="80add-133">Pure Function</span></span>  
<span data-ttu-id="80add-134">Die nächste Version des Programms zeigt, wie die `HyphenatedConcat`-Funktion als reine Funktion implementiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="80add-134">This next version of the program shows how to implement the `HyphenatedConcat` function as a pure function.</span></span>  
  
```csharp  
class Program  
{  
    public static string HyphenatedConcat(string s, string appendStr)  
    {  
        return (s + '-' + appendStr);  
    }  
  
    public static void Main(string[] args)  
    {  
        string s1 = "StringOne";  
        string s2 = HyphenatedConcat(s1, "StringTwo");  
        Console.WriteLine(s2);  
    }  
}  
```  
  
 <span data-ttu-id="80add-135">Auch diese Version erzeugt dieselbe Zeile in der Ausgabe: `StringOne-StringTwo`.</span><span class="sxs-lookup"><span data-stu-id="80add-135">Again, this version produces the same line of output: `StringOne-StringTwo`.</span></span> <span data-ttu-id="80add-136">Um den verketteten Wert beizubehalten, wird er in der Zwischenvariable `s2` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="80add-136">Note that to retain the concatenated value, it is stored in the intermediate variable `s2`.</span></span>  
  
 <span data-ttu-id="80add-137">Ein Ansatz, der sich als sehr hilfreich erweisen kann, besteht darin, Funktionen zu schreiben, die zwar lokal unrein (also lokale Variablen deklarieren und ändern), global aber rein sind.</span><span class="sxs-lookup"><span data-stu-id="80add-137">One approach that can be very useful is to write functions that are locally impure (that is, they declare and modify local variables) but are globally pure.</span></span> <span data-ttu-id="80add-138">Solche Funktionen besitzen viele der wünschenswerten Zusammensetzbarkeitseigenschaften, vermeiden dabei aber einige der komplizierteren Idiome der funktionalen Programmierung, z. B. die Notwendigkeit der Verwendung der Rekursion, wenn eine einfache Schleife dasselbe Ziel erreichen würde.</span><span class="sxs-lookup"><span data-stu-id="80add-138">Such functions have many of the desirable composability characteristics, but avoid some of the more convoluted functional programming idioms, such as having to use recursion when a simple loop would accomplish the same thing.</span></span>  
  
## <a name="standard-query-operators"></a><span data-ttu-id="80add-139">Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="80add-139">Standard Query Operators</span></span>  
 <span data-ttu-id="80add-140">Ein wichtiges Merkmal der Standardabfrageoperatoren besteht darin, dass sie als reine Funktionen implementiert sind.</span><span class="sxs-lookup"><span data-stu-id="80add-140">An important characteristic of the standard query operators is that they are implemented as pure functions.</span></span>  
  
 <span data-ttu-id="80add-141">Weitere Informationen finden Sie unter [Übersicht über Standardabfrageoperatoren (C#)](./standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="80add-141">For more information, see [Standard Query Operators Overview (C#)](./standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80add-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80add-142">See also</span></span>

- [<span data-ttu-id="80add-143">Introduction to Pure Functional Transformations (C#) (Einführung in reine funktionale Transformationen (c#))</span><span class="sxs-lookup"><span data-stu-id="80add-143">Introduction to Pure Functional Transformations (C#)</span></span>](./introduction-to-pure-functional-transformations.md)
- [<span data-ttu-id="80add-144">Funktionale Programmierung und Imperative Programmierung (C#)</span><span class="sxs-lookup"><span data-stu-id="80add-144">Functional Programming vs. Imperative Programming (C#)</span></span>](./functional-programming-vs-imperative-programming.md)
