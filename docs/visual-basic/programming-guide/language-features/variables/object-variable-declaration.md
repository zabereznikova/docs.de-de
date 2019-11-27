---
title: Deklaration von Objektvariablen
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
ms.openlocfilehash: d1964e3768124dde1deeabfada9006ff5a59def0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351813"
---
# <a name="object-variable-declaration-visual-basic"></a>Deklaration von Objektvariablen (Visual Basic)
Sie verwenden eine normale Deklarations Anweisung, um eine Objekt Variable zu deklarieren. Für den-Datentyp geben Sie entweder `Object` (d. h. den [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)) oder eine spezifischere Klasse an, aus der das Objekt erstellt werden soll.  
  
 Das Deklarieren einer Variablen als `Object` entspricht der Deklaration als <xref:System.Object?displayProperty=nameWithType>.  
  
 Wenn Sie eine Variable mit einer bestimmten Objektklasse deklarieren, können Sie auf alle Methoden und Eigenschaften zugreifen, die von dieser Klasse verfügbar gemacht werden, und auf die Klassen, von denen Sie erbt. Wenn Sie die Variable mit <xref:System.Object>deklarieren, kann Sie nur auf die Member der <xref:System.Object> Klasse zugreifen, es sei denn, Sie aktivieren `Option Strict Off`, um spätes Binden zuzulassen.  
  
## <a name="declaration-syntax"></a>Deklarationssyntax  
 Verwenden Sie die folgende Syntax, um eine Objekt Variable zu deklarieren:  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 Sie können auch [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [private](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)oder [static](../../../../visual-basic/language-reference/modifiers/static.md) in der Deklaration angeben. Die folgenden Beispiel Deklarationen sind gültig:  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a>Späte Bindung und frühe Bindung  
 Manchmal ist die bestimmte Klasse unbekannt, bis der Code ausgeführt wird. In diesem Fall müssen Sie die Objekt Variable mit dem `Object`-Datentyp deklarieren. Dadurch wird ein allgemeiner Verweis auf einen beliebigen Objekttyp erstellt, und die jeweilige Klasse wird zur Laufzeit zugewiesen. Dies wird als *späte Bindung*bezeichnet. Die späte Bindung erfordert zusätzliche Ausführungszeit. Außerdem schränkt er Ihren Code auf die Methoden und Eigenschaften der Klasse ein, die Sie zuletzt zugewiesen haben. Dies kann zu Laufzeitfehlern führen, wenn der Code versucht, auf Member einer anderen Klasse zuzugreifen.  
  
 Wenn Sie die jeweilige Klasse zum Zeitpunkt der Kompilierung kennen, sollten Sie die Objekt Variable so deklarieren, dass Sie dieser Klasse entspricht. Dies wird als *frühe Bindung* bezeichnet. Frühe Bindungen verbessern die Leistung und gewährleisten, dass Ihr Code auf alle Methoden und Eigenschaften der jeweiligen Klasse zugreift. Wenn in den vorangehenden Beispiel Deklarationen die Variable `objA` nur Objekte der Klasse <xref:System.Windows.Forms.Label?displayProperty=nameWithType>verwendet, sollten Sie `As System.Windows.Forms.Label` in der Deklaration angeben.  
  
### <a name="advantages-of-early-binding"></a>Vorteile der frühen Bindung  
 Das Deklarieren einer Objektvariablen als eine bestimmte Klasse bietet mehrere Vorteile:  
  
- Automatische Typüberprüfung  
  
- Garantierte Zugriffsberechtigung für alle Member der bestimmten Klasse  
  
- Microsoft IntelliSense-Unterstützung im Code-Editor  
  
- Bessere Lesbarkeit des Codes  
  
- Weniger Fehler in Ihrem Code  
  
- Fehler, die zur Kompilierzeit statt zur Laufzeit abgefangen wurden.  
  
- Schnellere Codeausführung  
  
## <a name="access-to-object-variable-members"></a>Zugriff auf Objektvariablen Elemente  
 Wenn `Option Strict` `On`aktiviert ist, kann eine Objekt Variable nur auf die Methoden und Eigenschaften der Klasse zugreifen, mit der Sie Sie deklarieren. Das folgende Beispiel veranschaulicht dies.  
  
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
  
## <a name="flexibility-of-object-variables"></a>Flexibilität von Objektvariablen  
 Beim Arbeiten mit Objekten in einer Vererbungs Hierarchie haben Sie die Wahl, welche Klasse zum Deklarieren der Objektvariablen verwendet werden soll. Wenn Sie diese Auswahl treffen, müssen Sie die Flexibilität der Objekt Zuweisung gegen den Zugriff auf die Member einer Klasse ausgleichen. Nehmen Sie beispielsweise die Vererbungs Hierarchie, die zur <xref:System.Windows.Forms.Form?displayProperty=nameWithType>-Klasse führt:  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 Angenommen, Ihre Anwendung definiert eine Formular Klasse mit dem Namen `specialForm`, die von Class <xref:System.Windows.Forms.Form>erbt. Sie können eine Objekt Variable deklarieren, die speziell auf `specialForm`verweist, wie im folgenden Beispiel gezeigt.  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 Die-Deklaration im vorangehenden Beispiel schränkt die Variablen `nextForm` auf Objekte der Klasse `specialForm`, aber auch alle Methoden und Eigenschaften von `specialForm` verfügbar `nextForm`sowie alle Member aller Klassen, von denen `specialForm` erbt.  
  
 Sie können eine Objekt Variable allgemeiner machen, indem Sie Sie als Typ <xref:System.Windows.Forms.Form>deklarieren, wie im folgenden Beispiel gezeigt.  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 Mit der Deklaration im vorherigen Beispiel können Sie `anyForm`beliebige Formulare in der Anwendung zuweisen. Obwohl `anyForm` auf alle Member der Klasse <xref:System.Windows.Forms.Form>zugreifen kann, können keine zusätzlichen Methoden oder Eigenschaften verwendet werden, die für bestimmte Formulare wie `specialForm`definiert sind.  
  
 Alle Member einer Basisklasse sind für abgeleitete Klassen verfügbar, aber die zusätzlichen Member einer abgeleiteten Klasse sind für die Basisklasse nicht verfügbar.  
  
## <a name="see-also"></a>Siehe auch

- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Zuweisen von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Werte von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Gewusst wie: Deklarieren einer Objektvariablen und Zuweisen eines Objekts in Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [Gewusst wie: Zugreifen auf Member eines Objekts](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [New-Operator](../../../../visual-basic/language-reference/operators/new-operator.md)
- [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
