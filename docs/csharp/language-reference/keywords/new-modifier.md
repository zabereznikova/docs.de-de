---
title: new-Modifizierer – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
ms.openlocfilehash: d5fd244ea22fd48bf5b81d2cdf55127f745c145b
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835017"
---
# <a name="new-modifier-c-reference"></a><span data-ttu-id="dbca7-102">new-Modifizierer (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="dbca7-102">new modifier (C# Reference)</span></span>

<span data-ttu-id="dbca7-103">Wenn das Schlüsselwort `new` als Deklarationsmodifizierer verwendet wird, blendet es explizit einen von einer Basisklasse geerbten Member aus.</span><span class="sxs-lookup"><span data-stu-id="dbca7-103">When used as a declaration modifier, the `new` keyword explicitly hides a member that is inherited from a base class.</span></span> <span data-ttu-id="dbca7-104">Wenn Sie einen geerbten Member ausblenden, ersetzt die abgeleitete Version des Members die Basisklassenversion.</span><span class="sxs-lookup"><span data-stu-id="dbca7-104">When you hide an inherited member, the derived version of the member replaces the base class version.</span></span> <span data-ttu-id="dbca7-105">Obwohl Sie Member verdecken können, ohne den `new`-Modifizierer zu verwenden, wird eine Compilerwarnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dbca7-105">Although you can hide members without using the `new` modifier, you get a compiler warning.</span></span> <span data-ttu-id="dbca7-106">Wenn Sie `new` verwenden, um einen Member explizit auszublenden, wird diese Warnung unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="dbca7-106">If you use `new` to explicitly hide a member, it suppresses this warning.</span></span>

<span data-ttu-id="dbca7-107">Um einen geerbten Member auszublenden, deklarieren Sie ihn mit demselben Membernamen in der abgeleiteten Klasse und ändern ihn mit dem `new`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="dbca7-107">To hide an inherited member, declare it in the derived class by using the same member name, and modify it with the `new` keyword.</span></span> <span data-ttu-id="dbca7-108">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="dbca7-108">For example:</span></span>

