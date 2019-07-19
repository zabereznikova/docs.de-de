---
ms.openlocfilehash: 9c54572b8dcedaa103db8503cfc1155b4698c3ed
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803470"
---
### <a name="workflow-xaml-checksums-for-symbols-changed-from-sha1-to-sha256"></a>Änderung der Workflow-XAML-Prüfsummen für Symbole von SHA1 in SHA256

|   |   |
|---|---|
|Details|Die Workflowlaufzeit generiert unter Verwendung eines Hashalgorithmus zur Unterstützung des Debuggens mit Visual Studio eine Prüfsumme für eine Workflow-XAML-Datei. In .NET Framework 4.6.2 und früheren Versionen wird beim Hashing der Workflowprüfsumme der MD5-Algorithmus verwendet, der auf Systemen, auf den FIPS aktiviert ist, Probleme verursacht hat. Ab .NET Framework 4.7 wurde der Standardalgorithmus in SHA1 geändert. Ab .NET Framework 4.8 wurde der Standardalgorithmus in SHA256 geändert.|
|Vorschlag|Wenn Ihr Code aufgrund eines Prüfsummenfehlers keine Workflowinstanzen laden oder keine entsprechende Symbole finden kann, sollten Sie versuchen, den <code>AppContext</code>-Schalter &quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols&quot; auf TRUE festzulegen. Dies können Sie in Form von Code tun:<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols&quot;, true);&#13;&#10;</code></pre>Stattdessen können Sie dies auch im Rahmen der Konfiguration vornehmen:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Bereich|Gering|
|Version|4.8|
|Typ|Neuzuweisung|

