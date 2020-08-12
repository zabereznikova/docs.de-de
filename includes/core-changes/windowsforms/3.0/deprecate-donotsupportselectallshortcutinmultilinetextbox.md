---
ms.openlocfilehash: 3fb8807a9b6f0bb0d2bc746f5e89eaa8a81d6aa8
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556181"
---
### <a name="donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a>Kompatibilitätsoption DoNotSupportSelectAllShortcutInMultilineTextBox wird nicht unterstützt

Der mit .NET Framework 4.6.1 eingeführte Kompatibilitätsswitch `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` wird in Windows Forms unter .NET Core und .NET 5.0 oder höher nicht unterstützt.

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET Framework 4.6.1 wird mit der Tastenkombination <kbd>STRG</kbd> + <kbd>A</kbd> in einem <xref:System.Windows.Forms.TextBox>-Steuerelement der gesamte Text ausgewählt. In .NET Framework 4.6 und früheren Versionen konnte mit der Tastenkombination <kbd>STRG</kbd> + <kbd>A</kbd> nicht der gesamte Text ausgewählt werden, wenn die beiden Eigenschaften [Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) und <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> auf `true` festgelegt waren. Der Kompatibilitätsswitch `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` wurde in .NET Framework 4.6.1 eingeführt, um das ursprüngliche Verhalten beizubehalten. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.

In .NET Core und .NET 5.0 oder höheren Versionen wird der `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox`-Switch nicht unterstützt.

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
