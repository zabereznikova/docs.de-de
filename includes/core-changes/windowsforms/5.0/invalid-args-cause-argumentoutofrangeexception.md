---
ms.openlocfilehash: f42da00487735acdcc60f876c75e1dfd17103008
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2020
ms.locfileid: "84702439"
---
### <a name="winforms-properties-now-throw-argumentoutofrangeexception"></a>WinForms-Eigenschaften lösen nun ArgumentOutOfRangeException aus

Einige Windows Forms-Eigenschaften lösen nun eine <xref:System.ArgumentOutOfRangeException> für ungültige Argumente aus, was zuvor nicht der Fall war.

#### <a name="change-description"></a>Änderungsbeschreibung

Zuvor haben diese Eigenschaften verschiedene Ausnahmen ausgelöst, wie z. B. <xref:System.NullReferenceException>, <xref:System.IndexOutOfRangeException> oder <xref:System.ArgumentException>, wenn Argumente außerhalb des zulässigen Bereichs übergeben wurden. Ab .NET 5.0 lösen diese Eigenschaften stattdessen eine <xref:System.ArgumentOutOfRangeException> aus, wenn Argumente außerhalb des zulässigen Bereichs übergeben werden.

Das Auslösen einer <xref:System.ArgumentOutOfRangeException>-Ausnahme entspricht dem Verhalten der .NET Runtime. Außerdem wird die Debugfunktion verbessert, indem ausdrücklich kommuniziert wird, welches Argument ungültig ist.

#### <a name="version-introduced"></a>Eingeführt in Version

.NET 5.0

#### <a name="recommended-action"></a>Empfohlene Aktion

- Aktualisieren Sie den Code, um das Übergeben ungültiger Argumente zu verhindern.
- Behandeln Sie ggf. eine <xref:System.ArgumentOutOfRangeException>, wenn Sie die Eigenschaft festlegen.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

In der folgenden Tabelle sind die betroffenen Eigenschaften und Parameter aufgeführt:

> [!div class="mx-tdBreakAll"]
> | Eigenschaft | Parametername | Hinzugefügte Version |
> |-|-|-|
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)?displayProperty=nameWithType> | `index` | 5.0 Vorschau 5 |
> | <xref:System.Windows.Forms.TreeNode.ImageIndex?displayProperty=nameWithType> | `value` | Version 5.0 Vorschau 6 |
> | <xref:System.Windows.Forms.TreeNode.SelectedImageIndex?displayProperty=nameWithType> | `value` | Version 5.0 Vorschau 6 |

<!-- 

#### Affected APIs

- `P:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)`
- `P:System.Windows.Forms.TreeNode.ImageIndex`
- `P:System.Windows.Forms.TreeNode.SelectedImageIndex`

-->
