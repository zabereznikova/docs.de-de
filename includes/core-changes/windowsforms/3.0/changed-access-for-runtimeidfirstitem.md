---
ms.openlocfilehash: 1ea2d70a7cfe04cc4c4b9b58ea6bb6fa0226b245
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721120"
---
### <a name="change-of-access-for-accessibleobjectruntimeidfirstitem"></a>Zugriffsänderung für AccessibleObject.RuntimeIDFirstItem

Ab .NET Core 3.0 RC1 hat sich der Zugriff auf `AccessibleObject.RuntimeIDFirstItem` aus `protected` in `internal` geändert.

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET Core 3.0 Vorschau 4 war das Feld `AccessibleObject.RuntimeIDFirstItem` vom Typ `protected`. Ab .NET Core 3.0 RC1 wurde der Typ aus `protected` in `internal` geändert, um dem Zugriffstyp des Felds in .NET Framework zu entsprechen.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0 RC1

#### <a name="recommended-action"></a>Empfohlene Aktion

Die Änderung kann sich auf Sie auswirken, wenn Sie eine .NET Core-App mit einem Typ entwickelt haben, der von <xref:System.Windows.Forms.AccessibleObject> abgeleitet ist und auf das `RuntimeIDFirstItem`-Feld zugreift. Wenn dies der Fall ist, können Sie wie folgt eine lokale Konstante definieren:

```csharp
const int RuntimeIDFirstItem = 0x2a;
```

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

- Nicht über API-Analyse erkennbar.

<!-- 

#### Affected APIs

- Not detectable via API analysis.

-->
