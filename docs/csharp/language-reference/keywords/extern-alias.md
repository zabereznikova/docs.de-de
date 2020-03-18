---
title: extern-Alias – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
ms.openlocfilehash: 86202333484933d7449b0c4d8c5a3f1a63cd7775
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713547"
---
# <a name="extern-alias-c-reference"></a><span data-ttu-id="dfa9f-102">extern-Alias (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="dfa9f-102">extern alias (C# Reference)</span></span>
<span data-ttu-id="dfa9f-103">Sie müssen möglicherweise auf zwei Versionen von Assemblys verweisen, die denselben vollqualifizierten Namen besitzen.</span><span class="sxs-lookup"><span data-stu-id="dfa9f-103">You might have to reference two versions of assemblies that have the same fully-qualified type names.</span></span> <span data-ttu-id="dfa9f-104">Beispielsweise müssen Sie möglicherweise zwei oder mehr Versionen einer Assembly in derselben Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="dfa9f-104">For example, you might have to use two or more versions of an assembly in the same application.</span></span> <span data-ttu-id="dfa9f-105">Indem Sie einen externen Assemblyalias verwenden, können die Namespaces jeder Assembly in Namespaces auf Stammebene, benannt durch den Alias, umschlossen werden, was es ihnen ermöglicht, von derselben Datei verwendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="dfa9f-105">By using an external assembly alias, the namespaces from each assembly can be wrapped inside root-level namespaces named by the alias, which enables them to be used in the same file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dfa9f-106">Das [extern](./extern.md)-Schlüsselwort dient außerdem als Methodenmodifizierer, der eine Methode deklariert, die in nicht verwaltetem Code geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="dfa9f-106">The [extern](./extern.md) keyword is also used as a method modifier, declaring a method written in unmanaged code.</span></span>  
  
 <span data-ttu-id="dfa9f-107">Um auf zwei Assemblys mit demselben vollqualifizierten Typnamen zu verweisen, muss ein Alias in einer Befehlszeile wie folgt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="dfa9f-107">To reference two assemblies with the same fully-qualified type names, an alias must be specified at a command prompt, as follows:</span></span>  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 <span data-ttu-id="dfa9f-108">Dies erstellt die externen Aliase `GridV1` und `GridV2`.</span><span class="sxs-lookup"><span data-stu-id="dfa9f-108">This creates the external aliases `GridV1` and `GridV2`.</span></span> <span data-ttu-id="dfa9f-109">Um diese Aliase aus einem Programm heraus zu verwenden, verweisen Sie mithilfe des `extern`-Schlüsselworts auf sie.</span><span class="sxs-lookup"><span data-stu-id="dfa9f-109">To use these aliases from within a program, reference them by using the `extern` keyword.</span></span> <span data-ttu-id="dfa9f-110">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="dfa9f-110">For example:</span></span>  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 <span data-ttu-id="dfa9f-111">Jede externe Aliasdeklaration führt einen zusätzlichen Namespace auf Stammebene ein, parallel zum (aber nicht innerhalb des) globalen Namespace.</span><span class="sxs-lookup"><span data-stu-id="dfa9f-111">Each extern alias declaration introduces an additional root-level namespace that parallels (but does not lie within) the global namespace.</span></span> <span data-ttu-id="dfa9f-112">Daher kann mithilfe des vollqualifizierten Namens, der als Stamm des entsprechenden Namespacealias dient, auf Typen jeder Assembly eindeutig verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="dfa9f-112">Thus types from each assembly can be referred to without ambiguity by using their fully qualified name, rooted in the appropriate namespace-alias.</span></span>  
  
 <span data-ttu-id="dfa9f-113">Im vorherigen Beispiel wäre `GridV1::Grid` das Steuerelement von `grid.dll`, und `GridV2::Grid` wäre das Steuerelement von `grid20.dll`.</span><span class="sxs-lookup"><span data-stu-id="dfa9f-113">In the previous example, `GridV1::Grid` would be the grid control from `grid.dll`, and `GridV2::Grid` would be the grid control from `grid20.dll`.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="dfa9f-114">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="dfa9f-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dfa9f-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dfa9f-115">See also</span></span>

- [<span data-ttu-id="dfa9f-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="dfa9f-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="dfa9f-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="dfa9f-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="dfa9f-118">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="dfa9f-118">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="dfa9f-119">::-Operator</span><span class="sxs-lookup"><span data-stu-id="dfa9f-119">:: Operator</span></span>](../operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="dfa9f-120">-reference (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="dfa9f-120">-reference (C# Compiler Options)</span></span>](../compiler-options/reference-compiler-option.md)
