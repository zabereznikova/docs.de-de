---
title: '&#39;Erweiterung&#39; Attribut kann nur für angewendet &#39;Modul&#39;, &#39;Sub&#39;, oder &#39;Funktion&#39; Deklarationen'
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: d7f8829cb879d612711ac6bcc6bf4aa065fbe323
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a>&#39;Erweiterung&#39; Attribut kann nur für angewendet &#39;Modul&#39;, &#39;Sub&#39;, oder &#39;Funktion&#39; Deklarationen
Die einzige Möglichkeit zum Erweitern eines Datentyps in Visual Basic werden Erweiterungsmethoden innerhalb eines Moduls, standard definiert werden. Die Erweiterungsmethode kann eine `Sub` Prozedur oder eine `Function` Prozedur. Alle Erweiterungsmethoden müssen mit dem Erweiterungsattribut markiert werden `<Extension()>`, aus der <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> Namespace. Optional kann ein Modul, eine Erweiterungsmethode enthält, auf die gleiche Weise markiert werden. Keine andere Verwendung von Extension-Attribut ist ungültig.  
  
 **Fehler-ID:** BC36550  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie das Extension-Attribut.  
  
-   Entwerfen Sie die Erweiterung als eine Methode, die in ein einschließendes Modul definiert.  
  
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
