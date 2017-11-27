---
title: Object Data Type
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 847f2b50296ad1a1ba6f0009d1d6afced27f9abe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="object-data-type"></a><span data-ttu-id="b9445-102">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="b9445-102">Object Data Type</span></span>
<span data-ttu-id="b9445-103">Enthält die Adressen, die auf Objekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="b9445-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="b9445-104">Sie können Verweistyp (Zeichenfolge, Array, Klasse oder Schnittstelle) zuweisen, um eine `Object` Variable.</span><span class="sxs-lookup"><span data-stu-id="b9445-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="b9445-105">Ein `Object` Variable kann auch auf Daten mit einem beliebigen Werttyp verweisen (numeric, `Boolean`, `Char`, `Date`, Struktur oder Enumeration).</span><span class="sxs-lookup"><span data-stu-id="b9445-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9445-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b9445-106">Remarks</span></span>  
 <span data-ttu-id="b9445-107">Die `Object` -Datentyp kann auf Daten eines beliebigen Datentyps, einschließlich jede Objektinstanz, die die Anwendung erkennt zeigen.</span><span class="sxs-lookup"><span data-stu-id="b9445-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="b9445-108">Verwendung `Object` , wenn Sie nicht zur Kompilierzeit wissen welchen Datentyp die Variable möglicherweise zeigen Sie auf.</span><span class="sxs-lookup"><span data-stu-id="b9445-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>  
  
 <span data-ttu-id="b9445-109">Der Standardwert von `Object` ist `Nothing` (ein null-Verweis).</span><span class="sxs-lookup"><span data-stu-id="b9445-109">The default value of `Object` is `Nothing` (a null reference).</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="b9445-110">Datentypen</span><span class="sxs-lookup"><span data-stu-id="b9445-110">Data Types</span></span>  
 <span data-ttu-id="b9445-111">Sie können eine Variable, eine Konstante oder ein Ausdruck eines beliebigen Datentyps zum Zuweisen einer `Object` Variable.</span><span class="sxs-lookup"><span data-stu-id="b9445-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="b9445-112">Zum Ermitteln des Datentyps einer `Object` Variable aktuell verweist, können Sie mithilfe der <xref:System.Type.GetTypeCode%2A> Methode der <xref:System.Type?displayProperty=nameWithType> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b9445-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="b9445-113">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b9445-113">The following example illustrates this.</span></span>  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 <span data-ttu-id="b9445-114">Die `Object` -Datentyp ist ein Verweistyp.</span><span class="sxs-lookup"><span data-stu-id="b9445-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="b9445-115">Visual Basic behandelt jedoch eine `Object` -Variable als ein Werttyp, wenn sie auf Daten eines Werttyps verweist.</span><span class="sxs-lookup"><span data-stu-id="b9445-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>  
  
## <a name="storage"></a><span data-ttu-id="b9445-116">Speicher</span><span class="sxs-lookup"><span data-stu-id="b9445-116">Storage</span></span>  
 <span data-ttu-id="b9445-117">Der Datentyp verweist, eine `Object` Variable enthält nicht dem Datenwert selbst, sondern einen Zeiger auf den Wert.</span><span class="sxs-lookup"><span data-stu-id="b9445-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="b9445-118">Es verwendet vier Bytes immer im Arbeitsspeicher des Computers, aber dies schließt nicht den Speicher für die Daten, die den Wert der Variablen darstellt.</span><span class="sxs-lookup"><span data-stu-id="b9445-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="b9445-119">Aufgrund der Code, der den Zeiger verwendet wird, um die Daten zu suchen `Object` -Variablen, die Werttypen sind etwas langsamer als explizit typisierte Variablen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b9445-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="b9445-120">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="b9445-120">Programming Tips</span></span>  
  
-   <span data-ttu-id="b9445-121">**Interop-Überlegungen.**</span><span class="sxs-lookup"><span data-stu-id="b9445-121">**Interop Considerations.**</span></span> <span data-ttu-id="b9445-122">Wenn Sie Komponenten, die nicht für .NET Framework, z. B. Automatisierungs- oder COM-Objekte, geschriebenen Datenbreite sollten Sie bedenken, dass Zeigertypen in anderen Umgebungen nicht mit Visual Basic kompatibel sind `Object` Typ.</span><span class="sxs-lookup"><span data-stu-id="b9445-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>  
  
