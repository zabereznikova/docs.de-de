---
title: Objekt-Werte (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- object variables, values
- values, of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
caps.latest.revision: 18
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
ms.openlocfilehash: 5f42706a79212ae523b08ee336fdcacb3f761af6
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="object-variable-values-visual-basic"></a><span data-ttu-id="630f5-102">Werte von Objektvariablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="630f5-102">Object Variable Values (Visual Basic)</span></span>
<span data-ttu-id="630f5-103">Eine Variable, der die [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md) kann auf Daten eines beliebigen Typs verweisen.</span><span class="sxs-lookup"><span data-stu-id="630f5-103">A variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) can refer to data of any type.</span></span> <span data-ttu-id="630f5-104">Der Wert in einer `Object` Variable wird an anderer Stelle im Arbeitsspeicher beibehalten, während die Variable selbst ein Zeiger auf die Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="630f5-104">The value you store in an `Object` variable is kept elsewhere in memory, while the variable itself holds a pointer to the data.</span></span>  
  
## <a name="object-classifier-functions"></a><span data-ttu-id="630f5-105">Objekt-Klassifizierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="630f5-105">Object Classifier Functions</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="630f5-106">enthält Funktionen, Zurückgeben von Informationen darüber, was, eine `Object` Variable verweist auf, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="630f5-106"> supplies functions that return information about what an `Object` variable refers to, as shown in the following table.</span></span>  
  
|<span data-ttu-id="630f5-107">Funktion</span><span class="sxs-lookup"><span data-stu-id="630f5-107">Function</span></span>|<span data-ttu-id="630f5-108">Gibt True zurück, wenn auf die Objektvariable verweist</span><span class="sxs-lookup"><span data-stu-id="630f5-108">Returns True if the Object variable refers to</span></span>|  
|--------------|---------------------------------------------------|  
|<span data-ttu-id="630f5-109"><xref:Microsoft.VisualBasic.Information.IsArray%2A></xref:Microsoft.VisualBasic.Information.IsArray%2A></span><span class="sxs-lookup"><span data-stu-id="630f5-109"><xref:Microsoft.VisualBasic.Information.IsArray%2A></span></span>|<span data-ttu-id="630f5-110">Ein Array von Werten, keinen einzelnen Wert</span><span class="sxs-lookup"><span data-stu-id="630f5-110">An array of values, rather than a single value</span></span>|  
|<span data-ttu-id="630f5-111"><xref:Microsoft.VisualBasic.Information.IsDate%2A></xref:Microsoft.VisualBasic.Information.IsDate%2A></span><span class="sxs-lookup"><span data-stu-id="630f5-111"><xref:Microsoft.VisualBasic.Information.IsDate%2A></span></span>|<span data-ttu-id="630f5-112">Ein [Date-Datentyp](../../../../visual-basic/language-reference/data-types/date-data-type.md) Wert oder eine Zeichenfolge, die als Wert für Datum und Uhrzeit interpretiert werden kann</span><span class="sxs-lookup"><span data-stu-id="630f5-112">A [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) value, or a string that can be interpreted as a date and time value</span></span>|  
|<span data-ttu-id="630f5-113"><xref:Microsoft.VisualBasic.Information.IsDBNull%2A></xref:Microsoft.VisualBasic.Information.IsDBNull%2A></span><span class="sxs-lookup"><span data-stu-id="630f5-113"><xref:Microsoft.VisualBasic.Information.IsDBNull%2A></span></span>|<span data-ttu-id="630f5-114">Ein Objekt vom Typ <xref:System.DBNull>der fehlende oder nicht vorhandene Daten darstellt</xref:System.DBNull></span><span class="sxs-lookup"><span data-stu-id="630f5-114">An object of type <xref:System.DBNull>, which represents missing or nonexistent data</span></span>|  
|<span data-ttu-id="630f5-115"><xref:Microsoft.VisualBasic.Information.IsError%2A></xref:Microsoft.VisualBasic.Information.IsError%2A></span><span class="sxs-lookup"><span data-stu-id="630f5-115"><xref:Microsoft.VisualBasic.Information.IsError%2A></span></span>|<span data-ttu-id="630f5-116">Ein Exception-Objekt, die von abgeleitet wird<xref:System.Exception></xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="630f5-116">An exception object, which derives from <xref:System.Exception></span></span>|  
|<span data-ttu-id="630f5-117"><xref:Microsoft.VisualBasic.Information.IsNothing%2A></xref:Microsoft.VisualBasic.Information.IsNothing%2A></span><span class="sxs-lookup"><span data-stu-id="630f5-117"><xref:Microsoft.VisualBasic.Information.IsNothing%2A></span></span>|<span data-ttu-id="630f5-118">[Nichts](../../../../visual-basic/language-reference/nothing.md), dass der Variablen gegenwärtig kein Objekt zugewiesen ist</span><span class="sxs-lookup"><span data-stu-id="630f5-118">[Nothing](../../../../visual-basic/language-reference/nothing.md), that is, no object is currently assigned to the variable</span></span>|  
|<span data-ttu-id="630f5-119"><xref:Microsoft.VisualBasic.Information.IsNumeric%2A></xref:Microsoft.VisualBasic.Information.IsNumeric%2A></span><span class="sxs-lookup"><span data-stu-id="630f5-119"><xref:Microsoft.VisualBasic.Information.IsNumeric%2A></span></span>|<span data-ttu-id="630f5-120">Eine Zahl oder eine Zeichenfolge, die als Zahl interpretiert werden kann</span><span class="sxs-lookup"><span data-stu-id="630f5-120">A number, or a string that can be interpreted as a number</span></span>|  
|<span data-ttu-id="630f5-121"><xref:Microsoft.VisualBasic.Information.IsReference%2A></xref:Microsoft.VisualBasic.Information.IsReference%2A></span><span class="sxs-lookup"><span data-stu-id="630f5-121"><xref:Microsoft.VisualBasic.Information.IsReference%2A></span></span>|<span data-ttu-id="630f5-122">Ein Verweistyp (z. B. eine Zeichenfolge, ein Array, Delegat oder ein Klassentyp)</span><span class="sxs-lookup"><span data-stu-id="630f5-122">A reference type (such as a string, array, delegate, or class type)</span></span>|  
  
 <span data-ttu-id="630f5-123">Diese Funktionen können Sie vermeiden, senden einen ungültigen Wert für einen Vorgang oder eine Prozedur.</span><span class="sxs-lookup"><span data-stu-id="630f5-123">You can use these functions to avoid submitting an invalid value to an operation or a procedure.</span></span>  
  
