---
title: Werte von Objektvariablen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], values
- values [Visual Basic], of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
ms.openlocfilehash: c17c5f85952596f0a080ca473e8f792740e66b8f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840392"
---
# <a name="object-variable-values-visual-basic"></a><span data-ttu-id="ff729-102">Werte von Objektvariablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff729-102">Object Variable Values (Visual Basic)</span></span>
<span data-ttu-id="ff729-103">Eine Variable die [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) kann auf Daten eines beliebigen Typs verweisen.</span><span class="sxs-lookup"><span data-stu-id="ff729-103">A variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) can refer to data of any type.</span></span> <span data-ttu-id="ff729-104">Der Wert, die Sie in Speichern einer `Object` Variable wird an anderer Stelle im Arbeitsspeicher gespeichert, während die Variable selbst einen Zeiger auf die Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="ff729-104">The value you store in an `Object` variable is kept elsewhere in memory, while the variable itself holds a pointer to the data.</span></span>  
  
## <a name="object-classifier-functions"></a><span data-ttu-id="ff729-105">Objekt Klassifizierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="ff729-105">Object Classifier Functions</span></span>  
 <span data-ttu-id="ff729-106">Visual Basic bietet Funktionen, Zurückgeben von Informationen darüber, was, eine `Object` Variable verweist auf, wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff729-106">Visual Basic supplies functions that return information about what an `Object` variable refers to, as shown in the following table.</span></span>  
  
|<span data-ttu-id="ff729-107">Funktion</span><span class="sxs-lookup"><span data-stu-id="ff729-107">Function</span></span>|<span data-ttu-id="ff729-108">Gibt True zurück, wenn auf die Objektvariable verweist</span><span class="sxs-lookup"><span data-stu-id="ff729-108">Returns True if the Object variable refers to</span></span>|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|<span data-ttu-id="ff729-109">Ein Array von Werten, anstatt einen einzelnen Wert</span><span class="sxs-lookup"><span data-stu-id="ff729-109">An array of values, rather than a single value</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|<span data-ttu-id="ff729-110">Ein [Date-Datentyps](../../../../visual-basic/language-reference/data-types/date-data-type.md) Wert oder eine Zeichenfolge, die als einen Wert für Datum und Uhrzeit interpretiert werden kann</span><span class="sxs-lookup"><span data-stu-id="ff729-110">A [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) value, or a string that can be interpreted as a date and time value</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|<span data-ttu-id="ff729-111">Ein Objekt des Typs <xref:System.DBNull>, steht für fehlende oder nicht vorhandene Daten</span><span class="sxs-lookup"><span data-stu-id="ff729-111">An object of type <xref:System.DBNull>, which represents missing or nonexistent data</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|<span data-ttu-id="ff729-112">Ein Exception-Objekt, das von abgeleitet ist <xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="ff729-112">An exception object, which derives from <xref:System.Exception></span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|<span data-ttu-id="ff729-113">["Nothing"](../../../../visual-basic/language-reference/nothing.md), d. h. kein Objekt auf die Variable derzeit zugewiesen ist</span><span class="sxs-lookup"><span data-stu-id="ff729-113">[Nothing](../../../../visual-basic/language-reference/nothing.md), that is, no object is currently assigned to the variable</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|<span data-ttu-id="ff729-114">Eine Zahl oder eine Zeichenfolge, die als Zahl interpretiert werden kann</span><span class="sxs-lookup"><span data-stu-id="ff729-114">A number, or a string that can be interpreted as a number</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|<span data-ttu-id="ff729-115">Ein Verweistyp (z. B. eine Zeichenfolge, ein Array, Delegat oder ein Klassentyp)</span><span class="sxs-lookup"><span data-stu-id="ff729-115">A reference type (such as a string, array, delegate, or class type)</span></span>|  
  
 <span data-ttu-id="ff729-116">Sie können diese Funktionen verwenden, um zu vermeiden, senden einen ungültigen Wert zu einer Operation oder einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="ff729-116">You can use these functions to avoid submitting an invalid value to an operation or a procedure.</span></span>  
  
