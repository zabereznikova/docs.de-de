---
title: Marshallen von Klassen, Strukturen und Unions
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6fb682d898de8cb6bc166426c3a1accbda452c83
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="marshaling-classes-structures-and-unions"></a><span data-ttu-id="354f3-102">Marshallen von Klassen, Strukturen und Unions</span><span class="sxs-lookup"><span data-stu-id="354f3-102">Marshaling Classes, Structures, and Unions</span></span>
<span data-ttu-id="354f3-103">Klassen und Strukturen sind in .NET Framework ähnlich.</span><span class="sxs-lookup"><span data-stu-id="354f3-103">Classes and structures are similar in the .NET Framework.</span></span> <span data-ttu-id="354f3-104">Beide können Felder, Eigenschaften und Ereignisse enthalten.</span><span class="sxs-lookup"><span data-stu-id="354f3-104">Both can have fields, properties, and events.</span></span> <span data-ttu-id="354f3-105">Sie können auch über statische und nicht statische Methoden verfügen.</span><span class="sxs-lookup"><span data-stu-id="354f3-105">They can also have static and nonstatic methods.</span></span> <span data-ttu-id="354f3-106">Ein deutlicher Unterschied ist, dass Strukturen Werttypen sind, während Klassen Verweistypen sind.</span><span class="sxs-lookup"><span data-stu-id="354f3-106">One notable difference is that structures are value types and classes are reference types.</span></span>  
  
 <span data-ttu-id="354f3-107">In der folgende Tabelle werden Marshallingoptionen für Klassen, Strukturen und Unions aufgelistet. Ihre Verwendung wird beschrieben, und es werden Links zu den entsprechenden Plattformaufrufbeispielen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="354f3-107">The following table lists marshaling options for classes, structures, and unions; describes their usage; and provides a link to the corresponding platform invoke sample.</span></span>  
  
