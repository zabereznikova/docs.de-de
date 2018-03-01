---
title: extern-Alias (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4e995586c08659853538726a12679770cd1ada37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="extern-alias-c-reference"></a><span data-ttu-id="3161d-102">extern-Alias (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3161d-102">extern alias (C# Reference)</span></span>
<span data-ttu-id="3161d-103">Sie müssen möglicherweise auf zwei Versionen von Assemblys verweisen, die denselben vollqualifizierten Namen besitzen.</span><span class="sxs-lookup"><span data-stu-id="3161d-103">You might have to reference two versions of assemblies that have the same fully-qualified type names.</span></span> <span data-ttu-id="3161d-104">Beispielsweise müssen Sie möglicherweise zwei oder mehr Versionen einer Assembly in derselben Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="3161d-104">For example, you might have to use two or more versions of an assembly in the same application.</span></span> <span data-ttu-id="3161d-105">Indem Sie einen externen Assemblyalias verwenden, können die Namespaces jeder Assembly in Namespaces auf Stammebene, benannt durch den Alias, umschlossen werden, was es ihnen ermöglicht, von derselben Datei verwendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="3161d-105">By using an external assembly alias, the namespaces from each assembly can be wrapped inside root-level namespaces named by the alias, which enables them to be used in the same file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3161d-106">Das [extern](../../../csharp/language-reference/keywords/extern.md)-Schlüsselwort dient außerdem als Methodenmodifizierer, der eine Methode deklariert, die in nicht verwaltetem Code geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="3161d-106">The [extern](../../../csharp/language-reference/keywords/extern.md) keyword is also used as a method modifier, declaring a method written in unmanaged code.</span></span>  
  
 <span data-ttu-id="3161d-107">Um auf zwei Assemblys mit demselben vollqualifizierten Typnamen zu verweisen, muss ein Alias in einer Befehlszeile wie folgt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="3161d-107">To reference two assemblies with the same fully-qualified type names, an alias must be specified at a command prompt, as follows:</span></span>  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 <span data-ttu-id="3161d-108">Dies erstellt die externen Aliase `GridV1` und `GridV2`.</span><span class="sxs-lookup"><span data-stu-id="3161d-108">This creates the external aliases `GridV1` and `GridV2`.</span></span> <span data-ttu-id="3161d-109">Um diese Aliase aus einem Programm heraus zu verwenden, verweisen Sie mithilfe des `extern`-Schlüsselworts auf sie.</span><span class="sxs-lookup"><span data-stu-id="3161d-109">To use these aliases from within a program, reference them by using the `extern` keyword.</span></span> <span data-ttu-id="3161d-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3161d-110">For example:</span></span>  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 <span data-ttu-id="3161d-111">Jede externe Aliasdeklaration führt einen zusätzlichen Namespace auf Stammebene ein, parallel zum (aber nicht innerhalb des) globalen Namespace.</span><span class="sxs-lookup"><span data-stu-id="3161d-111">Each extern alias declaration introduces an additional root-level namespace that parallels (but does not lie within) the global namespace.</span></span> <span data-ttu-id="3161d-112">Daher kann mithilfe des vollqualifizierten Namens, der als Stamm des entsprechenden Namespacealias dient, auf Typen jeder Assembly eindeutig verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="3161d-112">Thus types from each assembly can be referred to without ambiguity by using their fully qualified name, rooted in the appropriate namespace-alias.</span></span>  
  
 <span data-ttu-id="3161d-113">Im vorherigen Beispiel wäre `GridV1::Grid` das Steuerelement von `grid.dll`, und `GridV2::Grid` wäre das Steuerelement von `grid20.dll`.</span><span class="sxs-lookup"><span data-stu-id="3161d-113">In the previous example, `GridV1::Grid` would be the grid control from `grid.dll`, and `GridV2::Grid` would be the grid control from `grid20.dll`.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="3161d-114">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="3161d-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3161d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3161d-115">See Also</span></span>  
 [<span data-ttu-id="3161d-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="3161d-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="3161d-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3161d-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3161d-118">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="3161d-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="3161d-119">Namespaceschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="3161d-119">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="3161d-120">::-Operator</span><span class="sxs-lookup"><span data-stu-id="3161d-120">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
 [<span data-ttu-id="3161d-121">/reference (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="3161d-121">/reference (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)
