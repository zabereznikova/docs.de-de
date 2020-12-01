---
title: Marshallen verschiedener Typen von Arrays
description: Marshallen Sie verschiedene Typen von Arrays, wie z. B. ganze Zahlen nach Wert oder Verweis, zweidimensionale ganze Zahlen nach Wert, Zeichenfolgen nach Wert und Strukturen mit ganzen Zahlen oder Zeichenfolgen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- marshaling, Arrays sample
- data marshaling, Arrays sample
ms.assetid: c5ac9920-5b6e-4dc9-bf2d-1f6f8ad3b0bf
ms.openlocfilehash: b7777e99daf9d294bf26033f470a6e562b7b727f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269092"
---
# <a name="marshaling-different-types-of-arrays"></a><span data-ttu-id="6c762-103">Marshallen verschiedener Typen von Arrays</span><span class="sxs-lookup"><span data-stu-id="6c762-103">Marshaling Different Types of Arrays</span></span>

<span data-ttu-id="6c762-104">Ein Array ist ein Verweistyp in verwaltetem Code, der ein oder mehrere Elemente des gleichen Typs enthält.</span><span class="sxs-lookup"><span data-stu-id="6c762-104">An array is a reference type in managed code that contains one or more elements of the same type.</span></span> <span data-ttu-id="6c762-105">Obwohl es sich bei Arrays um Verweistypen handelt, werden sie als In-Parameter an unverwaltete Funktionen übergeben.</span><span class="sxs-lookup"><span data-stu-id="6c762-105">Although arrays are reference types, they are passed as In parameters to unmanaged functions.</span></span> <span data-ttu-id="6c762-106">Dieses Verhalten entspricht nicht der Art und Weise, wie verwaltete Arrays an verwaltete Objekte übergeben werden, d. h. Als In-/Out-Parameter.</span><span class="sxs-lookup"><span data-stu-id="6c762-106">This behavior is inconsistent with way managed arrays are passed to managed objects, which is as In/Out parameters.</span></span> <span data-ttu-id="6c762-107">Weitere Details finden Sie unter [Kopieren und Fixieren](copying-and-pinning.md).</span><span class="sxs-lookup"><span data-stu-id="6c762-107">For additional details, see [Copying and Pinning](copying-and-pinning.md).</span></span>  
  
 <span data-ttu-id="6c762-108">Die folgende Tabelle enthält eine Liste der Marshallingoptionen für Arrays und beschreibt deren Verwendung.</span><span class="sxs-lookup"><span data-stu-id="6c762-108">The following table lists marshaling options for arrays and describes their usage.</span></span>  
  
|<span data-ttu-id="6c762-109">Array</span><span class="sxs-lookup"><span data-stu-id="6c762-109">Array</span></span>|<span data-ttu-id="6c762-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c762-110">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6c762-111">Aus ganzen Zahlen nach Wert</span><span class="sxs-lookup"><span data-stu-id="6c762-111">Of integers by value.</span></span>|<span data-ttu-id="6c762-112">Übergibt ein aus ganzen Zahlen bestehendes Array als In-Parameter.</span><span class="sxs-lookup"><span data-stu-id="6c762-112">Passes an array of integers as an In parameter.</span></span>|  
|<span data-ttu-id="6c762-113">Aus ganzen Zahlen nach Verweis</span><span class="sxs-lookup"><span data-stu-id="6c762-113">Of integers by reference.</span></span>|<span data-ttu-id="6c762-114">Übergibt ein aus ganzen Zahlen bestehendes Array als In-/Out-Parameter.</span><span class="sxs-lookup"><span data-stu-id="6c762-114">Passes an array of integers as an In/Out parameter.</span></span>|  
|<span data-ttu-id="6c762-115">Aus ganzen Zahlen nach Wert (zweidimensional)</span><span class="sxs-lookup"><span data-stu-id="6c762-115">Of integers by value (two-dimensional).</span></span>|<span data-ttu-id="6c762-116">Übergibt eine Matrix aus ganzen Zahlen als In-Parameter.</span><span class="sxs-lookup"><span data-stu-id="6c762-116">Passes a matrix of integers as an In parameter.</span></span>|  
|<span data-ttu-id="6c762-117">Aus Zeichenfolgen nach Wert</span><span class="sxs-lookup"><span data-stu-id="6c762-117">Of strings by value.</span></span>|<span data-ttu-id="6c762-118">Übergibt ein aus Zeichenfolgen bestehendes Array als In-Parameter.</span><span class="sxs-lookup"><span data-stu-id="6c762-118">Passes an array of strings as an In parameter.</span></span>|  
|<span data-ttu-id="6c762-119">Aus Strukturen mit ganzen Zahlen</span><span class="sxs-lookup"><span data-stu-id="6c762-119">Of structures with integers.</span></span>|<span data-ttu-id="6c762-120">Übergibt ein aus Strukturen bestehendes Array mit ganzen Zahlen als In-Parameter.</span><span class="sxs-lookup"><span data-stu-id="6c762-120">Passes an array of structures that contain integers as an In parameter.</span></span>|  
|<span data-ttu-id="6c762-121">Aus Strukturen mit Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="6c762-121">Of structures with strings.</span></span>|<span data-ttu-id="6c762-122">Übergibt ein aus Strukturen bestehendes Array, das nur Zeichenfolgen enthält, als In-/Out-Parameter.</span><span class="sxs-lookup"><span data-stu-id="6c762-122">Passes an array of structures that contain only strings as an In/Out parameter.</span></span> <span data-ttu-id="6c762-123">Member des Arrays können geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6c762-123">Members of the array can be changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6c762-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6c762-124">Example</span></span>  

 <span data-ttu-id="6c762-125">Dieses Beispiel zeigt, wie die folgenden Arraytypen übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="6c762-125">This sample demonstrates how to pass the following types of arrays:</span></span>  
  
