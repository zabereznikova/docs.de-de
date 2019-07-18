---
ms.openlocfilehash: 8b0617d8f021a9534289fd7ae8539cd054684862
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774338"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a>WPF-TextBox.Text wird möglicherweise nicht mehr mit der Datenbindung synchronisiert

|   |   |
|---|---|
|Details|In einigen Fällen stellt die <xref:System.Windows.Controls.TextBox.Text>-Eigenschaft einen früheren Wert des datengebundenen Eigenschaftswerts dar, wenn die Eigenschaft während eines Datenbindungsschreibvorgangs geändert wird.|
|Vorschlag|Dies sollte keine negativen Auswirkungen haben. Sie können jedoch das vorherige Verhalten wiederherstellen, indem Sie die <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty>-Eigenschaft auf <code>false</code> festlegen.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType></li></ul>|
