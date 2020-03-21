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
# <a name="shadowing-in-visual-basic"></a>Shadowing in Visual Basic
Wenn zwei Programmierelemente denselben Namen haben, kann eines von ihnen das andere ausblenden oder *schatten.* In einer solchen Situation steht das schattierte Element nicht als Referenz zur Verfügung; Wenn der Code stattdessen den Elementnamen verwendet, löst der Visual Basic-Compiler ihn in das Schattenelement auf.  
  
## <a name="purpose"></a>Zweck  
 Der Hauptzweck des Shadowings besteht darin, die Definition Ihrer Klassenmitglieder zu schützen. Die Basisklasse kann eine Änderung durchlaufen, die ein Element mit demselben Namen wie das bereits definierte Element erstellt. In diesem Fall `Shadows` erzwingt der Modifikator Verweise über Ihre Klasse, die auf das von Ihnen definierte Element und nicht auf das neue Basisklassenelement aufgelöst werden.  
  
## <a name="types-of-shadowing"></a>Arten von Schatten  
 Ein Element kann ein anderes Element auf zwei verschiedene Arten überschatten. Das Schattenelement kann innerhalb einer Subregion der Region deklariert werden, die das Schattenelement enthält. *through scope* Oder eine Ableitungsklasse kann einen Member einer Basisklasse neu definieren, in diesem Fall erfolgt die Schattenung *durch Vererbung*.  
  
### <a name="shadowing-through-scope"></a>Shadowing durch den Scope  
 Programmierelemente im gleichen Modul, derselben Klasse oder Struktur können denselben Namen, aber einen unterschiedlichen Bereich haben. Wenn zwei Elemente auf diese Weise deklariert werden und der Code auf den Namen verweist, den sie gemeinsam verwenden, überschattet das Element mit dem engeren Bereich das andere Element (der Blockbereich ist das engste).  
  
 Beispielsweise kann ein Modul `Public` eine `temp`Variable mit dem Namen definieren, und eine `temp`Prozedur innerhalb des Moduls kann eine lokale Variable mit dem Namen deklarieren. Verweise `temp` auf innerhalb der Prozedur greifen auf `temp` die lokale Variable `Public` zu, während Verweise von außerhalb der Prozedur auf die Variable zugreifen. In diesem Fall überschattet `temp` die Prozedurvariable die Modulvariable `temp`.  
  
 Die folgende Abbildung zeigt zwei `temp`Variablen, beide mit dem Namen . Die lokale `temp` Variable überschattet `temp` die Membervariable, `p`wenn von einer eigenen Prozedur aus darauf zugegriffen wird. Das `MyClass` Schlüsselwort umgeht jedoch die Schattenung und greift auf die Membervariable zu.  
  
 ![Grafik, die das Schattenn durch den Bereich zeigt.](./media/shadowing/shadow-scope-diagram.gif)
  
 Ein Beispiel für das Schatieren durch den Bereich finden Sie unter [Gewusst wie: Ausblenden einer Variablen mit dem gleichen Namen wie Ihre Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).  
  
