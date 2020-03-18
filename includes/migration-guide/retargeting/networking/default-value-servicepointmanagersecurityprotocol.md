---
ms.openlocfilehash: 122a5ab3e2def7c19d3d523881fcb15df4dbca26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "68235592"
---
### <a name="default-value-of-servicepointmanagersecurityprotocol-is-securityprotocoltypesystemdefault"></a>Der Standardwert von ServicePointManager.SecurityProtocol ist SecurityProtocolType.System.Default

|   |   |
|---|---|
|Details|Bei Apps mit der Zielplattform .NET Framework 4.7 und höher ist der Standardwert der <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>-Eigenschaft <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType>. Diese Änderungen ermöglicht den Netzwerk-APIs von .NET Framework, die auf SslStream (z.B. FTP, HTTPS und SMTP) basieren, die Standardsicherheitsprotokolle des Betriebssystems zu erben, anstatt hartcodierte Werte zu verwenden, die von .NET Framework definiert werden. Der Standard variiert je nach Betriebssystem und sämtlichen benutzerdefinierten Konfigurationen, die vom Systemadministrator vorgenommen werden. Informationen zum standardmäßigen SChannel-Protokoll in der jeweiligen Version des Windows-Betriebssystems finden Sie unter [Protokolle in TLS/SSL (SChannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/protocols-in-tls-ssl--schannel-ssp-).</p>Bei Anwendungen, die auf eine frühere Version des .NET-Frameworks ausgelegt sind, hängt der Standardwert der <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>-Eigenschaft von der .NET Framework-Zielversion ab. Weitere Informationen finden Sie im [Abschnitt „Netzwerk“ des Artikels „Neuzuweisung von Änderungen für die Migration von .NET Framework 4.5.2 zu 4.6“](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#networking).|
|Vorschlag|Diese Änderung betrifft nur Anwendungen, die auf .NET Framework 4.7 oder höher ausgelegt sind. <br>Wenn Sie lieber ein definiertes Protokoll anstelle des Systemstandards verwenden möchten, können Sie den Wert der <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>-Eigenschaft explizit festlegen.<br>Wenn diese Änderung nicht erwünscht ist, können Sie sich dagegen entscheiden, indem Sie dem Abschnitt [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer Anwendungskonfigurationsdatei eine Konfigurationseinstellung hinzufügen. Im folgenden Beispiel sind sowohl der Abschnitt <code>&lt;runtime&gt;</code> als auch die Ablehnungsoption <code>Switch.System.Net.DontEnableSystemDefaultTlsVersions</code> dargestellt:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Net.DontEnableSystemDefaultTlsVersions=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|`Scope`|Nebenversion|
|Version|4.7|
|Geben Sie Folgendes ein:|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType></li></ul>|
