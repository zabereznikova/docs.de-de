---
ms.openlocfilehash: d0de1a262d57c67dd4dfb258d5ac013af5d8783d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617230"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a>WPF-TextBox.Text wird möglicherweise nicht mehr mit der Datenbindung synchronisiert

#### <a name="details"></a>Details

In einigen Fällen stellt die <xref:System.Windows.Controls.TextBox.Text>-Eigenschaft einen früheren Wert des datengebundenen Eigenschaftswerts dar, wenn die Eigenschaft während eines Datenbindungsschreibvorgangs geändert wird.

#### <a name="suggestion"></a>Vorschlag

Dies sollte keine negativen Auswirkungen haben. Sie können jedoch das vorherige Verhalten wiederherstellen, indem Sie die <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty>-Eigenschaft auf `false` festlegen.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.5         |
|Typ|Neuzuweisung

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType>
