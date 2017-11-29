---
title: Bestimmen des Objekttyps (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9a63b5cf5941deb4dcc7518880b4dc7d0545803c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="2f59d-102">Bestimmen des Objekttyps (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f59d-102">Determining Object Type (Visual Basic)</span></span>
<span data-ttu-id="2f59d-103">Generische Objektvariablen (d. h. Variablen Sie als deklarieren `Object`) Objekte aus einer Klasse enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="2f59d-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="2f59d-104">Bei Verwendung von Variablen des Typs `Object`, müssen Sie möglicherweise unterschiedliche Aktionen basierend auf der Klasse des Objekts, z. B. einige Objekte möglicherweise nicht unterstützen, eine bestimmte Eigenschaft oder Methode.</span><span class="sxs-lookup"><span data-stu-id="2f59d-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="2f59d-105">bietet zwei Möglichkeit zum bestimmen, welche Art von Objekt in der Objektvariable gespeichert ist: der `TypeName` Funktion und die `TypeOf...Is` Operator.</span><span class="sxs-lookup"><span data-stu-id="2f59d-105"> provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="2f59d-106">TypeName "und" TypeOf... Ist</span><span class="sxs-lookup"><span data-stu-id="2f59d-106">TypeName and TypeOf…Is</span></span>  
 <span data-ttu-id="2f59d-107">Die `TypeName` Funktion gibt eine Zeichenfolge zurück und ist die beste Wahl, wenn Sie speichern oder den Klassennamen eines Objekts anzeigen müssen, wie im folgenden Codefragment gezeigt:</span><span class="sxs-lookup"><span data-stu-id="2f59d-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]  
  
 <span data-ttu-id="2f59d-108">Die `TypeOf...Is` Operator ist die beste Wahl für das Testen des Objekttyps, da er viel schneller als ein entsprechender Zeichenfolgenvergleich mit `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="2f59d-108">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="2f59d-109">Das folgende Codefragment verwendet `TypeOf...Is` innerhalb einer `If...Then...Else` Anweisung:</span><span class="sxs-lookup"><span data-stu-id="2f59d-109">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 [!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]  
  
 <span data-ttu-id="2f59d-110">Vorsicht ist hier fällig.</span><span class="sxs-lookup"><span data-stu-id="2f59d-110">A word of caution is due here.</span></span> <span data-ttu-id="2f59d-111">Die `TypeOf...Is` Operator gibt `True` ein Objekt verfügt über einen bestimmten Typ oder einen bestimmten Typ abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="2f59d-111">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="2f59d-112">Fast alle Aufgaben, die Sie mit [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] umfasst Objekte, darunter einige Elemente, die normalerweise nicht als Objekte, z. B. Zeichenfolgen und ganzen Zahlen betrachtet.</span><span class="sxs-lookup"><span data-stu-id="2f59d-112">Almost everything you do with [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="2f59d-113">Diese Objekte abgeleitet sind, erben Sie Methoden aus <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="2f59d-113">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="2f59d-114">Beim Übergeben einer `Integer` und ausgewerteten mit `Object`, `TypeOf...Is` Operator gibt `True`.</span><span class="sxs-lookup"><span data-stu-id="2f59d-114">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="2f59d-115">Im folgenden Beispiel gemeldet, die den Parameter `InParam` ist sowohl ein `Object` und ein `Integer`:</span><span class="sxs-lookup"><span data-stu-id="2f59d-115">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 [!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]  
  
 <span data-ttu-id="2f59d-116">Im folgenden Beispiel wird sowohl `TypeOf...Is` und `TypeName` zum Bestimmen des Typs des Objekts übergeben wird, in der `Ctrl` Argument.</span><span class="sxs-lookup"><span data-stu-id="2f59d-116">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="2f59d-117">Die `TestObject` Prozeduraufrufe `ShowType` mit drei verschiedene Arten von Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="2f59d-117">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="2f59d-118">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="2f59d-118">To run the example</span></span>  
  
1.  <span data-ttu-id="2f59d-119">Erstellen Sie ein neues Windows-Anwendungsprojekt und Hinzufügen einer <xref:System.Windows.Forms.Button> -Steuerelement, ein <xref:System.Windows.Forms.CheckBox> -Steuerelement, und ein <xref:System.Windows.Forms.RadioButton> Steuerelement dem Formular.</span><span class="sxs-lookup"><span data-stu-id="2f59d-119">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2.  <span data-ttu-id="2f59d-120">Rufen Sie auf die Schaltfläche auf dem Formular und die `TestObject` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="2f59d-120">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3.  <span data-ttu-id="2f59d-121">Fügen Sie dem Formular den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="2f59d-121">Add the following code to your form:</span></span>  
  
     [!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2f59d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f59d-122">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Information.TypeName%2A>  
 [<span data-ttu-id="2f59d-123">Aufrufen einer Eigenschaft oder Methode mit einem Zeichenfolgennamen</span><span class="sxs-lookup"><span data-stu-id="2f59d-123">Calling a Property or Method Using a String Name</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)  
 [<span data-ttu-id="2f59d-124">Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="2f59d-124">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="2f59d-125">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2f59d-125">If...Then...Else Statement</span></span>](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="2f59d-126">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="2f59d-126">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [<span data-ttu-id="2f59d-127">Integer-Datentyp</span><span class="sxs-lookup"><span data-stu-id="2f59d-127">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
