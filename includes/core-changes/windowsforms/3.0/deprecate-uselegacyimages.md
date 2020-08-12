---
ms.openlocfilehash: d69f619522c7abc3171f1c089e53cc2754899f93
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556175"
---
### <a name="uselegacyimages-compatibility-switch-not-supported"></a>Kompatibilitätsoption UseLegacyImages wird nicht unterstützt

Der mit .NET Framework 4.8 eingeführte Kompatibilitätsswitch `Switch.System.Windows.Forms.UseLegacyImages` wird in Windows Forms unter .NET Core oder .NET 5.0 oder höher nicht unterstützt.

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET Framework 4.8 werden mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.UseLegacyImages` mögliche Bildskalierungsprobleme in ClickOnce-Szenarios in Umgebungen mit hohem DPI-Wert behoben. Wenn der Switch auf `true` festgelegt wird, kann der Benutzer die Legacybildskalierung in Anzeigen mit hohem DPI-Wert wiederherstellen, deren Skalierung auf mehr als 100 % festgelegt ist. Weitere Informationen finden Sie unter [Versionshinweise zu .NET Framework 4.8](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) auf GitHub.

In .NET Core und .NET 5.0 oder höher wird der `Switch.System.Windows.Forms.UseLegacyImages`-Switch nicht unterstützt.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Entfernen Sie den Switch. Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

- Keiner

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
