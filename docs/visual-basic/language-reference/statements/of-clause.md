---
title: Of-Klausel (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5ef3ac4ac88727b1dcae50fa14abde03f29a16fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="of-clause-visual-basic"></a>Of-Klausel (Visual Basic)
Führt eine `Of` -Klausel, die identifiziert eine *Typparameter* auf eine *generischen* -Klasse, Struktur, Schnittstelle, Delegat oder Prozedur. Informationen zu generischen Typen finden Sie unter [generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).  
  
## <a name="using-the-of-keyword"></a>Mit dem Schlüsselwort  
 Im folgenden Codebeispiel wird mit der `Of` Schlüsselwort, um den Umriss einer Klasse definieren, die zwei Typparameter erhält. Es *schränkt* der `keyType` Parameters, indem die <xref:System.IComparable> -Schnittstelle, d. h., der verwendete Code ein Typargument, das implementiert angeben muss <xref:System.IComparable>. Dies ist erforderlich, damit die `add` Prozeduraufruf können die <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> Methode. Weitere Informationen zu Einschränkungen finden Sie unter [Typliste](../../../visual-basic/language-reference/statements/type-list.md).  
  
```  
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
  
 Wenn Sie die vorangehende Klassendefinition abgeschlossen haben, können Sie eine Vielzahl von erstellen `dictionary` Klassen daraus. Die Typen, die Sie, um angeben `entryType` und `keyType` zu bestimmen, welche Art des Eintrags die Klasse enthält, und welche Art von Schlüssel dieser mit jeder Eintrag verknüpft. Aufgrund der Einschränkung müssen Sie angeben `keyType` ein Typ, der implementiert <xref:System.IComparable>.  
  
 Das folgende Codebeispiel erstellt ein Objekt, das enthält `String` Einträge und ordnet eine `Integer` mit den einzelnen Schlüssel. `Integer`implementiert <xref:System.IComparable> und erfüllt daher die Einschränkung auf `keyType`.  
  
```  
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
 <xref:System.IComparable>  
 [Typliste](../../../visual-basic/language-reference/statements/type-list.md)  
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
