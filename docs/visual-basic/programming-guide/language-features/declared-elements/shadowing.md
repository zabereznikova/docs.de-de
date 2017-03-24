---
title: Shadowing in Visual Basic | Microsoft-Dokumentation
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
- inheritance, shadowing
- overriding, and shadowing
- shadowing
- duplicate names
- shadowing, by inheritance
- declared elements, referencing
- shadowing, by scope
- declared elements, hiding
- naming conflicts, shadowing
- declared elements, shadowing
- shadowing, and overriding
- scope, shadowing
- Shadows keyword, about
- objects [Visual Basic], names
- names, shadowing
ms.assetid: 54bb4c25-12c4-4181-b4a0-93546053964e
caps.latest.revision: 24
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5f4053de05f0a7a42fccdade1714e08f8eb172e6
ms.lasthandoff: 03/13/2017

---
# <a name="shadowing-in-visual-basic"></a>Shadowing in Visual Basic
Wenn zwei Programmierelemente denselben Namen haben, eine davon kann auszublenden, oder *Schatten*, eine. In diesem Fall ist das gespiegelte Element nicht zur Verfügung; Stattdessen, wenn der Code verwendet den Elementnamen und die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler löst den Verweis in das spiegelnde Element.  
  
## <a name="purpose"></a>Zweck  
 Der Hauptzweck des shadowing ist die Definition von Klassenmembern zu schützen. Die Basisklasse kann geändert werden, die ein Element mit dem gleichen Namen wie eine erstellt, die Sie bereits definiert haben. In diesem Fall die `Shadows` Modifizierer erzwingt, dass Verweise über die Klasse, um die Member aufgelöst werden Sie definiert, sondern an das neue Element der Basisklasse.  
  
## <a name="types-of-shadowing"></a>Typen von Shadowing  
 Ein Element kann auf zwei verschiedene Weisen ein anderes Element spiegeln. Das spiegelnde Element kann innerhalb eines Unterbereichs des Bereichs enthält, für die Shadowing durchgeführt wurde in dem Fall das shadowing erfolgt deklariert werden *über den Gültigkeitsbereich*. Oder eine ableitende Klasse einen Member einer Basisklasse, die in dem Fall das shadowing erfolgt redefine kann *durch Vererbung*.  
  
