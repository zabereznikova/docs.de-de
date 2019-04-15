---
ms.openlocfilehash: feae645fdb06d5a578832e0b18981668c42d4ad1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236477"
---
### <a name="cspparametersparentwindowhandle-now-expects-hwnd-value"></a>CspParameters.ParentWindowHandle erwartet nun einen HWND-Wert

|   |   |
|---|---|
|Details|Der <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle>-Wert, der in .NET Framework 2.0 eingeführt wurde, ermöglicht einer Anwendung die Registrierung eines Handlewerts für das übergeordnete Fenster, sodass jedes Benutzeroberflächenelement, das auf den Schlüssel zugreifen muss (wie etwa eine PIN-Eingabeaufforderung oder ein Zustimmungsdialogfeld), als untergeordnetes modales Fenster des angegebenen Fensters geöffnet wird. Für eine Windows Forms-App, deren Zielplattform .NET Framework 4.7 oder höher ist, kann die Eigenschaft <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> beispielsweise mit dem folgenden Code festgelegt werden:<pre><code class="lang-csharp">cspParameters.ParentWindowHandle = form.Handle;&#13;&#10;</code></pre>In früheren Versionen von .NET Framework wurde erwartet, dass der Wert ein <xref:System.IntPtr?displayProperty=name>-Objekt ist, das einen Speicherort im Arbeitsspeicher darstellt, an dem sich der [HWND](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types#HWND)-Wert befindet. Das Festlegen der Eigenschaft auf form.Handle hatte unter Windows 7 und früheren Versionen keine Auswirkungen, unter Windows 8 und höheren Versionen resultiert dies jedoch in einer &quot;<xref:System.Security.Cryptography.CryptographicException?displayProperty=name>: The parameter is incorrect. (Der Parameter ist falsch).&quot;|
|Vorschlag|Für Apps mit der Zielplattform .NET Framework 4.7 oder höher, die eine übergeordnete Fensterbeziehung registrieren sollen, wird die Verwendung eines vereinfachten Formulars wie dem folgenden empfohlen:<pre><code class="lang-csharp">cspParameters.ParentWindowHandle = form.Handle;&#13;&#10;</code></pre>Einige Benutzer haben erkannt, dass der richtige zu übergebende Wert die Adresse eines Speicherorts im Arbeitsspeicher war, der den Wert <code>form.Handle</code> enthielt. Benutzer können sich gegen dieses geänderte Verhalten entscheiden, indem sie die AppContext-Option <code>Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle</code> auf <code>true</code> festlegen. Dies kann<ol><li>durch programmgesteuertes Festlegen von Kompatibilitätsoptionen für AppContext, wie [hier](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46) beschrieben wird,</li><li>Durch Hinzufügen der folgenden Zeile zum Abschnitt <code>&lt;runtime&gt;</code> der app.config-Datei:</li></ol><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Benutzer, die sich umgekehrt für das neue Verhalten der Laufzeit von .NET Framework 4.7 entscheiden, können die AppContext-Option auf <code>false</code> festlegen, wenn die Anwendung in älteren Versionen von .NET Framework geladen wird.|
|Bereich|Gering|
|Version|4.7|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Security.Cryptography.CspParameters.ParentWindowHandle?displayProperty=nameWithType></li></ul>|
