---
title: Namespaces – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 8a03baffc17da07ccab14c89dc9f99be2fc5ba1a
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635209"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="cb865-102">Namespaces (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="cb865-102">Namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="cb865-103">Namespaces werden beim Programmieren mit C# häufig und auf zwei verschiedene Arten verwendet.</span><span class="sxs-lookup"><span data-stu-id="cb865-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="cb865-104">Erstens: Das .NET Framework verwendet Namespaces, um seine vielen Klassen folgendermaßen zu organisieren:</span><span class="sxs-lookup"><span data-stu-id="cb865-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
 [!code-csharp[csProgGuide#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#22)]  
  
<span data-ttu-id="cb865-105">`System` ist ein Namespace, und `Console` ist eine Klasse in diesem Namespace.</span><span class="sxs-lookup"><span data-stu-id="cb865-105">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="cb865-106">Das `using`-Schlüsselwort kann verwendet werden, sodass der vollständige Name nicht erforderlich ist, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cb865-106">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuide#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#25)]  
  
<span data-ttu-id="cb865-107">Weitere Information finden Sie unter der [using-Anweisung](../../language-reference/keywords/using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="cb865-107">For more information, see the [using Directive](../../language-reference/keywords/using-directive.md).</span></span>  
  
<span data-ttu-id="cb865-108">Zweitens: Eigene Namespaces zu deklarieren kann Ihnen dabei helfen, den Umfang der Klassen- und Methodennamen in größeren Programmierprojekten zu steuern.</span><span class="sxs-lookup"><span data-stu-id="cb865-108">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="cb865-109">Verwenden Sie das [Namespace](../../language-reference/keywords/namespace.md)-Schlüsselwort, um einen Namespace wie im folgenden Beispiel zu deklarieren:</span><span class="sxs-lookup"><span data-stu-id="cb865-109">Use the [namespace](../../language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#6)]

<span data-ttu-id="cb865-110">Der Name des Namespace muss ein gültiger C#- [Bezeichnername](../inside-a-program/identifier-names.md) sein.</span><span class="sxs-lookup"><span data-stu-id="cb865-110">The name of the namespace must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span>

## <a name="namespaces-overview"></a><span data-ttu-id="cb865-111">Übersicht über Namespaces</span><span class="sxs-lookup"><span data-stu-id="cb865-111">Namespaces Overview</span></span>  

<span data-ttu-id="cb865-112">Namespaces verfügen über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="cb865-112">Namespaces have the following properties:</span></span>  
  
- <span data-ttu-id="cb865-113">Sie organisieren umfangreiche Codeprojekte.</span><span class="sxs-lookup"><span data-stu-id="cb865-113">They organize large code projects.</span></span>  
- <span data-ttu-id="cb865-114">Sie werden durch den `.`-Operator getrennt.</span><span class="sxs-lookup"><span data-stu-id="cb865-114">They are delimited by using the `.` operator.</span></span>  
- <span data-ttu-id="cb865-115">Durch die `using`-Direktive besteht keine Notwendigkeit, den Namen des Namespace für jede Klasse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="cb865-115">The `using` directive obviates the requirement to specify the name of the namespace for every class.</span></span>  
- <span data-ttu-id="cb865-116">Der `global`-Namespace ist der Stammnamespace: `global::System` verweist immer auf den .NET-Namespace <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="cb865-116">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET <xref:System> namespace.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="cb865-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="cb865-117">C# language specification</span></span>

<span data-ttu-id="cb865-118">Weitere Informationen finden Sie im Abschnitt [Namespaces](~/_csharplang/spec/namespaces.md) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="cb865-118">For more information, see the [Namespaces](~/_csharplang/spec/namespaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cb865-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb865-119">See also</span></span>

- [<span data-ttu-id="cb865-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="cb865-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="cb865-121">Using-Namespaces</span><span class="sxs-lookup"><span data-stu-id="cb865-121">Using Namespaces</span></span>](using-namespaces.md)
- [<span data-ttu-id="cb865-122">Verwenden des My-Namespaces</span><span class="sxs-lookup"><span data-stu-id="cb865-122">How to use the My namespace</span></span>](how-to-use-the-my-namespace.md)
- [<span data-ttu-id="cb865-123">Bezeichnernamen</span><span class="sxs-lookup"><span data-stu-id="cb865-123">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="cb865-124">using-Direktive</span><span class="sxs-lookup"><span data-stu-id="cb865-124">using Directive</span></span>](../../language-reference/keywords/using-directive.md)
- [<span data-ttu-id="cb865-125">:: Operator</span><span class="sxs-lookup"><span data-stu-id="cb865-125">:: Operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