|<span data-ttu-id="354f3-108">Typ</span><span class="sxs-lookup"><span data-stu-id="354f3-108">Type</span></span>|<span data-ttu-id="354f3-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="354f3-109">Description</span></span>|<span data-ttu-id="354f3-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="354f3-110">Sample</span></span>|  
|----------|-----------------|------------|  
|<span data-ttu-id="354f3-111">Klasse als Wert.</span><span class="sxs-lookup"><span data-stu-id="354f3-111">Class by value.</span></span>|<span data-ttu-id="354f3-112">Übergibt eine Klasse mit ganzzahligen Membern als In/Out-Parameter, wie der verwaltete Fall.</span><span class="sxs-lookup"><span data-stu-id="354f3-112">Passes a class with integer members as an In/Out parameter, like the managed case.</span></span>|<span data-ttu-id="354f3-113">SysTime-Beispiel</span><span class="sxs-lookup"><span data-stu-id="354f3-113">SysTime sample</span></span>|  
|<span data-ttu-id="354f3-114">Struktur als Wert.</span><span class="sxs-lookup"><span data-stu-id="354f3-114">Structure by value.</span></span>|<span data-ttu-id="354f3-115">Übergibt Strukturen als In-Parameter.</span><span class="sxs-lookup"><span data-stu-id="354f3-115">Passes structures as In parameters.</span></span>|<span data-ttu-id="354f3-116">Beispiel für Strukturen</span><span class="sxs-lookup"><span data-stu-id="354f3-116">Structures sample</span></span>|  
|<span data-ttu-id="354f3-117">Struktur als Verweis.</span><span class="sxs-lookup"><span data-stu-id="354f3-117">Structure by reference.</span></span>|<span data-ttu-id="354f3-118">Übergibt Strukturen als In/Out-Parameter.</span><span class="sxs-lookup"><span data-stu-id="354f3-118">Passes structures as In/Out parameters.</span></span>|<span data-ttu-id="354f3-119">OSInfo-Beispiel</span><span class="sxs-lookup"><span data-stu-id="354f3-119">OSInfo sample</span></span>|  
|<span data-ttu-id="354f3-120">Struktur mit geschachtelten Strukturen (vereinfacht).</span><span class="sxs-lookup"><span data-stu-id="354f3-120">Structure with nested structures (flattened).</span></span>|<span data-ttu-id="354f3-121">Übergibt eine Klasse, die eine Struktur mit geschachtelten Strukturen in der nicht verwalteten Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="354f3-121">Passes a class that represents a structure with nested structures in the unmanaged function.</span></span> <span data-ttu-id="354f3-122">Die Struktur wird zu einer einzigen großen Struktur im verwalteten Prototyp vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="354f3-122">The structure is flattened to one big structure in the managed prototype.</span></span>|<span data-ttu-id="354f3-123">FindFile-Beispiel</span><span class="sxs-lookup"><span data-stu-id="354f3-123">FindFile sample</span></span>|  
|<span data-ttu-id="354f3-124">Struktur mit einem Zeiger auf eine andere Struktur.</span><span class="sxs-lookup"><span data-stu-id="354f3-124">Structure with a pointer to another structure.</span></span>|<span data-ttu-id="354f3-125">Übergibt eine Struktur, die einen Zeiger auf eine zweite Struktur enthält, als Member.</span><span class="sxs-lookup"><span data-stu-id="354f3-125">Passes a structure that contains a pointer to a second structure as a member.</span></span>|<span data-ttu-id="354f3-126">Beispiel für Strukturen</span><span class="sxs-lookup"><span data-stu-id="354f3-126">Structures Sample</span></span>|  
|<span data-ttu-id="354f3-127">Array von Strukturen mit ganzen Zahlen als Wert.</span><span class="sxs-lookup"><span data-stu-id="354f3-127">Array of structures with integers by value.</span></span>|<span data-ttu-id="354f3-128">Übergibt ein Array von Strukturen, die nur ganze Zahlen enthalten, als In/Out-Parameter.</span><span class="sxs-lookup"><span data-stu-id="354f3-128">Passes an array of structures that contain only integers as an In/Out parameter.</span></span> <span data-ttu-id="354f3-129">Member des Arrays können geändert werden.</span><span class="sxs-lookup"><span data-stu-id="354f3-129">Members of the array can be changed.</span></span>|<span data-ttu-id="354f3-130">Beispiel zu Arrays</span><span class="sxs-lookup"><span data-stu-id="354f3-130">Arrays Sample</span></span>|  
|<span data-ttu-id="354f3-131">Array von Strukturen mit ganzen Zahlen und Zeichenfolgen als Verweis.</span><span class="sxs-lookup"><span data-stu-id="354f3-131">Array of structures with integers and strings by reference.</span></span>|<span data-ttu-id="354f3-132">Übergibt ein Array von Strukturen, die ganze Zahlen und Zeichenfolgen enthalten, als Out-Parameter.</span><span class="sxs-lookup"><span data-stu-id="354f3-132">Passes an array of structures that contain integers and strings as an Out parameter.</span></span> <span data-ttu-id="354f3-133">Die aufgerufene Funktion weist Speicher für das Array zu.</span><span class="sxs-lookup"><span data-stu-id="354f3-133">The called function allocates memory for the array.</span></span>|<span data-ttu-id="354f3-134">OutArrayOfStructs-Beispiel</span><span class="sxs-lookup"><span data-stu-id="354f3-134">OutArrayOfStructs Sample</span></span>|  
|<span data-ttu-id="354f3-135">Unions mit Werttypen.</span><span class="sxs-lookup"><span data-stu-id="354f3-135">Unions with value types.</span></span>|<span data-ttu-id="354f3-136">Übergibt Unions mit Werttypen (Integer und Double).</span><span class="sxs-lookup"><span data-stu-id="354f3-136">Passes unions with value types (integer and double).</span></span>|<span data-ttu-id="354f3-137">Unions-Beispiel</span><span class="sxs-lookup"><span data-stu-id="354f3-137">Unions sample</span></span>|  
|<span data-ttu-id="354f3-138">Unions mit gemischten Typen.</span><span class="sxs-lookup"><span data-stu-id="354f3-138">Unions with mixed types.</span></span>|<span data-ttu-id="354f3-139">Übergibt Unions mit gemischten Typen (Integer und String).</span><span class="sxs-lookup"><span data-stu-id="354f3-139">Passes unions with mixed types (integer and string).</span></span>|<span data-ttu-id="354f3-140">Unions-Beispiel</span><span class="sxs-lookup"><span data-stu-id="354f3-140">Unions sample</span></span>|  
|<span data-ttu-id="354f3-141">Nullwerte in Struktur.</span><span class="sxs-lookup"><span data-stu-id="354f3-141">Null values in structure.</span></span>|<span data-ttu-id="354f3-142">Übergibt einen NULL-Verweis (**Nothing** in Visual Basic) anstelle eines Verweises auf einen Werttyp.</span><span class="sxs-lookup"><span data-stu-id="354f3-142">Passes a null reference (**Nothing** in Visual Basic) instead of a reference to a value type.</span></span>|<span data-ttu-id="354f3-143">HandleRef-Beispiel</span><span class="sxs-lookup"><span data-stu-id="354f3-143">HandleRef sample</span></span>|  
  
## <a name="structures-sample"></a><span data-ttu-id="354f3-144">Beispiel für Strukturen</span><span class="sxs-lookup"><span data-stu-id="354f3-144">Structures sample</span></span>  
 <span data-ttu-id="354f3-145">Dieses Beispiel veranschaulicht das Übergeben einer Struktur, die auf eine zweite Struktur zeigt, einer Struktur mit einer eingebetteten Struktur sowie einer Struktur mit einem eingebetteten Array.</span><span class="sxs-lookup"><span data-stu-id="354f3-145">This sample demonstrates how to pass a structure that points to a second structure, pass a structure with an embedded structure, and pass a structure with an embedded array.</span></span>  
  
 <span data-ttu-id="354f3-146">Das Beispiel für Strukturen verwendet die folgenden nicht verwalteten Funktionen, die jeweils zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="354f3-146">The Structs sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
-   <span data-ttu-id="354f3-147">**TestStructInStruct** aus „PinvokeLib.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="354f3-147">**TestStructInStruct** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestStructInStruct(MYPERSON2* pPerson2);  
    ```  
  
-   <span data-ttu-id="354f3-148">**TestStructInStruct3** aus „PinvokeLib.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="354f3-148">**TestStructInStruct3** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestStructInStruct3(MYPERSON3 person3);  
    ```  
  
