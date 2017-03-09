---
title: "Object Variable Assignment (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Nothing keyword, object variable assignment"
  - "object variables, initializing"
  - "variables [Visual Basic], initializing"
  - "objects [Visual Basic], current instance"
  - "object variables, assigning"
  - "variables [Visual Basic], object variables"
  - "current instance, defined"
  - "variables [Visual Basic], assigning"
  - "assignment statements, object variable assignment"
  - "Me keyword, as object variable"
ms.assetid: 3706811d-fd40-44fe-8727-d692e8e55d6d
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Object Variable Assignment (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Ein Objekt wird einer Objektvariablen mit einer normalen Zuweisungsanweisung zugewiesen.  Sie können einen Objektausdruck oder das [Nothing](../../../../visual-basic/language-reference/nothing.md)\-Schlüsselwort zuweisen, wie im folgenden Beispiel veranschaulicht wird.  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 `Nothing` bedeutet, dass der Variablen gegenwärtig kein Objekt zugewiesen ist.  
  
## Initialisierung  
 Wenn mit der Ausführung des Codes begonnen wird, werden die Objektvariablen mit `Nothing` initialisiert.  Während der Ausführung der Deklarationsanweisungen werden die Variablen, deren Deklarationen die Initialisierung enthält, mit den angegebenen Werten neu initialisiert.  
  
 Sie können unter Verwendung des Schlüsselworts [New](../../../../visual-basic/language-reference/operators/new-operator.md) die Initialisierung in die Deklaration einschließen.  Mit den folgenden Deklarationsanweisungen werden die Objektvariablen `testUri` und `ver` deklariert und diesen Variablen spezielle Objekte zugewiesen.  Zur Initialisierung des Objekts wird jeweils einer der überladenen Konstruktoren der entsprechenden Klasse verwendet.  
  
```  
Dim testUri As New System.Uri("http://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## Disassoziation  
 Wenn eine Objektvariable auf `Nothing` festgelegt wird, wird die Zuordnung der Variablen zu einem speziellen Objekt beendet.  So wird verhindert, dass das Objekt durch eine Variablenänderung versehentlich geändert wird.  Außerdem können Sie testen, ob die Objektvariable auf ein gültiges Objekt zeigt; das folgende Beispiel veranschaulicht dies:  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 Wenn die Variable auf ein Objekt in einer anderen Anwendung verweist, kann mit diesem Test nicht festgestellt werden, ob die betreffende Anwendung beendet wurde oder ob das Objekt dort lediglich ungültig wurde.  
  
 Eine Objektvariable mit dem Wert `Nothing` wird auch als *Nullverweis* bezeichnet.  
  
## Aktuelle Instanz  
 Die *aktuelle Instanz* eines Objekts ist diejenige, in der der Code gegenwärtig ausgeführt wird.  Da Code immer innerhalb einer Prozedur ausgeführt wird, handelt es sich bei der aktuellen Instanz um diejenige, in der die Prozedur aufgerufen wurde.  
  
 Das `Me`\-Schlüsselwort fungiert als auf die aktuelle Instanz verweisende Objektvariable.  Sofern eine Prozedur nicht als [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) deklariert wurde, kann sie mithilfe des `Me`\-Schlüsselworts einen Zeiger auf die aktuelle Instanz abrufen.  Freigegebene Prozeduren können nicht einzelnen Objektinstanzen zugeordnet werden.  
  
 `Me` ist vor allem bei der Übergabe der aktuellen Instanz an eine Prozedur in einem anderen Modul hilfreich.  Nehmen wir beispielsweise an, es sind einige XML\-Dokumente vorhanden, und jedem dieser Dokumente soll ein Standardtext hinzugefügt werden.  Im folgenden Beispiel wird eine Prozedur definiert, die dies leistet.  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 Daraufhin kann jedes XML\-Dokumentobjekt die Prozedur aufrufen und ihr seine aktuelle Instanz mit der folgenden Anweisung als Argument übergeben:  Das folgende Beispiel veranschaulicht dies.  
  
```  
addStandardText(Me)  
```  
  
## Siehe auch  
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Object Variable Values](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [How to: Declare an Object Variable and Assign an Object to It in Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)   
 [How to: Make an Object Variable Not Refer to Any Instance](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)   
 [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)