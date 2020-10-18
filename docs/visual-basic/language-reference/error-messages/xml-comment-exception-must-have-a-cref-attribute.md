---
title: Eine XML-Kommentarausnahme muss ein cref-Attribut aufweisen.
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 18e7aa5f6905eaa9c509aa21fe6f5bfcd54d46f0
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163297"
---
# <a name="bc42319-xml-comment-exception-must-have-a-cref-attribute"></a>BC42319: die XML-Kommentar Ausnahme muss ein "kref"-Attribut aufweisen.

Das- \<exception> Tag bietet eine Möglichkeit, die Ausnahmen zu dokumentieren, die möglicherweise von einer Methode ausgelöst werden. Das erforderliche `cref` Attribut gibt den Namen eines Members an, der vom Dokumentations Generator geprüft wird. Wenn der Member vorhanden ist, wird er in den kanonischen Elementnamen in der Dokumentations Datei übersetzt.

**Fehler-ID:** BC42319

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

Fügen Sie der Ausnahme das- `cref` Attribut wie folgt hinzu:

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a>Siehe auch

- [\<exception>](../xmldoc/exception.md)
- [Vorgehensweise: Erstellen einer XML-Dokumentation](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML-Kommentartags](../xmldoc/index.md)
