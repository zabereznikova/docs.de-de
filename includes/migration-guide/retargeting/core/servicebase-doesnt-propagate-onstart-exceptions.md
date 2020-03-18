---
ms.openlocfilehash: 1148d040aa3b292d5c37eb50224413b6ddd202e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858942"
---
### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a>ServiceBase überträgt OnStart-Ausnahmen nicht

|   |   |
|---|---|
|Details|In .NET Framework 4.7 und früheren Versionen werden Ausnahmen, die beim Dienststart ausgelöst werden, nicht an den Aufrufer von <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> weitergegeben.<br/>Beginnend mit Anwendungen, die auf .NET Framework 4.7.1 ausgelegt sind, gibt die Laufzeit Ausnahmen an <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> für Dienste weiter, die nicht gestartet werden können.|
|Vorschlag|Wenn beim Start des Diensts eine Ausnahme auftritt, wird diese Ausnahme weitergegeben. Dies sollte bei der Diagnose von Fällen helfen, in denen Dienste nicht starten können. <br/>Wenn dieses Verhalten nicht erwünscht ist, können Sie sich dagegen entscheiden, indem Sie das folgende &lt;AppContextSwitchOverrides&gt;-Element dem Abschnitt &lt;runtime&gt; Ihrer Anwendungskonfigurationsdatei hinzufügen:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true&quot; /&gt;&#13;&#10;</code></pre>Wenn Ihre Anwendung auf eine frühere Version als 4.7.1 ausgerichtet ist und dieses Verhalten erforderlich ist, können Sie das folgende &lt;AppContextSwitchOverrides&gt;-Element dem Abschnitt &lt;runtime&gt; Ihrer Anwendungskonfigurationsdatei hinzufügen:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false&quot; /&gt;&#13;&#10;</code></pre>|
|`Scope`|Nebenversion|
|Version|4.7.1|
|Geben Sie Folgendes ein:|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType></li><li><xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType></li></ul>|
