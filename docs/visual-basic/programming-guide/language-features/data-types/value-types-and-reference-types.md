---
title: Wert- und Verweistypen
ms.date: 07/20/2015
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
ms.openlocfilehash: 3a1de120f5f97ba93939f332f121d70cd3091216
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392973"
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="4b94b-102">Wert- und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="4b94b-102">Value Types and Reference Types</span></span>
<span data-ttu-id="4b94b-103">Es gibt zwei Arten von Typen in Visual Basic: Verweis Typen und Werttypen.</span><span class="sxs-lookup"><span data-stu-id="4b94b-103">There are two kinds of types in Visual Basic: reference types and value types.</span></span> <span data-ttu-id="4b94b-104">Variablen von Verweistypen speichern Verweise auf ihre Daten (Objekte), während Variablen von Werttypen ihre Daten direkt enthalten.</span><span class="sxs-lookup"><span data-stu-id="4b94b-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="4b94b-105">Bei Verweistypen können zwei Variablen auf dasselbe Objekt verweisen. Daher können auf eine Variable angewendete Operationen das Objekt beeinflussen, auf das von der anderen Variablen verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="4b94b-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="4b94b-106">Bei Werttypen besitzt jede Variable eine eigene Kopie der Daten, und es ist nicht möglich, dass sich Vorgänge für eine Variable auf den anderen auswirken (außer im Fall des [ByRef-Modifizierers für Parameter](../../../language-reference/modifiers/byref.md)).</span><span class="sxs-lookup"><span data-stu-id="4b94b-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of the [ByRef modifier on parameters](../../../language-reference/modifiers/byref.md)).</span></span>
  
## <a name="value-types"></a><span data-ttu-id="4b94b-107">Werttypen</span><span class="sxs-lookup"><span data-stu-id="4b94b-107">Value Types</span></span>  
 <span data-ttu-id="4b94b-108">Ein Datentyp ist ein *Werttyp* , wenn die Daten in der eigenen Speicher Belegung enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4b94b-108">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="4b94b-109">Zu den Werttypen zählen die folgenden:</span><span class="sxs-lookup"><span data-stu-id="4b94b-109">Value types include the following:</span></span>  
  
- <span data-ttu-id="4b94b-110">Alle numerischen Datentypen</span><span class="sxs-lookup"><span data-stu-id="4b94b-110">All numeric data types</span></span>  
  
- <span data-ttu-id="4b94b-111">`Boolean`, `Char` und `Date`</span><span class="sxs-lookup"><span data-stu-id="4b94b-111">`Boolean`, `Char`, and `Date`</span></span>  
  
- <span data-ttu-id="4b94b-112">Alle Strukturen, auch wenn ihre Member Verweis Typen sind</span><span class="sxs-lookup"><span data-stu-id="4b94b-112">All structures, even if their members are reference types</span></span>  
  
- <span data-ttu-id="4b94b-113">Enumerationen, da der zugrunde liegende Typ immer `SByte` , `Short` , `Integer` , `Long` , `Byte` , `UShort` , `UInteger` oder ist.`ULong`</span><span class="sxs-lookup"><span data-stu-id="4b94b-113">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="4b94b-114">Jede Struktur ist ein Werttyp, auch wenn Sie Verweistyp Member enthält.</span><span class="sxs-lookup"><span data-stu-id="4b94b-114">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="4b94b-115">Aus diesem Grund werden Werttypen wie `Char` und `Integer` durch .NET Framework Strukturen implementiert.</span><span class="sxs-lookup"><span data-stu-id="4b94b-115">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="4b94b-116">Sie können einen Werttyp deklarieren, indem Sie das reservierte Schlüsselwort verwenden, z `Decimal` . b..</span><span class="sxs-lookup"><span data-stu-id="4b94b-116">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="4b94b-117">Sie können auch das- `New` Schlüsselwort verwenden, um einen Werttyp zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="4b94b-117">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="4b94b-118">Dies ist besonders nützlich, wenn der Typ über einen Konstruktor verfügt, der Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="4b94b-118">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="4b94b-119">Ein Beispiel hierfür ist der- <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> Konstruktor, der einen neuen `Decimal` Wert aus den angegebenen Teilen erstellt.</span><span class="sxs-lookup"><span data-stu-id="4b94b-119">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="4b94b-120">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="4b94b-120">Reference Types</span></span>  
 <span data-ttu-id="4b94b-121">Ein *Verweistyp* speichert einen Verweis auf seine Daten.</span><span class="sxs-lookup"><span data-stu-id="4b94b-121">A *reference type* stores a reference to its data.</span></span> <span data-ttu-id="4b94b-122">Verweis Typen umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4b94b-122">Reference types include the following:</span></span>  
  
- `String`  
  
- <span data-ttu-id="4b94b-123">Alle Arrays, auch wenn ihre Elemente Werttypen sind</span><span class="sxs-lookup"><span data-stu-id="4b94b-123">All arrays, even if their elements are value types</span></span>  
  
