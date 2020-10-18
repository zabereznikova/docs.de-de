---
title: XML-Entitätsverweise werden nicht unterstützt
ms.date: 07/20/2015
f1_keywords:
- vbc31180
- bc31180
helpviewer_keywords:
- BC31180
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
ms.openlocfilehash: 37e72dbd6de61a50b4192a0151db40cb4be49d1c
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163271"
---
# <a name="bc31180-xml-entity-references-are-not-supported"></a>BC31180: XML-Entitäts Verweise werden nicht unterstützt.

Ein Entitäts Verweis (z. b. `©` ), der nicht in der XML 1,0-Spezifikation definiert ist, ist als Wert für ein XML-Literalzeichen enthalten. Nur `&` `"` -, `<` -, `>` -,-und `'` XML-Entitäts Verweise werden in XML-Literalen unterstützt.

 **Fehler-ID:** BC31180

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Entfernen Sie den nicht unterstützten Entitäts Verweis.

## <a name="see-also"></a>Siehe auch

- [XML-Literale und die XML 1.0-Spezifikation](../../programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)
- [XML-Literale](../xml-literals/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
