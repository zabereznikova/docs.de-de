---
title: Verwenden von Namespaces (C#-Programmierhandbuch)
ms.date: 07/20/2015
f1_keywords:
- cs.names
helpviewer_keywords:
- fully qualified names [C#]
- namespaces [C#], how to use
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
ms.openlocfilehash: 81876d1818a6e82764e4aea0ae2b6f9e091f0ba3
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45648498"
---
# <a name="using-namespaces-c-programming-guide"></a><span data-ttu-id="610f5-102">Verwenden von Namespaces (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="610f5-102">Using Namespaces (C# Programming Guide)</span></span>
<span data-ttu-id="610f5-103">Namespaces werden häufig in C# -Programmen auf zwei verschiedene Arten verwendet.</span><span class="sxs-lookup"><span data-stu-id="610f5-103">Namespaces are heavily used within C# programs in two ways.</span></span> <span data-ttu-id="610f5-104">Erstens: Die .NET Framework-Klassen verwenden Namespaces, um ihre zahlreichen Klassen zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="610f5-104">Firstly, the .NET Framework classes use namespaces to organize its many classes.</span></span> <span data-ttu-id="610f5-105">Zweitens: Eigene Namespaces zu deklarieren kann Ihnen dabei helfen, den Umfang der Klassen- und Methodennamen in größeren Programmierprojekten zu steuern.</span><span class="sxs-lookup"><span data-stu-id="610f5-105">Secondly, declaring your own namespaces can help control the scope of class and method names in larger programming projects.</span></span>  
  
## <a name="accessing-namespaces"></a><span data-ttu-id="610f5-106">Zugriff auf Namespaces</span><span class="sxs-lookup"><span data-stu-id="610f5-106">Accessing Namespaces</span></span>  
 <span data-ttu-id="610f5-107">Die meisten C#-Anwendungen beginnen mit einem Abschnitt von `using`-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="610f5-107">Most C# applications begin with a section of `using` directives.</span></span> <span data-ttu-id="610f5-108">Dieser Abschnitt enthält die von der Anwendung häufig verwendeten Namespaces und erspart dem Programmierer die Angabe eines vollqualifizierten Namens bei jedem Verwenden einer enthaltenen Methode.</span><span class="sxs-lookup"><span data-stu-id="610f5-108">This section lists the namespaces that the application will be using frequently, and saves the programmer from specifying a fully qualified name every time that a method that is contained within is used.</span></span>  
  
 <span data-ttu-id="610f5-109">Z.B. durch das Einfügen der Zeile</span><span class="sxs-lookup"><span data-stu-id="610f5-109">For example, by including the line:</span></span>  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_1.cs)]  
  
 <span data-ttu-id="610f5-110">Bei Programmstart kann der Programmierer folgenden Code verwenden:</span><span class="sxs-lookup"><span data-stu-id="610f5-110">At the start of a program, the programmer can use the code:</span></span>  
  
 [!code-csharp[csProgGuide#31](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_2.cs)]  
  
 <span data-ttu-id="610f5-111">anstelle von:</span><span class="sxs-lookup"><span data-stu-id="610f5-111">Instead of:</span></span>  
  
 [!code-csharp[csProgGuide#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_3.cs)]  
  
## <a name="namespace-aliases"></a><span data-ttu-id="610f5-112">Namespacealiase</span><span class="sxs-lookup"><span data-stu-id="610f5-112">Namespace Aliases</span></span>  
 <span data-ttu-id="610f5-113">Die [using-Anweisungen](../../../csharp/language-reference/keywords/using-directive.md) kann auch zum Erstellen eines Alias für einen [Namespace](../../../csharp/language-reference/keywords/namespace.md) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="610f5-113">The [using Directive](../../../csharp/language-reference/keywords/using-directive.md) can also be used to create an alias for a [namespace](../../../csharp/language-reference/keywords/namespace.md).</span></span> <span data-ttu-id="610f5-114">Wenn Sie einen bereits vorhandenen Namespace verwenden, der geschachtelte Namespaces enthält, können Sie einen Alias deklarieren, als schnelle Möglichkeit um auf einen bestimmten geschachtelten Namespace zu verweisen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="610f5-114">For example, if you are using a previously written namespace that contains nested namespaces, you might want to declare an alias to provide a shorthand way of referencing one in particular, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#7](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_4.cs)]  
  
## <a name="using-namespaces-to-control-scope"></a><span data-ttu-id="610f5-115">Verwenden von Namespaces zur Steuerung des Gültigkeitsbereichs</span><span class="sxs-lookup"><span data-stu-id="610f5-115">Using Namespaces to control scope</span></span>  
 <span data-ttu-id="610f5-116">Mit dem Schlüsselwort `namespace` wird ein Bereich deklariert.</span><span class="sxs-lookup"><span data-stu-id="610f5-116">The `namespace` keyword is used to declare a scope.</span></span> <span data-ttu-id="610f5-117">Die Möglichkeit zum Erstellen von Bereichen innerhalb des Projekts, hilft Ihnen den Code zu organisieren und ermöglicht Ihnen die Erstellung von global eindeutigen Typen.</span><span class="sxs-lookup"><span data-stu-id="610f5-117">The ability to create scopes within your project helps organize code and lets you create globally-unique types.</span></span> <span data-ttu-id="610f5-118">Im folgenden Beispiel, wird eine Klasse mit dem Titel `SampleClass` in zwei ineinander geschachtelten Namespaces definiert.</span><span class="sxs-lookup"><span data-stu-id="610f5-118">In the following example, a class titled `SampleClass` is defined in two namespaces, one nested inside the other.</span></span> <span data-ttu-id="610f5-119">Die [. Operator](../../../csharp/language-reference/operators/member-access-operator.md) wird verwendet, um zu unterscheiden, welche Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="610f5-119">The [. Operator](../../../csharp/language-reference/operators/member-access-operator.md) is used to differentiate which method gets called.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#8](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_5.cs)]  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="610f5-120">Vollqualifizierte Namen</span><span class="sxs-lookup"><span data-stu-id="610f5-120">Fully Qualified Names</span></span>  
 <span data-ttu-id="610f5-121">Namespaces und Typen verfügen über eindeutige durch den vollqualifizierten Namen, die eine logische Hierarchie an.</span><span class="sxs-lookup"><span data-stu-id="610f5-121">Namespaces and types have unique titles described by fully qualified names that indicate a logical hierarchy.</span></span> <span data-ttu-id="610f5-122">Beispielsweise impliziert die Anweisung `A.B`, dass `A` der Name des Namespaces oder des Typs ist und, dass `B` darin geschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="610f5-122">For example, the statement `A.B` implies that `A` is the name of the namespace or type, and `B` is nested inside it.</span></span>  
  
 <span data-ttu-id="610f5-123">Im folgenden Beispiel gibt es geschachtelte Klassen und Namespaces.</span><span class="sxs-lookup"><span data-stu-id="610f5-123">In the following example, there are nested classes and namespaces.</span></span> <span data-ttu-id="610f5-124">Der vollqualifizierte Name ist als Kommentar angegeben, der auf jede Entität folgt.</span><span class="sxs-lookup"><span data-stu-id="610f5-124">The fully qualified name is indicated as a comment following each entity.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#9](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_6.cs)]  
  
 <span data-ttu-id="610f5-125">Das vorherige Codesegment weist Folgendes auf:</span><span class="sxs-lookup"><span data-stu-id="610f5-125">In the previous code segment:</span></span>  
  
-   <span data-ttu-id="610f5-126">Der Namespace `N1` ist ein Mitglied des globalen Namespaces.</span><span class="sxs-lookup"><span data-stu-id="610f5-126">The namespace `N1` is a member of the global namespace.</span></span> <span data-ttu-id="610f5-127">Sein vollqualifizierter Name lautet `N1`.</span><span class="sxs-lookup"><span data-stu-id="610f5-127">Its fully qualified name is `N1`.</span></span>  
  
-   <span data-ttu-id="610f5-128">Der Namespace `N2` ist ein Mitglied von `N1`.</span><span class="sxs-lookup"><span data-stu-id="610f5-128">The namespace `N2` is a member of `N1`.</span></span> <span data-ttu-id="610f5-129">Sein vollqualifizierter Name lautet `N1.N2`.</span><span class="sxs-lookup"><span data-stu-id="610f5-129">Its fully qualified name is `N1.N2`.</span></span>  
  
-   <span data-ttu-id="610f5-130">Die Klasse `C1` ist ein Mitglied von `N1`.</span><span class="sxs-lookup"><span data-stu-id="610f5-130">The class `C1` is a member of `N1`.</span></span> <span data-ttu-id="610f5-131">Sein vollqualifizierter Name lautet `N1.C1`.</span><span class="sxs-lookup"><span data-stu-id="610f5-131">Its fully qualified name is `N1.C1`.</span></span>  
  
-   <span data-ttu-id="610f5-132">Der Klassenname `C2` wird zweimal in diesem Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="610f5-132">The class name `C2` is used two times in this code.</span></span> <span data-ttu-id="610f5-133">Die vollqualifizierten Namen sind jedoch eindeutig.</span><span class="sxs-lookup"><span data-stu-id="610f5-133">However, the fully qualified names are unique.</span></span> <span data-ttu-id="610f5-134">Die erste Instanz von `C2` wird in `C1` deklariert; daher lautet der vollqualifizierte Name: `N1.C1.C2`.</span><span class="sxs-lookup"><span data-stu-id="610f5-134">The first instance of `C2` is declared inside `C1`; therefore, its fully qualified name is: `N1.C1.C2`.</span></span> <span data-ttu-id="610f5-135">Die zweite Instanz von `C2` wird in einem Namespace `N2` deklariert; daher lautet der vollqualifizierte Name: `N1.N2.C2`.</span><span class="sxs-lookup"><span data-stu-id="610f5-135">The second instance of `C2` is declared inside a namespace `N2`; therefore, its fully qualified name is `N1.N2.C2`.</span></span>  
  
 <span data-ttu-id="610f5-136">Mithilfe des vorhergehenden Codesegments können Sie dem Namespace `N1.N2` ein neues Klassenmitglied `C3` wie folgt hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="610f5-136">Using the previous code segment, you can add a new class member, `C3`, to the namespace `N1.N2` as follows:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#10](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_7.cs)]  
  
 <span data-ttu-id="610f5-137">Im Allgemeinen verwenden Sie `::`, um auf einen Namespacealias, oder `global::`, um auf den globalen Namespace zu verweisen, und `.`, um Typen oder Mitglieder zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="610f5-137">In general, use `::` to reference a namespace alias or `global::` to reference the global namespace and `.` to qualify types or members.</span></span>  
  
 <span data-ttu-id="610f5-138">Die Verwendung von `::` mit einem Alias, der auf einen Typ statt auf einen Namespace verweist ist ein Fehler.</span><span class="sxs-lookup"><span data-stu-id="610f5-138">It is an error to use `::` with an alias that references a type instead of a namespace.</span></span> <span data-ttu-id="610f5-139">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="610f5-139">For example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#11](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_8.cs)]  
  
 [!code-csharp[csProgGuideNamespaces#12](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_9.cs)]  
  
 <span data-ttu-id="610f5-140">Beachten Sie, dass das Wort `global` kein vorderfinierter Alias ist; deshalb hat `global.X` keine spezielle Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="610f5-140">Remember that the word `global` is not a predefined alias; therefore, `global.X` does not have any special meaning.</span></span> <span data-ttu-id="610f5-141">Er erhält erst dann eine besondere Bedeutung, wenn er mit `::` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="610f5-141">It acquires a special meaning only when it is used with `::`.</span></span>  
  
 <span data-ttu-id="610f5-142">Compilerwarnung CS0440 wird generiert, wenn Sie einen Alias mit dem Namen global definieren, da `global::` immer ein Verweis auf den globalen Namespace und nicht auf einen Alias ist.</span><span class="sxs-lookup"><span data-stu-id="610f5-142">Compiler warning CS0440 is generated if you define an alias named global because `global::` always references the global namespace and not an alias.</span></span> <span data-ttu-id="610f5-143">Beispielsweise generiert die folgende Zeile die folgende Warnung:</span><span class="sxs-lookup"><span data-stu-id="610f5-143">For example, the following line generates the warning:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#13](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_10.cs)]  
  
 <span data-ttu-id="610f5-144">Die Verwendung von `::` mit Aliasen ist ratsam, und verhindert die unbeabsichtigte Einführung von zusätzlichen Typen.</span><span class="sxs-lookup"><span data-stu-id="610f5-144">Using `::` with aliases is a good idea and protects against the unexpected introduction of additional types.</span></span> <span data-ttu-id="610f5-145">Betrachten Sie beispielsweise das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="610f5-145">For example, consider this example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#14](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_11.cs)]  
  
 [!code-csharp[csProgGuideNamespaces#15](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_12.cs)]  
  
 <span data-ttu-id="610f5-146">Dies funktioniert, aber wenn anschließend ein Typ mit dem Namen `Alias` eingeführt werden würde, würde `Alias.` an diesen Typ gebunden.</span><span class="sxs-lookup"><span data-stu-id="610f5-146">This works, but if a type named `Alias` were to subsequently be introduced, `Alias.` would bind to that type instead.</span></span> <span data-ttu-id="610f5-147">Mit `Alias::Exception` wird sichergestellt, dass `Alias` als ein Namespacealias behandelt und nicht für einen Typ gehalten wird.</span><span class="sxs-lookup"><span data-stu-id="610f5-147">Using `Alias::Exception` insures that `Alias` is treated as a namespace alias and not mistaken for a type.</span></span>  
  
 <span data-ttu-id="610f5-148">Finden Sie im Thema [Vorgehensweise: Verwenden des globalen Namespacealias](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md) Informationen zum `global` Alias.</span><span class="sxs-lookup"><span data-stu-id="610f5-148">See the topic [How to: Use the Global Namespace Alias](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md) for more information regarding the `global` alias.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="610f5-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="610f5-149">See Also</span></span>

- [<span data-ttu-id="610f5-150">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="610f5-150">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="610f5-151">Namespaces</span><span class="sxs-lookup"><span data-stu-id="610f5-151">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
- [<span data-ttu-id="610f5-152">Namespaceschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="610f5-152">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [<span data-ttu-id="610f5-153"> Operator</span><span class="sxs-lookup"><span data-stu-id="610f5-153">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)  
- [<span data-ttu-id="610f5-154">::-Operator</span><span class="sxs-lookup"><span data-stu-id="610f5-154">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
- [<span data-ttu-id="610f5-155">extern</span><span class="sxs-lookup"><span data-stu-id="610f5-155">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)
