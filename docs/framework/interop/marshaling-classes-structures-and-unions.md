---
title: Marshallen von Klassen, Strukturen und Unions
description: Erfahren Sie mehr über das Marshallen von Klassen, Strukturen und Unions. Sehen Sie sich Beispiele von Marshalingklassen, Strukturen mit geschachtelten Strukturen, Arrays von Strukturen und Unions an.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, classes
- marshaling, unions
- marshaling, structures
- marshaling, samples
- data marshaling, structures
- platform invoke, marshaling data
- marshaling, classes
- data marshaling, unions
- data marshaling, samples
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: 027832a2-9b43-4fd9-9b45-7f4196261a4e
ms.openlocfilehash: 25de633faabb1424bcf5e618cc5ca129e61c5fca
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547869"
---
# <a name="marshaling-classes-structures-and-unions"></a><span data-ttu-id="a5a4e-104">Marshallen von Klassen, Strukturen und Unions</span><span class="sxs-lookup"><span data-stu-id="a5a4e-104">Marshaling Classes, Structures, and Unions</span></span>

<span data-ttu-id="a5a4e-105">Klassen und Strukturen sind in .NET Framework ähnlich.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-105">Classes and structures are similar in the .NET Framework.</span></span> <span data-ttu-id="a5a4e-106">Beide können Felder, Eigenschaften und Ereignisse enthalten.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-106">Both can have fields, properties, and events.</span></span> <span data-ttu-id="a5a4e-107">Sie können auch über statische und nicht statische Methoden verfügen.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-107">They can also have static and nonstatic methods.</span></span> <span data-ttu-id="a5a4e-108">Ein deutlicher Unterschied ist, dass Strukturen Werttypen sind, während Klassen Verweistypen sind.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-108">One notable difference is that structures are value types and classes are reference types.</span></span>

<span data-ttu-id="a5a4e-109">In der folgende Tabelle werden Marshallingoptionen für Klassen, Strukturen und Unions aufgelistet. Ihre Verwendung wird beschrieben, und es werden Links zu den entsprechenden Plattformaufrufbeispielen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-109">The following table lists marshaling options for classes, structures, and unions; describes their usage; and provides a link to the corresponding platform invoke sample.</span></span>

