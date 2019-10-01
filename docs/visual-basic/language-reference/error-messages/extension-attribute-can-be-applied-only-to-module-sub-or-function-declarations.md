---
title: Das Extension-Attribut darf nur in Module-, Sub- oder Function-Deklarationen verwendet werden
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: 95a67a552efacf9e77dc3ebc3e0187817a6d82e2
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698585"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a>Das Extension-Attribut darf nur in Module-, Sub- oder Function-Deklarationen verwendet werden
Die einzige Möglichkeit zum Erweitern eines Datentyps in Visual Basic besteht darin, eine Erweiterungsmethode in einem Standardmodul zu definieren. Bei der Erweiterungsmethode kann es sich um eine `Sub`-Prozedur oder um eine `Function`-Prozedur handeln. Alle Erweiterungs Methoden müssen mit dem Erweiterungs Attribut `<Extension()>` aus dem <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>-Namespace gekennzeichnet werden. Optional kann ein Modul, das eine Erweiterungsmethode enthält, auf dieselbe Weise gekennzeichnet werden. Keine andere Verwendung des Erweiterungs Attributs ist gültig.  
  
 **Fehler-ID:** BC36550  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Entfernen Sie das Erweiterungs Attribut.  
  
- Entwerfen Sie Ihre Erweiterung als eine Methode, die in einem umschließenden Modul definiert ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `Print`-Methode für den `String`-Datentyp definiert.  
  
```vb  
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
