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
ms.openlocfilehash: 0595356fb75fc0ac73a49622d71fe1d28fa7b648
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90865907"
---
# <a name="of-clause-visual-basic"></a>Of-Klausel (Visual Basic)

Führt eine- `Of` Klausel ein, die einen *Typparameter* für eine *generische* Klasse, Struktur, Schnittstelle, einen Delegaten oder eine Prozedur bezeichnet. Informationen zu generischen Typen finden Sie unter [generische Typen in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).  
  
## <a name="using-the-of-keyword"></a>Verwenden des of-Schlüssel Worts  

 Im folgenden Codebeispiel wird das- `Of` Schlüsselwort verwendet, um die Gliederung einer Klasse zu definieren, die zwei Typparameter annimmt. Der *constrains* - `keyType` Parameter wird von der- <xref:System.IComparable> Schnittstelle eingeschränkt, was bedeutet, dass der verarbeitende Code ein Typargument bereitstellen muss, das implementiert <xref:System.IComparable> . Dies ist erforderlich, damit die- `add` Prozedur die-Methode aufgerufen werden kann <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> . Weitere Informationen über Einschränkungen finden Sie unter [Type List](type-list.md).  
  
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
  
 Wenn Sie die vorherige Klassendefinition Fertigstellen, können Sie eine Vielzahl von `dictionary` Klassen daraus erstellen. Die Typen, die Sie angeben, `entryType` und `keyType` bestimmen, welche Art von Eintrag die Klasse enthält und welche Art von Schlüssel Sie den einzelnen Einträgen zuordnet. Aufgrund der-Einschränkung müssen Sie `keyType` einen Typ angeben, der implementiert <xref:System.IComparable> .  
  
 Im folgenden Codebeispiel wird ein-Objekt erstellt, das `String` -Einträge enthält und `Integer` jedem jeweils einen Schlüssel zuordnet. `Integer` implementiert <xref:System.IComparable> und erfüllt daher die Einschränkung für `keyType` .  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 Das `Of`-Schlüsselwort kann in den folgenden Kontexten verwendet werden:  
  
 [Class-Anweisung](class-statement.md)  
  
 [Delegate-Anweisung](delegate-statement.md)  
  
 [Function-Anweisung](function-statement.md)  
  
 [Interface-Anweisung](interface-statement.md)  
  
 [Structure Statement](structure-statement.md)  
  
 [Sub-Anweisung](sub-statement.md)  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IComparable>
- [Type List](type-list.md)
- [Generische Typen in Visual Basic (Visual Basic)](../../programming-guide/language-features/data-types/generic-types.md)
- [In](../modifiers/in-generic-modifier.md)
- [aus](../modifiers/out-generic-modifier.md)