-   <span data-ttu-id="354f3-149">**TestStructInStruct** aus „PinvokeLib.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="354f3-149">**TestArrayInStruct** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestArrayInStruct( MYARRAYSTRUCT* pStruct );  
    ```  
  
 <span data-ttu-id="354f3-150">[PinvokeLib.dll](http://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614) ist eine benutzerdefinierte, nicht verwaltete Bibliothek, die Implementierungen für die zuvor aufgelisteten Funktionen und vier Strukturen enthält: **MYPERSON**, **MYPERSON2**, **MYPERSON3** und **MYARRAYSTRUCT**.</span><span class="sxs-lookup"><span data-stu-id="354f3-150">[PinvokeLib.dll](http://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614) is a custom unmanaged library that contains implementations for the previously listed functions and four structures: **MYPERSON**, **MYPERSON2**, **MYPERSON3**, and **MYARRAYSTRUCT**.</span></span> <span data-ttu-id="354f3-151">Diese Strukturen enthalten die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="354f3-151">These structures contain the following elements:</span></span>  
  
```  
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
  
 <span data-ttu-id="354f3-152">Die verwalteten Strukturen `MyPerson`, `MyPerson2`, `MyPerson3` und `MyArrayStruct` besitzen folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="354f3-152">The managed `MyPerson`, `MyPerson2`, `MyPerson3`, and `MyArrayStruct` structures have the following characteristic:</span></span>  
  
-   <span data-ttu-id="354f3-153">`MyPerson` enthält nur Zeichenfolgenmember.</span><span class="sxs-lookup"><span data-stu-id="354f3-153">`MyPerson` contains only string members.</span></span> <span data-ttu-id="354f3-154">Das [CharSet](../../../docs/framework/interop/specifying-a-character-set.md)-Feld legt die Zeichenfolgen auf das ANSI-Format fest, wenn sie an die nicht verwaltete Funktion übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="354f3-154">The [CharSet](../../../docs/framework/interop/specifying-a-character-set.md) field sets the strings to ANSI format when passed to the unmanaged function.</span></span>  
  
-   <span data-ttu-id="354f3-155">`MyPerson2` enthält eine **IntPtr** in der `MyPerson`-Struktur.</span><span class="sxs-lookup"><span data-stu-id="354f3-155">`MyPerson2` contains an **IntPtr** to the `MyPerson` structure.</span></span> <span data-ttu-id="354f3-156">Der **IntPtr**-Typ ersetzt den ursprünglichen Zeiger auf die nicht verwaltete Struktur, weil .NET Framework-Anwendungen nur dann Zeiger verwenden, wenn der Code als **unsicher** gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="354f3-156">The **IntPtr** type replaces the original pointer to the unmanaged structure because .NET Framework applications do not use pointers unless the code is marked **unsafe**.</span></span>  
  
-   <span data-ttu-id="354f3-157">`MyPerson3` enthält `MyPerson` als eingebettete Struktur.</span><span class="sxs-lookup"><span data-stu-id="354f3-157">`MyPerson3` contains `MyPerson` as an embedded structure.</span></span> <span data-ttu-id="354f3-158">Eine in eine Struktur eingebettete andere Struktur kann vereinfacht werden, indem die Elemente der eingebetteten Struktur direkt in der Hauptstruktur platziert werden. Alternativ kann die Struktur auch eingebettet bleiben, wie in diesem Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="354f3-158">A structure embedded within another structure can be flattened by placing the elements of the embedded structure directly into the main structure, or it can be left as an embedded structure, as is done in this sample.</span></span>  
  
-   <span data-ttu-id="354f3-159">`MyArrayStruct` enthält ein Array von ganzen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="354f3-159">`MyArrayStruct` contains an array of integers.</span></span> <span data-ttu-id="354f3-160">Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut legt den <xref:System.Runtime.InteropServices.UnmanagedType>-Enumerationswert auf **ByValArray** fest, womit die Anzahl der Elemente im Array angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="354f3-160">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration value to **ByValArray**, which is used to indicate the number of elements in the array.</span></span>  
  
 <span data-ttu-id="354f3-161">Für alle Strukturen in diesem Beispiel wird das <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut angewendet, um sicherzustellen, dass die Member im Speicher sequenziell in der Reihenfolge ihres Auftretens angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="354f3-161">For all structures in this sample, the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is applied to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>  
  
 <span data-ttu-id="354f3-162">Die `LibWrap`-Klasse enthält verwaltete Prototypen für die Methoden `TestStructInStruct`, `TestStructInStruct3` und `TestArrayInStruct`, die von der `App`-Klasse aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="354f3-162">The `LibWrap` class contains managed prototypes for the `TestStructInStruct`, `TestStructInStruct3`, and `TestArrayInStruct` methods called by the `App` class.</span></span> <span data-ttu-id="354f3-163">Jeder Prototyp deklariert einen einzelnen Parameter wie folgt:</span><span class="sxs-lookup"><span data-stu-id="354f3-163">Each prototype declares a single parameter, as follows:</span></span>  
  
-   <span data-ttu-id="354f3-164">`TestStructInStruct` deklariert einen Verweis auf den Typ `MyPerson2` als ihren Parameter.</span><span class="sxs-lookup"><span data-stu-id="354f3-164">`TestStructInStruct` declares a reference to type `MyPerson2` as its parameter.</span></span>  
  
