---
title: Zugriff auf Attribute mit Reflektion
ms.date: 07/20/2015
ms.assetid: c56e41da-5433-464f-a7bf-2a722e78bc9f
ms.openlocfilehash: 94352f07cf1f7e4a35f023503f138596ae5ac227
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353553"
---
# <a name="accessing-attributes-by-using-reflection-visual-basic"></a>Zugreifen auf Attribute mit Reflektion (Visual Basic)

Die Tatsache, dass Sie benutzerdefinierte Attribute definieren und diese in Ihren Quellcode platzieren können, hätte keinen Nutzen, wenn Sie diese Informationen nicht abrufen und darauf reagieren könnten. Mithilfe der Reflektion können Sie die Informationen abrufen, die mit benutzerdefinierten Attributen definiert wurden. Die Schlüsselmethode ist `GetCustomAttributes`, die ein Array von Objekten zurück gibt, die die Laufzeitäquivalente der Quellcodeattribute sind. Diese Methode hat mehrere überladene Versionen. Weitere Informationen finden Sie unter <xref:System.Attribute>.

Eine Attributspezifikation wie z.B.:

```vb
<Author("P. Ackerman", Version:=1.1)>
Class SampleClass
    ' P. Ackerman's code goes here...
End Class
```

 ist mit Folgendem vergleichbar:

```vb
Dim anonymousAuthorObject As Author = New Author("P. Ackerman")
anonymousAuthorObject.version = 1.1
```

Der Code wird allerdings erst ausgeführt, wenn `SampleClass` nach Attributen abgefragt wird. Wenn `GetCustomAttributes` in `SampleClass` aufgerufen wird, führt dies zur Erstellung und Initialisierung eines `Author`-Objekt wie oben aufgeführt. Wenn die Klasse andere Attribute aufweist, werden so auch andere Attributobjekte erstellt. `GetCustomAttributes` gibt anschließend das `Author`-Objekt zurück sowie jedes andere Attributobjekt eines Arrays. Dann können Sie dieses Array durchlaufen, anhand der Type der Arrayelemente feststellen, welche Attribute gelten, und Informationen jedes Attributobjekts erhalten.

## <a name="example"></a>Beispiel

Im Folgenden sehen Sie ein vollständiges Beispiel. Ein benutzerdefiniertes Attribut wird definiert, auf mehrere Entitäten angewendet und mithilfe der Reflektion abgerufen.

```vb
' Multiuse attribute
<System.AttributeUsage(System.AttributeTargets.Class Or
                       System.AttributeTargets.Struct,
                       AllowMultiple:=True)>
Public Class Author
    Inherits System.Attribute
    Private name As String
    Public version As Double
    Sub New(ByVal authorName As String)
        name = authorName

        ' Default value
        version = 1.0
    End Sub

    Function GetName() As String
        Return name
    End Function
End Class

' Class with the Author attribute
<Author("P. Ackerman")>
Public Class FirstClass
End Class

' Class without the Author attribute
Public Class SecondClass
End Class

' Class with multiple Author attributes.
<Author("P. Ackerman"), Author("R. Koch", Version:=2.0)>
Public Class ThirdClass
End Class

Class TestAuthorAttribute
    Sub Main()
        PrintAuthorInfo(GetType(FirstClass))
        PrintAuthorInfo(GetType(SecondClass))
        PrintAuthorInfo(GetType(ThirdClass))
    End Sub

    Private Shared Sub PrintAuthorInfo(ByVal t As System.Type)
        System.Console.WriteLine("Author information for {0}", t)

        ' Using reflection
        Dim attrs() As System.Attribute = System.Attribute.GetCustomAttributes(t)

        ' Displaying output
        For Each attr In attrs
            Dim a As Author = CType(attr, Author)
            System.Console.WriteLine("   {0}, version {1:f}", a.GetName(), a.version)
        Next
    End Sub

    ' Output:
    '   Author information for FirstClass
    '     P. Ackerman, version 1.00
    ' Author information for SecondClass
    ' Author information for ThirdClass
    '  R. Koch, version 2.00
    '  P. Ackerman, version 1.00

End Class
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection>
- <xref:System.Attribute>
- [Visual Basic-Programmierhandbuch](../../../../visual-basic/programming-guide/index.md)
- [Abrufen von Informationen aus Attributen](../../../../standard/attributes/retrieving-information-stored-in-attributes.md)
- [Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)
- [Attribute (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)
- [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) (Erstellen benutzerdefinierter Attribute (Visual Basic))
