---
ms.openlocfilehash: add3ff8faed2e7fab245e5b6f1b9158b7bdd06f5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74567367"
---
### <a name="cellformatting-event-not-raised-if-tooltip-is-shown"></a>CellFormatting-Ereignis wird nicht ausgelöst, wenn QuickInfo angezeigt wird

Eine <xref:System.Windows.Forms.DataGridView> zeigt nun Text- und die Fehler-QuickInfos einer Zelle an, wenn mit der Maus darauf gezeigt wird oder wenn sie mit der Tastatur ausgewählt wird. Wenn eine QuickInfo angezeigt wird, wird das <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>-Ereignis nicht ausgelöst.

#### <a name="change-description"></a>Änderungsbeschreibung

Vor .NET Core 3.1 wurde bei einer <xref:System.Windows.Forms.DataGridView>, für die die <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A>-Eigenschaft auf `true` festgelegt wurde, eine QuickInfo für den Text und Fehler einer Zelle angezeigt, wenn mit der Maus auf die Zelle gezeigt wurde. Es wurden keine QuickInfos angezeigt, wenn die Maus mit der Tastatur ausgewählt wurde (z. B. mit der TAB-TASTE, einer Tastenkombination oder den Pfeiltasten). Wenn der Benutzer eine Zelle bearbeitet hat und die <xref:System.Windows.Forms.DataGridView> sich noch im Bearbeitungsmodus befunden hat und mit der Maus auf eine Zelle gezeigt wurde, für die die <xref:System.Windows.Forms.DataGridViewCell.ToolTipText>-Eigenschaft nicht festgelegt war, wurde ein <xref:System.Windows.Forms.DataGridView.CellFormatting>-Ereignis ausgelöst, um den Text der Zelle für die Anzeige in der Zelle zu formatieren.

Um die Barrierefreiheitsstandards zu erfüllen, werden ab .NET Core 3.1 bei einer <xref:System.Windows.Forms.DataGridView>, für die die <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A>-Eigenschaft auf `true` festgelegt ist, QuickInfos für den Text und Fehler der Zelle nicht nur dann angezeigt, wenn mit der Maus darauf gezeigt wird, sondern auch, wenn sie mit der Tastatur ausgewählt wird. Infolge dieser Änderung wird das <xref:System.Windows.Forms.DataGridView.CellFormatting>-Ereignis *nicht* ausgelöst, wenn mit der Maus auf Zellen gezeigt wird, für die <xref:System.Windows.Forms.DataGridViewCell.ToolTipText>-Eigenschaft nicht festgelegt ist, und die <xref:System.Windows.Forms.DataGridView> sich im Bearbeitungsmodus befindet. Das Ereignis wird nicht ausgelöst, da der Inhalt der Zelle, auf die gezeigt wird, als QuickInfo und nicht in der Zelle dargestellt wird.

#### <a name="version-introduced"></a>Eingeführt in Version

3.1

#### <a name="recommended-action"></a>Empfohlene Aktion

Schreiben Sie Code um, der das <xref:System.Windows.Forms.DataGridView.CellFormatting>-Ereignis benötigt, während sich die <xref:System.Windows.Forms.DataGridView> im Bearbeitungsmodus befindet.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!-- 

### Affected APIs

- Not detectable via API analysis.

-->
