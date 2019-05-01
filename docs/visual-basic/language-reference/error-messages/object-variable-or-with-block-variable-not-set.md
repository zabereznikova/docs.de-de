---
title: Die Objektvariable oder die With-Blockvariable wurde nicht festgelegt.
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: 766b95163f164ec76135b964115069b6855ceebf
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "63807871"
---
# <a name="object-variable-or-with-block-variable-not-set"></a><span data-ttu-id="e4d1c-102">Die Objektvariable oder die With-Blockvariable wurde nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-102">Object variable or With block variable not set</span></span>
<span data-ttu-id="e4d1c-103">Eine ungültiges Objekt-Variable wird verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-103">An invalid object variable is being referenced.</span></span>   <span data-ttu-id="e4d1c-104">Dieser Fehler kann mehrere Ursachen haben:</span><span class="sxs-lookup"><span data-stu-id="e4d1c-104">This error can occur for several reasons:</span></span>

- <span data-ttu-id="e4d1c-105">Eine Variable wurde deklariert, ohne Angabe eines Typs.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-105">A variable was declared without specifying a type.</span></span> <span data-ttu-id="e4d1c-106">Wenn eine Variable ohne Angabe eines Typs deklariert ist, wird standardmäßig Typ `Object`.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-106">If a variable is declared without specifying a type, it defaults to type `Object`.</span></span>

    <span data-ttu-id="e4d1c-107">Z. B. eine Variable mit `Dim x` vom Typ `Object;` eine Variable mit `Dim x As String` vom Typ `String`.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-107">For example, a variable declared with `Dim x` would be of type `Object;` a variable declared with `Dim x As String` would be of type `String`.</span></span>

    > [!TIP]
    >  <span data-ttu-id="e4d1c-108">Die `Option Strict` Anweisung lässt keine impliziten Typisierung der Ergebnisse in eine `Object` Typ.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-108">The `Option Strict` statement disallows implicit typing that results in an `Object` type.</span></span> <span data-ttu-id="e4d1c-109">Wenn Sie den Typ weglassen, wird ein Fehler während der Kompilierung auftreten.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-109">If you omit the type, a compile-time error will occur.</span></span> <span data-ttu-id="e4d1c-110">Finden Sie unter [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e4d1c-110">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>

- <span data-ttu-id="e4d1c-111">Sie versuchen, ein Objekt zu verweisen, die festgelegt wurde, `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-111">You are attempting to reference an object that has been set to `Nothing`.</span></span>

- <span data-ttu-id="e4d1c-112">Sie versuchen, ein Element eine Array-Variable zuzugreifen, die ordnungsgemäß deklariert war nicht.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-112">You are attempting to access an element of an array variable that wasn't properly declared.</span></span>

    <span data-ttu-id="e4d1c-113">Zum Beispiel ein Array deklariert als `products() As String` den Fehler wird ausgelöst, wenn Sie versuchen, ein Element des Arrays verweisen `products(3) = "Widget"`.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-113">For example, an array declared as `products() As String` will trigger the error if you try to reference an element of the array `products(3) = "Widget"`.</span></span> <span data-ttu-id="e4d1c-114">Das Array verfügt über keine Elemente und wird als Objekt behandelt.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-114">The array has no elements and is treated as an object.</span></span>

- <span data-ttu-id="e4d1c-115">Sie versuchen, den Zugriff von Code in einem `With...End With` zu blockieren, bevor der Block initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-115">You are attempting to access code within a `With...End With` block before the block has been initialized.</span></span>   <span data-ttu-id="e4d1c-116">Ein `With...End With` Block muss initialisiert werden, indem Sie Ausführung der `With` Einstiegspunkt für die Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-116">A `With...End With` block must be initialized by executing the `With` statement entry point.</span></span>

> [!NOTE]
> <span data-ttu-id="e4d1c-117">In früheren Versionen von Visual Basic oder VBA wurde dieser Fehler auch durch Zuweisen eines Werts einer Variablen ohne Verwendung von ausgelöst der `Set` Schlüsselwort (`x = "name"` anstelle von `Set x = "name"`).</span><span class="sxs-lookup"><span data-stu-id="e4d1c-117">In earlier versions of Visual Basic or VBA this error was also triggered by assigning a value to a variable without using the `Set` keyword (`x = "name"` instead of `Set x = "name"`).</span></span> <span data-ttu-id="e4d1c-118">Die `Set` Schlüsselwort ist nicht mehr in Visual Basic.NET gültig.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-118">The `Set` keyword is no longer valid in Visual Basic .Net.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="e4d1c-119">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="e4d1c-119">To correct this error</span></span>

1. <span data-ttu-id="e4d1c-120">Legen Sie `Option Strict` zu `On` durch den folgenden Code am Anfang der das Hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="e4d1c-120">Set `Option Strict` to `On` by adding the following code to the beginning of the file:</span></span>

    ```vb
    Option Strict On
    ```

    <span data-ttu-id="e4d1c-121">Wenn Sie das Projekt ausführen, wird ein Compilerfehler angezeigt, der **Fehlerliste** für jede Variable, die ohne einen Typ angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-121">When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.</span></span>

2. <span data-ttu-id="e4d1c-122">Wenn Sie nicht aktivieren möchten `Option Strict`, Durchsuchen Ihres gesamten Codes für alle Variablen, die ohne einen Typ angegeben wurden (`Dim x` anstelle von `Dim x As String`), und fügen Sie der Deklaration der gewünschte Typ hinzu.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-122">If you don't want to enable `Option Strict`, search your code for any variables that were specified without a type (`Dim x` instead of `Dim x As String`) and add the intended type to the declaration.</span></span>

3. <span data-ttu-id="e4d1c-123">Stellen Sie sicher, dass Sie einer Objektvariablen, die festgelegt wurde, verweisen sind nicht `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-123">Make sure you aren't referring to  an object variable that has been set to `Nothing`.</span></span>  <span data-ttu-id="e4d1c-124">Suchen Sie Ihren Code für das Schlüsselwort `Nothing`, und Ihren Code so überarbeiten, dass das Objekt, dass festgelegt wurde `Nothing` erst nach dem Sie darauf verwiesen haben.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-124">Search your code for the keyword `Nothing`, and revise your code so that the object isn't set to `Nothing` until after you have referenced it.</span></span>

4. <span data-ttu-id="e4d1c-125">Stellen Sie sicher, dass alle Arrayvariablen, die dimensioniert werden, bevor Sie darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-125">Make sure that any array  variables are dimensioned before you access them.</span></span> <span data-ttu-id="e4d1c-126">Sie können entweder eine Dimension zuweisen, wenn Sie das Array erstellen (`Dim x(5) As String` anstelle von `Dim x() As String`), oder verwenden Sie die `ReDim` Schlüsselwort, um die Dimensionen des Arrays festgelegt, bevor Sie zuerst darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-126">You can either assign a dimension when you first create the array (`Dim x(5) As String` instead of `Dim x() As String`), or use the `ReDim` keyword to set the dimensions of the array before you first access it.</span></span>

5. <span data-ttu-id="e4d1c-127">Stellen Sie sicher, dass Ihre `With` Block wird initialisiert, indem Sie Ausführung der `With` Einstiegspunkt für die Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e4d1c-127">Make sure your `With` block is initialized by executing the `With` statement entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4d1c-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4d1c-128">See also</span></span>

- [<span data-ttu-id="e4d1c-129">Deklaration von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="e4d1c-129">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="e4d1c-130">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e4d1c-130">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="e4d1c-131">With...End With-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e4d1c-131">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
