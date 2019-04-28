---
title: 'Vorgehensweise: Bestimmen, ob zwei Objekten zwischen Bezugs (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: f59e00d80d28fc4bf24874d25b5c12643649c834
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769069"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>Vorgehensweise: Bestimmen, ob zwei Objekten zwischen Bezugs (Visual Basic)
Sie können vergleichen zwei Objekte, um die Beziehung zwischen den Klassen ggf. zu bestimmen, von dem sie erstellt werden. Die <xref:System.Type.IsInstanceOfType%2A> Methode der <xref:System.Type?displayProperty=nameWithType> -Klasse gibt `True` , wenn die angegebene Klasse von der aktuellen Klasse erbt oder der aktuelle Typ eine Schnittstelle, unterstützt durch die angegebene Klasse ist.  
  
### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>Um festzustellen, ob ein Objekt von einem anderen Objekt der Klasse oder Schnittstelle erbt  
  
1. Für das Objekt, das Sie denken des Basistyps, rufen Sie die <xref:System.Object.GetType%2A> Methode.  
  
2. Auf der <xref:System.Type?displayProperty=nameWithType> zurückgegebenes Objekt <xref:System.Object.GetType%2A>, rufen Sie die <xref:System.Type.IsInstanceOfType%2A> Methode.  
  
3. In der Argumentliste für <xref:System.Type.IsInstanceOfType%2A>, geben Sie das Objekt, das Sie denken möglicherweise des abgeleiteten Typs.  
  
     <xref:System.Type.IsInstanceOfType%2A> Gibt `True` Falls Argumenttyps erbt die <xref:System.Type?displayProperty=nameWithType> Objekttyp.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird bestimmt, ob ein Objekt eine von einer anderen Klasse abgeleitete Klasse darstellt.  
  
```  
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
  
 Beachten Sie die unerwartete Platzierung der zwei Variablen im Aufruf von <xref:System.Type.IsInstanceOfType%2A>. Der angenommene Basistyp dient zum Generieren der <xref:System.Type?displayProperty=nameWithType> -Klasse, und der angenommene abgeleitete Typ wird als Argument für das Übergeben der <xref:System.Type.IsInstanceOfType%2A> Methode.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Werte von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Vorgehensweise: Bestimmt, ob zwei Objekte identisch sind.](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
