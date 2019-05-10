---
title: Objekt-Datentyp (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
ms.openlocfilehash: 593fda6a4949a55d77ae70edd19159a618cc6b6d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592078"
---
# <a name="object-data-type"></a><span data-ttu-id="f4924-102">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="f4924-102">Object Data Type</span></span>
<span data-ttu-id="f4924-103">Enthält die Adressen, die auf Objekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="f4924-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="f4924-104">Sie können den Verweistyp (Zeichenfolge, Array, Klasse oder Schnittstelle) zuweisen, um eine `Object` Variable.</span><span class="sxs-lookup"><span data-stu-id="f4924-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="f4924-105">Ein `Object` Variablen finden Sie auch die Daten eines beliebigen Werttyps (numerisch, `Boolean`, `Char`, `Date`, Struktur oder Enumeration).</span><span class="sxs-lookup"><span data-stu-id="f4924-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4924-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f4924-106">Remarks</span></span>  
 <span data-ttu-id="f4924-107">Die `Object` -Datentyp kann auf Daten eines beliebigen Datentyps, einschließlich Objektinstanzen der Anwendung erkannt zeigen.</span><span class="sxs-lookup"><span data-stu-id="f4924-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="f4924-108">Verwendung `Object` , wenn Sie nicht zur Kompilierzeit wissen welchen Datentyp die Variable möglicherweise zeigen Sie auf.</span><span class="sxs-lookup"><span data-stu-id="f4924-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>  
  
 <span data-ttu-id="f4924-109">Der Standardwert von `Object` ist `Nothing` (ein null-Verweis).</span><span class="sxs-lookup"><span data-stu-id="f4924-109">The default value of `Object` is `Nothing` (a null reference).</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="f4924-110">Datentypen</span><span class="sxs-lookup"><span data-stu-id="f4924-110">Data Types</span></span>  
 <span data-ttu-id="f4924-111">Sie können eine Variable, eine Konstante oder ein Ausdruck eines beliebigen Datentyps, Zuweisen einer `Object` Variable.</span><span class="sxs-lookup"><span data-stu-id="f4924-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="f4924-112">Um zu bestimmen, den Datentyp einer `Object` -Variable aktuell verweist, können Sie mit der <xref:System.Type.GetTypeCode%2A> -Methode der der <xref:System.Type?displayProperty=nameWithType> Klasse.</span><span class="sxs-lookup"><span data-stu-id="f4924-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="f4924-113">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f4924-113">The following example illustrates this.</span></span>  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 <span data-ttu-id="f4924-114">Die `Object` Datentyp ein Verweistyp ist.</span><span class="sxs-lookup"><span data-stu-id="f4924-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="f4924-115">Visual Basic jedoch behandelt eine `Object` -Variable als einen Werttyp, wenn sie auf die Daten eines Werttyps verweist.</span><span class="sxs-lookup"><span data-stu-id="f4924-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>  
  
## <a name="storage"></a><span data-ttu-id="f4924-116">Speicher</span><span class="sxs-lookup"><span data-stu-id="f4924-116">Storage</span></span>  
 <span data-ttu-id="f4924-117">Beliebige Datentyp verweist, eine `Object` sind keine enthalten dem Datenwert selbst, sondern stattdessen ein Zeiger auf den Wert.</span><span class="sxs-lookup"><span data-stu-id="f4924-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="f4924-118">Sie verwendet stets die vier Bytes im Arbeitsspeicher des Computers, aber dies schließt nicht den Speicher für die Daten, die den Wert der Variablen darstellt.</span><span class="sxs-lookup"><span data-stu-id="f4924-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="f4924-119">Aufgrund der Code, der den Zeiger verwendet, um die Daten zu suchen `Object` Variablen, die Werttypen sind etwas langsamer als explizit typisierte Variablen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f4924-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="f4924-120">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="f4924-120">Programming Tips</span></span>  
  
- <span data-ttu-id="f4924-121">**Interop-Überlegungen.**</span><span class="sxs-lookup"><span data-stu-id="f4924-121">**Interop Considerations.**</span></span> <span data-ttu-id="f4924-122">Wenn Sie anbinden, Komponenten, die nicht für .NET Framework, z. B. Automatisierungs- oder COM-Objekte, geschriebenen müssen bedenken, dass Zeigertypen in anderen Umgebungen nicht mit den Visual Basic kompatibel sind `Object` Typ.</span><span class="sxs-lookup"><span data-stu-id="f4924-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>  
  
- <span data-ttu-id="f4924-123">**Leistung:**</span><span class="sxs-lookup"><span data-stu-id="f4924-123">**Performance.**</span></span> <span data-ttu-id="f4924-124">Eine Variable, die Sie deklarieren, mit der `Object` flexibel genug, um einen Verweis auf ein Objekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="f4924-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="f4924-125">Jedoch beim Aufrufen einer Methode oder Eigenschaft auf eine solche Variable immer fallen *späte Bindung* (Laufzeit).</span><span class="sxs-lookup"><span data-stu-id="f4924-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="f4924-126">Um zu erzwingen *frühe Bindung* (zum Zeitpunkt der Kompilierung) und eine bessere Leistung, deklarieren Sie die Variable mit einem bestimmten Klassennamen oder in der bestimmten Datentyp umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="f4924-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>  
  
     <span data-ttu-id="f4924-127">Beim Deklarieren einer Objektvariablen, versuchen Sie es an einen bestimmten Klassentyp, z.B. <xref:System.OperatingSystem>, anstatt die generalisierte `Object` Typ.</span><span class="sxs-lookup"><span data-stu-id="f4924-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="f4924-128">Verwenden Sie außerdem die spezifischste Klasse verfügbar sind, z. B. <xref:System.Windows.Forms.TextBox> anstelle von <xref:System.Windows.Forms.Control>, sodass Sie dessen Eigenschaften und Methoden zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="f4924-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="f4924-129">In der Regel können Sie die **Klassen** Liste der **Objektkatalog** verfügbaren Klassennamen zu finden.</span><span class="sxs-lookup"><span data-stu-id="f4924-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>  
  
- <span data-ttu-id="f4924-130">**Erweiternde.**</span><span class="sxs-lookup"><span data-stu-id="f4924-130">**Widening.**</span></span> <span data-ttu-id="f4924-131">Alle Datentypen und alle Verweistypen werden erweitert, um die `Object` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="f4924-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="f4924-132">Dies bedeutet, Sie können einen beliebigen Typ zu konvertieren `Object` unabhängig vom eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.</span><span class="sxs-lookup"><span data-stu-id="f4924-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
     <span data-ttu-id="f4924-133">Allerdings, wenn die Konvertierung zwischen Werttypen und `Object`, Visual Basic führt Operationen mit Bezeichnung *Boxing* und *unboxing*, die Ausführung langsamer stellen.</span><span class="sxs-lookup"><span data-stu-id="f4924-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>  
  
- <span data-ttu-id="f4924-134">**Typzeichen.**</span><span class="sxs-lookup"><span data-stu-id="f4924-134">**Type Characters.**</span></span> <span data-ttu-id="f4924-135">`Object` hat kein literal-Typzeichen oder Bezeichner-Typzeichen.</span><span class="sxs-lookup"><span data-stu-id="f4924-135">`Object` has no literal type character or identifier type character.</span></span>  
  
- <span data-ttu-id="f4924-136">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="f4924-136">**Framework Type.**</span></span> <span data-ttu-id="f4924-137">Der entsprechende Typ in .NET Framework ist die <xref:System.Object?displayProperty=nameWithType> Klasse.</span><span class="sxs-lookup"><span data-stu-id="f4924-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4924-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f4924-138">Example</span></span>  
 <span data-ttu-id="f4924-139">Das folgende Beispiel veranschaulicht eine `Object` Variable, die auf eine Objektinstanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="f4924-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## <a name="see-also"></a><span data-ttu-id="f4924-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4924-140">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="f4924-141">Datentypen</span><span class="sxs-lookup"><span data-stu-id="f4924-141">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="f4924-142">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="f4924-142">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="f4924-143">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="f4924-143">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="f4924-144">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="f4924-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="f4924-145">Vorgehensweise: Bestimmen Sie, ob zwei Objekte verknüpft sind</span><span class="sxs-lookup"><span data-stu-id="f4924-145">How to: Determine Whether Two Objects Are Related</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="f4924-146">Vorgehensweise: Bestimmt, ob zwei Objekte identisch sind.</span><span class="sxs-lookup"><span data-stu-id="f4924-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
