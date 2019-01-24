---
title: '&#39;Erweiterung&#39; Attribut kann nur angewendet werden &#39;Modul&#39;, &#39;Sub&#39;, oder &#39;Funktion&#39; Deklarationen'
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: fabd602f31a362fe33954253d565e86a065e0a83
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718233"
---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a>&#39;Erweiterung&#39; Attribut kann nur angewendet werden &#39;Modul&#39;, &#39;Sub&#39;, oder &#39;Funktion&#39; Deklarationen
Die einzige Möglichkeit zum Erweitern von eines Datentyps in Visual Basic ist eine Erweiterungsmethode in einem Standardmodul definieren. Die Erweiterungsmethode möglich ein `Sub` Prozedur oder ein `Function` Verfahren. Alle Erweiterungsmethoden müssen mit dem Extension-Attribut markiert werden `<Extension()>`, aus der <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> Namespace. Optional kann ein Modul, eine Erweiterungsmethode enthält, auf die gleiche Weise gekennzeichnet werden. Keine andere Verwendung der das Extension-Attribut ist ungültig.  
  
 **Fehler-ID:** BC36550  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie das Extension-Attribut.  
  
-   Entwerfen Sie die Erweiterung als eine Methode, in ein einschließendes Modul definiert.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert eine `Print` -Methode für die `String` -Datentyp.  
  
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
- [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Erweiterungsmethoden](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [Module-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md)
