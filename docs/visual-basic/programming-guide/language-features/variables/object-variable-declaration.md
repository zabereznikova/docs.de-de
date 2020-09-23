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
ms.openlocfilehash: 74b1401df3dbb2d744de74734d10cbcd92e9689e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077045"
---
# <a name="object-variable-declaration-visual-basic"></a>Deklaration von Objektvariablen (Visual Basic)

Sie verwenden eine normale Deklarations Anweisung, um eine Objekt Variable zu deklarieren. Für den-Datentyp geben Sie entweder (d. h. `Object` den [Object-Datentyp](../../../language-reference/data-types/object-data-type.md)) oder eine spezifischere Klasse an, aus der das Objekt erstellt werden soll.  
  
 Das Deklarieren einer Variablen als `Object` entspricht der Deklaration als <xref:System.Object?displayProperty=nameWithType> .  
  
 Wenn Sie eine Variable mit einer bestimmten Objektklasse deklarieren, können Sie auf alle Methoden und Eigenschaften zugreifen, die von dieser Klasse verfügbar gemacht werden, und auf die Klassen, von denen Sie erbt. Wenn Sie die Variable mit deklarieren <xref:System.Object> , kann Sie nur auf die Member der <xref:System.Object> Klasse zugreifen, es sei denn, Sie aktivieren die `Option Strict Off` späte Bindung.  
  
## <a name="declaration-syntax"></a>Deklarationssyntax  

 Verwenden Sie die folgende Syntax, um eine Objekt Variable zu deklarieren:  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 Sie können in der Deklaration auch [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md), `Protected Friend` , [private](../../../language-reference/modifiers/private.md), [Shared](../../../language-reference/modifiers/shared.md)oder [static](../../../language-reference/modifiers/static.md) angeben. Die folgenden Beispiel Deklarationen sind gültig:  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a>Späte Bindung und frühe Bindung  

 Manchmal ist die bestimmte Klasse unbekannt, bis der Code ausgeführt wird. In diesem Fall müssen Sie die Objekt Variable mit dem- `Object` Datentyp deklarieren. Dadurch wird ein allgemeiner Verweis auf einen beliebigen Objekttyp erstellt, und die jeweilige Klasse wird zur Laufzeit zugewiesen. Dies wird als *späte Bindung*bezeichnet. Die späte Bindung erfordert zusätzliche Ausführungszeit. Außerdem schränkt er Ihren Code auf die Methoden und Eigenschaften der Klasse ein, die Sie zuletzt zugewiesen haben. Dies kann zu Laufzeitfehlern führen, wenn der Code versucht, auf Member einer anderen Klasse zuzugreifen.  
  
 Wenn Sie die jeweilige Klasse zum Zeitpunkt der Kompilierung kennen, sollten Sie die Objekt Variable so deklarieren, dass Sie dieser Klasse entspricht. Dies wird als *frühe Bindung* bezeichnet. Frühe Bindungen verbessern die Leistung und gewährleisten, dass Ihr Code auf alle Methoden und Eigenschaften der jeweiligen Klasse zugreift. Wenn die Variable in den vorangehenden Beispiel Deklarationen `objA` nur Objekte der Klasse verwendet <xref:System.Windows.Forms.Label?displayProperty=nameWithType> , sollten Sie `As System.Windows.Forms.Label` in der Deklaration angeben.  
  
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

 Wenn `Option Strict` aktiviert ist `On` , kann eine Objekt Variable nur auf die Methoden und Eigenschaften der Klasse zugreifen, mit der Sie Sie deklarieren. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
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

 Beim Arbeiten mit Objekten in einer Vererbungs Hierarchie haben Sie die Wahl, welche Klasse zum Deklarieren der Objektvariablen verwendet werden soll. Wenn Sie diese Auswahl treffen, müssen Sie die Flexibilität der Objekt Zuweisung gegen den Zugriff auf die Member einer Klasse ausgleichen. Sehen Sie sich beispielsweise die Vererbungs Hierarchie an, die zur- <xref:System.Windows.Forms.Form?displayProperty=nameWithType> Klasse führt:  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 Angenommen, Ihre Anwendung definiert eine Formular Klasse `specialForm` mit dem Namen, die von der-Klasse erbt <xref:System.Windows.Forms.Form> . Sie können eine Objekt Variable deklarieren, die speziell auf verweist `specialForm` , wie im folgenden Beispiel gezeigt.  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 Die-Deklaration im vorherigen Beispiel schränkt die-Variable `nextForm` auf Objekte der-Klasse ein `specialForm` , aber Sie macht auch alle-Methoden und-Eigenschaften für `specialForm` verfügbar `nextForm` , sowie alle Member aller Klassen, von denen `specialForm` erbt.  
  
 Sie können eine Objekt Variable allgemeiner machen, indem Sie Sie als Typ deklarieren <xref:System.Windows.Forms.Form> , wie im folgenden Beispiel gezeigt.  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 Mit der Deklaration im vorherigen Beispiel können Sie ein beliebiges Formular in der Anwendung zuweisen `anyForm` . Obwohl zwar `anyForm` auf alle Member der Klasse zugreifen kann <xref:System.Windows.Forms.Form> , kann jedoch keine der zusätzlichen Methoden oder Eigenschaften verwendet werden, die für bestimmte Formulare wie z `specialForm` . b. definiert sind.  
  
 Alle Member einer Basisklasse sind für abgeleitete Klassen verfügbar, aber die zusätzlichen Member einer abgeleiteten Klasse sind für die Basisklasse nicht verfügbar.  
  
## <a name="see-also"></a>Siehe auch

- [Objektvariablen](object-variables.md)
- [Zuweisung von Objektvariablen](object-variable-assignment.md)
- [Werte von Objektvariablen](object-variable-values.md)
- [Gewusst wie: Deklarieren einer Objektvariablen und Zuweisen eines entsprechenden Objekts in Visual Basic](how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [Vorgehensweise: Zugreifen auf Member eines Objekts](how-to-access-members-of-an-object.md)
- [New-Operator](../../../language-reference/operators/new-operator.md)
- [Option Strict-Anweisung](../../../language-reference/statements/option-strict-statement.md)
- [Lokaler Typrückschluss](local-type-inference.md)
