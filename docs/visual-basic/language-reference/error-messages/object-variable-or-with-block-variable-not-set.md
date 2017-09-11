---
title: Die Objektvariable oder With-Blockvariable wurde nicht festgelegt | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID91
dev_langs:
- VB
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4db2c827c3e77cfa6cc51132f0d647a58c93c769
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="object-variable-or-with-block-variable-not-set"></a><span data-ttu-id="113a4-102">Die Objektvariable oder die With-Blockvariable wurde nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="113a4-102">Object variable or With block variable not set</span></span>
<span data-ttu-id="113a4-103">Eine ungültige Objekt-Variable wird verwiesen.</span><span class="sxs-lookup"><span data-stu-id="113a4-103">An invalid object variable is being referenced.</span></span>   <span data-ttu-id="113a4-104">Dieser Fehler kann mehrere Ursachen haben:</span><span class="sxs-lookup"><span data-stu-id="113a4-104">This error can occur for several reasons:</span></span>  
  
-   <span data-ttu-id="113a4-105">Eine Variable wurde deklariert, ohne Angabe eines Typs.</span><span class="sxs-lookup"><span data-stu-id="113a4-105">A variable was declared without specifying a type.</span></span> <span data-ttu-id="113a4-106">Wenn eine Variable ohne Angabe eines Typs deklariert ist, wird standardmäßig zur Eingabe `Object`.</span><span class="sxs-lookup"><span data-stu-id="113a4-106">If a variable is declared without specifying a type, it defaults to type `Object`.</span></span>  
  
     <span data-ttu-id="113a4-107">Z. B. eine Variable mit `Dim x` vom Typ `Object;` eine Variable mit `Dim x As String` vom Typ `String`.</span><span class="sxs-lookup"><span data-stu-id="113a4-107">For example, a variable declared with `Dim x` would be of type `Object;` a variable declared with `Dim x As String` would be of type `String`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="113a4-108">Die `Option Strict` Anweisung lässt keine implizite Typisierung, bei denen ein `Object` Typ.</span><span class="sxs-lookup"><span data-stu-id="113a4-108">The `Option Strict` statement disallows implicit typing that results in an `Object` type.</span></span> <span data-ttu-id="113a4-109">Wenn Sie den Typ angeben, wird ein Kompilierungsfehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="113a4-109">If you omit the type, a compile-time error will occur.</span></span> <span data-ttu-id="113a4-110">Finden Sie unter [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="113a4-110">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
-   <span data-ttu-id="113a4-111">Sie versuchen, ein Objekt zu verweisen, die festgelegt wurde`Nothing`</span><span class="sxs-lookup"><span data-stu-id="113a4-111">You are attempting to reference an object that has been set to `Nothing`</span></span>  
  
     <span data-ttu-id="113a4-112">.</span><span class="sxs-lookup"><span data-stu-id="113a4-112">.</span></span>  
  
-   <span data-ttu-id="113a4-113">Sie versuchen, ein Element einer Arrayvariablen zuzugreifen, die ordnungsgemäß deklariert war nicht.</span><span class="sxs-lookup"><span data-stu-id="113a4-113">You are attempting to access an element of an array variable that wasn't properly declared.</span></span>  
  
     <span data-ttu-id="113a4-114">Zum Beispiel deklariert ein Array als `products() As String` den Fehler wird ausgelöst, wenn Sie versuchen, ein Element des Arrays verweisen `products(3) = "Widget"`.</span><span class="sxs-lookup"><span data-stu-id="113a4-114">For example, an array declared as `products() As String` will trigger the error if you try to reference an element of the array `products(3) = "Widget"`.</span></span> <span data-ttu-id="113a4-115">Das Array enthält keine Elemente und wird als Objekt behandelt.</span><span class="sxs-lookup"><span data-stu-id="113a4-115">The array has no elements and is treated as an object.</span></span>  
  
-   <span data-ttu-id="113a4-116">Sie versuchen, den Zugriff von Code innerhalb einer `With...End With` blockiert werden, bevor der Block initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="113a4-116">You are attempting to access code within a `With...End With` block before the block has been initialized.</span></span>   <span data-ttu-id="113a4-117">Ein `With...End With` Block muss initialisiert werden, durch Ausführen der `With` Anweisung Einstiegspunkt.</span><span class="sxs-lookup"><span data-stu-id="113a4-117">A `With...End With` block must be initialized by executing the `With` statement entry point.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="113a4-118">In früheren Versionen von Visual Basic oder VBA dieser Fehler auch durch Zuweisen eines Werts zu einer Variablen ohne ausgelöst wurde der `Set` Schlüsselwort (`x = "name"` anstelle von `Set x = "name"`).</span><span class="sxs-lookup"><span data-stu-id="113a4-118">In earlier versions of Visual Basic or VBA this error was also triggered by assigning a value to a variable without using the `Set` keyword (`x = "name"` instead of `Set x = "name"`).</span></span> <span data-ttu-id="113a4-119">Die `Set` Schlüsselwort ist nicht mehr gültig ist, in Visual Basic.NET.</span><span class="sxs-lookup"><span data-stu-id="113a4-119">The `Set` keyword is no longer valid in Visual Basic .Net.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="113a4-120">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="113a4-120">To correct this error</span></span>  
  
1.  <span data-ttu-id="113a4-121">Legen Sie `Option Strict` zu `On` durch den folgenden Code am Anfang der das Hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="113a4-121">Set `Option Strict` to `On` by adding the following code to the beginning of the file:</span></span>  
  
```vb  
Option Strict On  
```  

     When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.  
  
2.  <span data-ttu-id="113a4-122">Wenn Sie nicht aktivieren möchten `Option Strict`, suchen Sie den Code für alle Variablen, die ohne einen Typ angegeben wurden (`Dim x` anstelle von `Dim x As String`) und fügen Sie den gewünschten Typ der Deklaration.</span><span class="sxs-lookup"><span data-stu-id="113a4-122">If you don't want to enable `Option Strict`, search your code for any variables that were specified without a type (`Dim x` instead of `Dim x As String`) and add the intended type to the declaration.</span></span>  
  
3.  <span data-ttu-id="113a4-123">Sicherstellen, dass Sie einer Objektvariablen, die festgelegt wurde, verweisen werden nicht `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="113a4-123">Make sure you aren't referring to  an object variable that has been set to `Nothing`.</span></span>  <span data-ttu-id="113a4-124">Suchen Sie den Code für das Schlüsselwort `Nothing`, und Überarbeiten Sie Ihren Code so, dass das Objekt ist nicht auf `Nothing` erst nachdem Sie darauf verwiesen haben.</span><span class="sxs-lookup"><span data-stu-id="113a4-124">Search your code for the keyword `Nothing`, and revise your code so that the object isn't set to `Nothing` until after you have referenced it.</span></span>  
  
4.  <span data-ttu-id="113a4-125">Stellen Sie sicher, dass alle Arrayvariablen dimensioniert werden, bevor Sie darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="113a4-125">Make sure that any array  variables are dimensioned before you access them.</span></span> <span data-ttu-id="113a4-126">Sie können entweder eine Dimension zuweisen, beim Erstellen von Arrays (`Dim x(5) As String` anstelle von `Dim x() As String`), oder verwenden Sie die `ReDim` -Schlüsselwort verwenden, um die Dimensionen des Arrays festgelegt, bevor darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="113a4-126">You can either assign a dimension when you first create the array (`Dim x(5) As String` instead of `Dim x() As String`), or use the `ReDim` keyword to set the dimensions of the array before you first access it.</span></span>  
  
5.  <span data-ttu-id="113a4-127">Stellen Sie sicher, dass Ihre `With` Block wird initialisiert, indem die Ausführung der `With` Anweisung Einstiegspunkt.</span><span class="sxs-lookup"><span data-stu-id="113a4-127">Make sure your `With` block is initialized by executing the `With` statement entry point.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="113a4-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="113a4-128">See Also</span></span>  
 <span data-ttu-id="113a4-129">[Deklaration von Objektvariablen](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="113a4-129">[Object Variable Declaration](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span></span>  
<span data-ttu-id="113a4-130"> [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="113a4-130"> [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) </span></span>  
<span data-ttu-id="113a4-131"> [With...End With-Anweisung](../../../visual-basic/language-reference/statements/with-end-with-statement.md)</span><span class="sxs-lookup"><span data-stu-id="113a4-131"> [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md)</span></span>
