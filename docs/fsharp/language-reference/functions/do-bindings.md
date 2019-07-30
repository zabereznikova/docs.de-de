---
title: do-Bindungen
description: Erfahren Sie, F# wie eine "Do"-Bindung verwendet wird, um Code auszuführen, ohne eine Funktion oder einen Wert zu definieren.
ms.date: 05/16/2016
ms.openlocfilehash: f98f523296bfaceeda35d4861eafbfeaa5a60c32
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630541"
---
# <a name="do-bindings"></a><span data-ttu-id="f0043-103">do-Bindungen</span><span class="sxs-lookup"><span data-stu-id="f0043-103">do Bindings</span></span>

<span data-ttu-id="f0043-104">Eine `do` Bindung wird verwendet, um Code auszuführen, ohne eine Funktion oder einen Wert zu definieren.</span><span class="sxs-lookup"><span data-stu-id="f0043-104">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="f0043-105">Außerdem können do-Bindungen in Klassen verwendet werden. weitere [ `do` ](../members/do-bindings-in-classes.md)Informationen finden Sie unter Bindungen in Klassen.</span><span class="sxs-lookup"><span data-stu-id="f0043-105">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="f0043-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0043-106">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="f0043-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0043-107">Remarks</span></span>

<span data-ttu-id="f0043-108">Verwenden Sie `do` eine Bindung, wenn Sie Code unabhängig von einer Funktions-oder Werte Definition ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="f0043-108">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="f0043-109">Der Ausdruck in einer `do` Bindung muss zurück `unit`geben.</span><span class="sxs-lookup"><span data-stu-id="f0043-109">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="f0043-110">Der Code in einer Bindung auf `do` oberster Ebene wird ausgeführt, wenn das Modul initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="f0043-110">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="f0043-111">Das Schlüssel `do` Wort ist optional.</span><span class="sxs-lookup"><span data-stu-id="f0043-111">The keyword `do` is optional.</span></span>

<span data-ttu-id="f0043-112">Attribute können auf eine Bindung auf oberster Ebene `do` angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0043-112">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="f0043-113">Wenn das Programm z. b. com-Interop verwendet, sollten Sie das `STAThread` -Attribut auf Ihr Programm anwenden.</span><span class="sxs-lookup"><span data-stu-id="f0043-113">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="f0043-114">Hierfür können Sie ein Attribut in einer `do` Bindung verwenden, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f0043-114">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a><span data-ttu-id="f0043-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0043-115">See also</span></span>

- [<span data-ttu-id="f0043-116">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="f0043-116">F# Language Reference</span></span>](../index.md)
- [<span data-ttu-id="f0043-117">Funktionen</span><span class="sxs-lookup"><span data-stu-id="f0043-117">Functions</span></span>](index.md)
