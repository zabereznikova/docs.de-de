---
title: Eine XML-Kommentarausnahme muss ein cref-Attribut aufweisen.
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 54965f3796b6c5ef0e387cd354abcb5740476257
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321172"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a>Eine XML-Kommentarausnahme muss ein cref-Attribut aufweisen.

Das > Tag \<exception bietet eine Möglichkeit, die Ausnahmen zu dokumentieren, die möglicherweise von einer Methode ausgelöst werden. Das erforderliche `cref`-Attribut legt den Namen eines Members fest, der vom Dokumentations Generator geprüft wird. Wenn der Member vorhanden ist, wird er in den kanonischen Elementnamen in der Dokumentations Datei übersetzt.

**Fehler-ID:** BC42319

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

Fügen Sie der Ausnahme das `cref`-Attribut wie folgt hinzu:

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a>Siehe auch

- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [Gewusst wie: Erstellen einer XML-Dokumentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
