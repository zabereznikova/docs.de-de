---
title: "Shadowing in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "inheritance, shadowing"
  - "overriding, and shadowing"
  - "shadowing"
  - "duplicate names"
  - "shadowing, by inheritance"
  - "declared elements, referencing"
  - "shadowing, by scope"
  - "declared elements, hiding"
  - "naming conflicts, shadowing"
  - "declared elements, shadowing"
  - "shadowing, and overriding"
  - "scope, shadowing"
  - "Shadows keyword, about"
  - "objects [Visual Basic], names"
  - "names, shadowing"
ms.assetid: 54bb4c25-12c4-4181-b4a0-93546053964e
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Shadowing in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Wenn zwei Programmierelemente denselben Namen haben, kann eines das andere verdecken, bzw. *Shadowing* durchführen.  In diesem Fall ist das Element, für das ein Shadowing durchgeführt wurde, für Verweise nicht verfügbar. Stattdessen löst der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Compiler den Verweis in das Shadowingelement auf, wenn der Code den Elementnamen verwendet.  
  
## Zweck  
 Hauptzweck des Shadowing ist es, die Definition von Klassenmembern zu schützen.  Die Basisklasse wird vielleicht in einer Weise geändert, die ein Element mit dem gleichen Namen wie dem bereits definierten Namen zur Folge hat.  In diesem Fall erzwingt der `Shadows`\-Modifizierer, dass Verweise über die Klasse in den von Ihnen definierten Member aufgelöst werden und nicht in das neue Basisklassenelement.  
  
## Shadowingtypen  
 Für Shadowing zwischen zwei Elementen gibt es zwei Möglichkeiten.  Das Shadowingelement kann innerhalb eines Unterbereichs des Bereichs deklariert werden, der das Element enthält, für das ein Shadowing durchgeführt wurde. In diesem Fall wird das Shadowing über den *Gültigkeitsbereich* erreicht.  Es ist auch möglich, dass eine ableitende Klasse einen Member einer Basisklasse erneut definiert. In diesem Fall erfolgt das Shadowing durch *Vererbung*.  
  
