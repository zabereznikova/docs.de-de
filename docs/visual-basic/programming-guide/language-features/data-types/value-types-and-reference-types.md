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
ms.openlocfilehash: f25caec43b7118b7b64db1b14516b0c5ea80f4f6
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504880"
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="09a7e-102">Wert- und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="09a7e-102">Value Types and Reference Types</span></span>
<span data-ttu-id="09a7e-103">Es gibt zwei Arten von Typen in Visual Basic: Verweistypen und Werttypen.</span><span class="sxs-lookup"><span data-stu-id="09a7e-103">There are two kinds of types in Visual Basic: reference types and value types.</span></span> <span data-ttu-id="09a7e-104">Variablen von Verweistypen speichern Verweise auf ihre Daten (Objekte), während Variablen von Werttypen ihre Daten direkt enthalten.</span><span class="sxs-lookup"><span data-stu-id="09a7e-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="09a7e-105">Bei Verweistypen können zwei Variablen auf dasselbe Objekt verweisen. Daher können auf eine Variable angewendete Operationen das Objekt beeinflussen, auf das von der anderen Variablen verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="09a7e-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="09a7e-106">Bei Werttypen besitzt jede Variable eine eigene Kopie der Daten, und es ist nicht möglich, für Vorgänge für eine Variable, die andere beeinflussen (außer im Fall von der [ByRef-Modifizierer für Parameter](../../../language-reference/modifiers/byref.md)).</span><span class="sxs-lookup"><span data-stu-id="09a7e-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of the [ByRef modifier on parameters](../../../language-reference/modifiers/byref.md)).</span></span>
  
## <a name="value-types"></a><span data-ttu-id="09a7e-107">Werttypen</span><span class="sxs-lookup"><span data-stu-id="09a7e-107">Value Types</span></span>  
 <span data-ttu-id="09a7e-108">Ein Datentyp ist ein *Werttyp* , wenn er die Daten in einer eigenen Speicherbelegung enthält.</span><span class="sxs-lookup"><span data-stu-id="09a7e-108">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="09a7e-109">Die folgenden sind Beispiele für Werttypen:</span><span class="sxs-lookup"><span data-stu-id="09a7e-109">Value types include the following:</span></span>  
  
- <span data-ttu-id="09a7e-110">Alle numerischen Datentypen</span><span class="sxs-lookup"><span data-stu-id="09a7e-110">All numeric data types</span></span>  
  
- <span data-ttu-id="09a7e-111">`Boolean`, `Char`und `Date`</span><span class="sxs-lookup"><span data-stu-id="09a7e-111">`Boolean`, `Char`, and `Date`</span></span>  
  
- <span data-ttu-id="09a7e-112">Alle Strukturen, auch wenn deren Member Verweistypen sind.</span><span class="sxs-lookup"><span data-stu-id="09a7e-112">All structures, even if their members are reference types</span></span>  
  
