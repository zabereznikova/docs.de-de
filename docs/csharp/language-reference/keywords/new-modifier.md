---
title: new-Modifizierer – C#-Referenz
ms.date: 07/20/2015
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
ms.openlocfilehash: 529d77b0a66a8a3cedfe7a400af0fb34dd653322
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795169"
---
# <a name="new-modifier-c-reference"></a><span data-ttu-id="7485a-102">new-Modifizierer (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7485a-102">new modifier (C# Reference)</span></span>

<span data-ttu-id="7485a-103">Wenn das Schlüsselwort `new` als Deklarationsmodifizierer verwendet wird, blendet es explizit einen von einer Basisklasse geerbten Member aus.</span><span class="sxs-lookup"><span data-stu-id="7485a-103">When used as a declaration modifier, the `new` keyword explicitly hides a member that is inherited from a base class.</span></span> <span data-ttu-id="7485a-104">Wenn Sie einen geerbten Member ausblenden, ersetzt die abgeleitete Version des Members die Basisklassenversion.</span><span class="sxs-lookup"><span data-stu-id="7485a-104">When you hide an inherited member, the derived version of the member replaces the base class version.</span></span> <span data-ttu-id="7485a-105">Obwohl Sie Member verdecken können, ohne den `new`-Modifizierer zu verwenden, wird eine Compilerwarnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7485a-105">Although you can hide members without using the `new` modifier, you get a compiler warning.</span></span> <span data-ttu-id="7485a-106">Wenn Sie `new` verwenden, um einen Member explizit auszublenden, wird diese Warnung unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="7485a-106">If you use `new` to explicitly hide a member, it suppresses this warning.</span></span>

<span data-ttu-id="7485a-107">Sie können das Schlüsselwort `new` auch verwenden, um [eine Instanz eines Typs](../operators/new-operator.md) zu erstellen oder als [Einschränkung eines generischen Typs](./new-constraint.md).</span><span class="sxs-lookup"><span data-stu-id="7485a-107">You can also use the `new` keyword to [create an instance of a type](../operators/new-operator.md) or as a [generic type constraint](./new-constraint.md).</span></span>

<span data-ttu-id="7485a-108">Um einen geerbten Member auszublenden, deklarieren Sie ihn mit demselben Membernamen in der abgeleiteten Klasse und ändern ihn mit dem `new`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="7485a-108">To hide an inherited member, declare it in the derived class by using the same member name, and modify it with the `new` keyword.</span></span> <span data-ttu-id="7485a-109">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7485a-109">For example:</span></span>

