---
title: Werttypen und Verweistypen | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- reference data types
- reference types
- value types
- value data types
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8136f58b2e7fce15e959e04b84b05f64d078d662
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="a6d23-102">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="a6d23-102">Value Types and Reference Types</span></span>
<span data-ttu-id="a6d23-103">In Visual Basic werden die Datentypen entsprechend ihrer Klassifizierung implementiert.</span><span class="sxs-lookup"><span data-stu-id="a6d23-103">In Visual Basic, data types are implemented based on their classification.</span></span> <span data-ttu-id="a6d23-104">Die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Datentypen können, ob eine Variable eines bestimmten Typs eigene Daten oder ein Zeiger auf die Daten speichert klassifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="a6d23-104">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types can be classified according to whether a variable of a particular type stores its own data or a pointer to the data.</span></span> <span data-ttu-id="a6d23-105">Wenn seine eigenen Daten speichert, es ist ein *Werttyp*, wenn er einen Zeiger auf Daten an anderer Stelle im Speicher enthält, ist ein *Referenztyp*.</span><span class="sxs-lookup"><span data-stu-id="a6d23-105">If it stores its own data it is a *value type*; if it holds a pointer to data elsewhere in memory it is a *reference type*.</span></span>  
  
## <a name="value-types"></a><span data-ttu-id="a6d23-106">Werttypen</span><span class="sxs-lookup"><span data-stu-id="a6d23-106">Value Types</span></span>  
 <span data-ttu-id="a6d23-107">Ein Datentyp ist ein *Werttyp* , wenn sie die Daten in eine eigene speicherbelegung enthält.</span><span class="sxs-lookup"><span data-stu-id="a6d23-107">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="a6d23-108">Die folgenden: Werttypen</span><span class="sxs-lookup"><span data-stu-id="a6d23-108">Value types include the following:</span></span>  
  
-   <span data-ttu-id="a6d23-109">Alle numerischen Datentypen</span><span class="sxs-lookup"><span data-stu-id="a6d23-109">All numeric data types</span></span>  
  
-   <span data-ttu-id="a6d23-110">`Boolean`, `Char` und `Date`</span><span class="sxs-lookup"><span data-stu-id="a6d23-110">`Boolean`, `Char`, and `Date`</span></span>  
  
-   <span data-ttu-id="a6d23-111">Alle Strukturen, auch wenn ihre Member Verweistypen sind.</span><span class="sxs-lookup"><span data-stu-id="a6d23-111">All structures, even if their members are reference types</span></span>  
  
-   <span data-ttu-id="a6d23-112">Enumerationen, da der zugrunde liegende Typ immer ist `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, oder`ULong`</span><span class="sxs-lookup"><span data-stu-id="a6d23-112">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="a6d23-113">Jede Struktur ist ein Werttyp, auch wenn sie Verweistypmember enthält.</span><span class="sxs-lookup"><span data-stu-id="a6d23-113">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="a6d23-114">Aus diesem Grund Werttypen wie `Char` und `Integer` vom .NET Framework-Strukturen implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="a6d23-114">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="a6d23-115">Sie können einen Werttyp deklarieren, indem Sie mit dem reservierten Schlüsselwort, z. B. `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="a6d23-115">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="a6d23-116">Sie können auch die `New` -Schlüsselwort verwenden, um einen Werttyp zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="a6d23-116">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="a6d23-117">Dies ist besonders nützlich, wenn der Typ einen Konstruktor verfügt, der Parameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="a6d23-117">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="a6d23-118">Ein Beispiel hierfür ist die <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>-Konstruktor, der ein neues erstellt `Decimal` Wert aus den bereitgestellten Teilen.</xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29></span><span class="sxs-lookup"><span data-stu-id="a6d23-118">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="a6d23-119">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="a6d23-119">Reference Types</span></span>  
 <span data-ttu-id="a6d23-120">Ein *Referenztyp* enthält einen Zeiger auf einen anderen Speicherort, der die Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="a6d23-120">A *reference type* contains a pointer to another memory location that holds the data.</span></span> <span data-ttu-id="a6d23-121">Verweistypen umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a6d23-121">Reference types include the following:</span></span>  
  
-   `String`  
  
-   <span data-ttu-id="a6d23-122">Alle Arrays, auch wenn ihre Elemente Werttypen sind.</span><span class="sxs-lookup"><span data-stu-id="a6d23-122">All arrays, even if their elements are value types</span></span>  
  