### <a name="shadowing-through-inheritance"></a>Shadowing durch Vererbung  
 Wenn eine abgeleitete Klasse ein Programmierelement neu definiert, das von einer Basisklasse geerbt wurde, überschattet das neu definierende Element das ursprüngliche Element. Sie können jeden Typ von deklarierten Elementen oder einen Satz überladener Elemente mit jedem anderen Typ überschatten. Beispielsweise kann `Integer` eine Variable `Function` eine Prozedur überschatten. Wenn Sie eine Prozedur mit einer anderen Prozedur überschatten, können Sie eine andere Parameterliste und einen anderen Rückgabetyp verwenden.  
  
 Die folgende Abbildung zeigt `b` eine Basisklasse und eine abgeleitete Klasse, `d` die von erbt. `b` Die Basisklasse definiert eine `proc`Prozedur mit dem Namen , und die abgeleitete Klasse überschattet sie mit einer anderen Prozedur mit demselben Namen. Die `Call` erste Anweisung greift `proc` auf die Schattenung in der abgeleiteten Klasse zu. Das `MyBase` Schlüsselwort umgeht jedoch die Schattenung und greift auf die schattierte Prozedur in der Basisklasse zu.  
  
 ![Grafisches Diagramm des Shadowings durch Vererbung](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 Ein Beispiel für das Schattenn durch Vererbung finden Sie unter [Gewusst wie: Ausblenden einer Variablen mit dem gleichen Namen wie Ihrer Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) und How [to: Hide an Erbvariable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).  
  
#### <a name="shadowing-and-access-level"></a>Schatten- und Zugriffsebene  
 Auf das Shadowing-Element kann nicht immer über den Code mithilfe der abgeleiteten Klasse zugegriffen werden. Sie kann z. `Private`B. deklariert werden. In einem solchen Fall wird das Shadowing besiegt, und der Compiler löst jeden Verweis auf dasselbe Element auf, das er hätte, wenn es kein Shadowing gegeben hätte. Dieses Element ist das zugängliche Element, das am wenigsten ableitungsal von der Schattenklasse zurückgeht. Wenn es sich bei dem schattierten Element um eine Prozedur handelt, erfolgt die Auflösung für die am nächsten zugängliche Version mit demselben Namen, derselben Parameterliste und demselben Rückgabetyp.  
  
 Das folgende Beispiel zeigt eine Vererbungshierarchie von drei Klassen. Jede Klasse definiert `Sub` `display`eine Prozedur , und `display` jede abgeleitete Klasse überschattet die Prozedur in ihrer Basisklasse.  
  
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
  
 Im vorherigen Beispiel schatten `secondClass` die `display` abgeleiteten Klassen mit einer `Private` Prozedur. Wenn `callDisplay` das `display` `secondClass`Modul einruft, `secondClass` befindet sich der `display` aufrufende Code außerhalb und kann daher nicht auf die private Prozedur zugreifen. Shadowing wird besiegt, und der Compiler löst `display` den Verweis auf die Basisklassenprozedur auf.  
  
 Die weitere abgeleitete `thirdClass` `display` Klasse `Public`deklariert jedoch `callDisplay` als , sodass der Code in darauf zugreifen kann.  
  
## <a name="shadowing-and-overriding"></a>Schatten und Überschreiben  
 Verwechseln Sie Schattennicht mit Überschreiben. Beide werden verwendet, wenn eine abgeleitete Klasse von einer Basisklasse erbt, und beide definieren ein deklariertes Element mit einem anderen neu. Aber es gibt erhebliche Unterschiede zwischen den beiden. Einen Vergleich finden Sie unter [Unterschiede zwischen Shadowing und Überschreiben](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).  
  
## <a name="shadowing-and-overloading"></a>Schatten und Überladen  
 Wenn Sie dasselbe Basisklassenelement mit mehr als einem Element in der abgeleiteten Klasse überschatten, werden die Schattenelemente zu überladenen Versionen dieses Elements. Weitere Informationen finden Sie unter [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## <a name="accessing-a-shadowed-element"></a>Zugreifen auf ein schattenhaftes Element  
 Wenn Sie auf ein Element aus einer abgeleiteten Klasse zugreifen, tun Sie dies normalerweise `Me` über die aktuelle Instanz dieser abgeleiteten Klasse, indem Sie den Elementnamen mit dem Schlüsselwort qualifizieren. Wenn die abgeleitete Klasse das Element in der Basisklasse überschattet, können `MyBase` Sie auf das Basisklassenelement zugreifen, indem Sie es mit dem Schlüsselwort qualifizieren.  
  
 Ein Beispiel für den Zugriff auf ein schattiertes Element finden Sie unter [Gewusst wie: Zugriff auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird.](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
  
### <a name="declaration-of-the-object-variable"></a>Deklaration der Objektvariablen  
 Wie Sie die Objektvariable erstellen, kann sich auch darauf auswirken, ob die abgeleitete Klasse auf ein Schattenelement oder das schattenhafte Element zugreift. Im folgenden Beispiel werden zwei Objekte aus einer abgeleiteten Klasse erstellt, aber ein Objekt wird als Basisklasse und das andere als abgeleitete Klasse deklariert.  
  
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
  
 Im vorherigen Beispiel wird `basObj` die Variable als Basisklasse deklariert. Das Zuweisen `dervCls` eines Objekts zu ihm stellt eine Erweiterungskonvertierung dar und ist daher gültig. Die Basisklasse kann jedoch nicht auf die `z` Schattenversion der Variablen in `basObj.z` der abgeleiteten Klasse zugreifen, sodass der Compiler in den ursprünglichen Basisklassenwert aufgelöst wird.  
  
## <a name="see-also"></a>Weitere Informationen

- [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [Außerkraftsetzungen](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Grundlagen der Vererbung](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
