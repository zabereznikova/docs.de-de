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
ms.openlocfilehash: 14770e74a0169dba3a45a04845dd32323e6201e3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415582"
---
# <a name="object-data-type"></a><span data-ttu-id="3474b-102">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="3474b-102">Object Data Type</span></span>

<span data-ttu-id="3474b-103">Enthält Adressen, die auf-Objekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="3474b-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="3474b-104">Sie können einem beliebigen Verweistyp (Zeichenfolge, Array, Klasse oder Schnittstelle) eine `Object` Variable zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3474b-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="3474b-105">Eine `Object` Variable kann auch auf Daten eines beliebigen Werttyps (numerisch, `Boolean` , `Char` , `Date` , Struktur oder Enumeration) verweisen.</span><span class="sxs-lookup"><span data-stu-id="3474b-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>

## <a name="remarks"></a><span data-ttu-id="3474b-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3474b-106">Remarks</span></span>

<span data-ttu-id="3474b-107">Der- `Object` Datentyp kann auf Daten eines beliebigen Datentyps verweisen, einschließlich aller von Ihrer Anwendung erkannten Objektinstanzen.</span><span class="sxs-lookup"><span data-stu-id="3474b-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="3474b-108">Verwenden `Object` Sie, wenn Sie zum Zeitpunkt der Kompilierung nicht wissen, auf welchen Datentyp die Variable verweisen könnte.</span><span class="sxs-lookup"><span data-stu-id="3474b-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>

<span data-ttu-id="3474b-109">Der Standardwert von `Object` ist `Nothing` (ein NULL-Verweis).</span><span class="sxs-lookup"><span data-stu-id="3474b-109">The default value of `Object` is `Nothing` (a null reference).</span></span>

## <a name="data-types"></a><span data-ttu-id="3474b-110">Datentypen</span><span class="sxs-lookup"><span data-stu-id="3474b-110">Data Types</span></span>

<span data-ttu-id="3474b-111">Sie können einer Variablen eine Variable, eine Konstante oder einen Ausdruck eines beliebigen Datentyps zuweisen `Object` .</span><span class="sxs-lookup"><span data-stu-id="3474b-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="3474b-112">Zum Ermitteln des Datentyps `Object` , auf den sich derzeit eine Variable bezieht, können Sie die- <xref:System.Type.GetTypeCode%2A> Methode der-Klasse verwenden <xref:System.Type?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="3474b-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="3474b-113">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3474b-113">The following example illustrates this.</span></span>

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

<span data-ttu-id="3474b-114">Beim `Object` Datentyp handelt es sich um einen Verweistyp.</span><span class="sxs-lookup"><span data-stu-id="3474b-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="3474b-115">Visual Basic behandelt eine Variable jedoch `Object` als Werttyp, wenn Sie auf Daten eines Werttyps verweist.</span><span class="sxs-lookup"><span data-stu-id="3474b-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>

## <a name="storage"></a><span data-ttu-id="3474b-116">Storage</span><span class="sxs-lookup"><span data-stu-id="3474b-116">Storage</span></span>

<span data-ttu-id="3474b-117">Jeder Datentyp, auf den er verweist, `Object` enthält eine Variable nicht den Daten Wert selbst, sondern einen Zeiger auf den Wert.</span><span class="sxs-lookup"><span data-stu-id="3474b-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="3474b-118">Es werden immer vier Bytes im Arbeitsspeicher des Computers verwendet. Dies schließt jedoch nicht den Speicher für die Daten ein, die den Wert der Variablen darstellen.</span><span class="sxs-lookup"><span data-stu-id="3474b-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="3474b-119">Aufgrund des Codes, in dem der-Zeiger verwendet wird, um die Daten zu suchen, `Object` sind Variablen, die Werttypen verwenden, etwas langsamer als die explizit typisierten Variablen.</span><span class="sxs-lookup"><span data-stu-id="3474b-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="3474b-120">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="3474b-120">Programming Tips</span></span>

- <span data-ttu-id="3474b-121">**Interop-Überlegungen.**</span><span class="sxs-lookup"><span data-stu-id="3474b-121">**Interop Considerations.**</span></span> <span data-ttu-id="3474b-122">Wenn Sie mit Komponenten verbunden sind, die nicht für die .NET Framework geschrieben wurden (z. b. Automatisierungs-oder COM-Objekte), beachten Sie, dass Zeiger Typen in anderen Umgebungen nicht mit dem Visual Basic Typ kompatibel sind `Object` .</span><span class="sxs-lookup"><span data-stu-id="3474b-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>