-   <span data-ttu-id="a6d23-123">Klassentypen Sie, z. B.<xref:System.Windows.Forms.Form></xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="a6d23-123">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
-   <span data-ttu-id="a6d23-124">Delegaten</span><span class="sxs-lookup"><span data-stu-id="a6d23-124">Delegates</span></span>  
  
 <span data-ttu-id="a6d23-125">Eine Klasse ist ein *Referenztyp*.</span><span class="sxs-lookup"><span data-stu-id="a6d23-125">A class is a *reference type*.</span></span> <span data-ttu-id="a6d23-126">Aus diesem Grund Verweistypen wie `Object` und `String` wird von [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] Klassen.</span><span class="sxs-lookup"><span data-stu-id="a6d23-126">For this reason, reference types such as `Object` and `String` are supported by [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] classes.</span></span> <span data-ttu-id="a6d23-127">Beachten Sie, dass jedes Array einen Verweistyp handelt, auch wenn seine Member Werttypen sind.</span><span class="sxs-lookup"><span data-stu-id="a6d23-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="a6d23-128">Da jeder Referenztyp eine zugrunde liegende .NET Framework-Klasse darstellt, müssen Sie verwenden die [Operator New](../../../../visual-basic/language-reference/operators/new-operator.md) Schlüsselwort, die Sie bei der Initialisierung.</span><span class="sxs-lookup"><span data-stu-id="a6d23-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="a6d23-129">Die folgende Anweisung initialisiert ein Array.</span><span class="sxs-lookup"><span data-stu-id="a6d23-129">The following statement initializes an array.</span></span>  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="a6d23-130">Elemente, die keine Typen sind</span><span class="sxs-lookup"><span data-stu-id="a6d23-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="a6d23-131">Die folgenden Programmierelemente qualifizieren wie Typen, Sie nicht, da Sie diese nicht als Datentyp für ein deklariertes Element angeben können:</span><span class="sxs-lookup"><span data-stu-id="a6d23-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
-   <span data-ttu-id="a6d23-132">Namespaces</span><span class="sxs-lookup"><span data-stu-id="a6d23-132">Namespaces</span></span>  
  
-   <span data-ttu-id="a6d23-133">Module</span><span class="sxs-lookup"><span data-stu-id="a6d23-133">Modules</span></span>  
  
-   <span data-ttu-id="a6d23-134">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="a6d23-134">Events</span></span>  
  
-   <span data-ttu-id="a6d23-135">Eigenschaften und Prozeduren</span><span class="sxs-lookup"><span data-stu-id="a6d23-135">Properties and procedures</span></span>  
  
-   <span data-ttu-id="a6d23-136">Variablen, Konstanten und Felder</span><span class="sxs-lookup"><span data-stu-id="a6d23-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="a6d23-137">Arbeiten mit den Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="a6d23-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="a6d23-138">Sie können ein Referenztyp oder ein Werttyp zu einer Variablen zuweisen der `Object` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="a6d23-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="a6d23-139">Ein `Object` -Variable enthält immer einen Zeiger auf die Daten, nie die Daten selbst.</span><span class="sxs-lookup"><span data-stu-id="a6d23-139">An `Object` variable always holds a pointer to the data, never the data itself.</span></span> <span data-ttu-id="a6d23-140">Jedoch wenn Sie einen Werttyp zum Zuweisen einer `Object` -Variable verhält sich als enthielte sie eigene Daten.</span><span class="sxs-lookup"><span data-stu-id="a6d23-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="a6d23-141">Weitere Informationen finden Sie unter [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="a6d23-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="a6d23-142">Können Sie ermitteln, ob ein `Object` Variablen fungiert als ein Referenztyp oder ein Werttyp durch Übergabe an die <xref:Microsoft.VisualBasic.Information.IsReference%2A>-Methode in der <xref:Microsoft.VisualBasic.Information>Klasse von der <xref:Microsoft.VisualBasic?displayProperty=fullName>Namespace.</xref:Microsoft.VisualBasic?displayProperty=fullName> </xref:Microsoft.VisualBasic.Information> </xref:Microsoft.VisualBasic.Information.IsReference%2A></span><span class="sxs-lookup"><span data-stu-id="a6d23-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="a6d23-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=fullName>Gibt `True` Wenn der Inhalt der `Object` Variable einen Referenztyp darstellt.</xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a6d23-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=fullName> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6d23-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6d23-144">See Also</span></span>  
 <span data-ttu-id="a6d23-145">[Auf NULL festlegbare Werttypen](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) </span><span class="sxs-lookup"><span data-stu-id="a6d23-145">[Nullable Value Types](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) </span></span>  
<span data-ttu-id="a6d23-146"> [Typumwandlungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="a6d23-146"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="a6d23-147"> [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a6d23-147"> [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="a6d23-148"> [Effiziente Verwendung von Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="a6d23-148"> [Efficient Use of Data Types](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md) </span></span>  
<span data-ttu-id="a6d23-149"> [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="a6d23-149"> [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span></span>  
<span data-ttu-id="a6d23-150"> [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)</span><span class="sxs-lookup"><span data-stu-id="a6d23-150"> [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md)</span></span>