## <a name="typeof-operator"></a><span data-ttu-id="630f5-124">Operator TypeOf</span><span class="sxs-lookup"><span data-stu-id="630f5-124">TypeOf Operator</span></span>  
 <span data-ttu-id="630f5-125">Sie können auch die [TypeOf-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) zu bestimmen, ob eine Objektvariable gegenwärtig auf einen bestimmten Datentyp verweist.</span><span class="sxs-lookup"><span data-stu-id="630f5-125">You can also use the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to determine whether an object variable currently refers to a specific data type.</span></span> <span data-ttu-id="630f5-126">The `TypeOf`... `Is` Ausdruck ergibt `True` , wenn der Laufzeittyp des Operanden abgeleitet ist oder den angegebenen Typ implementiert.</span><span class="sxs-lookup"><span data-stu-id="630f5-126">The `TypeOf`...`Is` expression evaluates to `True` if the run-time type of the operand is derived from or implements the specified type.</span></span>  
  
 <span data-ttu-id="630f5-127">Im folgenden Beispiel wird `TypeOf` auf Objektvariablen, die auf Wert-und Verweistypen verweisen.</span><span class="sxs-lookup"><span data-stu-id="630f5-127">The following example uses `TypeOf` on object variables referring to value and reference types.</span></span>  
  