### Shadowing über den Gültigkeitsbereich  
 Es ist möglich, dass Programmierelemente in demselben Modul, derselben Klasse oder derselben Struktur denselben Namen, aber unterschiedliche Gültigkeitsbereiche haben.  Wenn zwei Elemente auf diese Weise deklariert wurden und der Code auf den gemeinsamen Namen verweist, führt das Element mit dem engeren Gültigkeitsbereich für das andere Element Shadowing durch. \(Der Blockbereich ist der engste Gültigkeitsbereich\).  
  
 In einem Modul kann beispielsweise eine `Public`\-Variable mit dem Namen `temp` definiert werden, während in einer Prozedur innerhalb des Moduls eine lokale Variable deklariert wird, die ebenfalls den Namen `temp` trägt.  Verweise auf `temp` innerhalb der Prozedur greifen auf die lokale Variable zu, während Verweise auf `temp` außerhalb der Prozedur auf die `Public`\-Variable zugreifen.  In diesem Fall führt die Prozedurvariable `temp` ein Shadowing der Modulvariablen `temp` durch.  
  
 Die folgende Abbildung zeigt zwei Variablen mit dem Namen `temp`.  Die lokale Variable `temp` führt ein Shadowing der Membervariablen `temp` durch, wenn innerhalb ihrer eigenen Prozedur `p` darauf zugegriffen wird.  Allerdings umgeht das `MyClass`\-Schlüsselwort das Shadowing und greift auf die Membervariable zu.  
  
 ![Grafisches Diagramm des Shadowings über den Gültigkeitsbereich](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")  
Shadowing über den Gültigkeitsbereich  
  
 Ein Beispiel für das Shadowing über den Gültigkeitsbereich finden Sie unter [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).  
  
### Shadowing durch Vererbung  
 Wenn eine abgeleitete Klasse ein von einer Basisklasse geerbtes Programmierelement neu definiert, führt das neu definierende Element für das Originalelement Shadowing durch.  Für jeden deklarierten Elementtyp bzw. jede Gruppe überladener Elemente kann typunabhängig Shadowing durchgeführt werden.  Beispielsweise kann eine `Integer`\-Variable für eine `Function` \-Prozedur Shadowing durchführen.  Wenn eine Prozedur ein Shadowing einer anderen Prozedur durchführt, können Sie eine andere Parameterliste und einen anderen Rückgabetyp verwenden.  
  
 Die folgende Abbildung zeigt eine Basisklasse `b` und eine abgeleitete Klasse `d`, die von `b` erbt.  Die Basisklasse definiert eine Prozedur mit dem Namen `proc`, und die abgeleitete Klasse führt ein Shadowing der Prozedur mit einer anderen Prozedur gleichen Namens durch.  Die erste `Call`\-Anweisung greift in der abgeleiteten Klasse auf die Shadowingprozedur `proc` zu.  Allerdings umgeht das `MyBase`\-Schlüsselwort das Shadowing und greift in der Basisklasse auf die Prozedur zu, für die ein Shadowing durchgeführt wurde.  
  
 ![Grafisches Diagramm des Shadowings durch Vererbung](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")  
Shadowing durch Vererbung  
  
 Ein Beispiel für das Shadowing durch Vererbung finden Sie unter [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) und [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).  
  
#### Shadowing und Zugriffsebene  
 Der Code, der die abgeleitete Klasse verwendet, kann nicht immer auf das Shadowingelement zugreifen.  So könnte es zum Beispiel als `Private` deklariert sein.  In einem solchen Fall erfolgt kein Shadowing, und der Compiler löst alle vorhandenen Verweise in das gleiche Element auf, als ob es kein Shadowing gäbe.  Dieses Element ist das verwendbare Element, das die wenigsten Ableitungsschritte zurück von der Shadowingklasse liegt.  Handelt es sich bei dem Element, für das ein Shadowing durchgeführt wurde, um eine Prozedur, wird in die nächstliegende Version mit dem gleichen Namen, der gleichen Parameterliste und dem gleichen Rückgabetyp aufgelöst, auf die zugegriffen werden kann.  
  
 Das folgende Beispiel zeigt eine Vererbungshierarchie mit drei Klassen.  Jede Klasse definiert eine `Sub`\-Prozedur `display`, und jede abgeleitete Klasse führt ein Shadowing der `display`\-Prozedur in der entsprechenden Basisklasse durch.  
  
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
  
 Im vorhergehenden Beispiel führt die abgeleitete Klasse `secondClass` ein Shadowing von `display` mit einer `Private`\-Prozedur durch.  Wenn das `callDisplay`\-Modul `display` in `secondClass` aufruft, befindet sich der aufrufende Code außerhalb von `secondClass`, sodass er nicht auf die private `display`\-Prozedur zugreifen kann.  Es erfolgt kein Shadowing, und der Compiler löst den Verweis in die `display`\-Prozedur der Basisklasse auf.  
  
 Allerdings deklariert die weiter abgeleitete Klasse `thirdClass` die `display`\-Prozedur als `Public`, sodass der Code in `callDisplay` darauf zugreifen kann.  
  
## Shadowing und Überschreiben  
 Shadowing ist nicht zu verwechseln mit dem Überschreiben.  Beide Methoden werden verwendet, wenn eine abgeleitete Klasse von einer Basisklasse erbt und beide ein deklariertes Element durch ein anderes neu definieren.  Es gibt jedoch klare Unterschiede zwischen den beiden Verfahren.  Einen Vergleich finden Sie unter [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).  
  
## Shadowing und Überladen  
 Wenn Sie für ein und dasselbe Basisklassenelement mit mehr als einem Element in der abgeleiteten Klasse ein Shadowing durchführen, werden aus den Shadowingelementen überladene Versionen dieses Elements.  Weitere Informationen hierzu finden Sie unter [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## Zugreifen auf ein Element, für das ein Shadowing durchgeführt wurde  
 Wenn auf ein Element über eine abgeleitete Klasse zugegriffen wird, erfolgt dies gewöhnlich über die aktuelle Instanz dieser abgeleiteten Klasse und durch die Qualifizierung des Elementnamens mit dem `Me`\-Schlüsselwort.  Wenn die abgeleitete Klasse für das Element der Basisklasse Shadowing durchführt, kann durch die Qualifizierung mithilfe des `MyBase`\-Schlüsselworts auf das Element der Basisklasse zugegriffen werden.  
  
 Ein Beispiel für den Zugriff auf ein Element, für das ein Shadowing durchgeführt wurde, finden Sie unter [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
### Deklaration der Objektvariablen  
 Die Methode zum Erstellen der Objektvariablen kann sich auch darauf auswirken, ob die abgeleitete Klasse auf ein Shadowingelement oder auf das Element zugreift, für das ein Shadowing durchgeführt wurde.  Im folgenden Beispiel werden zwei Objekte aus einer abgeleiteten Klasse erstellt. Ein Objekt wird allerdings als die Basisklasse und das andere als die abgeleitete Klasse deklariert.  
  
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
  
 Im vorhergehenden Beispiel wird die Variable `basObj` als Basisklasse deklariert.  Die Zuweisung eines `dervCls`\-Objekts generiert eine erweiternde Konvertierung und ist daher gültig.  Die Basisklasse kann jedoch nicht auf die Shadowing\-Version der Variablen `z` in der abgeleiteten Klasse zugreifen. Daher löst der Compiler `basObj.z` in den Wert der ursprünglichen Basisklasse auf.  
  
## Siehe auch  
 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Inheritance Basics](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)