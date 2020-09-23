---
title: Werte von Objektvariablen
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], values
- values [Visual Basic], of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
ms.openlocfilehash: 800b9754ce27cc6a494dd781d06f4bdca8a10e87
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91080230"
---
# <a name="object-variable-values-visual-basic"></a><span data-ttu-id="6fb2b-102">Werte von Objektvariablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fb2b-102">Object Variable Values (Visual Basic)</span></span>

<span data-ttu-id="6fb2b-103">Eine Variable des [Objekt Datentyps](../../../language-reference/data-types/object-data-type.md) kann auf Daten eines beliebigen Typs verweisen.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-103">A variable of the [Object Data Type](../../../language-reference/data-types/object-data-type.md) can refer to data of any type.</span></span> <span data-ttu-id="6fb2b-104">Der Wert, den Sie in einer `Object` Variablen speichern, wird an anderer Stelle im Arbeitsspeicher beibehalten, während die Variable selbst einen Zeiger auf die Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-104">The value you store in an `Object` variable is kept elsewhere in memory, while the variable itself holds a pointer to the data.</span></span>  
  
## <a name="object-classifier-functions"></a><span data-ttu-id="6fb2b-105">Objektklassifizierungs Funktionen</span><span class="sxs-lookup"><span data-stu-id="6fb2b-105">Object Classifier Functions</span></span>  

 <span data-ttu-id="6fb2b-106">Visual Basic stellt Funktionen bereit, die Informationen über das, `Object` auf die eine Variable verweist, zurückgeben, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-106">Visual Basic supplies functions that return information about what an `Object` variable refers to, as shown in the following table.</span></span>  
  
|<span data-ttu-id="6fb2b-107">Funktion</span><span class="sxs-lookup"><span data-stu-id="6fb2b-107">Function</span></span>|<span data-ttu-id="6fb2b-108">Gibt true zurück, wenn die Objekt Variable auf verweist.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-108">Returns True if the Object variable refers to</span></span>|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|<span data-ttu-id="6fb2b-109">Ein Array von Werten anstelle eines einzelnen Werts</span><span class="sxs-lookup"><span data-stu-id="6fb2b-109">An array of values, rather than a single value</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|<span data-ttu-id="6fb2b-110">Ein [Date-Datentyp](../../../language-reference/data-types/date-data-type.md) Wert oder eine Zeichenfolge, die als Datums-und Uhrzeitwert interpretiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-110">A [Date Data Type](../../../language-reference/data-types/date-data-type.md) value, or a string that can be interpreted as a date and time value</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|<span data-ttu-id="6fb2b-111">Ein Objekt vom Typ <xref:System.DBNull> , das fehlende oder nicht vorhandene Daten darstellt.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-111">An object of type <xref:System.DBNull>, which represents missing or nonexistent data</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|<span data-ttu-id="6fb2b-112">Ein Ausnahme Objekt, das von abgeleitet ist. <xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="6fb2b-112">An exception object, which derives from <xref:System.Exception></span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|<span data-ttu-id="6fb2b-113">[Nothing](../../../language-reference/nothing.md), das heißt, es ist zurzeit kein Objekt der Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-113">[Nothing](../../../language-reference/nothing.md), that is, no object is currently assigned to the variable</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|<span data-ttu-id="6fb2b-114">Eine Zahl oder eine Zeichenfolge, die als Zahl interpretiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-114">A number, or a string that can be interpreted as a number</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|<span data-ttu-id="6fb2b-115">Ein Verweistyp (z. b. eine Zeichenfolge, ein Array, ein Delegat oder ein Klassentyp)</span><span class="sxs-lookup"><span data-stu-id="6fb2b-115">A reference type (such as a string, array, delegate, or class type)</span></span>|  
  
 <span data-ttu-id="6fb2b-116">Sie können diese Funktionen verwenden, um zu vermeiden, dass ein ungültiger Wert an einen Vorgang oder eine Prozedur gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-116">You can use these functions to avoid submitting an invalid value to an operation or a procedure.</span></span>  
  
