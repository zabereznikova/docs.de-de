---
title: let-Bindungen in Klassen (F#)
description: Erfahren Sie, wie Sie private Felder und private Funktionen für F#-Klassen definieren, mit "let"-Bindungen in der Klassendefinition.
ms.date: 05/16/2016
ms.openlocfilehash: 237eb98a57571a21c9187abf31f05160374cf4fc
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45972875"
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="db54a-103">let-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="db54a-103">let Bindings in Classes</span></span>

<span data-ttu-id="db54a-104">Sie können die privaten Felder und private Funktionen für F#-Klassen definieren, mit `let` Bindungen in der Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="db54a-104">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="db54a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="db54a-105">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="db54a-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="db54a-106">Remarks</span></span>

<span data-ttu-id="db54a-107">Die vorherige Syntax wird nach den Klassendeklarationen Überschrift und Vererbung, aber vor Memberdefinitionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="db54a-107">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="db54a-108">Die Syntax lautet wie `let` Bindungen außerhalb von Klassen, aber die Namen in einer Klasse definiert haben, einen Bereich, auf die Klasse beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="db54a-108">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="db54a-109">Ein `let` Bindung erstellt wird, ein privates Feld bzw. die Funktion; zum Verfügbarmachen von Daten oder Funktionen zu einer Eigenschaft oder ein Membermethode öffentlich deklarieren.</span><span class="sxs-lookup"><span data-stu-id="db54a-109">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="db54a-110">Ein `let` Bindung, ist nicht statisch ist eine Instanz namens `let` Bindung.</span><span class="sxs-lookup"><span data-stu-id="db54a-110">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="db54a-111">Instanz `let` Bindungen ausgeführt, wenn Objekte erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="db54a-111">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="db54a-112">Statische `let` Bindungen sind Teil der statische Initialisierer für die Klasse, die unbedingt ausführen, bevor Sie der Typ zuerst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="db54a-112">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="db54a-113">Der Code innerhalb der Instanz `let` der primäre Konstruktor Parameter von Bindungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="db54a-113">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="db54a-114">Attribute und Zugriffsmodifizierer dürfen nicht auf `let` Bindungen in Klassen.</span><span class="sxs-lookup"><span data-stu-id="db54a-114">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="db54a-115">Die folgenden Codebeispiele veranschaulichen verschiedene Arten von `let` Bindungen in Klassen.</span><span class="sxs-lookup"><span data-stu-id="db54a-115">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="db54a-116">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="db54a-116">The output is as follows.</span></span>

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="db54a-117">Alternative Möglichkeiten zum Erstellen von Feldern</span><span class="sxs-lookup"><span data-stu-id="db54a-117">Alternative Ways to Create Fields</span></span>

<span data-ttu-id="db54a-118">Sie können auch die `val` Schlüsselwort, um ein privates Feld erstellen.</span><span class="sxs-lookup"><span data-stu-id="db54a-118">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="db54a-119">Bei Verwendung der `val` -Schlüsselwort, das Feld ist kein Wert zugewiesen, wenn das Objekt wird erstellt, jedoch mit einem Standardwert initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="db54a-119">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="db54a-120">Weitere Informationen finden Sie unter [explizite Felder: das Val Schlüsselwort](explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="db54a-120">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="db54a-121">Sie können auch private Felder in einer Klasse definieren, indem Sie eine Elementdefinition und durch Hinzufügen des Schlüsselworts `private` der Definition.</span><span class="sxs-lookup"><span data-stu-id="db54a-121">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="db54a-122">Dies kann nützlich sein, wenn Sie erwarten, um den Zugriff auf ein Element zu ändern, ohne den Code umzuschreiben.</span><span class="sxs-lookup"><span data-stu-id="db54a-122">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="db54a-123">Weitere Informationen finden Sie unter [Zugriffssteuerung](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="db54a-123">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="db54a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db54a-124">See also</span></span>

- [<span data-ttu-id="db54a-125">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="db54a-125">Members</span></span>](index.md)
- [<span data-ttu-id="db54a-126">`do`-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="db54a-126">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)
- [<span data-ttu-id="db54a-127">`let` Bindungen</span><span class="sxs-lookup"><span data-stu-id="db54a-127">`let` Bindings</span></span>](../functions/let-bindings.md)
