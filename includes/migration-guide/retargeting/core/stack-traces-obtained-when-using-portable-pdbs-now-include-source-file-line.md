---
ms.openlocfilehash: 384f8c7fa08b69c13d05edb3404787d428dad837
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774073"
---
### <a name="stack-traces-obtained-when-using-portable-pdbs-now-include-source-file-and-line-information-if-requested"></a>Stapelüberwachungen, die bei der Verwendung portabler PDBs abgerufen werden, enthalten nun Quelldatei- und Zeileninformationen, wenn diese angefordert werden

|   |   |
|---|---|
|Details|Ab .NET Framework 4.7.2 enthalten Stapelüberwachungen, die bei der Verwendung portabler PDBs abgerufen werden, nun Quelldatei- und Zeileninformationen, wenn diese angefordert werden. In Versionen vor .NET Framework 4.7.2 waren Quelldatei- und Zeileninformationen bei Verwendung portabler PDBs selbst dann nicht verfügbar, wenn diese explizit angefordert wurden.|
|Vorschlag|Für Anwendungen mit der Zielplattform .NET Framework 4.7.2 können Sie sich gegen Quelldatei- und Zeileninformationen entscheiden, wenn Sie portable PDBs verwenden, wenn diese nicht erwünscht sind, indem Sie Folgendes dem Abschnitt <code>&lt;runtime&gt;</code> Ihrer Datei „<code>app.config</code>“ hinzufügen:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Bei Anwendungen, die für frühere Versionen von .NET Framework vorgesehen sind, aber in .NET Framework 4.7.2 oder höher ausgeführt werden, können Sie Quelldatei- und Zeileninformationen bei der Verwendung portabler PDBs aktivieren, indem Sie Folgendes dem Abschnitt <code>&lt;runtime&gt;</code> der Datei „<code>app.config</code>“ hinzufügen:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Bereich|Microsoft Edge|
|Version|4.7.2|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Diagnostics.StackTrace.%23ctor(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Boolean)?displayProperty=nameWithType><li><xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Int32,System.Boolean)?displayProperty=nameWithType></li></ul>|
