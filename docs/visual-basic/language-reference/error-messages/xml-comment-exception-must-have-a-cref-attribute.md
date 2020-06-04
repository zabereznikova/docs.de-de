---
title: Eine XML-Kommentarausnahme muss ein cref-Attribut aufweisen.
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: c498675ab6ae616fb63d3d76ef60bcac7e247145
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406507"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a>Eine XML-Kommentarausnahme muss ein cref-Attribut aufweisen.

Das- \<exception> Tag bietet eine Möglichkeit, die Ausnahmen zu dokumentieren, die möglicherweise von einer Methode ausgelöst werden. Das erforderliche `cref` Attribut gibt den Namen eines Members an, der vom Dokumentations Generator geprüft wird. Wenn der Member vorhanden ist, wird er in den kanonischen Elementnamen in der Dokumentations Datei übersetzt.

**Fehler-ID:** BC42319

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

Fügen Sie der Ausnahme das- `cref` Attribut wie folgt hinzu:

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a>Weitere Informationen

- [\<exception>](../xmldoc/exception.md)
- [Vorgehensweise: Erstellen einer XML-Dokumentation](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML-Kommentartags](../xmldoc/index.md)
