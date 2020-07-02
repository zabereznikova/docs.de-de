---
ms.openlocfilehash: 519de92ca4201d199941afe6382ddf9fc480fbbd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614522"
---
### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a>ServiceBase überträgt OnStart-Ausnahmen nicht

#### <a name="details"></a>Details

In .NET Framework 4.7 und früheren Versionen werden Ausnahmen, die beim Dienststart ausgelöst werden, nicht an den Aufrufer von <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> weitergegeben.<br/>Beginnend mit Anwendungen, die auf .NET Framework 4.7.1 ausgelegt sind, gibt die Laufzeit Ausnahmen an <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> für Dienste weiter, die nicht gestartet werden können.

#### <a name="suggestion"></a>Vorschlag

Wenn beim Start des Diensts eine Ausnahme auftritt, wird diese Ausnahme weitergegeben. Dies sollte bei der Diagnose von Fällen helfen, in denen Dienste nicht starten können. <br/>Wenn dieses Verhalten nicht erwünscht ist, können Sie sich dagegen entscheiden, indem Sie das folgende &lt;AppContextSwitchOverrides&gt;-Element dem Abschnitt &lt;runtime&gt; Ihrer Anwendungskonfigurationsdatei hinzufügen:

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true" />
```

Wenn Ihre Anwendung auf eine frühere Version als 4.7.1 ausgerichtet ist und dieses Verhalten erforderlich ist, können Sie das folgende &lt;AppContextSwitchOverrides&gt;-Element dem Abschnitt &lt;runtime&gt; Ihrer Anwendungskonfigurationsdatei hinzufügen:

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false" />
```

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.7.1       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType>
- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType>
