---
title: Verwenden von Namespaces (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.names
dev_langs:
- CSharp
helpviewer_keywords:
- fully qualified names [C#]
- namespaces [C#], how to use
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
caps.latest.revision: 26
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
ms.openlocfilehash: 61b5d78f1c4924e3858c14876d36e52d4ee46ceb
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="using-namespaces-c-programming-guide"></a><span data-ttu-id="82dac-102">Verwenden von Namespaces (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="82dac-102">Using Namespaces (C# Programming Guide)</span></span>
<span data-ttu-id="82dac-103">Namespaces werden häufig in C# -Programmen auf zwei verschiedene Arten verwendet.</span><span class="sxs-lookup"><span data-stu-id="82dac-103">Namespaces are heavily used within C# programs in two ways.</span></span> <span data-ttu-id="82dac-104">Erstens: Die .NET Framework-Klassen verwenden Namespaces, um ihre zahlreichen Klassen zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="82dac-104">Firstly, the .NET Framework classes use namespaces to organize its many classes.</span></span> <span data-ttu-id="82dac-105">Zweitens: Eigene Namespaces zu deklarieren kann Ihnen dabei helfen, den Umfang der Klassen- und Methodennamen in größeren Programmierprojekten zu steuern.</span><span class="sxs-lookup"><span data-stu-id="82dac-105">Secondly, declaring your own namespaces can help control the scope of class and method names in larger programming projects.</span></span>  
  
## <a name="accessing-namespaces"></a><span data-ttu-id="82dac-106">Zugriff auf Namespaces</span><span class="sxs-lookup"><span data-stu-id="82dac-106">Accessing Namespaces</span></span>  
 <span data-ttu-id="82dac-107">Die meisten C#-Anwendungen beginnen mit einem Abschnitt von `using`-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="82dac-107">Most C# applications begin with a section of `using` directives.</span></span> <span data-ttu-id="82dac-108">Dieser Abschnitt enthält die von der Anwendung häufig verwendeten Namespaces und erspart dem Programmierer die Angabe eines vollqualifizierten Namens bei jedem Verwenden einer enthaltenen Methode.</span><span class="sxs-lookup"><span data-stu-id="82dac-108">This section lists the namespaces that the application will be using frequently, and saves the programmer from specifying a fully qualified name every time that a method that is contained within is used.</span></span>  
  
 <span data-ttu-id="82dac-109">Z.B. durch das Einfügen der Zeile</span><span class="sxs-lookup"><span data-stu-id="82dac-109">For example, by including the line:</span></span>  
  
 <span data-ttu-id="82dac-110">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="82dac-110">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_1.cs)]</span></span>  
  
 <span data-ttu-id="82dac-111">Bei Programmstart kann der Programmierer folgenden Code verwenden:</span><span class="sxs-lookup"><span data-stu-id="82dac-111">At the start of a program, the programmer can use the code:</span></span>  
  
 <span data-ttu-id="82dac-112">[!code-cs[CsProgGuide#31](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="82dac-112">[!code-cs[csProgGuide#31](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_2.cs)]</span></span>  
  
 <span data-ttu-id="82dac-113">anstelle von:</span><span class="sxs-lookup"><span data-stu-id="82dac-113">Instead of:</span></span>  
  
 <span data-ttu-id="82dac-114">[!code-cs[CsProgGuide#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="82dac-114">[!code-cs[csProgGuide#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_3.cs)]</span></span>  
  
## <a name="namespace-aliases"></a><span data-ttu-id="82dac-115">Namespacealiase</span><span class="sxs-lookup"><span data-stu-id="82dac-115">Namespace Aliases</span></span>  
 <span data-ttu-id="82dac-116">Die [using-Anweisungen](../../../csharp/language-reference/keywords/using-directive.md) kann auch zum Erstellen eines Alias für einen [Namespace](../../../csharp/language-reference/keywords/namespace.md) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="82dac-116">The [using Directive](../../../csharp/language-reference/keywords/using-directive.md) can also be used to create an alias for a [namespace](../../../csharp/language-reference/keywords/namespace.md).</span></span> <span data-ttu-id="82dac-117">Wenn Sie einen bereits vorhandenen Namespace verwenden, der geschachtelte Namespaces enthält, können Sie einen Alias deklarieren, als schnelle Möglichkeit um auf einen bestimmten geschachtelten Namespace zu verweisen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="82dac-117">For example, if you are using a previously written namespace that contains nested namespaces, you might want to declare an alias to provide a shorthand way of referencing one in particular, as in the following example:</span></span>  
  
 <span data-ttu-id="82dac-118">[!code-cs[CsProgGuideNamespaces#7](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="82dac-118">[!code-cs[csProgGuideNamespaces#7](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_4.cs)]</span></span>  
  
## <a name="using-namespaces-to-control-scope"></a><span data-ttu-id="82dac-119">Verwenden von Namespaces zur Steuerung des Gültigkeitsbereichs</span><span class="sxs-lookup"><span data-stu-id="82dac-119">Using Namespaces to control scope</span></span>  
 <span data-ttu-id="82dac-120">Mit dem Schlüsselwort `namespace` wird ein Bereich deklariert.</span><span class="sxs-lookup"><span data-stu-id="82dac-120">The `namespace` keyword is used to declare a scope.</span></span> <span data-ttu-id="82dac-121">Die Möglichkeit zum Erstellen von Bereichen innerhalb des Projekts, hilft Ihnen den Code zu organisieren und ermöglicht Ihnen die Erstellung von global eindeutigen Typen.</span><span class="sxs-lookup"><span data-stu-id="82dac-121">The ability to create scopes within your project helps organize code and lets you create globally-unique types.</span></span> <span data-ttu-id="82dac-122">Im folgenden Beispiel, wird eine Klasse mit dem Titel `SampleClass` in zwei ineinander geschachtelten Namespaces definiert.</span><span class="sxs-lookup"><span data-stu-id="82dac-122">In the following example, a class titled `SampleClass` is defined in two namespaces, one nested inside the other.</span></span> <span data-ttu-id="82dac-123">Die [. Operator](../../../csharp/language-reference/operators/member-access-operator.md) wird verwendet, um zu unterscheiden, welche Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="82dac-123">The [. Operator](../../../csharp/language-reference/operators/member-access-operator.md) is used to differentiate which method gets called.</span></span>  
  
 <span data-ttu-id="82dac-124">[!code-cs[CsProgGuideNamespaces#8](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="82dac-124">[!code-cs[csProgGuideNamespaces#8](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_5.cs)]</span></span>  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="82dac-125">Vollqualifizierte Namen</span><span class="sxs-lookup"><span data-stu-id="82dac-125">Fully Qualified Names</span></span>  
 <span data-ttu-id="82dac-126">Namespaces und Typen verfügen über eindeutige durch den vollqualifizierten Namen, die eine logische Hierarchie an.</span><span class="sxs-lookup"><span data-stu-id="82dac-126">Namespaces and types have unique titles described by fully qualified names that indicate a logical hierarchy.</span></span> <span data-ttu-id="82dac-127">Beispielsweise impliziert die Anweisung `A.B`, dass `A` der Name des Namespaces oder des Typs ist und, dass `B` darin geschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="82dac-127">For example, the statement `A.B` implies that `A` is the name of the namespace or type, and `B` is nested inside it.</span></span>  
  
 <span data-ttu-id="82dac-128">Im folgenden Beispiel gibt es geschachtelte Klassen und Namespaces.</span><span class="sxs-lookup"><span data-stu-id="82dac-128">In the following example, there are nested classes and namespaces.</span></span> <span data-ttu-id="82dac-129">Der vollqualifizierte Name ist als Kommentar angegeben, der auf jede Entität folgt.</span><span class="sxs-lookup"><span data-stu-id="82dac-129">The fully qualified name is indicated as a comment following each entity.</span></span>  
  
 <span data-ttu-id="82dac-130">[!code-cs[CsProgGuideNamespaces#9](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="82dac-130">[!code-cs[csProgGuideNamespaces#9](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_6.cs)]</span></span>  
  
 <span data-ttu-id="82dac-131">Das vorherige Codesegment weist Folgendes auf:</span><span class="sxs-lookup"><span data-stu-id="82dac-131">In the previous code segment:</span></span>  
  
-   <span data-ttu-id="82dac-132">Der Namespace `N1` ist ein Mitglied des globalen Namespaces.</span><span class="sxs-lookup"><span data-stu-id="82dac-132">The namespace `N1` is a member of the global namespace.</span></span> <span data-ttu-id="82dac-133">Sein vollqualifizierter Name lautet `N1`.</span><span class="sxs-lookup"><span data-stu-id="82dac-133">Its fully qualified name is `N1`.</span></span>  
  
-   <span data-ttu-id="82dac-134">Der Namespace `N2` ist ein Mitglied von `N1`.</span><span class="sxs-lookup"><span data-stu-id="82dac-134">The namespace `N2` is a member of `N1`.</span></span> <span data-ttu-id="82dac-135">Sein vollqualifizierter Name lautet `N1.N2`.</span><span class="sxs-lookup"><span data-stu-id="82dac-135">Its fully qualified name is `N1.N2`.</span></span>  
  
-   <span data-ttu-id="82dac-136">Die Klasse `C1` ist ein Mitglied von `N1`.</span><span class="sxs-lookup"><span data-stu-id="82dac-136">The class `C1` is a member of `N1`.</span></span> <span data-ttu-id="82dac-137">Sein vollqualifizierter Name lautet `N1.C1`.</span><span class="sxs-lookup"><span data-stu-id="82dac-137">Its fully qualified name is `N1.C1`.</span></span>  
  
-   <span data-ttu-id="82dac-138">Der Klassenname `C2` wird zweimal in diesem Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="82dac-138">The class name `C2` is used two times in this code.</span></span> <span data-ttu-id="82dac-139">Die vollqualifizierten Namen sind jedoch eindeutig.</span><span class="sxs-lookup"><span data-stu-id="82dac-139">However, the fully qualified names are unique.</span></span> <span data-ttu-id="82dac-140">Die erste Instanz von `C2` wird in `C1` deklariert; daher lautet der vollqualifizierte Name: `N1.C1.C2`.</span><span class="sxs-lookup"><span data-stu-id="82dac-140">The first instance of `C2` is declared inside `C1`; therefore, its fully qualified name is: `N1.C1.C2`.</span></span> <span data-ttu-id="82dac-141">Die zweite Instanz von `C2` wird in einem Namespace `N2` deklariert; daher lautet der vollqualifizierte Name: `N1.N2.C2`.</span><span class="sxs-lookup"><span data-stu-id="82dac-141">The second instance of `C2` is declared inside a namespace `N2`; therefore, its fully qualified name is `N1.N2.C2`.</span></span>  
  
 <span data-ttu-id="82dac-142">Mithilfe des vorhergehenden Codesegments können Sie dem Namespace `N1.N2` ein neues Klassenmitglied `C3` wie folgt hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="82dac-142">Using the previous code segment, you can add a new class member, `C3`, to the namespace `N1.N2` as follows:</span></span>  
  
 <span data-ttu-id="82dac-143">[!code-cs[CsProgGuideNamespaces#10](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="82dac-143">[!code-cs[csProgGuideNamespaces#10](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_7.cs)]</span></span>  
  
 <span data-ttu-id="82dac-144">Im Allgemeinen verwenden Sie `::`, um auf einen Namespacealias, oder `global::`, um auf den globalen Namespace zu verweisen, und `.`, um Typen oder Mitglieder zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="82dac-144">In general, use `::` to reference a namespace alias or `global::` to reference the global namespace and `.` to qualify types or members.</span></span>  
  
 <span data-ttu-id="82dac-145">Die Verwendung von `::` mit einem Alias, der auf einen Typ statt auf einen Namespace verweist ist ein Fehler.</span><span class="sxs-lookup"><span data-stu-id="82dac-145">It is an error to use `::` with an alias that references a type instead of a namespace.</span></span> <span data-ttu-id="82dac-146">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="82dac-146">For example:</span></span>  
  
 <span data-ttu-id="82dac-147">[!code-cs[CsProgGuideNamespaces#11](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="82dac-147">[!code-cs[csProgGuideNamespaces#11](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_8.cs)]</span></span>  
  
 <span data-ttu-id="82dac-148">[!code-cs[CsProgGuideNamespaces#12](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="82dac-148">[!code-cs[csProgGuideNamespaces#12](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_9.cs)]</span></span>  
  
 <span data-ttu-id="82dac-149">Beachten Sie, dass das Wort `global` kein vorderfinierter Alias ist; deshalb hat `global.X` keine spezielle Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="82dac-149">Remember that the word `global` is not a predefined alias; therefore, `global.X` does not have any special meaning.</span></span> <span data-ttu-id="82dac-150">Er erhält erst dann eine besondere Bedeutung, wenn er mit `::` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="82dac-150">It acquires a special meaning only when it is used with `::`.</span></span>  
  
 <span data-ttu-id="82dac-151">Compilerwarnung CS0440 wird generiert, wenn Sie einen Alias mit dem Namen global definieren, da `global::` immer ein Verweis auf den globalen Namespace und nicht auf einen Alias ist.</span><span class="sxs-lookup"><span data-stu-id="82dac-151">Compiler warning CS0440 is generated if you define an alias named global because `global::` always references the global namespace and not an alias.</span></span> <span data-ttu-id="82dac-152">Beispielsweise generiert die folgende Zeile die folgende Warnung:</span><span class="sxs-lookup"><span data-stu-id="82dac-152">For example, the following line generates the warning:</span></span>  
  
 <span data-ttu-id="82dac-153">[!code-cs[CsProgGuideNamespaces#13](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="82dac-153">[!code-cs[csProgGuideNamespaces#13](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_10.cs)]</span></span>  
  
 <span data-ttu-id="82dac-154">Die Verwendung von `::` mit Aliasen ist ratsam, und verhindert die unbeabsichtigte Einführung von zusätzlichen Typen.</span><span class="sxs-lookup"><span data-stu-id="82dac-154">Using `::` with aliases is a good idea and protects against the unexpected introduction of additional types.</span></span> <span data-ttu-id="82dac-155">Betrachten Sie beispielsweise das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="82dac-155">For example, consider this example:</span></span>  
  
 <span data-ttu-id="82dac-156">[!code-cs[CsProgGuideNamespaces#14](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_11.cs)]</span><span class="sxs-lookup"><span data-stu-id="82dac-156">[!code-cs[csProgGuideNamespaces#14](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_11.cs)]</span></span>  
  
 <span data-ttu-id="82dac-157">[!code-cs[CsProgGuideNamespaces#15](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_12.cs)]</span><span class="sxs-lookup"><span data-stu-id="82dac-157">[!code-cs[csProgGuideNamespaces#15](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_12.cs)]</span></span>  
  
 <span data-ttu-id="82dac-158">Dies funktioniert, aber wenn anschließend ein Typ mit dem Namen `Alias` eingeführt werden würde, würde `Alias.` an diesen Typ gebunden.</span><span class="sxs-lookup"><span data-stu-id="82dac-158">This works, but if a type named `Alias` were to subsequently be introduced, `Alias.` would bind to that type instead.</span></span> <span data-ttu-id="82dac-159">Mit `Alias::Exception` wird sichergestellt, dass `Alias` als ein Namespacealias behandelt und nicht für einen Typ gehalten wird.</span><span class="sxs-lookup"><span data-stu-id="82dac-159">Using `Alias::Exception` insures that `Alias` is treated as a namespace alias and not mistaken for a type.</span></span>  
  
 <span data-ttu-id="82dac-160">Finden Sie im Thema [Vorgehensweise: Verwenden des globalen Namespacealias](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md) Informationen zum `global` Alias.</span><span class="sxs-lookup"><span data-stu-id="82dac-160">See the topic [How to: Use the Global Namespace Alias](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md) for more information regarding the `global` alias.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82dac-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82dac-161">See Also</span></span>  
 <span data-ttu-id="82dac-162">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="82dac-162">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="82dac-163">[Namespaces](../../../csharp/programming-guide/namespaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="82dac-163">[Namespaces](../../../csharp/programming-guide/namespaces/index.md) </span></span>  
 <span data-ttu-id="82dac-164">[Namespace Keywords (Schlüsselwörter des Namespace)](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="82dac-164">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
 <span data-ttu-id="82dac-165">[. Operator](../../../csharp/language-reference/operators/member-access-operator.md) </span><span class="sxs-lookup"><span data-stu-id="82dac-165">[. Operator](../../../csharp/language-reference/operators/member-access-operator.md) </span></span>  
 <span data-ttu-id="82dac-166">[Operator ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span><span class="sxs-lookup"><span data-stu-id="82dac-166">[:: Operator](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span></span>  
 [<span data-ttu-id="82dac-167">extern</span><span class="sxs-lookup"><span data-stu-id="82dac-167">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)

