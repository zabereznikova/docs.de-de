---
title: "Übergeben von Arrays als Argumente (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5e83c0c119bc1448be76f83416098158c7f5d684
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="b4de3-102">Übergeben von Arrays als Argumente (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b4de3-102">Passing Arrays as Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="b4de3-103">Arrays können als Argumente an Methodenparameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="b4de3-103">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="b4de3-104">Da es sich bei Arrays um Verweistypen handelt, kann die Methode den Wert der Elemente ändern.</span><span class="sxs-lookup"><span data-stu-id="b4de3-104">Because arrays are reference types, the method can change the value of the elements.</span></span>  
  
## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="b4de3-105">Übergeben von eindimensionalen Arrays als Argumente</span><span class="sxs-lookup"><span data-stu-id="b4de3-105">Passing Single-Dimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="b4de3-106">Sie können ein initialisiertes eindimensionales Array an eine Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="b4de3-106">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="b4de3-107">Die folgende Anweisung sendet z.B. ein Array an eine print-Methode.</span><span class="sxs-lookup"><span data-stu-id="b4de3-107">For example, the following statement sends an array to a print method.</span></span>  
  
 <span data-ttu-id="b4de3-108">[!code-cs[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b4de3-108">[!code-cs[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]</span></span>  
  
 <span data-ttu-id="b4de3-109">Im folgenden Code wird eine partielle Implementierung der print-Methode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b4de3-109">The following code shows a partial implementation of the print method.</span></span>  
  
 <span data-ttu-id="b4de3-110">[!code-cs[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="b4de3-110">[!code-cs[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]</span></span>  
  
 <span data-ttu-id="b4de3-111">Sie können einen neuen Array in einem Schritt initialisieren und übergeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4de3-111">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 <span data-ttu-id="b4de3-112">[!code-cs[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="b4de3-112">[!code-cs[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4de3-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4de3-113">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b4de3-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4de3-114">Description</span></span>  
 <span data-ttu-id="b4de3-115">Im folgenden Beispiel wird ein Array von Zeichenfolgen initialisiert und als Argument an eine `PrintArray`-Methode für Zeichenfolgen übergeben.</span><span class="sxs-lookup"><span data-stu-id="b4de3-115">In the following example, an array of strings is initialized and passed as an argument to a `PrintArray` method for strings.</span></span> <span data-ttu-id="b4de3-116">Die Methode zeigt die Elemente des Arrays an.</span><span class="sxs-lookup"><span data-stu-id="b4de3-116">The method displays the elements of the array.</span></span> <span data-ttu-id="b4de3-117">Als Nächstes werden die Methoden `ChangeArray` und `ChangeArrayElement` aufgerufen, um zu veranschaulichen, dass das Senden eines Arrayarguments nach Wert keine Änderungen an den Arrayelementen verhindert.</span><span class="sxs-lookup"><span data-stu-id="b4de3-117">Next, methods `ChangeArray` and `ChangeArrayElement` are called to demonstrate that sending an array argument by value does not prevent changes to the array elements.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b4de3-118">Code</span><span class="sxs-lookup"><span data-stu-id="b4de3-118">Code</span></span>  
 <span data-ttu-id="b4de3-119">[!code-cs[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="b4de3-119">[!code-cs[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]</span></span>  
  
## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="b4de3-120">Übergeben von mehrdimensionalen Arrays als Argumente</span><span class="sxs-lookup"><span data-stu-id="b4de3-120">Passing Multidimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="b4de3-121">Sie können ein initialisiertes mehrdimensionales Array genauso wie Sie ein eindimensionales Array an eine Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="b4de3-121">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>  
  
 <span data-ttu-id="b4de3-122">[!code-cs[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="b4de3-122">[!code-cs[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]</span></span>  
  
 <span data-ttu-id="b4de3-123">Der folgende Code zeigt eine partielle Deklaration einer print-Methode, die ein zweidimensionales Array als Argument akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="b4de3-123">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>  
  
 <span data-ttu-id="b4de3-124">[!code-cs[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="b4de3-124">[!code-cs[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]</span></span>  
  
 <span data-ttu-id="b4de3-125">Sie können einen neuen Array in einem Schritt initialisieren und übergeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4de3-125">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 <span data-ttu-id="b4de3-126">[!code-cs[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="b4de3-126">[!code-cs[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4de3-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4de3-127">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b4de3-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4de3-128">Description</span></span>  
 <span data-ttu-id="b4de3-129">Im folgenden Beispiel wird ein zweidimensionales Array von ganzen Zahlen initialisiert und an die `Print2DArray`-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="b4de3-129">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="b4de3-130">Die Methode zeigt die Elemente des Arrays an.</span><span class="sxs-lookup"><span data-stu-id="b4de3-130">The method displays the elements of the array.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b4de3-131">Code</span><span class="sxs-lookup"><span data-stu-id="b4de3-131">Code</span></span>  
 <span data-ttu-id="b4de3-132">[!code-cs[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="b4de3-132">[!code-cs[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4de3-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4de3-133">See Also</span></span>  
 <span data-ttu-id="b4de3-134">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b4de3-134">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b4de3-135">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="b4de3-135">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="b4de3-136">[Eindimensionale Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="b4de3-136">[Single-Dimensional Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span></span>  
 <span data-ttu-id="b4de3-137">[Mehrdimensionale Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="b4de3-137">[Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span></span>  
 [<span data-ttu-id="b4de3-138">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="b4de3-138">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

