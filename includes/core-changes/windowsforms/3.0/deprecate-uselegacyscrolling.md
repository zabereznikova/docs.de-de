---
ms.openlocfilehash: 80fc75d0736e2ae17699073a025e79b52b340613
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937077"
---
### <a name="domainupdownuselegacyscrolling-compatibility-switch-not-supported"></a>Kompatibilitätsoption DomainUpDown.UseLegacyScrolling wird nicht unterstützt

Der mit .NET Framework 4.7.1 eingeführte Kompatibilitätsswitch `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` wird in Windows Forms unter .NET Core 3.0 nicht unterstützt.

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET Framework 4.7.1 können Entwickler mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` die unabhängigen Aktionen <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> und <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> abstellen. Mit dem Switch wird das Legacyverhalten wiederhergestellt, bei dem <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> ignoriert wird, wenn Kontexttext vorhanden ist, und der Entwickler wird gezwungen, die Aktion <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> vor der Aktion <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> auf das Steuerelement anwenden. Weitere Informationen finden Sie unter [\<AppContextSwitchOverrides>-Element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

In .NET Core wird der Switch `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` nicht unterstützt.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0 Vorschau 9

#### <a name="recommended-action"></a>Empfohlene Aktion

Entfernen Sie den Switch. Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.DomainUpDown.DownButton`
- `M:System.Windows.Forms.DomainUpDown.UpButton`

-->
