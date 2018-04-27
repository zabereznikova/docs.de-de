---
title: Shadowing in Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 489e1786b08085f229f66b2dbc434b96b06d86df
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="shadowing-in-visual-basic"></a>Shadowing in Visual Basic
Wenn zwei Programmierelemente denselben Namen tragen, eine von ihnen kann auszublenden, oder *Schatten*, eine andere. In einer solchen Situation ist nicht das Shadowing-Element als Referenz verfügbar; Stattdessen, wenn Ihr Code den Elementnamen verwendet wird, löst Visual Basic-Compiler es in das shadowing-Element.  
  
## <a name="purpose"></a>Zweck  
 Die Hauptaufgabe des shadowings ist die Definition von Klassenmembern zu schützen. Die Basisklasse kann eine Änderung unterzogen werden, die ein Element mit dem gleichen Namen wie eine erstellt, die Sie bereits definiert haben. In diesem Fall die `Shadows` Modifizierer erzwingt, dass Verweise über die Klasse, um auf den Member aufgelöst werden Sie definiert, statt in das neue Element der Basisklasse.  
  
## <a name="types-of-shadowing"></a>Typen von Shadowing  
 Ein Element kann ein anderes Element auf zwei unterschiedliche Arten überschatten. Das shadowing-Element deklariert werden kann, innerhalb eines Unterbereichs des Bereichs, enthält das Shadowing-Element, in dem Fall das shadowing erfolgt *über den Gültigkeitsbereich*. Oder Sie können in eine abgeleitete Klasse einen Member einer Basisklasse, in dem Fall das shadowing erfolgt neu definieren *durch Vererbung*.  
  
