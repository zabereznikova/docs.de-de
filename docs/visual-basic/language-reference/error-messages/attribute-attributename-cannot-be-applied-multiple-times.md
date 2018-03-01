---
title: Attribut &#39; &lt;Attributename&gt;&#39; kann nicht mehrmals angewendet werden
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 216cf54fd164ca95b6378517a679b5b54183559f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="attribute-39ltattributenamegt39-cannot-be-applied-multiple-times"></a>Attribut &#39; &lt;Attributename&gt;&#39; kann nicht mehrmals angewendet werden
Das Attribut kann nur einmal angewendet werden. Die `AttributeUsage` Attribut ermittelt, ob ein Attribut mehr als einmal angewendet werden kann.  
  
 **Fehler-ID:** BC30663  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass das Attribut nur einmal angewendet wird.  
  
2.  Wenn Sie benutzerdefinierte Attribute Sie entwickelt haben verwenden, können Sie ändern die `AttributeUsage` Attribut, um mehreren Attributen, wie anhand des folgenden Beispiels zu ermöglichen.  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.AttributeUsageAttribute>  
 [Erstellen benutzerdefinierter Attribute](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
