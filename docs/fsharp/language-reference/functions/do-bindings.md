---
title: do-Bindungen (F#)
description: Darüber informieren Sie, wie ein F#-"Bindung" do"wird zum Ausführen von Code ohne die Definition einer Funktion oder Wert.
ms.date: 05/16/2016
ms.openlocfilehash: 6fd084090a204beab0da1c2deb5b5ae2a86281c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562335"
---
# <a name="do-bindings"></a><span data-ttu-id="c7e08-103">do-Bindungen</span><span class="sxs-lookup"><span data-stu-id="c7e08-103">do Bindings</span></span>

<span data-ttu-id="c7e08-104">Ein `do` Bindung verwendet, um Code auszuführen, ohne die Definition einer Funktion oder Wert.</span><span class="sxs-lookup"><span data-stu-id="c7e08-104">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="c7e08-105">Darüber hinaus werden Bindungen können werden in Klassen verwendet werden, finden Sie unter [ `do` Bindungen in Klassen](../members/do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="c7e08-105">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>


## <a name="syntax"></a><span data-ttu-id="c7e08-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7e08-106">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="c7e08-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c7e08-107">Remarks</span></span>
<span data-ttu-id="c7e08-108">Verwenden einer `do` binden, wenn der Code unabhängig von der Definition einer Funktion oder Wert ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7e08-108">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="c7e08-109">Der Ausdruck in einem `do` Bindung muss zurückgeben `unit`.</span><span class="sxs-lookup"><span data-stu-id="c7e08-109">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="c7e08-110">Code in einem der obersten Ebene `do` Bindung wird ausgeführt, wenn das Modul initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="c7e08-110">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="c7e08-111">Das Schlüsselwort `do` ist optional.</span><span class="sxs-lookup"><span data-stu-id="c7e08-111">The keyword `do` is optional.</span></span>

<span data-ttu-id="c7e08-112">Attribute können auf einem der obersten Ebene angewendet werden `do` Bindung.</span><span class="sxs-lookup"><span data-stu-id="c7e08-112">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="c7e08-113">Z. B. Wenn Ihr Programm COM-Interop verwendet, Sie möchten gelten die `STAThread` -Attribut auf das Programm.</span><span class="sxs-lookup"><span data-stu-id="c7e08-113">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="c7e08-114">Sie erreichen dies, indem Sie ein Attribut auf eine `do` binden, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c7e08-114">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]
    
## <a name="see-also"></a><span data-ttu-id="c7e08-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7e08-115">See Also</span></span>
[<span data-ttu-id="c7e08-116">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="c7e08-116">F# Language Reference</span></span>](../index.md)

[<span data-ttu-id="c7e08-117">Funktionen</span><span class="sxs-lookup"><span data-stu-id="c7e08-117">Functions</span></span>](index.md)

