---
title: Erstellen benutzerdefinierter Attribute
ms.date: 07/20/2015
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
ms.openlocfilehash: 84b400c2fa1b2d4019eec32092f954d680e64978
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400693"
---
# <a name="creating-custom-attributes-visual-basic"></a>Creating Custom Attributes (Visual Basic) (Erstellen benutzerdefinierter Attribute (Visual Basic))

Sie können eigene benutzerdefinierte Attribute erstellen, indem Sie eine Attributklasse definieren. Dies ist eine Klasse, die direkt oder indirekt von <xref:System.Attribute> abgeleitet wird, was es einfach macht, schnell Attributdefinitionen in Metadaten zu identifizieren. Angenommen, Sie möchten Typen mit dem Namen des Programmierers markieren, der den Typ geschrieben hat. Sie definieren möglicherweise eine benutzerdefinierte `Author`-Attributklasse:

```vb
<System.AttributeUsage(System.AttributeTargets.Class Or
                       System.AttributeTargets.Struct)>
Public Class Author
    Inherits System.Attribute
    Private name As String
    Public version As Double
    Sub New(ByVal authorName As String)
        name = authorName
        version = 1.0
    End Sub
End Class
```

Der Klassenname ist der Attributname, `Author`. Er ist von `System.Attribute` abgeleitet, ist also eine benutzerdefinierte Attributklasse. Die Parameter des Konstruktors sind die Positionsparameter des benutzerdefinierten Attributs. In diesem Beispiel ist `name` ein Positionsparameter. Alle öffentlichen Lese-/Schreibfelder oder -Eigenschaften werden Parameter genannt. In diesem Fall ist `version` der einzige Parameter mit Namen. Beachten Sie die Verwendung des `AttributeUsage`-Attributs, um das `Author`-Attribut ausschließlich für Klassen- und `Structure`-Deklarationen gültig zu machen.

Sie könnten dieses neue Attribut wie folgt verwenden:

```vb
<Author("P. Ackerman", Version:=1.1)>
Class SampleClass
    ' P. Ackerman's code goes here...
End Class
```

`AttributeUsage` verfügt über einen Parameter, `AllowMultiple`, mit dem Sie ein benutzerdefiniertes Attribut zur einmaligen oder mehrfachen Nutzung erstellen können. Im folgenden Codebeispiel wird ein mehrfach verwendbares Attribut erstellt.

```vb
' multiuse attribute
<System.AttributeUsage(System.AttributeTargets.Class Or
                       System.AttributeTargets.Struct,
                       AllowMultiple:=True)>
Public Class Author
    Inherits System.Attribute
```

Im folgenden Codebeispiel werden mehrere Attribute desselben Typs auf eine Klasse angewendet.

```vb
<Author("P. Ackerman", Version:=1.1),
Author("R. Koch", Version:=1.2)>
Class SampleClass
    ' P. Ackerman's code goes here...
    ' R. Koch's code goes here...
End Class
```

> [!NOTE]
> Wenn die Attributklasse eine Eigenschaft enthält, muss die Eigenschaft Lese- und Schreibberechtigung aufweisen.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Reflection>
- [Visual Basic-Programmierhandbuch](../../index.md)
- [Verfassen von benutzerdefinierten Attributen](../../../../standard/attributes/writing-custom-attributes.md)
- [Reflektion (Visual Basic)](../reflection.md)
- [Attribute (Visual Basic)](../../../language-reference/attributes.md)
- [Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md) (Zugreifen auf Attribute mithilfe der Reflektion (Visual Basic))
- [AttributeUsage (Visual Basic)](attributeusage.md)
