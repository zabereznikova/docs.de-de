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
ms.openlocfilehash: 9456316f71a213905bcb50336533c4e618f5174a
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42934184"
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="3d749-102">Wert- und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="3d749-102">Value Types and Reference Types</span></span>
<span data-ttu-id="3d749-103">In Visual Basic werden Datentypen basierend auf deren Klassifizierung implementiert.</span><span class="sxs-lookup"><span data-stu-id="3d749-103">In Visual Basic, data types are implemented based on their classification.</span></span> <span data-ttu-id="3d749-104">Die Visual Basic-Datentypen können klassifiziert werden, gemäß der gibt an, ob eine Variable eines bestimmten Typs seine eigenen Daten oder ein Zeiger auf die Daten speichert.</span><span class="sxs-lookup"><span data-stu-id="3d749-104">The Visual Basic data types can be classified according to whether a variable of a particular type stores its own data or a pointer to the data.</span></span> <span data-ttu-id="3d749-105">Wenn seine eigenen Daten speichert, es ist ein *Werttyp*; Wenn sie einen Zeiger auf die Daten an anderer Stelle im Arbeitsspeicher enthält es eine *Verweistyp*.</span><span class="sxs-lookup"><span data-stu-id="3d749-105">If it stores its own data it is a *value type*; if it holds a pointer to data elsewhere in memory it is a *reference type*.</span></span>  
  
## <a name="value-types"></a><span data-ttu-id="3d749-106">Werttypen</span><span class="sxs-lookup"><span data-stu-id="3d749-106">Value Types</span></span>  
 <span data-ttu-id="3d749-107">Ein Datentyp ist ein *Werttyp* , wenn sie die Daten in eine eigene speicherbelegung enthält.</span><span class="sxs-lookup"><span data-stu-id="3d749-107">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="3d749-108">Die folgenden: Werttypen</span><span class="sxs-lookup"><span data-stu-id="3d749-108">Value types include the following:</span></span>  
  
-   <span data-ttu-id="3d749-109">Alle numerischen Datentypen</span><span class="sxs-lookup"><span data-stu-id="3d749-109">All numeric data types</span></span>  
  
-   <span data-ttu-id="3d749-110">`Boolean`, `Char` und `Date`</span><span class="sxs-lookup"><span data-stu-id="3d749-110">`Boolean`, `Char`, and `Date`</span></span>  
  
-   <span data-ttu-id="3d749-111">Alle Strukturen, auch wenn deren Member Verweistypen sind.</span><span class="sxs-lookup"><span data-stu-id="3d749-111">All structures, even if their members are reference types</span></span>  
  
-   <span data-ttu-id="3d749-112">Enumerationen, da der zugrunde liegenden Typ immer ist `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, oder `ULong`</span><span class="sxs-lookup"><span data-stu-id="3d749-112">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="3d749-113">Jede Struktur ist ein Werttyp, auch wenn es sich um referenztypmember enthält.</span><span class="sxs-lookup"><span data-stu-id="3d749-113">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="3d749-114">Aus diesem Grund Werttypen wie z. B. `Char` und `Integer` von .NET Framework-Strukturen implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="3d749-114">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="3d749-115">Sie können einen Werttyp deklarieren, indem Sie mit dem reservierten Schlüsselwort, z. B. `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="3d749-115">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="3d749-116">Sie können auch die `New` Schlüsselwort, um einen Werttyp zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="3d749-116">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="3d749-117">Dies ist besonders nützlich, wenn der Typ einen Konstruktor verfügt, der Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="3d749-117">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="3d749-118">Ein Beispiel hierfür ist die <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> Konstruktor, der eine neue erstellt `Decimal` Wert aus den angegebenen teilen.</span><span class="sxs-lookup"><span data-stu-id="3d749-118">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="3d749-119">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="3d749-119">Reference Types</span></span>  
 <span data-ttu-id="3d749-120">Ein *Verweistyp* enthält einen Zeiger auf einen anderen Speicherort, das Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="3d749-120">A *reference type* contains a pointer to another memory location that holds the data.</span></span> <span data-ttu-id="3d749-121">Verweistypen umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3d749-121">Reference types include the following:</span></span>  
  
-   `String`  
  
-   <span data-ttu-id="3d749-122">Alle Arrays, auch wenn ihre Elemente Werttypen sind.</span><span class="sxs-lookup"><span data-stu-id="3d749-122">All arrays, even if their elements are value types</span></span>  
  
