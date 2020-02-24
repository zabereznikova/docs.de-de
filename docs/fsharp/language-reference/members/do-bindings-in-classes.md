---
title: do-Bindungen in Klassen
description: Erfahren Sie, wie Sie F# eine "Do"-Bindung in einer Klassendefinition verwenden, die Aktionen ausführt, wenn das Objekt erstellt wird oder wenn der Typ zum ersten Mal verwendet wird.
ms.date: 05/16/2016
ms.openlocfilehash: ced4f1bb17d9e23bf51cc79b5a275cc334cca013
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627586"
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="a0501-103">do-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="a0501-103">do Bindings in Classes</span></span>

<span data-ttu-id="a0501-104">Eine `do` Bindung in einer Klassendefinition führt Aktionen aus, wenn das Objekt erstellt wird, oder für `do` eine statische Bindung, wenn der Typ zum ersten Mal verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a0501-104">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>

## <a name="syntax"></a><span data-ttu-id="a0501-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0501-105">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="a0501-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0501-106">Remarks</span></span>

<span data-ttu-id="a0501-107">Eine `do` Bindung wird mit oder nach `let` Bindungen, aber vor Member-Definitionen in einer Klassendefinition angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0501-107">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="a0501-108">Obwohl das `do` -Schlüsselwort für `do` Bindungen auf Modulebene optional ist, ist es für `do` Bindungen in einer Klassendefinition nicht optional.</span><span class="sxs-lookup"><span data-stu-id="a0501-108">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="a0501-109">Bei der Erstellung jedes Objekts eines beliebigen Typs werden nicht statische `do` Bindungen und nicht statische `let` Bindungen in der Reihenfolge ausgeführt, in der Sie in der Klassendefinition angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a0501-109">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="a0501-110">Mehrere `do` Bindungen können in einem Typ auftreten.</span><span class="sxs-lookup"><span data-stu-id="a0501-110">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="a0501-111">Die nicht statischen `let` Bindungen und die nicht statischen `do` Bindungen werden zum Hauptteil des primären Konstruktors.</span><span class="sxs-lookup"><span data-stu-id="a0501-111">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="a0501-112">Der Code im Abschnitt nicht statische `do` Bindungen kann auf die primären Konstruktorparameter und alle Werte oder Funktionen verweisen, die `let` im Bindungs Abschnitt definiert sind.</span><span class="sxs-lookup"><span data-stu-id="a0501-112">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="a0501-113">Nicht statische `do` Bindungen können auf Member der Klasse zugreifen, sofern die Klasse über einen selbst Bezeichner verfügt, der durch ein `as` -Schlüsselwort in der Überschrift der-Klasse definiert wird, und solange alle Verwendungen dieser Member mit dem selbst Bezeichner für die Klasse qualifiziert sind.</span><span class="sxs-lookup"><span data-stu-id="a0501-113">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="a0501-114">Da `let` Bindungen die privaten Felder einer Klasse initialisieren, was häufig notwendig ist, um sicherzustellen, dass sich die Member `do` wie erwartet Verhalten, werden `let` Bindungen in der Regel nach Bindungen `do` eingefügt, sodass der Code in der Bindung Führen Sie mit einem vollständig initialisierten Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="a0501-114">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="a0501-115">Wenn Ihr Code versucht, einen Member zu verwenden, bevor die Initialisierung beendet ist, wird eine InvalidOperationException ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a0501-115">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="a0501-116">Statische `do` Bindungen können auf statische Member oder Felder der einschließenden Klasse verweisen, jedoch nicht auf Instanzmember oder-Felder.</span><span class="sxs-lookup"><span data-stu-id="a0501-116">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="a0501-117">Statische `do` Bindungen werden Teil des statischen Initialisierers für die Klasse, die vor der ersten Verwendung der Klasse garantiert ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a0501-117">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="a0501-118">Attribute werden bei `do` Bindungen in Typen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a0501-118">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="a0501-119">Wenn ein Attribut für Code erforderlich ist, der in einer `do` Bindung ausgeführt wird, muss er auf den primären Konstruktor angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0501-119">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="a0501-120">Im folgenden Code verfügt eine Klasse über eine statische `do` Bindung und eine nicht statische `do` Bindung.</span><span class="sxs-lookup"><span data-stu-id="a0501-120">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="a0501-121">Das-Objekt verfügt über einen Konstruktor mit zwei para `a` Metern `b`: und, und zwei private Felder werden in `let` den Bindungen für die-Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="a0501-121">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="a0501-122">Außerdem werden zwei Eigenschaften definiert.</span><span class="sxs-lookup"><span data-stu-id="a0501-122">Two properties are also defined.</span></span> <span data-ttu-id="a0501-123">Alle diese Werte befinden sich im Bereich "nicht statische `do` Bindungen", wie in der Zeile veranschaulicht, in der alle diese Werte gedruckt werden.</span><span class="sxs-lookup"><span data-stu-id="a0501-123">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="a0501-124">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="a0501-124">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="a0501-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0501-125">See also</span></span>

- [<span data-ttu-id="a0501-126">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="a0501-126">Members</span></span>](index.md)
- [<span data-ttu-id="a0501-127">Klassen</span><span class="sxs-lookup"><span data-stu-id="a0501-127">Classes</span></span>](../classes.md)
- [<span data-ttu-id="a0501-128">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="a0501-128">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="a0501-129">`let`-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="a0501-129">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)
- [<span data-ttu-id="a0501-130">`do`Land/Region</span><span class="sxs-lookup"><span data-stu-id="a0501-130">`do` Bindings</span></span>](../functions/do-Bindings.md)
