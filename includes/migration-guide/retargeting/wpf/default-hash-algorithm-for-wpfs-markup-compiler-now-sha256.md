---
ms.openlocfilehash: 14b8930044381d1d86ec7984d36a5c3588eebd81
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59233944"
---
### <a name="the-default-hash-algorithm-for-wpfs-markup-compiler-is-now-sha256"></a>Der Standardhashalgorithmus für den Markupcompiler von WPF ist jetzt SHA256

|   |   |
|---|---|
|Details|Die WPF-MarkupCompiler stellt Kompilierungsdienste für XAML-Markupdateien bereit.  In .NET Framework 4.7.1 und früheren Versionen war SHA1 der Standardhashalgorithmus, der für Prüfsummen verwendet wurde. Diese Standardeinstellung wurde ab .NET Framework 4.7.2 aufgrund von Sicherheitsbedenken im Zusammenhang mit SHA1 in SHA256 geändert.  Diese Änderung wirkt sich auf die gesamte Prüfsummengenerierung für Markupdateien während der Kompilierung aus.|
|Vorschlag|Ein Entwickler, der als Zielplattform .NET Framework 4.7.2 oder höher verwendet und das SHA1-Hashverhalten wiederherstellen möchte, muss das folgende AppContext-Flag festlegen.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Ein Entwickler, der SHA256-Hashwerte für eine niedrigere Frameworkversion als .NET 4.7.2 nutzen möchte, muss das unten genannte AppContext-Flag festlegen.  Beachten Sie, dass die installierte Version von .NET Framework 4.7.2 oder höher sein muss.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=false&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Bereich|Transparent|
|Version|4.7.2|
|Typ|Neuzuweisung|