## <a name="typeof-operator"></a><span data-ttu-id="6fb2b-117">Operator TypeOf</span><span class="sxs-lookup"><span data-stu-id="6fb2b-117">TypeOf Operator</span></span>  

 <span data-ttu-id="6fb2b-118">Sie können auch den [typeof-Operator](../../../language-reference/operators/typeof-operator.md) verwenden, um zu bestimmen, ob eine Objekt Variable derzeit auf einen bestimmten Datentyp verweist.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-118">You can also use the [TypeOf Operator](../../../language-reference/operators/typeof-operator.md) to determine whether an object variable currently refers to a specific data type.</span></span> <span data-ttu-id="6fb2b-119">Der `TypeOf` Ausdruck... `Is` wird als ausgewertet, `True` Wenn der Lauf Zeittyp des Operanden von abgeleitet ist oder den angegebenen Typ implementiert.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-119">The `TypeOf`...`Is` expression evaluates to `True` if the run-time type of the operand is derived from or implements the specified type.</span></span>  
  
 <span data-ttu-id="6fb2b-120">Im folgenden Beispiel wird `TypeOf` für Objektvariablen verwendet, die auf Wert-und Verweis Typen verweisen.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-120">The following example uses `TypeOf` on object variables referring to value and reference types.</span></span>  
  
```vb  
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
  
 <span data-ttu-id="6fb2b-121">Im vorherigen Beispiel werden die folgenden Zeilen in das **Debugfenster** geschrieben:</span><span class="sxs-lookup"><span data-stu-id="6fb2b-121">The preceding example writes the following lines to the **Debug** window:</span></span>  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 <span data-ttu-id="6fb2b-122">Die Objekt Variable `num` verweist auf Daten vom Typ `Integer` und `frm` verweist auf ein Objekt der Klasse <xref:System.Windows.Forms.Form> .</span><span class="sxs-lookup"><span data-stu-id="6fb2b-122">The object variable `num` refers to data of type `Integer`, and `frm` refers to an object of class <xref:System.Windows.Forms.Form>.</span></span>  
  
## <a name="object-arrays"></a><span data-ttu-id="6fb2b-123">Objekt Arrays</span><span class="sxs-lookup"><span data-stu-id="6fb2b-123">Object Arrays</span></span>  

 <span data-ttu-id="6fb2b-124">Sie können ein Array von Variablen deklarieren und verwenden `Object` .</span><span class="sxs-lookup"><span data-stu-id="6fb2b-124">You can declare and use an array of `Object` variables.</span></span> <span data-ttu-id="6fb2b-125">Dies ist nützlich, wenn Sie eine Vielzahl von Datentypen und Objektklassen verarbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-125">This is useful when you need to handle a variety of data types and object classes.</span></span> <span data-ttu-id="6fb2b-126">Alle Elemente in einem Array müssen denselben deklarierten Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-126">All the elements in an array must have the same declared data type.</span></span> <span data-ttu-id="6fb2b-127">Durch das Deklarieren dieses Datentyps als `Object` können Sie Objekte und Klassen Instanzen neben anderen Datentypen im Array speichern.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-127">Declaring this data type as `Object` allows you to store objects and class instances alongside other data types in the array.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fb2b-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fb2b-128">See also</span></span>

- [<span data-ttu-id="6fb2b-129">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="6fb2b-129">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="6fb2b-130">Deklaration von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="6fb2b-130">Object Variable Declaration</span></span>](object-variable-declaration.md)
- [<span data-ttu-id="6fb2b-131">Zuweisung von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="6fb2b-131">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="6fb2b-132">Vorgehensweise: Verweisen auf die aktuelle Instanz eines Objekts</span><span class="sxs-lookup"><span data-stu-id="6fb2b-132">How to: Refer to the Current Instance of an Object</span></span>](how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="6fb2b-133">Vorgehensweise: Bestimmen des Typs, auf den eine Objektvariable verweist</span><span class="sxs-lookup"><span data-stu-id="6fb2b-133">How to: Determine What Type an Object Variable Refers To</span></span>](how-to-determine-what-type-an-object-variable-refers-to.md)
- [<span data-ttu-id="6fb2b-134">Vorgehensweise: Bestimmen des Bezugs zwischen zwei Objekten</span><span class="sxs-lookup"><span data-stu-id="6fb2b-134">How to: Determine Whether Two Objects Are Related</span></span>](how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="6fb2b-135">Vorgehensweise: Bestimmen der Gleichheit zweier Objekte</span><span class="sxs-lookup"><span data-stu-id="6fb2b-135">How to: Determine Whether Two Objects Are Identical</span></span>](how-to-determine-whether-two-objects-are-identical.md)
- [<span data-ttu-id="6fb2b-136">Datentypen</span><span class="sxs-lookup"><span data-stu-id="6fb2b-136">Data Types</span></span>](../data-types/index.md)
