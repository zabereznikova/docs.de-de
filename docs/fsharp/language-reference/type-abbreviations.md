---
title: Typabkürzungen
description: Informationen Sie zu F# typabkürzungen auf einem Typ einen aussagekräftigeren Namen geben, damit der um Code leichter lesbar zu machen.
ms.date: 05/16/2016
ms.openlocfilehash: 339b22a675e3f1ad8a3da207053e611942b55a22
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630212"
---
# <a name="type-abbreviations"></a><span data-ttu-id="1e352-103">Typabkürzungen</span><span class="sxs-lookup"><span data-stu-id="1e352-103">Type Abbreviations</span></span>

<span data-ttu-id="1e352-104">Eine *typabkürzung* ist ein Alias oder ein alternativer Name für einen Typ.</span><span class="sxs-lookup"><span data-stu-id="1e352-104">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="1e352-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e352-105">Syntax</span></span>

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="1e352-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1e352-106">Remarks</span></span>

<span data-ttu-id="1e352-107">Mit typabkürzungen können Sie einen aussagekräftigeren Namen geben, um den Code leichter lesbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="1e352-107">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="1e352-108">Sie können Sie auch verwenden, um einen benutzerfreundlichen Namen für einen Typ zu erstellen, der andernfalls mühsam zu schreiben ist. Außerdem können Sie typabkürzungen verwenden, um die Änderung eines zugrunde liegenden Typs zu vereinfachen, ohne den gesamten Code zu ändern, der den Typ verwendet.</span><span class="sxs-lookup"><span data-stu-id="1e352-108">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="1e352-109">Im folgenden finden Sie eine einfache typabkürzung.</span><span class="sxs-lookup"><span data-stu-id="1e352-109">The following is a simple type abbreviation.</span></span>

<span data-ttu-id="1e352-110">Der Zugriff auf typabkürzungen ist `public`standardmäßig auf.</span><span class="sxs-lookup"><span data-stu-id="1e352-110">Accessibility of type abbreviations defaults to `public`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="1e352-111">Typabkürzungen können generische Parameter enthalten, wie im folgenden Code zu sehen.</span><span class="sxs-lookup"><span data-stu-id="1e352-111">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="1e352-112">Im vorherigen Code `Transform` ist eine typabkürzung, die eine Funktion darstellt, die ein einzelnes Argument eines beliebigen Typs annimmt und einen einzelnen Wert desselben Typs zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="1e352-112">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="1e352-113">Typabkürzungen werden im .NET Framework MSIL-Code nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="1e352-113">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="1e352-114">Wenn Sie eine F# Assembly aus einer anderen .NET Framework Sprache verwenden, müssen Sie daher den zugrunde liegenden Typnamen für eine typabkürzung verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e352-114">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="1e352-115">Typabkürzungen können auch für Maßeinheiten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1e352-115">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="1e352-116">Weitere Informationen finden Sie unter [Maßeinheiten](units-of-measure.md).</span><span class="sxs-lookup"><span data-stu-id="1e352-116">For more information, see [Units of Measure](units-of-measure.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1e352-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e352-117">See also</span></span>

- [<span data-ttu-id="1e352-118">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="1e352-118">F# Language Reference</span></span>](index.md)
