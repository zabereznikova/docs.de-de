---
title: Übergeben von Arrays als Argumente (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: d863cdc33a8a1a844aabbea9ba5876614e6e8dba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="b0239-102">Übergeben von Arrays als Argumente (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b0239-102">Passing Arrays as Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="b0239-103">Arrays können als Argumente an Methodenparameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="b0239-103">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="b0239-104">Da es sich bei Arrays um Verweistypen handelt, kann die Methode den Wert der Elemente ändern.</span><span class="sxs-lookup"><span data-stu-id="b0239-104">Because arrays are reference types, the method can change the value of the elements.</span></span>  
  
## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="b0239-105">Übergeben von eindimensionalen Arrays als Argumente</span><span class="sxs-lookup"><span data-stu-id="b0239-105">Passing Single-Dimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="b0239-106">Sie können ein initialisiertes eindimensionales Array an eine Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="b0239-106">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="b0239-107">Die folgende Anweisung sendet z.B. ein Array an eine print-Methode.</span><span class="sxs-lookup"><span data-stu-id="b0239-107">For example, the following statement sends an array to a print method.</span></span>  
  
 [!code-csharp[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]  
  
 <span data-ttu-id="b0239-108">Im folgenden Code wird eine partielle Implementierung der print-Methode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b0239-108">The following code shows a partial implementation of the print method.</span></span>  
  
 [!code-csharp[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]  
  
 <span data-ttu-id="b0239-109">Sie können einen neuen Array in einem Schritt initialisieren und übergeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0239-109">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 [!code-csharp[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="b0239-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b0239-110">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b0239-111">description</span><span class="sxs-lookup"><span data-stu-id="b0239-111">Description</span></span>  
 <span data-ttu-id="b0239-112">Im folgenden Beispiel wird ein Array von Zeichenfolgen initialisiert und als Argument an eine `PrintArray`-Methode für Zeichenfolgen übergeben.</span><span class="sxs-lookup"><span data-stu-id="b0239-112">In the following example, an array of strings is initialized and passed as an argument to a `PrintArray` method for strings.</span></span> <span data-ttu-id="b0239-113">Die Methode zeigt die Elemente des Arrays an.</span><span class="sxs-lookup"><span data-stu-id="b0239-113">The method displays the elements of the array.</span></span> <span data-ttu-id="b0239-114">Als Nächstes werden die Methoden `ChangeArray` und `ChangeArrayElement` aufgerufen, um zu veranschaulichen, dass das Senden eines Arrayarguments nach Wert keine Änderungen an den Arrayelementen verhindert.</span><span class="sxs-lookup"><span data-stu-id="b0239-114">Next, methods `ChangeArray` and `ChangeArrayElement` are called to demonstrate that sending an array argument by value does not prevent changes to the array elements.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b0239-115">Code</span><span class="sxs-lookup"><span data-stu-id="b0239-115">Code</span></span>  
 [!code-csharp[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]  
  
## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="b0239-116">Übergeben von mehrdimensionalen Arrays als Argumente</span><span class="sxs-lookup"><span data-stu-id="b0239-116">Passing Multidimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="b0239-117">Sie können ein initialisiertes mehrdimensionales Array genauso wie Sie ein eindimensionales Array an eine Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="b0239-117">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>  
  
 [!code-csharp[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]  
  
 <span data-ttu-id="b0239-118">Der folgende Code zeigt eine partielle Deklaration einer print-Methode, die ein zweidimensionales Array als Argument akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="b0239-118">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>  
  
 [!code-csharp[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]  
  
 <span data-ttu-id="b0239-119">Sie können einen neuen Array in einem Schritt initialisieren und übergeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0239-119">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]  
  
## <a name="example"></a><span data-ttu-id="b0239-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b0239-120">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b0239-121">description</span><span class="sxs-lookup"><span data-stu-id="b0239-121">Description</span></span>  
 <span data-ttu-id="b0239-122">Im folgenden Beispiel wird ein zweidimensionales Array von ganzen Zahlen initialisiert und an die `Print2DArray`-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="b0239-122">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="b0239-123">Die Methode zeigt die Elemente des Arrays an.</span><span class="sxs-lookup"><span data-stu-id="b0239-123">The method displays the elements of the array.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b0239-124">Code</span><span class="sxs-lookup"><span data-stu-id="b0239-124">Code</span></span>  
 [!code-csharp[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b0239-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0239-125">See Also</span></span>  
 [<span data-ttu-id="b0239-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b0239-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b0239-127">Arrays</span><span class="sxs-lookup"><span data-stu-id="b0239-127">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="b0239-128">Eindimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="b0239-128">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="b0239-129">Mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="b0239-129">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="b0239-130">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="b0239-130">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
