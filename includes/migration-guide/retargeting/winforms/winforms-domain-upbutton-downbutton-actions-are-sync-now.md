---
ms.openlocfilehash: f75a652f15be6b0d184db20dc5cd8aafd80539fe
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614584"
---
### <a name="winforms-domain-upbutton-and-downbutton-actions-are-in-sync-now"></a>Die UpButton- und DownButton-Aktionen der Domäne von WinForm sind jetzt synchronisiert

#### <a name="details"></a>Details

In .NET Framework 4.7.1 und früheren Versionen wird die <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>-Aktion des <xref:System.Windows.Forms.DomainUpDown>-Steuerelements ignoriert, wenn Steuerelementtext vorhanden ist, und der Entwickler muss die <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>-Aktion für das Steuerelement vor der <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>-Aktion verwenden. Ab .NET Framework 4.7.2 funktionieren die <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>- und <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>-Aktionen unabhängig voneinander in diesem Szenario und bleiben synchron.

#### <a name="suggestion"></a>Vorschlag

Damit eine Anwendung von diesen Änderungen profitieren kann, muss sie unter .NET Framework 4.7.2 oder höher ausgeführt werden. Die Anwendung kann von diesen Änderungen profitieren, wenn Sie Folgendes durchführen:

- Kompilieren Sie diese erneut, um .NET Framework 4.7.2 als Ziel zu verwenden. Diese Änderung wird standardmäßig für Windows Forms-Anwendungen aktiviert, die für .NET Framework 4.7.2 oder höher ausgelegt sind.
- Veraltetes Scrollingverhalten wird deaktiviert, indem wie im folgenden Beispiel dargestellt folgender [AppContext-Schalter](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) dem Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt und auf `false` festgelegt wird.

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.7.2       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
