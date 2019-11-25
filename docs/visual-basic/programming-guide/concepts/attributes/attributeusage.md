---
title: AttributeUsage
ms.date: 07/20/2015
ms.assetid: 48757216-c21d-4051-86d5-8a3e03c39d2c
ms.openlocfilehash: 7e54e82c1e9edfd0d9d393a014f9d91f82970363
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353547"
---
# <a name="attributeusage-visual-basic"></a>AttributeUsage (Visual Basic)

Bestimmt, wie eine benutzerdefinierte Attributklasse verwendet werden kann. `AttributeUsage` ist ein Attribut, dass auf benutzerdefinierte Attributdefinitionen zur Steuerung der Anwendung neuer Attribute angewendet werden kann. Die Standardeinstellungen sehen wie folgt aus, wenn Sie explizit angewendet werden:

```vb
<System.AttributeUsage(System.AttributeTargets.All,
                   AllowMultiple:=False,
                   Inherited:=True)>
Class NewAttribute
    Inherits System.Attribute
End Class
```

In diesem Beispiel kann die Klasse `NewAttribute` auf jede attributfähige Codeentität angewendet werden; allerdings nur einmal pro Entität. Wenn sie auf eine Basisklasse angewendet wird, wird sie an eine abgeleitete Klasse vererbt.

Die Argumente `AllowMultiple` und `Inherited` sind optional, sodass dieser Code die gleiche Wirkung hat:

```vb
<System.AttributeUsage(System.AttributeTargets.All)>
Class NewAttribute
    Inherits System.Attribute
End Class
```

Das erste `AttributeUsage`-Argument muss mindestens ein Element der <xref:System.AttributeTargets>-Enumeration sein. Mehrere Zieltypen können mithilfe des OR-Operator wie folgt verknüpft werden:

```vb
<AttributeUsage(AttributeTargets.Property Or AttributeTargets.Field)>
Class NewPropertyOrFieldAttribute
    Inherits Attribute
End Class
```

Wenn das `AllowMultiple`-Argument auf `true` festgelegt ist, kann das daraus entstehende Attribut wie folgt mehr als einmal auf eine einzelne Entität angewendet werden:

```vb
<AttributeUsage(AttributeTargets.Class, AllowMultiple:=True)>
Class MultiUseAttr
    Inherits Attribute
End Class

<MultiUseAttr(), MultiUseAttr()>
Class Class1
End Class
```

In diesem Fall kann `MultiUseAttr` wiederholt angewendet werden, da `AllowMultiple` auf `true` festgelegt ist. Beide gezeigten Formate für das Anwenden von mehreren Attributen sind gültig.

Wenn `Inherited` auf `false` festgelegt ist, wird das Attribut nicht an die von der attribuierten Klasse abgeleiteten Klassen vererbt. Beispiel:

```vb
<AttributeUsage(AttributeTargets.Class, Inherited:=False)>
Class Attr1
    Inherits Attribute
End Class

<Attr1()>
Class BClass

End Class

Class DClass
    Inherits BClass
End Class
```

In diesem Fall wird `Attr1` nicht durch Vererbung auf `DClass` angewendet.

## <a name="remarks"></a>Hinweise

Das `AttributeUsage`-Attribut ist für die einmalige Nutzung bestimmt; es kann nicht mehr als einmal auf dieselbe Klasse angewendet werden. `AttributeUsage` ist ein Alias für <xref:System.AttributeUsageAttribute>.

Weitere Informationen finden Sie unter [Zugreifen auf Attribute mithilfe der Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).

## <a name="example"></a>Beispiel

In folgendem Beispiel wird die Wirkung der Argumente `Inherited` und `AllowMultiple` auf das Attribut `AttributeUsage` und die Enumeration benutzerdefinierter Attribute veranschaulicht, die auf eine Klasse angewendet wurden.

```vb
' Create some custom attributes:
<AttributeUsage(System.AttributeTargets.Class, Inherited:=False)>
Class A1
    Inherits System.Attribute
End Class

<AttributeUsage(System.AttributeTargets.Class)>
Class A2
    Inherits System.Attribute
End Class

<AttributeUsage(System.AttributeTargets.Class, AllowMultiple:=True)>
Class A3
    Inherits System.Attribute
End Class

' Apply custom attributes to classes:
<A1(), A2()>
Class BaseClass

End Class

<A3(), A3()>
Class DerivedClass
    Inherits BaseClass
End Class

Public Class TestAttributeUsage
    Sub Main()
        Dim b As New BaseClass
        Dim d As New DerivedClass
        ' Display custom attributes for each class.
        Console.WriteLine("Attributes on Base Class:")
        Dim attrs() As Object = b.GetType().GetCustomAttributes(True)

        For Each attr In attrs
            Console.WriteLine(attr)
        Next

        Console.WriteLine("Attributes on Derived Class:")
        attrs = d.GetType().GetCustomAttributes(True)
        For Each attr In attrs
            Console.WriteLine(attr)
        Next
    End Sub
End Class
```

## <a name="sample-output"></a>Beispielausgabe

```console
Attributes on Base Class:
A1
A2
Attributes on Derived Class:
A3
A3
A2
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Attribute>
- <xref:System.Reflection>
- [Visual Basic-Programmierhandbuch](../../../../visual-basic/programming-guide/index.md)
- [Attribute](../../../../standard/attributes/index.md)
- [Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)
- [Attribute (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)
- [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) (Erstellen benutzerdefinierter Attribute (Visual Basic))
- [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Zugreifen auf Attribute mithilfe der Reflektion (Visual Basic))
