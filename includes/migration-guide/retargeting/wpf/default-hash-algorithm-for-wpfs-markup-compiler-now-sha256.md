---
ms.openlocfilehash: 4303b177ffe01328965c909a5a3809414fcead91
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614593"
---
### <a name="the-default-hash-algorithm-for-wpfs-markup-compiler-is-now-sha256"></a>Der Standardhashalgorithmus für den Markupcompiler von WPF ist jetzt SHA256

#### <a name="details"></a>Details

Die WPF-MarkupCompiler stellt Kompilierungsdienste für XAML-Markupdateien bereit.  In .NET Framework 4.7.1 und früheren Versionen war SHA1 der Standardhashalgorithmus, der für Prüfsummen verwendet wurde. Diese Standardeinstellung wurde ab .NET Framework 4.7.2 aufgrund von Sicherheitsbedenken im Zusammenhang mit SHA1 in SHA256 geändert.  Diese Änderung wirkt sich auf die gesamte Prüfsummengenerierung für Markupdateien während der Kompilierung aus.

#### <a name="suggestion"></a>Vorschlag

Ein Entwickler, der als Zielplattform .NET Framework 4.7.2 oder höher verwendet und das SHA1-Hashverhalten wiederherstellen möchte, muss das folgende AppContext-Flag festlegen.

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

Ein Entwickler, der SHA256-Hashwerte für eine niedrigere Frameworkversion als .NET 4.7.2 nutzen möchte, muss das unten genannte AppContext-Flag festlegen.  Beachten Sie, dass die installierte Version von .NET Framework 4.7.2 oder höher sein muss.

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=false&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   | Transparent |
| Version | 4.7.2       |
| Typ    | Neuzuweisung |
