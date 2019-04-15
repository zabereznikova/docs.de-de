---
ms.openlocfilehash: f1a1eab471d46f018a8e0d0cf787d487cf67c11e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59233960"
---
### <a name="contextmenustripsourcecontrol-property-contains-a-valid-control-in-the-case-of-nested-toolstripmenuitems"></a>„ContextMenuStrip.SourceControl“-Eigenschaft enthält im Fall geschachtelter „ToolStripMenuItems“ ein gültiges Steuerelement

|   |   |
|---|---|
|Details|In .NET Framework 4.7.1 und früheren Versionen gibt die <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>-Eigenschaft fälschlicherweise NULL zurück, wenn der Benutzer das Menü in geschachtelten <xref:System.Windows.Forms.ToolStripMenuItem>-Steuerelementen öffnet. In .NET Framework 4.7.2 und höher ist die <xref:System.Windows.Forms.ContextMenuStrip.SourceControl>-Eigenschaft immer auf das tatsächliche Quellsteuerelement festgelegt.|
|Vorschlag|<strong>Aktivieren oder Deaktivieren dieser Änderungen</strong>: Damit eine Anwendung von diesen Änderungen profitieren kann, muss sie unter .NET Framework 4.7.2 oder höher ausgeführt werden. Die Anwendung kann von diesen Änderungen profitieren, wenn Sie Folgendes durchführen:<ul><li>Die Anwendung ist auf .NET Framework 4.7.2 ausgelegt. Diese Änderung wird standardmäßig für Windows Forms-Anwendungen aktiviert, die auf .NET Framework 4.7.2 oder höher ausgelegt sind.</li><li>Die Anwendung ist auf .NET Framework 4.7.1 oder eine frühere Version ausgelegt und deaktiviert veraltete Verhaltensweisen der Barrierefreiheit, indem wie im folgenden Beispiel dargestellt folgender [AppContext-Schalter](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) zum Abschnitt <code>&lt;runtime&gt;</code> der Datei „app.config“ hinzugefügt und auf <code>false</code> festgelegt wird.</li></ul><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Bei Anwendungen, die auf .NET Framework 4.7.2 oder höher ausgelegt sind und das veraltete Barrierefreiheitsverhalten beibehalten sollen, können Sie die Verwendung des veralteten Quellcodeverwaltungswerts aktivieren, indem Sie den „AppContext“-Schalter auf <code>true</code> festlegen.|
|Bereich|Microsoft Edge|
|Version|4.7.2|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType></li></ul>|
