---
title: Eine XML-Kommentarausnahme muss ein cref-Attribut aufweisen.
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 2e57dc63cb7ad8b2e061296a082d6fa79b464f08
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592039"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a>Eine XML-Kommentarausnahme muss ein cref-Attribut aufweisen.
Das > Tag \<exception bietet eine Möglichkeit, die Ausnahmen zu dokumentieren, die möglicherweise von einer Methode ausgelöst werden. Das erforderliche `cref`-Attribut legt den Namen eines Members fest, der vom Dokumentations Generator geprüft wird. Wenn der Member vorhanden ist, wird er in den kanonischen Elementnamen in der Dokumentations Datei übersetzt.  
  
 **Fehler-ID:** BC42319  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Fügen Sie der Ausnahme das `cref`-Attribut wie folgt hinzu:  
  
    xml  
    <exception cref="member">Beschreibung</exception> von ""  
    ```  
  
## See also

- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md)
