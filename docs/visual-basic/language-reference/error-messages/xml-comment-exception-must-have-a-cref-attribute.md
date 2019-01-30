---
title: Eine XML-Kommentarausnahme muss ein cref-Attribut aufweisen.
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: a11bfe261ffb8ded95f2e513aaddf00aa00f702e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266636"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a>Eine XML-Kommentarausnahme muss ein cref-Attribut aufweisen.
Die \<Ausnahme >-Tag bietet eine Möglichkeit, die Ausnahmen zu dokumentieren, die von einer Methode ausgelöst werden können. Die erforderlichen `cref` -Attribut legt den Namen eines Members, der von der Dokumentations-Generator überprüft wird. Wenn das Element vorhanden ist, wird es in den kanonischen Elementnamen in der Dokumentationsdatei übersetzt.  
  
 **Fehler-ID:** BC42319  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Hinzufügen der `cref` -Attribut auf die Ausnahme wie folgt:  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a>Siehe auch
- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [Vorgehensweise: Erstellen von XML-Dokumentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
