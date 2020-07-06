---
ms.openlocfilehash: e9d34465970287ed94c0f0373ee4ae94d55aa1ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617177"
---
### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a>Die Methoden MachineKey.Encode und MachineKey.Decode sind jetzt veraltet

#### <a name="details"></a>Details

Diese Methoden sind jetzt veraltet. Die Kompilierung von Code, der diese Methoden aufruft, erzeugt eine Compilerwarnung.

#### <a name="suggestion"></a>Vorschlag

Die empfohlenen Alternativen sind <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> und <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>. Alternativ können die Buildwarnungen unterdrückt oder durch die Verwendung eines älteren Compilers vermieden werden. Die APIs werden weiterhin unterstützt.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.5         |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType>
- <xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType>
