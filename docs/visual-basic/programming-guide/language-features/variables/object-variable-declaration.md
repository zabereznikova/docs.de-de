---
title: Deklaration von Objektvariablen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- early binding [Visual Basic]
- declarations [Visual Basic], class
- classes [Visual Basic], declaring
- binding [Visual Basic], late and early
- object variables [Visual Basic], declaring
- variables [Visual Basic], object
- declaring variables [Visual Basic], object variables
- declaring classes [Visual Basic]
- late binding [Visual Basic]
ms.assetid: 2a5a41a3-1aa8-4236-b1f0-2382af7bf715
ms.openlocfilehash: 96b1677e301d3e83df400472bfa06e921f991bd1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544652"
---
# <a name="object-variable-declaration-visual-basic"></a>Deklaration von Objektvariablen (Visual Basic)
Sie haben eine normale deklarationsanweisung zum Deklarieren einer Objektvariablen verwenden. Für den Datentyp, geben Sie entweder `Object` (d. h. die [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)) oder eine spezifische Klasse, die von dem das Objekt ist, erstellt werden.  
  
 Deklarieren einer Variablen als `Object` ist identisch mit der Deklaration als <xref:System.Object?displayProperty=nameWithType>.  
  
 Wenn Sie eine Variable mit einem bestimmten Objekt-Klasse deklarieren, können darauf zugreifen, die alle Methoden und Eigenschaften, die von dieser Klasse und die Klassen, die von denen geerbt verfügbar gemacht werden. Sie deklarieren die Variable mit <xref:System.Object>, es kann nur Mitglieder der Zugriff der <xref:System.Object> Klasse, es sei denn, Sie deaktivieren `Option Strict Off` spätes Binden können.  
  
## <a name="declaration-syntax"></a>Deklarationssyntax  
 Verwenden Sie die folgende Syntax zum Deklarieren einer Objektvariablen:  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 Sie können auch angeben, [öffentliche](../../../../visual-basic/language-reference/modifiers/public.md), [geschützte](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), oder [statische](../../../../visual-basic/language-reference/modifiers/static.md) in der Deklaration. Die folgende Beispieldeklarationen sind gültig:  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a>Späte Bindung und der frühen Bindung  
 Manchmal ist die spezifische Klasse unbekannt, bis Ihr Code ausgeführt wird. In diesem Fall müssen Sie die Objektvariable mit deklarieren die `Object` -Datentyp. Dadurch wird einen allgemeinen Verweis auf jede Art von Objekt erstellt, und die spezifische Klasse zur Laufzeit zugewiesen wird. Dies wird als bezeichnet *späte Bindung*. Späte Bindung erfordert zusätzliche Ausführungszeit. Außerdem wird den Code die Methoden und Eigenschaften der Klasse, die Sie zuletzt zugewiesen werden, beschränkt. Dies kann Laufzeitfehler verursachen, wenn der Code versucht, den Zugriff auf Member einer anderen Klasse.  
  
 Wenn Sie die spezifische Klasse zum Zeitpunkt der Kompilierung bekannt ist, sollten Sie die Objektvariable werden von dieser Klasse deklarieren. Dies wird als *frühe Bindung* bezeichnet. Früher Bindung verbessert die Leistung und garantiert Ihren Codezugriff auf die Methoden und Eigenschaften der Klasse. Im obigen Beispieldeklarationen, wenn die Variable `objA` verwendet nur die Objekte der Klasse <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, geben Sie `As System.Windows.Forms.Label` in der Deklaration.  
  
### <a name="advantages-of-early-binding"></a>Vorteile der frühen Bindung  
 Deklarieren einer Objektvariablen als eine bestimmte Klasse bietet mehrere Vorteile:  
  
-   Automatische typüberprüfung  
  
-   Zugriff auf alle Elemente der speziellen Klasse garantiert  
  
-   Microsoft IntelliSense-Unterstützung im Code-Editor  
  
