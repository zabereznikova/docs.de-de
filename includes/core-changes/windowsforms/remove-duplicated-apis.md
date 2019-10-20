---
ms.openlocfilehash: 3d0a90a57c2b1c2759b8420e74c284668d54e9cb
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72526747"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a>Doppelte APIs aus Windows Forms entfernt

Eine Reihe von APIs, die versehentlich im Namespace <xref:System.Windows.Forms?displayProperty=fullName> ab .NET Core 3.0 Vorschau 4 dupliziert wurden, wurden in .NET Core 3.0 RC1 entfernt.

#### <a name="change-description"></a>Änderungsbeschreibung

.NET Core 3.0 Vorschau 4 hat versehentlich eine Reihe von Typen im Namespace <xref:System.Windows.Forms?displayProperty=fullName> dupliziert, die bereits im Namespace <xref:System.ComponentModel.Design?displayProperty=fullName> vorhanden waren. Ab .NET Core 3.0 RC1 sind diese duplizierten Typen nicht mehr verfügbar. In der folgenden Tabelle werden der ursprüngliche Typ und der duplizierte Typ aufgelistet:

|Ursprünglicher Typ|Duplizierter Typ|
|---|---|
|<xref:System.ComponentModel.Design.DesignerActionListsChangedEventArgs?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventArgs`|
|<xref:System.ComponentModel.Design.DesignerActionListsChangedEventHandler?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventHandler`|
|<xref:System.ComponentModel.Design.DesignerActionListsChangedType?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedType`|
|<xref:System.ComponentModel.Design.DesignerActionUIService?displayProperty=fullName>|`System.Windows.Forms.DesignerActionUIService`|
|<xref:System.ComponentModel.Design.DesignerCommandSet?displayProperty=fullName>|`System.Windows.Forms.DesignerCommandSet`|

#### <a name="version-introduced"></a>Eingeführt in Version

3.0 RC1

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Aktualisieren Sie den Code so, dass er auf den ursprünglichen Typ verweist, wie in der Spalte **Ursprünglicher Typ** der Tabelle gezeigt.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

- Nicht über API-Analyse erkennbar.

<!--

### Affected APIs

- Not detectable via API analysis.

-->
