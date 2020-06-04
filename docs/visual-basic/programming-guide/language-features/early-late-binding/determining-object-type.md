---
title: Bestimmen des Objekttyps
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: 3b1c4ad0ab4fd8d2897aff6ad9097cdc81272455
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410643"
---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="0fca8-102">Bestimmen des Objekttyps (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0fca8-102">Determining Object Type (Visual Basic)</span></span>
<span data-ttu-id="0fca8-103">Generische Objektvariablen (d. h. Variablen, die Sie als deklarieren `Object` ) können Objekte aus beliebigen Klassen enthalten.</span><span class="sxs-lookup"><span data-stu-id="0fca8-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="0fca8-104">Wenn Sie Variablen vom Typ verwenden `Object` , müssen Sie möglicherweise basierend auf der-Klasse des-Objekts verschiedene Aktionen durchführen, z. b. können einige Objekte eine bestimmte Eigenschaft oder Methode nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0fca8-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> <span data-ttu-id="0fca8-105">Visual Basic bietet zwei Möglichkeiten, um zu bestimmen, welcher Objekttyp in einer Objektvariablen gespeichert wird: die `TypeName` -Funktion und der- `TypeOf...Is` Operator.</span><span class="sxs-lookup"><span data-stu-id="0fca8-105">Visual Basic provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="0fca8-106">Typname und typeof... Richtet</span><span class="sxs-lookup"><span data-stu-id="0fca8-106">TypeName and TypeOf…Is</span></span>  
 <span data-ttu-id="0fca8-107">Die `TypeName` -Funktion gibt eine Zeichenfolge zurück und ist die beste Wahl, wenn Sie den Klassennamen eines Objekts speichern oder anzeigen müssen, wie im folgenden Code Fragment gezeigt:</span><span class="sxs-lookup"><span data-stu-id="0fca8-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 <span data-ttu-id="0fca8-108">Der `TypeOf...Is` -Operator ist die beste Wahl, um den Typ eines Objekts zu testen, da er viel schneller ist als ein entsprechender Zeichen folgen Vergleich mit `TypeName` .</span><span class="sxs-lookup"><span data-stu-id="0fca8-108">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="0fca8-109">Das folgende Code Fragment verwendet `TypeOf...Is` in einer- `If...Then...Else` Anweisung:</span><span class="sxs-lookup"><span data-stu-id="0fca8-109">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 <span data-ttu-id="0fca8-110">Hier ist ein Wort mit Bedacht.</span><span class="sxs-lookup"><span data-stu-id="0fca8-110">A word of caution is due here.</span></span> <span data-ttu-id="0fca8-111">Der- `TypeOf...Is` Operator gibt zurück `True` , wenn ein Objekt einen bestimmten Typ hat oder von einem bestimmten Typ abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="0fca8-111">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="0fca8-112">Fast alles, was Sie mit Visual Basic tun, umfasst-Objekte, die einige Elemente enthalten, die normalerweise nicht als Objekte angesehen werden, z. b. Zeichen folgen und ganze Zahlen</span><span class="sxs-lookup"><span data-stu-id="0fca8-112">Almost everything you do with Visual Basic involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="0fca8-113">Diese Objekte werden von abgeleitet und Erben Methoden von <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="0fca8-113">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="0fca8-114">Wenn ein `Integer` und mit ausgewertet `Object` wird, `TypeOf...Is` gibt der Operator zurück `True` .</span><span class="sxs-lookup"><span data-stu-id="0fca8-114">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="0fca8-115">Im folgenden Beispiel wird berichtet, dass der `InParam` -Parameter sowohl ein `Object` als auch ein ist `Integer` :</span><span class="sxs-lookup"><span data-stu-id="0fca8-115">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 <span data-ttu-id="0fca8-116">Im folgenden Beispiel wird sowohl `TypeOf...Is` als auch verwendet `TypeName` , um den Objekttyp zu bestimmen, der im-Argument an ihn übermittelt wird `Ctrl`</span><span class="sxs-lookup"><span data-stu-id="0fca8-116">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="0fca8-117">Die `TestObject` Prozedur ruft `ShowType` mit drei unterschiedlichen Arten von Steuerelementen auf.</span><span class="sxs-lookup"><span data-stu-id="0fca8-117">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="0fca8-118">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="0fca8-118">To run the example</span></span>  
  
1. <span data-ttu-id="0fca8-119">Erstellen Sie ein neues Windows-Anwendungsprojekt, und fügen Sie <xref:System.Windows.Forms.Button> dem Formular ein Steuerelement, ein <xref:System.Windows.Forms.CheckBox> -Steuerelement und ein-Steuerelement hinzu <xref:System.Windows.Forms.RadioButton> .</span><span class="sxs-lookup"><span data-stu-id="0fca8-119">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2. <span data-ttu-id="0fca8-120">Klicken Sie in der Schaltfläche auf dem Formular auf die `TestObject` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="0fca8-120">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3. <span data-ttu-id="0fca8-121">Fügen Sie dem Formular folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="0fca8-121">Add the following code to your form:</span></span>  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a><span data-ttu-id="0fca8-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0fca8-122">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [<span data-ttu-id="0fca8-123">Aufrufen einer Eigenschaft oder Methode mit einem Zeichenfolgennamen</span><span class="sxs-lookup"><span data-stu-id="0fca8-123">Calling a Property or Method Using a String Name</span></span>](calling-a-property-or-method-using-a-string-name.md)
- [<span data-ttu-id="0fca8-124">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="0fca8-124">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="0fca8-125">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0fca8-125">If...Then...Else Statement</span></span>](../../../language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="0fca8-126">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="0fca8-126">String Data Type</span></span>](../../../language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="0fca8-127">Integer-Datentyp</span><span class="sxs-lookup"><span data-stu-id="0fca8-127">Integer Data Type</span></span>](../../../language-reference/data-types/integer-data-type.md)