- <span data-ttu-id="4b94b-124">Klassentypen, z. b.<xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="4b94b-124">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
- <span data-ttu-id="4b94b-125">Delegaten</span><span class="sxs-lookup"><span data-stu-id="4b94b-125">Delegates</span></span>  
  
 <span data-ttu-id="4b94b-126">Eine Klasse ist ein *Verweistyp*.</span><span class="sxs-lookup"><span data-stu-id="4b94b-126">A class is a *reference type*.</span></span> <span data-ttu-id="4b94b-127">Beachten Sie, dass jedes Array ein Verweistyp ist, auch wenn seine Member Werttypen sind.</span><span class="sxs-lookup"><span data-stu-id="4b94b-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="4b94b-128">Da jeder Verweistyp eine zugrunde liegende .NET Framework Klasse darstellt, müssen Sie das [neue Operator](../../../language-reference/operators/new-operator.md) Schlüsselwort verwenden, wenn Sie es initialisieren.</span><span class="sxs-lookup"><span data-stu-id="4b94b-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="4b94b-129">Mit der folgenden Anweisung wird ein Array initialisiert.</span><span class="sxs-lookup"><span data-stu-id="4b94b-129">The following statement initializes an array.</span></span>  
  
```vb  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="4b94b-130">Elemente, die keine Typen sind</span><span class="sxs-lookup"><span data-stu-id="4b94b-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="4b94b-131">Die folgenden Programmier Elemente sind nicht als-Typen qualifiziert, da Sie Sie nicht als Datentyp für ein deklariertes Element angeben können:</span><span class="sxs-lookup"><span data-stu-id="4b94b-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
- <span data-ttu-id="4b94b-132">Namespaces</span><span class="sxs-lookup"><span data-stu-id="4b94b-132">Namespaces</span></span>  
  
- <span data-ttu-id="4b94b-133">Module</span><span class="sxs-lookup"><span data-stu-id="4b94b-133">Modules</span></span>  
  
- <span data-ttu-id="4b94b-134">Events</span><span class="sxs-lookup"><span data-stu-id="4b94b-134">Events</span></span>  
  
- <span data-ttu-id="4b94b-135">Eigenschaften und Prozeduren</span><span class="sxs-lookup"><span data-stu-id="4b94b-135">Properties and procedures</span></span>  
  
- <span data-ttu-id="4b94b-136">Variablen, Konstanten und Felder</span><span class="sxs-lookup"><span data-stu-id="4b94b-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="4b94b-137">Arbeiten mit dem Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="4b94b-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="4b94b-138">Sie können einer Variablen des-Datentyps entweder einen Verweistyp oder einen Werttyp zuweisen `Object` .</span><span class="sxs-lookup"><span data-stu-id="4b94b-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="4b94b-139">Eine `Object` Variable enthält immer einen Verweis auf die Daten, nie die Daten selbst.</span><span class="sxs-lookup"><span data-stu-id="4b94b-139">An `Object` variable always holds a reference to the data, never the data itself.</span></span> <span data-ttu-id="4b94b-140">Wenn Sie jedoch einer Variablen einen Werttyp zuweisen `Object` , verhält er sich so, als ob er seine eigenen Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="4b94b-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="4b94b-141">Weitere Informationen finden Sie unter [Object Data Type](../../../language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="4b94b-141">For more information, see [Object Data Type](../../../language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="4b94b-142">Sie können herausfinden, ob eine `Object` Variable als Verweistyp oder Werttyp fungiert, indem Sie Sie an die- <xref:Microsoft.VisualBasic.Information.IsReference%2A> Methode in der- <xref:Microsoft.VisualBasic.Information> Klasse des- <xref:Microsoft.VisualBasic?displayProperty=nameWithType> Namespace übergeben.</span><span class="sxs-lookup"><span data-stu-id="4b94b-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="4b94b-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType>Gibt zurück, `True` Wenn der Inhalt der `Object` Variablen einen Verweistyp darstellt.</span><span class="sxs-lookup"><span data-stu-id="4b94b-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b94b-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4b94b-144">See also</span></span>

- [<span data-ttu-id="4b94b-145">Nullable-Werttypen</span><span class="sxs-lookup"><span data-stu-id="4b94b-145">Nullable Value Types</span></span>](nullable-value-types.md)
- [<span data-ttu-id="4b94b-146">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4b94b-146">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="4b94b-147">Structure Statement</span><span class="sxs-lookup"><span data-stu-id="4b94b-147">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="4b94b-148">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="4b94b-148">Efficient Use of Data Types</span></span>](efficient-use-of-data-types.md)
- [<span data-ttu-id="4b94b-149">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="4b94b-149">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="4b94b-150">Datentypen</span><span class="sxs-lookup"><span data-stu-id="4b94b-150">Data Types</span></span>](index.md)
