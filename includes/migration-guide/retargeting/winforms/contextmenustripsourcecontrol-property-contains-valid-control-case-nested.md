---
ms.openlocfilehash: 97299ddb9bee89c792ddb3d2b9c37516180996f7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614570"
---
### <a name="contextmenustripsourcecontrol-property-contains-a-valid-control-in-the-case-of-nested-toolstripmenuitems"></a>„ContextMenuStrip.SourceControl“-Eigenschaft enthält im Fall geschachtelter „ToolStripMenuItems“ ein gültiges Steuerelement

#### <a name="details"></a>Details

In .NET Framework 4.7.1 und früheren Versionen gibt die <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>-Eigenschaft fälschlicherweise NULL zurück, wenn der Benutzer das Menü in geschachtelten <xref:System.Windows.Forms.ToolStripMenuItem>-Steuerelementen öffnet. In .NET Framework 4.7.2 und höher ist die <xref:System.Windows.Forms.ContextMenuStrip.SourceControl>-Eigenschaft immer auf das tatsächliche Quellsteuerelement festgelegt.

#### <a name="suggestion"></a>Vorschlag

**Aktivieren oder Deaktivieren dieser Änderungen:** Damit eine Anwendung von diesen Änderungen profitieren kann, muss sie unter .NET Framework 4.7.2 oder höher ausgeführt werden. Die Anwendung kann von diesen Änderungen profitieren, wenn Sie Folgendes durchführen:

- Die Anwendung ist auf .NET Framework 4.7.2 ausgelegt. Diese Änderung wird standardmäßig für Windows Forms-Anwendungen aktiviert, die auf .NET Framework 4.7.2 oder höher ausgelegt sind.
- Die Anwendung ist auf .NET Framework 4.7.1 oder eine frühere Version ausgelegt und deaktiviert veraltete Verhaltensweisen der Barrierefreiheit, indem wie im folgenden Beispiel dargestellt folgender [AppContext-Schalter](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) zum Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt und auf `false` festgelegt wird.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue=false"/>
</runtime>
```

Bei Anwendungen, die auf .NET Framework 4.7.2 oder höher ausgelegt sind und das veraltete Barrierefreiheitsverhalten beibehalten sollen, können Sie die Verwendung des veralteten Quellcodeverwaltungswerts aktivieren, indem Sie den „AppContext“-Schalter auf `true` festlegen.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.7.2       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>
