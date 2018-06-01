---
title: Marshallen verschiedener Typen von Arrays
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- marshaling, Arrays sample
- data marshaling, Arrays sample
ms.assetid: c5ac9920-5b6e-4dc9-bf2d-1f6f8ad3b0bf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed2a4b91608306021ce510098eaf044520cbb089
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33391455"
---
# <a name="marshaling-different-types-of-arrays"></a><span data-ttu-id="13ea3-102">Marshallen verschiedener Typen von Arrays</span><span class="sxs-lookup"><span data-stu-id="13ea3-102">Marshaling Different Types of Arrays</span></span>
<span data-ttu-id="13ea3-103">Ein Array ist ein Verweistyp in verwaltetem Code, der ein oder mehrere Elemente des gleichen Typs enthält.</span><span class="sxs-lookup"><span data-stu-id="13ea3-103">An array is a reference type in managed code that contains one or more elements of the same type.</span></span> <span data-ttu-id="13ea3-104">Obwohl es sich bei Arrays um Verweistypen handelt, werden sie als In-Parameter an unverwaltete Funktionen übergeben.</span><span class="sxs-lookup"><span data-stu-id="13ea3-104">Although arrays are reference types, they are passed as In parameters to unmanaged functions.</span></span> <span data-ttu-id="13ea3-105">Dieses Verhalten entspricht nicht der Art und Weise, wie verwaltete Arrays an verwaltete Objekte übergeben werden, d. h. Als In-/Out-Parameter.</span><span class="sxs-lookup"><span data-stu-id="13ea3-105">This behavior is inconsistent with way managed arrays are passed to managed objects, which is as In/Out parameters.</span></span> <span data-ttu-id="13ea3-106">Weitere Details finden Sie unter [Kopieren und Fixieren](copying-and-pinning.md).</span><span class="sxs-lookup"><span data-stu-id="13ea3-106">For additional details, see [Copying and Pinning](copying-and-pinning.md).</span></span>  
  
 <span data-ttu-id="13ea3-107">Die folgende Tabelle enthält eine Liste der Marshallingoptionen für Arrays und beschreibt deren Verwendung.</span><span class="sxs-lookup"><span data-stu-id="13ea3-107">The following table lists marshaling options for arrays and describes their usage.</span></span>  
  
|<span data-ttu-id="13ea3-108">Array</span><span class="sxs-lookup"><span data-stu-id="13ea3-108">Array</span></span>|<span data-ttu-id="13ea3-109">description</span><span class="sxs-lookup"><span data-stu-id="13ea3-109">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="13ea3-110">Aus ganzen Zahlen nach Wert</span><span class="sxs-lookup"><span data-stu-id="13ea3-110">Of integers by value.</span></span>|<span data-ttu-id="13ea3-111">Übergibt ein aus ganzen Zahlen bestehendes Array als In-Parameter.</span><span class="sxs-lookup"><span data-stu-id="13ea3-111">Passes an array of integers as an In parameter.</span></span>|  
|<span data-ttu-id="13ea3-112">Aus ganzen Zahlen nach Verweis</span><span class="sxs-lookup"><span data-stu-id="13ea3-112">Of integers by reference.</span></span>|<span data-ttu-id="13ea3-113">Übergibt ein aus ganzen Zahlen bestehendes Array als In-/Out-Parameter.</span><span class="sxs-lookup"><span data-stu-id="13ea3-113">Passes an array of integers as an In/Out parameter.</span></span>|  
|<span data-ttu-id="13ea3-114">Aus ganzen Zahlen nach Wert (zweidimensional)</span><span class="sxs-lookup"><span data-stu-id="13ea3-114">Of integers by value (two-dimensional).</span></span>|<span data-ttu-id="13ea3-115">Übergibt eine Matrix aus ganzen Zahlen als In-Parameter.</span><span class="sxs-lookup"><span data-stu-id="13ea3-115">Passes a matrix of integers as an In parameter.</span></span>|  
|<span data-ttu-id="13ea3-116">Aus Zeichenfolgen nach Wert</span><span class="sxs-lookup"><span data-stu-id="13ea3-116">Of strings by value.</span></span>|<span data-ttu-id="13ea3-117">Übergibt ein aus Zeichenfolgen bestehendes Array als In-Parameter.</span><span class="sxs-lookup"><span data-stu-id="13ea3-117">Passes an array of strings as an In parameter.</span></span>|  
|<span data-ttu-id="13ea3-118">Aus Strukturen mit ganzen Zahlen</span><span class="sxs-lookup"><span data-stu-id="13ea3-118">Of structures with integers.</span></span>|<span data-ttu-id="13ea3-119">Übergibt ein aus Strukturen bestehendes Array mit ganzen Zahlen als In-Parameter.</span><span class="sxs-lookup"><span data-stu-id="13ea3-119">Passes an array of structures that contain integers as an In parameter.</span></span>|  
|<span data-ttu-id="13ea3-120">Aus Strukturen mit Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="13ea3-120">Of structures with strings.</span></span>|<span data-ttu-id="13ea3-121">Übergibt ein aus Strukturen bestehendes Array, das nur ganze Zahlen enthält, als In-/Out-Parameter.</span><span class="sxs-lookup"><span data-stu-id="13ea3-121">Passes an array of structures that contain only integers as an In/Out parameter.</span></span> <span data-ttu-id="13ea3-122">Member des Arrays können geändert werden.</span><span class="sxs-lookup"><span data-stu-id="13ea3-122">Members of the array can be changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="13ea3-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13ea3-123">Example</span></span>  
 <span data-ttu-id="13ea3-124">Dieses Beispiel zeigt, wie die folgenden Arraytypen übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="13ea3-124">This sample demonstrates how to pass the following types of arrays:</span></span>  
  
