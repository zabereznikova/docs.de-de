---
title: Marshallen von Klassen, Strukturen und Unions
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
ms.openlocfilehash: 708ed6a232950cb69796f105f6f198749ed53a24
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "82200014"
---
# <a name="marshaling-classes-structures-and-unions"></a><span data-ttu-id="babd9-102">Marshallen von Klassen, Strukturen und Unions</span><span class="sxs-lookup"><span data-stu-id="babd9-102">Marshaling Classes, Structures, and Unions</span></span>

<span data-ttu-id="babd9-103">Klassen und Strukturen sind in .NET Framework ähnlich.</span><span class="sxs-lookup"><span data-stu-id="babd9-103">Classes and structures are similar in the .NET Framework.</span></span> <span data-ttu-id="babd9-104">Beide können Felder, Eigenschaften und Ereignisse enthalten.</span><span class="sxs-lookup"><span data-stu-id="babd9-104">Both can have fields, properties, and events.</span></span> <span data-ttu-id="babd9-105">Sie können auch über statische und nicht statische Methoden verfügen.</span><span class="sxs-lookup"><span data-stu-id="babd9-105">They can also have static and nonstatic methods.</span></span> <span data-ttu-id="babd9-106">Ein deutlicher Unterschied ist, dass Strukturen Werttypen sind, während Klassen Verweistypen sind.</span><span class="sxs-lookup"><span data-stu-id="babd9-106">One notable difference is that structures are value types and classes are reference types.</span></span>

<span data-ttu-id="babd9-107">In der folgende Tabelle werden Marshallingoptionen für Klassen, Strukturen und Unions aufgelistet. Ihre Verwendung wird beschrieben, und es werden Links zu den entsprechenden Plattformaufrufbeispielen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="babd9-107">The following table lists marshaling options for classes, structures, and unions; describes their usage; and provides a link to the corresponding platform invoke sample.</span></span>

