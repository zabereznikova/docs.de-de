---
title: 'Vorgehensweise: Bestimmen des Bezugs zwischen zwei Objekten'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: b33815d58b0ef40f7f75a6a41bb4b1eeef591859
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072222"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>Gewusst wie: Bestimmen des Bezugs zwischen zwei Objekten (Visual Basic)

Sie können zwei-Objekte vergleichen, um die Beziehung (sofern vorhanden) zwischen den Klassen zu bestimmen, von denen Sie erstellt werden. Die- <xref:System.Type.IsInstanceOfType%2A> Methode der- <xref:System.Type?displayProperty=nameWithType> Klasse gibt zurück `True` , wenn die angegebene Klasse von der aktuellen Klasse erbt, oder, wenn der aktuelle Typ eine Schnittstelle ist, die von der angegebenen Klasse unterstützt wird.

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>So bestimmen Sie, ob ein Objekt von der Klasse oder Schnittstelle eines anderen Objekts erbt

1. Rufen Sie für das Objekt, das Sie als Basistyp betrachten können, die- <xref:System.Object.GetType%2A> Methode auf.

2. Rufen Sie für das <xref:System.Type?displayProperty=nameWithType> von zurückgegebene-Objekt <xref:System.Object.GetType%2A> die-Methode auf <xref:System.Type.IsInstanceOfType%2A> .

3. Geben Sie in der Argumentliste für <xref:System.Type.IsInstanceOfType%2A> das Objekt an, das Sie möglicherweise vom abgeleiteten Typ haben.

    <xref:System.Type.IsInstanceOfType%2A> Gibt zurück, `True` Wenn der Argumenttyp vom <xref:System.Type?displayProperty=nameWithType> Objekttyp erbt.

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

Beachten Sie die unerwartete Platzierung der beiden Objektvariablen im-Befehl <xref:System.Type.IsInstanceOfType%2A> . Der vermeintliche Basistyp wird verwendet, um die <xref:System.Type?displayProperty=nameWithType> -Klasse zu generieren, und der vermeintliche abgeleitete Typ wird als Argument an die-Methode übermittelt <xref:System.Type.IsInstanceOfType%2A> .

## <a name="see-also"></a>Siehe auch

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Objektvariablen](object-variables.md)
- [Werte von Objektvariablen](object-variable-values.md)
- [Vorgehensweise: Bestimmen der Gleichheit zweier Objekte](how-to-determine-whether-two-objects-are-identical.md)