- <span data-ttu-id="09a7e-113">Enumerationen, da der zugrunde liegende Typ immer `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger` oder `ULong` ist</span><span class="sxs-lookup"><span data-stu-id="09a7e-113">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="09a7e-114">Jede Struktur ist ein Werttyp, auch wenn sie Verweistypmember enthält.</span><span class="sxs-lookup"><span data-stu-id="09a7e-114">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="09a7e-115">Aus diesem Grund werden Werttypen wie z. B. `Char` und `Integer` von .NET Framework-Strukturen implementiert.</span><span class="sxs-lookup"><span data-stu-id="09a7e-115">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="09a7e-116">Sie können einen Werttyp deklarieren, indem Sie das reservierte Schlüsselwort verwenden, z. B. `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="09a7e-116">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="09a7e-117">Sie können auch das Schlüsselwort `New` verwenden, um einen Werttyp zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="09a7e-117">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="09a7e-118">Dies ist besonders nützlich, wenn der Typ über einen Konstruktor verfügt, der Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="09a7e-118">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="09a7e-119">Ein Beispiel hierfür ist der Konstruktor <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>, der einen neue `Decimal`-Wert aus den angegebenen Teilen erstellt.</span><span class="sxs-lookup"><span data-stu-id="09a7e-119">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="09a7e-120">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="09a7e-120">Reference Types</span></span>  
 <span data-ttu-id="09a7e-121">Ein *Verweistyp* speichert einen Verweis auf die Daten.</span><span class="sxs-lookup"><span data-stu-id="09a7e-121">A *reference type* stores a reference to its data.</span></span> <span data-ttu-id="09a7e-122">Verweistypen umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="09a7e-122">Reference types include the following:</span></span>  
  
- `String`  
  
- <span data-ttu-id="09a7e-123">Alle Arrays, auch wenn ihre Elemente Werttypen sind.</span><span class="sxs-lookup"><span data-stu-id="09a7e-123">All arrays, even if their elements are value types</span></span>  
  
- <span data-ttu-id="09a7e-124">Klassentypen Sie, z. B. <xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="09a7e-124">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
- <span data-ttu-id="09a7e-125">Delegaten</span><span class="sxs-lookup"><span data-stu-id="09a7e-125">Delegates</span></span>  
  
 <span data-ttu-id="09a7e-126">Eine Klasse ist eine *Verweistyp*.</span><span class="sxs-lookup"><span data-stu-id="09a7e-126">A class is a *reference type*.</span></span> <span data-ttu-id="09a7e-127">Beachten Sie, dass jedes Array ein Verweistyp ist, auch wenn seine Member Werttypen sind.</span><span class="sxs-lookup"><span data-stu-id="09a7e-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="09a7e-128">Da jede Verweistyp eine zugrunde liegende .NET Framework-Klasse darstellt, müssen Sie verwenden die [neuer Operator](../../../../visual-basic/language-reference/operators/new-operator.md) Schlüsselwort, die Sie bei der Initialisierung.</span><span class="sxs-lookup"><span data-stu-id="09a7e-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="09a7e-129">Die folgende Anweisung initialisiert ein Array.</span><span class="sxs-lookup"><span data-stu-id="09a7e-129">The following statement initializes an array.</span></span>  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="09a7e-130">Elemente, die keine Typen sind</span><span class="sxs-lookup"><span data-stu-id="09a7e-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="09a7e-131">Die folgenden Programmierelemente gelten nicht als Typen, da Sie keines davon als Datentyp für ein deklariertes Element angeben können:</span><span class="sxs-lookup"><span data-stu-id="09a7e-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
- <span data-ttu-id="09a7e-132">Namespaces</span><span class="sxs-lookup"><span data-stu-id="09a7e-132">Namespaces</span></span>  
  
- <span data-ttu-id="09a7e-133">Module</span><span class="sxs-lookup"><span data-stu-id="09a7e-133">Modules</span></span>  
  
- <span data-ttu-id="09a7e-134">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="09a7e-134">Events</span></span>  
  
- <span data-ttu-id="09a7e-135">Eigenschaften und Prozeduren</span><span class="sxs-lookup"><span data-stu-id="09a7e-135">Properties and procedures</span></span>  
  
- <span data-ttu-id="09a7e-136">Variablen, Konstanten und Felder</span><span class="sxs-lookup"><span data-stu-id="09a7e-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="09a7e-137">Arbeiten mit den Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="09a7e-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="09a7e-138">Sie können entweder ein Verweistyp oder ein Werttyp zuweisen, um eine Variable vom die `Object` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="09a7e-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="09a7e-139">Ein `Object` Variable enthält immer einen Verweis auf die Daten nie die Daten selbst.</span><span class="sxs-lookup"><span data-stu-id="09a7e-139">An `Object` variable always holds a reference to the data, never the data itself.</span></span> <span data-ttu-id="09a7e-140">Jedoch wenn Sie einen Werttyp zum Zuweisen einer `Object` Variablen, verhält es sich, als ob es sich um seine eigenen Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="09a7e-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="09a7e-141">Weitere Informationen finden Sie unter [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="09a7e-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="09a7e-142">Finden Sie heraus, ob ein `Object` Variablen fungiert als ein Verweistyp oder ein Werttyp durch Übergabe an die <xref:Microsoft.VisualBasic.Information.IsReference%2A> -Methode in der die <xref:Microsoft.VisualBasic.Information> Klasse von der <xref:Microsoft.VisualBasic?displayProperty=nameWithType> Namespace.</span><span class="sxs-lookup"><span data-stu-id="09a7e-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="09a7e-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> Gibt `True` Wenn den Inhalt der `Object` Variable stellt einen Verweistyp handelt.</span><span class="sxs-lookup"><span data-stu-id="09a7e-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09a7e-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09a7e-144">See also</span></span>

- [<span data-ttu-id="09a7e-145">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="09a7e-145">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="09a7e-146">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="09a7e-146">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="09a7e-147">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="09a7e-147">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="09a7e-148">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="09a7e-148">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="09a7e-149">Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="09a7e-149">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="09a7e-150">Datentypen</span><span class="sxs-lookup"><span data-stu-id="09a7e-150">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
