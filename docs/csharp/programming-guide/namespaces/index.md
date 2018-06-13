---
title: Namespaces (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 60e4c6e98ca9e71d1a095a0c7ee1df6be6d13f4b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334349"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="63113-102">Namespaces (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="63113-102">Namespaces (C# Programming Guide)</span></span>
<span data-ttu-id="63113-103">Namespaces werden beim Programmieren mit C# häufig und auf zwei verschiedene Arten verwendet.</span><span class="sxs-lookup"><span data-stu-id="63113-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="63113-104">Erstens: Das .NET Framework verwendet Namespaces, um seine vielen Klassen folgendermaßen zu organisieren:</span><span class="sxs-lookup"><span data-stu-id="63113-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
 [!code-csharp[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
 <span data-ttu-id="63113-105">`System` ist ein Namespace, und `Console` ist eine Klasse in diesem Namespace.</span><span class="sxs-lookup"><span data-stu-id="63113-105">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="63113-106">Das `using`-Schlüsselwort kann verwendet werden, sodass der vollständige Name nicht erforderlich ist, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="63113-106">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
 [!code-csharp[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
 <span data-ttu-id="63113-107">Weitere Information finden Sie unter [using-Direktive](../../../csharp/language-reference/keywords/using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="63113-107">For more information, see [using Directive](../../../csharp/language-reference/keywords/using-directive.md).</span></span>  
  
 <span data-ttu-id="63113-108">Zweitens: Eigene Namespaces zu deklarieren kann Ihnen dabei helfen, den Umfang der Klassen- und Methodennamen in größeren Programmierprojekten zu steuern.</span><span class="sxs-lookup"><span data-stu-id="63113-108">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="63113-109">Verwenden Sie das [Namespace](../../../csharp/language-reference/keywords/namespace.md)-Schlüsselwort, um einen Namespace wie im folgenden Beispiel zu deklarieren:</span><span class="sxs-lookup"><span data-stu-id="63113-109">Use the [namespace](../../../csharp/language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]  
  
## <a name="namespaces-overview"></a><span data-ttu-id="63113-110">Übersicht über Namespaces</span><span class="sxs-lookup"><span data-stu-id="63113-110">Namespaces Overview</span></span>  
 <span data-ttu-id="63113-111">Namespaces verfügen über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="63113-111">Namespaces have the following properties:</span></span>  
  
-   <span data-ttu-id="63113-112">Sie organisieren umfangreiche Codeprojekte.</span><span class="sxs-lookup"><span data-stu-id="63113-112">They organize large code projects.</span></span>  
  
-   <span data-ttu-id="63113-113">Sie werden durch den `.`-Operator getrennt.</span><span class="sxs-lookup"><span data-stu-id="63113-113">They are delimited by using the `.` operator.</span></span>  
  
-   <span data-ttu-id="63113-114">Durch `using directive` besteht keine Notwendigkeit, den Namen des Namespace für jede Klasse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="63113-114">The `using directive` obviates the requirement to specify the name of the namespace for every class.</span></span>  
  
-   <span data-ttu-id="63113-115">Der `global`-Namespace ist der Stammnamespace: `global::System` verweist immer auf den `System`-Namespace des .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="63113-115">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET Framework namespace `System`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="63113-116">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="63113-116">Related Sections</span></span>  
 <span data-ttu-id="63113-117">Weitere Informationen zu Namespaces finden Sie unter folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="63113-117">See the following topics for more information about namespaces:</span></span>  
  
-   [<span data-ttu-id="63113-118">Using-Namespaces</span><span class="sxs-lookup"><span data-stu-id="63113-118">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="63113-119">Gewusst wie: Verwenden des globalen Namespacealias</span><span class="sxs-lookup"><span data-stu-id="63113-119">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [<span data-ttu-id="63113-120">Gewusst wie: Verwenden des My-Namespaces</span><span class="sxs-lookup"><span data-stu-id="63113-120">How to: Use the My Namespace</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="63113-121">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="63113-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="63113-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63113-122">See Also</span></span>  
 [<span data-ttu-id="63113-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="63113-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="63113-124">Namespaceschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="63113-124">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="63113-125">using-Direktive</span><span class="sxs-lookup"><span data-stu-id="63113-125">using Directive</span></span>](../../../csharp/language-reference/keywords/using-directive.md)  
 [<span data-ttu-id="63113-126">::-Operator</span><span class="sxs-lookup"><span data-stu-id="63113-126">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
 [<span data-ttu-id="63113-127"> Operator</span><span class="sxs-lookup"><span data-stu-id="63113-127">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)
