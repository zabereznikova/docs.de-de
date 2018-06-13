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
ms.openlocfilehash: fde6259b67a8d963ed8c30b87c94029fb2658664
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656070"
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="04206-102">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="04206-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="04206-103">Wenn zwei Programmierelemente denselben Namen tragen, eine von ihnen kann auszublenden, oder *Schatten*, eine andere.</span><span class="sxs-lookup"><span data-stu-id="04206-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="04206-104">In einer solchen Situation ist nicht das Shadowing-Element als Referenz verfügbar; Stattdessen, wenn Ihr Code den Elementnamen verwendet wird, löst Visual Basic-Compiler es in das shadowing-Element.</span><span class="sxs-lookup"><span data-stu-id="04206-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the Visual Basic compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="04206-105">Zweck</span><span class="sxs-lookup"><span data-stu-id="04206-105">Purpose</span></span>  
 <span data-ttu-id="04206-106">Die Hauptaufgabe des shadowings ist die Definition von Klassenmembern zu schützen.</span><span class="sxs-lookup"><span data-stu-id="04206-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="04206-107">Die Basisklasse kann eine Änderung unterzogen werden, die ein Element mit dem gleichen Namen wie eine erstellt, die Sie bereits definiert haben.</span><span class="sxs-lookup"><span data-stu-id="04206-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="04206-108">In diesem Fall die `Shadows` Modifizierer erzwingt, dass Verweise über die Klasse, um auf den Member aufgelöst werden Sie definiert, statt in das neue Element der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="04206-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="04206-109">Typen von Shadowing</span><span class="sxs-lookup"><span data-stu-id="04206-109">Types of Shadowing</span></span>  
 <span data-ttu-id="04206-110">Ein Element kann ein anderes Element auf zwei unterschiedliche Arten überschatten.</span><span class="sxs-lookup"><span data-stu-id="04206-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="04206-111">Das shadowing-Element deklariert werden kann, innerhalb eines Unterbereichs des Bereichs, enthält das Shadowing-Element, in dem Fall das shadowing erfolgt *über den Gültigkeitsbereich*.</span><span class="sxs-lookup"><span data-stu-id="04206-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="04206-112">Oder Sie können in eine abgeleitete Klasse einen Member einer Basisklasse, in dem Fall das shadowing erfolgt neu definieren *durch Vererbung*.</span><span class="sxs-lookup"><span data-stu-id="04206-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="04206-113">Shadowing über den Gültigkeitsbereich</span><span class="sxs-lookup"><span data-stu-id="04206-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="04206-114">Es ist möglich, von Programmierelementen im Modul, Klasse oder Struktur, die den gleichen Namen, aber unterschiedlichen Gültigkeitsbereichen zu haben.</span><span class="sxs-lookup"><span data-stu-id="04206-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="04206-115">Wenn zwei Elemente auf diese Weise deklariert werden, und der Code verweist auf den Namen, die sie gemeinsam verwenden, führt das Element mit dem engeren Bereich Shadowing für das andere Element (Blockbereich ist die engste).</span><span class="sxs-lookup"><span data-stu-id="04206-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="04206-116">Ein Modul kann definieren, z. B. eine `Public` Variable mit dem Namen `temp`, und einer Prozedur innerhalb des Moduls deklariert eine lokale Variable namens auch `temp`.</span><span class="sxs-lookup"><span data-stu-id="04206-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="04206-117">Verweise auf `temp` innerhalb der Prozedur greifen auf die lokale Variable, während Verweise auf `temp` von außerhalb der Prozedur greifen auf die `Public` Variable.</span><span class="sxs-lookup"><span data-stu-id="04206-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="04206-118">In diesem Fall die Prozedurvariable `temp` führt Shadowing für die Modulvariable `temp`.</span><span class="sxs-lookup"><span data-stu-id="04206-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="04206-119">Die folgende Abbildung zeigt zwei Variablen, die beiden benannten `temp`.</span><span class="sxs-lookup"><span data-stu-id="04206-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="04206-120">Die lokale Variable `temp` führt Shadowing für die Membervariable `temp` bei einem Zugriff vom innerhalb ihrer eigenen Prozedur `p`.</span><span class="sxs-lookup"><span data-stu-id="04206-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="04206-121">Allerdings die `MyClass` Schlüsselwort umgeht das shadowing und greift auf die Membervariable.</span><span class="sxs-lookup"><span data-stu-id="04206-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 <span data-ttu-id="04206-122">![Grafisches Diagramm des shadowings über den Gültigkeitsbereich](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")</span><span class="sxs-lookup"><span data-stu-id="04206-122">![Graphic diagram of shadowing through scope](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")</span></span>  
