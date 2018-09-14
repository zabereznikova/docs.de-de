---
title: Namespaces (C#-Programmierhandbuch)
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: c4011092a6c605137053b544d4b9f14cce2fdb4c
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45560281"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="b0578-102">Namespaces (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b0578-102">Namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="b0578-103">Namespaces werden beim Programmieren mit C# häufig und auf zwei verschiedene Arten verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0578-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="b0578-104">Erstens: Das .NET Framework verwendet Namespaces, um seine vielen Klassen folgendermaßen zu organisieren:</span><span class="sxs-lookup"><span data-stu-id="b0578-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
[!code-csharp[csProgGuide#22](../inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
<span data-ttu-id="b0578-105">`System` ist ein Namespace, und `Console` ist eine Klasse in diesem Namespace.</span><span class="sxs-lookup"><span data-stu-id="b0578-105">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="b0578-106">Das `using`-Schlüsselwort kann verwendet werden, sodass der vollständige Name nicht erforderlich ist, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b0578-106">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
[!code-csharp[csProgGuide#1](../inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
[!code-csharp[csProgGuide#25](../inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
<span data-ttu-id="b0578-107">Weitere Information finden Sie unter der [using-Anweisung](../../language-reference/keywords/using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="b0578-107">For more information, see the [using Directive](../../language-reference/keywords/using-directive.md).</span></span>  
  
<span data-ttu-id="b0578-108">Zweitens: Eigene Namespaces zu deklarieren kann Ihnen dabei helfen, den Umfang der Klassen- und Methodennamen in größeren Programmierprojekten zu steuern.</span><span class="sxs-lookup"><span data-stu-id="b0578-108">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="b0578-109">Verwenden Sie das [Namespace](../../language-reference/keywords/namespace.md)-Schlüsselwort, um einen Namespace wie im folgenden Beispiel zu deklarieren:</span><span class="sxs-lookup"><span data-stu-id="b0578-109">Use the [namespace](../../language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
[!code-csharp[csProgGuideNamespaces#6](codesnippet/CSharp/index_4.cs)]

<span data-ttu-id="b0578-110">Der Name des Namespace muss ein gültiger C#- [Bezeichnername](../inside-a-program/identifier-names.md) sein.</span><span class="sxs-lookup"><span data-stu-id="b0578-110">The name of the namespace must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span>

## <a name="namespaces-overview"></a><span data-ttu-id="b0578-111">Übersicht über Namespaces</span><span class="sxs-lookup"><span data-stu-id="b0578-111">Namespaces Overview</span></span>  

<span data-ttu-id="b0578-112">Namespaces verfügen über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="b0578-112">Namespaces have the following properties:</span></span>  
  
- <span data-ttu-id="b0578-113">Sie organisieren umfangreiche Codeprojekte.</span><span class="sxs-lookup"><span data-stu-id="b0578-113">They organize large code projects.</span></span>  
- <span data-ttu-id="b0578-114">Sie werden durch den `.`-Operator getrennt.</span><span class="sxs-lookup"><span data-stu-id="b0578-114">They are delimited by using the `.` operator.</span></span>  
- <span data-ttu-id="b0578-115">Durch `using directive` besteht keine Notwendigkeit, den Namen des Namespace für jede Klasse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b0578-115">The `using directive` obviates the requirement to specify the name of the namespace for every class.</span></span>  
- <span data-ttu-id="b0578-116">Der `global`-Namespace ist der Stammnamespace: `global::System` verweist immer auf den `System`-Namespace des .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b0578-116">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET Framework namespace `System`.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="b0578-117">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="b0578-117">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b0578-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0578-118">See Also</span></span>

- [<span data-ttu-id="b0578-119">Using-Namespaces</span><span class="sxs-lookup"><span data-stu-id="b0578-119">Using Namespaces</span></span>](using-namespaces.md)
- [<span data-ttu-id="b0578-120">Gewusst wie: Verwenden des globalen Namespacealias</span><span class="sxs-lookup"><span data-stu-id="b0578-120">How to: Use the Global Namespace Alias</span></span>](how-to-use-the-global-namespace-alias.md)
- [<span data-ttu-id="b0578-121">Gewusst wie: Verwenden des My-Namespaces</span><span class="sxs-lookup"><span data-stu-id="b0578-121">How to: Use the My Namespace</span></span>](how-to-use-the-my-namespace.md)
- [<span data-ttu-id="b0578-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b0578-122">C# Programming Guide</span></span>](../index.md)  
- [<span data-ttu-id="b0578-123">Bezeichnernamen</span><span class="sxs-lookup"><span data-stu-id="b0578-123">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="b0578-124">Namespaceschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b0578-124">Namespace Keywords</span></span>](../../language-reference/keywords/namespace-keywords.md)  
- [<span data-ttu-id="b0578-125">using-Direktive</span><span class="sxs-lookup"><span data-stu-id="b0578-125">using Directive</span></span>](../../language-reference/keywords/using-directive.md)  
- [<span data-ttu-id="b0578-126">::-Operator</span><span class="sxs-lookup"><span data-stu-id="b0578-126">:: Operator</span></span>](../../language-reference/operators/namespace-alias-qualifer.md)  
- [<span data-ttu-id="b0578-127"> Operator</span><span class="sxs-lookup"><span data-stu-id="b0578-127">. Operator</span></span>](../../language-reference/operators/member-access-operator.md)
>>>>>>> <span data-ttu-id="b0578-128">Benennungsregeln für Bezeichner hinzufügen</span><span class="sxs-lookup"><span data-stu-id="b0578-128">add identifier naming rules</span></span>
