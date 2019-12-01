---
ms.openlocfilehash: 265fc5bea97bf85bcb9cc8111f915e14297d9957
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643874"
---
### <a name="switchsystemwindowsformsdonotloadlatestricheditcontrol-compatibility-switch-not-supported"></a>Kompatibilitätsswitch „Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl“ wird nicht unterstützt

Der mit .NET Framework 4.7.1 eingeführte Kompatibilitätsswitch `Switch.System.Windows.Forms.UseLegacyImages` wird in Windows Forms unter .NET Core 3.0 nicht unterstützt.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Framework 4.6.2 und früheren Versionen wurde mit dem <xref:System.Windows.Forms.RichTextBox>-Steuerelement das Win32 RichEdit-Steuerelement v3.0 instanziiert, und bei Anwendungen für .NET Framework 4.7.1 wurde mit dem <xref:System.Windows.Forms.RichTextBox>-Steuerelement RichEdit v4.1 (in *msftedit.dll*) instanziiert. Der Kompatibilitätsswitch `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` wurde eingeführt, damit Anwendungen für .NET Framework 4.7.1 und höhere Versionen das neue RichEdit v4.1-Steuerelement abstellen und stattdessen das alte RichEdit v3-Steuerelement verwenden können.

In .NET Core wird der Switch `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` nicht unterstützt. Es werden nur neue Versionen des <xref:System.Windows.Forms.RichTextBox>-Steuerelements unterstützt.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0 Vorschau 9

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Entfernen Sie den Switch. Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
