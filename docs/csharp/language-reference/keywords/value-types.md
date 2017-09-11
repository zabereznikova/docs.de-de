---
title: Werttypen (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.valuetypes
dev_langs:
- CSharp
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7500426846562dd7f3bbb8ea99f300a3e8a26546
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="value-types-c-reference"></a><span data-ttu-id="52822-102">Werttypen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="52822-102">Value Types (C# Reference)</span></span>
<span data-ttu-id="52822-103">Die Werttypen sind in zwei Hauptkategorien unterteilt:</span><span class="sxs-lookup"><span data-stu-id="52822-103">The value types consist of two main categories:</span></span>  
  
-   [<span data-ttu-id="52822-104">Strukturen</span><span class="sxs-lookup"><span data-stu-id="52822-104">Structs</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
-   [<span data-ttu-id="52822-105">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="52822-105">Enumerations</span></span>](../../../csharp/language-reference/keywords/enum.md)  
  
 <span data-ttu-id="52822-106">Strukturen werden in diese Kategorien eingeteilt:</span><span class="sxs-lookup"><span data-stu-id="52822-106">Structs fall into these categories:</span></span>  
  
-   <span data-ttu-id="52822-107">Numerische Typen</span><span class="sxs-lookup"><span data-stu-id="52822-107">Numeric types</span></span>  
  
    -   [<span data-ttu-id="52822-108">Integrale Typen</span><span class="sxs-lookup"><span data-stu-id="52822-108">Integral types</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
  
    -   [<span data-ttu-id="52822-109">Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="52822-109">Floating-point types</span></span>](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
  
    -   [<span data-ttu-id="52822-110">decimal</span><span class="sxs-lookup"><span data-stu-id="52822-110">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)  
  
-   [<span data-ttu-id="52822-111">bool</span><span class="sxs-lookup"><span data-stu-id="52822-111">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)  
  
-   <span data-ttu-id="52822-112">Benutzerdefinierte Strukturen</span><span class="sxs-lookup"><span data-stu-id="52822-112">User defined structs.</span></span>  
  
## <a name="main-features-of-value-types"></a><span data-ttu-id="52822-113">Hauptfunktionen von Werttypen</span><span class="sxs-lookup"><span data-stu-id="52822-113">Main Features of Value Types</span></span>  
 <span data-ttu-id="52822-114">Variablen, die auf Werttypen basieren, enthalten Werte direkt.</span><span class="sxs-lookup"><span data-stu-id="52822-114">Variables that are based on value types directly contain values.</span></span> <span data-ttu-id="52822-115">Durch das Zuweisen einer Werttypvariablen zu einer anderen wird der enthaltene Wert kopiert.</span><span class="sxs-lookup"><span data-stu-id="52822-115">Assigning one value type variable to another copies the contained value.</span></span> <span data-ttu-id="52822-116">Dies unterscheidet sich von der Zuweisung von Verweistypvariablen. Dabei wird ein Verweis auf das Objekt, aber nicht das Objekt selbst kopiert.</span><span class="sxs-lookup"><span data-stu-id="52822-116">This differs from the assignment of reference type variables, which copies a reference to the object but not the object itself.</span></span>  
  
 <span data-ttu-id="52822-117">Alle Werttypen werden implizit von <xref:System.ValueType?displayProperty=fullName> abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="52822-117">All value types are derived implicitly from the <xref:System.ValueType?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="52822-118">Im Gegensatz zu Verweistypen können Sie von Werttypen keinen neuen ableiten.</span><span class="sxs-lookup"><span data-stu-id="52822-118">Unlike with reference types, you cannot derive a new type from a value type.</span></span> <span data-ttu-id="52822-119">Strukturen können aber wie Verweistypen Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="52822-119">However, like reference types, structs can implement interfaces.</span></span>  
  
 <span data-ttu-id="52822-120">Im Gegensatz zu Verweistypen können Werttypen nicht den Wert `null` enthalten.</span><span class="sxs-lookup"><span data-stu-id="52822-120">Unlike reference types, a value type cannot contain the `null` value.</span></span> <span data-ttu-id="52822-121">Allerdings ermöglicht es die Funktion [Nullable-Typ](../../../csharp/programming-guide/nullable-types/index.md), dass Werttypen `null` zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="52822-121">However, the [nullable types](../../../csharp/programming-guide/nullable-types/index.md) feature does allow for value types to be assigned to `null`.</span></span>  
  
 <span data-ttu-id="52822-122">Jeder Werttyp hat einen impliziten Standardkonstruktor, der den Standardwert dieses Typs initialisiert.</span><span class="sxs-lookup"><span data-stu-id="52822-122">Each value type has an implicit default constructor that initializes the default value of that type.</span></span> <span data-ttu-id="52822-123">Informationen zu den Standardwerten von Werttypen finden Sie unter [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="52822-123">For information about default values of value types, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
## <a name="main-features-of-simple-types"></a><span data-ttu-id="52822-124">Hauptfunktionen von einfachen Typen</span><span class="sxs-lookup"><span data-stu-id="52822-124">Main Features of Simple Types</span></span>  
 <span data-ttu-id="52822-125">Alle einfachen Typen, die für C# wesentlichen Typen, sind Aliasse der Systemtypen aus dem .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="52822-125">All of the simple types -- those integral to the C# language -- are aliases of the .NET Framework System types.</span></span> <span data-ttu-id="52822-126">[int](../../../csharp/language-reference/keywords/int.md) ist z.B. ein Alias von <xref:System.Int32?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="52822-126">For example, [int](../../../csharp/language-reference/keywords/int.md) is an alias of <xref:System.Int32?displayProperty=fullName>.</span></span> <span data-ttu-id="52822-127">Eine vollständige Liste der Aliase finden Sie unter [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="52822-127">For a complete list of aliases, see [Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md).</span></span>  
  
 <span data-ttu-id="52822-128">Konstante Ausdrücke, deren Operanden alle einfache Typkonstanten sind, werden zur Kompilierzeit ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="52822-128">Constant expressions, whose operands are all simple type constants, are evaluated at compilation time.</span></span>  
  
 <span data-ttu-id="52822-129">Einfache Typen können mithilfe von Literalen initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="52822-129">Simple types can be initialized by using literals.</span></span> <span data-ttu-id="52822-130">„A“ ist beispielsweise ein Literal vom Typ `char`, und 2001 ist ein Literal vom Typ `int`.</span><span class="sxs-lookup"><span data-stu-id="52822-130">For example, 'A' is a literal of the type `char` and 2001 is a literal of the type `int`.</span></span>  
  
## <a name="initializing-value-types"></a><span data-ttu-id="52822-131">Initialisieren von Werttypen</span><span class="sxs-lookup"><span data-stu-id="52822-131">Initializing Value Types</span></span>  
 <span data-ttu-id="52822-132">Lokale Variablen in C# müssen vor ihrer Verwendung initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="52822-132">Local variables in C# must be initialized before they are used.</span></span> <span data-ttu-id="52822-133">Sie könnten eine lokale Variable beispielsweise ohne Initialisierung wie im folgenden Beispiel deklarieren:</span><span class="sxs-lookup"><span data-stu-id="52822-133">For example, you might declare a local variable without initialization as in the following example:</span></span>  
  
```  
int myInt;  
```  
  
 <span data-ttu-id="52822-134">Sie können sie nicht verwenden, bis Sie sie initialisiert haben.</span><span class="sxs-lookup"><span data-stu-id="52822-134">You cannot use it before you initialize it.</span></span> <span data-ttu-id="52822-135">Sie können sie mit der folgenden Anweisung initialisieren:</span><span class="sxs-lookup"><span data-stu-id="52822-135">You can initialize it using the following statement:</span></span>  
  
```  
myInt = new int();  // Invoke default constructor for int type.  
```  
  
 <span data-ttu-id="52822-136">Diese Anweisung entspricht der folgenden Anweisung:</span><span class="sxs-lookup"><span data-stu-id="52822-136">This statement is equivalent to the following statement:</span></span>  
  
```  
myInt = 0;         // Assign an initial value, 0 in this example.  
```  
  
 <span data-ttu-id="52822-137">Natürlich können Sie sich die Deklaration und die Initialisierung in derselben Anweisung befinden, wie in den folgenden Beispielen dargestellt:</span><span class="sxs-lookup"><span data-stu-id="52822-137">You can, of course, have the declaration and the initialization in the same statement as in the following examples:</span></span>  
  
```  
int myInt = new int();  
```  
  
 <span data-ttu-id="52822-138">– oder –</span><span class="sxs-lookup"><span data-stu-id="52822-138">–or–</span></span>  
  
```  
int myInt = 0;  
```  
  
 <span data-ttu-id="52822-139">Durch die Verwendung des Operators [new](../../../csharp/language-reference/keywords/new.md) wird der Standardkonstruktor des angegebenen Typs aufgerufen und der Variablen der Standardwert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="52822-139">Using the [new](../../../csharp/language-reference/keywords/new.md) operator calls the default constructor of the specific type and assigns the default value to the variable.</span></span> <span data-ttu-id="52822-140">Im vorherigen Beispiel hat der Standardkonstruktor `myInt` den Wert `0` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="52822-140">In the preceding example, the default constructor assigned the value `0` to `myInt`.</span></span> <span data-ttu-id="52822-141">Weitere Informationen zu Werten, die durch Aufrufen von Standardkonstruktoren zugewiesen werden, finden Sie unter [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="52822-141">For more information about values assigned by calling default constructors, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
 <span data-ttu-id="52822-142">Verwenden Sie bei benutzerdefinierten Typen [new](../../../csharp/language-reference/keywords/new.md) zum Aufrufen des Standardkonstruktors.</span><span class="sxs-lookup"><span data-stu-id="52822-142">With user-defined types, use [new](../../../csharp/language-reference/keywords/new.md) to invoke the default constructor.</span></span> <span data-ttu-id="52822-143">Die folgende Anweisung ruft z.B. den Standardkonstruktor der `Point`-Struktur auf:</span><span class="sxs-lookup"><span data-stu-id="52822-143">For example, the following statement invokes the default constructor of the `Point` struct:</span></span>  
  
```  
Point p = new Point(); // Invoke default constructor for the struct.  
```  
  
 <span data-ttu-id="52822-144">Nach diesem Aufruf gilt die Struktur als definitiv zugewiesen. Das bedeutet, dass alle ihre Member mit ihren Standardwerten initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="52822-144">After this call, the struct is considered to be definitely assigned; that is, all its members are initialized to their default values.</span></span>  
  
 <span data-ttu-id="52822-145">Weitere Informationen zum Operator „new“ finden Sie unter [new](../../../csharp/language-reference/keywords/new.md).</span><span class="sxs-lookup"><span data-stu-id="52822-145">For more information about the new operator, see [new](../../../csharp/language-reference/keywords/new.md).</span></span>  
  
 <span data-ttu-id="52822-146">Informationen zum Formatieren der Ausgabe von numerischen Typen finden Sie unter [Tabelle zur Formatierung numerischer Ergebnisse](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).</span><span class="sxs-lookup"><span data-stu-id="52822-146">For information about formatting the output of numeric types, see [Formatting Numeric Results Table](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52822-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52822-147">See Also</span></span>  
 <span data-ttu-id="52822-148">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="52822-148">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="52822-149">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="52822-149">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="52822-150">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="52822-150">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="52822-151">[Typen](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="52822-151">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="52822-152">[Referenztabellen für Typen](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span><span class="sxs-lookup"><span data-stu-id="52822-152">[Reference Tables for Types](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span></span>  
 [<span data-ttu-id="52822-153">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="52822-153">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)

