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
ms.openlocfilehash: 30c02cf367c461c3896a01538d03380627de294f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004853"
---
# <a name="shadowing-in-visual-basic"></a>Shadowing in Visual Basic
Wenn zwei Programmier Elemente denselben Namen haben, kann einer von Ihnen einen ausblenden oder einen *Schatten*der anderen verwenden. In einer solchen Situation ist das Shadowing-Element nicht für den Verweis verfügbar. Wenn der Code den Elementnamen verwendet, wird er stattdessen vom Visual Basic Compiler in das Shadowing-Element aufgelöst.  
  
## <a name="purpose"></a>Zweck  
 Der Hauptzweck von shadowingbesteht darin, die Definition der Klassenmember zu schützen. Die Basisklasse kann einer Änderung unterzogen werden, die ein Element mit dem gleichen Namen erstellt, den Sie bereits definiert haben. In diesem Fall erzwingt der `Shadows` Modifizierer, dass Verweise durch Ihre Klasse in den von Ihnen definierten Member aufgelöst werden, anstatt das neue Basisklassen Element zu verwenden.  
  
## <a name="types-of-shadowing"></a>Typen von Shadowings  
 Ein Element kann auf zwei verschiedene Arten einen Schatten für ein anderes Element haben. Das Shadowing-Element kann in einem Teilbereich des Bereichs deklariert werden, der das schattiert-Element enthält. in diesem Fall wird der Shadowing *über den Bereich*erreicht. Oder eine abgeleitete Klasse kann einen Member einer Basisklasse neu definieren. in diesem Fall erfolgt die über schattung *durch Vererbung*.  
  
### <a name="shadowing-through-scope"></a>Shadothrough im Gültigkeitsbereich  
 Es ist möglich, dass Elemente im gleichen Modul, in derselben Klasse oder in derselben Struktur denselben Namen, aber unterschiedlichen Gültigkeitsbereich aufweisen. Wenn zwei-Elemente auf diese Weise deklariert werden und sich der Code auf den Namen bezieht, den Sie freigeben, wird das-Element mit dem engeren Bereich mit dem anderen-Element Shadowing (Block Bereich ist die engste).  
  
 Ein Modul kann z. b. eine `Public` Variable mit dem Namen `temp`definieren, und eine Prozedur innerhalb des Moduls kann eine lokale Variable mit dem Namen `temp`deklarieren. Verweise auf `temp` innerhalb der Prozedur greifen auf die lokale Variable zu, während Verweise auf `temp` von außerhalb der Prozedur auf die `Public` Variable zugreifen. In diesem Fall `temp` die Prozedur Variable die Modul Variable `temp`.  
  
 Die folgende Abbildung zeigt zwei Variablen, die beide den Namen `temp`haben. Die lokale Variable `temp` Schatten der Element Variablen `temp`, wenn der Zugriff innerhalb der eigenen Prozedur `p`erfolgt. Allerdings umgeht das `MyClass`-Schlüsselwort den shadodown und greift auf die Member-Variable zu.  
  
 ![Grafik, die shadothrough durch den Gültigkeitsbereich anzeigt.](./media/shadowing/shadow-scope-diagram.gif)
  
 Ein Beispiel für die über schattung durch den Bereich finden Sie unter Gewusst [wie: Ausblenden einer Variablen mit dem gleichen Namen wie die Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).  
  
