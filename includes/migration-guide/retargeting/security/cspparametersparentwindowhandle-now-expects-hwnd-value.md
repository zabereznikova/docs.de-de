---
ms.openlocfilehash: 72f907c117748fb19ca0663f24445a8c978afd32
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "68235550"
---
### <a name="cspparametersparentwindowhandle-now-expects-hwnd-value"></a>CspParameters.ParentWindowHandle erwartet nun einen HWND-Wert

|   |   |
|---|---|
|Details|Der <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle>-Wert, der in .NET Framework 2.0 eingeführt wurde, ermöglicht einer Anwendung die Registrierung eines Handlewerts für das übergeordnete Fenster, sodass jedes Benutzeroberflächenelement, das auf den Schlüssel zugreifen muss (wie etwa eine PIN-Eingabeaufforderung oder ein Zustimmungsdialogfeld), als untergeordnetes modales Fenster des angegebenen Fensters geöffnet wird. Für eine Windows Forms-App, deren Zielplattform .NET Framework 4.7 oder höher ist, kann die Eigenschaft <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> beispielsweise mit dem folgenden Code festgelegt werden:<pre><code class="lang-csharp">cspParameters.ParentWindowHandle = form.Handle;&#13;&#10;</code></pre>In früheren Versionen von .NET Framework wurde erwartet, dass der Wert ein <xref:System.IntPtr?displayProperty=name>-Objekt ist, das einen Speicherort im Arbeitsspeicher darstellt, an dem sich der [HWND](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types#HWND)-Wert befindet. Das Festlegen der Eigenschaft auf form.Handle hatte unter Windows 7 und früheren Versionen keine Auswirkungen, unter Windows 8 und höheren Versionen resultiert dies jedoch in der Fehlermeldung &quot;<xref:System.Security.Cryptography.CryptographicException?displayProperty=name>: The parameter is incorrect.&quot; (CryptographicException: Der Parameter ist falsch.).|
|Vorschlag|Für Apps mit der Zielplattform .NET Framework 4.7 oder höher, die eine übergeordnete Fensterbeziehung registrieren sollen, wird die Verwendung eines vereinfachten Formulars wie dem folgenden empfohlen:<pre><code class="lang-csharp">cspParameters.ParentWindowHandle = form.Handle;&#13;&#10;</code></pre>Einige Benutzer haben erkannt, dass der richtige zu übergebende Wert die Adresse eines Speicherorts im Arbeitsspeicher war, der den Wert <code>form.Handle</code> enthielt. Benutzer können sich gegen dieses geänderte Verhalten entscheiden, indem sie die AppContext-Option <code>Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle</code> auf <code>true</code> festlegen. Dies kann<ol><li>durch programmgesteuertes Festlegen von Kompatibilitätsoptionen für AppContext, wie [hier](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46) beschrieben wird,</li><li>Durch Hinzufügen der folgenden Zeile zum Abschnitt <code>&lt;runtime&gt;</code> der app.config-Datei:</li></ol><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Benutzer, die sich umgekehrt für das neue Verhalten der Laufzeit von .NET Framework 4.7 entscheiden, können die AppContext-Option auf <code>false</code> festlegen, wenn die Anwendung in älteren Versionen von .NET Framework geladen wird.|
|`Scope`|Nebenversion|
|Version|4.7|
|Geben Sie Folgendes ein:|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Security.Cryptography.CspParameters.ParentWindowHandle?displayProperty=nameWithType></li></ul>|
