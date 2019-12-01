---
ms.openlocfilehash: a9d0fe3516ade04bc38b804268a9d989f6891d80
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643880"
---
### <a name="switchsystemwindowsformsdonotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a>Kompatibilitätsswitch „Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox“ wird nicht unterstützt

Der mit .NET Framework 4.6.1 eingeführte Kompatibilitätsswitch `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` wird in Windows Forms unter .NET Core 3.0 nicht unterstützt.

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET Framework 4.6.1 wird mit der Tastenkombination <kbd>STRG</kbd> + <kbd>A</kbd> in einem <xref:System.Windows.Forms.TextBox>-Steuerelement der gesamte Text ausgewählt. In .NET Framework 4.6 und früheren Versionen konnte mit der Tastenkombination <kbd>STRG</kbd> + <kbd>A</kbd> nicht der gesamte Text ausgewählt werden, wenn die beiden Eigenschaften [Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) und <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> auf `true` festgelegt waren. Der Kompatibilitätsswitch `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` wurde in .NET Framework 4.6.1 eingeführt, um das ursprüngliche Verhalten beizubehalten. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.

In .NET Core wird der Switch `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` nicht unterstützt.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0 Vorschau 9

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Entfernen Sie den Switch. Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

- Keine

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