- <span data-ttu-id="6c762-126">Array aus ganzen Zahlen nach Wert</span><span class="sxs-lookup"><span data-stu-id="6c762-126">Array of integers by value.</span></span>  
  
- <span data-ttu-id="6c762-127">Array aus ganzen Zahlen nach Verweis, dessen Größe geändert werden kann</span><span class="sxs-lookup"><span data-stu-id="6c762-127">Array of integers by reference, which can be resized.</span></span>  
  
- <span data-ttu-id="6c762-128">Mehrdimensionales Array (Matrix) mit ganzen Zahlen nach Wert</span><span class="sxs-lookup"><span data-stu-id="6c762-128">Multidimensional array (matrix) of integers by value.</span></span>  
  
- <span data-ttu-id="6c762-129">Array aus Zeichenfolgen nach Wert</span><span class="sxs-lookup"><span data-stu-id="6c762-129">Array of strings by value.</span></span>  
  
- <span data-ttu-id="6c762-130">Array aus Strukturen mit ganzen Zahlen</span><span class="sxs-lookup"><span data-stu-id="6c762-130">Array of structures with integers.</span></span>  
  
- <span data-ttu-id="6c762-131">Array aus Strukturen mit Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="6c762-131">Array of structures with strings.</span></span>  
  
 <span data-ttu-id="6c762-132">Sofern ein Array nicht explizit nach Verweis gemarshallt wird, wird das Standardverhalten des Arrays als In-Parameter gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="6c762-132">Unless an array is explicitly marshaled by reference, the default behavior marshals the array as an In parameter.</span></span> <span data-ttu-id="6c762-133">Sie können dieses Verhalten ändern, indem Sie explizit die Attribute <xref:System.Runtime.InteropServices.InAttribute> und <xref:System.Runtime.InteropServices.OutAttribute> anwenden.</span><span class="sxs-lookup"><span data-stu-id="6c762-133">You can change this behavior by applying the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes explicitly.</span></span>  
  
 <span data-ttu-id="6c762-134">Das Beispiel für Arrays verwendet die folgenden nicht verwalteten Funktionen, die jeweils zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="6c762-134">The Arrays sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
- <span data-ttu-id="6c762-135">**TestArrayOfInts** aus PinvokeLib.dll exportiert.</span><span class="sxs-lookup"><span data-stu-id="6c762-135">**TestArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfInts(int* pArray, int pSize);  
    ```  
  
- <span data-ttu-id="6c762-136">**TestRefArrayOfInts** aus PinvokeLib.dll exportiert.</span><span class="sxs-lookup"><span data-stu-id="6c762-136">**TestRefArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestRefArrayOfInts(int** ppArray, int* pSize);  
    ```  
  
