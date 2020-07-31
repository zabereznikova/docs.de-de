---
title: Übergeben von Arrays als Argumente – C#-Programmierhandbuch
description: Arrays in C# können als Argumente an Methodenparameter übergeben werden. Da es sich bei Arrays um Verweistypen handelt, kann die Methode den Wert der Elemente ändern.
ms.date: 07/05/2018
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: 68f174421e56e2cf082fe670f93c4f6627d7c17b
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474630"
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="20d7d-104">Übergeben von Arrays als Argumente (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="20d7d-104">Passing arrays as arguments (C# Programming Guide)</span></span>

<span data-ttu-id="20d7d-105">Arrays können als Argumente an Methodenparameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="20d7d-105">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="20d7d-106">Da es sich bei Arrays um Verweistypen handelt, kann die Methode den Wert der Elemente ändern.</span><span class="sxs-lookup"><span data-stu-id="20d7d-106">Because arrays are reference types, the method can change the value of the elements.</span></span>

## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="20d7d-107">Übergeben von eindimensionalen Arrays als Argumente</span><span class="sxs-lookup"><span data-stu-id="20d7d-107">Passing single-dimensional arrays as arguments</span></span>

<span data-ttu-id="20d7d-108">Sie können ein initialisiertes eindimensionales Array an eine Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="20d7d-108">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="20d7d-109">Die folgende Anweisung sendet z.B. ein Array an eine print-Methode.</span><span class="sxs-lookup"><span data-stu-id="20d7d-109">For example, the following statement sends an array to a print method.</span></span>

[!code-csharp[csProgGuideArrays#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#34)]

<span data-ttu-id="20d7d-110">Im folgenden Code wird eine partielle Implementierung der print-Methode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="20d7d-110">The following code shows a partial implementation of the print method.</span></span>

[!code-csharp[csProgGuideArrays#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#33)]

<span data-ttu-id="20d7d-111">Sie können einen neuen Array in einem Schritt initialisieren und übergeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="20d7d-111">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>

[!code-csharp[CsProgGuideArrays#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#35)]

### <a name="example"></a><span data-ttu-id="20d7d-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="20d7d-112">Example</span></span>

<span data-ttu-id="20d7d-113">Im folgenden Beispiel wird ein Array von Zeichenfolgen initialisiert und als Argument an eine `DisplayArray`-Methode für Zeichenfolgen übergeben.</span><span class="sxs-lookup"><span data-stu-id="20d7d-113">In the following example, an array of strings is initialized and passed as an argument to a `DisplayArray` method for strings.</span></span> <span data-ttu-id="20d7d-114">Die Methode zeigt die Elemente des Arrays an.</span><span class="sxs-lookup"><span data-stu-id="20d7d-114">The method displays the elements of the array.</span></span> <span data-ttu-id="20d7d-115">Als Nächstes kehrt die `ChangeArray`-Methode die Elemente des Arrays um, und die `ChangeArrayElements`-Methode ändert die ersten drei Elemente des Arrays.</span><span class="sxs-lookup"><span data-stu-id="20d7d-115">Next, the `ChangeArray` method reverses the array elements, and then the `ChangeArrayElements` method modifies the first three elements of the array.</span></span> <span data-ttu-id="20d7d-116">Nachdem jede Methode zurückgegeben wird, zeigt die `DisplayArray`-Methode an, dass das Übergeben eines Arrays nach Wert keine Änderungen an den Arrayelementen verhindert.</span><span class="sxs-lookup"><span data-stu-id="20d7d-116">After each method returns, the `DisplayArray` method shows that passing an array by value doesn't prevent changes to the array elements.</span></span>

[!code-csharp[csProgGuideArrays#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/ArrayExample.cs)]

## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="20d7d-117">Übergeben von mehrdimensionalen Arrays als Argumente</span><span class="sxs-lookup"><span data-stu-id="20d7d-117">Passing multidimensional arrays as arguments</span></span>

<span data-ttu-id="20d7d-118">Sie können ein initialisiertes mehrdimensionales Array genauso wie Sie ein eindimensionales Array an eine Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="20d7d-118">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>

[!code-csharp[csProgGuideArrays#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#41)]

<span data-ttu-id="20d7d-119">Der folgende Code zeigt eine partielle Deklaration einer print-Methode, die ein zweidimensionales Array als Argument akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="20d7d-119">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>

[!code-csharp[csProgGuideArrays#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#36)]

<span data-ttu-id="20d7d-120">Wie im folgenden Beispiel dargestellt können Sie ein Array in einem Schritt initialisieren und übergeben.</span><span class="sxs-lookup"><span data-stu-id="20d7d-120">You can initialize and pass a new array in one step, as is shown in the following example:</span></span>

[!code-csharp[csProgGuideArrays#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#32)]

### <a name="example"></a><span data-ttu-id="20d7d-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="20d7d-121">Example</span></span>

<span data-ttu-id="20d7d-122">Im folgenden Beispiel wird ein zweidimensionales Array von ganzen Zahlen initialisiert und an die `Print2DArray`-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="20d7d-122">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="20d7d-123">Die Methode zeigt die Elemente des Arrays an.</span><span class="sxs-lookup"><span data-stu-id="20d7d-123">The method displays the elements of the array.</span></span>

[!code-csharp[csProgGuideArrays#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#31)]

## <a name="see-also"></a><span data-ttu-id="20d7d-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20d7d-124">See also</span></span>

- [<span data-ttu-id="20d7d-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="20d7d-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="20d7d-126">Arrays</span><span class="sxs-lookup"><span data-stu-id="20d7d-126">Arrays</span></span>](index.md)
- [<span data-ttu-id="20d7d-127">Eindimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="20d7d-127">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="20d7d-128">Mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="20d7d-128">Multidimensional Arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="20d7d-129">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="20d7d-129">Jagged Arrays</span></span>](jagged-arrays.md)