-   <span data-ttu-id="b9445-123">**Leistung:**</span><span class="sxs-lookup"><span data-stu-id="b9445-123">**Performance.**</span></span> <span data-ttu-id="b9445-124">Eine Variable, die Sie deklarieren die `Object` flexibel genug, um einen Verweis auf ein beliebiges Objekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="b9445-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="b9445-125">Jedoch, wenn Sie eine Methode oder Eigenschaft für eine solche Variable aufrufen, immer anfallen *späte Bindung* (Laufzeit).</span><span class="sxs-lookup"><span data-stu-id="b9445-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="b9445-126">Gezwungen *frühe Bindung* (zum Zeitpunkt der Kompilierung) und zu einer besseren Leistung, deklarieren Sie die Variable mit einem bestimmten Klassennamen, oder es in den betreffenden Datentyp umwandeln.</span><span class="sxs-lookup"><span data-stu-id="b9445-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>  
  
     <span data-ttu-id="b9445-127">Wenn Sie eine Objektvariable deklarieren, verwenden Sie beispielsweise einen bestimmten Klassentyp versucht <xref:System.OperatingSystem>, anstatt das generalisierte `Object` Typ.</span><span class="sxs-lookup"><span data-stu-id="b9445-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="b9445-128">Verwenden Sie zudem die spezifischste Klasse verfügbar sind, z. B. <xref:System.Windows.Forms.TextBox> anstelle von <xref:System.Windows.Forms.Control>, sodass Sie die Eigenschaften und Methoden zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="b9445-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="b9445-129">In der Regel können Sie die **Klassen** in Liste der **Objektkatalog** verfügbaren Klassennamen gefunden.</span><span class="sxs-lookup"><span data-stu-id="b9445-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>  
  
-   <span data-ttu-id="b9445-130">**Widening.**</span><span class="sxs-lookup"><span data-stu-id="b9445-130">**Widening.**</span></span> <span data-ttu-id="b9445-131">Alle Datentypen und alle Verweistypen erweitert werden, um die `Object` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="b9445-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="b9445-132">Dies bedeutet, Sie können einen beliebigen Typ zu konvertieren `Object` ohne dass eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.</span><span class="sxs-lookup"><span data-stu-id="b9445-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
     <span data-ttu-id="b9445-133">Allerdings, wenn die Konvertierung zwischen Werttypen und `Object`, Visual Basic führt Vorgänge aufgerufen *Boxing* und *unboxing*, die Ausführung verlangsamt bilden.</span><span class="sxs-lookup"><span data-stu-id="b9445-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>  
  
-   <span data-ttu-id="b9445-134">**Typzeichen.**</span><span class="sxs-lookup"><span data-stu-id="b9445-134">**Type Characters.**</span></span> <span data-ttu-id="b9445-135">`Object`hat kein literal-Typzeichen oder Bezeichner-Typzeichen.</span><span class="sxs-lookup"><span data-stu-id="b9445-135">`Object` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="b9445-136">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="b9445-136">**Framework Type.**</span></span> <span data-ttu-id="b9445-137">Der entsprechende Typ in .NET Framework ist die <xref:System.Object?displayProperty=nameWithType> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b9445-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9445-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9445-138">Example</span></span>  
 <span data-ttu-id="b9445-139">Das folgende Beispiel veranschaulicht eine `Object` Variable verweist auf eine Objektinstanz.</span><span class="sxs-lookup"><span data-stu-id="b9445-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## <a name="see-also"></a><span data-ttu-id="b9445-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9445-140">See Also</span></span>  
 <xref:System.Object>  
 [<span data-ttu-id="b9445-141">Datentypen</span><span class="sxs-lookup"><span data-stu-id="b9445-141">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="b9445-142">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="b9445-142">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="b9445-143">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="b9445-143">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="b9445-144">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="b9445-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="b9445-145">Gewusst wie: Bestimmen des Bezugs zwischen zwei Objekten</span><span class="sxs-lookup"><span data-stu-id="b9445-145">How to: Determine Whether Two Objects Are Related</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [<span data-ttu-id="b9445-146">Gewusst wie: Bestimmen der Gleichheit zweier Objekte</span><span class="sxs-lookup"><span data-stu-id="b9445-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
