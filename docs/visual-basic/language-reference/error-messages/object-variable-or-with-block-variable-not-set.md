---
title: Die Objektvariable oder die With-Blockvariable wurde nicht festgelegt.
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: 07c215d373e4ac1cbadf82a48b8cb3d90efdbdb4
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040561"
---
# <a name="object-variable-or-with-block-variable-not-set"></a><span data-ttu-id="d3eeb-102">Die Objektvariable oder die With-Blockvariable wurde nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-102">Object variable or With block variable not set</span></span>
<span data-ttu-id="d3eeb-103">Es wird auf eine ungültige Objekt Variable verwiesen.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-103">An invalid object variable is being referenced.</span></span>   <span data-ttu-id="d3eeb-104">Dieser Fehler kann mehrere Ursachen haben:</span><span class="sxs-lookup"><span data-stu-id="d3eeb-104">This error can occur for several reasons:</span></span>

- <span data-ttu-id="d3eeb-105">Eine Variable wurde ohne Angabe eines Typs deklariert.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-105">A variable was declared without specifying a type.</span></span> <span data-ttu-id="d3eeb-106">Wenn eine Variable ohne Angabe eines Typs deklariert wird, wird standardmäßig der `Object`Typ verwendet.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-106">If a variable is declared without specifying a type, it defaults to type `Object`.</span></span>

    <span data-ttu-id="d3eeb-107">Beispielsweise ist eine Variable, die `Dim x` mit deklariert wird, `Object;` vom Typ. eine `Dim x As String` Variable, die mit `String`deklariert wurde, ist vom Typ.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-107">For example, a variable declared with `Dim x` would be of type `Object;` a variable declared with `Dim x As String` would be of type `String`.</span></span>

    > [!TIP]
    > <span data-ttu-id="d3eeb-108">Die `Option Strict` -Anweisung lässt die implizite Typisierung nicht zu `Object` , die zu einem-Typ führt.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-108">The `Option Strict` statement disallows implicit typing that results in an `Object` type.</span></span> <span data-ttu-id="d3eeb-109">Wenn Sie den Typ weglassen, tritt ein Kompilierzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-109">If you omit the type, a compile-time error will occur.</span></span> <span data-ttu-id="d3eeb-110">Siehe [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d3eeb-110">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>

- <span data-ttu-id="d3eeb-111">Sie versuchen, auf ein Objekt zu verweisen, das auf `Nothing`festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-111">You are attempting to reference an object that has been set to `Nothing`.</span></span>

- <span data-ttu-id="d3eeb-112">Sie versuchen, auf ein Element einer Array Variablen zuzugreifen, die nicht ordnungsgemäß deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-112">You are attempting to access an element of an array variable that wasn't properly declared.</span></span>

    <span data-ttu-id="d3eeb-113">Beispielsweise löst ein als `products() As String` deklariertes Array den Fehler aus, wenn Sie versuchen, auf ein Element des Arrays `products(3) = "Widget"`zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-113">For example, an array declared as `products() As String` will trigger the error if you try to reference an element of the array `products(3) = "Widget"`.</span></span> <span data-ttu-id="d3eeb-114">Das Array hat keine Elemente und wird als Objekt behandelt.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-114">The array has no elements and is treated as an object.</span></span>

- <span data-ttu-id="d3eeb-115">Sie versuchen, auf Code innerhalb eines `With...End With` -Blocks zuzugreifen, bevor der-Block initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-115">You are attempting to access code within a `With...End With` block before the block has been initialized.</span></span>   <span data-ttu-id="d3eeb-116">Ein `With...End With` -Block muss initialisiert werden, indem `With` der Anweisungs Einstiegspunkt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-116">A `With...End With` block must be initialized by executing the `With` statement entry point.</span></span>

> [!NOTE]
> <span data-ttu-id="d3eeb-117">In früheren Versionen von Visual Basic oder VBA wurde dieser Fehler auch durch Zuweisen eines Werts zu einer Variablen ausgelöst, ohne das `Set` -Schlüssel`x = "name"` Wort ( `Set x = "name"`anstelle von) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-117">In earlier versions of Visual Basic or VBA this error was also triggered by assigning a value to a variable without using the `Set` keyword (`x = "name"` instead of `Set x = "name"`).</span></span> <span data-ttu-id="d3eeb-118">Das `Set` Schlüsselwort ist in Visual Basic .net nicht mehr gültig.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-118">The `Set` keyword is no longer valid in Visual Basic .Net.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d3eeb-119">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d3eeb-119">To correct this error</span></span>

1. <span data-ttu-id="d3eeb-120">Legen `Option Strict` Sie `On` auf fest, indem Sie am Anfang der Datei den folgenden Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="d3eeb-120">Set `Option Strict` to `On` by adding the following code to the beginning of the file:</span></span>

    ```vb
    Option Strict On
    ```

    <span data-ttu-id="d3eeb-121">Wenn Sie das Projekt ausführen, wird ein Compilerfehler im **Fehlerliste** für jede Variable angezeigt, die ohne Typ angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-121">When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.</span></span>

2. <span data-ttu-id="d3eeb-122">Wenn Sie nicht aktivieren `Option Strict`möchten, Durchsuchen Sie den Code nach allen Variablen, die ohne einen Typ (`Dim x` anstelle von `Dim x As String`) angegeben wurden, und fügen Sie den vorgesehenen Typ der Deklaration hinzu.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-122">If you don't want to enable `Option Strict`, search your code for any variables that were specified without a type (`Dim x` instead of `Dim x As String`) and add the intended type to the declaration.</span></span>

3. <span data-ttu-id="d3eeb-123">Stellen Sie sicher, dass Sie nicht auf eine Objekt Variable verweisen, die `Nothing`auf festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-123">Make sure you aren't referring to  an object variable that has been set to `Nothing`.</span></span>  <span data-ttu-id="d3eeb-124">Durchsuchen Sie den Code nach `Nothing`dem Schlüsselwort, und überarbeiten Sie den Code so, `Nothing` dass das Objekt nicht auf festgelegt ist, bis Sie darauf verwiesen haben.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-124">Search your code for the keyword `Nothing`, and revise your code so that the object isn't set to `Nothing` until after you have referenced it.</span></span>

4. <span data-ttu-id="d3eeb-125">Stellen Sie sicher, dass alle Array Variablen dimensioniert sind, bevor Sie darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-125">Make sure that any array  variables are dimensioned before you access them.</span></span> <span data-ttu-id="d3eeb-126">Sie können entweder eine Dimension zuweisen, wenn Sie das Array erstmalig erstellen `Dim x() As String`(`Dim x(5) As String` anstelle von), `ReDim` oder das-Schlüsselwort verwenden, um die Dimensionen des Arrays vor dem ersten Zugriff festzulegen.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-126">You can either assign a dimension when you first create the array (`Dim x(5) As String` instead of `Dim x() As String`), or use the `ReDim` keyword to set the dimensions of the array before you first access it.</span></span>

5. <span data-ttu-id="d3eeb-127">Stellen Sie sicher `With` , dass der Block initialisiert wird `With` , indem Sie den Anweisungs Einstiegspunkt ausführen.</span><span class="sxs-lookup"><span data-stu-id="d3eeb-127">Make sure your `With` block is initialized by executing the `With` statement entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3eeb-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3eeb-128">See also</span></span>

- [<span data-ttu-id="d3eeb-129">Deklaration von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="d3eeb-129">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="d3eeb-130">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d3eeb-130">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="d3eeb-131">With...End With-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d3eeb-131">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