## <a name="typeof-operator"></a><span data-ttu-id="ff729-117">Operator TypeOf</span><span class="sxs-lookup"><span data-stu-id="ff729-117">TypeOf Operator</span></span>  
 <span data-ttu-id="ff729-118">Sie können auch die [TypeOf-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) zu bestimmen, ob eine Objektvariable derzeit in einem bestimmten Datentyp verweist.</span><span class="sxs-lookup"><span data-stu-id="ff729-118">You can also use the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to determine whether an object variable currently refers to a specific data type.</span></span> <span data-ttu-id="ff729-119">Die `TypeOf`... `Is` Ausdruck wird zu `True` , wenn die Run-Time-Typ des Operanden abgeleitet ist, oder den angegebenen Typ implementiert.</span><span class="sxs-lookup"><span data-stu-id="ff729-119">The `TypeOf`...`Is` expression evaluates to `True` if the run-time type of the operand is derived from or implements the specified type.</span></span>  
  
 <span data-ttu-id="ff729-120">Im folgenden Beispiel wird `TypeOf` in Objektvariablen, die auf der Wert-und Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="ff729-120">The following example uses `TypeOf` on object variables referring to value and reference types.</span></span>  
  
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
  
 <span data-ttu-id="ff729-121">Im obige Beispiel schreibt die folgenden Zeilen, die **Debuggen** Fenster:</span><span class="sxs-lookup"><span data-stu-id="ff729-121">The preceding example writes the following lines to the **Debug** window:</span></span>  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 <span data-ttu-id="ff729-122">Die Objektvariable `num` bezieht sich auf die Daten des Typs `Integer`, und `frm` bezieht sich auf ein Objekt der Klasse <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="ff729-122">The object variable `num` refers to data of type `Integer`, and `frm` refers to an object of class <xref:System.Windows.Forms.Form>.</span></span>  
  
## <a name="object-arrays"></a><span data-ttu-id="ff729-123">Objektarrays</span><span class="sxs-lookup"><span data-stu-id="ff729-123">Object Arrays</span></span>  
 <span data-ttu-id="ff729-124">Sie können deklarieren und verwenden Sie ein Array von `Object` Variablen.</span><span class="sxs-lookup"><span data-stu-id="ff729-124">You can declare and use an array of `Object` variables.</span></span> <span data-ttu-id="ff729-125">Dies ist nützlich, wenn Sie eine Vielzahl von Datentypen und Objektklassen verarbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="ff729-125">This is useful when you need to handle a variety of data types and object classes.</span></span> <span data-ttu-id="ff729-126">Alle Elemente in einem Array müssen den gleichen Datentyp deklariert.</span><span class="sxs-lookup"><span data-stu-id="ff729-126">All the elements in an array must have the same declared data type.</span></span> <span data-ttu-id="ff729-127">Dieser Datentyp als deklarieren `Object` ermöglicht Ihnen das Speichern von Objekten und -Klasseninstanzen zusammen mit anderen Datentypen in das Array.</span><span class="sxs-lookup"><span data-stu-id="ff729-127">Declaring this data type as `Object` allows you to store objects and class instances alongside other data types in the array.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff729-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff729-128">See also</span></span>

- [<span data-ttu-id="ff729-129">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="ff729-129">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="ff729-130">Deklaration von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="ff729-130">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="ff729-131">Zuweisen von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="ff729-131">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="ff729-132">Vorgehensweise: Verweisen Sie auf die aktuelle Instanz eines Objekts</span><span class="sxs-lookup"><span data-stu-id="ff729-132">How to: Refer to the Current Instance of an Object</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="ff729-133">Vorgehensweise: Bestimmen des Typs, um eine Objektvariable verweist</span><span class="sxs-lookup"><span data-stu-id="ff729-133">How to: Determine What Type an Object Variable Refers To</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)
- [<span data-ttu-id="ff729-134">Vorgehensweise: Bestimmen Sie, ob zwei Objekte verknüpft sind</span><span class="sxs-lookup"><span data-stu-id="ff729-134">How to: Determine Whether Two Objects Are Related</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="ff729-135">Vorgehensweise: Bestimmt, ob zwei Objekte identisch sind.</span><span class="sxs-lookup"><span data-stu-id="ff729-135">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
- [<span data-ttu-id="ff729-136">Datentypen</span><span class="sxs-lookup"><span data-stu-id="ff729-136">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
