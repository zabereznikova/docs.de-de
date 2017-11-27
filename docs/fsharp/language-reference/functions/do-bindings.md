---
title: do-Bindungen (F#)
description: "Darüber informieren Sie, wie ein F#-\"Bindung\" do\"wird zum Ausführen von Code ohne die Definition einer Funktion oder Wert."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4c1057a3-3aa1-4b64-b46a-25ffe33f0be9
ms.openlocfilehash: f2563d384b67c005c96c2ff487c786476d385e70
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="do-bindings"></a><span data-ttu-id="2d949-104">do-Bindungen</span><span class="sxs-lookup"><span data-stu-id="2d949-104">do Bindings</span></span>

<span data-ttu-id="2d949-105">Ein `do` Bindung verwendet, um Code auszuführen, ohne die Definition einer Funktion oder Wert.</span><span class="sxs-lookup"><span data-stu-id="2d949-105">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="2d949-106">Darüber hinaus werden Bindungen können werden in Klassen verwendet werden, finden Sie unter [ `do` Bindungen in Klassen](../members/do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="2d949-106">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>


## <a name="syntax"></a><span data-ttu-id="2d949-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d949-107">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="2d949-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2d949-108">Remarks</span></span>
<span data-ttu-id="2d949-109">Verwenden einer `do` binden, wenn der Code unabhängig von der Definition einer Funktion oder Wert ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2d949-109">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="2d949-110">Der Ausdruck in einem `do` Bindung muss zurückgeben `unit`.</span><span class="sxs-lookup"><span data-stu-id="2d949-110">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="2d949-111">Code in einem der obersten Ebene `do` Bindung wird ausgeführt, wenn das Modul initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="2d949-111">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="2d949-112">Das Schlüsselwort `do` ist optional.</span><span class="sxs-lookup"><span data-stu-id="2d949-112">The keyword `do` is optional.</span></span>

<span data-ttu-id="2d949-113">Attribute können auf einem der obersten Ebene angewendet werden `do` Bindung.</span><span class="sxs-lookup"><span data-stu-id="2d949-113">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="2d949-114">Z. B. Wenn Ihr Programm COM-Interop verwendet, Sie möchten gelten die `STAThread` -Attribut auf das Programm.</span><span class="sxs-lookup"><span data-stu-id="2d949-114">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="2d949-115">Sie erreichen dies, indem Sie ein Attribut auf eine `do` binden, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="2d949-115">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]
    
## <a name="see-also"></a><span data-ttu-id="2d949-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d949-116">See Also</span></span>
[<span data-ttu-id="2d949-117">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="2d949-117">F# Language Reference</span></span>](../index.md)

[<span data-ttu-id="2d949-118">Funktionen</span><span class="sxs-lookup"><span data-stu-id="2d949-118">Functions</span></span>](index.md)