|<span data-ttu-id="babd9-108">Typ</span><span class="sxs-lookup"><span data-stu-id="babd9-108">Type</span></span>|<span data-ttu-id="babd9-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="babd9-109">Description</span></span>|<span data-ttu-id="babd9-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="babd9-110">Sample</span></span>|
|----------|-----------------|------------|
|<span data-ttu-id="babd9-111">Klasse als Wert.</span><span class="sxs-lookup"><span data-stu-id="babd9-111">Class by value.</span></span>|<span data-ttu-id="babd9-112">Übergibt eine Klasse mit ganzzahligen Membern als In/Out-Parameter, wie der verwaltete Fall.</span><span class="sxs-lookup"><span data-stu-id="babd9-112">Passes a class with integer members as an In/Out parameter, like the managed case.</span></span>|[<span data-ttu-id="babd9-113">SysTime-Beispiel</span><span class="sxs-lookup"><span data-stu-id="babd9-113">SysTime sample</span></span>](#systime-sample)|
|<span data-ttu-id="babd9-114">Struktur als Wert.</span><span class="sxs-lookup"><span data-stu-id="babd9-114">Structure by value.</span></span>|<span data-ttu-id="babd9-115">Übergibt Strukturen als In-Parameter.</span><span class="sxs-lookup"><span data-stu-id="babd9-115">Passes structures as In parameters.</span></span>|[<span data-ttu-id="babd9-116">Beispiel für Strukturen</span><span class="sxs-lookup"><span data-stu-id="babd9-116">Structures sample</span></span>](#structures-sample)|
|<span data-ttu-id="babd9-117">Struktur als Verweis.</span><span class="sxs-lookup"><span data-stu-id="babd9-117">Structure by reference.</span></span>|<span data-ttu-id="babd9-118">Übergibt Strukturen als In/Out-Parameter.</span><span class="sxs-lookup"><span data-stu-id="babd9-118">Passes structures as In/Out parameters.</span></span>|<span data-ttu-id="babd9-119">[OSInfo-Beispiel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="babd9-119">[OSInfo sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))</span></span>|
|<span data-ttu-id="babd9-120">Struktur mit geschachtelten Strukturen (vereinfacht).</span><span class="sxs-lookup"><span data-stu-id="babd9-120">Structure with nested structures (flattened).</span></span>|<span data-ttu-id="babd9-121">Übergibt eine Klasse, die eine Struktur mit geschachtelten Strukturen in der nicht verwalteten Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="babd9-121">Passes a class that represents a structure with nested structures in the unmanaged function.</span></span> <span data-ttu-id="babd9-122">Die Struktur wird zu einer einzigen großen Struktur im verwalteten Prototyp vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="babd9-122">The structure is flattened to one big structure in the managed prototype.</span></span>|[<span data-ttu-id="babd9-123">FindFile-Beispiel</span><span class="sxs-lookup"><span data-stu-id="babd9-123">FindFile sample</span></span>](#findfile-sample)|
|<span data-ttu-id="babd9-124">Struktur mit einem Zeiger auf eine andere Struktur.</span><span class="sxs-lookup"><span data-stu-id="babd9-124">Structure with a pointer to another structure.</span></span>|<span data-ttu-id="babd9-125">Übergibt eine Struktur, die einen Zeiger auf eine zweite Struktur enthält, als Member.</span><span class="sxs-lookup"><span data-stu-id="babd9-125">Passes a structure that contains a pointer to a second structure as a member.</span></span>|[<span data-ttu-id="babd9-126">Beispiel für Strukturen</span><span class="sxs-lookup"><span data-stu-id="babd9-126">Structures Sample</span></span>](#structures-sample)|
|<span data-ttu-id="babd9-127">Array von Strukturen mit ganzen Zahlen als Wert.</span><span class="sxs-lookup"><span data-stu-id="babd9-127">Array of structures with integers by value.</span></span>|<span data-ttu-id="babd9-128">Übergibt ein aus Strukturen bestehendes Array, das nur ganze Zahlen enthält, als In-/Out-Parameter.</span><span class="sxs-lookup"><span data-stu-id="babd9-128">Passes an array of structures that contain only integers as an In/Out parameter.</span></span> <span data-ttu-id="babd9-129">Member des Arrays können geändert werden.</span><span class="sxs-lookup"><span data-stu-id="babd9-129">Members of the array can be changed.</span></span>|[<span data-ttu-id="babd9-130">Beispiel für Arrays</span><span class="sxs-lookup"><span data-stu-id="babd9-130">Arrays Sample</span></span>](marshaling-different-types-of-arrays.md)|
|<span data-ttu-id="babd9-131">Array von Strukturen mit ganzen Zahlen und Zeichenfolgen als Verweis.</span><span class="sxs-lookup"><span data-stu-id="babd9-131">Array of structures with integers and strings by reference.</span></span>|<span data-ttu-id="babd9-132">Übergibt ein Array von Strukturen, die ganze Zahlen und Zeichenfolgen enthalten, als Out-Parameter.</span><span class="sxs-lookup"><span data-stu-id="babd9-132">Passes an array of structures that contain integers and strings as an Out parameter.</span></span> <span data-ttu-id="babd9-133">Die aufgerufene Funktion weist Speicher für das Array zu.</span><span class="sxs-lookup"><span data-stu-id="babd9-133">The called function allocates memory for the array.</span></span>|[<span data-ttu-id="babd9-134">OutArrayOfStructs-Beispiel</span><span class="sxs-lookup"><span data-stu-id="babd9-134">OutArrayOfStructs Sample</span></span>](#outarrayofstructs-sample)|
|<span data-ttu-id="babd9-135">Unions mit Werttypen.</span><span class="sxs-lookup"><span data-stu-id="babd9-135">Unions with value types.</span></span>|<span data-ttu-id="babd9-136">Übergibt Unions mit Werttypen (Integer und Double).</span><span class="sxs-lookup"><span data-stu-id="babd9-136">Passes unions with value types (integer and double).</span></span>|[<span data-ttu-id="babd9-137">Unions-Beispiel</span><span class="sxs-lookup"><span data-stu-id="babd9-137">Unions sample</span></span>](#unions-sample)|
|<span data-ttu-id="babd9-138">Unions mit gemischten Typen.</span><span class="sxs-lookup"><span data-stu-id="babd9-138">Unions with mixed types.</span></span>|<span data-ttu-id="babd9-139">Übergibt Unions mit gemischten Typen (Integer und String).</span><span class="sxs-lookup"><span data-stu-id="babd9-139">Passes unions with mixed types (integer and string).</span></span>|[<span data-ttu-id="babd9-140">Unions-Beispiel</span><span class="sxs-lookup"><span data-stu-id="babd9-140">Unions sample</span></span>](#unions-sample)|
|<span data-ttu-id="babd9-141">Struktur mit plattformspezifischem Layout.</span><span class="sxs-lookup"><span data-stu-id="babd9-141">Struct with platform-specific layout.</span></span>|<span data-ttu-id="babd9-142">Übergibt einen Typ mit Definitionen für natives Packen.</span><span class="sxs-lookup"><span data-stu-id="babd9-142">Passes a type with native-packing definitions.</span></span>|[<span data-ttu-id="babd9-143">Plattformbeispiel</span><span class="sxs-lookup"><span data-stu-id="babd9-143">Platform sample</span></span>](#platform-sample)|
|<span data-ttu-id="babd9-144">Nullwerte in Struktur.</span><span class="sxs-lookup"><span data-stu-id="babd9-144">Null values in structure.</span></span>|<span data-ttu-id="babd9-145">Übergibt einen NULL-Verweis (**Nothing** in Visual Basic) anstelle eines Verweises auf einen Werttyp.</span><span class="sxs-lookup"><span data-stu-id="babd9-145">Passes a null reference (**Nothing** in Visual Basic) instead of a reference to a value type.</span></span>|<span data-ttu-id="babd9-146">[HandleRef-Beispiel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/hc662t8k(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="babd9-146">[HandleRef sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/hc662t8k(v=vs.85))</span></span>|

## <a name="structures-sample"></a><span data-ttu-id="babd9-147">Beispiel für Strukturen</span><span class="sxs-lookup"><span data-stu-id="babd9-147">Structures sample</span></span>

<span data-ttu-id="babd9-148">Dieses Beispiel veranschaulicht das Übergeben einer Struktur, die auf eine zweite Struktur zeigt, einer Struktur mit einer eingebetteten Struktur sowie einer Struktur mit einem eingebetteten Array.</span><span class="sxs-lookup"><span data-stu-id="babd9-148">This sample demonstrates how to pass a structure that points to a second structure, pass a structure with an embedded structure, and pass a structure with an embedded array.</span></span>  
  
<span data-ttu-id="babd9-149">Das Beispiel für Strukturen verwendet die folgenden nicht verwalteten Funktionen, die jeweils zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="babd9-149">The Structs sample uses the following unmanaged functions, shown with their original function declaration:</span></span>

- <span data-ttu-id="babd9-150">**TestStructInStruct** aus „PinvokeLib.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="babd9-150">**TestStructInStruct** exported from PinvokeLib.dll.</span></span>

    ```cpp
    int TestStructInStruct(MYPERSON2* pPerson2);
    ```

- <span data-ttu-id="babd9-151">**TestStructInStruct3** aus „PinvokeLib.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="babd9-151">**TestStructInStruct3** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestStructInStruct3(MYPERSON3 person3);
    ```

- <span data-ttu-id="babd9-152">**TestStructInStruct** aus „PinvokeLib.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="babd9-152">**TestArrayInStruct** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestArrayInStruct(MYARRAYSTRUCT* pStruct);
    ```

<span data-ttu-id="babd9-153">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) ist eine benutzerdefinierte, nicht verwaltete Bibliothek, die Implementierungen für die zuvor aufgelisteten Funktionen und vier Strukturen enthält: **MYPERSON**, **MYPERSON2**, **MYPERSON3** und **MYARRAYSTRUCT**.</span><span class="sxs-lookup"><span data-stu-id="babd9-153">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains implementations for the previously listed functions and four structures: **MYPERSON**, **MYPERSON2**, **MYPERSON3**, and **MYARRAYSTRUCT**.</span></span> <span data-ttu-id="babd9-154">Diese Strukturen enthalten die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="babd9-154">These structures contain the following elements:</span></span>

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

<span data-ttu-id="babd9-155">Die verwalteten Strukturen `MyPerson`, `MyPerson2`, `MyPerson3` und `MyArrayStruct` besitzen folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="babd9-155">The managed `MyPerson`, `MyPerson2`, `MyPerson3`, and `MyArrayStruct` structures have the following characteristic:</span></span>

- <span data-ttu-id="babd9-156">`MyPerson` enthält nur Zeichenfolgenmember.</span><span class="sxs-lookup"><span data-stu-id="babd9-156">`MyPerson` contains only string members.</span></span> <span data-ttu-id="babd9-157">Das [CharSet](specifying-a-character-set.md)-Feld legt die Zeichenfolgen auf das ANSI-Format fest, wenn sie an die nicht verwaltete Funktion übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="babd9-157">The [CharSet](specifying-a-character-set.md) field sets the strings to ANSI format when passed to the unmanaged function.</span></span>

- <span data-ttu-id="babd9-158">`MyPerson2` enthält eine **IntPtr** in der `MyPerson`-Struktur.</span><span class="sxs-lookup"><span data-stu-id="babd9-158">`MyPerson2` contains an **IntPtr** to the `MyPerson` structure.</span></span> <span data-ttu-id="babd9-159">Der **IntPtr**-Typ ersetzt den ursprünglichen Zeiger auf die nicht verwaltete Struktur, weil .NET Framework-Anwendungen nur dann Zeiger verwenden, wenn der Code als **unsicher** gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="babd9-159">The **IntPtr** type replaces the original pointer to the unmanaged structure because .NET Framework applications do not use pointers unless the code is marked **unsafe**.</span></span>

- <span data-ttu-id="babd9-160">`MyPerson3` enthält `MyPerson` als eingebettete Struktur.</span><span class="sxs-lookup"><span data-stu-id="babd9-160">`MyPerson3` contains `MyPerson` as an embedded structure.</span></span> <span data-ttu-id="babd9-161">Eine in eine Struktur eingebettete andere Struktur kann vereinfacht werden, indem die Elemente der eingebetteten Struktur direkt in der Hauptstruktur platziert werden. Alternativ kann die Struktur auch eingebettet bleiben, wie in diesem Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="babd9-161">A structure embedded within another structure can be flattened by placing the elements of the embedded structure directly into the main structure, or it can be left as an embedded structure, as is done in this sample.</span></span>

- <span data-ttu-id="babd9-162">`MyArrayStruct` enthält ein Array von ganzen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="babd9-162">`MyArrayStruct` contains an array of integers.</span></span> <span data-ttu-id="babd9-163">Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut legt den <xref:System.Runtime.InteropServices.UnmanagedType>-Enumerationswert auf **ByValArray** fest, womit die Anzahl der Elemente im Array angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="babd9-163">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration value to **ByValArray**, which is used to indicate the number of elements in the array.</span></span>

<span data-ttu-id="babd9-164">Für alle Strukturen in diesem Beispiel wird das <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut angewendet, um sicherzustellen, dass die Member im Speicher sequenziell in der Reihenfolge ihres Auftretens angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="babd9-164">For all structures in this sample, the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is applied to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>

<span data-ttu-id="babd9-165">Die `NativeMethods`-Klasse enthält verwaltete Prototypen für die Methoden `TestStructInStruct`, `TestStructInStruct3` und `TestArrayInStruct`, die von der `App`-Klasse aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="babd9-165">The `NativeMethods` class contains managed prototypes for the `TestStructInStruct`, `TestStructInStruct3`, and `TestArrayInStruct` methods called by the `App` class.</span></span> <span data-ttu-id="babd9-166">Jeder Prototyp deklariert einen einzelnen Parameter wie folgt:</span><span class="sxs-lookup"><span data-stu-id="babd9-166">Each prototype declares a single parameter, as follows:</span></span>

- <span data-ttu-id="babd9-167">`TestStructInStruct` deklariert einen Verweis auf den Typ `MyPerson2` als ihren Parameter.</span><span class="sxs-lookup"><span data-stu-id="babd9-167">`TestStructInStruct` declares a reference to type `MyPerson2` as its parameter.</span></span>

- <span data-ttu-id="babd9-168">`TestStructInStruct3` deklariert den Typ `MyPerson3` als ihren Parameter und übergibt den Parameter als Wert.</span><span class="sxs-lookup"><span data-stu-id="babd9-168">`TestStructInStruct3` declares type `MyPerson3` as its parameter and passes the parameter by value.</span></span>

- <span data-ttu-id="babd9-169">`TestArrayInStruct` deklariert einen Verweis auf den Typ `MyArrayStruct` als ihren Parameter.</span><span class="sxs-lookup"><span data-stu-id="babd9-169">`TestArrayInStruct` declares a reference to type `MyArrayStruct` as its parameter.</span></span>

<span data-ttu-id="babd9-170">Strukturen als Argumente von Methoden werden als Wert übergeben, es sei denn, der Parameter enthält das **Ref**-Schlüsselwort (**ByRef** in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="babd9-170">Structures as arguments to methods are passed by value unless the parameter contains the **ref** (**ByRef** in Visual Basic) keyword.</span></span> <span data-ttu-id="babd9-171">Zum Beispiel übergibt die `TestStructInStruct`-Methode einen Verweis (den Wert einer Adresse) auf ein Objekt vom Typ `MyPerson2` an nicht verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="babd9-171">For example, the `TestStructInStruct` method passes a reference (the value of an address) to an object of type `MyPerson2` to unmanaged code.</span></span> <span data-ttu-id="babd9-172">Um die Struktur zu bearbeiten, auf die `MyPerson2` zeigt, erstellt das Beispiel einen Puffer einer angegebenen Größe und gibt dessen Adresse zurück, indem die Methoden <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> und <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="babd9-172">To manipulate the structure that `MyPerson2` points to, the sample creates a buffer of a specified size and returns its address by combining the <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="babd9-173">Anschließend kopiert das Beispiel den Inhalt der verwalteten Struktur in den nicht verwalteten Puffer.</span><span class="sxs-lookup"><span data-stu-id="babd9-173">Next, the sample copies the content of the managed structure to the unmanaged buffer.</span></span> <span data-ttu-id="babd9-174">Zum Schluss verwendet das Beispiel die <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType>-Methode für das Marshalling von Daten aus dem nicht verwalteten Puffer in ein verwaltetes Objekt sowie die <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType>-Methode, um den nicht verwalteten Speicherblock freizugeben.</span><span class="sxs-lookup"><span data-stu-id="babd9-174">Finally, the sample uses the <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> method to marshal data from the unmanaged buffer to a managed object and the <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> method to free the unmanaged block of memory.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="babd9-175">Deklarieren von Prototypen</span><span class="sxs-lookup"><span data-stu-id="babd9-175">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#23](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#23)]
[!code-csharp[Conceptual.Interop.Marshaling#23](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#23)]
[!code-vb[Conceptual.Interop.Marshaling#23](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#23)]

### <a name="calling-functions"></a><span data-ttu-id="babd9-176">Aufrufen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="babd9-176">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#24](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#24)]
[!code-csharp[Conceptual.Interop.Marshaling#24](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#24)]
[!code-vb[Conceptual.Interop.Marshaling#24](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#24)]

## <a name="findfile-sample"></a><span data-ttu-id="babd9-177">FindFile-Beispiel</span><span class="sxs-lookup"><span data-stu-id="babd9-177">FindFile sample</span></span>

<span data-ttu-id="babd9-178">Dieses Beispiel demonstriert, wie eine Struktur, die eine zweite, eingebettete Struktur enthält, an eine nicht verwaltete Funktion übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="babd9-178">This sample demonstrates how to pass a structure that contains a second, embedded structure to an unmanaged function.</span></span> <span data-ttu-id="babd9-179">Außerdem wird veranschaulicht, wie Sie das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut verwenden, um ein Arrays mit fester Länge innerhalb der Struktur zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="babd9-179">It also demonstrates how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to declare a fixed-length array within the structure.</span></span> <span data-ttu-id="babd9-180">In diesem Beispiel werden die Elemente der eingebetteten Struktur der übergeordneten Struktur hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="babd9-180">In this sample, the embedded structure elements are added to the parent structure.</span></span> <span data-ttu-id="babd9-181">Ein Beispiel für eine nicht vereinfachte eingebettete Struktur finden Sie unter [Beispiel für Strukturen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="babd9-181">For a sample of an embedded structure that is not flattened, see [Structures Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100)).</span></span>

<span data-ttu-id="babd9-182">Das "FindFile"-Beispiel verwendet die folgende nicht verwaltete Funktion, die zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="babd9-182">The FindFile sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="babd9-183">**FindFirstFile** aus „Kernel32.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="babd9-183">**FindFirstFile** exported from Kernel32.dll.</span></span>

    ```cpp
    HANDLE FindFirstFile(LPCTSTR lpFileName, LPWIN32_FIND_DATA lpFindFileData);
    ```

<span data-ttu-id="babd9-184">Die ursprüngliche, an die Funktion übergebene Struktur enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="babd9-184">The original structure passed to the function contains the following elements:</span></span>

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

<span data-ttu-id="babd9-185">In diesem Beispiel enthält die `FindData`-Klasse einen entsprechenden Datenmember für jedes Element der Originalstruktur und der eingebetteten Struktur.</span><span class="sxs-lookup"><span data-stu-id="babd9-185">In this sample, the `FindData` class contains a corresponding data member for each element of the original structure and the embedded structure.</span></span> <span data-ttu-id="babd9-186">Anstelle zweier ursprünglicher Zeichenpuffer ersetzt die Klasse Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="babd9-186">In place of two original character buffers, the class substitutes strings.</span></span> <span data-ttu-id="babd9-187">Das **MarshalAsAttribute**-Attribut legt die <xref:System.Runtime.InteropServices.UnmanagedType>-Enumeration auf **ByValTStr** fest. Dieser Wert wird zum Identifizieren der Inlinezeichenarrays mit fester Länge verwendet, die innerhalb der nicht verwalteten Strukturen erscheinen.</span><span class="sxs-lookup"><span data-stu-id="babd9-187">**MarshalAsAttribute** sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged structures.</span></span>

<span data-ttu-id="babd9-188">Die `NativeMethods`-Klasse enthält einen verwalteten Prototyp der `FindFirstFile`-Methode, der die `FindData`-Klasse als Parameter übergibt.</span><span class="sxs-lookup"><span data-stu-id="babd9-188">The `NativeMethods` class contains a managed prototype of the `FindFirstFile` method, which passes the `FindData` class as a parameter.</span></span> <span data-ttu-id="babd9-189">Der Parameter muss mit den Attributen <xref:System.Runtime.InteropServices.InAttribute> und <xref:System.Runtime.InteropServices.OutAttribute> deklariert werden, weil Klassen, die Verweistypen sind, standardmäßig als In-Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="babd9-189">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="babd9-190">Deklarieren von Prototypen</span><span class="sxs-lookup"><span data-stu-id="babd9-190">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#17](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#17)]
[!code-csharp[Conceptual.Interop.Marshaling#17](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#17)]
[!code-vb[Conceptual.Interop.Marshaling#17](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#17)]

### <a name="calling-functions"></a><span data-ttu-id="babd9-191">Aufrufen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="babd9-191">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#18](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#18)]
[!code-csharp[Conceptual.Interop.Marshaling#18](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#18)]
 [!code-vb[Conceptual.Interop.Marshaling#18](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#18)]

## <a name="unions-sample"></a><span data-ttu-id="babd9-192">Unions-Beispiel</span><span class="sxs-lookup"><span data-stu-id="babd9-192">Unions sample</span></span>

<span data-ttu-id="babd9-193">Dieses Beispiel veranschaulicht, wie Strukturen, die nur Werttypen enthalten, sowie Strukturen, die einen Werttyp und eine Zeichenfolge enthalten, als Parameter an eine nicht verwaltete Funktion übergeben werden, die eine Union erwartet.</span><span class="sxs-lookup"><span data-stu-id="babd9-193">This sample demonstrates how to pass structures containing only value types, and structures containing a value type and a string as parameters to an unmanaged function expecting a union.</span></span> <span data-ttu-id="babd9-194">Eine Union stellt einen Speicherbereich dar, der von zwei oder mehr Variablen gemeinsam genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="babd9-194">A union represents a memory location that can be shared by two or more variables.</span></span>

<span data-ttu-id="babd9-195">Das "Unions"-Beispiel verwendet die folgende nicht verwaltete Funktion, die zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="babd9-195">The Unions sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="babd9-196">**TestUnion** aus „PinvokeLib.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="babd9-196">**TestUnion** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestUnion(MYUNION u, int type);
    ```

<span data-ttu-id="babd9-197">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) ist eine benutzerdefinierte, nicht verwaltete Bibliothek, die eine Implementierung für die zuvor aufgelistete Funktion und zwei Unions enthält: **MYUNION** und **MYUNION2**.</span><span class="sxs-lookup"><span data-stu-id="babd9-197">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains an implementation for the previously listed function and two unions, **MYUNION** and **MYUNION2**.</span></span> <span data-ttu-id="babd9-198">Die Union enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="babd9-198">The unions contain the following elements:</span></span>

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

<span data-ttu-id="babd9-199">In verwaltetem Code sind Unions als Strukturen definiert.</span><span class="sxs-lookup"><span data-stu-id="babd9-199">In managed code, unions are defined as structures.</span></span> <span data-ttu-id="babd9-200">Die `MyUnion`-Struktur enthält zwei Werttypen als Member: einen Integer- und einen Double-Wert.</span><span class="sxs-lookup"><span data-stu-id="babd9-200">The `MyUnion` structure contains two value types as its members: an integer and a double.</span></span> <span data-ttu-id="babd9-201">Das <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut wird festgelegt, um die genaue Position der einzelnen Datenmember zu kontrollieren.</span><span class="sxs-lookup"><span data-stu-id="babd9-201">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to control the precise position of each data member.</span></span> <span data-ttu-id="babd9-202">Das <xref:System.Runtime.InteropServices.FieldOffsetAttribute>-Attribut stellt die physische Position von Feldern innerhalb der nicht verwalteten Darstellung einer Union bereit.</span><span class="sxs-lookup"><span data-stu-id="babd9-202">The <xref:System.Runtime.InteropServices.FieldOffsetAttribute> attribute provides the physical position of fields within the unmanaged representation of a union.</span></span> <span data-ttu-id="babd9-203">Beachten Sie, dass beide Member denselben Offsetwert besitzen, sodass die Member denselben Speicherbereich definieren können.</span><span class="sxs-lookup"><span data-stu-id="babd9-203">Notice that both members have the same offset values, so the members can define the same piece of memory.</span></span>

<span data-ttu-id="babd9-204">`MyUnion2_1` und `MyUnion2_2` enthalten einen Werttyp (Integer) bzw. eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="babd9-204">`MyUnion2_1` and `MyUnion2_2` contain a value type (integer) and a string, respectively.</span></span> <span data-ttu-id="babd9-205">In verwaltetem Code dürfen Werttypen und Verweistypen nicht überlappen.</span><span class="sxs-lookup"><span data-stu-id="babd9-205">In managed code, value types and reference types are not permitted to overlap.</span></span> <span data-ttu-id="babd9-206">Dieses Beispiel verwendet das Überladen von Methoden, um dem Aufrufer die Verwendung beider Typen zu ermöglichen, wenn dieselbe nicht verwaltete Funktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="babd9-206">This sample uses method overloading to enable the caller to use both types when calling the same unmanaged function.</span></span> <span data-ttu-id="babd9-207">Das Layout von `MyUnion2_1` ist explizit und besitzt einen genauen Offsetwert.</span><span class="sxs-lookup"><span data-stu-id="babd9-207">The layout of `MyUnion2_1` is explicit and has a precise offset value.</span></span> <span data-ttu-id="babd9-208">Im Gegensatz dazu verfügt `MyUnion2_2` über ein sequenzielles Layout, da explizite Layouts für Verweistypen nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="babd9-208">In contrast, `MyUnion2_2` has a sequential layout, because explicit layouts are not permitted with reference types.</span></span> <span data-ttu-id="babd9-209">Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut legt die <xref:System.Runtime.InteropServices.UnmanagedType>-Enumeration auf **ByValTStr** fest. Dieser Wert wird zum Identifizieren der Inlinezeichenarrays mit fester Länge verwendet, die innerhalb der nicht verwalteten Darstellung der Union erscheinen.</span><span class="sxs-lookup"><span data-stu-id="babd9-209">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged representation of the union.</span></span>

<span data-ttu-id="babd9-210">Die `NativeMethods`-Klasse enthält die Prototypen für die Methoden `TestUnion` und `TestUnion2`.</span><span class="sxs-lookup"><span data-stu-id="babd9-210">The `NativeMethods` class contains the prototypes for the `TestUnion` and `TestUnion2` methods.</span></span> <span data-ttu-id="babd9-211">`TestUnion2` wird überladen, um `MyUnion2_1` oder `MyUnion2_2` als Parameter zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="babd9-211">`TestUnion2` is overloaded to declare `MyUnion2_1` or `MyUnion2_2` as parameters.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="babd9-212">Deklarieren von Prototypen</span><span class="sxs-lookup"><span data-stu-id="babd9-212">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#28](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#28)]
[!code-csharp[Conceptual.Interop.Marshaling#28](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#28)]
[!code-vb[Conceptual.Interop.Marshaling#28](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#28)]

### <a name="calling-functions"></a><span data-ttu-id="babd9-213">Aufrufen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="babd9-213">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#29](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#29)]
[!code-csharp[Conceptual.Interop.Marshaling#29](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#29)]
[!code-vb[Conceptual.Interop.Marshaling#29](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#29)]

## <a name="platform-sample"></a><span data-ttu-id="babd9-214">Plattformbeispiel</span><span class="sxs-lookup"><span data-stu-id="babd9-214">Platform sample</span></span>

<span data-ttu-id="babd9-215">In einigen Szenarios können sich die Layouts `struct` und `union` abhängig von der Zielplattform unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="babd9-215">In some scenarios, `struct` and `union` layouts can differ depending on the targeted platform.</span></span> <span data-ttu-id="babd9-216">Beachten Sie zum Beispiel den [`STRRET`](/windows/win32/api/shtypes/ns-shtypes-strret)-Typ, wenn er in einem COM-Szenario definiert ist:</span><span class="sxs-lookup"><span data-stu-id="babd9-216">For example, consider the [`STRRET`](/windows/win32/api/shtypes/ns-shtypes-strret) type when defined in a COM scenario:</span></span>

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

<span data-ttu-id="babd9-217">Das obige `struct`-Layout wird mit Windows-Headern deklariert, die das Arbeitsspeicherlayout des Typs beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="babd9-217">The above `struct` is declared with Windows' headers that influence the memory layout of the type.</span></span> <span data-ttu-id="babd9-218">Wenn sie in einer verwalteten Umgebung definiert sind, werden diese Layoutdetails benötigt, um ordnungsgemäß mit nativem Code zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="babd9-218">When defined in a managed environment, these layout details are needed to properly interoperate with native code.</span></span>

<span data-ttu-id="babd9-219">Die korrekte verwaltete Definition dieses Typs in einem 32-Bit-Prozess lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="babd9-219">The correct managed definition of this type in a 32-bit process is:</span></span>

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

<span data-ttu-id="babd9-220">Bei einem 64-Bit-Prozess unterscheiden sich die Größen- *und* Feldoffsets.</span><span class="sxs-lookup"><span data-stu-id="babd9-220">On a 64-bit process, the size *and* field offsets are different.</span></span> <span data-ttu-id="babd9-221">Das korrekte Layout sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="babd9-221">The correct layout is:</span></span>

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

<span data-ttu-id="babd9-222">Wenn Sie das native Layout in einem Interopszenario nicht genau beachten, kann dies zu zufälligen Abstürzen oder zu schlechteren falschen Berechnungen führen.</span><span class="sxs-lookup"><span data-stu-id="babd9-222">Failure to properly consider the native layout in an interop scenario can result in random crashes or worse, incorrect computations.</span></span>

<span data-ttu-id="babd9-223">In der Standardeinstellung können .NET-Assemblys sowohl in der 32-Bit- als auch der 64-Bit-Version der .NET-Runtime ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="babd9-223">By default, .NET assemblies can run in both a 32-bit and 64-bit version of the .NET runtime.</span></span> <span data-ttu-id="babd9-224">Die App muss bis zur Laufzeit warten, um zu entscheiden, welche der vorherigen Definitionen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="babd9-224">The app must wait until run time to decide which of the previous definitions to use.</span></span>

<span data-ttu-id="babd9-225">Der folgende Codeausschnitt zeigt ein Beispiel für die Wahl zwischen der 32-Bit- und der 64-Bit-Definition zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="babd9-225">The following code snippet shows an example of how to choose between the 32-bit and 64-bit definition at run time.</span></span>

```CSharp
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

## <a name="systime-sample"></a><span data-ttu-id="babd9-226">SysTime-Beispiel</span><span class="sxs-lookup"><span data-stu-id="babd9-226">SysTime sample</span></span>

<span data-ttu-id="babd9-227">Dieses Beispiel demonstriert, wie ein Zeiger auf eine Klasse an eine nicht verwaltete Funktion übergeben wird, die einen Zeiger auf eine Struktur erwartet.</span><span class="sxs-lookup"><span data-stu-id="babd9-227">This sample demonstrates how to pass a pointer to a class to an unmanaged function that expects a pointer to a structure.</span></span>

<span data-ttu-id="babd9-228">Das "SysTime"-Beispiel verwendet die folgende nicht verwaltete Funktion, die zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="babd9-228">The SysTime sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="babd9-229">**GetSystemTime** aus Kernel32.dll exportiert.</span><span class="sxs-lookup"><span data-stu-id="babd9-229">**GetSystemTime** exported from Kernel32.dll.</span></span>

    ```cpp
    VOID GetSystemTime(LPSYSTEMTIME lpSystemTime);
    ```

<span data-ttu-id="babd9-230">Die ursprüngliche, an die Funktion übergebene Struktur enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="babd9-230">The original structure passed to the function contains the following elements:</span></span>

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

<span data-ttu-id="babd9-231">In diesem Beispiel enthält die `SystemTime`-Klasse die Elemente der Originalstruktur, die als Klassenelemente dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="babd9-231">In this sample, the `SystemTime` class contains the elements of the original structure represented as class members.</span></span> <span data-ttu-id="babd9-232">Das <xref:System.Runtime.InteropServices.StructLayoutAttribute> -Attribut ist so eingerichtet, dass sichergestellt wird, dass die Member im Speicher sequenziell in der Reihenfolge ihres Erscheinens angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="babd9-232">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>

<span data-ttu-id="babd9-233">Die `NativeMethods`-Klasse enthält einen verwalteten Prototyp der `GetSystemTime`-Methode, der die `SystemTime`-Klasse standardmäßig als In/Out-Parameter übergibt.</span><span class="sxs-lookup"><span data-stu-id="babd9-233">The `NativeMethods` class contains a managed prototype of the `GetSystemTime` method, which passes the `SystemTime` class as an In/Out parameter by default.</span></span> <span data-ttu-id="babd9-234">Der Parameter muss mit den Attributen <xref:System.Runtime.InteropServices.InAttribute> und <xref:System.Runtime.InteropServices.OutAttribute> deklariert werden, weil Klassen, die Verweistypen sind, standardmäßig als In-Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="babd9-234">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span> <span data-ttu-id="babd9-235">Damit der Aufrufer die Ergebnisse empfängt, müssen diese [direktionalen Attribute](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) explizit angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="babd9-235">For the caller to receive the results, these [directional attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) must be applied explicitly.</span></span> <span data-ttu-id="babd9-236">Die `App`-Klasse erstellt eine neue Instanz der `SystemTime`-Klasse und greift auf deren Datenfelder zu.</span><span class="sxs-lookup"><span data-stu-id="babd9-236">The `App` class creates a new instance of the `SystemTime` class and accesses its data fields.</span></span>

### <a name="code-samples"></a><span data-ttu-id="babd9-237">Codebeispiele</span><span class="sxs-lookup"><span data-stu-id="babd9-237">Code Samples</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#25](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/systime.cpp#25)]
[!code-csharp[Conceptual.Interop.Marshaling#25](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/systime.cs#25)]
[!code-vb[Conceptual.Interop.Marshaling#25](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/systime.vb#25)]

## <a name="outarrayofstructs-sample"></a><span data-ttu-id="babd9-238">OutArrayOfStructs-Beispiel</span><span class="sxs-lookup"><span data-stu-id="babd9-238">OutArrayOfStructs sample</span></span>

<span data-ttu-id="babd9-239">Dieses Beispiel veranschaulicht, wie ein Array von Strukturen, das Integer- und String-Werte als Out-Parameter enthält, an eine nicht verwaltete Funktionen übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="babd9-239">This sample shows how to pass an array of structures that contains integers and strings as Out parameters to an unmanaged function.</span></span>

<span data-ttu-id="babd9-240">In diesem Beispiel wird veranschaulicht, wie eine systemeigene Funktion unter Verwendung der <xref:System.Runtime.InteropServices.Marshal>-Klasse und mithilfe von unsicherem Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="babd9-240">This sample demonstrates how to call a native function by using the <xref:System.Runtime.InteropServices.Marshal> class and by using unsafe code.</span></span>

<span data-ttu-id="babd9-241">Dieses Beispiel verwendet eine Wrapperfunktion und Plattformaufrufe, die in [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) definiert sind und auch in den Quelldateien bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="babd9-241">This sample uses a wrapper functions and platform invokes defined in [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll), also provided in the source files.</span></span> <span data-ttu-id="babd9-242">Es verwendet die `TestOutArrayOfStructs`-Funktion und die `MYSTRSTRUCT2`-Struktur.</span><span class="sxs-lookup"><span data-stu-id="babd9-242">It uses the `TestOutArrayOfStructs` function and the `MYSTRSTRUCT2` structure.</span></span> <span data-ttu-id="babd9-243">Die Struktur enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="babd9-243">The structure contains the following elements:</span></span>

```cpp
typedef struct _MYSTRSTRUCT2
{
   char* buffer;
   UINT size;
} MYSTRSTRUCT2;
```

<span data-ttu-id="babd9-244">Die `MyStruct`-Klasse enthält ein Zeichenfolgenobjekt aus ANSI-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="babd9-244">The `MyStruct` class contains a string object of ANSI characters.</span></span> <span data-ttu-id="babd9-245">Das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>-Feld gibt das ANSI-Format an.</span><span class="sxs-lookup"><span data-stu-id="babd9-245">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> field specifies ANSI format.</span></span> <span data-ttu-id="babd9-246">`MyUnsafeStruct` ist eine Struktur, die einen <xref:System.IntPtr>-Typ anstelle einer Zeichenfolge enthält.</span><span class="sxs-lookup"><span data-stu-id="babd9-246">`MyUnsafeStruct`, is a structure containing an <xref:System.IntPtr> type instead of a string.</span></span>

<span data-ttu-id="babd9-247">Die `NativeMethods`-Klasse enthält die überladene `TestOutArrayOfStructs`-Prototypenmethode.</span><span class="sxs-lookup"><span data-stu-id="babd9-247">The `NativeMethods` class contains the overloaded `TestOutArrayOfStructs` prototype method.</span></span> <span data-ttu-id="babd9-248">Wenn eine Methode einen Zeiger als Parameter deklariert, sollte die Klasse mit dem `unsafe`-Schlüsselwort markiert werden.</span><span class="sxs-lookup"><span data-stu-id="babd9-248">If a method declares a pointer as a parameter, the class should be marked with the `unsafe` keyword.</span></span> <span data-ttu-id="babd9-249">Da Visual Basic keinen unsicheren Code verwenden kann, sind die überladene Methode, der „unsafe“-Modifizierer und die `MyUnsafeStruct`-Struktur nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="babd9-249">Because Visual Basic cannot use unsafe code, the overloaded method, unsafe modifier, and the `MyUnsafeStruct` structure are unnecessary.</span></span>

<span data-ttu-id="babd9-250">Die `App` -Klasse implementiert die `UsingMarshaling`-Methode, die alle Aufgaben durchführt, die zum Übergeben des Arrays erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="babd9-250">The `App` class implements the `UsingMarshaling` method, which performs all the tasks necessary to pass the array.</span></span> <span data-ttu-id="babd9-251">Das Array wird mit dem `out`-Schlüsselwort (`ByRef` in Visual Basic) markiert, um anzuzeigen, dass Daten vom Aufgerufenen an den Aufrufer übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="babd9-251">The array is marked with the `out` (`ByRef` in Visual Basic) keyword to indicate that data passes from callee to caller.</span></span> <span data-ttu-id="babd9-252">Die Implementierung verwendet die folgenden <xref:System.Runtime.InteropServices.Marshal>-Klassenmethoden:</span><span class="sxs-lookup"><span data-stu-id="babd9-252">The implementation uses the following <xref:System.Runtime.InteropServices.Marshal> class methods:</span></span>

- <span data-ttu-id="babd9-253"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> für das Marshalling von Daten aus dem nicht verwalteten Speicherblock zu einem verwalteten Objekt.</span><span class="sxs-lookup"><span data-stu-id="babd9-253"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> to marshal data from the unmanaged buffer to a managed object.</span></span>

- <span data-ttu-id="babd9-254"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> zum Freigeben des für Zeichenfolgen in der Struktur reservierten Speichers.</span><span class="sxs-lookup"><span data-stu-id="babd9-254"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> to release the memory reserved for strings in the structure.</span></span>

- <span data-ttu-id="babd9-255"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> zum Freigeben des für das Array reservierten Speichers.</span><span class="sxs-lookup"><span data-stu-id="babd9-255"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> to release the memory reserved for the array.</span></span>

<span data-ttu-id="babd9-256">Wie zuvor erwähnt, lässt C# unsicheren Code zu, und Visual Basic nicht.</span><span class="sxs-lookup"><span data-stu-id="babd9-256">As previously mentioned, C# allows unsafe code and Visual Basic does not.</span></span> <span data-ttu-id="babd9-257">In dem C#-Beispiel ist `UsingUnsafePointer` eine alternative Methodenimplementierung, die Zeiger anstelle der <xref:System.Runtime.InteropServices.Marshal>-Klasse verwendet, um das Array, das die `MyUnsafeStruct`-Struktur enthält, zurück zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="babd9-257">In the C# sample, `UsingUnsafePointer` is an alternative method implementation that uses pointers instead of the <xref:System.Runtime.InteropServices.Marshal> class to pass back the array containing the `MyUnsafeStruct` structure.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="babd9-258">Deklarieren von Prototypen</span><span class="sxs-lookup"><span data-stu-id="babd9-258">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#20](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#20)]
[!code-csharp[Conceptual.Interop.Marshaling#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#20)]
[!code-vb[Conceptual.Interop.Marshaling#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#20)]

### <a name="calling-functions"></a><span data-ttu-id="babd9-259">Aufrufen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="babd9-259">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#21](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#21)]
[!code-csharp[Conceptual.Interop.Marshaling#21](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#21)]
[!code-vb[Conceptual.Interop.Marshaling#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#21)]

## <a name="see-also"></a><span data-ttu-id="babd9-260">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="babd9-260">See also</span></span>

- [<span data-ttu-id="babd9-261">Marshallen von Daten mit Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="babd9-261">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
- [<span data-ttu-id="babd9-262">Marshallen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="babd9-262">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="babd9-263">Maushallen verschiedener Typen von Arrays</span><span class="sxs-lookup"><span data-stu-id="babd9-263">Marshaling Different Types of Arrays</span></span>](marshaling-different-types-of-arrays.md)
