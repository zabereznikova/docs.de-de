---
title: Of-Klausel
ms.date: 07/20/2015
f1_keywords:
- Of
- vb.Of
- vb.of
helpviewer_keywords:
- Of keyword [Visual Basic]
- arguments [Visual Basic], data types
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
ms.openlocfilehash: d88c43efe858d6b81b7d8d2470b234ff5d40632a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353844"
---
# <a name="of-clause-visual-basic"></a>Of-Klausel (Visual Basic)
Führt eine `Of`-Klausel ein, die einen *Typparameter* für eine *generische* Klasse, Struktur, Schnittstelle, einen Delegaten oder eine Prozedur bezeichnet. Informationen zu generischen Typen finden Sie unter [generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).  
  
## <a name="using-the-of-keyword"></a>Verwenden des of-Schlüssel Worts  
 Im folgenden Codebeispiel wird das `Of`-Schlüsselwort verwendet, um die Gliederung einer Klasse zu definieren, die zwei Typparameter annimmt. Dadurch wird der `keyType` Parameter durch die <xref:System.IComparable> Schnittstelle *eingeschränkt* , was bedeutet, dass der verarbeitende Code ein Typargument bereitstellen muss, das <xref:System.IComparable>implementiert. Dies ist erforderlich, damit die `add` Prozedur die <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType>-Methode aufgerufen werden kann. Weitere Informationen über Einschränkungen finden Sie unter [Type List](../../../visual-basic/language-reference/statements/type-list.md).  
  
```vb  
Public Class Dictionary(Of entryType, keyType As IComparable)  
    Public Sub add(ByVal e As entryType, ByVal k As keyType)  
        Dim dk As keyType  
        If k.CompareTo(dk) = 0 Then  
        End If  
    End Sub  
    Public Function find(ByVal k As keyType) As entryType  
    End Function  
End Class  
```  
  
 Wenn Sie die vorherige Klassendefinition Fertigstellen, können Sie eine Vielzahl von `dictionary` Klassen daraus erstellen. Die Typen, die Sie angeben, um `entryType` und `keyType` bestimmen, welche Art von Eintrag die Klasse enthält und welche Art von Schlüssel Sie den einzelnen Einträgen zuordnet. Aufgrund der-Einschränkung müssen Sie angeben, um einen Typ `keyType`, der <xref:System.IComparable>implementiert.  
  
 Im folgenden Codebeispiel wird ein-Objekt erstellt, das `String` Einträge enthält und jedem ein `Integer` Schlüssel zuordnet. `Integer` implementiert <xref:System.IComparable> und erfüllt daher die Einschränkung für `keyType`.  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 Das `Of`-Schlüsselwort kann in den folgenden Kontexten verwendet werden:  
  
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IComparable>
- [Typliste](../../../visual-basic/language-reference/statements/type-list.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
