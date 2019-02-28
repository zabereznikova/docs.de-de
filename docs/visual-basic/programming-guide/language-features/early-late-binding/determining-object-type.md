---
title: Bestimmen des Objekttyps (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: becbbef008e8a474db198748d45f260fcb90c758
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966774"
---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="d7f48-102">Bestimmen des Objekttyps (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7f48-102">Determining Object Type (Visual Basic)</span></span>
<span data-ttu-id="d7f48-103">Generisches Objektvariablen (d. h. deklarierte Variablen als `Object`) Objekte aus einer Klasse enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="d7f48-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="d7f48-104">Bei Verwendung von Variablen des Typs `Object`, müssen Sie möglicherweise verschiedene Aktionen basierend auf der Klasse des Objekts, z. B. einige Objekte können nicht unterstützen, eine bestimmte Eigenschaft oder Methode.</span><span class="sxs-lookup"><span data-stu-id="d7f48-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> <span data-ttu-id="d7f48-105">Visual Basic bietet zwei Methoden ermitteln, welche Art von Objekt in eine Objektvariable gespeichert ist: die `TypeName` Funktion und die `TypeOf...Is` Operator.</span><span class="sxs-lookup"><span data-stu-id="d7f48-105">Visual Basic provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="d7f48-106">TypeName "und" TypeOf... Ist</span><span class="sxs-lookup"><span data-stu-id="d7f48-106">TypeName and TypeOf…Is</span></span>  
 <span data-ttu-id="d7f48-107">Die `TypeName` Funktion gibt eine Zeichenfolge zurück und ist die beste Wahl, beim Speichern oder Anzeigen der Klassenname des Objekts, wie im folgenden Codefragment gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d7f48-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 <span data-ttu-id="d7f48-108">Die `TypeOf...Is` Operator ist die beste Wahl für den Typ eines Objekts, zu testen, da sie viel schneller als eine entsprechende Zeichenfolge Vergleich ist `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="d7f48-108">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="d7f48-109">Das folgende Codefragment verwendet `TypeOf...Is` innerhalb einer `If...Then...Else` Anweisung:</span><span class="sxs-lookup"><span data-stu-id="d7f48-109">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 <span data-ttu-id="d7f48-110">Hier ist ein Wort der Warnung fällig.</span><span class="sxs-lookup"><span data-stu-id="d7f48-110">A word of caution is due here.</span></span> <span data-ttu-id="d7f48-111">Die `TypeOf...Is` Operator gibt `True` wird ein Objekt eines bestimmten Typs ist, oder von einem bestimmten Typ abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="d7f48-111">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="d7f48-112">Fast alles, was Visual Basic bieten Ihnen umfasst Objekte, die einige Elemente, die normalerweise nicht betrachtet werden als Objekte, z. B. Zeichenfolgen und Zahlen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d7f48-112">Almost everything you do with Visual Basic involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="d7f48-113">Diese Objekte davon abgeleitet sind, und Methoden erben <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="d7f48-113">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="d7f48-114">Beim Übergeben einer `Integer` und ausgewerteten mit `Object`, die `TypeOf...Is` Operator gibt `True`.</span><span class="sxs-lookup"><span data-stu-id="d7f48-114">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="d7f48-115">Das folgende Beispiel meldet, dass der Parameter `InParam` sowohl eine `Object` und `Integer`:</span><span class="sxs-lookup"><span data-stu-id="d7f48-115">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 <span data-ttu-id="d7f48-116">Im folgenden Beispiel wird sowohl `TypeOf...Is` und `TypeName` bestimmen den Typ des Objekts übergeben, die Sie in der `Ctrl` Argument.</span><span class="sxs-lookup"><span data-stu-id="d7f48-116">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="d7f48-117">Die `TestObject` Prozeduraufrufe `ShowType` mit drei verschiedene Arten von Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="d7f48-117">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="d7f48-118">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="d7f48-118">To run the example</span></span>  
  
1.  <span data-ttu-id="d7f48-119">Erstellen Sie ein neues Windows-Anwendungsprojekt und fügen eine <xref:System.Windows.Forms.Button> -Steuerelement, ein <xref:System.Windows.Forms.CheckBox> -Steuerelement, und ein <xref:System.Windows.Forms.RadioButton> -Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="d7f48-119">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2.  <span data-ttu-id="d7f48-120">Rufen Sie über die Schaltfläche im Formular die `TestObject` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="d7f48-120">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3.  <span data-ttu-id="d7f48-121">Fügen Sie dem Formular den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="d7f48-121">Add the following code to your form:</span></span>  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a><span data-ttu-id="d7f48-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7f48-122">See also</span></span>
- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [<span data-ttu-id="d7f48-123">Aufrufen einer Eigenschaft oder Methode mit einem Zeichenfolgennamen</span><span class="sxs-lookup"><span data-stu-id="d7f48-123">Calling a Property or Method Using a String Name</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)
- [<span data-ttu-id="d7f48-124">Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="d7f48-124">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="d7f48-125">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d7f48-125">If...Then...Else Statement</span></span>](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="d7f48-126">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="d7f48-126">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="d7f48-127">Integer-Datentyp</span><span class="sxs-lookup"><span data-stu-id="d7f48-127">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
