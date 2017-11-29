---
title: let-Bindungen in Klassen (F#)
description: "Erfahren Sie, wie private Felder und private Funktionen für F#-Klassen, die mithilfe von 'let' Bindungen in der Klassendefinition definiert sind."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9d3710f5-68b1-4e4c-b02b-27fe018f20e8
ms.openlocfilehash: 1337cc0794e366e8c39745f5c45065362c9c38c9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="dfa7f-104">let-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="dfa7f-104">let Bindings in Classes</span></span>

<span data-ttu-id="dfa7f-105">Sie können private Felder und private Funktionen für F#-Klassen definieren, mit `let` Bindungen in der Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="dfa7f-105">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>


## <a name="syntax"></a><span data-ttu-id="dfa7f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="dfa7f-106">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="dfa7f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dfa7f-107">Remarks</span></span>
<span data-ttu-id="dfa7f-108">Die vorherige Syntax wird nach den Klassendeklarationen Überschrift und Vererbung, aber vor Memberdefinitionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dfa7f-108">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="dfa7f-109">Die Syntax gleicht der `let` Bindungen außerhalb von Klassen, aber die Namen in einer Klasse definiert ist, einen Bereich, auf die Klasse beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="dfa7f-109">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="dfa7f-110">Ein `let` Bindung erstellt, ein privates Feld bzw. die Funktion; um Daten verfügbar zu machen oder Funktionen öffentlich, deklarieren Sie eine Eigenschaft oder ein Member-Methode.</span><span class="sxs-lookup"><span data-stu-id="dfa7f-110">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="dfa7f-111">Ein `let` Bindung, die sich nicht statisch ist eine Instanz aufgerufen `let` Bindung.</span><span class="sxs-lookup"><span data-stu-id="dfa7f-111">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="dfa7f-112">Instanz `let` Bindungen ausgeführt, wenn Objekte erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="dfa7f-112">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="dfa7f-113">Statische `let` Bindungen sind Teil der statische Initialisierer für die Klasse, die unbedingt ausführen, bevor der Typ zuerst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dfa7f-113">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="dfa7f-114">Der Code innerhalb der Instanz `let` den primären Konstruktor Parameter von Bindungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="dfa7f-114">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="dfa7f-115">Attribute und Zugriffsmodifizierer sind zulässig, `let` Bindungen in Klassen.</span><span class="sxs-lookup"><span data-stu-id="dfa7f-115">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="dfa7f-116">Die folgenden Codebeispiele veranschaulichen verschiedene `let` Bindungen in Klassen.</span><span class="sxs-lookup"><span data-stu-id="dfa7f-116">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="dfa7f-117">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="dfa7f-117">The output is as follows.</span></span>

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="dfa7f-118">Alternative Möglichkeiten zum Erstellen von Feldern</span><span class="sxs-lookup"><span data-stu-id="dfa7f-118">Alternative Ways to Create Fields</span></span>
<span data-ttu-id="dfa7f-119">Sie können auch die `val` Schlüsselwort, um ein privates Feld erstellen.</span><span class="sxs-lookup"><span data-stu-id="dfa7f-119">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="dfa7f-120">Bei Verwendung der `val` -Schlüsselwort, das Feld ist kein Wert zugewiesen, wenn das Objekt erstellt wird, sondern stattdessen mit einem Standardwert initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="dfa7f-120">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="dfa7f-121">Weitere Informationen finden Sie unter [explizite Felder: das Val Schlüsselwort](explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="dfa7f-121">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="dfa7f-122">Sie können auch private Felder in einer Klasse definieren, durch die Definition eines Elements verwenden und das Schlüsselwort hinzufügen `private` der Definition.</span><span class="sxs-lookup"><span data-stu-id="dfa7f-122">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="dfa7f-123">Dies kann nützlich, wenn Sie erwarten, den Zugriff auf ein Element ändern dass, ohne den Code umzuschreiben sein.</span><span class="sxs-lookup"><span data-stu-id="dfa7f-123">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="dfa7f-124">Weitere Informationen finden Sie unter [Zugriffssteuerung](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="dfa7f-124">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dfa7f-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfa7f-125">See Also</span></span>
[<span data-ttu-id="dfa7f-126">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="dfa7f-126">Members</span></span>](index.md)

[<span data-ttu-id="dfa7f-127">`do`-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="dfa7f-127">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)

[<span data-ttu-id="dfa7f-128">`let`Bindungen</span><span class="sxs-lookup"><span data-stu-id="dfa7f-128">`let` Bindings</span></span>](../functions/let-bindings.md)