-   <span data-ttu-id="354f3-165">`TestStructInStruct3` deklariert den Typ `MyPerson3` als ihren Parameter und übergibt den Parameter als Wert.</span><span class="sxs-lookup"><span data-stu-id="354f3-165">`TestStructInStruct3` declares type `MyPerson3` as its parameter and passes the parameter by value.</span></span>  
  
-   <span data-ttu-id="354f3-166">`TestArrayInStruct` deklariert einen Verweis auf den Typ `MyArrayStruct` als ihren Parameter.</span><span class="sxs-lookup"><span data-stu-id="354f3-166">`TestArrayInStruct` declares a reference to type `MyArrayStruct` as its parameter.</span></span>  
  
 <span data-ttu-id="354f3-167">Strukturen als Argumente von Methoden werden als Wert übergeben, es sei denn, der Parameter enthält das **Ref**-Schlüsselwort (**ByRef** in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="354f3-167">Structures as arguments to methods are passed by value unless the parameter contains the **ref** (**ByRef** in Visual Basic) keyword.</span></span> <span data-ttu-id="354f3-168">Zum Beispiel übergibt die `TestStructInStruct`-Methode einen Verweis (den Wert einer Adresse) auf ein Objekt vom Typ `MyPerson2` an nicht verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="354f3-168">For example, the `TestStructInStruct` method passes a reference (the value of an address) to an object of type `MyPerson2` to unmanaged code.</span></span> <span data-ttu-id="354f3-169">Um die Struktur zu bearbeiten, auf die `MyPerson2` zeigt, erstellt das Beispiel einen Puffer einer angegebenen Größe und gibt dessen Adresse zurück, indem die Methoden <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> und <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="354f3-169">To manipulate the structure that `MyPerson2` points to, the sample creates a buffer of a specified size and returns its address by combining the <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="354f3-170">Anschließend kopiert das Beispiel den Inhalt der verwalteten Struktur in den nicht verwalteten Puffer.</span><span class="sxs-lookup"><span data-stu-id="354f3-170">Next, the sample copies the content of the managed structure to the unmanaged buffer.</span></span> <span data-ttu-id="354f3-171">Zum Schluss verwendet das Beispiel die <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType>-Methode für das Marshalling von Daten aus dem nicht verwalteten Puffer in ein verwaltetes Objekt sowie die <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType>-Methode, um den nicht verwalteten Speicherblock freizugeben.</span><span class="sxs-lookup"><span data-stu-id="354f3-171">Finally, the sample uses the <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> method to marshal data from the unmanaged buffer to a managed object and the <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> method to free the unmanaged block of memory.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="354f3-172">Deklarieren von Prototypen</span><span class="sxs-lookup"><span data-stu-id="354f3-172">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#23](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#23)]
 [!code-csharp[Conceptual.Interop.Marshaling#23](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#23)]
 [!code-vb[Conceptual.Interop.Marshaling#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#23)]  
  
### <a name="calling-functions"></a><span data-ttu-id="354f3-173">Aufrufen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="354f3-173">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#24](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#24)]
 [!code-csharp[Conceptual.Interop.Marshaling#24](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#24)]
 [!code-vb[Conceptual.Interop.Marshaling#24](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#24)]  
  
## <a name="findfile-sample"></a><span data-ttu-id="354f3-174">FindFile-Beispiel</span><span class="sxs-lookup"><span data-stu-id="354f3-174">FindFile sample</span></span>  
 <span data-ttu-id="354f3-175">Dieses Beispiel demonstriert, wie eine Struktur, die eine zweite, eingebettete Struktur enthält, an eine nicht verwaltete Funktion übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="354f3-175">This sample demonstrates how to pass a structure that contains a second, embedded structure to an unmanaged function.</span></span> <span data-ttu-id="354f3-176">Außerdem wird veranschaulicht, wie Sie das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut verwenden, um ein Arrays mit fester Länge innerhalb der Struktur zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="354f3-176">It also demonstrates how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to declare a fixed-length array within the structure.</span></span> <span data-ttu-id="354f3-177">In diesem Beispiel werden die Elemente der eingebetteten Struktur der übergeordneten Struktur hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="354f3-177">In this sample, the embedded structure elements are added to the parent structure.</span></span> <span data-ttu-id="354f3-178">Ein Beispiel für eine nicht vereinfachte eingebettete Struktur finden Sie unter [Beispiel für Strukturen](http://msdn.microsoft.com/library/96a62265-dcf9-4608-bc0a-1f762ab9f48e).</span><span class="sxs-lookup"><span data-stu-id="354f3-178">For a sample of an embedded structure that is not flattened, see [Structures Sample](http://msdn.microsoft.com/library/96a62265-dcf9-4608-bc0a-1f762ab9f48e).</span></span>  
  
 <span data-ttu-id="354f3-179">Das "FindFile"-Beispiel verwendet die folgende nicht verwaltete Funktion, die zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="354f3-179">The FindFile sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
-   <span data-ttu-id="354f3-180">**FindFirstFile** aus „Kernel32.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="354f3-180">**FindFirstFile** exported from Kernel32.dll.</span></span>  
  
    ```  
    HANDLE FindFirstFile(LPCTSTR lpFileName, LPWIN32_FIND_DATA lpFindFileData);  
    ```  
  
 <span data-ttu-id="354f3-181">Die ursprüngliche, an die Funktion übergebene Struktur enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="354f3-181">The original structure passed to the function contains the following elements:</span></span>  
  
```  
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
  
 <span data-ttu-id="354f3-182">In diesem Beispiel enthält die `FindData`-Klasse einen entsprechenden Datenmember für jedes Element der Originalstruktur und der eingebetteten Struktur.</span><span class="sxs-lookup"><span data-stu-id="354f3-182">In this sample, the `FindData` class contains a corresponding data member for each element of the original structure and the embedded structure.</span></span> <span data-ttu-id="354f3-183">Anstelle zweier ursprünglicher Zeichenpuffer ersetzt die Klasse Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="354f3-183">In place of two original character buffers, the class substitutes strings.</span></span> <span data-ttu-id="354f3-184">Das **MarshalAsAttribute**-Attribut legt die <xref:System.Runtime.InteropServices.UnmanagedType>-Enumeration auf **ByValTStr** fest. Dieser Wert wird zum Identifizieren der Inlinezeichenarrays mit fester Länge verwendet, die innerhalb der nicht verwalteten Strukturen erscheinen.</span><span class="sxs-lookup"><span data-stu-id="354f3-184">**MarshalAsAttribute** sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged structures.</span></span>  
  
 <span data-ttu-id="354f3-185">Die `LibWrap`-Klasse enthält einen verwalteten Prototyp der `FindFirstFile`-Methode, der die `FindData`-Klasse als Parameter übergibt.</span><span class="sxs-lookup"><span data-stu-id="354f3-185">The `LibWrap` class contains a managed prototype of the `FindFirstFile` method, which passes the `FindData` class as a parameter.</span></span> <span data-ttu-id="354f3-186">Der Parameter muss mit den Attributen <xref:System.Runtime.InteropServices.InAttribute> und <xref:System.Runtime.InteropServices.OutAttribute> deklariert werden, weil Klassen, die Verweistypen sind, standardmäßig als In-Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="354f3-186">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="354f3-187">Deklarieren von Prototypen</span><span class="sxs-lookup"><span data-stu-id="354f3-187">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#17)]
 [!code-csharp[Conceptual.Interop.Marshaling#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#17)]
 [!code-vb[Conceptual.Interop.Marshaling#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#17)]  
  
### <a name="calling-functions"></a><span data-ttu-id="354f3-188">Aufrufen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="354f3-188">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#18)]
 [!code-csharp[Conceptual.Interop.Marshaling#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#18)]
 [!code-vb[Conceptual.Interop.Marshaling#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#18)]  
  
## <a name="unions-sample"></a><span data-ttu-id="354f3-189">Unions-Beispiel</span><span class="sxs-lookup"><span data-stu-id="354f3-189">Unions sample</span></span>  
 <span data-ttu-id="354f3-190">Dieses Beispiel veranschaulicht, wie Strukturen, die nur Werttypen enthalten, sowie Strukturen, die einen Werttyp und eine Zeichenfolge enthalten, als Parameter an eine nicht verwaltete Funktion übergeben werden, die eine Union erwartet.</span><span class="sxs-lookup"><span data-stu-id="354f3-190">This sample demonstrates how to pass structures containing only value types, and structures containing a value type and a string as parameters to an unmanaged function expecting a union.</span></span> <span data-ttu-id="354f3-191">Eine Union stellt einen Speicherbereich dar, der von zwei oder mehr Variablen gemeinsam genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="354f3-191">A union represents a memory location that can be shared by two or more variables.</span></span>  
  
 <span data-ttu-id="354f3-192">Das "Unions"-Beispiel verwendet die folgende nicht verwaltete Funktion, die zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="354f3-192">The Unions sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
-   <span data-ttu-id="354f3-193">**TestUnion** aus „PinvokeLib.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="354f3-193">**TestUnion** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestUnion(MYUNION u, int type);  
    ```  
  
 <span data-ttu-id="354f3-194">[PinvokeLib.dll](http://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614) ist eine benutzerdefinierte, nicht verwaltete Bibliothek, die eine Implementierung für die zuvor aufgelistete Funktion und zwei Unions enthält: **MYUNION** und **MYUNION2**.</span><span class="sxs-lookup"><span data-stu-id="354f3-194">[PinvokeLib.dll](http://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614) is a custom unmanaged library that contains an implementation for the previously listed function and two unions, **MYUNION** and **MYUNION2**.</span></span> <span data-ttu-id="354f3-195">Die Union enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="354f3-195">The unions contain the following elements:</span></span>  
  
```  
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
  
 <span data-ttu-id="354f3-196">In verwaltetem Code sind Unions als Strukturen definiert.</span><span class="sxs-lookup"><span data-stu-id="354f3-196">In managed code, unions are defined as structures.</span></span> <span data-ttu-id="354f3-197">Die `MyUnion`-Struktur enthält zwei Werttypen als Member: einen Integer- und einen Double-Wert.</span><span class="sxs-lookup"><span data-stu-id="354f3-197">The `MyUnion` structure contains two value types as its members: an integer and a double.</span></span> <span data-ttu-id="354f3-198">Das <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut wird festgelegt, um die genaue Position der einzelnen Datenmember zu kontrollieren.</span><span class="sxs-lookup"><span data-stu-id="354f3-198">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to control the precise position of each data member.</span></span> <span data-ttu-id="354f3-199">Das <xref:System.Runtime.InteropServices.FieldOffsetAttribute>-Attribut stellt die physische Position von Feldern innerhalb der nicht verwalteten Darstellung einer Union bereit.</span><span class="sxs-lookup"><span data-stu-id="354f3-199">The <xref:System.Runtime.InteropServices.FieldOffsetAttribute> attribute provides the physical position of fields within the unmanaged representation of a union.</span></span> <span data-ttu-id="354f3-200">Beachten Sie, dass beide Member denselben Offsetwert besitzen, sodass die Member denselben Speicherbereich definieren können.</span><span class="sxs-lookup"><span data-stu-id="354f3-200">Notice that both members have the same offset values, so the members can define the same piece of memory.</span></span>  
  
 <span data-ttu-id="354f3-201">`MyUnion2_1` und `MyUnion2_2` enthalten einen Werttyp (Integer) bzw. eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="354f3-201">`MyUnion2_1` and `MyUnion2_2` contain a value type (integer) and a string, respectively.</span></span> <span data-ttu-id="354f3-202">In verwaltetem Code dürfen Werttypen und Verweistypen nicht überlappen.</span><span class="sxs-lookup"><span data-stu-id="354f3-202">In managed code, value types and reference types are not permitted to overlap.</span></span> <span data-ttu-id="354f3-203">Dieses Beispiel verwendet das Überladen von Methoden, um dem Aufrufer die Verwendung beider Typen zu ermöglichen, wenn dieselbe nicht verwaltete Funktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="354f3-203">This sample uses method overloading to enable the caller to use both types when calling the same unmanaged function.</span></span> <span data-ttu-id="354f3-204">Das Layout von `MyUnion2_1` ist explizit und besitzt einen genauen Offsetwert.</span><span class="sxs-lookup"><span data-stu-id="354f3-204">The layout of `MyUnion2_1` is explicit and has a precise offset value.</span></span> <span data-ttu-id="354f3-205">Im Gegensatz dazu verfügt `MyUnion2_2` über ein sequenzielles Layout, da explizite Layouts für Verweistypen nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="354f3-205">In contrast, `MyUnion2_2` has a sequential layout, because explicit layouts are not permitted with reference types.</span></span> <span data-ttu-id="354f3-206">Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut legt die <xref:System.Runtime.InteropServices.UnmanagedType>-Enumeration auf **ByValTStr** fest. Dieser Wert wird zum Identifizieren der Inlinezeichenarrays mit fester Länge verwendet, die innerhalb der nicht verwalteten Darstellung der Union erscheinen.</span><span class="sxs-lookup"><span data-stu-id="354f3-206">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged representation of the union.</span></span>  
  
 <span data-ttu-id="354f3-207">Die `LibWrap`-Klasse enthält die Prototypen für die Methoden `TestUnion` und `TestUnion2`.</span><span class="sxs-lookup"><span data-stu-id="354f3-207">The `LibWrap` class contains the prototypes for the `TestUnion` and `TestUnion2` methods.</span></span> <span data-ttu-id="354f3-208">`TestUnion2` wird überladen, um `MyUnion2_1` oder `MyUnion2_2` als Parameter zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="354f3-208">`TestUnion2` is overloaded to declare `MyUnion2_1` or `MyUnion2_2` as parameters.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="354f3-209">Deklarieren von Prototypen</span><span class="sxs-lookup"><span data-stu-id="354f3-209">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#28](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#28)]
 [!code-csharp[Conceptual.Interop.Marshaling#28](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#28)]
 [!code-vb[Conceptual.Interop.Marshaling#28](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#28)]  
  
### <a name="calling-functions"></a><span data-ttu-id="354f3-210">Aufrufen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="354f3-210">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#29](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#29)]
 [!code-csharp[Conceptual.Interop.Marshaling#29](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#29)]
 [!code-vb[Conceptual.Interop.Marshaling#29](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#29)]  
  
## <a name="systime-sample"></a><span data-ttu-id="354f3-211">SysTime-Beispiel</span><span class="sxs-lookup"><span data-stu-id="354f3-211">SysTime sample</span></span>  
 <span data-ttu-id="354f3-212">Dieses Beispiel demonstriert, wie ein Zeiger auf eine Klasse an eine nicht verwaltete Funktion übergeben wird, die einen Zeiger auf eine Struktur erwartet.</span><span class="sxs-lookup"><span data-stu-id="354f3-212">This sample demonstrates how to pass a pointer to a class to an unmanaged function that expects a pointer to a structure.</span></span>  
  
 <span data-ttu-id="354f3-213">Das "SysTime"-Beispiel verwendet die folgende nicht verwaltete Funktion, die zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="354f3-213">The SysTime sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
-   <span data-ttu-id="354f3-214">**GetSystemTime** aus Kernel32.dll exportiert.</span><span class="sxs-lookup"><span data-stu-id="354f3-214">**GetSystemTime** exported from Kernel32.dll.</span></span>  
  
    ```  
    VOID GetSystemTime(LPSYSTEMTIME lpSystemTime);  
    ```  
  
 <span data-ttu-id="354f3-215">Die ursprüngliche, an die Funktion übergebene Struktur enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="354f3-215">The original structure passed to the function contains the following elements:</span></span>  
  
```  
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
  
 <span data-ttu-id="354f3-216">In diesem Beispiel enthält die `SystemTime`-Klasse die Elemente der Originalstruktur, die als Klassenelemente dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="354f3-216">In this sample, the `SystemTime` class contains the elements of the original structure represented as class members.</span></span> <span data-ttu-id="354f3-217">Das <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut ist so eingerichtet, dass sichergestellt wird, dass die Member im Speicher sequenziell in der Reihenfolge ihres Erscheinens angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="354f3-217">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>  
  
 <span data-ttu-id="354f3-218">Die `LibWrap`-Klasse enthält einen verwalteten Prototyp der `GetSystemTime`-Methode, der die `SystemTime`-Klasse standardmäßig als In/Out-Parameter übergibt.</span><span class="sxs-lookup"><span data-stu-id="354f3-218">The `LibWrap` class contains a managed prototype of the `GetSystemTime` method, which passes the `SystemTime` class as an In/Out parameter by default.</span></span> <span data-ttu-id="354f3-219">Der Parameter muss mit den Attributen <xref:System.Runtime.InteropServices.InAttribute> und <xref:System.Runtime.InteropServices.OutAttribute> deklariert werden, weil Klassen, die Verweistypen sind, standardmäßig als In-Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="354f3-219">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span> <span data-ttu-id="354f3-220">Damit der Aufrufer die Ergebnisse empfängt, müssen diese [direktionalen Attribute](http://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2) explizit angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="354f3-220">For the caller to receive the results, these [directional attributes](http://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2) must be applied explicitly.</span></span> <span data-ttu-id="354f3-221">Die `App`-Klasse erstellt eine neue Instanz der `SystemTime`-Klasse und greift auf deren Datenfelder zu.</span><span class="sxs-lookup"><span data-stu-id="354f3-221">The `App` class creates a new instance of the `SystemTime` class and accesses its data fields.</span></span>  
  
### <a name="code-samples"></a><span data-ttu-id="354f3-222">Codebeispiele</span><span class="sxs-lookup"><span data-stu-id="354f3-222">Code Samples</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#25](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/systime.cpp#25)]
 [!code-csharp[Conceptual.Interop.Marshaling#25](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/systime.cs#25)]
 [!code-vb[Conceptual.Interop.Marshaling#25](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/systime.vb#25)]  
  
## <a name="outarrayofstructs-sample"></a><span data-ttu-id="354f3-223">OutArrayOfStructs-Beispiel</span><span class="sxs-lookup"><span data-stu-id="354f3-223">OutArrayOfStructs sample</span></span>  
 <span data-ttu-id="354f3-224">Dieses Beispiel veranschaulicht, wie ein Array von Strukturen, das Integer- und String-Werte als Out-Parameter enthält, an eine nicht verwaltete Funktionen übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="354f3-224">This sample shows how to pass an array of structures that contains integers and strings as Out parameters to an unmanaged function.</span></span>  
  
 <span data-ttu-id="354f3-225">In diesem Beispiel wird veranschaulicht, wie eine systemeigene Funktion unter Verwendung der <xref:System.Runtime.InteropServices.Marshal>-Klasse und mithilfe von unsicherem Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="354f3-225">This sample demonstrates how to call a native function by using the <xref:System.Runtime.InteropServices.Marshal> class and by using unsafe code.</span></span>  
  
 <span data-ttu-id="354f3-226">Dieses Beispiel verwendet eine Wrapperfunktion und Plattformaufrufe, die in [PinvokeLib.dll](http://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614) definiert sind und auch in den Quelldateien bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="354f3-226">This sample uses a wrapper functions and platform invokes defined in [PinvokeLib.dll](http://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614), also provided in the source files.</span></span> <span data-ttu-id="354f3-227">Es verwendet die `TestOutArrayOfStructs`-Funktion und die `MYSTRSTRUCT2`-Struktur.</span><span class="sxs-lookup"><span data-stu-id="354f3-227">It uses the `TestOutArrayOfStructs` function and the `MYSTRSTRUCT2` structure.</span></span> <span data-ttu-id="354f3-228">Die Struktur enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="354f3-228">The structure contains the following elements:</span></span>  
  
```  
typedef struct _MYSTRSTRUCT2  
{  
   char* buffer;  
   UINT size;   
} MYSTRSTRUCT2;  
```  
  
 <span data-ttu-id="354f3-229">Die `MyStruct`-Klasse enthält ein Zeichenfolgenobjekt aus ANSI-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="354f3-229">The `MyStruct` class contains a string object of ANSI characters.</span></span> <span data-ttu-id="354f3-230">Das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>-Feld gibt das ANSI-Format an.</span><span class="sxs-lookup"><span data-stu-id="354f3-230">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> field specifies ANSI format.</span></span> <span data-ttu-id="354f3-231">`MyUnsafeStruct` ist eine Struktur, die einen <xref:System.IntPtr>-Typ anstelle einer Zeichenfolge enthält.</span><span class="sxs-lookup"><span data-stu-id="354f3-231">`MyUnsafeStruct`, is a structure containing an <xref:System.IntPtr> type instead of a string.</span></span>  
  
 <span data-ttu-id="354f3-232">Die `LibWrap`-Klasse enthält die überladene `TestOutArrayOfStructs`-Prototypenmethode.</span><span class="sxs-lookup"><span data-stu-id="354f3-232">The `LibWrap` class contains the overloaded `TestOutArrayOfStructs` prototype method.</span></span> <span data-ttu-id="354f3-233">Wenn eine Methode einen Zeiger als Parameter deklariert, sollte die Klasse mit dem `unsafe`-Schlüsselwort markiert werden.</span><span class="sxs-lookup"><span data-stu-id="354f3-233">If a method declares a pointer as a parameter, the class should be marked with the `unsafe` keyword.</span></span> <span data-ttu-id="354f3-234">Da [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] keinen unsicheren Code verwenden kann, sind die überladene Methode, der "unsafe"-Modifizierer und die `MyUnsafeStruct`-Struktur nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="354f3-234">Because [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] cannot use unsafe code, the overloaded method, unsafe modifier, and the `MyUnsafeStruct` structure are unnecessary.</span></span>  
  
 <span data-ttu-id="354f3-235">Die `App` -Klasse implementiert die `UsingMarshaling`-Methode, die alle Aufgaben durchführt, die zum Übergeben des Arrays erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="354f3-235">The `App` class implements the `UsingMarshaling` method, which performs all the tasks necessary to pass the array.</span></span> <span data-ttu-id="354f3-236">Das Array wird mit dem `out`-Schlüsselwort (`ByRef` in Visual Basic) markiert, um anzuzeigen, dass Daten vom Aufgerufenen an den Aufrufer übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="354f3-236">The array is marked with the `out` (`ByRef` in Visual Basic) keyword to indicate that data passes from callee to caller.</span></span> <span data-ttu-id="354f3-237">Die Implementierung verwendet die folgenden <xref:System.Runtime.InteropServices.Marshal>-Klassenmethoden:</span><span class="sxs-lookup"><span data-stu-id="354f3-237">The implementation uses the following <xref:System.Runtime.InteropServices.Marshal> class methods:</span></span>  
  
-   <span data-ttu-id="354f3-238"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> für das Marshalling von Daten aus dem nicht verwalteten Speicherblock zu einem verwalteten Objekt.</span><span class="sxs-lookup"><span data-stu-id="354f3-238"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> to marshal data from the unmanaged buffer to a managed object.</span></span>  
  
-   <span data-ttu-id="354f3-239"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> zum Freigeben des für Zeichenfolgen in der Struktur reservierten Speichers.</span><span class="sxs-lookup"><span data-stu-id="354f3-239"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> to release the memory reserved for strings in the structure.</span></span>  
  
-   <span data-ttu-id="354f3-240"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> zum Freigeben des für das Array reservierten Speichers.</span><span class="sxs-lookup"><span data-stu-id="354f3-240"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> to release the memory reserved for the array.</span></span>  
  
 <span data-ttu-id="354f3-241">Wie zuvor erwähnt, lässt C# unsicheren Code zu, und [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] nicht.</span><span class="sxs-lookup"><span data-stu-id="354f3-241">As previously mentioned, C# allows unsafe code and [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] does not.</span></span> <span data-ttu-id="354f3-242">In dem C#-Beispiel ist `UsingUnsafePointer` eine alternative Methodenimplementierung, die Zeiger anstelle der <xref:System.Runtime.InteropServices.Marshal>-Klasse verwendet, um das Array, das die `MyUnsafeStruct`-Struktur enthält, zurück zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="354f3-242">In the C# sample, `UsingUnsafePointer` is an alternative method implementation that uses pointers instead of the <xref:System.Runtime.InteropServices.Marshal> class to pass back the array containing the `MyUnsafeStruct` structure.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="354f3-243">Deklarieren von Prototypen</span><span class="sxs-lookup"><span data-stu-id="354f3-243">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#20)]
 [!code-csharp[Conceptual.Interop.Marshaling#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#20)]
 [!code-vb[Conceptual.Interop.Marshaling#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#20)]  
  
### <a name="calling-functions"></a><span data-ttu-id="354f3-244">Aufrufen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="354f3-244">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#21](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#21)]
 [!code-csharp[Conceptual.Interop.Marshaling#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#21)]
 [!code-vb[Conceptual.Interop.Marshaling#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="354f3-245">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="354f3-245">See Also</span></span>  
 [<span data-ttu-id="354f3-246">Marshallen von Daten mit Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="354f3-246">Marshaling Data with Platform Invoke</span></span>](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)  
 [<span data-ttu-id="354f3-247">Datentypen für Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="354f3-247">Platform Invoke Data Types</span></span>](http://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f)  
 [<span data-ttu-id="354f3-248">Marshallen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="354f3-248">Marshaling Strings</span></span>](../../../docs/framework/interop/marshaling-strings.md)  
 [<span data-ttu-id="354f3-249">Marshallen von Typenarrays</span><span class="sxs-lookup"><span data-stu-id="354f3-249">Marshaling Arrays of Types</span></span>](http://msdn.microsoft.com/library/049b1c1b-228f-4445-88ec-91bc7fd4b1e8)
