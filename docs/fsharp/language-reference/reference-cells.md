---
title: Referenzzellen
description: Erfahren Sie, wie F# Referenzzellen Speicherorte sind, die Ihnen ermöglichen, änderbare Werte mit Verweissemantik zu erstellen.
ms.date: 05/16/2016
ms.openlocfilehash: 2bca7797b272c0e7d5bf54df07041dc08e33709a
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216778"
---
# <a name="reference-cells"></a><span data-ttu-id="7509d-103">Referenzzellen</span><span class="sxs-lookup"><span data-stu-id="7509d-103">Reference Cells</span></span>

<span data-ttu-id="7509d-104">*Verweis Zellen* sind Speicherorte, die es Ihnen ermöglichen, änderbare Werte mit Verweis Semantik zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7509d-104">*Reference cells* are storage locations that enable you to create mutable values with reference semantics.</span></span>

## <a name="syntax"></a><span data-ttu-id="7509d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7509d-105">Syntax</span></span>

```fsharp
ref expression
```

## <a name="remarks"></a><span data-ttu-id="7509d-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7509d-106">Remarks</span></span>

<span data-ttu-id="7509d-107">Sie verwenden den Operator `ref` vor einem Wert, um eine neue Referenzzelle zu erstellen, die den Wert kapselt.</span><span class="sxs-lookup"><span data-stu-id="7509d-107">You use the `ref` operator before a value to create a new reference cell that encapsulates the value.</span></span> <span data-ttu-id="7509d-108">Anschließend können Sie den zugrunde liegenden Wert ändern, da er änderbar ist.</span><span class="sxs-lookup"><span data-stu-id="7509d-108">You can then change the underlying value because it is mutable.</span></span>

<span data-ttu-id="7509d-109">Eine Referenzzelle enthält einen tatsächlichen Wert, sie ist nicht lediglich eine Adresse.</span><span class="sxs-lookup"><span data-stu-id="7509d-109">A reference cell holds an actual value; it is not just an address.</span></span> <span data-ttu-id="7509d-110">Wenn Sie mit dem Operator `ref` eine Referenzzelle erstellen, erstellen Sie eine Kopie des zugrunde liegenden Werts als gekapselten änderbaren Wert.</span><span class="sxs-lookup"><span data-stu-id="7509d-110">When you create a reference cell by using the `ref` operator, you create a copy of the underlying value as an encapsulated mutable value.</span></span>

<span data-ttu-id="7509d-111">Mit dem Operator `!` (Bang) können Sie eine Referenzzelle dereferenzieren.</span><span class="sxs-lookup"><span data-stu-id="7509d-111">You can dereference a reference cell by using the `!` (bang) operator.</span></span>

<span data-ttu-id="7509d-112">Im folgenden Codebeispiel werden die Deklaration und Verwendung von Referenzzellen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7509d-112">The following code example illustrates the declaration and use of reference cells.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

<span data-ttu-id="7509d-113">Die Ausgabe lautet `50`.</span><span class="sxs-lookup"><span data-stu-id="7509d-113">The output is `50`.</span></span>

<span data-ttu-id="7509d-114">Referenzzellen sind Instanzen des generischen `Ref`-Datensatztyps, der wie folgt deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="7509d-114">Reference cells are instances of the `Ref` generic record type, which is declared as follows.</span></span>

```fsharp
type Ref<'a> =
{ mutable contents: 'a }
```

<span data-ttu-id="7509d-115">Der Typ `'a ref` ist ein Synonym für `Ref<'a>`.</span><span class="sxs-lookup"><span data-stu-id="7509d-115">The type `'a ref` is a synonym for `Ref<'a>`.</span></span> <span data-ttu-id="7509d-116">Der Compiler und IntelliSense in der IDE zeigen erstere Version für diesen Typ an, jedoch ist letztere Version die zugrunde liegende Definition.</span><span class="sxs-lookup"><span data-stu-id="7509d-116">The compiler and IntelliSense in the IDE display the former for this type, but the underlying definition is the latter.</span></span>

<span data-ttu-id="7509d-117">Mit dem Operator `ref` wird eine neue Referenzzelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="7509d-117">The `ref` operator creates a new reference cell.</span></span> <span data-ttu-id="7509d-118">Der folgende Code ist die Deklaration des Operators `ref`.</span><span class="sxs-lookup"><span data-stu-id="7509d-118">The following code is the declaration of the `ref` operator.</span></span>

```fsharp
let ref x = { contents = x }
```

<span data-ttu-id="7509d-119">Die folgende Tabelle enthält die Funktionen, die für die Referenzzelle verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="7509d-119">The following table shows the features that are available on the reference cell.</span></span>

