---
title: Das Attribut "<attributename>" kann nicht mehrmals angewendet werden.
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 27cbe6d0043179c4a5d52baae06bad805f9d1d3a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162660"
---
# <a name="bc30663-attribute-attributename-cannot-be-applied-multiple-times"></a>BC30663: das Attribut " \<attributename> " kann nicht mehrmals angewendet werden.

Das-Attribut kann nur einmal angewendet werden. Das- `AttributeUsage` Attribut bestimmt, ob ein Attribut mehrmals angewendet werden kann.

 **Fehler-ID:** BC30663

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Stellen Sie sicher, dass das-Attribut nur einmal angewendet wird.

2. Wenn Sie von Ihnen entwickelte benutzerdefinierte Attribute verwenden, sollten Sie `AttributeUsage` das-Attribut ändern, um die Verwendung mehrerer Attribute zuzulassen, wie im folgenden Beispiel gezeigt.

```vb
<AttributeUsage(AllowMultiple := True)>
```

## <a name="see-also"></a>Siehe auch

- <xref:System.AttributeUsageAttribute>
- [Erstellen benutzerdefinierter Attribute](../../programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../programming-guide/concepts/attributes/attributeusage.md)
