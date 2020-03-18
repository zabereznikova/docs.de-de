---
ms.openlocfilehash: e609b8006846cd202a6a7eeec2529cf1fbb09e7c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75936989"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a>Doppelte APIs aus Windows Forms entfernt

Eine Reihe von APIs, die versehentlich im Namespace <xref:System.Windows.Forms?displayProperty=fullName> ab .NET Core 3.0 Vorschau 4 dupliziert wurden, wurden in .NET Core 3.0 RC1 entfernt.

#### <a name="change-description"></a>Änderungsbeschreibung

.NET Core 3.0 Vorschau 4 hat versehentlich eine Reihe von Typen im Namespace <xref:System.Windows.Forms?displayProperty=fullName> dupliziert, die bereits im Namespace <xref:System.ComponentModel.Design?displayProperty=fullName> vorhanden waren. Ab .NET Core 3.0 RC1 sind diese duplizierten Typen nicht mehr verfügbar. In der folgenden Tabelle werden der ursprüngliche Typ und der duplizierte Typ aufgelistet:

> [!div class="mx-tdCol2BreakAll"]
> |Ursprünglicher Typ|Duplizierter Typ|
> |---|---|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventArgs?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventArgs`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventHandler?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventHandler`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedType?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedType`|
> |<xref:System.ComponentModel.Design.DesignerActionUIService?displayProperty=fullName>|`System.Windows.Forms.DesignerActionUIService`|
> |<xref:System.ComponentModel.Design.DesignerCommandSet?displayProperty=fullName>|`System.Windows.Forms.DesignerCommandSet`|

#### <a name="version-introduced"></a>Eingeführt in Version

3.0 RC1

#### <a name="recommended-action"></a>Empfohlene Aktion

Aktualisieren Sie den Code so, dass er auf den ursprünglichen Typ verweist, wie in der Spalte **Ursprünglicher Typ** der Tabelle gezeigt.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

- Nicht über API-Analyse erkennbar.

<!--

### Affected APIs

- Not detectable via API analysis.

-->
