---
ms.openlocfilehash: d3bfeda8309af83d8e4199999ed91263a17caeea
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556183"
---
### <a name="removed-status-bar-controls"></a>Statusleisten-Steuerelement wurde entfernt

Ab .NET 5.0 sind einige Windows Forms-Steuerelemente nicht mehr verfügbar.

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET 5.0 sind einige Windows Forms-Steuerelemente für Statusleistenfunktionen nicht mehr verfügbar. Ersatzsteuerelemente, die ein besseres Design und eine umfassendere Unterstützung bieten, wurden in .NET Framework 2.0 eingeführt. Die veralteten Steuerelemente wurden zwar bereits aus den Designer-Toolboxen entfernt, konnten aber weiterhin verwendet werden. Nun wurden sie vollständig entfernt.

Die folgenden Typen stehen nicht mehr länger zur Verfügung:

* `StatusBar`
* `StatusBarDrawItemEventArgs`
* `StatusBarDrawItemEventHandler`
* `StatusBarPanel`
* `StatusBarPanelAutoSize`
* `StatusBarPanelBorderStyle`
* `StatusBarPanelClickEventArgs`
* `StatusBarPanelClickEventHandler`
* `StatusBarPanelStyle`

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 1

#### <a name="recommended-action"></a>Empfohlene Aktion

Wechseln Sie zu den Ersetzungs-APIs für diese Steuerelemente und ihre Szenarios:

| Altes Steuerelement (API) | Empfohlener Ersatz                          |
|-------------------|--------------------------------------------------|
| StatusBar         | <xref:System.Windows.Forms.StatusStrip>          |
| StatusBarPanel    | <xref:System.Windows.Forms.ToolStripStatusLabel> |

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Forms.StatusBar?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanel?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelAutoSize?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelBorderStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelStyle?displayProperty=fullName>

<!-- 

#### Affected APIs

- `T:System.Windows.Forms.StatusBar`
- `T:System.Windows.Forms.StatusBarDrawItemEventArgs`
- `T:System.Windows.Forms.StatusBarDrawItemEventHandler`
- `T:System.Windows.Forms.StatusBarPanel`
- `T:System.Windows.Forms.StatusBarPanelAutoSize`
- `T:System.Windows.Forms.StatusBarPanelBorderStyle`
- `T:System.Windows.Forms.StatusBarPanelClickEventArgs`
- `T:System.Windows.Forms.StatusBarPanelClickEventHandler`
- `T:System.Windows.Forms.StatusBarPanelStyle` 

-->
