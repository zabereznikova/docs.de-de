---
ms.openlocfilehash: 63a38f33fef09577c5ed621727b8c38e4c7e1bdf
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760849"
---
### <a name="the-default-hash-algorithm-for-wpfs-markup-compiler-is-now-sha256"></a>Der Standardhashalgorithmus für den Markupcompiler von WPF ist jetzt SHA256

|   |   |
|---|---|
|Details|Die WPF-MarkupCompiler stellt Kompilierungsdienste für XAML-Markupdateien bereit.  In .NET Framework 4.7.1 und früheren Versionen war SHA1 der Standardhashalgorithmus, der für Prüfsummen verwendet wurde. Diese Standardeinstellung wurde ab .NET Framework 4.7.2 aufgrund von Sicherheitsbedenken im Zusammenhang mit SHA1 in SHA256 geändert.  Diese Änderung wirkt sich auf die gesamte Prüfsummengenerierung für Markupdateien während der Kompilierung aus.|
|Vorschlag|Ein Entwickler, der als Zielplattform .NET Framework 4.7.2 oder höher verwendet und das SHA1-Hashverhalten wiederherstellen möchte, muss das folgende AppContext-Flag festlegen.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Ein Entwickler, der SHA256-Hashwerte für eine niedrigere Frameworkversion als .NET 4.7.2 nutzen möchte, muss das unten genannte AppContext-Flag festlegen.  Beachten Sie, dass die installierte Version von .NET Framework 4.7.2 oder höher sein muss.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=false&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Bereich|Transparent|
|Version|4.7.2|
|Typ|Neuzuweisung|