-   <span data-ttu-id="13ea3-125">Array aus ganzen Zahlen nach Wert</span><span class="sxs-lookup"><span data-stu-id="13ea3-125">Array of integers by value.</span></span>  
  
-   <span data-ttu-id="13ea3-126">Array aus ganzen Zahlen nach Verweis, dessen Größe geändert werden kann</span><span class="sxs-lookup"><span data-stu-id="13ea3-126">Array of integers by reference, which can be resized.</span></span>  
  
-   <span data-ttu-id="13ea3-127">Mehrdimensionales Array (Matrix) mit ganzen Zahlen nach Wert</span><span class="sxs-lookup"><span data-stu-id="13ea3-127">Multidimensional array (matrix) of integers by value.</span></span>  
  
-   <span data-ttu-id="13ea3-128">Array aus Zeichenfolgen nach Wert</span><span class="sxs-lookup"><span data-stu-id="13ea3-128">Array of strings by value.</span></span>  
  
-   <span data-ttu-id="13ea3-129">Array aus Strukturen mit ganzen Zahlen</span><span class="sxs-lookup"><span data-stu-id="13ea3-129">Array of structures with integers.</span></span>  
  
-   <span data-ttu-id="13ea3-130">Array aus Strukturen mit Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="13ea3-130">Array of structures with strings.</span></span>  
  
 <span data-ttu-id="13ea3-131">Sofern ein Array nicht explizit nach Verweis gemarshallt wird, wird das Standardverhalten des Arrays als In-Parameter gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="13ea3-131">Unless an array is explicitly marshaled by reference, the default behavior marshals the array as an In parameter.</span></span> <span data-ttu-id="13ea3-132">Sie können dieses Verhalten ändern, indem Sie explizit die Attribute <xref:System.Runtime.InteropServices.InAttribute> und <xref:System.Runtime.InteropServices.OutAttribute> anwenden.</span><span class="sxs-lookup"><span data-stu-id="13ea3-132">You can change this behavior by applying the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes explicitly.</span></span>  
  
 <span data-ttu-id="13ea3-133">Das Beispiel für Arrays verwendet die folgenden nicht verwalteten Funktionen, die jeweils zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="13ea3-133">The Arrays sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
-   <span data-ttu-id="13ea3-134">**TestArrayOfInts** aus PinvokeLib.dll exportiert.</span><span class="sxs-lookup"><span data-stu-id="13ea3-134">**TestArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestArrayOfInts(int* pArray, int pSize);  
    ```  
  
-   <span data-ttu-id="13ea3-135">**TestRefArrayOfInts** aus PinvokeLib.dll exportiert.</span><span class="sxs-lookup"><span data-stu-id="13ea3-135">**TestRefArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestRefArrayOfInts(int** ppArray, int* pSize);  
    ```  
  
-   <span data-ttu-id="13ea3-136">**TestMatrixOfInts** aus PinvokeLib.dll exportiert.</span><span class="sxs-lookup"><span data-stu-id="13ea3-136">**TestMatrixOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestMatrixOfInts(int pMatrix[][COL_DIM], int row);  
    ```  
  
-   <span data-ttu-id="13ea3-137">**TestArrayOfStrings** aus PinvokeLib.dll exportiert.</span><span class="sxs-lookup"><span data-stu-id="13ea3-137">**TestArrayOfStrings** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestArrayOfStrings(char** ppStrArray, int size);  
    ```  
  
