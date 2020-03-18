---
title: Verwenden von Namespaces – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- cs.names
helpviewer_keywords:
- fully qualified names [C#]
- namespaces [C#], how to use
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
ms.openlocfilehash: 5193fc7aaae83cbc0c75e81835244eaaaece69a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75700197"
---
# <a name="using-namespaces-c-programming-guide"></a><span data-ttu-id="3bce5-102">Verwenden von Namespaces (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="3bce5-102">Using namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="3bce5-103">Namespaces werden häufig in C# -Programmen auf zwei verschiedene Arten verwendet.</span><span class="sxs-lookup"><span data-stu-id="3bce5-103">Namespaces are heavily used within C# programs in two ways.</span></span> <span data-ttu-id="3bce5-104">Erstens: Die .NET Framework-Klassen verwenden Namespaces, um ihre zahlreichen Klassen zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="3bce5-104">Firstly, the .NET Framework classes use namespaces to organize its many classes.</span></span> <span data-ttu-id="3bce5-105">Zweitens: Eigene Namespaces zu deklarieren kann Ihnen dabei helfen, den Umfang der Klassen- und Methodennamen in größeren Programmierprojekten zu steuern.</span><span class="sxs-lookup"><span data-stu-id="3bce5-105">Secondly, declaring your own namespaces can help control the scope of class and method names in larger programming projects.</span></span>  
  
## <a name="accessing-namespaces"></a><span data-ttu-id="3bce5-106">Zugriff auf Namespaces</span><span class="sxs-lookup"><span data-stu-id="3bce5-106">Accessing namespaces</span></span>

 <span data-ttu-id="3bce5-107">Die meisten C#-Anwendungen beginnen mit einem Abschnitt von `using`-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="3bce5-107">Most C# applications begin with a section of `using` directives.</span></span> <span data-ttu-id="3bce5-108">Dieser Abschnitt enthält die von der Anwendung häufig verwendeten Namespaces und erspart dem Programmierer die Angabe eines vollqualifizierten Namens bei jedem Verwenden einer enthaltenen Methode.</span><span class="sxs-lookup"><span data-stu-id="3bce5-108">This section lists the namespaces that the application will be using frequently, and saves the programmer from specifying a fully qualified name every time that a method that is contained within is used.</span></span>  
  
 <span data-ttu-id="3bce5-109">Z.B. durch das Einfügen der Zeile</span><span class="sxs-lookup"><span data-stu-id="3bce5-109">For example, by including the line:</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 <span data-ttu-id="3bce5-110">Bei Programmstart kann der Programmierer folgenden Code verwenden:</span><span class="sxs-lookup"><span data-stu-id="3bce5-110">At the start of a program, the programmer can use the code:</span></span>  
  
 [!code-csharp[csProgGuide#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#31)]  
  
 <span data-ttu-id="3bce5-111">anstelle von:</span><span class="sxs-lookup"><span data-stu-id="3bce5-111">Instead of:</span></span>  
  
 [!code-csharp[csProgGuide#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#30)]  
  
## <a name="namespace-aliases"></a><span data-ttu-id="3bce5-112">Namespacealiase</span><span class="sxs-lookup"><span data-stu-id="3bce5-112">Namespace aliases</span></span>

 <span data-ttu-id="3bce5-113">Sie können auch die [`using`-Anweisung](../../language-reference/keywords/using-directive.md) verwenden, um einen Alias für einen Namespace zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3bce5-113">You also can use the [`using` directive](../../language-reference/keywords/using-directive.md) to create an alias for a namespace.</span></span> <span data-ttu-id="3bce5-114">Verwenden Sie [den Namespacealias-Qualifizierer`::`](../../language-reference/operators/namespace-alias-qualifier.md), um auf die Member des Namespace mit Alias zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="3bce5-114">Use the [namespace alias qualifier `::`](../../language-reference/operators/namespace-alias-qualifier.md) to access the members of the aliased namespace.</span></span> <span data-ttu-id="3bce5-115">Im folgenden Beispiel wird gezeigt, wie ein Namespacealias erstellt und verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="3bce5-115">The following example shows how to create and use a namespace alias:</span></span>
  
[!code-csharp[csProgGuideNamespaces#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#5)]
  
## <a name="using-namespaces-to-control-scope"></a><span data-ttu-id="3bce5-116">Verwenden von Namespaces zur Steuerung des Gültigkeitsbereichs</span><span class="sxs-lookup"><span data-stu-id="3bce5-116">Using namespaces to control scope</span></span>

 <span data-ttu-id="3bce5-117">Mit dem Schlüsselwort `namespace` wird ein Bereich deklariert.</span><span class="sxs-lookup"><span data-stu-id="3bce5-117">The `namespace` keyword is used to declare a scope.</span></span> <span data-ttu-id="3bce5-118">Die Möglichkeit zum Erstellen von Bereichen innerhalb des Projekts, hilft Ihnen den Code zu organisieren und ermöglicht Ihnen die Erstellung von global eindeutigen Typen.</span><span class="sxs-lookup"><span data-stu-id="3bce5-118">The ability to create scopes within your project helps organize code and lets you create globally-unique types.</span></span> <span data-ttu-id="3bce5-119">Im folgenden Beispiel, wird eine Klasse mit dem Titel `SampleClass` in zwei ineinander geschachtelten Namespaces definiert.</span><span class="sxs-lookup"><span data-stu-id="3bce5-119">In the following example, a class titled `SampleClass` is defined in two namespaces, one nested inside the other.</span></span> <span data-ttu-id="3bce5-120">Der [Operator `.` für den Memberzugriff](../../language-reference/operators/member-access-operators.md#member-access-operator-) wird verwendet, um zu unterscheiden, welche Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="3bce5-120">The [member access `.` operator](../../language-reference/operators/member-access-operators.md#member-access-operator-) is used to differentiate which method gets called.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#8)]  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="3bce5-121">Vollqualifizierte Namen</span><span class="sxs-lookup"><span data-stu-id="3bce5-121">Fully qualified names</span></span>

 <span data-ttu-id="3bce5-122">Namespaces und Typen verfügen über eindeutige durch den vollqualifizierten Namen, die eine logische Hierarchie an.</span><span class="sxs-lookup"><span data-stu-id="3bce5-122">Namespaces and types have unique titles described by fully qualified names that indicate a logical hierarchy.</span></span> <span data-ttu-id="3bce5-123">Beispielsweise impliziert die Anweisung `A.B`, dass `A` der Name des Namespaces oder des Typs ist und, dass `B` darin geschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="3bce5-123">For example, the statement `A.B` implies that `A` is the name of the namespace or type, and `B` is nested inside it.</span></span>  
  
 <span data-ttu-id="3bce5-124">Im folgenden Beispiel gibt es geschachtelte Klassen und Namespaces.</span><span class="sxs-lookup"><span data-stu-id="3bce5-124">In the following example, there are nested classes and namespaces.</span></span> <span data-ttu-id="3bce5-125">Der vollqualifizierte Name ist als Kommentar angegeben, der auf jede Entität folgt.</span><span class="sxs-lookup"><span data-stu-id="3bce5-125">The fully qualified name is indicated as a comment following each entity.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#9)]  
  
 <span data-ttu-id="3bce5-126">Das vorherige Codesegment weist Folgendes auf:</span><span class="sxs-lookup"><span data-stu-id="3bce5-126">In the previous code segment:</span></span>  
  
- <span data-ttu-id="3bce5-127">Der Namespace `N1` ist ein Mitglied des globalen Namespaces.</span><span class="sxs-lookup"><span data-stu-id="3bce5-127">The namespace `N1` is a member of the global namespace.</span></span> <span data-ttu-id="3bce5-128">Sein vollqualifizierter Name lautet `N1`.</span><span class="sxs-lookup"><span data-stu-id="3bce5-128">Its fully qualified name is `N1`.</span></span>  
  
- <span data-ttu-id="3bce5-129">Der Namespace `N2` ist ein Mitglied von `N1`.</span><span class="sxs-lookup"><span data-stu-id="3bce5-129">The namespace `N2` is a member of `N1`.</span></span> <span data-ttu-id="3bce5-130">Sein vollqualifizierter Name lautet `N1.N2`.</span><span class="sxs-lookup"><span data-stu-id="3bce5-130">Its fully qualified name is `N1.N2`.</span></span>  
  
- <span data-ttu-id="3bce5-131">Die Klasse `C1` ist ein Mitglied von `N1`.</span><span class="sxs-lookup"><span data-stu-id="3bce5-131">The class `C1` is a member of `N1`.</span></span> <span data-ttu-id="3bce5-132">Sein vollqualifizierter Name lautet `N1.C1`.</span><span class="sxs-lookup"><span data-stu-id="3bce5-132">Its fully qualified name is `N1.C1`.</span></span>  
  
- <span data-ttu-id="3bce5-133">Der Klassenname `C2` wird zweimal in diesem Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="3bce5-133">The class name `C2` is used two times in this code.</span></span> <span data-ttu-id="3bce5-134">Die vollqualifizierten Namen sind jedoch eindeutig.</span><span class="sxs-lookup"><span data-stu-id="3bce5-134">However, the fully qualified names are unique.</span></span> <span data-ttu-id="3bce5-135">Die erste Instanz von `C2` wird in `C1` deklariert; daher lautet der vollqualifizierte Name: `N1.C1.C2`.</span><span class="sxs-lookup"><span data-stu-id="3bce5-135">The first instance of `C2` is declared inside `C1`; therefore, its fully qualified name is: `N1.C1.C2`.</span></span> <span data-ttu-id="3bce5-136">Die zweite Instanz von `C2` wird in einem Namespace `N2` deklariert; daher lautet der vollqualifizierte Name: `N1.N2.C2`.</span><span class="sxs-lookup"><span data-stu-id="3bce5-136">The second instance of `C2` is declared inside a namespace `N2`; therefore, its fully qualified name is `N1.N2.C2`.</span></span>  
  
 <span data-ttu-id="3bce5-137">Mithilfe des vorhergehenden Codesegments können Sie dem Namespace `C3` ein neues Klassenmitglied `N1.N2` wie folgt hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="3bce5-137">Using the previous code segment, you can add a new class member, `C3`, to the namespace `N1.N2` as follows:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#10)]  
  
 <span data-ttu-id="3bce5-138">Im Allgemeinen verwenden Sie den [Namespacealias-Qualifizierer `::`](../../language-reference/operators/namespace-alias-qualifier.md), um auf einen Namespacealias, oder `global::`, um auf den globalen Namespace zu verweisen, und `.`, um Typen oder Mitglieder zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="3bce5-138">In general, use the [namespace alias qualifier `::`](../../language-reference/operators/namespace-alias-qualifier.md) to reference a namespace alias or `global::` to reference the global namespace and `.` to qualify types or members.</span></span>  
  
 <span data-ttu-id="3bce5-139">Die Verwendung von `::` mit einem Alias, der auf einen Typ statt auf einen Namespace verweist ist ein Fehler.</span><span class="sxs-lookup"><span data-stu-id="3bce5-139">It is an error to use `::` with an alias that references a type instead of a namespace.</span></span> <span data-ttu-id="3bce5-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3bce5-140">For example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#11)]  
  
 [!code-csharp[csProgGuideNamespaces#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#12)]  
  
 <span data-ttu-id="3bce5-141">Beachten Sie, dass das Wort `global` kein vorderfinierter Alias ist; deshalb hat `global.X` keine spezielle Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="3bce5-141">Remember that the word `global` is not a predefined alias; therefore, `global.X` does not have any special meaning.</span></span> <span data-ttu-id="3bce5-142">Er erhält erst dann eine besondere Bedeutung, wenn er mit `::` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3bce5-142">It acquires a special meaning only when it is used with `::`.</span></span>  
  
 <span data-ttu-id="3bce5-143">Compilerwarnung CS0440 wird generiert, wenn Sie einen Alias mit dem Namen global definieren, da `global::` immer ein Verweis auf den globalen Namespace und nicht auf einen Alias ist.</span><span class="sxs-lookup"><span data-stu-id="3bce5-143">Compiler warning CS0440 is generated if you define an alias named global because `global::` always references the global namespace and not an alias.</span></span> <span data-ttu-id="3bce5-144">Beispielsweise generiert die folgende Zeile die folgende Warnung:</span><span class="sxs-lookup"><span data-stu-id="3bce5-144">For example, the following line generates the warning:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#13)]  
  
 <span data-ttu-id="3bce5-145">Die Verwendung von `::` mit Aliasen ist ratsam, und verhindert die unbeabsichtigte Einführung von zusätzlichen Typen.</span><span class="sxs-lookup"><span data-stu-id="3bce5-145">Using `::` with aliases is a good idea and protects against the unexpected introduction of additional types.</span></span> <span data-ttu-id="3bce5-146">Betrachten Sie beispielsweise das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3bce5-146">For example, consider this example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#14)]  
  
 [!code-csharp[csProgGuideNamespaces#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#15)]  
  
 <span data-ttu-id="3bce5-147">Dies funktioniert, aber wenn anschließend ein Typ mit dem Namen `Alias` eingeführt werden würde, würde `Alias.` an diesen Typ gebunden.</span><span class="sxs-lookup"><span data-stu-id="3bce5-147">This works, but if a type named `Alias` were to subsequently be introduced, `Alias.` would bind to that type instead.</span></span> <span data-ttu-id="3bce5-148">Mit `Alias::Exception` wird sichergestellt, dass `Alias` als ein Namespacealias behandelt und nicht für einen Typ gehalten wird.</span><span class="sxs-lookup"><span data-stu-id="3bce5-148">Using `Alias::Exception` ensures that `Alias` is treated as a namespace alias and not mistaken for a type.</span></span>  

## <a name="see-also"></a><span data-ttu-id="3bce5-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3bce5-149">See also</span></span>

- [<span data-ttu-id="3bce5-150">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3bce5-150">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3bce5-151">Namespaces</span><span class="sxs-lookup"><span data-stu-id="3bce5-151">Namespaces</span></span>](./index.md)
- [<span data-ttu-id="3bce5-152">.-Operator</span><span class="sxs-lookup"><span data-stu-id="3bce5-152">. operator</span></span>](../../language-reference/operators/member-access-operators.md#member-access-operator-)
- [<span data-ttu-id="3bce5-153">::-Operator</span><span class="sxs-lookup"><span data-stu-id="3bce5-153">:: operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="3bce5-154">extern alias</span><span class="sxs-lookup"><span data-stu-id="3bce5-154">extern alias</span></span>](../../language-reference/keywords/extern-alias.md)
