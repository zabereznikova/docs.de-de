---
title: do-Bindungen
description: Erfahren Sie, wie ein F# 'do', Bindung werden verwendet, um Code auszuführen, ohne die Definition einer Funktion oder Wert.
ms.date: 05/16/2016
ms.openlocfilehash: d29f8557fda06097d2e85748ab6286f0415730b3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61683378"
---
# <a name="do-bindings"></a><span data-ttu-id="2a8b7-103">do-Bindungen</span><span class="sxs-lookup"><span data-stu-id="2a8b7-103">do Bindings</span></span>

<span data-ttu-id="2a8b7-104">Ein `do` Bindung wird verwendet, um Code auszuführen, ohne die Definition einer Funktion oder Wert.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-104">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="2a8b7-105">Darüber hinaus werden Bindungen möglich in Klassen finden Sie in [ `do` Bindungen in Klassen](../members/do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="2a8b7-105">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="2a8b7-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a8b7-106">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="2a8b7-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2a8b7-107">Remarks</span></span>

<span data-ttu-id="2a8b7-108">Verwenden einer `do` binden, wenn Sie möchten, dass zum Ausführen von Code unabhängig von der Definition einer Funktion oder Wert.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-108">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="2a8b7-109">Der Ausdruck in einem `do` Bindung muss zurückgeben `unit`.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-109">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="2a8b7-110">Code in einem der obersten Ebene `do` Bindung ausgeführt wird, wenn das Modul initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-110">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="2a8b7-111">Das Schlüsselwort `do` ist optional.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-111">The keyword `do` is optional.</span></span>

<span data-ttu-id="2a8b7-112">Attribute können auf oberster Ebene angewendet werden `do` Bindung.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-112">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="2a8b7-113">Z. B. Wenn Ihr Programm COM-Interop verwendet, Sie möchten gelten die `STAThread` -Attribut auf Ihr Programm.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-113">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="2a8b7-114">Sie erreichen dies, indem Sie ein Attribut auf eine `do` binden, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="2a8b7-114">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a><span data-ttu-id="2a8b7-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a8b7-115">See also</span></span>

- [<span data-ttu-id="2a8b7-116">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="2a8b7-116">F# Language Reference</span></span>](../index.md)
- [<span data-ttu-id="2a8b7-117">Funktionen</span><span class="sxs-lookup"><span data-stu-id="2a8b7-117">Functions</span></span>](index.md)