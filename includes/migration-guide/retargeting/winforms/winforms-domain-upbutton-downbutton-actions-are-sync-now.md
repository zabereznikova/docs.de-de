---
ms.openlocfilehash: e73fe48467ede501bae0ddd9362d9d55b3ca998b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774054"
---
### <a name="winforms-domain-upbutton-and-downbutton-actions-are-in-sync-now"></a>Die UpButton- und DownButton-Aktionen der Domäne von WinForm sind jetzt synchronisiert

|   |   |
|---|---|
|Details|In .NET Framework 4.7.1 und früheren Versionen wird die <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>-Aktion des <xref:System.Windows.Forms.DomainUpDown>-Steuerelements ignoriert, wenn Steuerelementtext vorhanden ist, und der Entwickler muss die <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>-Aktion für das Steuerelement vor der <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>-Aktion verwenden. Ab .NET Framework 4.7.2 funktionieren die <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>- und <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>-Aktionen unabhängig voneinander in diesem Szenario und bleiben synchron.|
|Vorschlag|Damit eine Anwendung von diesen Änderungen profitieren kann, muss sie unter .NET Framework 4.7.2 oder höher ausgeführt werden. Die Anwendung kann von diesen Änderungen profitieren, wenn Sie Folgendes durchführen:<ul><li>Kompilieren Sie diese erneut, um .NET Framework 4.7.2 als Ziel zu verwenden. Diese Änderung wird standardmäßig für Windows Forms-Anwendungen aktiviert, die für .NET Framework 4.7.2 oder höher ausgelegt sind.</li><li>Veraltetes Scrollingverhalten wird deaktiviert, indem wie im folgenden Beispiel dargestellt folgender [AppContext-Schalter](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) dem Abschnitt <code>&lt;runtime&gt;</code> der Datei „app.config“ hinzugefügt und auf <code>false</code> festgelegt wird.</li></ul><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Bereich|Microsoft Edge|
|Version|4.7.2|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType></li><li><xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType></li></ul>|