- <span data-ttu-id="3474b-123">**Leistung:**</span><span class="sxs-lookup"><span data-stu-id="3474b-123">**Performance.**</span></span> <span data-ttu-id="3474b-124">Eine Variable, die Sie mit dem-Typ deklarieren `Object` , ist flexibel genug, um einen Verweis auf jedes Objekt zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="3474b-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="3474b-125">Wenn Sie jedoch eine Methode oder Eigenschaft für eine solche Variable aufrufen, wird immer eine *späte Bindung* (zur Laufzeit) verursacht.</span><span class="sxs-lookup"><span data-stu-id="3474b-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="3474b-126">Um eine *frühe Bindung* (zur Kompilierzeit) und eine bessere Leistung zu erzwingen, deklarieren Sie die Variable mit einem bestimmten Klassennamen, oder wandeln Sie Sie in den spezifischen Datentyp um.</span><span class="sxs-lookup"><span data-stu-id="3474b-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>

  <span data-ttu-id="3474b-127">Wenn Sie eine Objekt Variable deklarieren, versuchen Sie, einen bestimmten Klassentyp zu verwenden, z <xref:System.OperatingSystem> . b. anstelle des generalisierten `Object` Typs.</span><span class="sxs-lookup"><span data-stu-id="3474b-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="3474b-128">Sie sollten auch die spezifischere verfügbare Klasse verwenden, z <xref:System.Windows.Forms.TextBox> . b. anstelle von <xref:System.Windows.Forms.Control> , damit Sie auf die Eigenschaften und Methoden zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="3474b-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="3474b-129">In der Regel können Sie die Liste **Klassen** im **Objektkatalog** verwenden, um nach verfügbaren Klassennamen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="3474b-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>

- <span data-ttu-id="3474b-130">**Tet.**</span><span class="sxs-lookup"><span data-stu-id="3474b-130">**Widening.**</span></span> <span data-ttu-id="3474b-131">Alle Datentypen und alle Verweis Typen werden auf den- `Object` Datentyp erweitert.</span><span class="sxs-lookup"><span data-stu-id="3474b-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="3474b-132">Dies bedeutet, dass Sie jeden Typ in konvertieren können, `Object` ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="3474b-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

  <span data-ttu-id="3474b-133">Wenn Sie jedoch zwischen Werttypen und konvertieren `Object` , führt Visual Basic Vorgänge mit dem Namen *Boxing* und *Unboxing*aus, wodurch die Ausführung langsamer wird.</span><span class="sxs-lookup"><span data-stu-id="3474b-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>

- <span data-ttu-id="3474b-134">**Geben Sie Zeichen ein.**</span><span class="sxs-lookup"><span data-stu-id="3474b-134">**Type Characters.**</span></span> <span data-ttu-id="3474b-135">`Object`weist kein Literaltyp Zeichen oder Bezeichnertyp Zeichen auf.</span><span class="sxs-lookup"><span data-stu-id="3474b-135">`Object` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="3474b-136">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="3474b-136">**Framework Type.**</span></span> <span data-ttu-id="3474b-137">Der entsprechende Typ in der .NET Framework ist die- <xref:System.Object?displayProperty=nameWithType> Klasse.</span><span class="sxs-lookup"><span data-stu-id="3474b-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>

## <a name="example"></a><span data-ttu-id="3474b-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3474b-138">Example</span></span>

<span data-ttu-id="3474b-139">Im folgenden Beispiel wird eine `Object` Variable veranschaulicht, die auf eine Objektinstanz verweist.</span><span class="sxs-lookup"><span data-stu-id="3474b-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a><span data-ttu-id="3474b-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3474b-140">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="3474b-141">Datentypen</span><span class="sxs-lookup"><span data-stu-id="3474b-141">Data Types</span></span>](index.md)
- [<span data-ttu-id="3474b-142">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="3474b-142">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="3474b-143">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="3474b-143">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="3474b-144">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="3474b-144">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="3474b-145">Vorgehensweise: Bestimmen des Bezugs zwischen zwei Objekten</span><span class="sxs-lookup"><span data-stu-id="3474b-145">How to: Determine Whether Two Objects Are Related</span></span>](../../programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="3474b-146">Vorgehensweise: Bestimmen der Gleichheit zweier Objekte</span><span class="sxs-lookup"><span data-stu-id="3474b-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
