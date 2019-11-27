---
title: 'Gewusst wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: ae04d338b61027c3917ad3a7f62ff40f0a95e53e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347138"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a><span data-ttu-id="c0358-102">Gewusst wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0358-102">How to: Declare an Object by Using an Object Initializer (Visual Basic)</span></span>
<span data-ttu-id="c0358-103">Objektinitialisierer ermöglichen es Ihnen, eine Instanz einer Klasse in einer einzelnen Anweisung zu deklarieren und zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="c0358-103">Object initializers enable you to declare and instantiate an instance of a class in a single statement.</span></span> <span data-ttu-id="c0358-104">Außerdem können Sie einen oder mehrere Member der-Instanz gleichzeitig initialisieren, ohne einen parametrisierten Konstruktor aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="c0358-104">In addition, you can initialize one or more members of the instance at the same time, without invoking a parameterized constructor.</span></span>  
  
 <span data-ttu-id="c0358-105">Wenn Sie einen Objektinitialisierer verwenden, um eine Instanz eines benannten Typs zu erstellen, wird der Parameter lose Konstruktor für die Klasse aufgerufen, gefolgt von der Initialisierung der designierten Elemente in der von Ihnen angegebenen Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="c0358-105">When you use an object initializer to create an instance of a named type, the parameterless constructor for the class is called, followed by initialization of designated members in the order you specify.</span></span>  
  
 <span data-ttu-id="c0358-106">Im folgenden Verfahren wird gezeigt, wie Sie eine Instanz einer `Student`-Klasse auf drei verschiedene Arten erstellen.</span><span class="sxs-lookup"><span data-stu-id="c0358-106">The following procedure shows how to create an instance of a `Student` class in three different ways.</span></span> <span data-ttu-id="c0358-107">Die Klasse verfügt unter anderem über die Eigenschaften "Vorname", "Nachname" und "Klassen Jahr".</span><span class="sxs-lookup"><span data-stu-id="c0358-107">The class has first name, last name, and class year properties, among others.</span></span> <span data-ttu-id="c0358-108">Jede der drei Deklarationen erstellt eine neue Instanz `Student`, bei der die-`First` Eigenschaft auf "Michael" festgelegt ist, die-`Last` Eigenschaft auf "Tucker" festgelegt ist und alle anderen Member auf ihre Standardwerte festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="c0358-108">Each of the three declarations creates a new instance of `Student`, with property `First` set to "Michael", property `Last` set to "Tucker", and all other members set to their default values.</span></span> <span data-ttu-id="c0358-109">Das Ergebnis jeder Deklaration in der Prozedur entspricht dem folgenden Beispiel, in dem kein Objektinitialisierer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c0358-109">The result of each declaration in the procedure is equivalent to the following example, which does not use an object initializer.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 <span data-ttu-id="c0358-110">Eine Implementierung der `Student`-Klasse finden Sie unter Gewusst [wie: Erstellen einer Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="c0358-110">For an implementation of the `Student` class, see [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="c0358-111">Sie können den Code aus diesem Thema kopieren, um die-Klasse einzurichten und eine Liste mit `Student` Objekten zu erstellen, mit denen Sie arbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="c0358-111">You can copy the code from that topic to set up the class and create a list of `Student` objects to work with.</span></span>  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a><span data-ttu-id="c0358-112">So erstellen Sie ein Objekt einer benannten Klasse mithilfe eines Objektinitialisierers</span><span class="sxs-lookup"><span data-stu-id="c0358-112">To create an object of a named class by using an object initializer</span></span>  
  
1. <span data-ttu-id="c0358-113">Beginnen Sie die Deklaration, als ob Sie einen Konstruktor verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c0358-113">Begin the declaration as if you planned to use a constructor.</span></span>  
  
     `Dim student1 As New Student`  
  
2. <span data-ttu-id="c0358-114">Geben Sie das Schlüsselwort `With`ein, gefolgt von einer Initialisierungs Liste in geschweiften Klammern.</span><span class="sxs-lookup"><span data-stu-id="c0358-114">Type the keyword `With`, followed by an initialization list in braces.</span></span>  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3. <span data-ttu-id="c0358-115">Fügen Sie in der Initialisierungs Liste jede Eigenschaft ein, die Sie initialisieren möchten, und weisen Sie Ihr einen Anfangswert zu.</span><span class="sxs-lookup"><span data-stu-id="c0358-115">In the initialization list, include each property that you want to initialize and assign an initial value to it.</span></span> <span data-ttu-id="c0358-116">Dem Namen der Eigenschaft wird ein Zeitraum vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="c0358-116">The name of the property is preceded by a period.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     <span data-ttu-id="c0358-117">Sie können einen oder mehrere Member der-Klasse initialisieren.</span><span class="sxs-lookup"><span data-stu-id="c0358-117">You can initialize one or more members of the class.</span></span>  
  
4. <span data-ttu-id="c0358-118">Alternativ können Sie eine neue Instanz der Klasse deklarieren und ihr dann einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c0358-118">Alternatively, you can declare a new instance of the class and then assign a value to it.</span></span> <span data-ttu-id="c0358-119">Deklarieren Sie zuerst eine Instanz von `Student`:</span><span class="sxs-lookup"><span data-stu-id="c0358-119">First, declare an instance of `Student`:</span></span>  
  
     `Dim student2 As Student`  
  
5. <span data-ttu-id="c0358-120">Beginnen Sie mit der Erstellung einer Instanz von `Student` auf die übliche Weise.</span><span class="sxs-lookup"><span data-stu-id="c0358-120">Begin the creation of an instance of `Student` in the normal way.</span></span>  
  
     `Dim student2 As Student = New Student`  
  
6. <span data-ttu-id="c0358-121">Geben Sie `With` und dann einen Objektinitialisierer ein, um einen oder mehrere Member der neuen Instanz zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="c0358-121">Type `With` and then an object initializer to initialize one or more members of the new instance.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7. <span data-ttu-id="c0358-122">Sie können die Definition im vorherigen Schritt vereinfachen, indem Sie `As Student`weglassen.</span><span class="sxs-lookup"><span data-stu-id="c0358-122">You can simplify the definition in the previous step by omitting `As Student`.</span></span> <span data-ttu-id="c0358-123">Wenn Sie dies tun, bestimmt der Compiler, dass `student3` eine Instanz von `Student` ist, indem der lokale Typrückschluss verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c0358-123">If you do this, the compiler determines that `student3` is an instance of `Student` by using local type inference.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     <span data-ttu-id="c0358-124">Weitere Informationen finden Sie unter [lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="c0358-124">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0358-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0358-125">See also</span></span>

- [<span data-ttu-id="c0358-126">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="c0358-126">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="c0358-127">Gewusst wie: Erstellen einer Liste von Elementen</span><span class="sxs-lookup"><span data-stu-id="c0358-127">How to: Create a List of Items</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
- [<span data-ttu-id="c0358-128">Objektinitialisierer: Benannte und anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="c0358-128">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="c0358-129">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="c0358-129">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
