---
ms.openlocfilehash: 7c2e80669d9ef27f87cde9442d8eeab0ee31a524
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614624"
---
### <a name="wpf-textboxpasswordbox-text-selection-does-not-follow-system-colors"></a>TextBox-/PasswordBox-Textauswahl von WPF folgt nicht den Systemfarben

#### <a name="details"></a>Details

In .NET Framework 4.7.1 und früheren Versionen konnten `System.Windows.Controls.TextBox` und `System.Windows.Controls.PasswordBox` von WPF nur eine Textauswahl aus der Adorner-Ebene rendern. In einigen Systemdesigns verdeckte dies Text, wodurch die Lesbarkeit erschwert wurde.  In .NET Framework 4.7.2 und höher besteht für Entwickler eine Option, ein nicht auf Adorner basierendes Auswahlrenderingschema zu aktivieren, das dieses Problem behebt.

#### <a name="suggestion"></a>Vorschlag

Ein Entwickler, die diese Änderung nutzen möchte, muss das folgende AppContext-Flag entsprechend festlegen.  Um dieses Feature nutzen zu können, muss die installierte Version von .NET Framework 4.7.2 oder höher sein. Um die nicht auf Adorner basierende Auswahl zu aktivieren, verwenden Sie das folgenden AppContext-Flag.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Text.UseAdornerForTextboxSelectionRendering=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.7.2       |
| Typ    | Neuzuweisung |
