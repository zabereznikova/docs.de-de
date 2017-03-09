---
title: "Of Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "Of"
  - "vb.Of"
  - "vb.of"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Of keyword"
  - "arguments [Visual Basic], data types"
  - "constraints, Visual Basic generic types"
  - "generic parameters"
  - "generics [Visual Basic], constraints"
  - "parameters, type"
  - "types [Visual Basic], generic"
  - "parameters, generic"
  - "type parameters"
  - "data type arguments"
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Of Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Leitet eine `Of`\-Klausel ein, die in einer *generischen* Klasse, Struktur, Schnittstelle, Prozedur oder in einem Delegaten einen *Typparameter* identifiziert.  Informationen zu generischen Typen finden Sie unter [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).  
  
## Verwenden des Of\-Schlüsselworts  
 Im folgenden Codebeispiel wird mithilfe des `Of`\-Schlüsselworts die Gliederung in einer Klasse definiert, die zwei Typparameter annimmt.  Das Schlüsselwort *beschränkt* den `keyType`\-Parameter durch die <xref:System.IComparable>\-Schnittstelle; d. h., der verwendete Code muss ein Typargument bereitstellen, das <xref:System.IComparable> implementiert.  Dies ist notwendig, damit die `add`\-Prozedur die <xref:System.IComparable.CompareTo%2A?displayProperty=fullName>\-Methode aufrufen kann.  Weitere Informationen über Einschränkungen finden Sie unter [Type List](../../../visual-basic/language-reference/statements/type-list.md).  
  
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
  
 Wenn Sie die vorangehende Klassendefinition vervollständigen, können Sie eine Vielzahl von `dictionary`\-Klassen daraus konstruieren.  Durch die Typen, die Sie für `entryType` und `keyType` vorgeben, wird bestimmt, welchen Eintragstyp die Klasse enthält und welchen Schlüsseltyp sie den Einträgen zuordnet.  Aufgrund der Einschränkung müssen Sie für `keyType` einen Typ angeben, der <xref:System.IComparable> implementiert.  
  
 Im folgenden Codebeispiel wird ein Objekt erstellt, das `String`\-Einträge enthält und jedem Objekt einen `Integer`\-Schlüssel zuordnet.  `Integer` implementiert <xref:System.IComparable> und entspricht der Einschränkung auf `keyType`.  
  
```  
Dim d As New dictionary(Of String, Integer)  
```  
  
 Das `Of`\-Schlüsselwort kann in den folgenden Kontexten verwendet werden:  
  
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Delegate\-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Function\-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface\-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub\-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Siehe auch  
 <xref:System.IComparable>   
 [Type List](../../../visual-basic/language-reference/statements/type-list.md)   
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)   
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)