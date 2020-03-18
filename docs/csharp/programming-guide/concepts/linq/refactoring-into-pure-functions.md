---
title: Refactoring in reine Funktionen (C#)
ms.date: 07/20/2015
ms.assetid: 2944a0d4-fd33-4e2e-badd-abb0f9be2fcc
ms.openlocfilehash: 4cf91ff078bd1c4582daa05475a91c4a4ecaba3e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "70253112"
---
# <a name="refactoring-into-pure-functions-c"></a><span data-ttu-id="3be19-102">Refactoring in reine Funktionen (C#)</span><span class="sxs-lookup"><span data-stu-id="3be19-102">Refactoring Into Pure Functions (C#)</span></span>

<span data-ttu-id="3be19-103">Ein wichtiger Aspekt bei dem Studium reiner funktionaler Transformationen besteht darin zu lernen, wie Code mit reinen Funktionen umgestaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3be19-103">An important aspect of pure functional transformations is learning how to refactor code using pure functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3be19-104">Nach der allgemeinen Nomenklatur bei der funktionalen Programmierung werden Programme mit reinen Funktionen umgestaltet.</span><span class="sxs-lookup"><span data-stu-id="3be19-104">The common nomenclature in functional programming is that you refactor programs using pure functions.</span></span> <span data-ttu-id="3be19-105">In Visual Basic und C++ geht dies mit der Verwendung von Funktionen in den jeweiligen Sprachen einher.</span><span class="sxs-lookup"><span data-stu-id="3be19-105">In Visual Basic and C++, this aligns with the use of functions in the respective languages.</span></span> <span data-ttu-id="3be19-106">In C# werden Funktionen aber als Methoden bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3be19-106">However, in C#, functions are called methods.</span></span> <span data-ttu-id="3be19-107">Im Rahmen dieser Erläuterung ist die reine Funktion als C#-Methode implementiert.</span><span class="sxs-lookup"><span data-stu-id="3be19-107">For the purposes of this discussion, a pure function is implemented as a method in C#.</span></span>  
  
 <span data-ttu-id="3be19-108">Wie bereits weiter oben erwähnt, besitzt eine reine Funktion zwei nützliche Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="3be19-108">As noted previously in this section, a pure function has two useful characteristics:</span></span>  
  
- <span data-ttu-id="3be19-109">Sie hat keine Nebenwirkungen.</span><span class="sxs-lookup"><span data-stu-id="3be19-109">It has no side effects.</span></span> <span data-ttu-id="3be19-110">Die Funktion ändert keine Variablen oder Daten irgendeines Typs außerhalb der Funktion.</span><span class="sxs-lookup"><span data-stu-id="3be19-110">The function does not change any variables or the data of any type outside of the function.</span></span>  
  
- <span data-ttu-id="3be19-111">Sie ist konsistent.</span><span class="sxs-lookup"><span data-stu-id="3be19-111">It is consistent.</span></span> <span data-ttu-id="3be19-112">Bei identischen Eingabedaten gibt die Funktion immer denselben Ausgabewert zurück.</span><span class="sxs-lookup"><span data-stu-id="3be19-112">Given the same set of input data, it will always return the same output value.</span></span>  
  
 <span data-ttu-id="3be19-113">Eine Möglichkeit des Umstiegs auf die funktionale Programmierung besteht darin, vorhandenen Code umzugestalten und so unnötige Nebenwirkungen und externe Abhängigkeiten abzuschaffen.</span><span class="sxs-lookup"><span data-stu-id="3be19-113">One way of transitioning to functional programming is to refactor existing code to eliminate unnecessary side effects and external dependencies.</span></span> <span data-ttu-id="3be19-114">Auf diese Weise können Sie Versionen von reinen Funktionen von vorhandenem Code erstellen.</span><span class="sxs-lookup"><span data-stu-id="3be19-114">In this way, you can create pure function versions of existing code.</span></span>  
  
 <span data-ttu-id="3be19-115">In diesem Thema wird erläutert, was eine reine Funktion ist und was nicht.</span><span class="sxs-lookup"><span data-stu-id="3be19-115">This topic discusses what a pure function is and what it is not.</span></span> <span data-ttu-id="3be19-116">Im [Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (C#)](./shape-of-wordprocessingml-documents.md) wird gezeigt, wie Sie ein WordprocessingML-Dokument bearbeiten können. Außerdem enthält dieses Tutorial zwei Beispiele für das Refactoring mithilfe einer reinen Funktion.</span><span class="sxs-lookup"><span data-stu-id="3be19-116">The [Tutorial: Manipulating Content in a WordprocessingML Document (C#)](./shape-of-wordprocessingml-documents.md) tutorial shows how to manipulate a WordprocessingML document, and includes two examples of how to refactor using a pure function.</span></span>  
  
## <a name="eliminating-side-effects-and-external-dependencies"></a><span data-ttu-id="3be19-117">Beseitigen von Nebenwirkungen und externen Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="3be19-117">Eliminating Side Effects and External Dependencies</span></span>  
 <span data-ttu-id="3be19-118">In den folgenden Beispielen werden zwei nicht reine Funktionen einer reinen Funktion gegenübergestellt.</span><span class="sxs-lookup"><span data-stu-id="3be19-118">The following examples contrast two non-pure functions and a pure function.</span></span>  
  
### <a name="non-pure-function-that-changes-a-class-member"></a><span data-ttu-id="3be19-119">Nicht reine Funktion, die einen Klassenmember ändert</span><span class="sxs-lookup"><span data-stu-id="3be19-119">Non-Pure Function that Changes a Class Member</span></span>  
 <span data-ttu-id="3be19-120">Im folgenden Code ist die `HyphenatedConcat`-Funktion keine reine Funktion, da sie den `aMember`-Datenmember in der Klasse ändert:</span><span class="sxs-lookup"><span data-stu-id="3be19-120">In the following code, the `HyphenatedConcat` function is not a pure function, because it modifies the `aMember` data member in the class:</span></span>  
  
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
  
 <span data-ttu-id="3be19-121">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3be19-121">This code produces the following output:</span></span>  
  
```output  
StringOne-StringTwo  
```  
  
 <span data-ttu-id="3be19-122">Ob die zu ändernden Daten `public`-Zugriff oder `private`-Zugriff besitzen oder ein `static`-Member bzw. ein Instanzmember sind, spielt keine Rolle.</span><span class="sxs-lookup"><span data-stu-id="3be19-122">Note that it is irrelevant whether the data being modified has `public` or `private` access, or is a `static` member or an instance member.</span></span> <span data-ttu-id="3be19-123">Reine Funktionen führen zu keinerlei Änderungen an Daten außerhalb der Funktion.</span><span class="sxs-lookup"><span data-stu-id="3be19-123">A pure function does not change any data outside of the function.</span></span>  
  
### <a name="non-pure-function-that-changes-an-argument"></a><span data-ttu-id="3be19-124">Nicht reine Funktion, die ein Argument ändert</span><span class="sxs-lookup"><span data-stu-id="3be19-124">Non-Pure Function that Changes an Argument</span></span>  
 <span data-ttu-id="3be19-125">Außerdem ist die folgende Version derselben Funktion keine reine Funktion, weil sie den Inhalt ihres Parameters, `sb`, ändert.</span><span class="sxs-lookup"><span data-stu-id="3be19-125">Furthermore, the following version of this same function is not pure because it modifies the contents of its parameter, `sb`.</span></span>  
  
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
  
 <span data-ttu-id="3be19-126">Diese Version des Programms produziert dieselbe Ausgabe wie die erste Version, weil die `HyphenatedConcat`-Funktion durch Aufrufen der <xref:System.Text.StringBuilder.Append%2A>-Memberfunktion den Wert (Status) ihres ersten Parameters geändert hat.</span><span class="sxs-lookup"><span data-stu-id="3be19-126">This version of the program produces the same output as the first version, because the `HyphenatedConcat` function has changed the value (state) of its first parameter by invoking the <xref:System.Text.StringBuilder.Append%2A> member function.</span></span> <span data-ttu-id="3be19-127">Beachten Sie, dass diese Änderung trotz der Tatsache auftritt, dass `HyphenatedConcat` mit Wertparameterübergabe arbeitet.</span><span class="sxs-lookup"><span data-stu-id="3be19-127">Note that this alteration occurs despite that fact that `HyphenatedConcat` uses call-by-value parameter passing.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3be19-128">Wenn Sie bei Verweistypen einen Parameter nach Wert übergeben, führt dies zu einer Kopie des Verweises auf ein zu übergebendes Objekt.</span><span class="sxs-lookup"><span data-stu-id="3be19-128">For reference types, if you pass a parameter by value, it results in a copy of the reference to an object being passed.</span></span> <span data-ttu-id="3be19-129">Diese Kopie ist weiterhin mit denselben Instanzdaten wie der ursprüngliche Verweis verknüpft (so lange, bis die Verweisvariable einem neuen Objekt zugewiesen wird).</span><span class="sxs-lookup"><span data-stu-id="3be19-129">This copy is still associated with the same instance data as the original reference (until the reference variable is assigned to a new object).</span></span> <span data-ttu-id="3be19-130">Für das Ändern eines Parameters durch einen Parameter ist die Referenzparameterübergabe nicht unbedingt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3be19-130">Call-by-reference is not necessarily required for a function to modify a parameter.</span></span>  
  
### <a name="pure-function"></a><span data-ttu-id="3be19-131">Reine Funktion</span><span class="sxs-lookup"><span data-stu-id="3be19-131">Pure Function</span></span>  
<span data-ttu-id="3be19-132">Die nächste Version des Programms zeigt, wie die `HyphenatedConcat`-Funktion als reine Funktion implementiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="3be19-132">This next version of the program shows how to implement the `HyphenatedConcat` function as a pure function.</span></span>  
  
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
  
 <span data-ttu-id="3be19-133">Auch diese Version erzeugt dieselbe Zeile in der Ausgabe: `StringOne-StringTwo`.</span><span class="sxs-lookup"><span data-stu-id="3be19-133">Again, this version produces the same line of output: `StringOne-StringTwo`.</span></span> <span data-ttu-id="3be19-134">Um den verketteten Wert beizubehalten, wird er in der Zwischenvariable `s2` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3be19-134">Note that to retain the concatenated value, it is stored in the intermediate variable `s2`.</span></span>  
  
 <span data-ttu-id="3be19-135">Ein Ansatz, der sich als sehr hilfreich erweisen kann, besteht darin, Funktionen zu schreiben, die zwar lokal unrein (also lokale Variablen deklarieren und ändern), global aber rein sind.</span><span class="sxs-lookup"><span data-stu-id="3be19-135">One approach that can be very useful is to write functions that are locally impure (that is, they declare and modify local variables) but are globally pure.</span></span> <span data-ttu-id="3be19-136">Solche Funktionen besitzen viele der wünschenswerten Zusammensetzbarkeitseigenschaften, vermeiden dabei aber einige der komplizierteren Idiome der funktionalen Programmierung, z. B. die Notwendigkeit der Verwendung der Rekursion, wenn eine einfache Schleife dasselbe Ziel erreichen würde.</span><span class="sxs-lookup"><span data-stu-id="3be19-136">Such functions have many of the desirable composability characteristics, but avoid some of the more convoluted functional programming idioms, such as having to use recursion when a simple loop would accomplish the same thing.</span></span>  
  
## <a name="standard-query-operators"></a><span data-ttu-id="3be19-137">Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="3be19-137">Standard Query Operators</span></span>  
 <span data-ttu-id="3be19-138">Ein wichtiges Merkmal der Standardabfrageoperatoren besteht darin, dass sie als reine Funktionen implementiert sind.</span><span class="sxs-lookup"><span data-stu-id="3be19-138">An important characteristic of the standard query operators is that they are implemented as pure functions.</span></span>  
  
 <span data-ttu-id="3be19-139">Weitere Informationen finden Sie unter [Übersicht über Standardabfrageoperatoren (C#)](./standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3be19-139">For more information, see [Standard Query Operators Overview (C#)](./standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3be19-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3be19-140">See also</span></span>

- [<span data-ttu-id="3be19-141">Introduction to Pure Functional Transformations (C#) (Einführung in reine funktionale Transformationen (c#))</span><span class="sxs-lookup"><span data-stu-id="3be19-141">Introduction to Pure Functional Transformations (C#)</span></span>](./introduction-to-pure-functional-transformations.md)
- [<span data-ttu-id="3be19-142">Funktionale Programmierung und Imperative Programmierung (C#)</span><span class="sxs-lookup"><span data-stu-id="3be19-142">Functional Programming vs. Imperative Programming (C#)</span></span>](./functional-programming-vs-imperative-programming.md)
