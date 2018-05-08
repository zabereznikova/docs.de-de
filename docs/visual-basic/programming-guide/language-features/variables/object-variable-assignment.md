---
title: Zuweisen von Objektvariablen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], object variable assignment
- object variables [Visual Basic], initializing
- variables [Visual Basic], initializing
- objects [Visual Basic], current instance
- object variables [Visual Basic], assigning
- variables [Visual Basic], object variables
- current instance [Visual Basic], defined
- variables [Visual Basic], assigning
- assignment statements [Visual Basic], object variable assignment
- Me keyword [Visual Basic], as object variable
ms.assetid: 3706811d-fd40-44fe-8727-d692e8e55d6d
ms.openlocfilehash: f20a03c4d9a0e33203629ae066686f4c9f25c105
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="object-variable-assignment-visual-basic"></a>Zuweisen von Objektvariablen (Visual Basic)
Sie verwenden eine normale zuweisungsanweisung Objektvariable ein Objekt zuweisen. Sie können ein Objektausdrücke zuweisen oder die [nichts](../../../../visual-basic/language-reference/nothing.md) -Schlüsselwort, wie im folgenden Beispiel veranschaulicht.  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 `Nothing` bedeutet, es wurde kein Objekt, das der Variablen zugewiesen.  
  
## <a name="initialization"></a>Initialisierung  
 Wenn Ihr Code beginnt die Ausführung, Ihr Objekts Variablen werden initialisiert, um `Nothing`. Diejenigen, deren Deklarationen Initialisierung enthalten, sind, die Werte erneut initialisiert, die Sie angeben, wenn die deklarationsanweisungen ausgeführt werden.  
  
 Sie können die Initialisierung in der Deklaration einschließen, mit der [neu](../../../../visual-basic/language-reference/operators/new-operator.md) Schlüsselwort. Die folgende deklarationsanweisungen deklarieren Objektvariablen `testUri` und `ver` und bestimmte Objekte zuzuweisen. Jede verwendet eine der überladenen Konstruktoren der entsprechenden Klasse zum Initialisieren des Objekts.  
  
```  
Dim testUri As New System.Uri("http://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## <a name="disassociation"></a>Disassocation  
 Festlegen einer Objektvariablen auf `Nothing` reagiert nicht mehr, die Zuordnung der Variablen mit bestimmten Objekts. Dies verhindert, dass Sie fälschlicherweise das Objekt durch Ändern der Variablen ändert. Zudem können Sie zum Überprüfen, ob die Objektvariable auf ein gültiges Objekt, wie im folgenden Beispiel gezeigt verweist.  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 Wenn das Objekt, auf dem die Variable verweist in einer anderen Anwendung, kann nicht diesen Test bestimmen, ob die Anwendung beendet wurde, oder das Objekt nur für ungültig zu erklären.  
  
 Ein Object-Variablen mit einem Wert von `Nothing` steht eine *null-Verweis*.  
  
## <a name="current-instance"></a>Aktuelle Instanz  
 Die *aktuelle Instanz* eines Objekts wird in dem der Code derzeit ausgeführt wird. Da der gesamte Code innerhalb einer Prozedur ausgeführt wird, wird die aktuelle Instanz in der die Prozedur aufgerufen wurde.  
  
 Die `Me` -Schlüsselwort fungiert als eine Objektvariable verweist auf die aktuelle Instanz. Eine Prozedur ist nicht [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), kann die `Me` Schlüsselwort, um einen Zeiger auf die aktuelle Instanz. Freigegebene Prozeduren können nicht mit einer bestimmten Instanz einer Klasse zugeordnet werden.  
  
 Mithilfe von `Me` ist besonders nützlich für die aktuelle Instanz an eine Prozedur in einem anderen Modul übergeben. Nehmen wir beispielsweise an, Sie verfügen über eine Reihe von XML-Dokumenten und einige standard-Text hinzufügen möchten. Das folgende Beispiel definiert eine Prozedur zu diesem Zweck.  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 Jedes XML-Dokumentobjekt kann dann rufen Sie die Prozedur und die aktuelle Instanz als Argument übergeben. Dies wird im folgenden Beispiel veranschaulicht:  
  
```  
addStandardText(Me)  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [Werte von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [Vorgehensweise: Deklarieren einer Objektvariablen und Zuweisen eines entsprechenden Objekts in Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)  
 [Gewusst wie: Entfernen aller Verweise einer Objektvariablen auf Instanzen](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)  
 [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
