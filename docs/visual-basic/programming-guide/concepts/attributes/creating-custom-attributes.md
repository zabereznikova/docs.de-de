---
title: Erstellen von benutzerdefinierten Attributen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1aa97a591fdbdfab931a8b5e4f70ec3c00762332
ms.lasthandoff: 03/13/2017

---
# <a name="creating-custom-attributes-visual-basic"></a>Erstellen von benutzerdefinierten Attributen (Visual Basic)
Sie können eigene benutzerdefinierte Attribute erstellen, durch die Definition einer Attributklasse, die eine Klasse, die direkt oder indirekt abgeleitet <xref:System.Attribute>, welche identifizieren Attributdefinitionen, die in den Metadaten, die schnell und einfach macht.</xref:System.Attribute> Angenommen Sie, Sie Tagtypen mit dem Namen des Programmierers, die den Typ erstellt hat. Sie definieren eine benutzerdefinierte `Author` Attributklasse:  
  
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
  
 Der Klassenname ist der Attributname `Author`. Sie ist abgeleitet von `System.Attribute`, sodass eine benutzerdefinierte Attributklasse. Die Parameter des Konstruktors sind Positionsparameter des benutzerdefinierten Attributs. In diesem Beispiel `name` ist ein Positionsparameter. Alle öffentlichen Schreib-Lese-Felder oder Eigenschaften sind benannte Parameter. In diesem Fall `version` ist der einzige benannte Parameter. Beachten Sie, dass die `AttributeUsage` -Attribut der `Author` Attribut gilt nur für die Klasse und `Structure` Deklarationen.  
  
 Sie könnten dieses neue Attribut wie folgt verwenden:  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 `AttributeUsage`hat einen benannten Parameter, `AllowMultiple`, mit denen Sie ein benutzerdefiniertes Attribut einfache oder mehrfache Verwendung konfiguriert werden können. Im folgenden Codebeispiel wird ein mehrfach verwendbares Attribut erstellt.  
  
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
>  Wenn die Attributklasse eine Eigenschaft enthält, muss die Eigenschaft Lese-/ Schreibzugriff sein.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Reflection></xref:System.Reflection>   
 [Visual Basic-Programmierhandbuch](../../../../visual-basic/programming-guide/index.md)   
 [Verfassen von benutzerdefinierten Attributen](http://msdn.microsoft.com/library/97216f69-bde8-49fd-ac40-f18c500ef5dc)   
 [Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)   
 [Attribute (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)   
 [Zugriff auf Attribute mit Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)   
 [AttributeUsage (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
