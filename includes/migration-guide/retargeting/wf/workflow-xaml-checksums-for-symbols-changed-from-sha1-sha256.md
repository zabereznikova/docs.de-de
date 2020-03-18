---
ms.openlocfilehash: f814703e187726d3988787fac52e5049988fd4d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803470"
---
### <a name="workflow-xaml-checksums-for-symbols-changed-from-sha1-to-sha256"></a>Änderung der Workflow-XAML-Prüfsummen für Symbole von SHA1 in SHA256

|   |   |
|---|---|
|Details|Die Workflowlaufzeit generiert unter Verwendung eines Hashalgorithmus zur Unterstützung des Debuggens mit Visual Studio eine Prüfsumme für eine Workflow-XAML-Datei. In .NET Framework 4.6.2 und früheren Versionen wird beim Hashing der Workflowprüfsumme der MD5-Algorithmus verwendet, der auf Systemen, auf den FIPS aktiviert ist, Probleme verursacht hat. Ab .NET Framework 4.7 wurde der Standardalgorithmus in SHA1 geändert. Ab .NET Framework 4.8 wurde der Standardalgorithmus in SHA256 geändert.|
|Vorschlag|Wenn Ihr Code aufgrund eines Prüfsummenfehlers keine Workflowinstanzen laden oder keine entsprechende Symbole finden kann, sollten Sie versuchen, den <code>AppContext</code>-Schalter &quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols&quot; auf TRUE festzulegen. Dies können Sie in Form von Code tun:<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols&quot;, true);&#13;&#10;</code></pre>Stattdessen können Sie dies auch im Rahmen der Konfiguration vornehmen:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|`Scope`|Nebenversion|
|Version|4.8|
|Geben Sie Folgendes ein:|Neuzuweisung|
