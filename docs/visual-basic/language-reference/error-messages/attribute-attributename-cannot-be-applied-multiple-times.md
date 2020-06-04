---
title: Das Attribut "<attributename>" kann nicht mehrmals angewendet werden.
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 14145f165adf5ccd20298a70ca5596488b488b0c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409958"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a>Das Attribut "\<attributename>" kann nicht mehrmals angewendet werden.

Das-Attribut kann nur einmal angewendet werden. Das- `AttributeUsage` Attribut bestimmt, ob ein Attribut mehrmals angewendet werden kann.  
  
 **Fehler-ID:** BC30663  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Stellen Sie sicher, dass das-Attribut nur einmal angewendet wird.  
  
2. Wenn Sie von Ihnen entwickelte benutzerdefinierte Attribute verwenden, sollten Sie `AttributeUsage` das-Attribut ändern, um die Verwendung mehrerer Attribute zuzulassen, wie im folgenden Beispiel gezeigt.  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.AttributeUsageAttribute>
- [Erstellen benutzerdefinierter Attribute](../../programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../programming-guide/concepts/attributes/attributeusage.md)
