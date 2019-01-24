---
title: Attribut &#39; &lt;Attributename&gt; &#39; kann nicht mehrmals angewendet werden
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 6609ce299799bc3c4b78d48478e99e4d4101dd72
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565162"
---
# <a name="attribute-39ltattributenamegt39-cannot-be-applied-multiple-times"></a>Attribut &#39; &lt;Attributename&gt; &#39; kann nicht mehrmals angewendet werden
Das Attribut kann nur einmal angewendet werden. Die `AttributeUsage` Attribut bestimmt, ob ein Attribut mehr als einmal angewendet werden kann.  
  
 **Fehler-ID:** BC30663  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass das Attribut nur einmal angewendet wird.  
  
2.  Wenn Sie benutzerdefinierte Attribute, die für Sie entwickelt haben verwenden werden, können Sie ändern die `AttributeUsage` Attribut, um die Verwendung von mehreren Attributen, wie Sie mit dem folgenden Beispiel zu ermöglichen.  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.AttributeUsageAttribute>
- [Erstellen benutzerdefinierter Attribute](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
