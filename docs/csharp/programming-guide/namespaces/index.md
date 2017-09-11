---
title: Namespaces (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
caps.latest.revision: 27
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
ms.openlocfilehash: a45339a4c3320a92c0339b1cad6345a2555ed920
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="2c310-102">Namespaces (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="2c310-102">Namespaces (C# Programming Guide)</span></span>
<span data-ttu-id="2c310-103">Namespaces werden beim Programmieren mit C# häufig und auf zwei verschiedene Arten verwendet.</span><span class="sxs-lookup"><span data-stu-id="2c310-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="2c310-104">Erstens: Das .NET Framework verwendet Namespaces, um seine vielen Klassen folgendermaßen zu organisieren:</span><span class="sxs-lookup"><span data-stu-id="2c310-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
 <span data-ttu-id="2c310-105">[!code-cs[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2c310-105">[!code-cs[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]</span></span>  
  
 <span data-ttu-id="2c310-106">`System` ist ein Namespace, und `Console` ist eine Klasse in diesem Namespace.</span><span class="sxs-lookup"><span data-stu-id="2c310-106">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="2c310-107">Das `using`-Schlüsselwort kann verwendet werden, sodass der vollständige Name nicht erforderlich ist, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2c310-107">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
 <span data-ttu-id="2c310-108">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="2c310-108">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]</span></span>  
  
 <span data-ttu-id="2c310-109">[!code-cs[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="2c310-109">[!code-cs[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]</span></span>  
  
 <span data-ttu-id="2c310-110">Weitere Information finden Sie unter [using-Direktive](../../../csharp/language-reference/keywords/using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="2c310-110">For more information, see [using Directive](../../../csharp/language-reference/keywords/using-directive.md).</span></span>  
  
 <span data-ttu-id="2c310-111">Zweitens: Eigene Namespaces zu deklarieren kann Ihnen dabei helfen, den Umfang der Klassen- und Methodennamen in größeren Programmierprojekten zu steuern.</span><span class="sxs-lookup"><span data-stu-id="2c310-111">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="2c310-112">Verwenden Sie das [Namespace](../../../csharp/language-reference/keywords/namespace.md)-Schlüsselwort, um einen Namespace wie im folgenden Beispiel zu deklarieren:</span><span class="sxs-lookup"><span data-stu-id="2c310-112">Use the [namespace](../../../csharp/language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
 <span data-ttu-id="2c310-113">[!code-cs[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="2c310-113">[!code-cs[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]</span></span>  
  
## <a name="namespaces-overview"></a><span data-ttu-id="2c310-114">Übersicht über Namespaces</span><span class="sxs-lookup"><span data-stu-id="2c310-114">Namespaces Overview</span></span>  
 <span data-ttu-id="2c310-115">Namespaces verfügen über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="2c310-115">Namespaces have the following properties:</span></span>  
  
-   <span data-ttu-id="2c310-116">Sie organisieren umfangreiche Codeprojekte.</span><span class="sxs-lookup"><span data-stu-id="2c310-116">They organize large code projects.</span></span>  
  
-   <span data-ttu-id="2c310-117">Sie werden durch den `.`-Operator getrennt.</span><span class="sxs-lookup"><span data-stu-id="2c310-117">They are delimited by using the `.` operator.</span></span>  
  
-   <span data-ttu-id="2c310-118">Durch `using directive` besteht keine Notwendigkeit, den Namen des Namespace für jede Klasse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2c310-118">The `using directive` obviates the requirement to specify the name of the namespace for every class.</span></span>  
  
-   <span data-ttu-id="2c310-119">Der `global`-Namespace ist der Stammnamespace: `global::System` verweist immer auf den `System`-Namespace des .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2c310-119">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET Framework namespace `System`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2c310-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="2c310-120">Related Sections</span></span>  
 <span data-ttu-id="2c310-121">Weitere Informationen zu Namespaces finden Sie unter folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="2c310-121">See the following topics for more information about namespaces:</span></span>  
  
-   [<span data-ttu-id="2c310-122">Using-Namespaces</span><span class="sxs-lookup"><span data-stu-id="2c310-122">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="2c310-123">Gewusst wie: Verwenden des globalen Namespacealias</span><span class="sxs-lookup"><span data-stu-id="2c310-123">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [<span data-ttu-id="2c310-124">Gewusst wie: Verwenden des My-Namespaces</span><span class="sxs-lookup"><span data-stu-id="2c310-124">How to: Use the My Namespace</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="2c310-125">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="2c310-125">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2c310-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c310-126">See Also</span></span>  
 <span data-ttu-id="2c310-127">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2c310-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2c310-128">[Namespace Keywords (Schlüsselwörter des Namespace)](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="2c310-128">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
 <span data-ttu-id="2c310-129">[using-Direktive](../../../csharp/language-reference/keywords/using-directive.md) </span><span class="sxs-lookup"><span data-stu-id="2c310-129">[using Directive](../../../csharp/language-reference/keywords/using-directive.md) </span></span>  
 <span data-ttu-id="2c310-130">[Operator ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span><span class="sxs-lookup"><span data-stu-id="2c310-130">[:: Operator](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span></span>  
 [<span data-ttu-id="2c310-131">. Operator</span><span class="sxs-lookup"><span data-stu-id="2c310-131">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)