-   <span data-ttu-id="13ea3-138">**TestArrayOfStructs** aus PinvokeLib.dll exportiert.</span><span class="sxs-lookup"><span data-stu-id="13ea3-138">**TestArrayOfStructs** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestArrayOfStructs(MYPOINT* pPointArray, int size);  
    ```  
  
-   <span data-ttu-id="13ea3-139">**TestArrayOfStructs2** aus PinvokeLib.dll exportiert.</span><span class="sxs-lookup"><span data-stu-id="13ea3-139">**TestArrayOfStructs2** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestArrayOfStructs2 (MYPERSON* pPersonArray, int size);  
    ```  
  
 <span data-ttu-id="13ea3-140">[PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100)) ist eine benutzerdefinierte, nicht verwaltete Bibliothek, die Implementierungen für die zuvor aufgelisteten Funktionen und zwei Strukturvariablen (**MYPOINT** und **MYPERSON**) enthält.</span><span class="sxs-lookup"><span data-stu-id="13ea3-140">[PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100)) is a custom unmanaged library that contains implementations for the previously listed functions and two structure variables, **MYPOINT** and **MYPERSON**.</span></span> <span data-ttu-id="13ea3-141">Die Strukturen enthalten die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="13ea3-141">The structures contain the following elements:</span></span>  
  
```  
typedef struct _MYPOINT  
{  
   int x;   
   int y;   
} MYPOINT;  
  
typedef struct _MYPERSON  
{  
   char* first;   
   char* last;   
} MYPERSON;  
```  
  
 <span data-ttu-id="13ea3-142">In diesem Beispiel enthalten die Strukturen `MyPoint` und `MyPerson` eingebettete Typen.</span><span class="sxs-lookup"><span data-stu-id="13ea3-142">In this sample, the `MyPoint` and `MyPerson` structures contain embedded types.</span></span> <span data-ttu-id="13ea3-143">Das <xref:System.Runtime.InteropServices.StructLayoutAttribute> -Attribut ist so eingerichtet, dass sichergestellt wird, dass die Member im Speicher sequenziell in der Reihenfolge ihres Erscheinens angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="13ea3-143">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>  
  
 <span data-ttu-id="13ea3-144">Die `LibWrap`-Klasse enthält eine Reihe von Methoden, die von der `App`-Klasse aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="13ea3-144">The `LibWrap` class contains a set of methods called by the `App` class.</span></span> <span data-ttu-id="13ea3-145">Spezifische Details zum Übergeben von Array finden Sie in den Kommentaren im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="13ea3-145">For specific details about passing arrays, see the comments in the following sample.</span></span> <span data-ttu-id="13ea3-146">Ein Array vom Typ "Verweis" wird standardmäßig als In-Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="13ea3-146">An array, which is a reference type, is passed as an In parameter by default.</span></span> <span data-ttu-id="13ea3-147">Damit das aufrufende Programm die Ergebnisse erhält, müssen **InAttribute** und **OutAttribute** explizit dem Argument hinzugefügt werden, das das Array enthält.</span><span class="sxs-lookup"><span data-stu-id="13ea3-147">For the caller to receive the results, **InAttribute** and **OutAttribute** must be applied explicitly to the argument containing the array.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="13ea3-148">Deklarieren von Prototypen</span><span class="sxs-lookup"><span data-stu-id="13ea3-148">Declaring Prototypes</span></span>  
 [!code-csharp[Conceptual.Interop.Marshaling#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#31)]
 [!code-vb[Conceptual.Interop.Marshaling#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#31)]  
  
### <a name="calling-functions"></a><span data-ttu-id="13ea3-149">Aufrufen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="13ea3-149">Calling Functions</span></span>  
 [!code-csharp[Conceptual.Interop.Marshaling#32](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#32)]
 [!code-vb[Conceptual.Interop.Marshaling#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="13ea3-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13ea3-150">See Also</span></span>  
 <span data-ttu-id="13ea3-151">[Marshallen von Typenarrays](https://msdn.microsoft.com/library/049b1c1b-228f-4445-88ec-91bc7fd4b1e8(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="13ea3-151">[Marshaling Arrays of Types](https://msdn.microsoft.com/library/049b1c1b-228f-4445-88ec-91bc7fd4b1e8(v=vs.100))</span></span>  
 <span data-ttu-id="13ea3-152">[Datentypen für den Plattformaufruf](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="13ea3-152">[Platform Invoke Data Types](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span></span>  
 [<span data-ttu-id="13ea3-153">Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)</span><span class="sxs-lookup"><span data-stu-id="13ea3-153">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
