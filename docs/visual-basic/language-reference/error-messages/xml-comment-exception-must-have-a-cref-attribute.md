---
title: Eine XML-Kommentarausnahme benötigen eine &#39;Cref&#39; Attribut
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: abe9fe0f6216f81fa223fe83a122b580577e1c32
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43404764"
---
# <a name="xml-comment-exception-must-have-a-39cref39-attribute"></a>Eine XML-Kommentarausnahme benötigen eine &#39;Cref&#39; Attribut
Die \<Ausnahme >-Tag bietet eine Möglichkeit, die Ausnahmen zu dokumentieren, die von einer Methode ausgelöst werden können. Die erforderlichen `cref` -Attribut legt den Namen eines Members, der von der Dokumentations-Generator überprüft wird. Wenn das Element vorhanden ist, wird es in den kanonischen Elementnamen in der Dokumentationsdatei übersetzt.  
  
 **Fehler-ID:** BC42319  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Hinzufügen der `cref` -Attribut auf die Ausnahme wie folgt:  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)  
 [Gewusst wie: Erstellen einer XML-Dokumentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