<span data-ttu-id="04206-123">Shadowing über den Gültigkeitsbereich</span><span class="sxs-lookup"><span data-stu-id="04206-123">Shadowing through scope</span></span>  
  
 <span data-ttu-id="04206-124">Ein Beispiel des shadowings über den Bereich finden Sie unter [wie: Ausblenden einer Variablen mit dem gleichen Namen wie Ihre Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span><span class="sxs-lookup"><span data-stu-id="04206-124">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="04206-125">Shadowings durch Vererbung</span><span class="sxs-lookup"><span data-stu-id="04206-125">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="04206-126">Wenn ein Programmierelement, die von einer Basisklasse geerbt von eine abgeleitete Klasse neu definiert, führt Shadowing für das ursprüngliche Element das redefine-Element.</span><span class="sxs-lookup"><span data-stu-id="04206-126">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="04206-127">Sie können jede Art von deklarierter Elemente oder Satz überladener Elemente mit einem beliebigen anderen Typ vornehmen.</span><span class="sxs-lookup"><span data-stu-id="04206-127">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="04206-128">Z. B. ein `Integer` Variablen kann Shadowing für eine `Function` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="04206-128">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="04206-129">Wenn Sie eine Prozedur mit einer anderen Prozedur vornehmen, können Sie eine andere Parameterliste und einen anderen Rückgabetyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="04206-129">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="04206-130">Die folgende Abbildung zeigt eine Basisklasse `b` und eine abgeleitete Klasse `d` von erbt `b`.</span><span class="sxs-lookup"><span data-stu-id="04206-130">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="04206-131">Die Basisklasse definiert eine Prozedur namens `proc`, und die abgeleitete Klasse Shadowing mit einer anderen Prozedur mit demselben Namen.</span><span class="sxs-lookup"><span data-stu-id="04206-131">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="04206-132">Die erste `Call` Anweisung greift auf das shadowing `proc` in der abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="04206-132">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="04206-133">Allerdings die `MyBase` Schlüsselwort umgeht das shadowing und greift auf die die Prozedur in der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="04206-133">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 <span data-ttu-id="04206-134">![Grafisches Diagramm des shadowings durch Vererbung](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")</span><span class="sxs-lookup"><span data-stu-id="04206-134">![Graphic diagram of shadowing through inheritance](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")</span></span>  
<span data-ttu-id="04206-135">Shadowings durch Vererbung</span><span class="sxs-lookup"><span data-stu-id="04206-135">Shadowing through inheritance</span></span>  
  
 <span data-ttu-id="04206-136">Ein Beispiel des shadowings durch Vererbung finden Sie unter [wie: Ausblenden einer Variablen mit dem gleichen Namen wie Ihre Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) und [wie: Ausblenden einer geerbten Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span><span class="sxs-lookup"><span data-stu-id="04206-136">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="04206-137">Shadowing und Zugriffsebene</span><span class="sxs-lookup"><span data-stu-id="04206-137">Shadowing and Access Level</span></span>  
 <span data-ttu-id="04206-138">Das shadowing-Element ist nicht immer aus dem Code, der mit der abgeleiteten Klasse zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="04206-138">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="04206-139">Beispielsweise kann deklariert werden `Private`.</span><span class="sxs-lookup"><span data-stu-id="04206-139">For example, it might be declared `Private`.</span></span> <span data-ttu-id="04206-140">In diesem Fall erfolgt kein shadowing und der Compiler löst alle Verweise auf dasselbe Element er hätte gab es keine shadowing.</span><span class="sxs-lookup"><span data-stu-id="04206-140">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="04206-141">Dieses Element ist das zugegriffen werden kann, die wenigsten Ableitungsschritte Schritte rückwärts von der Klasse Shadowing, Element.</span><span class="sxs-lookup"><span data-stu-id="04206-141">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="04206-142">Wenn schattierte Element eine Prozedur ist, wird die Auflösung darin, die die nächste Version mit dem gleichen Namen, die Parameterliste, und Rückgabetyp.</span><span class="sxs-lookup"><span data-stu-id="04206-142">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="04206-143">Das folgende Beispiel zeigt eine Vererbungshierarchie von drei Klassen.</span><span class="sxs-lookup"><span data-stu-id="04206-143">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="04206-144">Jede Klasse definiert ein `Sub` Prozedur `display`, und jede abgeleitete Klasse Schatten der `display` Prozedur in der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="04206-144">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
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
  
 <span data-ttu-id="04206-145">Im vorherigen Beispiel, die abgeleitete Klasse `secondClass` Schatten `display` mit einem `Private` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="04206-145">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="04206-146">Beim Modul `callDisplay` Aufrufe `display` in `secondClass`, der aufrufende Code liegt außerhalb des `secondClass` und daher nicht den privaten verfügbar `display` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="04206-146">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="04206-147">Es erfolgt kein Shadowing und löst der Compiler den Verweis auf die Basisklasse `display` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="04206-147">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="04206-148">Jedoch stärker abgeleiteten Klasse `thirdClass` deklariert `display` als `Public`, sodass der Code in `callDisplay` darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="04206-148">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="04206-149">Shadowing und überschreiben</span><span class="sxs-lookup"><span data-stu-id="04206-149">Shadowing and Overriding</span></span>  
 <span data-ttu-id="04206-150">Verwechseln Sie shadowing und Überschreiben nicht.</span><span class="sxs-lookup"><span data-stu-id="04206-150">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="04206-151">Beide werden verwendet, wenn eine abgeleitete Klasse, die von einer Basisklasse erbt, und beide ein deklariertes Element mit einem anderen neu definieren.</span><span class="sxs-lookup"><span data-stu-id="04206-151">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="04206-152">Es gibt jedoch bedeutende Unterschiede zwischen den beiden.</span><span class="sxs-lookup"><span data-stu-id="04206-152">But there are significant differences between the two.</span></span> <span data-ttu-id="04206-153">Einen Vergleich finden Sie unter [Unterschiede zwischen Shadowing und überschreiben](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span><span class="sxs-lookup"><span data-stu-id="04206-153">For a comparison, see [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="04206-154">Shadowing und Überladung</span><span class="sxs-lookup"><span data-stu-id="04206-154">Shadowing and Overloading</span></span>  
 <span data-ttu-id="04206-155">Wenn Sie das gleiche Basisklassenelement mit mehr als ein Element in die abgeleitete Klasse vornehmen, werden die shadowing Elemente überladene Versionen des jeweiligen Elements.</span><span class="sxs-lookup"><span data-stu-id="04206-155">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="04206-156">Weitere Informationen finden Sie unter [Prozedurüberladung](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="04206-156">For more information, see [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="04206-157">Zugreifen auf ein schattiertes Element</span><span class="sxs-lookup"><span data-stu-id="04206-157">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="04206-158">Wenn Sie ein Element aus einer abgeleiteten Klasse zugreifen, normalerweise dazu über der aktuellen Instanz der abgeleiteten Klasse, qualifizieren den Elementnamen mit der `Me` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="04206-158">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="04206-159">Wenn die abgeleitete Klasse, die in der Basisklasse überschattet, können Sie Element der Basisklasse aufrufen, durch die Qualifizierung mit dem `MyBase` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="04206-159">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="04206-160">Ein Beispiel für den Zugriff auf ein schattiertes Element finden Sie unter [Vorgehensweise: Zugriff auf eine Variable Hidden durch eine abgeleitete Klasse](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="04206-160">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="04206-161">Deklaration von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="04206-161">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="04206-162">Erstellen der Object-Variablen kann auch beeinflussen, an, ob die abgeleitete Klasse shadowing-Element oder das Shadowing-Element zugreift.</span><span class="sxs-lookup"><span data-stu-id="04206-162">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="04206-163">Das folgende Beispiel erstellt zwei Objekte durch eine abgeleitete Klasse, aber ein Objekt ist als die Basisklasse und die andere als die abgeleitete Klasse deklariert.</span><span class="sxs-lookup"><span data-stu-id="04206-163">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
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
  
 <span data-ttu-id="04206-164">Im vorherigen Beispiel, die Variable `basObj` als Basisklasse deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="04206-164">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="04206-165">Zuweisen einer `dervCls` Objekt eine erweiternde Konvertierung und ist daher ungültig.</span><span class="sxs-lookup"><span data-stu-id="04206-165">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="04206-166">Jedoch nicht die Basisklasse die shadowing-Version der Variablen zugreifen `z` in der abgeleiteten Klasse, sodass der Compiler löst `basObj.z` auf den ursprünglichen Wert der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="04206-166">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04206-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04206-167">See Also</span></span>  
 [<span data-ttu-id="04206-168">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="04206-168">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="04206-169">Gültigkeitsbereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="04206-169">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [<span data-ttu-id="04206-170">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="04206-170">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="04206-171">Shadows</span><span class="sxs-lookup"><span data-stu-id="04206-171">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="04206-172">Overrides</span><span class="sxs-lookup"><span data-stu-id="04206-172">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="04206-173">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="04206-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="04206-174">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="04206-174">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