```  
' The following statement puts a value type (Integer) in an Object variable.  
Dim num As Object = 10  
' The following statement puts a reference type (Form) in an Object variable.  
Dim frm As Object = New Form()  
If TypeOf num Is Long Then Debug.WriteLine("num is Long")  
If TypeOf num Is Integer Then Debug.WriteLine("num is Integer")  
If TypeOf num Is Short Then Debug.WriteLine("num is Short")  
If TypeOf num Is Object Then Debug.WriteLine("num is Object")  
If TypeOf frm Is Form Then Debug.WriteLine("frm is Form")  
If TypeOf frm Is Label Then Debug.WriteLine("frm is Label")  
If TypeOf frm Is Object Then Debug.WriteLine("frm is Object")  
```  
  
 <span data-ttu-id="630f5-128">Das vorhergehende Beispiel schreibt die folgenden Zeilen der **Debuggen** Fenster:</span><span class="sxs-lookup"><span data-stu-id="630f5-128">The preceding example writes the following lines to the **Debug** window:</span></span>  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 <span data-ttu-id="630f5-129">Die Objektvariable `num` bezieht sich auf Daten des Typs `Integer`, und `frm` bezieht sich auf ein Objekt der Klasse <xref:System.Windows.Forms.Form>.</xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="630f5-129">The object variable `num` refers to data of type `Integer`, and `frm` refers to an object of class <xref:System.Windows.Forms.Form>.</span></span>  
  
## <a name="object-arrays"></a><span data-ttu-id="630f5-130">Objektarrays</span><span class="sxs-lookup"><span data-stu-id="630f5-130">Object Arrays</span></span>  
 <span data-ttu-id="630f5-131">Sie können deklarieren und verwenden Sie ein Array von `Object` Variablen.</span><span class="sxs-lookup"><span data-stu-id="630f5-131">You can declare and use an array of `Object` variables.</span></span> <span data-ttu-id="630f5-132">Dies ist hilfreich, wenn Sie eine Vielzahl von Datentypen und Objektklassen verarbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="630f5-132">This is useful when you need to handle a variety of data types and object classes.</span></span> <span data-ttu-id="630f5-133">Alle Elemente in einem Array müssen den gleichen Datentyp deklariert.</span><span class="sxs-lookup"><span data-stu-id="630f5-133">All the elements in an array must have the same declared data type.</span></span> <span data-ttu-id="630f5-134">Dieser Datentyp als deklarieren `Object` ermöglicht es Ihnen, Objekte zu speichern und Klasseninstanzen neben weiteren Datentypen im Array.</span><span class="sxs-lookup"><span data-stu-id="630f5-134">Declaring this data type as `Object` allows you to store objects and class instances alongside other data types in the array.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="630f5-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="630f5-135">See Also</span></span>  
 <span data-ttu-id="630f5-136">[Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span><span class="sxs-lookup"><span data-stu-id="630f5-136">[Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span></span>  
<span data-ttu-id="630f5-137"> [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="630f5-137"> [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span></span>  
<span data-ttu-id="630f5-138"> [Zuweisen von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md) </span><span class="sxs-lookup"><span data-stu-id="630f5-138"> [Object Variable Assignment](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md) </span></span>  
<span data-ttu-id="630f5-139"> [Gewusst wie: Verweisen auf die aktuelle Instanz eines Objekts](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md) </span><span class="sxs-lookup"><span data-stu-id="630f5-139"> [How to: Refer to the Current Instance of an Object](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md) </span></span>  
<span data-ttu-id="630f5-140"> [Gewusst wie: Bestimmen des Typs, auf den eine Objektvariable verweist](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md) </span><span class="sxs-lookup"><span data-stu-id="630f5-140"> [How to: Determine What Type an Object Variable Refers To](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md) </span></span>  
<span data-ttu-id="630f5-141"> [Gewusst wie: Bestimmen des Bezugs zwischen zwei Objekten](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md) </span><span class="sxs-lookup"><span data-stu-id="630f5-141"> [How to: Determine Whether Two Objects Are Related](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md) </span></span>  
<span data-ttu-id="630f5-142"> [Gewusst wie: bestimmen, ob zwei Objekte identisch sind](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md) </span><span class="sxs-lookup"><span data-stu-id="630f5-142"> [How to: Determine Whether Two Objects Are Identical](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md) </span></span>  
<span data-ttu-id="630f5-143"> [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)</span><span class="sxs-lookup"><span data-stu-id="630f5-143"> [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md)</span></span>
