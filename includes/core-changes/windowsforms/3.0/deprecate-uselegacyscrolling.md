---
ms.openlocfilehash: ee4a27dde9f1e7756401e3d8b709514082f5d3b1
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556179"
---
### <a name="domainupdownuselegacyscrolling-compatibility-switch-not-supported"></a>Kompatibilitätsoption DomainUpDown.UseLegacyScrolling wird nicht unterstützt

Der mit .NET Framework 4.7.1 eingeführte Kompatibilitätsswitch `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` wird in Windows Forms unter .NET Core oder .NET 5.0 oder höher nicht unterstützt.

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET Framework 4.7.1 können Entwickler mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` die unabhängigen Aktionen <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> und <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> abstellen. Mit dem Switch wird das Legacyverhalten wiederhergestellt, bei dem <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> ignoriert wird, wenn Kontexttext vorhanden ist, und der Entwickler wird gezwungen, die Aktion <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> vor der Aktion <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> auf das Steuerelement anwenden. Weitere Informationen finden Sie unter [\<AppContextSwitchOverrides>-Element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

In .NET Core und .NET 5.0 oder höher wird der `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling`-Switch nicht unterstützt.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Entfernen Sie den Switch. Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.DomainUpDown.DownButton`
- `M:System.Windows.Forms.DomainUpDown.UpButton`

-->