- <span data-ttu-id="6c762-137">**TestMatrixOfInts** aus PinvokeLib.dll exportiert.</span><span class="sxs-lookup"><span data-stu-id="6c762-137">**TestMatrixOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestMatrixOfInts(int pMatrix[][COL_DIM], int row);  
    ```  
  
- <span data-ttu-id="6c762-138">**TestArrayOfStrings** aus PinvokeLib.dll exportiert.</span><span class="sxs-lookup"><span data-stu-id="6c762-138">**TestArrayOfStrings** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfStrings(char** ppStrArray, int size);  
    ```  
  
- <span data-ttu-id="6c762-139">**TestArrayOfStructs** aus PinvokeLib.dll exportiert.</span><span class="sxs-lookup"><span data-stu-id="6c762-139">**TestArrayOfStructs** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfStructs(MYPOINT* pPointArray, int size);  
    ```  
  
- <span data-ttu-id="6c762-140">**TestArrayOfStructs2** aus PinvokeLib.dll exportiert.</span><span class="sxs-lookup"><span data-stu-id="6c762-140">**TestArrayOfStructs2** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfStructs2 (MYPERSON* pPersonArray, int size);  
    ```  
  
 <span data-ttu-id="6c762-141">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) ist eine benutzerdefinierte, nicht verwaltete Bibliothek, die Implementierungen für die zuvor aufgelisteten Funktionen und zwei Strukturvariablen ( **MYPOINT** und **MYPERSON**) enthält.</span><span class="sxs-lookup"><span data-stu-id="6c762-141">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains implementations for the previously listed functions and two structure variables, **MYPOINT** and **MYPERSON**.</span></span> <span data-ttu-id="6c762-142">Die Strukturen enthalten die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="6c762-142">The structures contain the following elements:</span></span>  
  
```cpp
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
  
 <span data-ttu-id="6c762-143">In diesem Beispiel enthalten die Strukturen `MyPoint` und `MyPerson` eingebettete Typen.</span><span class="sxs-lookup"><span data-stu-id="6c762-143">In this sample, the `MyPoint` and `MyPerson` structures contain embedded types.</span></span> <span data-ttu-id="6c762-144">Das <xref:System.Runtime.InteropServices.StructLayoutAttribute> -Attribut ist so eingerichtet, dass sichergestellt wird, dass die Member im Speicher sequenziell in der Reihenfolge ihres Erscheinens angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6c762-144">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>  
  
 <span data-ttu-id="6c762-145">Die `NativeMethods` -Klasse enthält eine Reihe von Methoden, die von der `App` -Klasse aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6c762-145">The `NativeMethods` class contains a set of methods called by the `App` class.</span></span> <span data-ttu-id="6c762-146">Spezifische Details zum Übergeben von Array finden Sie in den Kommentaren im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="6c762-146">For specific details about passing arrays, see the comments in the following sample.</span></span> <span data-ttu-id="6c762-147">Ein Array vom Typ "Verweis" wird standardmäßig als In-Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="6c762-147">An array, which is a reference type, is passed as an In parameter by default.</span></span> <span data-ttu-id="6c762-148">Damit das aufrufende Programm die Ergebnisse erhält, müssen **InAttribute** und **OutAttribute** explizit dem Argument hinzugefügt werden, das das Array enthält.</span><span class="sxs-lookup"><span data-stu-id="6c762-148">For the caller to receive the results, **InAttribute** and **OutAttribute** must be applied explicitly to the argument containing the array.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="6c762-149">Deklarieren von Prototypen</span><span class="sxs-lookup"><span data-stu-id="6c762-149">Declaring Prototypes</span></span>  

 [!code-csharp[Conceptual.Interop.Marshaling#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#31)]
 [!code-vb[Conceptual.Interop.Marshaling#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#31)]  
  
### <a name="calling-functions"></a><span data-ttu-id="6c762-150">Aufrufen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="6c762-150">Calling Functions</span></span>  

 [!code-csharp[Conceptual.Interop.Marshaling#32](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#32)]
 [!code-vb[Conceptual.Interop.Marshaling#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="6c762-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c762-151">See also</span></span>

- [<span data-ttu-id="6c762-152">Datentypen für den Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="6c762-152">Platform invoke data types</span></span>](marshaling-data-with-platform-invoke.md#platform-invoke-data-types)
- [<span data-ttu-id="6c762-153">Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)</span><span class="sxs-lookup"><span data-stu-id="6c762-153">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
