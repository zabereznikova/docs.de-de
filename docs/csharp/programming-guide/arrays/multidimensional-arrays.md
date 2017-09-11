---
title: Mehrdimensionale Arrays (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
caps.latest.revision: 16
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
ms.openlocfilehash: 0203046e2038e97cf791141f6863fd8940b22ea4
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="multidimensional-arrays-c-programming-guide"></a><span data-ttu-id="3b64e-102">Mehrdimensionale Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="3b64e-102">Multidimensional Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="3b64e-103">Arrays können mehr als eine Dimension aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3b64e-103">Arrays can have more than one dimension.</span></span> <span data-ttu-id="3b64e-104">Die folgende Deklaration erstellt z.B. ein zweidimensionales Array mit vier Zeilen und zwei Spalten.</span><span class="sxs-lookup"><span data-stu-id="3b64e-104">For example, the following declaration creates a two-dimensional array of four rows and two columns.</span></span>  
  
 <span data-ttu-id="3b64e-105">[!code-cs[csProgGuideArrays#11](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3b64e-105">[!code-cs[csProgGuideArrays#11](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_1.cs)]</span></span>  
  
 <span data-ttu-id="3b64e-106">Die folgende Deklaration erstellt ein Array mit drei Dimensionen 4, 2 und 3.</span><span class="sxs-lookup"><span data-stu-id="3b64e-106">The following declaration creates an array of three dimensions, 4, 2, and 3.</span></span>  
  
 <span data-ttu-id="3b64e-107">[!code-cs[csProgGuideArrays#12](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="3b64e-107">[!code-cs[csProgGuideArrays#12](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_2.cs)]</span></span>  
  
## <a name="array-initialization"></a><span data-ttu-id="3b64e-108">Arrayinitialisierung</span><span class="sxs-lookup"><span data-stu-id="3b64e-108">Array Initialization</span></span>  
 <span data-ttu-id="3b64e-109">Sie können das Array wie im folgenden Beispiel gezeigt nach der Deklaration initialisieren.</span><span class="sxs-lookup"><span data-stu-id="3b64e-109">You can initialize the array upon declaration, as is shown in the following example.</span></span>  
  
 <span data-ttu-id="3b64e-110">[!code-cs[csProgGuideArrays#13](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="3b64e-110">[!code-cs[csProgGuideArrays#13](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_3.cs)]</span></span>  
  
 <span data-ttu-id="3b64e-111">Sie können das Array auch ohne Angabe des Rangs initialisieren.</span><span class="sxs-lookup"><span data-stu-id="3b64e-111">You also can initialize the array without specifying the rank.</span></span>  
  
 <span data-ttu-id="3b64e-112">[!code-cs[csProgGuideArrays#14](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="3b64e-112">[!code-cs[csProgGuideArrays#14](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_4.cs)]</span></span>  
  
 <span data-ttu-id="3b64e-113">Wenn Sie eine Arrayvariable ohne Initialisierung deklarieren möchten, müssen Sie der Variable mit dem Operator `new` ein Array zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3b64e-113">If you choose to declare an array variable without initialization, you must use the `new` operator to assign an array to the variable.</span></span> <span data-ttu-id="3b64e-114">Die Verwendung von `new` wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3b64e-114">The use of `new` is shown in the following example.</span></span>  
  
 <span data-ttu-id="3b64e-115">[!code-cs[csProgGuideArrays#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="3b64e-115">[!code-cs[csProgGuideArrays#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_5.cs)]</span></span>  
  
 <span data-ttu-id="3b64e-116">Im folgende Beispiel wird einem bestimmten Arrayelement ein Wert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="3b64e-116">The following example assigns a value to a particular array element.</span></span>  
  
 <span data-ttu-id="3b64e-117">[!code-cs[csProgGuideArrays#16](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="3b64e-117">[!code-cs[csProgGuideArrays#16](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_6.cs)]</span></span>  
  
 <span data-ttu-id="3b64e-118">Auf ähnliche Weise wird im folgenden Beispiel der Wert eines bestimmten Arrayelements abgerufen und der Variablen `elementValue` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="3b64e-118">Similarly, the following example gets the value of a particular array element and assigns it to variable `elementValue`.</span></span>  
  
 <span data-ttu-id="3b64e-119">[!code-cs[csProgGuideArrays#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="3b64e-119">[!code-cs[csProgGuideArrays#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_7.cs)]</span></span>  
  
 <span data-ttu-id="3b64e-120">Im folgenden Codebeispiel werden die Arrayelemente auf Standardwerte initialisiert (mit Ausnahme von verzweigten Arrays).</span><span class="sxs-lookup"><span data-stu-id="3b64e-120">The following code example initializes the array elements to default values (except for jagged arrays).</span></span>  
  
 <span data-ttu-id="3b64e-121">[!code-cs[csProgGuideArrays#17](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="3b64e-121">[!code-cs[csProgGuideArrays#17](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_8.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b64e-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b64e-122">See Also</span></span>  
 <span data-ttu-id="3b64e-123">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3b64e-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3b64e-124">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="3b64e-124">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="3b64e-125">[Eindimensionale Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="3b64e-125">[Single-Dimensional Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span></span>  
 [<span data-ttu-id="3b64e-126">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="3b64e-126">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

