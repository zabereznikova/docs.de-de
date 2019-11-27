---
title: Object Data Type
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
ms.openlocfilehash: 2ccb9b69b865c259d078ed9642d63c7f83514756
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343965"
---
# <a name="object-data-type"></a><span data-ttu-id="d98f7-102">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="d98f7-102">Object Data Type</span></span>

<span data-ttu-id="d98f7-103">Enthält Adressen, die auf-Objekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="d98f7-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="d98f7-104">Sie können einen beliebigen Verweistyp (Zeichenfolge, Array, Klasse oder Schnittstelle) einer `Object` Variablen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d98f7-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="d98f7-105">Eine `Object` Variable kann auch auf Daten eines beliebigen Werttyps (numerisch, `Boolean`, `Char`, `Date`, Struktur oder Enumeration) verweisen.</span><span class="sxs-lookup"><span data-stu-id="d98f7-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>

## <a name="remarks"></a><span data-ttu-id="d98f7-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d98f7-106">Remarks</span></span>

<span data-ttu-id="d98f7-107">Der `Object`-Datentyp kann auf Daten eines beliebigen Datentyps verweisen, einschließlich aller von Ihrer Anwendung erkannten Objektinstanzen.</span><span class="sxs-lookup"><span data-stu-id="d98f7-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="d98f7-108">Verwenden Sie `Object`, wenn Sie zum Zeitpunkt der Kompilierung nicht wissen, auf welchen Datentyp die Variable verweisen könnte.</span><span class="sxs-lookup"><span data-stu-id="d98f7-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>

<span data-ttu-id="d98f7-109">Der Standardwert `Object` ist `Nothing` (ein NULL-Verweis).</span><span class="sxs-lookup"><span data-stu-id="d98f7-109">The default value of `Object` is `Nothing` (a null reference).</span></span>

## <a name="data-types"></a><span data-ttu-id="d98f7-110">Datentypen</span><span class="sxs-lookup"><span data-stu-id="d98f7-110">Data Types</span></span>

<span data-ttu-id="d98f7-111">Sie können einer `Object` Variablen eine Variable, eine Konstante oder einen Ausdruck eines beliebigen Datentyps zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d98f7-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="d98f7-112">Zum Ermitteln des Datentyps, auf den sich eine `Object` Variable derzeit bezieht, können Sie die <xref:System.Type.GetTypeCode%2A>-Methode der <xref:System.Type?displayProperty=nameWithType>-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="d98f7-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="d98f7-113">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d98f7-113">The following example illustrates this.</span></span>

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

<span data-ttu-id="d98f7-114">Der `Object`-Datentyp ist ein Referenztyp.</span><span class="sxs-lookup"><span data-stu-id="d98f7-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="d98f7-115">Visual Basic behandelt jedoch eine `Object` Variable als Werttyp, wenn Sie auf Daten eines Werttyps verweist.</span><span class="sxs-lookup"><span data-stu-id="d98f7-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>

## <a name="storage"></a><span data-ttu-id="d98f7-116">Speicher</span><span class="sxs-lookup"><span data-stu-id="d98f7-116">Storage</span></span>

<span data-ttu-id="d98f7-117">Jeder Datentyp, auf den er verweist, eine `Object` Variable enthält nicht den Daten Wert selbst, sondern einen Zeiger auf den Wert.</span><span class="sxs-lookup"><span data-stu-id="d98f7-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="d98f7-118">Es werden immer vier Bytes im Arbeitsspeicher des Computers verwendet. Dies schließt jedoch nicht den Speicher für die Daten ein, die den Wert der Variablen darstellen.</span><span class="sxs-lookup"><span data-stu-id="d98f7-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="d98f7-119">Aufgrund des Codes, in dem der-Zeiger zum Suchen der Daten verwendet wird, sind `Object` Variablen, die Werttypen verwenden, etwas langsamer für den Zugriff als explizit typisierte Variablen.</span><span class="sxs-lookup"><span data-stu-id="d98f7-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="d98f7-120">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="d98f7-120">Programming Tips</span></span>

- <span data-ttu-id="d98f7-121">**Interop-Überlegungen.**</span><span class="sxs-lookup"><span data-stu-id="d98f7-121">**Interop Considerations.**</span></span> <span data-ttu-id="d98f7-122">Wenn Sie mit Komponenten verbunden sind, die nicht für die .NET Framework geschrieben wurden (z. b. Automatisierungs-oder COM-Objekte), beachten Sie, dass Zeiger Typen in anderen Umgebungen nicht mit dem Visual Basic `Object` Typ kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="d98f7-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>

