---
description: new-Modifizierer – C#-Referenz
title: new-Modifizierer – C#-Referenz
ms.date: 07/20/2015
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
ms.openlocfilehash: 2da0a360868250169fb16380c80bf32c4b335d7a
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139410"
---
# <a name="new-modifier-c-reference"></a><span data-ttu-id="d43cc-103">new-Modifizierer (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d43cc-103">new modifier (C# Reference)</span></span>

<span data-ttu-id="d43cc-104">Wenn das Schlüsselwort `new` als Deklarationsmodifizierer verwendet wird, blendet es explizit einen von einer Basisklasse geerbten Member aus.</span><span class="sxs-lookup"><span data-stu-id="d43cc-104">When used as a declaration modifier, the `new` keyword explicitly hides a member that is inherited from a base class.</span></span> <span data-ttu-id="d43cc-105">Wenn Sie einen geerbten Member ausblenden, ersetzt die abgeleitete Version des Members die Basisklassenversion.</span><span class="sxs-lookup"><span data-stu-id="d43cc-105">When you hide an inherited member, the derived version of the member replaces the base class version.</span></span> <span data-ttu-id="d43cc-106">Obwohl Sie Member verdecken können, ohne den `new`-Modifizierer zu verwenden, wird eine Compilerwarnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d43cc-106">Although you can hide members without using the `new` modifier, you get a compiler warning.</span></span> <span data-ttu-id="d43cc-107">Wenn Sie `new` verwenden, um einen Member explizit auszublenden, wird diese Warnung unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="d43cc-107">If you use `new` to explicitly hide a member, it suppresses this warning.</span></span>

<span data-ttu-id="d43cc-108">Sie können das Schlüsselwort `new` auch verwenden, um [eine Instanz eines Typs](../operators/new-operator.md) zu erstellen oder als [Einschränkung eines generischen Typs](./new-constraint.md).</span><span class="sxs-lookup"><span data-stu-id="d43cc-108">You can also use the `new` keyword to [create an instance of a type](../operators/new-operator.md) or as a [generic type constraint](./new-constraint.md).</span></span>

<span data-ttu-id="d43cc-109">Um einen geerbten Member auszublenden, deklarieren Sie ihn mit demselben Membernamen in der abgeleiteten Klasse und ändern ihn mit dem `new`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="d43cc-109">To hide an inherited member, declare it in the derived class by using the same member name, and modify it with the `new` keyword.</span></span> <span data-ttu-id="d43cc-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d43cc-110">For example:</span></span>

