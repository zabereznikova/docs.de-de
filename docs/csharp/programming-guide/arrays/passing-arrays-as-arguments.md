---
title: Übergeben von Arrays als Argumente – C#-Programmierhandbuch
ms.date: 07/05/2018
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: 2e53008910a9062ada25680eb4b8e54a225fd226
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705690"
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="3be43-102">Übergeben von Arrays als Argumente (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="3be43-102">Passing arrays as arguments (C# Programming Guide)</span></span>

<span data-ttu-id="3be43-103">Arrays können als Argumente an Methodenparameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="3be43-103">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="3be43-104">Da es sich bei Arrays um Verweistypen handelt, kann die Methode den Wert der Elemente ändern.</span><span class="sxs-lookup"><span data-stu-id="3be43-104">Because arrays are reference types, the method can change the value of the elements.</span></span>

## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="3be43-105">Übergeben von eindimensionalen Arrays als Argumente</span><span class="sxs-lookup"><span data-stu-id="3be43-105">Passing single-dimensional arrays as arguments</span></span>

<span data-ttu-id="3be43-106">Sie können ein initialisiertes eindimensionales Array an eine Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="3be43-106">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="3be43-107">Die folgende Anweisung sendet z.B. ein Array an eine print-Methode.</span><span class="sxs-lookup"><span data-stu-id="3be43-107">For example, the following statement sends an array to a print method.</span></span>

[!code-csharp[csProgGuideArrays#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#34)]

<span data-ttu-id="3be43-108">Im folgenden Code wird eine partielle Implementierung der print-Methode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3be43-108">The following code shows a partial implementation of the print method.</span></span>

[!code-csharp[csProgGuideArrays#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#33)]

<span data-ttu-id="3be43-109">Sie können einen neuen Array in einem Schritt initialisieren und übergeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3be43-109">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>

[!code-csharp[CsProgGuideArrays#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#35)]

### <a name="example"></a><span data-ttu-id="3be43-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3be43-110">Example</span></span>

<span data-ttu-id="3be43-111">Im folgenden Beispiel wird ein Array von Zeichenfolgen initialisiert und als Argument an eine `DisplayArray`-Methode für Zeichenfolgen übergeben.</span><span class="sxs-lookup"><span data-stu-id="3be43-111">In the following example, an array of strings is initialized and passed as an argument to a `DisplayArray` method for strings.</span></span> <span data-ttu-id="3be43-112">Die Methode zeigt die Elemente des Arrays an.</span><span class="sxs-lookup"><span data-stu-id="3be43-112">The method displays the elements of the array.</span></span> <span data-ttu-id="3be43-113">Als Nächstes kehrt die `ChangeArray`-Methode die Elemente des Arrays um, und die `ChangeArrayElements`-Methode ändert die ersten drei Elemente des Arrays.</span><span class="sxs-lookup"><span data-stu-id="3be43-113">Next, the `ChangeArray` method reverses the array elements, and then the `ChangeArrayElements` method modifies the first three elements of the array.</span></span> <span data-ttu-id="3be43-114">Nachdem jede Methode zurückgegeben wird, zeigt die `DisplayArray`-Methode an, dass das Übergeben eines Arrays nach Wert keine Änderungen an den Arrayelementen verhindert.</span><span class="sxs-lookup"><span data-stu-id="3be43-114">After each method returns, the `DisplayArray` method shows that passing an array by value doesn't prevent changes to the array elements.</span></span>

[!code-csharp[csProgGuideArrays#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/ArrayExample.cs)]

## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="3be43-115">Übergeben von mehrdimensionalen Arrays als Argumente</span><span class="sxs-lookup"><span data-stu-id="3be43-115">Passing multidimensional arrays as arguments</span></span>

<span data-ttu-id="3be43-116">Sie können ein initialisiertes mehrdimensionales Array genauso wie Sie ein eindimensionales Array an eine Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="3be43-116">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>

[!code-csharp[csProgGuideArrays#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#41)]

<span data-ttu-id="3be43-117">Der folgende Code zeigt eine partielle Deklaration einer print-Methode, die ein zweidimensionales Array als Argument akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="3be43-117">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>

[!code-csharp[csProgGuideArrays#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#36)]

<span data-ttu-id="3be43-118">Wie im folgenden Beispiel dargestellt können Sie ein Array in einem Schritt initialisieren und übergeben.</span><span class="sxs-lookup"><span data-stu-id="3be43-118">You can initialize and pass a new array in one step, as is shown in the following example:</span></span>

[!code-csharp[csProgGuideArrays#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#32)]

### <a name="example"></a><span data-ttu-id="3be43-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3be43-119">Example</span></span>

<span data-ttu-id="3be43-120">Im folgenden Beispiel wird ein zweidimensionales Array von ganzen Zahlen initialisiert und an die `Print2DArray`-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="3be43-120">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="3be43-121">Die Methode zeigt die Elemente des Arrays an.</span><span class="sxs-lookup"><span data-stu-id="3be43-121">The method displays the elements of the array.</span></span>

[!code-csharp[csProgGuideArrays#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#31)]

## <a name="see-also"></a><span data-ttu-id="3be43-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3be43-122">See also</span></span>

- [<span data-ttu-id="3be43-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3be43-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3be43-124">Arrays</span><span class="sxs-lookup"><span data-stu-id="3be43-124">Arrays</span></span>](index.md)
- [<span data-ttu-id="3be43-125">Eindimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="3be43-125">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="3be43-126">Mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="3be43-126">Multidimensional Arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="3be43-127">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="3be43-127">Jagged Arrays</span></span>](jagged-arrays.md)
