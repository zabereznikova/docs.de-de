---
title: 'Vorgehensweise: Deklarieren eines Objekts mithilfe eines Objektinitialisierers (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: eeaf3b4a611944395269fcae045bab00d25f0167
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561066"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a><span data-ttu-id="3c5f3-102">Vorgehensweise: Deklarieren eines Objekts mithilfe eines Objektinitialisierers (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c5f3-102">How to: Declare an Object by Using an Object Initializer (Visual Basic)</span></span>
<span data-ttu-id="3c5f3-103">Objektinitialisierer ermöglichen Sie deklarieren und instanziieren Sie eine Instanz einer Klasse in einer einzigen Anweisung.</span><span class="sxs-lookup"><span data-stu-id="3c5f3-103">Object initializers enable you to declare and instantiate an instance of a class in a single statement.</span></span> <span data-ttu-id="3c5f3-104">Darüber hinaus können Sie eine oder mehrere Member der Instanz zur gleichen Zeit, initialisieren, ohne einen parametrisierten Konstruktor aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="3c5f3-104">In addition, you can initialize one or more members of the instance at the same time, without invoking a parameterized constructor.</span></span>  
  
 <span data-ttu-id="3c5f3-105">Wenn Sie einen Objektinitialisierer verwenden, um eine Instanz eines benannten Typs erstellen, wird der Standardkonstruktor für die Klasse aufgerufen, gefolgt von der Initialisierung der angegebenen Member in der Reihenfolge, in die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="3c5f3-105">When you use an object initializer to create an instance of a named type, the default constructor for the class is called, followed by initialization of designated members in the order you specify.</span></span>  
  
 <span data-ttu-id="3c5f3-106">Das folgende Verfahren zeigt, wie zum Erstellen einer Instanz von einem `Student` Klasse auf drei verschiedene Arten.</span><span class="sxs-lookup"><span data-stu-id="3c5f3-106">The following procedure shows how to create an instance of a `Student` class in three different ways.</span></span> <span data-ttu-id="3c5f3-107">Die Klasse verfügt über Vorname, Nachname und Jahr Klasseneigenschaften, u. a.</span><span class="sxs-lookup"><span data-stu-id="3c5f3-107">The class has first name, last name, and class year properties, among others.</span></span> <span data-ttu-id="3c5f3-108">Jede dieser drei Deklarationen erstellt eine neue Instanz der `Student`, mit der Eigenschaft `First` legen Sie auf "Michael,"-Eigenschaft `Last` "Tucker" festgelegt, und alle anderen Elemente auf ihre Standardwerte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3c5f3-108">Each of the three declarations creates a new instance of `Student`, with property `First` set to "Michael", property `Last` set to "Tucker", and all other members set to their default values.</span></span> <span data-ttu-id="3c5f3-109">Das Ergebnis jeder Deklaration in der Prozedur entspricht im folgenden Beispiel, das einen Objektinitialisierer nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="3c5f3-109">The result of each declaration in the procedure is equivalent to the following example, which does not use an object initializer.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#20](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_1.vb)]  
  
 <span data-ttu-id="3c5f3-110">Eine Implementierung der `Student` Klasse, finden Sie unter [Vorgehensweise: Erstellen Sie eine Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="3c5f3-110">For an implementation of the `Student` class, see [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="3c5f3-111">Kopieren Sie den Code in diesem Thema richten Sie die Klasse, und erstellen eine Liste der `Student` Objekte zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3c5f3-111">You can copy the code from that topic to set up the class and create a list of `Student` objects to work with.</span></span>  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a><span data-ttu-id="3c5f3-112">So erstellen Sie ein Objekt einer benannten Klasse mit einem Objektinitialisierer</span><span class="sxs-lookup"><span data-stu-id="3c5f3-112">To create an object of a named class by using an object initializer</span></span>  
  
1.  <span data-ttu-id="3c5f3-113">Beginnen Sie die Deklaration, als ob Sie einen Konstruktor nutzen will.</span><span class="sxs-lookup"><span data-stu-id="3c5f3-113">Begin the declaration as if you planned to use a constructor.</span></span>  
  
     `Dim student1 As New Student`  
  
2.  <span data-ttu-id="3c5f3-114">Geben Sie das Schlüsselwort `With`, gefolgt von einer Initialisierungsliste in geschweiften Klammern.</span><span class="sxs-lookup"><span data-stu-id="3c5f3-114">Type the keyword `With`, followed by an initialization list in braces.</span></span>  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3.  <span data-ttu-id="3c5f3-115">Enthalten Sie in der Initialisierungsliste jede Eigenschaft, die Sie verwenden möchten, initialisieren und einen Anfangswert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3c5f3-115">In the initialization list, include each property that you want to initialize and assign an initial value to it.</span></span> <span data-ttu-id="3c5f3-116">Der Name der Eigenschaft wird ein Punkt voranstehen.</span><span class="sxs-lookup"><span data-stu-id="3c5f3-116">The name of the property is preceded by a period.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#21](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_2.vb)]  
  
     <span data-ttu-id="3c5f3-117">Sie können eine oder mehrere Member der Klasse initialisieren.</span><span class="sxs-lookup"><span data-stu-id="3c5f3-117">You can initialize one or more members of the class.</span></span>  
  
4.  <span data-ttu-id="3c5f3-118">Alternativ können Sie eine neue Instanz der Klasse deklarieren, und klicken Sie dann einen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="3c5f3-118">Alternatively, you can declare a new instance of the class and then assign a value to it.</span></span> <span data-ttu-id="3c5f3-119">Deklarieren Sie zuerst eine Instanz von `Student`:</span><span class="sxs-lookup"><span data-stu-id="3c5f3-119">First, declare an instance of `Student`:</span></span>  
  
     `Dim student2 As Student`  
  
5.  <span data-ttu-id="3c5f3-120">Beginnen Sie mit der Erstellung einer Instanz von `Student` auf die übliche Weise.</span><span class="sxs-lookup"><span data-stu-id="3c5f3-120">Begin the creation of an instance of `Student` in the normal way.</span></span>  
  
     `Dim student2 As Student = New Student`  
  
6.  <span data-ttu-id="3c5f3-121">Typ `With` und klicken Sie dann einen Objektinitialisierer zum Initialisieren von Membern von ein oder mehrere der neuen Instanz.</span><span class="sxs-lookup"><span data-stu-id="3c5f3-121">Type `With` and then an object initializer to initialize one or more members of the new instance.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#22](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_3.vb)]  
  
7.  <span data-ttu-id="3c5f3-122">Sie können die Definition im vorherigen Schritt vereinfachen, indem das Auslassen `As Student`.</span><span class="sxs-lookup"><span data-stu-id="3c5f3-122">You can simplify the definition in the previous step by omitting `As Student`.</span></span> <span data-ttu-id="3c5f3-123">Wenn Sie dies tun, wird der Compiler bestimmt, die `student3` ist eine Instanz der `Student` mithilfe von lokalen Typrückschluss.</span><span class="sxs-lookup"><span data-stu-id="3c5f3-123">If you do this, the compiler determines that `student3` is an instance of `Student` by using local type inference.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#23](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_4.vb)]  
  
     <span data-ttu-id="3c5f3-124">Weitere Informationen finden Sie unter [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="3c5f3-124">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c5f3-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c5f3-125">See also</span></span>
- [<span data-ttu-id="3c5f3-126">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="3c5f3-126">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="3c5f3-127">Vorgehensweise: Erstellen Sie eine Liste von Elementen</span><span class="sxs-lookup"><span data-stu-id="3c5f3-127">How to: Create a List of Items</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
- [<span data-ttu-id="3c5f3-128">Objektinitialisierer: Benannte und anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="3c5f3-128">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="3c5f3-129">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="3c5f3-129">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
