---
ms.openlocfilehash: 3f0e8fb4d0d727b40cff5de7cfdc7529bf32dac4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937045"
---
### <a name="donotloadlatestricheditcontrol-compatibility-switch-not-supported"></a>Kompatibilitätsoption DoNotLoadLatestRichEditControl wird nicht unterstützt

Der mit .NET Framework 4.7.1 eingeführte Kompatibilitätsswitch `Switch.System.Windows.Forms.UseLegacyImages` wird in Windows Forms unter .NET Core 3.0 nicht unterstützt.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Framework 4.6.2 und früheren Versionen wurde mit dem <xref:System.Windows.Forms.RichTextBox>-Steuerelement das Win32 RichEdit-Steuerelement v3.0 instanziiert, und bei Anwendungen für .NET Framework 4.7.1 wurde mit dem <xref:System.Windows.Forms.RichTextBox>-Steuerelement RichEdit v4.1 (in *msftedit.dll*) instanziiert. Der Kompatibilitätsswitch `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` wurde eingeführt, damit Anwendungen für .NET Framework 4.7.1 und höhere Versionen das neue RichEdit v4.1-Steuerelement abstellen und stattdessen das alte RichEdit v3-Steuerelement verwenden können.

In .NET Core wird der Switch `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` nicht unterstützt. Es werden nur neue Versionen des <xref:System.Windows.Forms.RichTextBox>-Steuerelements unterstützt.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0 Vorschau 9

#### <a name="recommended-action"></a>Empfohlene Aktion

Entfernen Sie den Switch. Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
