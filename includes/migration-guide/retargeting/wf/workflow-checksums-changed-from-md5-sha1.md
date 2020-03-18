---
ms.openlocfilehash: 0b42e320ba439a4cfc196471fc6dd4b3c15cd9d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859181"
---
### <a name="workflow-checksums-changed-from-md5-to-sha1"></a>Änderung der Workflowprüfsummen von MD5 in SHA1

|   |   |
|---|---|
|Details|Die Workflowlaufzeit generiert unter Verwendung eines Hashalgorithmus zur Unterstützung des Debuggens mit Visual Studio eine Prüfsumme für eine Workflowinstanz. In .NET Framework 4.6.2 und früheren Versionen wird beim Hashing der Workflowprüfsumme der MD5-Algorithmus verwendet, der auf Systemen, auf den FIPS aktiviert ist, Probleme verursacht hat. Ab .NET Framework 4.7 wird der SHA1-Algorithmus verwendet. Wenn Ihr Code diese Prüfsummen dauerhaft gespeichert hat, sind diese nicht kompatibel.|
|Vorschlag|Wenn Ihr Code aufgrund eines Prüfsummenfehlers keine Workflowinstanzen laden kann, sollten Sie versuchen, den <code>AppContext</code>-Schalter &quot;Switch.System.Activities.UseMD5ForWFDebugger&quot; auf TRUE festzulegen. Dies können Sie in Form von Code tun:<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Activities.UseMD5ForWFDebugger&quot;, true);&#13;&#10;</code></pre>Stattdessen können Sie dies auch im Rahmen der Konfiguration vornehmen:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Activities.UseMD5ForWFDebugger=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|`Scope`|Nebenversion|
|Version|4.7|
|Geben Sie Folgendes ein:|Neuzuweisung|