### <a name="shadowing-through-scope"></a>Shadowing über den Gültigkeitsbereich  
 Es ist möglich, von Programmierelementen im Modul, Klasse oder Struktur, die den gleichen Namen, aber unterschiedlichen Gültigkeitsbereichen zu haben. Wenn zwei Elemente auf diese Weise deklariert werden, und der Code verweist auf den Namen, die sie gemeinsam verwenden, führt das Element mit dem engeren Bereich Shadowing für das andere Element (Blockbereich ist die engste).  
  
 Ein Modul kann definieren, z. B. eine `Public` Variable mit dem Namen `temp`, und einer Prozedur innerhalb des Moduls deklariert eine lokale Variable namens auch `temp`. Verweise auf `temp` innerhalb der Prozedur greifen auf die lokale Variable, während Verweise auf `temp` von außerhalb der Prozedur greifen auf die `Public` Variable. In diesem Fall die Prozedurvariable `temp` führt Shadowing für die Modulvariable `temp`.  
  
 Die folgende Abbildung zeigt zwei Variablen, die beiden benannten `temp`. Die lokale Variable `temp` führt Shadowing für die Membervariable `temp` bei einem Zugriff vom innerhalb ihrer eigenen Prozedur `p`. Allerdings die `MyClass` Schlüsselwort umgeht das shadowing und greift auf die Membervariable.  
  
 ![Grafisches Diagramm des shadowings über den Gültigkeitsbereich](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")  
Shadowing über den Gültigkeitsbereich  
  
 Ein Beispiel des shadowings über den Bereich finden Sie unter [wie: Ausblenden einer Variablen mit dem gleichen Namen wie Ihre Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).  
  
### <a name="shadowing-through-inheritance"></a>Shadowings durch Vererbung  
 Wenn ein Programmierelement, die von einer Basisklasse geerbt von eine abgeleitete Klasse neu definiert, führt Shadowing für das ursprüngliche Element das redefine-Element. Sie können jede Art von deklarierter Elemente oder Satz überladener Elemente mit einem beliebigen anderen Typ vornehmen. Z. B. ein `Integer` Variablen kann Shadowing für eine `Function` Prozedur. Wenn Sie eine Prozedur mit einer anderen Prozedur vornehmen, können Sie eine andere Parameterliste und einen anderen Rückgabetyp aufweisen.  
  
 Die folgende Abbildung zeigt eine Basisklasse `b` und eine abgeleitete Klasse `d` von erbt `b`. Die Basisklasse definiert eine Prozedur namens `proc`, und die abgeleitete Klasse Shadowing mit einer anderen Prozedur mit demselben Namen. Die erste `Call` Anweisung greift auf das shadowing `proc` in der abgeleiteten Klasse. Allerdings die `MyBase` Schlüsselwort umgeht das shadowing und greift auf die die Prozedur in der Basisklasse.  
  
 ![Grafisches Diagramm des shadowings durch Vererbung](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")  
Shadowings durch Vererbung  
  
 Ein Beispiel des shadowings durch Vererbung finden Sie unter [wie: Ausblenden einer Variablen mit dem gleichen Namen wie Ihre Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) und [wie: Ausblenden einer geerbten Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).  
  
#### <a name="shadowing-and-access-level"></a>Shadowing und Zugriffsebene  
 Das shadowing-Element ist nicht immer aus dem Code, der mit der abgeleiteten Klasse zugegriffen werden kann. Beispielsweise kann deklariert werden `Private`. In diesem Fall erfolgt kein shadowing und der Compiler löst alle Verweise auf dasselbe Element er hätte gab es keine shadowing. Dieses Element ist das zugegriffen werden kann, die wenigsten Ableitungsschritte Schritte rückwärts von der Klasse Shadowing, Element. Wenn schattierte Element eine Prozedur ist, wird die Auflösung darin, die die nächste Version mit dem gleichen Namen, die Parameterliste, und Rückgabetyp.  
  
 Das folgende Beispiel zeigt eine Vererbungshierarchie von drei Klassen. Jede Klasse definiert ein `Sub` Prozedur `display`, und jede abgeleitete Klasse Schatten der `display` Prozedur in der Basisklasse.  
  
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
  
 Im vorherigen Beispiel, die abgeleitete Klasse `secondClass` Schatten `display` mit einem `Private` Prozedur. Beim Modul `callDisplay` Aufrufe `display` in `secondClass`, der aufrufende Code liegt außerhalb des `secondClass` und daher nicht den privaten verfügbar `display` Prozedur. Es erfolgt kein Shadowing und löst der Compiler den Verweis auf die Basisklasse `display` Prozedur.  
  
 Jedoch stärker abgeleiteten Klasse `thirdClass` deklariert `display` als `Public`, sodass der Code in `callDisplay` darauf zugreifen können.  
  
## <a name="shadowing-and-overriding"></a>Shadowing und überschreiben  
 Verwechseln Sie shadowing und Überschreiben nicht. Beide werden verwendet, wenn eine abgeleitete Klasse, die von einer Basisklasse erbt, und beide ein deklariertes Element mit einem anderen neu definieren. Es gibt jedoch bedeutende Unterschiede zwischen den beiden. Einen Vergleich finden Sie unter [Unterschiede zwischen Shadowing und überschreiben](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).  
  
## <a name="shadowing-and-overloading"></a>Shadowing und Überladung  
 Wenn Sie das gleiche Basisklassenelement mit mehr als ein Element in die abgeleitete Klasse vornehmen, werden die shadowing Elemente überladene Versionen des jeweiligen Elements. Weitere Informationen finden Sie unter [Prozedurüberladung](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## <a name="accessing-a-shadowed-element"></a>Zugreifen auf ein schattiertes Element  
 Wenn Sie ein Element aus einer abgeleiteten Klasse zugreifen, normalerweise dazu über der aktuellen Instanz der abgeleiteten Klasse, qualifizieren den Elementnamen mit der `Me` Schlüsselwort. Wenn die abgeleitete Klasse, die in der Basisklasse überschattet, können Sie Element der Basisklasse aufrufen, durch die Qualifizierung mit dem `MyBase` Schlüsselwort.  
  
 Ein Beispiel für den Zugriff auf ein schattiertes Element finden Sie unter [Vorgehensweise: Zugriff auf eine Variable Hidden durch eine abgeleitete Klasse](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
### <a name="declaration-of-the-object-variable"></a>Deklaration von Objektvariablen  
 Erstellen der Object-Variablen kann auch beeinflussen, an, ob die abgeleitete Klasse shadowing-Element oder das Shadowing-Element zugreift. Das folgende Beispiel erstellt zwei Objekte durch eine abgeleitete Klasse, aber ein Objekt ist als die Basisklasse und die andere als die abgeleitete Klasse deklariert.  
  
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
  
 Im vorherigen Beispiel, die Variable `basObj` als Basisklasse deklariert ist. Zuweisen einer `dervCls` Objekt eine erweiternde Konvertierung und ist daher ungültig. Jedoch nicht die Basisklasse die shadowing-Version der Variablen zugreifen `z` in der abgeleiteten Klasse, sodass der Compiler löst `basObj.z` auf den ursprünglichen Wert der Basisklasse.  
  
## <a name="see-also"></a>Siehe auch  
 [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [Grundlagen der Vererbung](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