[!code-csharp[csrefKeywordsOperator#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#8)]

<span data-ttu-id="7485a-110">In diesem Beispiel wird `BaseC.Invoke` durch `DerivedC.Invoke` ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="7485a-110">In this example, `BaseC.Invoke` is hidden by `DerivedC.Invoke`.</span></span> <span data-ttu-id="7485a-111">Der Vorgang wirkt sich nicht auf das Feld `x` aus, da es nicht mit einem ähnlichen Namen ausgeblendet wird.</span><span class="sxs-lookup"><span data-stu-id="7485a-111">The field `x` is not affected because it is not hidden by a similar name.</span></span>

<span data-ttu-id="7485a-112">Das Ausblenden des Namens durch Vererbung nimmt eine der folgenden Formen an:</span><span class="sxs-lookup"><span data-stu-id="7485a-112">Name hiding through inheritance takes one of the following forms:</span></span>

- <span data-ttu-id="7485a-113">Im Allgemeinen blendet eine Konstante, ein Feld, eine Eigenschaft oder einen Typ, der in einer Klasse oder Struktur eingegeben wird, alle Basisklassenmember aus, die den gleichen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="7485a-113">Generally, a constant, field, property, or type that is introduced in a class or struct hides all base class members that share its name.</span></span> <span data-ttu-id="7485a-114">Es werden bestimmte Fälle unterschieden.</span><span class="sxs-lookup"><span data-stu-id="7485a-114">There are special cases.</span></span> <span data-ttu-id="7485a-115">Wenn Sie beispielsweise ein neues Feld mit dem Namen `N` mit einem nicht aufrufbaren Typ deklarieren, und ein Basistyp deklariert `N` als Methode, blendet das neue Feld die Basisdeklaration nicht in der Aufrufsyntax aus.</span><span class="sxs-lookup"><span data-stu-id="7485a-115">For example, if you declare a new field with name `N` to have a type that is not invocable, and a base type declares `N` to be a method, the new field does not hide the base declaration in invocation syntax.</span></span> <span data-ttu-id="7485a-116">Weitere Informationen finden Sie im Abschnitt [Membersuchvorgänge](~/_csharplang/spec/expressions.md#member-lookup) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="7485a-116">For more information, see the [Member lookup](~/_csharplang/spec/expressions.md#member-lookup) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

- <span data-ttu-id="7485a-117">Durch eine Methode, die in eine Klasse oder Struktur eingeführt ist, werden Eigenschaften, Felder und Typen mit dem gleichen Namen in der Basisklasse ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="7485a-117">A method introduced in a class or struct hides properties, fields, and types that share that name in the base class.</span></span> <span data-ttu-id="7485a-118">Alle Basisklassenmethoden mit der gleichen Signatur werden ebenfalls ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="7485a-118">It also hides all base class methods that have the same signature.</span></span>

- <span data-ttu-id="7485a-119">Durch einen Indexer, der in einer Klasse oder Struktur eingeführt ist, werden alle Basisklassenindexer mit der gleichen Signatur ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="7485a-119">An indexer introduced in a class or struct hides all base class indexers that have the same signature.</span></span>

<span data-ttu-id="7485a-120">`new` und [override](override.md) dürfen nicht gleichzeitig auf denselben Member angewendet werden, da sich die Bedeutungen der beiden Modifizierer gegenseitig ausschließen.</span><span class="sxs-lookup"><span data-stu-id="7485a-120">It is an error to use both `new` and [override](override.md) on the same member, because the two modifiers have mutually exclusive meanings.</span></span> <span data-ttu-id="7485a-121">Mit dem `new`-Modifizierer wird ein neuer Member mit demselben Namen erstellt, und der ursprüngliche Member wird ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="7485a-121">The `new` modifier creates a new member with the same name and causes the original member to become hidden.</span></span> <span data-ttu-id="7485a-122">Der `override`-Modifizierer verlängert die Implementierung für einen geerbten Member.</span><span class="sxs-lookup"><span data-stu-id="7485a-122">The `override` modifier extends the implementation for an inherited member.</span></span>

<span data-ttu-id="7485a-123">Wenn der `new`-Modifizierer in einer Deklaration verwendet wird, in der kein geerbter Member ausgeblendet wird, wird eine Warnung generiert.</span><span class="sxs-lookup"><span data-stu-id="7485a-123">Using the `new` modifier in a declaration that does not hide an inherited member generates a warning.</span></span>

## <a name="example"></a><span data-ttu-id="7485a-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7485a-124">Example</span></span>

<span data-ttu-id="7485a-125">In diesem Beispiel wird von einer Basisklasse, `BaseC`, und einer abgeleiteten Klasse, `DerivedC`, der gleiche Feldname `x` verwendet. Auf diese Weise wird der Wert des geerbten Felds ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="7485a-125">In this example, a base class, `BaseC`, and a derived class, `DerivedC`, use the same field name `x`, which hides the value of the inherited field.</span></span> <span data-ttu-id="7485a-126">Im Beispiel wird die Verwendung des `new`-Modifizierers veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7485a-126">The example demonstrates the use of the `new` modifier.</span></span> <span data-ttu-id="7485a-127">Außerdem wird gezeigt, wie mit den voll qualifizierten Namen auf die ausgeblendeten Member der Basisklasse zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="7485a-127">It also demonstrates how to access the hidden members of the base class by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#9)]

## <a name="example"></a><span data-ttu-id="7485a-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7485a-128">Example</span></span>

<span data-ttu-id="7485a-129">In diesem Beispiel blendet eine geschachtelte Klasse eine Klasse mit dem gleichen Namen in der Basisklasse aus.</span><span class="sxs-lookup"><span data-stu-id="7485a-129">In this example, a nested class hides a class that has the same name in the base class.</span></span> <span data-ttu-id="7485a-130">Das Beispiel veranschaulicht, wie mit dem `new`-Modifizierer die Warnmeldung vermieden wird und wie mit den voll qualifizierten Namen auf die ausgeblendeten Klassenmember zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="7485a-130">The example demonstrates how to use the `new` modifier to eliminate the warning message and how to access the hidden class members by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#10)]

<span data-ttu-id="7485a-131">Wenn der `new`-Modifizierer entfernt wird, kann das Programm dennoch kompiliert und ausgeführt werden. Es wird jedoch folgende Warnung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="7485a-131">If you remove the `new` modifier, the program will still compile and run, but you will get the following warning:</span></span>

```text
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.
```

## <a name="c-language-specification"></a><span data-ttu-id="7485a-132">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="7485a-132">C# language specification</span></span>

<span data-ttu-id="7485a-133">Weitere Informationen finden Sie im Abschnitt [Der new-Modifizierer](~/_csharplang/spec/classes.md#the-new-modifier) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="7485a-133">For more information, see [The new modifier](~/_csharplang/spec/classes.md#the-new-modifier) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7485a-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7485a-134">See also</span></span>

- [<span data-ttu-id="7485a-135">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="7485a-135">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7485a-136">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7485a-136">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7485a-137">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="7485a-137">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="7485a-138">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="7485a-138">Modifiers</span></span>](index.md)
- [<span data-ttu-id="7485a-139">Versionsverwaltung mit den Schlüsselwörtern "override" und "new"</span><span class="sxs-lookup"><span data-stu-id="7485a-139">Versioning with the Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)
- [<span data-ttu-id="7485a-140">Wann müssen die Schlüsselwörter "override" und "new" verwendet werden?</span><span class="sxs-lookup"><span data-stu-id="7485a-140">Knowing When to Use Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)
