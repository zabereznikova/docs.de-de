---
title: Shadowing
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], shadowing
- overriding, and shadowing
- shadowing
- duplicate names [Visual Basic]
- shadowing, by inheritance
- declared elements [Visual Basic], referencing
- shadowing, by scope
- declared elements [Visual Basic], hiding
- naming conflicts, shadowing
- declared elements [Visual Basic], shadowing
- shadowing, and overriding
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic], about
- objects [Visual Basic], names
- names [Visual Basic], shadowing
ms.assetid: 54bb4c25-12c4-4181-b4a0-93546053964e
ms.openlocfilehash: 034b5c0ecf3be6e77048fb7318e931801575f07a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345327"
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="b7762-102">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b7762-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="b7762-103">Wenn zwei Programmier Elemente denselben Namen haben, kann einer von Ihnen einen ausblenden oder einen *Schatten*der anderen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7762-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="b7762-104">In einer solchen Situation ist das Shadowing-Element nicht für den Verweis verfügbar. Wenn der Code den Elementnamen verwendet, wird er stattdessen vom Visual Basic Compiler in das Shadowing-Element aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="b7762-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the Visual Basic compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="b7762-105">Zweck</span><span class="sxs-lookup"><span data-stu-id="b7762-105">Purpose</span></span>  
 <span data-ttu-id="b7762-106">Der Hauptzweck von shadowingbesteht darin, die Definition der Klassenmember zu schützen.</span><span class="sxs-lookup"><span data-stu-id="b7762-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="b7762-107">Die Basisklasse kann einer Änderung unterzogen werden, die ein Element mit dem gleichen Namen erstellt, den Sie bereits definiert haben.</span><span class="sxs-lookup"><span data-stu-id="b7762-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="b7762-108">In diesem Fall erzwingt der `Shadows` Modifizierer, dass Verweise durch Ihre Klasse in den von Ihnen definierten Member aufgelöst werden, anstatt das neue Basisklassen Element zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7762-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="b7762-109">Typen von Shadowings</span><span class="sxs-lookup"><span data-stu-id="b7762-109">Types of Shadowing</span></span>  
 <span data-ttu-id="b7762-110">Ein Element kann auf zwei verschiedene Arten einen Schatten für ein anderes Element haben.</span><span class="sxs-lookup"><span data-stu-id="b7762-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="b7762-111">Das Shadowing-Element kann in einem Teilbereich des Bereichs deklariert werden, der das schattiert-Element enthält. in diesem Fall wird der Shadowing *über den Bereich*erreicht.</span><span class="sxs-lookup"><span data-stu-id="b7762-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="b7762-112">Oder eine abgeleitete Klasse kann einen Member einer Basisklasse neu definieren. in diesem Fall erfolgt die über schattung *durch Vererbung*.</span><span class="sxs-lookup"><span data-stu-id="b7762-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="b7762-113">Shadothrough im Gültigkeitsbereich</span><span class="sxs-lookup"><span data-stu-id="b7762-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="b7762-114">Es ist möglich, dass Elemente im gleichen Modul, in derselben Klasse oder in derselben Struktur denselben Namen, aber unterschiedlichen Gültigkeitsbereich aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b7762-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="b7762-115">Wenn zwei-Elemente auf diese Weise deklariert werden und sich der Code auf den Namen bezieht, den Sie freigeben, wird das-Element mit dem engeren Bereich mit dem anderen-Element Shadowing (Block Bereich ist die engste).</span><span class="sxs-lookup"><span data-stu-id="b7762-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="b7762-116">Ein Modul kann z. b. eine `Public` Variable mit dem Namen `temp`definieren, und eine Prozedur innerhalb des Moduls kann eine lokale Variable mit dem Namen `temp`deklarieren.</span><span class="sxs-lookup"><span data-stu-id="b7762-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="b7762-117">Verweise auf `temp` innerhalb der Prozedur greifen auf die lokale Variable zu, während Verweise auf `temp` von außerhalb der Prozedur auf die `Public` Variable zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b7762-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="b7762-118">In diesem Fall `temp` die Prozedur Variable die Modul Variable `temp`.</span><span class="sxs-lookup"><span data-stu-id="b7762-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="b7762-119">Die folgende Abbildung zeigt zwei Variablen, die beide den Namen `temp`haben.</span><span class="sxs-lookup"><span data-stu-id="b7762-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="b7762-120">Die lokale Variable `temp` Schatten der Element Variablen `temp`, wenn der Zugriff innerhalb der eigenen Prozedur `p`erfolgt.</span><span class="sxs-lookup"><span data-stu-id="b7762-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="b7762-121">Allerdings umgeht das `MyClass`-Schlüsselwort den shadodown und greift auf die Member-Variable zu.</span><span class="sxs-lookup"><span data-stu-id="b7762-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 ![Grafik, die shadothrough durch den Gültigkeitsbereich anzeigt.](./media/shadowing/shadow-scope-diagram.gif)
  
 <span data-ttu-id="b7762-123">Ein Beispiel für die über schattung durch den Bereich finden Sie unter Gewusst [wie: Ausblenden einer Variablen mit dem gleichen Namen wie die Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span><span class="sxs-lookup"><span data-stu-id="b7762-123">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="b7762-124">Über schattung durch Vererbung</span><span class="sxs-lookup"><span data-stu-id="b7762-124">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="b7762-125">Wenn eine abgeleitete Klasse ein Programmier Element neu definiert, das von einer Basisklasse geerbt wurde, gibt das neu definierende Element einen Schatten für das ursprüngliche Element aus.</span><span class="sxs-lookup"><span data-stu-id="b7762-125">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="b7762-126">Sie können einen beliebigen Typ eines deklarierten Elements oder einen Satz überladener Elemente mit einem beliebigen anderen Typ schattieren.</span><span class="sxs-lookup"><span data-stu-id="b7762-126">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="b7762-127">Beispielsweise kann eine `Integer` Variable eine `Function` Prozedur schattieren.</span><span class="sxs-lookup"><span data-stu-id="b7762-127">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="b7762-128">Wenn Sie eine Prozedur mit einer anderen Prozedur als Schatten verwenden, können Sie eine andere Parameterliste und einen anderen Rückgabetyp verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7762-128">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="b7762-129">Die folgende Abbildung zeigt eine Basisklasse `b` und eine abgeleitete Klasse `d`, die von `b`erbt.</span><span class="sxs-lookup"><span data-stu-id="b7762-129">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="b7762-130">Die-Basisklasse definiert eine Prozedur mit dem Namen `proc`, und die abgeleitete Klasse überschattet Sie mit einer anderen Prozedur desselben Namens.</span><span class="sxs-lookup"><span data-stu-id="b7762-130">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="b7762-131">Die erste `Call` Anweisung greift auf die Shadowing`proc` in der abgeleiteten Klasse zu.</span><span class="sxs-lookup"><span data-stu-id="b7762-131">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="b7762-132">Allerdings umgeht das `MyBase`-Schlüsselwort den Shadowing und greift auf die Shadowing-Prozedur in der-Basisklasse zu.</span><span class="sxs-lookup"><span data-stu-id="b7762-132">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 ![Grafisches Diagramm des Shadowings durch Vererbung](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 <span data-ttu-id="b7762-134">Ein Beispiel für das Durchsuchen von Vererbung durch die Vererbung finden Sie unter Gewusst [wie: Ausblenden einer Variablen mit dem gleichen Namen wie die Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) und Gewusst [wie: Ausblenden einer geerbten Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span><span class="sxs-lookup"><span data-stu-id="b7762-134">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="b7762-135">Shadowingund Zugriffsebene</span><span class="sxs-lookup"><span data-stu-id="b7762-135">Shadowing and Access Level</span></span>  
 <span data-ttu-id="b7762-136">Auf das Shadowingelement kann nicht immer über den Code zugegriffen werden, wenn die abgeleitete Klasse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b7762-136">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="b7762-137">Beispielsweise könnte Sie als `Private`deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="b7762-137">For example, it might be declared `Private`.</span></span> <span data-ttu-id="b7762-138">In einem solchen Fall wird shadodown unterbunden, und der Compiler löst alle Verweise auf dasselbe Element auf, das er hätte, wenn kein shadodown vorhanden wäre.</span><span class="sxs-lookup"><span data-stu-id="b7762-138">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="b7762-139">Dieses Element ist das barrierefreie Element, bei dem die wenigsten abderivations Schritte von der Shadowingklasse rückwärts ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b7762-139">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="b7762-140">Wenn das Shadowing Element eine Prozedur ist, wird die Auflösung an die nächstgelegene Barrierefreie Version mit dem gleichen Namen, der gleichen Parameterliste und dem gleichen Rückgabetyp durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="b7762-140">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="b7762-141">Das folgende Beispiel zeigt eine Vererbungs Hierarchie von drei Klassen.</span><span class="sxs-lookup"><span data-stu-id="b7762-141">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="b7762-142">Jede Klasse definiert eine `Sub` Prozedur `display`, und jede abgeleitete Klasse überschattet die `display` Prozedur in ihrer Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="b7762-142">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
```vb  
Public Class firstClass  
    Public Sub display()  
        MsgBox("This is firstClass")  
    End Sub  
End Class  
Public Class secondClass  
    Inherits firstClass  
    Private Shadows Sub display()  
        MsgBox("This is secondClass")  
    End Sub  
End Class  
Public Class thirdClass  
    Inherits secondClass  
    Public Shadows Sub display()  
        MsgBox("This is thirdClass")  
    End Sub  
End Class  
Module callDisplay  
    Dim first As New firstClass  
    Dim second As New secondClass  
    Dim third As New thirdClass  
    Public Sub callDisplayProcedures()  
        ' The following statement displays "This is firstClass".  
        first.display()  
        ' The following statement displays "This is firstClass".  
        second.display()  
        ' The following statement displays "This is thirdClass".  
        third.display()  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="b7762-143">Im vorherigen Beispiel `secondClass` die abgeleitete Klasse Shadowing `display` mit einer `Private` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="b7762-143">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="b7762-144">Wenn die Modul `callDisplay` `display` in `secondClass`aufruft, befindet sich der Aufruf Code außerhalb `secondClass` und kann daher nicht auf die private `display` Prozedur zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b7762-144">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="b7762-145">Shadowings wird untersucht, und der Compiler löst den Verweis auf die Basisklasse `display` Prozedur auf.</span><span class="sxs-lookup"><span data-stu-id="b7762-145">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="b7762-146">Die weitere abgeleitete Klasse `thirdClass` jedoch `display` als `Public`deklariert, sodass der Code in `callDisplay` darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="b7762-146">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="b7762-147">Shadodown und überschreiben</span><span class="sxs-lookup"><span data-stu-id="b7762-147">Shadowing and Overriding</span></span>  
 <span data-ttu-id="b7762-148">Shadodown kann nicht mit Überschreiben verwechselt werden.</span><span class="sxs-lookup"><span data-stu-id="b7762-148">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="b7762-149">Beide werden verwendet, wenn eine abgeleitete Klasse von einer Basisklasse erbt, und beide definieren ein deklariertes Element mit einem anderen.</span><span class="sxs-lookup"><span data-stu-id="b7762-149">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="b7762-150">Es gibt jedoch bedeutende Unterschiede zwischen den beiden.</span><span class="sxs-lookup"><span data-stu-id="b7762-150">But there are significant differences between the two.</span></span> <span data-ttu-id="b7762-151">Einen Vergleich finden Sie [unter Unterschiede zwischen shadodown und](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)überschreiben.</span><span class="sxs-lookup"><span data-stu-id="b7762-151">For a comparison, see [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="b7762-152">Shadoading und überladen</span><span class="sxs-lookup"><span data-stu-id="b7762-152">Shadowing and Overloading</span></span>  
 <span data-ttu-id="b7762-153">Wenn Sie das gleiche Basisklassen Element mit mehr als einem Element in der abgeleiteten Klasse überschatten, werden die Shadowing-Elemente überladene Versionen dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="b7762-153">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="b7762-154">Weitere Informationen finden Sie unter [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="b7762-154">For more information, see [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="b7762-155">Zugreifen auf ein Shadowing Element</span><span class="sxs-lookup"><span data-stu-id="b7762-155">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="b7762-156">Wenn Sie auf ein Element aus einer abgeleiteten Klasse zugreifen, verwenden Sie normalerweise die aktuelle Instanz der abgeleiteten Klasse, indem Sie den Elementnamen mit dem `Me`-Schlüsselwort qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="b7762-156">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="b7762-157">Wenn die abgeleitete Klasse ein Shadowing für das Element in der Basisklasse durchführt, können Sie auf das Basisklassen Element zugreifen, indem Sie es mit dem Schlüsselwort `MyBase` qualifizieren</span><span class="sxs-lookup"><span data-stu-id="b7762-157">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="b7762-158">Ein Beispiel für den Zugriff auf ein Shadowing Element finden Sie unter Gewusst [wie: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)wird.</span><span class="sxs-lookup"><span data-stu-id="b7762-158">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="b7762-159">Deklaration der Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="b7762-159">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="b7762-160">Wie Sie die Objekt Variable erstellen, kann sich auch darauf auswirken, ob die abgeleitete Klasse auf ein Shadowing-Element oder das Shadowing-Element zugreift</span><span class="sxs-lookup"><span data-stu-id="b7762-160">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="b7762-161">Im folgenden Beispiel werden zwei Objekte aus einer abgeleiteten Klasse erstellt, aber ein Objekt wird als Basisklasse und die andere als abgeleitete Klasse deklariert.</span><span class="sxs-lookup"><span data-stu-id="b7762-161">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
```vb  
Public Class baseCls  
    ' The following statement declares the element that is to be shadowed.  
    Public z As Integer = 100  
End Class  
Public Class dervCls  
    Inherits baseCls  
    ' The following statement declares the shadowing element.  
    Public Shadows z As String = "*"  
End Class  
Public Class useClasses  
    ' The following statement creates the object declared as the base class.  
    Dim basObj As baseCls = New dervCls()  
    ' Note that dervCls widens to its base class baseCls.  
    ' The following statement creates the object declared as the derived class.  
    Dim derObj As dervCls = New dervCls()  
    Public Sub showZ()   
    ' The following statement outputs 100 (the shadowed element).  
        MsgBox("Accessed through base class: " & basObj.z)  
    ' The following statement outputs "*" (the shadowing element).  
        MsgBox("Accessed through derived class: " & derObj.z)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="b7762-162">Im vorherigen Beispiel wird die Variable `basObj` als Basisklasse deklariert.</span><span class="sxs-lookup"><span data-stu-id="b7762-162">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="b7762-163">Das Zuweisen eines `dervCls` Objekts zu diesem Objekt stellt eine erweiternde Konvertierung dar und ist daher gültig.</span><span class="sxs-lookup"><span data-stu-id="b7762-163">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="b7762-164">Die Basisklasse kann jedoch nicht auf die Shadowingversion der Variablen `z` in der abgeleiteten Klasse zugreifen, sodass der Compiler `basObj.z` in den ursprünglichen Basisklassen Wert auflöst.</span><span class="sxs-lookup"><span data-stu-id="b7762-164">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7762-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7762-165">See also</span></span>

- [<span data-ttu-id="b7762-166">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="b7762-166">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="b7762-167">Bereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b7762-167">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="b7762-168">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="b7762-168">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="b7762-169">Shadows</span><span class="sxs-lookup"><span data-stu-id="b7762-169">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="b7762-170">Overrides</span><span class="sxs-lookup"><span data-stu-id="b7762-170">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="b7762-171">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="b7762-171">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="b7762-172">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="b7762-172">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
