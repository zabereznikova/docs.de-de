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
ms.openlocfilehash: 891e56b064f8a327abe28293223a85b9d95e8fd3
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301813"
---
# <a name="extern-alias-c-reference"></a><span data-ttu-id="ac37f-102">extern-Alias (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ac37f-102">extern alias (C# Reference)</span></span>
<span data-ttu-id="ac37f-103">Sie müssen möglicherweise auf zwei Versionen von Assemblys verweisen, die denselben vollqualifizierten Namen besitzen.</span><span class="sxs-lookup"><span data-stu-id="ac37f-103">You might have to reference two versions of assemblies that have the same fully-qualified type names.</span></span> <span data-ttu-id="ac37f-104">Beispielsweise müssen Sie möglicherweise zwei oder mehr Versionen einer Assembly in derselben Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="ac37f-104">For example, you might have to use two or more versions of an assembly in the same application.</span></span> <span data-ttu-id="ac37f-105">Indem Sie einen externen Assemblyalias verwenden, können die Namespaces jeder Assembly in Namespaces auf Stammebene, benannt durch den Alias, umschlossen werden, was es ihnen ermöglicht, von derselben Datei verwendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="ac37f-105">By using an external assembly alias, the namespaces from each assembly can be wrapped inside root-level namespaces named by the alias, which enables them to be used in the same file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ac37f-106">Das [extern](./extern.md)-Schlüsselwort dient außerdem als Methodenmodifizierer, der eine Methode deklariert, die in nicht verwaltetem Code geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="ac37f-106">The [extern](./extern.md) keyword is also used as a method modifier, declaring a method written in unmanaged code.</span></span>  
  
 <span data-ttu-id="ac37f-107">Um auf zwei Assemblys mit demselben vollqualifizierten Typnamen zu verweisen, muss ein Alias in einer Befehlszeile wie folgt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="ac37f-107">To reference two assemblies with the same fully-qualified type names, an alias must be specified at a command prompt, as follows:</span></span>  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 <span data-ttu-id="ac37f-108">Dies erstellt die externen Aliase `GridV1` und `GridV2`.</span><span class="sxs-lookup"><span data-stu-id="ac37f-108">This creates the external aliases `GridV1` and `GridV2`.</span></span> <span data-ttu-id="ac37f-109">Um diese Aliase aus einem Programm heraus zu verwenden, verweisen Sie mithilfe des `extern`-Schlüsselworts auf sie.</span><span class="sxs-lookup"><span data-stu-id="ac37f-109">To use these aliases from within a program, reference them by using the `extern` keyword.</span></span> <span data-ttu-id="ac37f-110">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ac37f-110">For example:</span></span>  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 <span data-ttu-id="ac37f-111">Jede externe Aliasdeklaration führt einen zusätzlichen Namespace auf Stammebene ein, parallel zum (aber nicht innerhalb des) globalen Namespace.</span><span class="sxs-lookup"><span data-stu-id="ac37f-111">Each extern alias declaration introduces an additional root-level namespace that parallels (but does not lie within) the global namespace.</span></span> <span data-ttu-id="ac37f-112">Daher kann mithilfe des vollqualifizierten Namens, der als Stamm des entsprechenden Namespacealias dient, auf Typen jeder Assembly eindeutig verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="ac37f-112">Thus types from each assembly can be referred to without ambiguity by using their fully qualified name, rooted in the appropriate namespace-alias.</span></span>  
  
 <span data-ttu-id="ac37f-113">Im vorherigen Beispiel wäre `GridV1::Grid` das Steuerelement von `grid.dll`, und `GridV2::Grid` wäre das Steuerelement von `grid20.dll`.</span><span class="sxs-lookup"><span data-stu-id="ac37f-113">In the previous example, `GridV1::Grid` would be the grid control from `grid.dll`, and `GridV2::Grid` would be the grid control from `grid20.dll`.</span></span>  
  
## <a name="using-visual-studio"></a><span data-ttu-id="ac37f-114">Verwenden von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ac37f-114">Using Visual Studio</span></span>

<span data-ttu-id="ac37f-115">Wenn Sie Visual Studio verwenden, können Aliase auf ähnliche Weise bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ac37f-115">If you are using Visual Studio, aliases can be provided in similar way.</span></span>

<span data-ttu-id="ac37f-116">Fügen Sie Ihrem Projekt in Visual Studio Verweise auf *grid.dll* und *grid20.dll* hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac37f-116">Add reference of *grid.dll* and *grid20.dll* to your project in Visual Studio.</span></span> <span data-ttu-id="ac37f-117">Öffnen Sie eine Registerkarte mit Eigenschaften, und ändern Sie die Aliase von „global“ in „GridV1“ bzw. „GridV2“.</span><span class="sxs-lookup"><span data-stu-id="ac37f-117">Open a property tab and change the Aliases from global to GridV1 and GridV2 respectively.</span></span>

<span data-ttu-id="ac37f-118">Verwenden Sie diese Aliase auf die gleiche Weise wie oben:</span><span class="sxs-lookup"><span data-stu-id="ac37f-118">Use these aliases the same way above</span></span>

```csharp
 extern alias GridV1;  
  
 extern alias GridV2;  
```

<span data-ttu-id="ac37f-119">Jetzt können Sie einen Alias für einen Namespace oder Typ erstellen, indem Sie eine *using-alias-Anweisung* verwenden.</span><span class="sxs-lookup"><span data-stu-id="ac37f-119">Now you can create alias for a namespace or a type by *using alias directive*.</span></span> <span data-ttu-id="ac37f-120">Weitere Information finden Sie unter [using-Anweisung](using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="ac37f-120">For more information, see [using directive](using-directive.md).</span></span>

```csharp
using Class1V1 = GridV1::Namespace.Class1;

using Class1V2 = GridV2::Namespace.Class1;
```

## <a name="c-language-specification"></a><span data-ttu-id="ac37f-121">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="ac37f-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ac37f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac37f-122">See also</span></span>

- [<span data-ttu-id="ac37f-123">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ac37f-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ac37f-124">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ac37f-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ac37f-125">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ac37f-125">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="ac37f-126">:: Operator</span><span class="sxs-lookup"><span data-stu-id="ac37f-126">:: Operator</span></span>](../operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="ac37f-127">-reference (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="ac37f-127">-reference (C# Compiler Options)</span></span>](../compiler-options/reference-compiler-option.md)