- <span data-ttu-id="d98f7-123">**Leistung**</span><span class="sxs-lookup"><span data-stu-id="d98f7-123">**Performance.**</span></span> <span data-ttu-id="d98f7-124">Eine Variable, die Sie mit dem `Object`-Typ deklarieren, ist flexibel genug, um einen Verweis auf jedes Objekt zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="d98f7-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="d98f7-125">Wenn Sie jedoch eine Methode oder Eigenschaft für eine solche Variable aufrufen, wird immer eine *späte Bindung* (zur Laufzeit) verursacht.</span><span class="sxs-lookup"><span data-stu-id="d98f7-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="d98f7-126">Um eine *frühe Bindung* (zur Kompilierzeit) und eine bessere Leistung zu erzwingen, deklarieren Sie die Variable mit einem bestimmten Klassennamen, oder wandeln Sie Sie in den spezifischen Datentyp um.</span><span class="sxs-lookup"><span data-stu-id="d98f7-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>

  <span data-ttu-id="d98f7-127">Wenn Sie eine Objekt Variable deklarieren, versuchen Sie, einen bestimmten Klassentyp, z. b. <xref:System.OperatingSystem>, anstelle des generalisierten `Object` Typs zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d98f7-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="d98f7-128">Sie sollten auch die spezifischere verfügbare Klasse verwenden, wie z. b. <xref:System.Windows.Forms.TextBox> anstelle von <xref:System.Windows.Forms.Control>, damit Sie auf die Eigenschaften und Methoden zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="d98f7-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="d98f7-129">In der Regel können Sie die Liste **Klassen** im **Objektkatalog** verwenden, um nach verfügbaren Klassennamen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="d98f7-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>

- <span data-ttu-id="d98f7-130">**Tet.**</span><span class="sxs-lookup"><span data-stu-id="d98f7-130">**Widening.**</span></span> <span data-ttu-id="d98f7-131">Alle Datentypen und alle Verweis Typen werden auf den Datentyp `Object` erweitert.</span><span class="sxs-lookup"><span data-stu-id="d98f7-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="d98f7-132">Dies bedeutet, dass Sie jeden Typ in `Object` konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="d98f7-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

  <span data-ttu-id="d98f7-133">Wenn Sie jedoch zwischen Werttypen und `Object`konvertieren, führt Visual Basic Vorgänge aus, die als *Boxing* und *Unboxing*bezeichnet werden. Dadurch wird die Ausführung langsamer.</span><span class="sxs-lookup"><span data-stu-id="d98f7-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>

- <span data-ttu-id="d98f7-134">**Geben Sie Zeichen ein.**</span><span class="sxs-lookup"><span data-stu-id="d98f7-134">**Type Characters.**</span></span> <span data-ttu-id="d98f7-135">`Object` hat kein Literaltyp Zeichen oder Bezeichnertyp Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d98f7-135">`Object` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="d98f7-136">**Frameworktyp.**</span><span class="sxs-lookup"><span data-stu-id="d98f7-136">**Framework Type.**</span></span> <span data-ttu-id="d98f7-137">Der entsprechende Typ in der .NET Framework ist die <xref:System.Object?displayProperty=nameWithType> Klasse.</span><span class="sxs-lookup"><span data-stu-id="d98f7-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>

## <a name="example"></a><span data-ttu-id="d98f7-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d98f7-138">Example</span></span>

<span data-ttu-id="d98f7-139">Im folgenden Beispiel wird eine `Object` Variable veranschaulicht, die auf eine Objektinstanz verweist.</span><span class="sxs-lookup"><span data-stu-id="d98f7-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a><span data-ttu-id="d98f7-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d98f7-140">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="d98f7-141">Datentypen</span><span class="sxs-lookup"><span data-stu-id="d98f7-141">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="d98f7-142">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="d98f7-142">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="d98f7-143">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="d98f7-143">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="d98f7-144">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="d98f7-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="d98f7-145">Gewusst wie: Bestimmen des Bezugs zwischen zwei Objekten</span><span class="sxs-lookup"><span data-stu-id="d98f7-145">How to: Determine Whether Two Objects Are Related</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="d98f7-146">Gewusst wie: Bestimmen der Gleichheit zweier Objekte</span><span class="sxs-lookup"><span data-stu-id="d98f7-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
