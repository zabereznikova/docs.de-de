---
title: 'Gewusst wie: Bestimmen des Bezugs zwischen zwei Objekten'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: b3f5fc017166ba9cf28359db5de850c81b73bd69
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348627"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>Gewusst wie: Bestimmen des Bezugs zwischen zwei Objekten (Visual Basic)

Sie können zwei-Objekte vergleichen, um die Beziehung (sofern vorhanden) zwischen den Klassen zu bestimmen, von denen Sie erstellt werden. Die <xref:System.Type.IsInstanceOfType%2A>-Methode der <xref:System.Type?displayProperty=nameWithType> Klasse gibt `True` zurück, wenn die angegebene Klasse von der aktuellen Klasse erbt, oder, wenn der aktuelle Typ eine Schnittstelle ist, die von der angegebenen Klasse unterstützt wird.

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>So bestimmen Sie, ob ein Objekt von der Klasse oder Schnittstelle eines anderen Objekts erbt

1. Rufen Sie für das Objekt, das Sie denken, möglicherweise den Basistyp auf, die <xref:System.Object.GetType%2A>-Methode auf.

2. Rufen Sie für das von <xref:System.Object.GetType%2A>zurückgegebene <xref:System.Type?displayProperty=nameWithType> Objekt die <xref:System.Type.IsInstanceOfType%2A>-Methode auf.

3. Geben Sie in der Argumentliste für <xref:System.Type.IsInstanceOfType%2A>das Objekt an, das Sie möglicherweise vom abgeleiteten Typ haben.

    <xref:System.Type.IsInstanceOfType%2A> gibt `True` zurück, wenn der Argumenttyp vom <xref:System.Type?displayProperty=nameWithType> Objekttyp erbt.

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

Beachten Sie die unerwartete Platzierung der beiden Objektvariablen im <xref:System.Type.IsInstanceOfType%2A>-Aufrufe. Der vermeintliche Basistyp wird verwendet, um die <xref:System.Type?displayProperty=nameWithType>-Klasse zu generieren, und der vermeintliche abgeleitete Typ wird als Argument an die <xref:System.Type.IsInstanceOfType%2A>-Methode übermittelt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Werte von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Gewusst wie: Bestimmen der Gleichheit zweier Objekte](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