|<span data-ttu-id="a5a4e-110">Typ</span><span class="sxs-lookup"><span data-stu-id="a5a4e-110">Type</span></span>|<span data-ttu-id="a5a4e-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5a4e-111">Description</span></span>|<span data-ttu-id="a5a4e-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5a4e-112">Sample</span></span>|
|----------|-----------------|------------|
|<span data-ttu-id="a5a4e-113">Klasse als Wert.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-113">Class by value.</span></span>|<span data-ttu-id="a5a4e-114">Übergibt eine Klasse mit ganzzahligen Membern als In/Out-Parameter, wie der verwaltete Fall.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-114">Passes a class with integer members as an In/Out parameter, like the managed case.</span></span>|[<span data-ttu-id="a5a4e-115">SysTime-Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5a4e-115">SysTime sample</span></span>](#systime-sample)|
|<span data-ttu-id="a5a4e-116">Struktur als Wert.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-116">Structure by value.</span></span>|<span data-ttu-id="a5a4e-117">Übergibt Strukturen als In-Parameter.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-117">Passes structures as In parameters.</span></span>|[<span data-ttu-id="a5a4e-118">Beispiel für Strukturen</span><span class="sxs-lookup"><span data-stu-id="a5a4e-118">Structures sample</span></span>](#structures-sample)|
|<span data-ttu-id="a5a4e-119">Struktur als Verweis.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-119">Structure by reference.</span></span>|<span data-ttu-id="a5a4e-120">Übergibt Strukturen als In/Out-Parameter.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-120">Passes structures as In/Out parameters.</span></span>|<span data-ttu-id="a5a4e-121">[OSInfo-Beispiel](/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a5a4e-121">[OSInfo sample](/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))</span></span>|
|<span data-ttu-id="a5a4e-122">Struktur mit geschachtelten Strukturen (vereinfacht).</span><span class="sxs-lookup"><span data-stu-id="a5a4e-122">Structure with nested structures (flattened).</span></span>|<span data-ttu-id="a5a4e-123">Übergibt eine Klasse, die eine Struktur mit geschachtelten Strukturen in der nicht verwalteten Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-123">Passes a class that represents a structure with nested structures in the unmanaged function.</span></span> <span data-ttu-id="a5a4e-124">Die Struktur wird zu einer einzigen großen Struktur im verwalteten Prototyp vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-124">The structure is flattened to one big structure in the managed prototype.</span></span>|[<span data-ttu-id="a5a4e-125">FindFile-Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5a4e-125">FindFile sample</span></span>](#findfile-sample)|
|<span data-ttu-id="a5a4e-126">Struktur mit einem Zeiger auf eine andere Struktur.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-126">Structure with a pointer to another structure.</span></span>|<span data-ttu-id="a5a4e-127">Übergibt eine Struktur, die einen Zeiger auf eine zweite Struktur enthält, als Member.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-127">Passes a structure that contains a pointer to a second structure as a member.</span></span>|[<span data-ttu-id="a5a4e-128">Beispiel für Strukturen</span><span class="sxs-lookup"><span data-stu-id="a5a4e-128">Structures Sample</span></span>](#structures-sample)|
|<span data-ttu-id="a5a4e-129">Array von Strukturen mit ganzen Zahlen als Wert.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-129">Array of structures with integers by value.</span></span>|<span data-ttu-id="a5a4e-130">Übergibt ein aus Strukturen bestehendes Array, das nur ganze Zahlen enthält, als In-/Out-Parameter.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-130">Passes an array of structures that contain only integers as an In/Out parameter.</span></span> <span data-ttu-id="a5a4e-131">Member des Arrays können geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-131">Members of the array can be changed.</span></span>|[<span data-ttu-id="a5a4e-132">Beispiel für Arrays</span><span class="sxs-lookup"><span data-stu-id="a5a4e-132">Arrays Sample</span></span>](marshaling-different-types-of-arrays.md)|
|<span data-ttu-id="a5a4e-133">Array von Strukturen mit ganzen Zahlen und Zeichenfolgen als Verweis.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-133">Array of structures with integers and strings by reference.</span></span>|<span data-ttu-id="a5a4e-134">Übergibt ein Array von Strukturen, die ganze Zahlen und Zeichenfolgen enthalten, als Out-Parameter.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-134">Passes an array of structures that contain integers and strings as an Out parameter.</span></span> <span data-ttu-id="a5a4e-135">Die aufgerufene Funktion weist Speicher für das Array zu.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-135">The called function allocates memory for the array.</span></span>|[<span data-ttu-id="a5a4e-136">OutArrayOfStructs-Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5a4e-136">OutArrayOfStructs Sample</span></span>](#outarrayofstructs-sample)|
|<span data-ttu-id="a5a4e-137">Unions mit Werttypen.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-137">Unions with value types.</span></span>|<span data-ttu-id="a5a4e-138">Übergibt Unions mit Werttypen (Integer und Double).</span><span class="sxs-lookup"><span data-stu-id="a5a4e-138">Passes unions with value types (integer and double).</span></span>|[<span data-ttu-id="a5a4e-139">Unions-Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5a4e-139">Unions sample</span></span>](#unions-sample)|
|<span data-ttu-id="a5a4e-140">Unions mit gemischten Typen.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-140">Unions with mixed types.</span></span>|<span data-ttu-id="a5a4e-141">Übergibt Unions mit gemischten Typen (Integer und String).</span><span class="sxs-lookup"><span data-stu-id="a5a4e-141">Passes unions with mixed types (integer and string).</span></span>|[<span data-ttu-id="a5a4e-142">Unions-Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5a4e-142">Unions sample</span></span>](#unions-sample)|
|<span data-ttu-id="a5a4e-143">Struktur mit plattformspezifischem Layout.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-143">Struct with platform-specific layout.</span></span>|<span data-ttu-id="a5a4e-144">Übergibt einen Typ mit Definitionen für natives Packen.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-144">Passes a type with native-packing definitions.</span></span>|[<span data-ttu-id="a5a4e-145">Plattformbeispiel</span><span class="sxs-lookup"><span data-stu-id="a5a4e-145">Platform sample</span></span>](#platform-sample)|
|<span data-ttu-id="a5a4e-146">Nullwerte in Struktur.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-146">Null values in structure.</span></span>|<span data-ttu-id="a5a4e-147">Übergibt einen NULL-Verweis (**Nothing** in Visual Basic) anstelle eines Verweises auf einen Werttyp.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-147">Passes a null reference (**Nothing** in Visual Basic) instead of a reference to a value type.</span></span>|<span data-ttu-id="a5a4e-148">[HandleRef-Beispiel](/previous-versions/dotnet/netframework-3.0/hc662t8k(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="a5a4e-148">[HandleRef sample](/previous-versions/dotnet/netframework-3.0/hc662t8k(v=vs.85))</span></span>|

## <a name="structures-sample"></a><span data-ttu-id="a5a4e-149">Beispiel für Strukturen</span><span class="sxs-lookup"><span data-stu-id="a5a4e-149">Structures sample</span></span>

<span data-ttu-id="a5a4e-150">Dieses Beispiel veranschaulicht das Übergeben einer Struktur, die auf eine zweite Struktur zeigt, einer Struktur mit einer eingebetteten Struktur sowie einer Struktur mit einem eingebetteten Array.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-150">This sample demonstrates how to pass a structure that points to a second structure, pass a structure with an embedded structure, and pass a structure with an embedded array.</span></span>  
  
<span data-ttu-id="a5a4e-151">Das Beispiel für Strukturen verwendet die folgenden nicht verwalteten Funktionen, die jeweils zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="a5a4e-151">The Structs sample uses the following unmanaged functions, shown with their original function declaration:</span></span>

- <span data-ttu-id="a5a4e-152">**TestStructInStruct** aus „PinvokeLib.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-152">**TestStructInStruct** exported from PinvokeLib.dll.</span></span>

    ```cpp
    int TestStructInStruct(MYPERSON2* pPerson2);
    ```

- <span data-ttu-id="a5a4e-153">**TestStructInStruct3** aus „PinvokeLib.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-153">**TestStructInStruct3** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestStructInStruct3(MYPERSON3 person3);
    ```

- <span data-ttu-id="a5a4e-154">**TestStructInStruct** aus „PinvokeLib.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-154">**TestArrayInStruct** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestArrayInStruct(MYARRAYSTRUCT* pStruct);
    ```

<span data-ttu-id="a5a4e-155">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) ist eine benutzerdefinierte, nicht verwaltete Bibliothek, die Implementierungen für die zuvor aufgelisteten Funktionen und vier Strukturen enthält: **MYPERSON**, **MYPERSON2**, **MYPERSON3** und **MYARRAYSTRUCT**.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-155">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains implementations for the previously listed functions and four structures: **MYPERSON**, **MYPERSON2**, **MYPERSON3**, and **MYARRAYSTRUCT**.</span></span> <span data-ttu-id="a5a4e-156">Diese Strukturen enthalten die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="a5a4e-156">These structures contain the following elements:</span></span>

```cpp
typedef struct _MYPERSON
{
   char* first;
   char* last;
} MYPERSON, *LP_MYPERSON;

typedef struct _MYPERSON2
{
   MYPERSON* person;
   int age;
} MYPERSON2, *LP_MYPERSON2;

typedef struct _MYPERSON3
{
   MYPERSON person;
   int age;
} MYPERSON3;

typedef struct _MYARRAYSTRUCT
{
   bool flag;
   int vals[ 3 ];
} MYARRAYSTRUCT;
```

<span data-ttu-id="a5a4e-157">Die verwalteten Strukturen `MyPerson`, `MyPerson2`, `MyPerson3` und `MyArrayStruct` besitzen folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="a5a4e-157">The managed `MyPerson`, `MyPerson2`, `MyPerson3`, and `MyArrayStruct` structures have the following characteristic:</span></span>

- <span data-ttu-id="a5a4e-158">`MyPerson` enthält nur Zeichenfolgenmember.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-158">`MyPerson` contains only string members.</span></span> <span data-ttu-id="a5a4e-159">Das [CharSet](specifying-a-character-set.md)-Feld legt die Zeichenfolgen auf das ANSI-Format fest, wenn sie an die nicht verwaltete Funktion übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-159">The [CharSet](specifying-a-character-set.md) field sets the strings to ANSI format when passed to the unmanaged function.</span></span>

- <span data-ttu-id="a5a4e-160">`MyPerson2` enthält eine **IntPtr** in der `MyPerson`-Struktur.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-160">`MyPerson2` contains an **IntPtr** to the `MyPerson` structure.</span></span> <span data-ttu-id="a5a4e-161">Der **IntPtr**-Typ ersetzt den ursprünglichen Zeiger auf die nicht verwaltete Struktur, weil .NET Framework-Anwendungen nur dann Zeiger verwenden, wenn der Code als **unsicher** gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-161">The **IntPtr** type replaces the original pointer to the unmanaged structure because .NET Framework applications do not use pointers unless the code is marked **unsafe**.</span></span>

- <span data-ttu-id="a5a4e-162">`MyPerson3` enthält `MyPerson` als eingebettete Struktur.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-162">`MyPerson3` contains `MyPerson` as an embedded structure.</span></span> <span data-ttu-id="a5a4e-163">Eine in eine Struktur eingebettete andere Struktur kann vereinfacht werden, indem die Elemente der eingebetteten Struktur direkt in der Hauptstruktur platziert werden. Alternativ kann die Struktur auch eingebettet bleiben, wie in diesem Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-163">A structure embedded within another structure can be flattened by placing the elements of the embedded structure directly into the main structure, or it can be left as an embedded structure, as is done in this sample.</span></span>

- <span data-ttu-id="a5a4e-164">`MyArrayStruct` enthält ein Array von ganzen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-164">`MyArrayStruct` contains an array of integers.</span></span> <span data-ttu-id="a5a4e-165">Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut legt den <xref:System.Runtime.InteropServices.UnmanagedType>-Enumerationswert auf **ByValArray** fest, womit die Anzahl der Elemente im Array angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-165">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration value to **ByValArray**, which is used to indicate the number of elements in the array.</span></span>

<span data-ttu-id="a5a4e-166">Für alle Strukturen in diesem Beispiel wird das <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut angewendet, um sicherzustellen, dass die Member im Speicher sequenziell in der Reihenfolge ihres Auftretens angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-166">For all structures in this sample, the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is applied to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>

<span data-ttu-id="a5a4e-167">Die `NativeMethods`-Klasse enthält verwaltete Prototypen für die Methoden `TestStructInStruct`, `TestStructInStruct3` und `TestArrayInStruct`, die von der `App`-Klasse aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-167">The `NativeMethods` class contains managed prototypes for the `TestStructInStruct`, `TestStructInStruct3`, and `TestArrayInStruct` methods called by the `App` class.</span></span> <span data-ttu-id="a5a4e-168">Jeder Prototyp deklariert einen einzelnen Parameter wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a5a4e-168">Each prototype declares a single parameter, as follows:</span></span>

- <span data-ttu-id="a5a4e-169">`TestStructInStruct` deklariert einen Verweis auf den Typ `MyPerson2` als ihren Parameter.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-169">`TestStructInStruct` declares a reference to type `MyPerson2` as its parameter.</span></span>

- <span data-ttu-id="a5a4e-170">`TestStructInStruct3` deklariert den Typ `MyPerson3` als ihren Parameter und übergibt den Parameter als Wert.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-170">`TestStructInStruct3` declares type `MyPerson3` as its parameter and passes the parameter by value.</span></span>

- <span data-ttu-id="a5a4e-171">`TestArrayInStruct` deklariert einen Verweis auf den Typ `MyArrayStruct` als ihren Parameter.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-171">`TestArrayInStruct` declares a reference to type `MyArrayStruct` as its parameter.</span></span>

<span data-ttu-id="a5a4e-172">Strukturen als Argumente von Methoden werden als Wert übergeben, es sei denn, der Parameter enthält das **Ref**-Schlüsselwort (**ByRef** in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="a5a4e-172">Structures as arguments to methods are passed by value unless the parameter contains the **ref** (**ByRef** in Visual Basic) keyword.</span></span> <span data-ttu-id="a5a4e-173">Zum Beispiel übergibt die `TestStructInStruct`-Methode einen Verweis (den Wert einer Adresse) auf ein Objekt vom Typ `MyPerson2` an nicht verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-173">For example, the `TestStructInStruct` method passes a reference (the value of an address) to an object of type `MyPerson2` to unmanaged code.</span></span> <span data-ttu-id="a5a4e-174">Um die Struktur zu bearbeiten, auf die `MyPerson2` zeigt, erstellt das Beispiel einen Puffer einer angegebenen Größe und gibt dessen Adresse zurück, indem die Methoden <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> und <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-174">To manipulate the structure that `MyPerson2` points to, the sample creates a buffer of a specified size and returns its address by combining the <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="a5a4e-175">Anschließend kopiert das Beispiel den Inhalt der verwalteten Struktur in den nicht verwalteten Puffer.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-175">Next, the sample copies the content of the managed structure to the unmanaged buffer.</span></span> <span data-ttu-id="a5a4e-176">Zum Schluss verwendet das Beispiel die <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType>-Methode für das Marshalling von Daten aus dem nicht verwalteten Puffer in ein verwaltetes Objekt sowie die <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType>-Methode, um den nicht verwalteten Speicherblock freizugeben.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-176">Finally, the sample uses the <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> method to marshal data from the unmanaged buffer to a managed object and the <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> method to free the unmanaged block of memory.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="a5a4e-177">Deklarieren von Prototypen</span><span class="sxs-lookup"><span data-stu-id="a5a4e-177">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#23](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#23)]
[!code-csharp[Conceptual.Interop.Marshaling#23](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#23)]
[!code-vb[Conceptual.Interop.Marshaling#23](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#23)]

### <a name="calling-functions"></a><span data-ttu-id="a5a4e-178">Aufrufen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="a5a4e-178">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#24](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#24)]
[!code-csharp[Conceptual.Interop.Marshaling#24](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#24)]
[!code-vb[Conceptual.Interop.Marshaling#24](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#24)]

## <a name="findfile-sample"></a><span data-ttu-id="a5a4e-179">FindFile-Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5a4e-179">FindFile sample</span></span>

<span data-ttu-id="a5a4e-180">Dieses Beispiel demonstriert, wie eine Struktur, die eine zweite, eingebettete Struktur enthält, an eine nicht verwaltete Funktion übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-180">This sample demonstrates how to pass a structure that contains a second, embedded structure to an unmanaged function.</span></span> <span data-ttu-id="a5a4e-181">Außerdem wird veranschaulicht, wie Sie das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut verwenden, um ein Arrays mit fester Länge innerhalb der Struktur zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-181">It also demonstrates how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to declare a fixed-length array within the structure.</span></span> <span data-ttu-id="a5a4e-182">In diesem Beispiel werden die Elemente der eingebetteten Struktur der übergeordneten Struktur hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-182">In this sample, the embedded structure elements are added to the parent structure.</span></span> <span data-ttu-id="a5a4e-183">Ein Beispiel für eine nicht vereinfachte eingebettete Struktur finden Sie unter [Beispiel für Strukturen](/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="a5a4e-183">For a sample of an embedded structure that is not flattened, see [Structures Sample](/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100)).</span></span>

<span data-ttu-id="a5a4e-184">Das "FindFile"-Beispiel verwendet die folgende nicht verwaltete Funktion, die zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="a5a4e-184">The FindFile sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="a5a4e-185">**FindFirstFile** aus „Kernel32.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-185">**FindFirstFile** exported from Kernel32.dll.</span></span>

    ```cpp
    HANDLE FindFirstFile(LPCTSTR lpFileName, LPWIN32_FIND_DATA lpFindFileData);
    ```

<span data-ttu-id="a5a4e-186">Die ursprüngliche, an die Funktion übergebene Struktur enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="a5a4e-186">The original structure passed to the function contains the following elements:</span></span>

```cpp
typedef struct _WIN32_FIND_DATA
{
  DWORD    dwFileAttributes;
  FILETIME ftCreationTime;
  FILETIME ftLastAccessTime;
  FILETIME ftLastWriteTime;
  DWORD    nFileSizeHigh;
  DWORD    nFileSizeLow;
  DWORD    dwReserved0;
  DWORD    dwReserved1;
  TCHAR    cFileName[ MAX_PATH ];
  TCHAR    cAlternateFileName[ 14 ];
} WIN32_FIND_DATA, *PWIN32_FIND_DATA;
```

<span data-ttu-id="a5a4e-187">In diesem Beispiel enthält die `FindData`-Klasse einen entsprechenden Datenmember für jedes Element der Originalstruktur und der eingebetteten Struktur.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-187">In this sample, the `FindData` class contains a corresponding data member for each element of the original structure and the embedded structure.</span></span> <span data-ttu-id="a5a4e-188">Anstelle zweier ursprünglicher Zeichenpuffer ersetzt die Klasse Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-188">In place of two original character buffers, the class substitutes strings.</span></span> <span data-ttu-id="a5a4e-189">Das **MarshalAsAttribute**-Attribut legt die <xref:System.Runtime.InteropServices.UnmanagedType>-Enumeration auf **ByValTStr** fest. Dieser Wert wird zum Identifizieren der Inlinezeichenarrays mit fester Länge verwendet, die innerhalb der nicht verwalteten Strukturen erscheinen.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-189">**MarshalAsAttribute** sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged structures.</span></span>

<span data-ttu-id="a5a4e-190">Die `NativeMethods`-Klasse enthält einen verwalteten Prototyp der `FindFirstFile`-Methode, der die `FindData`-Klasse als Parameter übergibt.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-190">The `NativeMethods` class contains a managed prototype of the `FindFirstFile` method, which passes the `FindData` class as a parameter.</span></span> <span data-ttu-id="a5a4e-191">Der Parameter muss mit den Attributen <xref:System.Runtime.InteropServices.InAttribute> und <xref:System.Runtime.InteropServices.OutAttribute> deklariert werden, weil Klassen, die Verweistypen sind, standardmäßig als In-Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-191">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="a5a4e-192">Deklarieren von Prototypen</span><span class="sxs-lookup"><span data-stu-id="a5a4e-192">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#17](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#17)]
[!code-csharp[Conceptual.Interop.Marshaling#17](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#17)]
[!code-vb[Conceptual.Interop.Marshaling#17](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#17)]

### <a name="calling-functions"></a><span data-ttu-id="a5a4e-193">Aufrufen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="a5a4e-193">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#18](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#18)]
[!code-csharp[Conceptual.Interop.Marshaling#18](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#18)]
 [!code-vb[Conceptual.Interop.Marshaling#18](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#18)]

## <a name="unions-sample"></a><span data-ttu-id="a5a4e-194">Unions-Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5a4e-194">Unions sample</span></span>

<span data-ttu-id="a5a4e-195">Dieses Beispiel veranschaulicht, wie Strukturen, die nur Werttypen enthalten, sowie Strukturen, die einen Werttyp und eine Zeichenfolge enthalten, als Parameter an eine nicht verwaltete Funktion übergeben werden, die eine Union erwartet.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-195">This sample demonstrates how to pass structures containing only value types, and structures containing a value type and a string as parameters to an unmanaged function expecting a union.</span></span> <span data-ttu-id="a5a4e-196">Eine Union stellt einen Speicherbereich dar, der von zwei oder mehr Variablen gemeinsam genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-196">A union represents a memory location that can be shared by two or more variables.</span></span>

<span data-ttu-id="a5a4e-197">Das "Unions"-Beispiel verwendet die folgende nicht verwaltete Funktion, die zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="a5a4e-197">The Unions sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="a5a4e-198">**TestUnion** aus „PinvokeLib.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-198">**TestUnion** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestUnion(MYUNION u, int type);
    ```

<span data-ttu-id="a5a4e-199">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) ist eine benutzerdefinierte, nicht verwaltete Bibliothek, die eine Implementierung für die zuvor aufgelistete Funktion und zwei Unions enthält: **MYUNION** und **MYUNION2**.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-199">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains an implementation for the previously listed function and two unions, **MYUNION** and **MYUNION2**.</span></span> <span data-ttu-id="a5a4e-200">Die Union enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="a5a4e-200">The unions contain the following elements:</span></span>

```cpp
union MYUNION
{
    int number;
    double d;
}

union MYUNION2
{
    int i;
    char str[128];
};
```

<span data-ttu-id="a5a4e-201">In verwaltetem Code sind Unions als Strukturen definiert.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-201">In managed code, unions are defined as structures.</span></span> <span data-ttu-id="a5a4e-202">Die `MyUnion`-Struktur enthält zwei Werttypen als Member: einen Integer- und einen Double-Wert.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-202">The `MyUnion` structure contains two value types as its members: an integer and a double.</span></span> <span data-ttu-id="a5a4e-203">Das <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut wird festgelegt, um die genaue Position der einzelnen Datenmember zu kontrollieren.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-203">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to control the precise position of each data member.</span></span> <span data-ttu-id="a5a4e-204">Das <xref:System.Runtime.InteropServices.FieldOffsetAttribute>-Attribut stellt die physische Position von Feldern innerhalb der nicht verwalteten Darstellung einer Union bereit.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-204">The <xref:System.Runtime.InteropServices.FieldOffsetAttribute> attribute provides the physical position of fields within the unmanaged representation of a union.</span></span> <span data-ttu-id="a5a4e-205">Beachten Sie, dass beide Member denselben Offsetwert besitzen, sodass die Member denselben Speicherbereich definieren können.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-205">Notice that both members have the same offset values, so the members can define the same piece of memory.</span></span>

<span data-ttu-id="a5a4e-206">`MyUnion2_1` und `MyUnion2_2` enthalten einen Werttyp (Integer) bzw. eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-206">`MyUnion2_1` and `MyUnion2_2` contain a value type (integer) and a string, respectively.</span></span> <span data-ttu-id="a5a4e-207">In verwaltetem Code dürfen Werttypen und Verweistypen nicht überlappen.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-207">In managed code, value types and reference types are not permitted to overlap.</span></span> <span data-ttu-id="a5a4e-208">Dieses Beispiel verwendet das Überladen von Methoden, um dem Aufrufer die Verwendung beider Typen zu ermöglichen, wenn dieselbe nicht verwaltete Funktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-208">This sample uses method overloading to enable the caller to use both types when calling the same unmanaged function.</span></span> <span data-ttu-id="a5a4e-209">Das Layout von `MyUnion2_1` ist explizit und besitzt einen genauen Offsetwert.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-209">The layout of `MyUnion2_1` is explicit and has a precise offset value.</span></span> <span data-ttu-id="a5a4e-210">Im Gegensatz dazu verfügt `MyUnion2_2` über ein sequenzielles Layout, da explizite Layouts für Verweistypen nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-210">In contrast, `MyUnion2_2` has a sequential layout, because explicit layouts are not permitted with reference types.</span></span> <span data-ttu-id="a5a4e-211">Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut legt die <xref:System.Runtime.InteropServices.UnmanagedType>-Enumeration auf **ByValTStr** fest. Dieser Wert wird zum Identifizieren der Inlinezeichenarrays mit fester Länge verwendet, die innerhalb der nicht verwalteten Darstellung der Union erscheinen.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-211">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged representation of the union.</span></span>

<span data-ttu-id="a5a4e-212">Die `NativeMethods`-Klasse enthält die Prototypen für die Methoden `TestUnion` und `TestUnion2`.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-212">The `NativeMethods` class contains the prototypes for the `TestUnion` and `TestUnion2` methods.</span></span> <span data-ttu-id="a5a4e-213">`TestUnion2` wird überladen, um `MyUnion2_1` oder `MyUnion2_2` als Parameter zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-213">`TestUnion2` is overloaded to declare `MyUnion2_1` or `MyUnion2_2` as parameters.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="a5a4e-214">Deklarieren von Prototypen</span><span class="sxs-lookup"><span data-stu-id="a5a4e-214">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#28](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#28)]
[!code-csharp[Conceptual.Interop.Marshaling#28](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#28)]
[!code-vb[Conceptual.Interop.Marshaling#28](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#28)]

### <a name="calling-functions"></a><span data-ttu-id="a5a4e-215">Aufrufen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="a5a4e-215">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#29](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#29)]
[!code-csharp[Conceptual.Interop.Marshaling#29](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#29)]
[!code-vb[Conceptual.Interop.Marshaling#29](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#29)]

## <a name="platform-sample"></a><span data-ttu-id="a5a4e-216">Plattformbeispiel</span><span class="sxs-lookup"><span data-stu-id="a5a4e-216">Platform sample</span></span>

<span data-ttu-id="a5a4e-217">In einigen Szenarios können sich die Layouts `struct` und `union` abhängig von der Zielplattform unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-217">In some scenarios, `struct` and `union` layouts can differ depending on the targeted platform.</span></span> <span data-ttu-id="a5a4e-218">Beachten Sie zum Beispiel den [`STRRET`](/windows/win32/api/shtypes/ns-shtypes-strret)-Typ, wenn er in einem COM-Szenario definiert ist:</span><span class="sxs-lookup"><span data-stu-id="a5a4e-218">For example, consider the [`STRRET`](/windows/win32/api/shtypes/ns-shtypes-strret) type when defined in a COM scenario:</span></span>

```c++
#include <pshpack8.h> /* Defines the packing of the struct */
typedef struct _STRRET
    {
    UINT uType;
    /* [switch_is][switch_type] */ union
        {
        /* [case()][string] */ LPWSTR pOleStr;
        /* [case()] */ UINT uOffset;
        /* [case()] */ char cStr[ 260 ];
        }  DUMMYUNIONNAME;
    }  STRRET;
#include <poppack.h>
```

<span data-ttu-id="a5a4e-219">Das obige `struct`-Layout wird mit Windows-Headern deklariert, die das Arbeitsspeicherlayout des Typs beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-219">The above `struct` is declared with Windows' headers that influence the memory layout of the type.</span></span> <span data-ttu-id="a5a4e-220">Wenn sie in einer verwalteten Umgebung definiert sind, werden diese Layoutdetails benötigt, um ordnungsgemäß mit nativem Code zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-220">When defined in a managed environment, these layout details are needed to properly interoperate with native code.</span></span>

<span data-ttu-id="a5a4e-221">Die korrekte verwaltete Definition dieses Typs in einem 32-Bit-Prozess lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a5a4e-221">The correct managed definition of this type in a 32-bit process is:</span></span>

``` CSharp
[StructLayout(LayoutKind.Explicit, Size = 264)]
public struct STRRET_32
{
    [FieldOffset(0)]
    public uint uType;

    [FieldOffset(4)]
    public IntPtr pOleStr;

    [FieldOffset(4)]
    public uint uOffset;

    [FieldOffset(4)]
    public IntPtr cStr;
}
```

<span data-ttu-id="a5a4e-222">Bei einem 64-Bit-Prozess unterscheiden sich die Größen- *und* Feldoffsets.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-222">On a 64-bit process, the size *and* field offsets are different.</span></span> <span data-ttu-id="a5a4e-223">Das korrekte Layout sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="a5a4e-223">The correct layout is:</span></span>

``` CSharp
[StructLayout(LayoutKind.Explicit, Size = 272)]
public struct STRRET_64
{
    [FieldOffset(0)]
    public uint uType;

    [FieldOffset(8)]
    public IntPtr pOleStr;

    [FieldOffset(8)]
    public uint uOffset;

    [FieldOffset(8)]
    public IntPtr cStr;
}
```

<span data-ttu-id="a5a4e-224">Wenn Sie das native Layout in einem Interopszenario nicht genau beachten, kann dies zu zufälligen Abstürzen oder zu schlechteren falschen Berechnungen führen.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-224">Failure to properly consider the native layout in an interop scenario can result in random crashes or worse, incorrect computations.</span></span>

<span data-ttu-id="a5a4e-225">In der Standardeinstellung können .NET-Assemblys sowohl in der 32-Bit- als auch der 64-Bit-Version der .NET-Runtime ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-225">By default, .NET assemblies can run in both a 32-bit and 64-bit version of the .NET runtime.</span></span> <span data-ttu-id="a5a4e-226">Die App muss bis zur Laufzeit warten, um zu entscheiden, welche der vorherigen Definitionen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-226">The app must wait until run time to decide which of the previous definitions to use.</span></span>

<span data-ttu-id="a5a4e-227">Der folgende Codeausschnitt zeigt ein Beispiel für die Wahl zwischen der 32-Bit- und der 64-Bit-Definition zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-227">The following code snippet shows an example of how to choose between the 32-bit and 64-bit definition at run time.</span></span>

```csharp
if (IntPtr.Size == 8)
{
    // Use the STRRET_64 definition
}
else
{
    Debug.Assert(IntPtr.Size == 4);
    // Use the STRRET_32 definition
}
```

## <a name="systime-sample"></a><span data-ttu-id="a5a4e-228">SysTime-Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5a4e-228">SysTime sample</span></span>

<span data-ttu-id="a5a4e-229">Dieses Beispiel demonstriert, wie ein Zeiger auf eine Klasse an eine nicht verwaltete Funktion übergeben wird, die einen Zeiger auf eine Struktur erwartet.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-229">This sample demonstrates how to pass a pointer to a class to an unmanaged function that expects a pointer to a structure.</span></span>

<span data-ttu-id="a5a4e-230">Das "SysTime"-Beispiel verwendet die folgende nicht verwaltete Funktion, die zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="a5a4e-230">The SysTime sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="a5a4e-231">**GetSystemTime** aus Kernel32.dll exportiert.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-231">**GetSystemTime** exported from Kernel32.dll.</span></span>

    ```cpp
    VOID GetSystemTime(LPSYSTEMTIME lpSystemTime);
    ```

<span data-ttu-id="a5a4e-232">Die ursprüngliche, an die Funktion übergebene Struktur enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="a5a4e-232">The original structure passed to the function contains the following elements:</span></span>

```cpp
typedef struct _SYSTEMTIME {
    WORD wYear;
    WORD wMonth;
    WORD wDayOfWeek;
    WORD wDay;
    WORD wHour;
    WORD wMinute;
    WORD wSecond;
    WORD wMilliseconds;
} SYSTEMTIME, *PSYSTEMTIME;
```

<span data-ttu-id="a5a4e-233">In diesem Beispiel enthält die `SystemTime`-Klasse die Elemente der Originalstruktur, die als Klassenelemente dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-233">In this sample, the `SystemTime` class contains the elements of the original structure represented as class members.</span></span> <span data-ttu-id="a5a4e-234">Das <xref:System.Runtime.InteropServices.StructLayoutAttribute> -Attribut ist so eingerichtet, dass sichergestellt wird, dass die Member im Speicher sequenziell in der Reihenfolge ihres Erscheinens angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-234">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>

<span data-ttu-id="a5a4e-235">Die `NativeMethods`-Klasse enthält einen verwalteten Prototyp der `GetSystemTime`-Methode, der die `SystemTime`-Klasse standardmäßig als In/Out-Parameter übergibt.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-235">The `NativeMethods` class contains a managed prototype of the `GetSystemTime` method, which passes the `SystemTime` class as an In/Out parameter by default.</span></span> <span data-ttu-id="a5a4e-236">Der Parameter muss mit den Attributen <xref:System.Runtime.InteropServices.InAttribute> und <xref:System.Runtime.InteropServices.OutAttribute> deklariert werden, weil Klassen, die Verweistypen sind, standardmäßig als In-Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-236">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span> <span data-ttu-id="a5a4e-237">Damit der Aufrufer die Ergebnisse empfängt, müssen diese [direktionalen Attribute](/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) explizit angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-237">For the caller to receive the results, these [directional attributes](/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) must be applied explicitly.</span></span> <span data-ttu-id="a5a4e-238">Die `App`-Klasse erstellt eine neue Instanz der `SystemTime`-Klasse und greift auf deren Datenfelder zu.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-238">The `App` class creates a new instance of the `SystemTime` class and accesses its data fields.</span></span>

### <a name="code-samples"></a><span data-ttu-id="a5a4e-239">Codebeispiele</span><span class="sxs-lookup"><span data-stu-id="a5a4e-239">Code Samples</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#25](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/systime.cpp#25)]
[!code-csharp[Conceptual.Interop.Marshaling#25](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/systime.cs#25)]
[!code-vb[Conceptual.Interop.Marshaling#25](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/systime.vb#25)]

## <a name="outarrayofstructs-sample"></a><span data-ttu-id="a5a4e-240">OutArrayOfStructs-Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5a4e-240">OutArrayOfStructs sample</span></span>

<span data-ttu-id="a5a4e-241">Dieses Beispiel veranschaulicht, wie ein Array von Strukturen, das Integer- und String-Werte als Out-Parameter enthält, an eine nicht verwaltete Funktionen übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-241">This sample shows how to pass an array of structures that contains integers and strings as Out parameters to an unmanaged function.</span></span>

<span data-ttu-id="a5a4e-242">In diesem Beispiel wird veranschaulicht, wie eine systemeigene Funktion unter Verwendung der <xref:System.Runtime.InteropServices.Marshal>-Klasse und mithilfe von unsicherem Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-242">This sample demonstrates how to call a native function by using the <xref:System.Runtime.InteropServices.Marshal> class and by using unsafe code.</span></span>

<span data-ttu-id="a5a4e-243">Dieses Beispiel verwendet eine Wrapperfunktion und Plattformaufrufe, die in [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) definiert sind und auch in den Quelldateien bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-243">This sample uses a wrapper functions and platform invokes defined in [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll), also provided in the source files.</span></span> <span data-ttu-id="a5a4e-244">Es verwendet die `TestOutArrayOfStructs`-Funktion und die `MYSTRSTRUCT2`-Struktur.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-244">It uses the `TestOutArrayOfStructs` function and the `MYSTRSTRUCT2` structure.</span></span> <span data-ttu-id="a5a4e-245">Die Struktur enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="a5a4e-245">The structure contains the following elements:</span></span>

```cpp
typedef struct _MYSTRSTRUCT2
{
   char* buffer;
   UINT size;
} MYSTRSTRUCT2;
```

<span data-ttu-id="a5a4e-246">Die `MyStruct`-Klasse enthält ein Zeichenfolgenobjekt aus ANSI-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-246">The `MyStruct` class contains a string object of ANSI characters.</span></span> <span data-ttu-id="a5a4e-247">Das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>-Feld gibt das ANSI-Format an.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-247">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> field specifies ANSI format.</span></span> <span data-ttu-id="a5a4e-248">`MyUnsafeStruct` ist eine Struktur, die einen <xref:System.IntPtr>-Typ anstelle einer Zeichenfolge enthält.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-248">`MyUnsafeStruct`, is a structure containing an <xref:System.IntPtr> type instead of a string.</span></span>

<span data-ttu-id="a5a4e-249">Die `NativeMethods`-Klasse enthält die überladene `TestOutArrayOfStructs`-Prototypenmethode.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-249">The `NativeMethods` class contains the overloaded `TestOutArrayOfStructs` prototype method.</span></span> <span data-ttu-id="a5a4e-250">Wenn eine Methode einen Zeiger als Parameter deklariert, sollte die Klasse mit dem `unsafe`-Schlüsselwort markiert werden.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-250">If a method declares a pointer as a parameter, the class should be marked with the `unsafe` keyword.</span></span> <span data-ttu-id="a5a4e-251">Da Visual Basic keinen unsicheren Code verwenden kann, sind die überladene Methode, der „unsafe“-Modifizierer und die `MyUnsafeStruct`-Struktur nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-251">Because Visual Basic cannot use unsafe code, the overloaded method, unsafe modifier, and the `MyUnsafeStruct` structure are unnecessary.</span></span>

<span data-ttu-id="a5a4e-252">Die `App` -Klasse implementiert die `UsingMarshaling`-Methode, die alle Aufgaben durchführt, die zum Übergeben des Arrays erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-252">The `App` class implements the `UsingMarshaling` method, which performs all the tasks necessary to pass the array.</span></span> <span data-ttu-id="a5a4e-253">Das Array wird mit dem `out`-Schlüsselwort (`ByRef` in Visual Basic) markiert, um anzuzeigen, dass Daten vom Aufgerufenen an den Aufrufer übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-253">The array is marked with the `out` (`ByRef` in Visual Basic) keyword to indicate that data passes from callee to caller.</span></span> <span data-ttu-id="a5a4e-254">Die Implementierung verwendet die folgenden <xref:System.Runtime.InteropServices.Marshal>-Klassenmethoden:</span><span class="sxs-lookup"><span data-stu-id="a5a4e-254">The implementation uses the following <xref:System.Runtime.InteropServices.Marshal> class methods:</span></span>

- <span data-ttu-id="a5a4e-255"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> für das Marshalling von Daten aus dem nicht verwalteten Speicherblock zu einem verwalteten Objekt.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-255"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> to marshal data from the unmanaged buffer to a managed object.</span></span>

- <span data-ttu-id="a5a4e-256"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> zum Freigeben des für Zeichenfolgen in der Struktur reservierten Speichers.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-256"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> to release the memory reserved for strings in the structure.</span></span>

- <span data-ttu-id="a5a4e-257"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> zum Freigeben des für das Array reservierten Speichers.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-257"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> to release the memory reserved for the array.</span></span>

<span data-ttu-id="a5a4e-258">Wie zuvor erwähnt, lässt C# unsicheren Code zu, und Visual Basic nicht.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-258">As previously mentioned, C# allows unsafe code and Visual Basic does not.</span></span> <span data-ttu-id="a5a4e-259">In dem C#-Beispiel ist `UsingUnsafePointer` eine alternative Methodenimplementierung, die Zeiger anstelle der <xref:System.Runtime.InteropServices.Marshal>-Klasse verwendet, um das Array, das die `MyUnsafeStruct`-Struktur enthält, zurück zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="a5a4e-259">In the C# sample, `UsingUnsafePointer` is an alternative method implementation that uses pointers instead of the <xref:System.Runtime.InteropServices.Marshal> class to pass back the array containing the `MyUnsafeStruct` structure.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="a5a4e-260">Deklarieren von Prototypen</span><span class="sxs-lookup"><span data-stu-id="a5a4e-260">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#20](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#20)]
[!code-csharp[Conceptual.Interop.Marshaling#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#20)]
[!code-vb[Conceptual.Interop.Marshaling#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#20)]

### <a name="calling-functions"></a><span data-ttu-id="a5a4e-261">Aufrufen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="a5a4e-261">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#21](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#21)]
[!code-csharp[Conceptual.Interop.Marshaling#21](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#21)]
[!code-vb[Conceptual.Interop.Marshaling#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#21)]

## <a name="see-also"></a><span data-ttu-id="a5a4e-262">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5a4e-262">See also</span></span>

- [<span data-ttu-id="a5a4e-263">Marshallen von Daten mit Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="a5a4e-263">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
- [<span data-ttu-id="a5a4e-264">Marshallen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="a5a4e-264">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="a5a4e-265">Maushallen verschiedener Typen von Arrays</span><span class="sxs-lookup"><span data-stu-id="a5a4e-265">Marshaling Different Types of Arrays</span></span>](marshaling-different-types-of-arrays.md)