|<span data-ttu-id="7509d-120">Operator, Member oder Feld</span><span class="sxs-lookup"><span data-stu-id="7509d-120">Operator, member, or field</span></span>|<span data-ttu-id="7509d-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7509d-121">Description</span></span>|<span data-ttu-id="7509d-122">Typ</span><span class="sxs-lookup"><span data-stu-id="7509d-122">Type</span></span>|<span data-ttu-id="7509d-123">Definition</span><span class="sxs-lookup"><span data-stu-id="7509d-123">Definition</span></span>|
|--------------------------|-----------|----|----------|
|<span data-ttu-id="7509d-124">`!` (Dereferenzierungsoperator)</span><span class="sxs-lookup"><span data-stu-id="7509d-124">`!` (dereference operator)</span></span>|<span data-ttu-id="7509d-125">Gibt den zugrunde liegenden Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="7509d-125">Returns the underlying value.</span></span>|`'a ref -> 'a`|`let (!) r = r.contents`|
|<span data-ttu-id="7509d-126">`:=` (Zuweisungsoperator)</span><span class="sxs-lookup"><span data-stu-id="7509d-126">`:=` (assignment operator)</span></span>|<span data-ttu-id="7509d-127">Ändert den zugrunde liegenden Wert.</span><span class="sxs-lookup"><span data-stu-id="7509d-127">Changes the underlying value.</span></span>|`'a ref -> 'a -> unit`|`let (:=) r x = r.contents <- x`|
|<span data-ttu-id="7509d-128">`ref` (Operator)</span><span class="sxs-lookup"><span data-stu-id="7509d-128">`ref` (operator)</span></span>|<span data-ttu-id="7509d-129">Kapselt einen Wert in einer neuen Referenzzelle.</span><span class="sxs-lookup"><span data-stu-id="7509d-129">Encapsulates a value into a new reference cell.</span></span>|`'a -> 'a ref`|`let ref x = { contents = x }`|
|<span data-ttu-id="7509d-130">`Value`Property</span><span class="sxs-lookup"><span data-stu-id="7509d-130">`Value` (property)</span></span>|<span data-ttu-id="7509d-131">Ruft den zugrunde liegenden Wert ab oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="7509d-131">Gets or sets the underlying value.</span></span>|`unit -> 'a`|`member x.Value = x.contents`|
|<span data-ttu-id="7509d-132">`contents` (Datensatzfeld)</span><span class="sxs-lookup"><span data-stu-id="7509d-132">`contents` (record field)</span></span>|<span data-ttu-id="7509d-133">Ruft den zugrunde liegenden Wert ab oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="7509d-133">Gets or sets the underlying value.</span></span>|`'a`|`let ref x = { contents = x }`|

<span data-ttu-id="7509d-134">Es gibt mehrere Möglichkeiten, auf den zugrunde liegenden Wert zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="7509d-134">There are several ways to access the underlying value.</span></span> <span data-ttu-id="7509d-135">Der vom Dereferenzierungsoperator (`!`) zurückgegebene Wert ist kein zuweisbarer Wert.</span><span class="sxs-lookup"><span data-stu-id="7509d-135">The value returned by the dereference operator (`!`) is not an assignable value.</span></span> <span data-ttu-id="7509d-136">Wenn Sie den zugrunde liegenden Wert ändern, müssen Sie daher stattdessen den Zuweisungsoperator (`:=`) verwenden.</span><span class="sxs-lookup"><span data-stu-id="7509d-136">Therefore, if you are modifying the underlying value, you must use the assignment operator (`:=`) instead.</span></span>

<span data-ttu-id="7509d-137">Sowohl die `Value`-Eigenschaft als auch das `contents`-Feld sind zuweisbare Werte.</span><span class="sxs-lookup"><span data-stu-id="7509d-137">Both the `Value` property and the `contents` field are assignable values.</span></span> <span data-ttu-id="7509d-138">Daher können Sie diese verwenden, um auf den zugrunde liegenden Wert zuzugreifen oder diesen zu ändern, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7509d-138">Therefore, you can use these to either access or change the underlying value, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

<span data-ttu-id="7509d-139">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="7509d-139">The output is as follows.</span></span>

```console
10
10
11
12
```

<span data-ttu-id="7509d-140">Das Feld `contents` wird für die Kompatibilität mit anderen Versionen von ML bereitgestellt und gibt während der Kompilierung eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="7509d-140">The field `contents` is provided for compatibility with other versions of ML and will produce a warning during compilation.</span></span> <span data-ttu-id="7509d-141">Verwenden Sie die `--mlcompatibility`-Compileroption, um die Warnung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7509d-141">To disable the warning, use the `--mlcompatibility` compiler option.</span></span> <span data-ttu-id="7509d-142">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="7509d-142">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="7509d-143">C#Programmierer sollten wissen, `ref` dass C# in nicht der gleiche ist wie `ref` in F#.</span><span class="sxs-lookup"><span data-stu-id="7509d-143">C# programmers should know that `ref` in C# is not the same thing as `ref` in F#.</span></span> <span data-ttu-id="7509d-144">Die entsprechende Konstrukte in F# sind [Byrefs](byrefs.md), die ein anderes Konzept als Referenzzellen sind.</span><span class="sxs-lookup"><span data-stu-id="7509d-144">The equivalent constructs in F# are [byrefs](byrefs.md), which are a different concept from reference cells.</span></span>

<span data-ttu-id="7509d-145">Als `mutable`markierte Werte werden möglicherweise automatisch auf `'a ref` herauf gestuft, wenn Sie durch einen Abschluss aufgezeichnet werden. siehe [Werte](./values/index.md).</span><span class="sxs-lookup"><span data-stu-id="7509d-145">Values marked as `mutable`may be automatically promoted to `'a ref` if captured by a closure; see [Values](./values/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7509d-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7509d-146">See also</span></span>

- [<span data-ttu-id="7509d-147">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="7509d-147">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="7509d-148">Parameter und Argumente</span><span class="sxs-lookup"><span data-stu-id="7509d-148">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="7509d-149">Symbol- und Operatorenreferenz</span><span class="sxs-lookup"><span data-stu-id="7509d-149">Symbol and Operator Reference</span></span>](./symbol-and-operator-reference/index.md)
- [<span data-ttu-id="7509d-150">Werte</span><span class="sxs-lookup"><span data-stu-id="7509d-150">Values</span></span>](./values/index.md)
