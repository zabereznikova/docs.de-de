---
title: Das Extension-Attribut kann nur auf &quot;Module&quot;, &quot;Sub&quot; oder &quot;Function&quot; Deklarationen angewendet werden | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36550
- vbc36550
dev_langs:
- VB
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3eee008f737bf625023b6e4d58e1df7d282148d3
ms.lasthandoff: 03/13/2017

---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a>Das Extension-Attribut kann nur auf "Module", "Sub" oder "Function" Deklarationen angewendet werden
Die einzige Möglichkeit zum Erweitern von eines Datentyps in Visual Basic ist eine Erweiterungsmethode innerhalb eines Standardmoduls definieren. Die Erweiterungsmethode kann eine `Sub` Prozedur oder ein `Function` Verfahren. Alle Erweiterungsmethoden müssen mit dem Extension-Attribut markiert werden `<Extension()>`, aus der <xref:System.Runtime.CompilerServices?displayProperty=fullName>Namespace.</xref:System.Runtime.CompilerServices?displayProperty=fullName> Optional kann ein Modul, das eine Erweiterungsmethode enthält, auf die gleiche Weise markiert werden. Eine andere Verwendung des Extension-Attribut ist ungültig.  
  
 **Fehler-ID:** BC36550  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie das Extension-Attribut.  
  
-   Entwerfen Sie die Erweiterung als eine Methode, die in einem einschließenden Modul definiert.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert eine `Print` Methode für die `String` -Datentyp.  
  
```  
Imports StringUtility  
Imports System.Runtime.CompilerServices  
Namespace StringUtility  
    <Extension()>   
    Module StringExtensions  
        <Extension()>   
        Public Sub Print (ByVal str As String)  
            Console.WriteLine(str)  
        End Sub  
    End Module  
End Namespace  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)   
 [Erweiterungsmethoden](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)   
 [Module-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md)
