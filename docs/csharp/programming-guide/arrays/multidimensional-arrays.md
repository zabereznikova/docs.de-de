---
title: Mehrdimensionale Arrays – C#-Programmierhandbuch
description: Arrays in C# können mehr als eine Dimension aufweisen. Bei dieser Beispieldeklaration wird ein zweidimensionales Array mit vier Zeilen und zwei Spalten erstellt.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
ms.openlocfilehash: a2f204c0866672b317569fbc620aa8af60829ffd
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475007"
---
# <a name="multidimensional-arrays-c-programming-guide"></a><span data-ttu-id="01a60-104">Mehrdimensionale Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="01a60-104">Multidimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="01a60-105">Arrays können mehr als eine Dimension aufweisen.</span><span class="sxs-lookup"><span data-stu-id="01a60-105">Arrays can have more than one dimension.</span></span> <span data-ttu-id="01a60-106">Die folgende Deklaration erstellt z.B. ein zweidimensionales Array mit vier Zeilen und zwei Spalten.</span><span class="sxs-lookup"><span data-stu-id="01a60-106">For example, the following declaration creates a two-dimensional array of four rows and two columns.</span></span>  
  
 [!code-csharp[csProgGuideArrays#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#11)]  
  
 <span data-ttu-id="01a60-107">Die folgende Deklaration erstellt ein Array mit drei Dimensionen 4, 2 und 3.</span><span class="sxs-lookup"><span data-stu-id="01a60-107">The following declaration creates an array of three dimensions, 4, 2, and 3.</span></span>  
  
 [!code-csharp[csProgGuideArrays#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#12)]  
  
## <a name="array-initialization"></a><span data-ttu-id="01a60-108">Arrayinitialisierung</span><span class="sxs-lookup"><span data-stu-id="01a60-108">Array Initialization</span></span>

 <span data-ttu-id="01a60-109">Sie können das Array wie im folgenden Beispiel gezeigt nach der Deklaration initialisieren.</span><span class="sxs-lookup"><span data-stu-id="01a60-109">You can initialize the array upon declaration, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#13)]  
  
 <span data-ttu-id="01a60-110">Sie können das Array auch ohne Angabe des Rangs initialisieren.</span><span class="sxs-lookup"><span data-stu-id="01a60-110">You can also initialize the array without specifying the rank.</span></span>  
  
 [!code-csharp[csProgGuideArrays#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#14)]  
  
 <span data-ttu-id="01a60-111">Wenn Sie eine Arrayvariable ohne Initialisierung deklarieren möchten, müssen Sie der Variable mit dem Operator `new` ein Array zuweisen.</span><span class="sxs-lookup"><span data-stu-id="01a60-111">If you choose to declare an array variable without initialization, you must use the `new` operator to assign an array to the variable.</span></span> <span data-ttu-id="01a60-112">Die Verwendung von `new` wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="01a60-112">The use of `new` is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#15)]  
  
 <span data-ttu-id="01a60-113">Im folgende Beispiel wird einem bestimmten Arrayelement ein Wert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="01a60-113">The following example assigns a value to a particular array element.</span></span>  
  
 [!code-csharp[csProgGuideArrays#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#16)]  
  
 <span data-ttu-id="01a60-114">Auf ähnliche Weise wird im folgenden Beispiel der Wert eines bestimmten Arrayelements abgerufen und der Variablen `elementValue` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="01a60-114">Similarly, the following example gets the value of a particular array element and assigns it to variable `elementValue`.</span></span>  
  
 [!code-csharp[csProgGuideArrays#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#42)]  
  
 <span data-ttu-id="01a60-115">Im folgenden Codebeispiel werden die Arrayelemente auf Standardwerte initialisiert (mit Ausnahme von verzweigten Arrays).</span><span class="sxs-lookup"><span data-stu-id="01a60-115">The following code example initializes the array elements to default values (except for jagged arrays).</span></span>  
  
 [!code-csharp[csProgGuideArrays#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#17)]  
  
## <a name="see-also"></a><span data-ttu-id="01a60-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01a60-116">See also</span></span>

- [<span data-ttu-id="01a60-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="01a60-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="01a60-118">Arrays</span><span class="sxs-lookup"><span data-stu-id="01a60-118">Arrays</span></span>](./index.md)
- [<span data-ttu-id="01a60-119">Eindimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="01a60-119">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="01a60-120">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="01a60-120">Jagged Arrays</span></span>](./jagged-arrays.md)