[!code-csharp[csrefKeywordsOperator#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#8)]

<span data-ttu-id="d43cc-111">In diesem Beispiel wird `BaseC.Invoke` durch `DerivedC.Invoke` ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d43cc-111">In this example, `BaseC.Invoke` is hidden by `DerivedC.Invoke`.</span></span> <span data-ttu-id="d43cc-112">Der Vorgang wirkt sich nicht auf das Feld `x` aus, da es nicht mit einem ähnlichen Namen ausgeblendet wird.</span><span class="sxs-lookup"><span data-stu-id="d43cc-112">The field `x` is not affected because it is not hidden by a similar name.</span></span>

<span data-ttu-id="d43cc-113">Das Ausblenden des Namens durch Vererbung nimmt eine der folgenden Formen an:</span><span class="sxs-lookup"><span data-stu-id="d43cc-113">Name hiding through inheritance takes one of the following forms:</span></span>

- <span data-ttu-id="d43cc-114">Im Allgemeinen blendet eine Konstante, ein Feld, eine Eigenschaft oder einen Typ, der in einer Klasse oder Struktur eingegeben wird, alle Basisklassenmember aus, die den gleichen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="d43cc-114">Generally, a constant, field, property, or type that is introduced in a class or struct hides all base class members that share its name.</span></span> <span data-ttu-id="d43cc-115">Es werden bestimmte Fälle unterschieden.</span><span class="sxs-lookup"><span data-stu-id="d43cc-115">There are special cases.</span></span> <span data-ttu-id="d43cc-116">Wenn Sie beispielsweise ein neues Feld mit dem Namen `N` mit einem nicht aufrufbaren Typ deklarieren, und ein Basistyp deklariert `N` als Methode, blendet das neue Feld die Basisdeklaration nicht in der Aufrufsyntax aus.</span><span class="sxs-lookup"><span data-stu-id="d43cc-116">For example, if you declare a new field with name `N` to have a type that is not invocable, and a base type declares `N` to be a method, the new field does not hide the base declaration in invocation syntax.</span></span> <span data-ttu-id="d43cc-117">Weitere Informationen finden Sie im Abschnitt [Membersuchvorgänge](~/_csharplang/spec/expressions.md#member-lookup) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="d43cc-117">For more information, see the [Member lookup](~/_csharplang/spec/expressions.md#member-lookup) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

- <span data-ttu-id="d43cc-118">Durch eine Methode, die in eine Klasse oder Struktur eingeführt ist, werden Eigenschaften, Felder und Typen mit dem gleichen Namen in der Basisklasse ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d43cc-118">A method introduced in a class or struct hides properties, fields, and types that share that name in the base class.</span></span> <span data-ttu-id="d43cc-119">Alle Basisklassenmethoden mit der gleichen Signatur werden ebenfalls ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d43cc-119">It also hides all base class methods that have the same signature.</span></span>

- <span data-ttu-id="d43cc-120">Durch einen Indexer, der in einer Klasse oder Struktur eingeführt ist, werden alle Basisklassenindexer mit der gleichen Signatur ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d43cc-120">An indexer introduced in a class or struct hides all base class indexers that have the same signature.</span></span>

<span data-ttu-id="d43cc-121">`new` und [override](override.md) dürfen nicht gleichzeitig auf denselben Member angewendet werden, da sich die Bedeutungen der beiden Modifizierer gegenseitig ausschließen.</span><span class="sxs-lookup"><span data-stu-id="d43cc-121">It is an error to use both `new` and [override](override.md) on the same member, because the two modifiers have mutually exclusive meanings.</span></span> <span data-ttu-id="d43cc-122">Mit dem `new`-Modifizierer wird ein neuer Member mit demselben Namen erstellt, und der ursprüngliche Member wird ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d43cc-122">The `new` modifier creates a new member with the same name and causes the original member to become hidden.</span></span> <span data-ttu-id="d43cc-123">Der `override`-Modifizierer verlängert die Implementierung für einen geerbten Member.</span><span class="sxs-lookup"><span data-stu-id="d43cc-123">The `override` modifier extends the implementation for an inherited member.</span></span>

<span data-ttu-id="d43cc-124">Wenn der `new`-Modifizierer in einer Deklaration verwendet wird, in der kein geerbter Member ausgeblendet wird, wird eine Warnung generiert.</span><span class="sxs-lookup"><span data-stu-id="d43cc-124">Using the `new` modifier in a declaration that does not hide an inherited member generates a warning.</span></span>

## <a name="example"></a><span data-ttu-id="d43cc-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d43cc-125">Example</span></span>

<span data-ttu-id="d43cc-126">In diesem Beispiel wird von einer Basisklasse, `BaseC`, und einer abgeleiteten Klasse, `DerivedC`, der gleiche Feldname `x` verwendet. Auf diese Weise wird der Wert des geerbten Felds ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d43cc-126">In this example, a base class, `BaseC`, and a derived class, `DerivedC`, use the same field name `x`, which hides the value of the inherited field.</span></span> <span data-ttu-id="d43cc-127">Im Beispiel wird die Verwendung des `new`-Modifizierers veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d43cc-127">The example demonstrates the use of the `new` modifier.</span></span> <span data-ttu-id="d43cc-128">Außerdem wird gezeigt, wie mit den voll qualifizierten Namen auf die ausgeblendeten Member der Basisklasse zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="d43cc-128">It also demonstrates how to access the hidden members of the base class by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#9)]

## <a name="example"></a><span data-ttu-id="d43cc-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d43cc-129">Example</span></span>

<span data-ttu-id="d43cc-130">In diesem Beispiel blendet eine geschachtelte Klasse eine Klasse mit dem gleichen Namen in der Basisklasse aus.</span><span class="sxs-lookup"><span data-stu-id="d43cc-130">In this example, a nested class hides a class that has the same name in the base class.</span></span> <span data-ttu-id="d43cc-131">Das Beispiel veranschaulicht, wie mit dem `new`-Modifizierer die Warnmeldung vermieden wird und wie mit den voll qualifizierten Namen auf die ausgeblendeten Klassenmember zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="d43cc-131">The example demonstrates how to use the `new` modifier to eliminate the warning message and how to access the hidden class members by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#10)]

<span data-ttu-id="d43cc-132">Wenn der `new`-Modifizierer entfernt wird, kann das Programm dennoch kompiliert und ausgeführt werden. Es wird jedoch folgende Warnung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="d43cc-132">If you remove the `new` modifier, the program will still compile and run, but you will get the following warning:</span></span>

```text
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.
```

## <a name="c-language-specification"></a><span data-ttu-id="d43cc-133">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="d43cc-133">C# language specification</span></span>

<span data-ttu-id="d43cc-134">Weitere Informationen finden Sie im Abschnitt [Der new-Modifizierer](~/_csharplang/spec/classes.md#the-new-modifier) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="d43cc-134">For more information, see [The new modifier](~/_csharplang/spec/classes.md#the-new-modifier) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d43cc-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d43cc-135">See also</span></span>

- [<span data-ttu-id="d43cc-136">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d43cc-136">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d43cc-137">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d43cc-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d43cc-138">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d43cc-138">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="d43cc-139">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="d43cc-139">Modifiers</span></span>](index.md)
- [<span data-ttu-id="d43cc-140">Versionsverwaltung mit den Schlüsselwörtern "override" und "new"</span><span class="sxs-lookup"><span data-stu-id="d43cc-140">Versioning with the Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)
- [<span data-ttu-id="d43cc-141">Wann müssen die Schlüsselwörter "override" und "new" verwendet werden?</span><span class="sxs-lookup"><span data-stu-id="d43cc-141">Knowing When to Use Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)
