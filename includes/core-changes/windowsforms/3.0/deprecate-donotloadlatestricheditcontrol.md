---
ms.openlocfilehash: e10b5168d59edd56ff549a3a1e3a09d023fe5e28
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556176"
---
### <a name="donotloadlatestricheditcontrol-compatibility-switch-not-supported"></a>Kompatibilitätsoption DoNotLoadLatestRichEditControl wird nicht unterstützt

Der mit .NET Framework 4.7.1 eingeführte Kompatibilitätsswitch `Switch.System.Windows.Forms.UseLegacyImages` wird in Windows Forms unter .NET Core oder .NET 5.0 oder höher nicht unterstützt.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Framework 4.6.2 und früheren Versionen instanziiert das <xref:System.Windows.Forms.RichTextBox>-Steuerelement das Win32 RichEdit-Steuerelement v3.0, und bei Anwendungen für .NET Framework 4.7.1 instanziiert das <xref:System.Windows.Forms.RichTextBox>-Steuerelement RichEdit v4.1 (in *msftedit.dll*). Der Kompatibilitätsswitch `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` wurde eingeführt, damit Anwendungen für .NET Framework 4.7.1 und höhere Versionen das neue RichEdit v4.1-Steuerelement ignorieren und stattdessen das alte RichEdit v3-Steuerelement verwenden können.

In .NET Core und .NET 5.0 oder höheren Versionen wird der `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl`-Switch nicht unterstützt. Es werden nur neue Versionen des <xref:System.Windows.Forms.RichTextBox>-Steuerelements unterstützt.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Entfernen Sie den Switch. Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

#### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