### <a name="shadowing-through-inheritance"></a>Über schattung durch Vererbung  
 Wenn eine abgeleitete Klasse ein Programmier Element neu definiert, das von einer Basisklasse geerbt wurde, gibt das neu definierende Element einen Schatten für das ursprüngliche Element aus. Sie können einen beliebigen Typ eines deklarierten Elements oder einen Satz überladener Elemente mit einem beliebigen anderen Typ schattieren. Beispielsweise kann eine `Integer` Variable eine `Function` Prozedur schattieren. Wenn Sie eine Prozedur mit einer anderen Prozedur als Schatten verwenden, können Sie eine andere Parameterliste und einen anderen Rückgabetyp verwenden.  
  
 Die folgende Abbildung zeigt eine Basisklasse `b` und eine abgeleitete Klasse `d`, die von `b`erbt. Die-Basisklasse definiert eine Prozedur mit dem Namen `proc`, und die abgeleitete Klasse überschattet Sie mit einer anderen Prozedur desselben Namens. Die erste `Call` Anweisung greift auf die Shadowing`proc` in der abgeleiteten Klasse zu. Allerdings umgeht das `MyBase`-Schlüsselwort den Shadowing und greift auf die Shadowing-Prozedur in der-Basisklasse zu.  
  
 ![Grafisches Diagramm des Shadowings durch Vererbung](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 Ein Beispiel für das Durchsuchen von Vererbung durch die Vererbung finden Sie unter Gewusst [wie: Ausblenden einer Variablen mit dem gleichen Namen wie die Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) und Gewusst [wie: Ausblenden einer geerbten Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).  
  
#### <a name="shadowing-and-access-level"></a>Shadowingund Zugriffsebene  
 Auf das Shadowingelement kann nicht immer über den Code zugegriffen werden, wenn die abgeleitete Klasse verwendet wird. Beispielsweise könnte Sie als `Private`deklariert werden. In einem solchen Fall wird shadodown unterbunden, und der Compiler löst alle Verweise auf dasselbe Element auf, das er hätte, wenn kein shadodown vorhanden wäre. Dieses Element ist das barrierefreie Element, bei dem die wenigsten abderivations Schritte von der Shadowingklasse rückwärts ausgeführt werden. Wenn das Shadowing Element eine Prozedur ist, wird die Auflösung an die nächstgelegene Barrierefreie Version mit dem gleichen Namen, der gleichen Parameterliste und dem gleichen Rückgabetyp durchgeführt.  
  
 Das folgende Beispiel zeigt eine Vererbungs Hierarchie von drei Klassen. Jede Klasse definiert eine `Sub` Prozedur `display`, und jede abgeleitete Klasse überschattet die `display` Prozedur in ihrer Basisklasse.  
  
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
  
 Im vorherigen Beispiel `secondClass` die abgeleitete Klasse Shadowing `display` mit einer `Private` Prozedur. Wenn die Modul `callDisplay` `display` in `secondClass`aufruft, befindet sich der Aufruf Code außerhalb `secondClass` und kann daher nicht auf die private `display` Prozedur zugreifen. Shadowings wird untersucht, und der Compiler löst den Verweis auf die Basisklasse `display` Prozedur auf.  
  
 Die weitere abgeleitete Klasse `thirdClass` jedoch `display` als `Public`deklariert, sodass der Code in `callDisplay` darauf zugreifen kann.  
  
## <a name="shadowing-and-overriding"></a>Shadodown und überschreiben  
 Shadodown kann nicht mit Überschreiben verwechselt werden. Beide werden verwendet, wenn eine abgeleitete Klasse von einer Basisklasse erbt, und beide definieren ein deklariertes Element mit einem anderen. Es gibt jedoch bedeutende Unterschiede zwischen den beiden. Einen Vergleich finden Sie [unter Unterschiede zwischen shadodown und](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)überschreiben.  
  
## <a name="shadowing-and-overloading"></a>Shadoading und überladen  
 Wenn Sie das gleiche Basisklassen Element mit mehr als einem Element in der abgeleiteten Klasse überschatten, werden die Shadowing-Elemente überladene Versionen dieses Elements. Weitere Informationen finden Sie unter [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## <a name="accessing-a-shadowed-element"></a>Zugreifen auf ein Shadowing Element  
 Wenn Sie auf ein Element aus einer abgeleiteten Klasse zugreifen, verwenden Sie normalerweise die aktuelle Instanz der abgeleiteten Klasse, indem Sie den Elementnamen mit dem `Me`-Schlüsselwort qualifizieren. Wenn die abgeleitete Klasse ein Shadowing für das Element in der Basisklasse durchführt, können Sie auf das Basisklassen Element zugreifen, indem Sie es mit dem Schlüsselwort `MyBase` qualifizieren  
  
 Ein Beispiel für den Zugriff auf ein Shadowing Element finden Sie unter Gewusst [wie: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)wird.  
  
### <a name="declaration-of-the-object-variable"></a>Deklaration der Objektvariablen  
 Wie Sie die Objekt Variable erstellen, kann sich auch darauf auswirken, ob die abgeleitete Klasse auf ein Shadowing-Element oder das Shadowing-Element zugreift Im folgenden Beispiel werden zwei Objekte aus einer abgeleiteten Klasse erstellt, aber ein Objekt wird als Basisklasse und die andere als abgeleitete Klasse deklariert.  
  
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
  
 Im vorherigen Beispiel wird die Variable `basObj` als Basisklasse deklariert. Das Zuweisen eines `dervCls` Objekts zu diesem Objekt stellt eine erweiternde Konvertierung dar und ist daher gültig. Die Basisklasse kann jedoch nicht auf die Shadowingversion der Variablen `z` in der abgeleiteten Klasse zugreifen, sodass der Compiler `basObj.z` in den ursprünglichen Basisklassen Wert auflöst.  
  
## <a name="see-also"></a>Siehe auch

- [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Bereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Grundlagen der Vererbung](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
