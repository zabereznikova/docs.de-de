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
ms.openlocfilehash: 20a33478f622fca6d3183772f53dcb3e72f79409
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266884"
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="a0960-102">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a0960-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="a0960-103">Wenn zwei Programmierelemente denselben Namen haben, kann eines von ihnen das andere ausblenden oder *schatten.*</span><span class="sxs-lookup"><span data-stu-id="a0960-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="a0960-104">In einer solchen Situation steht das schattierte Element nicht als Referenz zur Verfügung; Wenn der Code stattdessen den Elementnamen verwendet, löst der Visual Basic-Compiler ihn in das Schattenelement auf.</span><span class="sxs-lookup"><span data-stu-id="a0960-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the Visual Basic compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="a0960-105">Zweck</span><span class="sxs-lookup"><span data-stu-id="a0960-105">Purpose</span></span>  
 <span data-ttu-id="a0960-106">Der Hauptzweck des Shadowings besteht darin, die Definition Ihrer Klassenmitglieder zu schützen.</span><span class="sxs-lookup"><span data-stu-id="a0960-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="a0960-107">Die Basisklasse kann eine Änderung durchlaufen, die ein Element mit demselben Namen wie das bereits definierte Element erstellt.</span><span class="sxs-lookup"><span data-stu-id="a0960-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="a0960-108">In diesem Fall `Shadows` erzwingt der Modifikator Verweise über Ihre Klasse, die auf das von Ihnen definierte Element und nicht auf das neue Basisklassenelement aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="a0960-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="a0960-109">Arten von Schatten</span><span class="sxs-lookup"><span data-stu-id="a0960-109">Types of Shadowing</span></span>  
 <span data-ttu-id="a0960-110">Ein Element kann ein anderes Element auf zwei verschiedene Arten überschatten.</span><span class="sxs-lookup"><span data-stu-id="a0960-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="a0960-111">Das Schattenelement kann innerhalb einer Subregion der Region deklariert werden, die das Schattenelement enthält. *through scope*</span><span class="sxs-lookup"><span data-stu-id="a0960-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="a0960-112">Oder eine Ableitungsklasse kann einen Member einer Basisklasse neu definieren, in diesem Fall erfolgt die Schattenung *durch Vererbung*.</span><span class="sxs-lookup"><span data-stu-id="a0960-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="a0960-113">Shadowing durch den Scope</span><span class="sxs-lookup"><span data-stu-id="a0960-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="a0960-114">Programmierelemente im gleichen Modul, derselben Klasse oder Struktur können denselben Namen, aber einen unterschiedlichen Bereich haben.</span><span class="sxs-lookup"><span data-stu-id="a0960-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="a0960-115">Wenn zwei Elemente auf diese Weise deklariert werden und der Code auf den Namen verweist, den sie gemeinsam verwenden, überschattet das Element mit dem engeren Bereich das andere Element (der Blockbereich ist das engste).</span><span class="sxs-lookup"><span data-stu-id="a0960-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="a0960-116">Beispielsweise kann ein Modul `Public` eine `temp`Variable mit dem Namen definieren, und eine `temp`Prozedur innerhalb des Moduls kann eine lokale Variable mit dem Namen deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a0960-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="a0960-117">Verweise `temp` auf innerhalb der Prozedur greifen auf `temp` die lokale Variable `Public` zu, während Verweise von außerhalb der Prozedur auf die Variable zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a0960-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="a0960-118">In diesem Fall überschattet `temp` die Prozedurvariable die Modulvariable `temp`.</span><span class="sxs-lookup"><span data-stu-id="a0960-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="a0960-119">Die folgende Abbildung zeigt zwei `temp`Variablen, beide mit dem Namen .</span><span class="sxs-lookup"><span data-stu-id="a0960-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="a0960-120">Die lokale `temp` Variable überschattet `temp` die Membervariable, `p`wenn von einer eigenen Prozedur aus darauf zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="a0960-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="a0960-121">Das `MyClass` Schlüsselwort umgeht jedoch die Schattenung und greift auf die Membervariable zu.</span><span class="sxs-lookup"><span data-stu-id="a0960-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 ![Grafik, die das Schattenn durch den Bereich zeigt.](./media/shadowing/shadow-scope-diagram.gif)
  
 <span data-ttu-id="a0960-123">Ein Beispiel für das Schatieren durch den Bereich finden Sie unter [Gewusst wie: Ausblenden einer Variablen mit dem gleichen Namen wie Ihre Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span><span class="sxs-lookup"><span data-stu-id="a0960-123">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="a0960-124">Shadowing durch Vererbung</span><span class="sxs-lookup"><span data-stu-id="a0960-124">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="a0960-125">Wenn eine abgeleitete Klasse ein Programmierelement neu definiert, das von einer Basisklasse geerbt wurde, überschattet das neu definierende Element das ursprüngliche Element.</span><span class="sxs-lookup"><span data-stu-id="a0960-125">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="a0960-126">Sie können jeden Typ von deklarierten Elementen oder einen Satz überladener Elemente mit jedem anderen Typ überschatten.</span><span class="sxs-lookup"><span data-stu-id="a0960-126">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="a0960-127">Beispielsweise kann `Integer` eine Variable `Function` eine Prozedur überschatten.</span><span class="sxs-lookup"><span data-stu-id="a0960-127">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="a0960-128">Wenn Sie eine Prozedur mit einer anderen Prozedur überschatten, können Sie eine andere Parameterliste und einen anderen Rückgabetyp verwenden.</span><span class="sxs-lookup"><span data-stu-id="a0960-128">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="a0960-129">Die folgende Abbildung zeigt `b` eine Basisklasse und eine abgeleitete Klasse, `d` die von erbt. `b`</span><span class="sxs-lookup"><span data-stu-id="a0960-129">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="a0960-130">Die Basisklasse definiert eine `proc`Prozedur mit dem Namen , und die abgeleitete Klasse überschattet sie mit einer anderen Prozedur mit demselben Namen.</span><span class="sxs-lookup"><span data-stu-id="a0960-130">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="a0960-131">Die `Call` erste Anweisung greift `proc` auf die Schattenung in der abgeleiteten Klasse zu.</span><span class="sxs-lookup"><span data-stu-id="a0960-131">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="a0960-132">Das `MyBase` Schlüsselwort umgeht jedoch die Schattenung und greift auf die schattierte Prozedur in der Basisklasse zu.</span><span class="sxs-lookup"><span data-stu-id="a0960-132">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 ![Grafisches Diagramm des Shadowings durch Vererbung](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 <span data-ttu-id="a0960-134">Ein Beispiel für das Schattenn durch Vererbung finden Sie unter [Gewusst wie: Ausblenden einer Variablen mit dem gleichen Namen wie Ihrer Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) und How [to: Hide an Erbvariable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span><span class="sxs-lookup"><span data-stu-id="a0960-134">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="a0960-135">Schatten- und Zugriffsebene</span><span class="sxs-lookup"><span data-stu-id="a0960-135">Shadowing and Access Level</span></span>  
 <span data-ttu-id="a0960-136">Auf das Shadowing-Element kann nicht immer über den Code mithilfe der abgeleiteten Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="a0960-136">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="a0960-137">Sie kann z. `Private`B. deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="a0960-137">For example, it might be declared `Private`.</span></span> <span data-ttu-id="a0960-138">In einem solchen Fall wird das Shadowing besiegt, und der Compiler löst jeden Verweis auf dasselbe Element auf, das er hätte, wenn es kein Shadowing gegeben hätte.</span><span class="sxs-lookup"><span data-stu-id="a0960-138">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="a0960-139">Dieses Element ist das zugängliche Element, das am wenigsten ableitungsal von der Schattenklasse zurückgeht.</span><span class="sxs-lookup"><span data-stu-id="a0960-139">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="a0960-140">Wenn es sich bei dem schattierten Element um eine Prozedur handelt, erfolgt die Auflösung für die am nächsten zugängliche Version mit demselben Namen, derselben Parameterliste und demselben Rückgabetyp.</span><span class="sxs-lookup"><span data-stu-id="a0960-140">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="a0960-141">Das folgende Beispiel zeigt eine Vererbungshierarchie von drei Klassen.</span><span class="sxs-lookup"><span data-stu-id="a0960-141">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="a0960-142">Jede Klasse definiert `Sub` `display`eine Prozedur , und `display` jede abgeleitete Klasse überschattet die Prozedur in ihrer Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="a0960-142">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
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
  
 <span data-ttu-id="a0960-143">Im vorherigen Beispiel schatten `secondClass` die `display` abgeleiteten Klassen mit einer `Private` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="a0960-143">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="a0960-144">Wenn `callDisplay` das `display` `secondClass`Modul einruft, `secondClass` befindet sich der `display` aufrufende Code außerhalb und kann daher nicht auf die private Prozedur zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a0960-144">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="a0960-145">Shadowing wird besiegt, und der Compiler löst `display` den Verweis auf die Basisklassenprozedur auf.</span><span class="sxs-lookup"><span data-stu-id="a0960-145">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="a0960-146">Die weitere abgeleitete `thirdClass` `display` Klasse `Public`deklariert jedoch `callDisplay` als , sodass der Code in darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="a0960-146">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="a0960-147">Schatten und Überschreiben</span><span class="sxs-lookup"><span data-stu-id="a0960-147">Shadowing and Overriding</span></span>  
 <span data-ttu-id="a0960-148">Verwechseln Sie Schattennicht mit Überschreiben.</span><span class="sxs-lookup"><span data-stu-id="a0960-148">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="a0960-149">Beide werden verwendet, wenn eine abgeleitete Klasse von einer Basisklasse erbt, und beide definieren ein deklariertes Element mit einem anderen neu.</span><span class="sxs-lookup"><span data-stu-id="a0960-149">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="a0960-150">Aber es gibt erhebliche Unterschiede zwischen den beiden.</span><span class="sxs-lookup"><span data-stu-id="a0960-150">But there are significant differences between the two.</span></span> <span data-ttu-id="a0960-151">Einen Vergleich finden Sie unter [Unterschiede zwischen Shadowing und Überschreiben](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span><span class="sxs-lookup"><span data-stu-id="a0960-151">For a comparison, see [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="a0960-152">Schatten und Überladen</span><span class="sxs-lookup"><span data-stu-id="a0960-152">Shadowing and Overloading</span></span>  
 <span data-ttu-id="a0960-153">Wenn Sie dasselbe Basisklassenelement mit mehr als einem Element in der abgeleiteten Klasse überschatten, werden die Schattenelemente zu überladenen Versionen dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="a0960-153">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="a0960-154">Weitere Informationen finden Sie unter [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="a0960-154">For more information, see [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="a0960-155">Zugreifen auf ein schattenhaftes Element</span><span class="sxs-lookup"><span data-stu-id="a0960-155">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="a0960-156">Wenn Sie auf ein Element aus einer abgeleiteten Klasse zugreifen, tun Sie dies normalerweise `Me` über die aktuelle Instanz dieser abgeleiteten Klasse, indem Sie den Elementnamen mit dem Schlüsselwort qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="a0960-156">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="a0960-157">Wenn die abgeleitete Klasse das Element in der Basisklasse überschattet, können `MyBase` Sie auf das Basisklassenelement zugreifen, indem Sie es mit dem Schlüsselwort qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="a0960-157">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="a0960-158">Ein Beispiel für den Zugriff auf ein schattiertes Element finden Sie unter [Gewusst wie: Zugriff auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird.](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)</span><span class="sxs-lookup"><span data-stu-id="a0960-158">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="a0960-159">Deklaration der Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="a0960-159">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="a0960-160">Wie Sie die Objektvariable erstellen, kann sich auch darauf auswirken, ob die abgeleitete Klasse auf ein Schattenelement oder das schattenhafte Element zugreift.</span><span class="sxs-lookup"><span data-stu-id="a0960-160">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="a0960-161">Im folgenden Beispiel werden zwei Objekte aus einer abgeleiteten Klasse erstellt, aber ein Objekt wird als Basisklasse und das andere als abgeleitete Klasse deklariert.</span><span class="sxs-lookup"><span data-stu-id="a0960-161">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
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
  
 <span data-ttu-id="a0960-162">Im vorherigen Beispiel wird `basObj` die Variable als Basisklasse deklariert.</span><span class="sxs-lookup"><span data-stu-id="a0960-162">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="a0960-163">Das Zuweisen `dervCls` eines Objekts zu ihm stellt eine Erweiterungskonvertierung dar und ist daher gültig.</span><span class="sxs-lookup"><span data-stu-id="a0960-163">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="a0960-164">Die Basisklasse kann jedoch nicht auf die `z` Schattenversion der Variablen in `basObj.z` der abgeleiteten Klasse zugreifen, sodass der Compiler in den ursprünglichen Basisklassenwert aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="a0960-164">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0960-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a0960-165">See also</span></span>

- [<span data-ttu-id="a0960-166">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="a0960-166">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="a0960-167">Gültigkeitsbereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a0960-167">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="a0960-168">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="a0960-168">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="a0960-169">Shadows</span><span class="sxs-lookup"><span data-stu-id="a0960-169">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="a0960-170">Außerkraftsetzungen</span><span class="sxs-lookup"><span data-stu-id="a0960-170">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="a0960-171">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="a0960-171">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="a0960-172">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="a0960-172">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
