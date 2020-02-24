---
title: let-Bindungen in Klassen
description: Erfahren Sie, wie Sie private Felder und private Funktionen F# für Klassen mithilfe von let-Bindungen in der Klassendefinition definieren.
ms.date: 05/16/2016
ms.openlocfilehash: 1366ab8f1f4f606fe5947a8fc4df10de49346b3e
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216534"
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="9fa78-103">let-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="9fa78-103">let Bindings in Classes</span></span>

<span data-ttu-id="9fa78-104">Sie können private Felder und private Funktionen für F# Klassen definieren, indem `let` Sie in der Klassendefinition Bindungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9fa78-104">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="9fa78-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9fa78-105">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="9fa78-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9fa78-106">Remarks</span></span>

<span data-ttu-id="9fa78-107">Die vorherige Syntax wird nach der Klassen Überschrift und den Vererbungs Deklarationen, jedoch vor allen Element Definitionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9fa78-107">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="9fa78-108">Die Syntax ähnelt `let` der Bindung außerhalb von Klassen, aber die in einer Klasse definierten Namen haben einen Bereich, der auf die Klasse beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="9fa78-108">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="9fa78-109">Eine `let` Bindung erstellt ein privates Feld oder eine private Funktion. um Daten oder Funktionen öffentlich verfügbar zu machen, deklarieren Sie eine Eigenschaft oder eine Member-Methode.</span><span class="sxs-lookup"><span data-stu-id="9fa78-109">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="9fa78-110">Eine `let` Bindung, die nicht statisch ist, wird als `let` instanzbindung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="9fa78-110">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="9fa78-111">Instanzbindungen `let` werden ausgeführt, wenn Objekte erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9fa78-111">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="9fa78-112">Statische `let` Bindungen sind Teil des statischen Initialisierers für die-Klasse, die vor der ersten Verwendung des Typs garantiert ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9fa78-112">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="9fa78-113">Der Code in instanzbindungen `let` kann die Parameter des primären Konstruktors verwenden.</span><span class="sxs-lookup"><span data-stu-id="9fa78-113">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="9fa78-114">Attribute und Zugriffsmodifizierer `let` sind für Bindungen in Klassen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="9fa78-114">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="9fa78-115">In den folgenden Codebeispielen werden verschiedene Typen `let` von Bindungen in Klassen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9fa78-115">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="9fa78-116">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="9fa78-116">The output is as follows.</span></span>

```console
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="9fa78-117">Alternative Möglichkeiten zum Erstellen von Feldern</span><span class="sxs-lookup"><span data-stu-id="9fa78-117">Alternative Ways to Create Fields</span></span>

<span data-ttu-id="9fa78-118">Sie können auch das `val` -Schlüsselwort verwenden, um ein privates Feld zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9fa78-118">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="9fa78-119">Wenn Sie das `val` -Schlüsselwort verwenden, wird dem Feld kein Wert zugewiesen, wenn das Objekt erstellt wird, sondern mit einem Standardwert initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="9fa78-119">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="9fa78-120">Weitere Informationen finden [Sie unter Explizite Felder: Das Val-](explicit-fields-the-val-keyword.md)Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="9fa78-120">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="9fa78-121">Sie können auch private Felder in einer Klasse definieren, indem Sie eine Element Definition verwenden und der `private` Definition das Schlüsselwort hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9fa78-121">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="9fa78-122">Dies kann hilfreich sein, wenn Sie die Barrierefreiheit eines Members ändern möchten, ohne den Code neu zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="9fa78-122">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="9fa78-123">Weitere Informationen finden Sie unter [Zugriffssteuerung](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="9fa78-123">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9fa78-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9fa78-124">See also</span></span>

- [<span data-ttu-id="9fa78-125">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="9fa78-125">Members</span></span>](index.md)
- [<span data-ttu-id="9fa78-126">`do`-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="9fa78-126">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)
- [<span data-ttu-id="9fa78-127">`let`Land/Region</span><span class="sxs-lookup"><span data-stu-id="9fa78-127">`let` Bindings</span></span>](../functions/let-bindings.md)
