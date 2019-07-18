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
ms.openlocfilehash: 9ad992a53618fa2f410e0b0fb23886c30136384f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917902"
---
# <a name="shadowing-in-visual-basic"></a>Shadowing in Visual Basic
Wenn zwei Programmierelemente mit demselben Namen gemeinsam nutzen, eine davon kann auszublenden, oder *Schatten*, der andere Controller. In diesem Fall ist das Shadowing-Element nicht als Referenz verfügbar; Stattdessen löst, wenn Ihr Code den Elementnamen verwendet, die Visual Basic-Compiler es auf das shadowing-Element.  
  
## <a name="purpose"></a>Zweck  
 Der Hauptzweck des shadowings ist die Definition von Klassenmembern zu schützen. Die Basisklasse kann eine Änderung durchlaufen, die ein Element mit dem gleichen Namen wie eine erstellt wird, die Sie bereits definiert haben. In diesem Fall die `Shadows` Modifizierer erzwingt, dass Verweise über die Klasse, um der Member aufgelöst werden Sie definiert, statt auf das neue Element der Basisklasse.  
  
## <a name="types-of-shadowing"></a>Typen des Shadowings  
 Ein Element kann ein anderes Element auf zwei unterschiedliche Arten spiegeln. Das shadowing-Element deklariert werden kann, innerhalb eines Unterbereichs des Bereichs, enthält das Shadowing-Element, in dem Fall, die das shadowing erfolgt *über den Gültigkeitsbereich*. Oder Sie können in eine abgeleitete Klasse ein Member einer Basisklasse, in dem Fall, die das shadowing erfolgt neu definieren *durch Vererbung*.  
  
### <a name="shadowing-through-scope"></a>Shadowings über den Gültigkeitsbereich  
 Es ist möglich, für die Programmierung von Elementen in der gleichen-Modul, Klasse oder Struktur, um den gleichen Namen aber unterschiedlichen Gültigkeitsbereichen zu erhalten. Wenn zwei Elemente auf diese Weise deklariert wurden, und der Code verweist auf den gemeinsamen Namen, spiegelt das Element mit der engeren Bereich definiert das andere Element (Blockbereich ist die geringstmögliche).  
  
 Ein Modul kann definieren, z. B. eine `Public` Variable mit dem Namen `temp`, und eine Prozedur innerhalb des Moduls kann eine lokale Variable, die auch mit dem Namen deklarieren `temp`. Verweise auf `temp` innerhalb die Prozedur Zugriff auf die lokale Variable, während Verweise auf `temp` von außerhalb der Prozedur greifen auf die `Public` Variable. In diesem Fall die Prozedurvariable `temp` führt Shadowing für die Modulvariable `temp`.  
  
 Die folgende Abbildung zeigt zwei Variablen, die sowohl für benannte `temp`. Die lokale Variable `temp` führt Shadowing für die Membervariable `temp` Wenn der Zugriff innerhalb ihrer eigenen Prozedur `p`. Allerdings die `MyClass` Schlüsselwort umgeht das shadowing und greift auf die Membervariable.  
  
 ![Grafik, die zeigt shadowings über den Gültigkeitsbereich.](./media/shadowing/shadow-scope-diagram.gif)
  
 Ein Beispiel des shadowings über den Bereich finden Sie unter [Vorgehensweise: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).  
  