[!code-csharp[csrefKeywordsOperator#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#8)]

<span data-ttu-id="dbca7-109">In diesem Beispiel wird `BaseC.Invoke` durch `DerivedC.Invoke` ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="dbca7-109">In this example, `BaseC.Invoke` is hidden by `DerivedC.Invoke`.</span></span> <span data-ttu-id="dbca7-110">Der Vorgang wirkt sich nicht auf das Feld `x` aus, da es nicht mit einem ähnlichen Namen ausgeblendet wird.</span><span class="sxs-lookup"><span data-stu-id="dbca7-110">The field `x` is not affected because it is not hidden by a similar name.</span></span>

<span data-ttu-id="dbca7-111">Das Ausblenden des Namens durch Vererbung nimmt eine der folgenden Formen an:</span><span class="sxs-lookup"><span data-stu-id="dbca7-111">Name hiding through inheritance takes one of the following forms:</span></span>

- <span data-ttu-id="dbca7-112">Im Allgemeinen blendet eine Konstante, ein Feld, eine Eigenschaft oder einen Typ, der in einer Klasse oder Struktur eingegeben wird, alle Basisklassenmember aus, die den gleichen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="dbca7-112">Generally, a constant, field, property, or type that is introduced in a class or struct hides all base class members that share its name.</span></span>  <span data-ttu-id="dbca7-113">Es werden bestimmte Fälle unterschieden.</span><span class="sxs-lookup"><span data-stu-id="dbca7-113">There are special cases.</span></span>  <span data-ttu-id="dbca7-114">Wenn Sie beispielsweise ein neues Feld mit dem Namen `N` mit einem nicht aufrufbaren Typ deklarieren, und ein Basistyp deklariert `N` als Methode, blendet das neue Feld die Basisdeklaration nicht in der Aufrufsyntax aus.</span><span class="sxs-lookup"><span data-stu-id="dbca7-114">For example, if you declare a new field with name `N` to have a type that is not invocable, and a base type declares `N` to be a method, the new field does not hide the base declaration in invocation syntax.</span></span>  <span data-ttu-id="dbca7-115">Weitere Informationen finden Sie unter [C# 5.0-Sprachspezifikation](https://www.microsoft.com/download/details.aspx?id=7029) (siehe Abschnitt „Suche nach Membern“ im Abschnitt „Ausdrücke“).</span><span class="sxs-lookup"><span data-stu-id="dbca7-115">See the [C# 5.0 language specification](https://www.microsoft.com/download/details.aspx?id=7029) for details (see section "Member Lookup" in section "Expressions").</span></span>

- <span data-ttu-id="dbca7-116">Durch eine Methode, die in eine Klasse oder Struktur eingeführt ist, werden Eigenschaften, Felder und Typen mit dem gleichen Namen in der Basisklasse ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="dbca7-116">A method introduced in a class or struct hides properties, fields, and types that share that name in the base class.</span></span> <span data-ttu-id="dbca7-117">Alle Basisklassenmethoden mit der gleichen Signatur werden ebenfalls ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="dbca7-117">It also hides all base class methods that have the same signature.</span></span>

- <span data-ttu-id="dbca7-118">Durch einen Indexer, der in einer Klasse oder Struktur eingeführt ist, werden alle Basisklassenindexer mit der gleichen Signatur ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="dbca7-118">An indexer introduced in a class or struct hides all base class indexers that have the same signature.</span></span>

<span data-ttu-id="dbca7-119">`new` und [override](override.md) dürfen nicht gleichzeitig auf denselben Member angewendet werden, da sich die Bedeutungen der beiden Modifizierer gegenseitig ausschließen.</span><span class="sxs-lookup"><span data-stu-id="dbca7-119">It is an error to use both `new` and [override](override.md) on the same member, because the two modifiers have mutually exclusive meanings.</span></span> <span data-ttu-id="dbca7-120">Mit dem `new`-Modifizierer wird ein neuer Member mit demselben Namen erstellt, und der ursprüngliche Member wird ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="dbca7-120">The `new` modifier creates a new member with the same name and causes the original member to become hidden.</span></span> <span data-ttu-id="dbca7-121">Der `override`-Modifizierer verlängert die Implementierung für einen geerbten Member.</span><span class="sxs-lookup"><span data-stu-id="dbca7-121">The `override` modifier extends the implementation for an inherited member.</span></span>

<span data-ttu-id="dbca7-122">Wenn der `new`-Modifizierer in einer Deklaration verwendet wird, in der kein geerbter Member ausgeblendet wird, wird eine Warnung generiert.</span><span class="sxs-lookup"><span data-stu-id="dbca7-122">Using the `new` modifier in a declaration that does not hide an inherited member generates a warning.</span></span>

## <a name="example"></a><span data-ttu-id="dbca7-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dbca7-123">Example</span></span>

<span data-ttu-id="dbca7-124">In diesem Beispiel wird von einer Basisklasse, `BaseC`, und einer abgeleiteten Klasse, `DerivedC`, der gleiche Feldname `x` verwendet. Auf diese Weise wird der Wert des geerbten Felds ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="dbca7-124">In this example, a base class, `BaseC`, and a derived class, `DerivedC`, use the same field name `x`, which hides the value of the inherited field.</span></span> <span data-ttu-id="dbca7-125">Im Beispiel wird die Verwendung des `new`-Modifizierers veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="dbca7-125">The example demonstrates the use of the `new` modifier.</span></span> <span data-ttu-id="dbca7-126">Außerdem wird gezeigt, wie mit den voll qualifizierten Namen auf die ausgeblendeten Member der Basisklasse zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="dbca7-126">It also demonstrates how to access the hidden members of the base class by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#9)]

## <a name="example"></a><span data-ttu-id="dbca7-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dbca7-127">Example</span></span>

<span data-ttu-id="dbca7-128">In diesem Beispiel blendet eine geschachtelte Klasse eine Klasse mit dem gleichen Namen in der Basisklasse aus.</span><span class="sxs-lookup"><span data-stu-id="dbca7-128">In this example, a nested class hides a class that has the same name in the base class.</span></span> <span data-ttu-id="dbca7-129">Das Beispiel veranschaulicht, wie mit dem `new`-Modifizierer die Warnmeldung vermieden wird und wie mit den voll qualifizierten Namen auf die ausgeblendeten Klassenmember zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="dbca7-129">The example demonstrates how to use the `new` modifier to eliminate the warning message and how to access the hidden class members by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#10)]

<span data-ttu-id="dbca7-130">Wenn der `new`-Modifizierer entfernt wird, kann das Programm dennoch kompiliert und ausgeführt werden. Es wird jedoch folgende Warnung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="dbca7-130">If you remove the `new` modifier, the program will still compile and run, but you will get the following warning:</span></span>

```
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.
```

## <a name="c-language-specification"></a><span data-ttu-id="dbca7-131">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="dbca7-131">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="dbca7-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbca7-132">See also</span></span>

- [<span data-ttu-id="dbca7-133">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="dbca7-133">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="dbca7-134">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="dbca7-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="dbca7-135">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="dbca7-135">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="dbca7-136">Operatorschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="dbca7-136">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="dbca7-137">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="dbca7-137">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="dbca7-138">Versionsverwaltung mit den Schlüsselwörtern "override" und "new"</span><span class="sxs-lookup"><span data-stu-id="dbca7-138">Versioning with the Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)
- [<span data-ttu-id="dbca7-139">Wann müssen die Schlüsselwörter "override" und "new" verwendet werden?</span><span class="sxs-lookup"><span data-stu-id="dbca7-139">Knowing When to Use Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)
