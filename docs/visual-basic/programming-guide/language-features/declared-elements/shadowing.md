---
title: Shadowing in Visual Basic
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
ms.openlocfilehash: 15c7112f7e318542859162655c78e19558178e5a
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58411004"
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="123f2-102">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="123f2-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="123f2-103">Wenn zwei Programmierelemente mit demselben Namen gemeinsam nutzen, eine davon kann auszublenden, oder *Schatten*, der andere Controller.</span><span class="sxs-lookup"><span data-stu-id="123f2-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="123f2-104">In diesem Fall ist das Shadowing-Element nicht als Referenz verfügbar; Stattdessen löst, wenn Ihr Code den Elementnamen verwendet, die Visual Basic-Compiler es auf das shadowing-Element.</span><span class="sxs-lookup"><span data-stu-id="123f2-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the Visual Basic compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="123f2-105">Zweck</span><span class="sxs-lookup"><span data-stu-id="123f2-105">Purpose</span></span>  
 <span data-ttu-id="123f2-106">Der Hauptzweck des shadowings ist die Definition von Klassenmembern zu schützen.</span><span class="sxs-lookup"><span data-stu-id="123f2-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="123f2-107">Die Basisklasse kann eine Änderung durchlaufen, die ein Element mit dem gleichen Namen wie eine erstellt wird, die Sie bereits definiert haben.</span><span class="sxs-lookup"><span data-stu-id="123f2-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="123f2-108">In diesem Fall die `Shadows` Modifizierer erzwingt, dass Verweise über die Klasse, um der Member aufgelöst werden Sie definiert, statt auf das neue Element der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="123f2-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="123f2-109">Typen des Shadowings</span><span class="sxs-lookup"><span data-stu-id="123f2-109">Types of Shadowing</span></span>  
 <span data-ttu-id="123f2-110">Ein Element kann ein anderes Element auf zwei unterschiedliche Arten spiegeln.</span><span class="sxs-lookup"><span data-stu-id="123f2-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="123f2-111">Das shadowing-Element deklariert werden kann, innerhalb eines Unterbereichs des Bereichs, enthält das Shadowing-Element, in dem Fall, die das shadowing erfolgt *über den Gültigkeitsbereich*.</span><span class="sxs-lookup"><span data-stu-id="123f2-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="123f2-112">Oder Sie können in eine abgeleitete Klasse ein Member einer Basisklasse, in dem Fall, die das shadowing erfolgt neu definieren *durch Vererbung*.</span><span class="sxs-lookup"><span data-stu-id="123f2-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="123f2-113">Shadowings über den Gültigkeitsbereich</span><span class="sxs-lookup"><span data-stu-id="123f2-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="123f2-114">Es ist möglich, für die Programmierung von Elementen in der gleichen-Modul, Klasse oder Struktur, um den gleichen Namen aber unterschiedlichen Gültigkeitsbereichen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="123f2-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="123f2-115">Wenn zwei Elemente auf diese Weise deklariert wurden, und der Code verweist auf den gemeinsamen Namen, spiegelt das Element mit der engeren Bereich definiert das andere Element (Blockbereich ist die geringstmögliche).</span><span class="sxs-lookup"><span data-stu-id="123f2-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="123f2-116">Ein Modul kann definieren, z. B. eine `Public` Variable mit dem Namen `temp`, und eine Prozedur innerhalb des Moduls kann eine lokale Variable, die auch mit dem Namen deklarieren `temp`.</span><span class="sxs-lookup"><span data-stu-id="123f2-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="123f2-117">Verweise auf `temp` innerhalb die Prozedur Zugriff auf die lokale Variable, während Verweise auf `temp` von außerhalb der Prozedur greifen auf die `Public` Variable.</span><span class="sxs-lookup"><span data-stu-id="123f2-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="123f2-118">In diesem Fall die Prozedurvariable `temp` führt Shadowing für die Modulvariable `temp`.</span><span class="sxs-lookup"><span data-stu-id="123f2-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="123f2-119">Die folgende Abbildung zeigt zwei Variablen, die sowohl für benannte `temp`.</span><span class="sxs-lookup"><span data-stu-id="123f2-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="123f2-120">Die lokale Variable `temp` führt Shadowing für die Membervariable `temp` Wenn der Zugriff innerhalb ihrer eigenen Prozedur `p`.</span><span class="sxs-lookup"><span data-stu-id="123f2-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="123f2-121">Allerdings die `MyClass` Schlüsselwort umgeht das shadowing und greift auf die Membervariable.</span><span class="sxs-lookup"><span data-stu-id="123f2-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 ![Grafik, die zeigt shadowings über den Gültigkeitsbereich.](./media/shadowing/shadow-scope-diagram.gif)
  
 <span data-ttu-id="123f2-123">Ein Beispiel des shadowings über den Bereich finden Sie unter [Vorgehensweise: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span><span class="sxs-lookup"><span data-stu-id="123f2-123">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="123f2-124">Shadowings durch Vererbung</span><span class="sxs-lookup"><span data-stu-id="123f2-124">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="123f2-125">Wenn eine abgeleitete Klasse neu definiert ein Programmierelement, das von einer Basisklasse geerbt wird, führt Shadowing für das ursprüngliche Element das redefine-Element.</span><span class="sxs-lookup"><span data-stu-id="123f2-125">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="123f2-126">Ein Typ des deklarierten Elements oder Satz überladener Elemente kann mit keinem anderen Typ Shadowing durchführen.</span><span class="sxs-lookup"><span data-stu-id="123f2-126">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="123f2-127">Z. B. eine `Integer` Variablen kann Shadowing für eine `Function` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="123f2-127">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="123f2-128">Wenn Sie eine Prozedur mit einer anderen Prozedur spiegeln, können Sie eine andere Parameterliste und einen anderen Rückgabetyp.</span><span class="sxs-lookup"><span data-stu-id="123f2-128">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="123f2-129">Die folgende Abbildung zeigt eine Basisklasse `b` und eine abgeleitete Klasse `d` von erbt `b`.</span><span class="sxs-lookup"><span data-stu-id="123f2-129">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="123f2-130">Die Basisklasse der Klasse definiert eine Prozedur namens `proc`, und die abgeleitete Klasse mit einer anderen Prozedur mit demselben Namen Shadowing für Sie.</span><span class="sxs-lookup"><span data-stu-id="123f2-130">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="123f2-131">Die erste `Call` Anweisung greift auf das shadowing `proc` in der abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="123f2-131">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="123f2-132">Allerdings die `MyBase` Schlüsselwort umgeht das shadowing und greift auf die Prozedur Shadowing durchgeführt wurde, in der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="123f2-132">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 ![Grafisches Diagramm des Shadowings durch Vererbung](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 <span data-ttu-id="123f2-134">Ein Beispiel des shadowings durch Vererbung, finden Sie unter [Vorgehensweise: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) und [Vorgehensweise: Ausblenden einer geerbten Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span><span class="sxs-lookup"><span data-stu-id="123f2-134">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="123f2-135">Shadowing und Zugriffsebene</span><span class="sxs-lookup"><span data-stu-id="123f2-135">Shadowing and Access Level</span></span>  
 <span data-ttu-id="123f2-136">Das shadowing-Element ist nicht immer aus dem Code, mit der abgeleiteten Klasse zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="123f2-136">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="123f2-137">Zum Beispiel kann deklariert werden `Private`.</span><span class="sxs-lookup"><span data-stu-id="123f2-137">For example, it might be declared `Private`.</span></span> <span data-ttu-id="123f2-138">In diesem Fall erfolgt kein shadowing und der Compiler löst alle Verweise auf dasselbe Element mussten gab es kein shadowing.</span><span class="sxs-lookup"><span data-stu-id="123f2-138">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="123f2-139">Dieses Element ist das barrierefreie Element gilt Ableitungsschritte Schritte rückwärts von den shadowing-Klasse.</span><span class="sxs-lookup"><span data-stu-id="123f2-139">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="123f2-140">Ist das Shadowing-Element eine Prozedur, die Lösung besteht darin, die die nächste Version mit dem gleichen Namen, die Parameterliste, und den Rückgabetyp.</span><span class="sxs-lookup"><span data-stu-id="123f2-140">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="123f2-141">Das folgende Beispiel zeigt eine Vererbungshierarchie von drei Klassen.</span><span class="sxs-lookup"><span data-stu-id="123f2-141">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="123f2-142">Jede Klasse definiert eine `Sub` Prozedur `display`, und jede abgeleitete Klasse Schatten der `display` Prozedur in der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="123f2-142">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
```  
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
  
 <span data-ttu-id="123f2-143">Im vorherigen Beispiel, die abgeleitete Klasse `secondClass` Shadows `display` mit einem `Private` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="123f2-143">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="123f2-144">Beim Modul `callDisplay` Aufrufe `display` in `secondClass`, befindet sich außerhalb der aufrufende Code `secondClass` und daher nicht den privaten verfügbar `display` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="123f2-144">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="123f2-145">Es erfolgt kein Shadowing und der Compiler löst den Verweis auf die Basisklasse `display` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="123f2-145">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="123f2-146">Aber die weitere abgeleitete Klasse `thirdClass` deklariert `display` als `Public`, sodass der Code in `callDisplay` darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="123f2-146">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="123f2-147">Shadowing und überschreiben</span><span class="sxs-lookup"><span data-stu-id="123f2-147">Shadowing and Overriding</span></span>  
 <span data-ttu-id="123f2-148">Ist nicht zu verwechseln shadowing und überschreiben.</span><span class="sxs-lookup"><span data-stu-id="123f2-148">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="123f2-149">Beide werden verwendet, wenn eine abgeleitete Klasse, die von einer Basisklasse erbt, und beide einen deklariertes Element mit einem anderen neu definieren.</span><span class="sxs-lookup"><span data-stu-id="123f2-149">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="123f2-150">Es gibt jedoch bedeutende Unterschiede zwischen den beiden.</span><span class="sxs-lookup"><span data-stu-id="123f2-150">But there are significant differences between the two.</span></span> <span data-ttu-id="123f2-151">Einen Vergleich finden Sie unter [Unterschiede zwischen Shadowing und überschreiben](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span><span class="sxs-lookup"><span data-stu-id="123f2-151">For a comparison, see [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="123f2-152">Shadowing und Überladung</span><span class="sxs-lookup"><span data-stu-id="123f2-152">Shadowing and Overloading</span></span>  
 <span data-ttu-id="123f2-153">Wenn Sie das gleiche Element der Basisklasse mit mehr als ein Element in der abgeleiteten Klasse spiegeln, werden die shadowing Elemente überladenen Versionen dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="123f2-153">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="123f2-154">Weitere Informationen finden Sie unter [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="123f2-154">For more information, see [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="123f2-155">Zugreifen auf ein schattiertes Element</span><span class="sxs-lookup"><span data-stu-id="123f2-155">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="123f2-156">Wenn Sie ein Element aus einer abgeleiteten Klasse zugreifen, erfolgt dies gewöhnlich über die aktuelle Instanz der abgeleiteten Klasse und durch die Qualifizierung der Elementname mit dem `Me` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="123f2-156">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="123f2-157">Wenn die abgeleitete Klasse das Element in der Basisklasse überschattet, können Sie das Element der Basisklasse aufrufen, durch die Qualifizierung mit dem `MyBase` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="123f2-157">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="123f2-158">Ein Beispiel für den Zugriff auf ein schattiertes Element finden Sie unter [Vorgehensweise: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="123f2-158">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="123f2-159">Deklaration der Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="123f2-159">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="123f2-160">Erstellen Sie die Objektvariable kann auch beeinflussen, ob die abgeleitete Klasse ein shadowing-Element oder das gespiegelte Element zugreift.</span><span class="sxs-lookup"><span data-stu-id="123f2-160">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="123f2-161">Das folgende Beispiel erstellt zwei Objekte aus einer abgeleiteten Klasse, aber ein einzelnes Objekt ist als die Basisklasse und die andere als die abgeleitete Klasse deklariert.</span><span class="sxs-lookup"><span data-stu-id="123f2-161">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
```  
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
  
 <span data-ttu-id="123f2-162">Im vorherigen Beispiel, die Variable `basObj` ist als die Basisklasse der Klasse deklariert.</span><span class="sxs-lookup"><span data-stu-id="123f2-162">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="123f2-163">Zuweisen einer `dervCls` Objekt eine erweiternde Konvertierung und ist daher gültig.</span><span class="sxs-lookup"><span data-stu-id="123f2-163">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="123f2-164">Jedoch nicht die Basisklasse die shadowing-Version der Variablen zugreifen `z` in der abgeleiteten Klasse, sodass der Compiler löst `basObj.z` auf den ursprünglichen Wert der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="123f2-164">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="123f2-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="123f2-165">See also</span></span>
- [<span data-ttu-id="123f2-166">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="123f2-166">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="123f2-167">Gültigkeitsbereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="123f2-167">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="123f2-168">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="123f2-168">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="123f2-169">Shadows</span><span class="sxs-lookup"><span data-stu-id="123f2-169">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="123f2-170">Overrides</span><span class="sxs-lookup"><span data-stu-id="123f2-170">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="123f2-171">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="123f2-171">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="123f2-172">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="123f2-172">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
