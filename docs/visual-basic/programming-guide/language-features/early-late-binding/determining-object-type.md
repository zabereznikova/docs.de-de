---
title: Bestimmen des Objekttyps (Visual Basic) | Microsoft-Dokumentation
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
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables, testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
caps.latest.revision: 13
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
ms.openlocfilehash: fec7a275029dde469425b651d5b1220cb21ddbf6
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="546a7-102">Bestimmen des Objekttyps (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="546a7-102">Determining Object Type (Visual Basic)</span></span>
<span data-ttu-id="546a7-103">Generische Objektvariablen (d. h. deklarierte Variablen als `Object`) können Objekte aus allen Klassen enthalten.</span><span class="sxs-lookup"><span data-stu-id="546a7-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="546a7-104">Bei Verwendung von Variablen des Typs `Object`, müssen Sie möglicherweise unterschiedliche Aktionen basierend auf der Klasse des Objekts, z. B. einige Objekte möglicherweise nicht unterstützen, eine bestimmte Eigenschaft oder Methode.</span><span class="sxs-lookup"><span data-stu-id="546a7-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="546a7-105">stellt zwei Methoden zum bestimmen, welche Art von Objekt in einer Objektvariablen gespeichert ist: die `TypeName` Funktion und die `TypeOf...Is` Operator.</span><span class="sxs-lookup"><span data-stu-id="546a7-105"> provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="546a7-106">TypeName und TypeOf... Ist</span><span class="sxs-lookup"><span data-stu-id="546a7-106">TypeName and TypeOf…Is</span></span>  
 <span data-ttu-id="546a7-107">Die `TypeName` -Funktion gibt eine Zeichenfolge zurück und ist die beste Wahl, beim Speichern oder Anzeigen des Klassennamens eines Objekts, wie im folgenden Codefragment gezeigt:</span><span class="sxs-lookup"><span data-stu-id="546a7-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 <span data-ttu-id="546a7-108">[!code-vb[VbVbalrOOP&#92;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="546a7-108">[!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]</span></span>  
  
 <span data-ttu-id="546a7-109">Die `TypeOf...Is` Operator ist die beste Wahl für den Typ eines Objekts, testen, da er viel schneller als ein entsprechender Zeichenfolgenvergleich mit ist `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="546a7-109">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="546a7-110">Das folgende Codefragment verwendet `TypeOf...Is` innerhalb einer `If...Then...Else` Anweisung:</span><span class="sxs-lookup"><span data-stu-id="546a7-110">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 <span data-ttu-id="546a7-111">[!code-vb[VbVbalrOOP&#93;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="546a7-111">[!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]</span></span>  
  
 <span data-ttu-id="546a7-112">Hier ist ein Wort der Warnung fällig.</span><span class="sxs-lookup"><span data-stu-id="546a7-112">A word of caution is due here.</span></span> <span data-ttu-id="546a7-113">Die `TypeOf...Is` Operator gibt `True` wird ein Objekt eines bestimmten Typs ist, oder von einem bestimmten Typ abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="546a7-113">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="546a7-114">Fast alle Aufgaben, die Sie mit [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] umfasst Objekte, die einige Elemente, die normalerweise nicht als Objekte betrachtet werden, z. B. Zeichenfolgen und ganze Zahlen enthalten.</span><span class="sxs-lookup"><span data-stu-id="546a7-114">Almost everything you do with [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="546a7-115">Diese Objekte werden von abgeleitet und erben Methoden <xref:System.Object>.</xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="546a7-115">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="546a7-116">Beim Übergeben einer `Integer` und ausgewerteten mit `Object`, `TypeOf...Is` Operator gibt `True`.</span><span class="sxs-lookup"><span data-stu-id="546a7-116">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="546a7-117">Im folgende Beispiel meldet, der Parameter `InParam` sowohl ein `Object` und ein `Integer`:</span><span class="sxs-lookup"><span data-stu-id="546a7-117">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 <span data-ttu-id="546a7-118">[!code-vb[VbVbalrOOP&#94;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="546a7-118">[!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]</span></span>  
  
 <span data-ttu-id="546a7-119">Im folgenden Beispiel wird sowohl `TypeOf...Is` und `TypeName` den Typ des übergebenen Objekts bestimmt die `Ctrl` Argument.</span><span class="sxs-lookup"><span data-stu-id="546a7-119">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="546a7-120">Die `TestObject` Prozeduraufrufe `ShowType` mit drei verschiedenen Arten von Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="546a7-120">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="546a7-121">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="546a7-121">To run the example</span></span>  
  
1.  <span data-ttu-id="546a7-122">Erstellen Sie ein neues Windows-Anwendungsprojekt und fügen ein <xref:System.Windows.Forms.Button>-Steuerelement, ein <xref:System.Windows.Forms.CheckBox>-Steuerelement und ein <xref:System.Windows.Forms.RadioButton>-Steuerelement auf das Formular.</xref:System.Windows.Forms.RadioButton> </xref:System.Windows.Forms.CheckBox> </xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="546a7-122">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2.  <span data-ttu-id="546a7-123">Rufen Sie über die Schaltfläche im Formular der `TestObject` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="546a7-123">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3.  <span data-ttu-id="546a7-124">Fügen Sie dem Formular den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="546a7-124">Add the following code to your form:</span></span>  
  
     <span data-ttu-id="546a7-125">[!code-vb[VbVbalrOOP&#95;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="546a7-125">[!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="546a7-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="546a7-126">See Also</span></span>  
 <span data-ttu-id="546a7-127"><xref:Microsoft.VisualBasic.Information.TypeName%2A></xref:Microsoft.VisualBasic.Information.TypeName%2A></span><span class="sxs-lookup"><span data-stu-id="546a7-127"><xref:Microsoft.VisualBasic.Information.TypeName%2A></span></span>   
<span data-ttu-id="546a7-128"> [Aufrufen einer Eigenschaft oder Methode mit einem Zeichenfolgennamen](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md) </span><span class="sxs-lookup"><span data-stu-id="546a7-128"> [Calling a Property or Method Using a String Name](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md) </span></span>  
<span data-ttu-id="546a7-129"> [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="546a7-129"> [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span></span>  
<span data-ttu-id="546a7-130"> [If... Dann... Else-Anweisung](../../../../visual-basic/language-reference/statements/if-then-else-statement.md) </span><span class="sxs-lookup"><span data-stu-id="546a7-130"> [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md) </span></span>  
<span data-ttu-id="546a7-131"> [String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="546a7-131"> [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) </span></span>  
<span data-ttu-id="546a7-132"> [Integer-Datentyp](../../../../visual-basic/language-reference/data-types/integer-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="546a7-132"> [Integer Data Type](../../../../visual-basic/language-reference/data-types/integer-data-type.md)</span></span>
