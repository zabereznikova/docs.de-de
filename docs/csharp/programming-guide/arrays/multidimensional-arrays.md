---
title: Mehrdimensionale Arrays – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
ms.openlocfilehash: eb49f4386b6106328f1613b5ec70794ac26fc9b7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715037"
---
# <a name="multidimensional-arrays-c-programming-guide"></a><span data-ttu-id="5543e-102">Mehrdimensionale Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="5543e-102">Multidimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="5543e-103">Arrays können mehr als eine Dimension aufweisen.</span><span class="sxs-lookup"><span data-stu-id="5543e-103">Arrays can have more than one dimension.</span></span> <span data-ttu-id="5543e-104">Die folgende Deklaration erstellt z.B. ein zweidimensionales Array mit vier Zeilen und zwei Spalten.</span><span class="sxs-lookup"><span data-stu-id="5543e-104">For example, the following declaration creates a two-dimensional array of four rows and two columns.</span></span>  
  
 [!code-csharp[csProgGuideArrays#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#11)]  
  
 <span data-ttu-id="5543e-105">Die folgende Deklaration erstellt ein Array mit drei Dimensionen 4, 2 und 3.</span><span class="sxs-lookup"><span data-stu-id="5543e-105">The following declaration creates an array of three dimensions, 4, 2, and 3.</span></span>  
  
 [!code-csharp[csProgGuideArrays#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#12)]  
  
## <a name="array-initialization"></a><span data-ttu-id="5543e-106">Arrayinitialisierung</span><span class="sxs-lookup"><span data-stu-id="5543e-106">Array Initialization</span></span>

 <span data-ttu-id="5543e-107">Sie können das Array wie im folgenden Beispiel gezeigt nach der Deklaration initialisieren.</span><span class="sxs-lookup"><span data-stu-id="5543e-107">You can initialize the array upon declaration, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#13)]  
  
 <span data-ttu-id="5543e-108">Sie können das Array auch ohne Angabe des Rangs initialisieren.</span><span class="sxs-lookup"><span data-stu-id="5543e-108">You also can initialize the array without specifying the rank.</span></span>  
  
 [!code-csharp[csProgGuideArrays#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#14)]  
  
 <span data-ttu-id="5543e-109">Wenn Sie eine Arrayvariable ohne Initialisierung deklarieren möchten, müssen Sie der Variable mit dem Operator `new` ein Array zuweisen.</span><span class="sxs-lookup"><span data-stu-id="5543e-109">If you choose to declare an array variable without initialization, you must use the `new` operator to assign an array to the variable.</span></span> <span data-ttu-id="5543e-110">Die Verwendung von `new` wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5543e-110">The use of `new` is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#15)]  
  
 <span data-ttu-id="5543e-111">Im folgende Beispiel wird einem bestimmten Arrayelement ein Wert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="5543e-111">The following example assigns a value to a particular array element.</span></span>  
  
 [!code-csharp[csProgGuideArrays#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#16)]  
  
 <span data-ttu-id="5543e-112">Auf ähnliche Weise wird im folgenden Beispiel der Wert eines bestimmten Arrayelements abgerufen und der Variablen `elementValue` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="5543e-112">Similarly, the following example gets the value of a particular array element and assigns it to variable `elementValue`.</span></span>  
  
 [!code-csharp[csProgGuideArrays#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#42)]  
  
 <span data-ttu-id="5543e-113">Im folgenden Codebeispiel werden die Arrayelemente auf Standardwerte initialisiert (mit Ausnahme von verzweigten Arrays).</span><span class="sxs-lookup"><span data-stu-id="5543e-113">The following code example initializes the array elements to default values (except for jagged arrays).</span></span>  
  
 [!code-csharp[csProgGuideArrays#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#17)]  
  
## <a name="see-also"></a><span data-ttu-id="5543e-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5543e-114">See also</span></span>

- [<span data-ttu-id="5543e-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="5543e-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5543e-116">Arrays</span><span class="sxs-lookup"><span data-stu-id="5543e-116">Arrays</span></span>](./index.md)
- [<span data-ttu-id="5543e-117">Eindimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="5543e-117">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="5543e-118">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="5543e-118">Jagged Arrays</span></span>](./jagged-arrays.md)
