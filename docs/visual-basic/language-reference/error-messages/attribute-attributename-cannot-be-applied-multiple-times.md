---
title: Das Attribut "<attributename>" kann nicht mehrmals angewendet werden.
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: f2f4dc428a247275f9919c4a8b6e6944a558eef0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968225"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a>Das Attribut '\<AttributeName > ' kann nicht mehrmals angewendet werden.

Das-Attribut kann nur einmal angewendet werden. Das `AttributeUsage`-Attribut bestimmt, ob ein Attribut mehrmals angewendet werden kann.  
  
 **Fehler-ID:** BC30663  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Stellen Sie sicher, dass das-Attribut nur einmal angewendet wird.  
  
2. Wenn Sie benutzerdefinierte Attribute verwenden, die Sie entwickelt haben, sollten Sie das `AttributeUsage` Attribut ändern, um die Verwendung mehrerer Attribute zuzulassen, wie im folgenden Beispiel gezeigt.  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.AttributeUsageAttribute>
- [Erstellen benutzerdefinierter Attribute](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