### <a name="shadowing-through-inheritance"></a>Shadowings durch Vererbung  
 Wenn eine abgeleitete Klasse neu definiert ein Programmierelement, das von einer Basisklasse geerbt wird, führt Shadowing für das ursprüngliche Element das redefine-Element. Ein Typ des deklarierten Elements oder Satz überladener Elemente kann mit keinem anderen Typ Shadowing durchführen. Z. B. eine `Integer` Variablen kann Shadowing für eine `Function` Verfahren. Wenn Sie eine Prozedur mit einer anderen Prozedur spiegeln, können Sie eine andere Parameterliste und einen anderen Rückgabetyp.  
  
 Die folgende Abbildung zeigt eine Basisklasse `b` und eine abgeleitete Klasse `d` von erbt `b`. Die Basisklasse der Klasse definiert eine Prozedur namens `proc`, und die abgeleitete Klasse mit einer anderen Prozedur mit demselben Namen Shadowing für Sie. Die erste `Call` Anweisung greift auf das shadowing `proc` in der abgeleiteten Klasse. Allerdings die `MyBase` Schlüsselwort umgeht das shadowing und greift auf die Prozedur Shadowing durchgeführt wurde, in der Basisklasse.  
  
 ![Grafisches Diagramm des Shadowings durch Vererbung](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 Ein Beispiel des shadowings durch Vererbung, finden Sie unter [Vorgehensweise: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) und [Vorgehensweise: Ausblenden einer geerbten Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).  
  
#### <a name="shadowing-and-access-level"></a>Shadowing und Zugriffsebene  
 Das shadowing-Element ist nicht immer aus dem Code, mit der abgeleiteten Klasse zugegriffen werden kann. Zum Beispiel kann deklariert werden `Private`. In diesem Fall erfolgt kein shadowing und der Compiler löst alle Verweise auf dasselbe Element mussten gab es kein shadowing. Dieses Element ist das barrierefreie Element gilt Ableitungsschritte Schritte rückwärts von den shadowing-Klasse. Ist das Shadowing-Element eine Prozedur, die Lösung besteht darin, die die nächste Version mit dem gleichen Namen, die Parameterliste, und den Rückgabetyp.  
  
 Das folgende Beispiel zeigt eine Vererbungshierarchie von drei Klassen. Jede Klasse definiert eine `Sub` Prozedur `display`, und jede abgeleitete Klasse Schatten der `display` Prozedur in der Basisklasse.  
  
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
  
 Im vorherigen Beispiel, die abgeleitete Klasse `secondClass` Shadows `display` mit einem `Private` Verfahren. Beim Modul `callDisplay` Aufrufe `display` in `secondClass`, befindet sich außerhalb der aufrufende Code `secondClass` und daher nicht den privaten verfügbar `display` Verfahren. Es erfolgt kein Shadowing und der Compiler löst den Verweis auf die Basisklasse `display` Verfahren.  
  
 Aber die weitere abgeleitete Klasse `thirdClass` deklariert `display` als `Public`, sodass der Code in `callDisplay` darauf zugreifen können.  
  
## <a name="shadowing-and-overriding"></a>Shadowing und überschreiben  
 Ist nicht zu verwechseln shadowing und überschreiben. Beide werden verwendet, wenn eine abgeleitete Klasse, die von einer Basisklasse erbt, und beide einen deklariertes Element mit einem anderen neu definieren. Es gibt jedoch bedeutende Unterschiede zwischen den beiden. Einen Vergleich finden Sie unter [Unterschiede zwischen Shadowing und überschreiben](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).  
  
## <a name="shadowing-and-overloading"></a>Shadowing und Überladung  
 Wenn Sie das gleiche Element der Basisklasse mit mehr als ein Element in der abgeleiteten Klasse spiegeln, werden die shadowing Elemente überladenen Versionen dieses Elements. Weitere Informationen finden Sie unter [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## <a name="accessing-a-shadowed-element"></a>Zugreifen auf ein schattiertes Element  
 Wenn Sie ein Element aus einer abgeleiteten Klasse zugreifen, erfolgt dies gewöhnlich über die aktuelle Instanz der abgeleiteten Klasse und durch die Qualifizierung der Elementname mit dem `Me` Schlüsselwort. Wenn die abgeleitete Klasse das Element in der Basisklasse überschattet, können Sie das Element der Basisklasse aufrufen, durch die Qualifizierung mit dem `MyBase` Schlüsselwort.  
  
 Ein Beispiel für den Zugriff auf ein schattiertes Element finden Sie unter [Vorgehensweise: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
### <a name="declaration-of-the-object-variable"></a>Deklaration der Objektvariablen  
 Erstellen Sie die Objektvariable kann auch beeinflussen, ob die abgeleitete Klasse ein shadowing-Element oder das gespiegelte Element zugreift. Das folgende Beispiel erstellt zwei Objekte aus einer abgeleiteten Klasse, aber ein einzelnes Objekt ist als die Basisklasse und die andere als die abgeleitete Klasse deklariert.  
  
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
  
 Im vorherigen Beispiel, die Variable `basObj` ist als die Basisklasse der Klasse deklariert. Zuweisen einer `dervCls` Objekt eine erweiternde Konvertierung und ist daher gültig. Jedoch nicht die Basisklasse die shadowing-Version der Variablen zugreifen `z` in der abgeleiteten Klasse, sodass der Compiler löst `basObj.z` auf den ursprünglichen Wert der Basisklasse.  
  
## <a name="see-also"></a>Siehe auch

- [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Grundlagen der Vererbung](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