-   <span data-ttu-id="3d749-123">Klassentypen Sie, z. B. <xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="3d749-123">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
-   <span data-ttu-id="3d749-124">Delegaten</span><span class="sxs-lookup"><span data-stu-id="3d749-124">Delegates</span></span>  
  
 <span data-ttu-id="3d749-125">Eine Klasse ist eine *Verweistyp*.</span><span class="sxs-lookup"><span data-stu-id="3d749-125">A class is a *reference type*.</span></span> <span data-ttu-id="3d749-126">Aus diesem Grund verweisen auf Typen wie z. B. `Object` und `String` werden von unterstützt [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Klassen.</span><span class="sxs-lookup"><span data-stu-id="3d749-126">For this reason, reference types such as `Object` and `String` are supported by [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes.</span></span> <span data-ttu-id="3d749-127">Beachten Sie, dass jedes Array ein Verweistyp ist, auch wenn seine Member Werttypen sind.</span><span class="sxs-lookup"><span data-stu-id="3d749-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="3d749-128">Da jede Verweistyp eine zugrunde liegende .NET Framework-Klasse darstellt, müssen Sie verwenden die [neuer Operator](../../../../visual-basic/language-reference/operators/new-operator.md) Schlüsselwort, die Sie bei der Initialisierung.</span><span class="sxs-lookup"><span data-stu-id="3d749-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="3d749-129">Die folgende Anweisung initialisiert ein Array.</span><span class="sxs-lookup"><span data-stu-id="3d749-129">The following statement initializes an array.</span></span>  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="3d749-130">Elemente, die keine Typen sind</span><span class="sxs-lookup"><span data-stu-id="3d749-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="3d749-131">Die folgenden Programmierelemente qualifiziere nicht als Typen, da Sie diese als Datentyp für eine deklarierte Element angeben können:</span><span class="sxs-lookup"><span data-stu-id="3d749-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
-   <span data-ttu-id="3d749-132">Namespaces</span><span class="sxs-lookup"><span data-stu-id="3d749-132">Namespaces</span></span>  
  
-   <span data-ttu-id="3d749-133">Module</span><span class="sxs-lookup"><span data-stu-id="3d749-133">Modules</span></span>  
  
-   <span data-ttu-id="3d749-134">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="3d749-134">Events</span></span>  
  
-   <span data-ttu-id="3d749-135">Eigenschaften und Prozeduren</span><span class="sxs-lookup"><span data-stu-id="3d749-135">Properties and procedures</span></span>  
  
-   <span data-ttu-id="3d749-136">Variablen, Konstanten und Felder</span><span class="sxs-lookup"><span data-stu-id="3d749-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="3d749-137">Arbeiten mit den Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="3d749-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="3d749-138">Sie können entweder ein Verweistyp oder ein Werttyp zuweisen, um eine Variable vom die `Object` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="3d749-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="3d749-139">Ein `Object` -Variable enthält immer einen Zeiger auf die Daten nie die Daten selbst.</span><span class="sxs-lookup"><span data-stu-id="3d749-139">An `Object` variable always holds a pointer to the data, never the data itself.</span></span> <span data-ttu-id="3d749-140">Jedoch wenn Sie einen Werttyp zum Zuweisen einer `Object` Variablen, verhält es sich, als ob es sich um seine eigenen Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="3d749-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="3d749-141">Weitere Informationen finden Sie unter [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="3d749-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="3d749-142">Finden Sie heraus, ob ein `Object` Variablen fungiert als ein Verweistyp oder ein Werttyp durch Übergabe an die <xref:Microsoft.VisualBasic.Information.IsReference%2A> -Methode in der die <xref:Microsoft.VisualBasic.Information> Klasse von der <xref:Microsoft.VisualBasic?displayProperty=nameWithType> Namespace.</span><span class="sxs-lookup"><span data-stu-id="3d749-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="3d749-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> Gibt `True` Wenn den Inhalt der `Object` Variable stellt einen Verweistyp handelt.</span><span class="sxs-lookup"><span data-stu-id="3d749-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d749-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d749-144">See Also</span></span>  
 [<span data-ttu-id="3d749-145">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="3d749-145">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="3d749-146">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3d749-146">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="3d749-147">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3d749-147">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="3d749-148">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="3d749-148">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="3d749-149">Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="3d749-149">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="3d749-150">Datentypen</span><span class="sxs-lookup"><span data-stu-id="3d749-150">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
