---
title: do-Bindungen (F#)
description: Erfahren Sie, wie eine F#-"Bindung" do"verwendet wird, Code auszuführen, ohne die Definition einer Funktion oder einen Wert.
ms.date: 05/16/2016
ms.openlocfilehash: 78dbf8da0fe40b5af566ad98693df1109eede7e4
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "44353095"
---
# <a name="do-bindings"></a><span data-ttu-id="0276a-103">do-Bindungen</span><span class="sxs-lookup"><span data-stu-id="0276a-103">do Bindings</span></span>

<span data-ttu-id="0276a-104">Ein `do` Bindung wird verwendet, um Code auszuführen, ohne die Definition einer Funktion oder Wert.</span><span class="sxs-lookup"><span data-stu-id="0276a-104">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="0276a-105">Darüber hinaus werden Bindungen möglich in Klassen finden Sie in [ `do` Bindungen in Klassen](../members/do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="0276a-105">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="0276a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="0276a-106">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="0276a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0276a-107">Remarks</span></span>

<span data-ttu-id="0276a-108">Verwenden einer `do` binden, wenn Sie möchten, dass zum Ausführen von Code unabhängig von der Definition einer Funktion oder Wert.</span><span class="sxs-lookup"><span data-stu-id="0276a-108">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="0276a-109">Der Ausdruck in einem `do` Bindung muss zurückgeben `unit`.</span><span class="sxs-lookup"><span data-stu-id="0276a-109">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="0276a-110">Code in einem der obersten Ebene `do` Bindung ausgeführt wird, wenn das Modul initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="0276a-110">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="0276a-111">Das Schlüsselwort `do` ist optional.</span><span class="sxs-lookup"><span data-stu-id="0276a-111">The keyword `do` is optional.</span></span>

<span data-ttu-id="0276a-112">Attribute können auf oberster Ebene angewendet werden `do` Bindung.</span><span class="sxs-lookup"><span data-stu-id="0276a-112">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="0276a-113">Z. B. Wenn Ihr Programm COM-Interop verwendet, Sie möchten gelten die `STAThread` -Attribut auf Ihr Programm.</span><span class="sxs-lookup"><span data-stu-id="0276a-113">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="0276a-114">Sie erreichen dies, indem Sie ein Attribut auf eine `do` binden, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0276a-114">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a><span data-ttu-id="0276a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0276a-115">See also</span></span>

- [<span data-ttu-id="0276a-116">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="0276a-116">F# Language Reference</span></span>](../index.md)
- [<span data-ttu-id="0276a-117">Funktionen</span><span class="sxs-lookup"><span data-stu-id="0276a-117">Functions</span></span>](index.md)
