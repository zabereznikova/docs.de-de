---
ms.openlocfilehash: 5bbbf9075683b0f124e126b661b4ab85011e6c2e
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643928"
---
### <a name="change-of-access-for-accessibleobjectruntimeidfirstitem"></a>Zugriffsänderung für AccessibleObject.RuntimeIDFirstItem

Ab .NET Core 3.0 RC1 hat sich der Zugriff auf `AccessibleObject.RuntimeIDFirstItem` aus `protected` in `internal` geändert.

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET Core 3.0 Vorschau 4 war das Feld `AccessibleObject.RuntimeIDFirstItem` vom Typ `protected`. Ab .NET Core 3.0 RC1 wurde der Typ aus `protected` in `internal` geändert, um dem Zugriffstyp des Felds in .NET Framework zu entsprechen.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0 RC1

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Die Änderung kann sich auf Sie auswirken, wenn Sie eine .NET Core-App mit einem Typ entwickelt haben, der von <xref:System.Windows.Forms.AccessibleObject> abgeleitet ist und auf das `RuntimeIDFirstItem`-Feld zugreift. Wenn dies der Fall ist, können Sie wie folgt eine lokale Konstante definieren:

```csharp
const int RuntimeIDFirstItem = 0x2a;
```

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

- Nicht über API-Analyse erkennbar.

<!-- 

### Affected APIs

- Not detectable via API analysis.

-->