### <a name="shadowing-through-scope"></a>Shadowing über den Gültigkeitsbereich  
 Es ist möglich, dass Programmierelemente in demselben Modul, Klasse oder Struktur, die den gleichen Namen, aber unterschiedliche Gültigkeitsbereiche haben. Wenn zwei Elemente auf diese Weise deklariert wurden und der Code auf den gemeinsamen Namen verweist, spiegelt das Element mit dem engeren Gültigkeitsbereich das andere Element (der Blockbereich ist der engste).  
  
 Ein Modul kann definieren, z. B. ein `Public` Variable mit dem Namen `temp`, und eine Prozedur innerhalb des Moduls eine lokale Variable namens auch deklarieren kann `temp`. Verweise auf `temp` innerhalb der Prozedur greifen auf die lokale Variable zu, während Verweise auf `temp` von außerhalb der Prozedur greifen auf die `Public` Variable. In diesem Fall die Prozedurvariable `temp` Shadowing der Modulvariablen `temp`.  
  
 Die folgende Abbildung zeigt zwei Variablen, die mit dem Namen `temp`. Die lokale Variable `temp` die Membervariable shadows `temp` , wenn innerhalb ihrer eigenen Prozedur über `p`. Allerdings die `MyClass` Schlüsselwort umgeht das shadowing und greift auf die Membervariable.  
  
 ![Grafisches Diagramm des shadowings über den Gültigkeitsbereich](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")  
Shadowing über den Gültigkeitsbereich  
  
 Ein Beispiel für das shadowing über den Gültigkeitsbereich, finden Sie unter [Gewusst wie: Ausblenden einer Variablen mit dem gleichen Namen wie der Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).  
  
### <a name="shadowing-through-inheritance"></a>Shadowing durch Vererbung  
 Wenn eine abgeleitete Klasse ein von einer Basisklasse geerbtes Programmierelement neu definiert, spiegelt das neu definierte Element das ursprüngliche Element. Jede Art von deklarierten Element oder eine Gruppe überladener Elemente kann mit keinem anderen Typ Shadowing durchführen. Z. B. ein `Integer` Variable Schatten kann ein `Function` Verfahren. Wenn Sie eine Prozedur mit einer anderen Prozedur spiegeln, können Sie eine andere Parameterliste und einen anderen Rückgabetyp verwenden.  
  
 Die folgende Abbildung zeigt eine Basisklasse `b` und eine abgeleitete Klasse `d` , die von erbt `b`. Die Basisklasse definiert eine Prozedur namens `proc`, und die abgeleitete Klasse mit einer anderen Prozedur mit demselben Namen Shadowing. Die erste `Call` Anweisung greift auf das shadowing `proc` in der abgeleiteten Klasse. Allerdings die `MyBase` Schlüsselwort umgeht das shadowing und greift auf die schattierte Prozedur in der Basisklasse.  
  
 ![Grafisches Diagramm des shadowings durch Vererbung](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")  
Shadowing durch Vererbung  
  
 Ein Beispiel für das shadowing durch Vererbung, finden Sie unter [Gewusst wie: Ausblenden einer Variablen mit dem gleichen Namen wie Ihre Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) und [Gewusst wie: Ausblenden einer geerbten Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).  
  
#### <a name="shadowing-and-access-level"></a>Shadowing und Zugriffsebene  
 Das spiegelnde Element ist nicht immer aus dem Code, der mit der abgeleiteten Klasse zugegriffen werden kann. Beispielsweise können deklariert werden `Private`. In diesem Fall erfolgt kein shadowing, und der Compiler löst alle Verweise auf dasselbe Element haben gab es kein shadowing. Dieses Element ist die wenigsten Ableitungsschritte Schritte rückwärts von der Klasse shadowing barrierefreien Elements. Ist das gespiegelte Element eine Prozedur, wird die Lösung ist die nächste Version auf mit dem gleichen Namen, die Liste der Parameter und Rückgabetyp.  
  
 Das folgende Beispiel zeigt eine Vererbungshierarchie mit drei Klassen. Jede Klasse definiert eine `Sub` Prozedur `display`, und jede abgeleitete Klasse Schatten der `display` Prozedur in der Basisklasse.  
  
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
  
 Im vorherigen Beispiel, die abgeleitete Klasse `secondClass` Schatten `display` mit einem `Private` Verfahren. Beim Modul `callDisplay` Aufrufe `display` in `secondClass`, der aufrufende Code liegt außerhalb des `secondClass` und daher nicht den privaten verfügbar `display` Verfahren. Es erfolgt kein Shadowing, und der Compiler löst den Verweis auf die Basisklasse `display` Verfahren.  
  
 Jedoch stärker abgeleiteten Klasse `thirdClass` deklariert `display` als `Public`, sodass der Code in `callDisplay` darauf zugreifen können.  
  
## <a name="shadowing-and-overriding"></a>Shadowing und überschreiben  
 Verwechseln Sie shadowing und Überschreiben nicht. Beide werden verwendet, wenn eine abgeleitete Klasse von einer Basisklasse erbt und beide ein deklariertes Element mit einem anderen neu definieren. Aber es bedeutende Unterschiede zwischen den beiden gibt. Einen Vergleich finden Sie unter [Unterschiede zwischen Shadowing und überschreiben](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).  
  
## <a name="shadowing-and-overloading"></a>Shadowing und überladen  
 Wenn Sie ein Element mit der gleichen Basisklasse mit mehr als ein Element in der abgeleiteten Klasse Shadowing, werden die shadowing Elemente überladene Versionen dieses Elements. Weitere Informationen finden Sie unter [Prozedurüberladung](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## <a name="accessing-a-shadowed-element"></a>Zugreifen auf ein gespiegeltes Element  
 Wenn Sie ein Element aus einer abgeleiteten Klasse zugreifen, erfolgt dies gewöhnlich über die aktuelle Instanz der abgeleiteten Klasse und durch die Qualifizierung des Elementnamens mit dem `Me` Schlüsselwort. Wenn die abgeleitete Klasse, die das Element in der Basisklasse Shadowing durchführt, können Sie das Element der Basisklasse aufrufen, durch die Qualifizierung mit dem `MyBase` Schlüsselwort.  
  
 Ein Beispiel für den Zugriff auf ein Element Shadowing durchgeführt wurde, finden Sie unter [Gewusst wie: Zugriff auf eine Variable Hidden durch eine abgeleitete Klasse](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
### <a name="declaration-of-the-object-variable"></a>Deklaration von Objektvariablen  
 Erstellen der Objektvariablen kann auch beeinflussen, ob die abgeleitete Klasse spiegelnde Element oder das gespiegelte Element zugreift. Das folgende Beispiel erstellt zwei Objekte aus einer abgeleiteten Klasse, aber ein Objekt ist als die Basisklasse und die andere als die abgeleitete Klasse deklariert.  
  
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
  
 Im vorhergehenden Beispiel die Variable `basObj` als Basisklasse deklariert ist. Zuweisen einer `dervCls` -Objekt, eine erweiternde Konvertierung und ist daher gültig. Die Basisklasse kann jedoch nicht die shadowing-Version der Variablen zugreifen `z` in der abgeleiteten Klasse, sodass der Compiler löst `basObj.z` auf den ursprünglichen Wert der Basisklasse.  
  
## <a name="see-also"></a>Siehe auch  
 [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Schatten](../../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Außerkraftsetzungen](../../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Grundlagen der Vererbung](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
