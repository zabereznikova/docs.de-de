---
title: 'Vorgehensweise: Bestimmen, ob zwei Objekte verwandt sind (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: 2b17be4ef5a7dabfc4779ab6f5675cc2baec9c3c
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626558"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>Vorgehensweise: Bestimmen, ob zwei Objekte verwandt sind (Visual Basic)

Sie können zwei-Objekte vergleichen, um die Beziehung (sofern vorhanden) zwischen den Klassen zu bestimmen, von denen Sie erstellt werden. Die <xref:System.Type.IsInstanceOfType%2A> -Methode <xref:System.Type?displayProperty=nameWithType> der-Klasse `True` gibt zurück, wenn die angegebene Klasse von der aktuellen Klasse erbt, oder, wenn der aktuelle Typ eine Schnittstelle ist, die von der angegebenen Klasse unterstützt wird.

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>So bestimmen Sie, ob ein Objekt von der Klasse oder Schnittstelle eines anderen Objekts erbt

1. Rufen Sie für das Objekt, das Sie als Basistyp betrachten können, <xref:System.Object.GetType%2A> die-Methode auf.

2. Rufen Sie <xref:System.Type?displayProperty=nameWithType> für das von <xref:System.Object.GetType%2A>zurückgegebene- <xref:System.Type.IsInstanceOfType%2A> Objekt die-Methode auf.

3. Geben Sie in der Argument <xref:System.Type.IsInstanceOfType%2A>Liste für das Objekt an, das Sie möglicherweise vom abgeleiteten Typ haben.

    <xref:System.Type.IsInstanceOfType%2A>gibt `True` zurück, wenn der <xref:System.Type?displayProperty=nameWithType> Argumenttyp vom Objekttyp erbt.

## <a name="example"></a>Beispiel
 Im folgenden Beispiel wird bestimmt, ob ein-Objekt eine Klasse darstellt, die von der Klasse eines anderen Objekts abgeleitet wurde.

```vb
Public Class baseClass
End Class
Public Class derivedClass : Inherits baseClass
End Class
Public Class testTheseClasses
    Public Sub seeIfRelated()
        Dim baseObj As Object = New baseClass()
        Dim derivedObj As Object = New derivedClass()
        Dim related As Boolean
        related = baseObj.GetType().IsInstanceOfType(derivedObj)
        MsgBox(CStr(related))
    End Sub
End Class
```

Beachten Sie die unerwartete Platzierung der beiden Objektvariablen im <xref:System.Type.IsInstanceOfType%2A>-Befehl. Der vermeintliche Basistyp wird verwendet, um die <xref:System.Type?displayProperty=nameWithType> -Klasse zu generieren, und der vermeintliche abgeleitete Typ wird als Argument <xref:System.Type.IsInstanceOfType%2A> an die-Methode übermittelt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Werte von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Vorgehensweise: Bestimmen, ob zwei Objekte identisch sind](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