-   Verbesserte Lesbarkeit des Codes  
  
-   Weniger Fehler im code  
  
-   Fehler, die zur abgefangen Kompilierzeit statt zur Laufzeit  
  
-   Schnellere Ausführung von code  
  
## <a name="access-to-object-variable-members"></a>Zugriff auf Member von Objektvariablen  
 Wenn `Option Strict` standardablaufverfolung `On`, nur die Methoden und Eigenschaften der Klasse mit dem Sie wurde deklariert, kann eine Objektvariable zugreifen. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
' Option statements must precede all other source file lines.  
Option Strict On  
' Imports statement must precede all declarations in the source file.  
Imports System.Windows.Forms  
Public Sub accessMembers()  
    Dim p As Object  
    Dim q As System.Windows.Forms.Label  
    p = New System.Windows.Forms.Label  
    q = New System.Windows.Forms.Label  
    Dim j, k As Integer  
    ' The following statement generates a compiler ERROR.  
    j = p.Left  
    ' The following statement retrieves the left edge of the label in pixels.  
    k = q.Left  
End Sub  
```  
  
 In diesem Beispiel kann `p` nur die Mitglieder der <xref:System.Object> -Klasse selbst verwenden, die nicht die `Left` -Eigenschaft enthalten. Auf der anderen Seite wurde `q` als Typ <xref:System.Windows.Forms.Label>deklariert, sodass es alle Methoden und Eigenschaften der <xref:System.Windows.Forms.Label> -Klasse im <xref:System.Windows.Forms> -Namespace verwenden kann.  
  
## <a name="flexibility-of-object-variables"></a>Die Flexibilität von Objektvariablen  
 Bei der Arbeit mit Objekten in einer Vererbungshierarchie müssen Sie eine Auswahl von welcher Klasse zum Deklarieren Ihrer Objektvariablen verwenden. Auf dieser Auswahl müssen Sie die Flexibilität der Zuweisung von Objekten für den Zugriff auf Member einer Klasse ausgleichen. Betrachten Sie z. B. die Vererbungshierarchie, die zu führt die <xref:System.Windows.Forms.Form?displayProperty=nameWithType> Klasse:  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 Angenommen, Ihre Anwendung die Formularklasse definiert `specialForm`, erbt von Klasse <xref:System.Windows.Forms.Form>. Sie können angeben, Deklarieren einer Objektvariablen, die speziell verweist `specialForm`, wie im folgende Beispiel gezeigt.  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 Die Deklaration im vorherigen Beispiel schränkt die Variable `nextForm` auf Objekte der Klasse `specialForm`, macht zudem alle Methoden und Eigenschaften der `specialForm` zur `nextForm`sowie die Member aller Klassen aus dem `specialForm` erbt.  
  
 Sie können eine Objektvariable allgemeineren machen, indem Sie die Deklaration des Typs <xref:System.Windows.Forms.Form>, wie im folgende Beispiel gezeigt.  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 Ermöglicht das Zuweisen von keiner Form in der Anwendung für die Deklaration im vorherigen Beispiel `anyForm`. Aber Obwohl `anyForm` können auf alle Member der Klasse zugreifen <xref:System.Windows.Forms.Form>, es können keine zusätzlichen Methoden oder Eigenschaften, die für bestimmte Formulare definiert, wie z. B. `specialForm`.  
  
 Es sind alle Member einer Basisklasse abgeleiteten Klassen zur Verfügung, aber die zusätzlichen Member einer abgeleiteten Klasse sind nicht verfügbar, auf die Basisklasse.  
  
## <a name="see-also"></a>Siehe auch
- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Zuweisen von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Werte von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Vorgehensweise: Deklarieren einer Objektvariablen und Zuweisen eines entsprechenden Objekts in Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [Vorgehensweise: Zugreifen auf Member eines Objekts](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [New-Operator](../../../../visual-basic/language-reference/operators/new-operator.md)
- [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
