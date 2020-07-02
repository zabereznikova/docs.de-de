---
ms.openlocfilehash: 5c86be598ab6196ecf4da05451c7f22d2be52c12
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614471"
---
### <a name="default-value-of-servicepointmanagersecurityprotocol-is-securityprotocoltypesystemdefault"></a>Der Standardwert von ServicePointManager.SecurityProtocol ist SecurityProtocolType.System.Default

#### <a name="details"></a>Details

Bei Apps mit der Zielplattform .NET Framework 4.7 und höher ist der Standardwert der <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>-Eigenschaft <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType>. Diese Änderungen ermöglicht den Netzwerk-APIs von .NET Framework, die auf SslStream (z.B. FTP, HTTPS und SMTP) basieren, die Standardsicherheitsprotokolle des Betriebssystems zu erben, anstatt hartcodierte Werte zu verwenden, die von .NET Framework definiert werden. Der Standard variiert je nach Betriebssystem und sämtlichen benutzerdefinierten Konfigurationen, die vom Systemadministrator vorgenommen werden. Informationen zum standardmäßigen SChannel-Protokoll in der jeweiligen Version des Windows-Betriebssystems finden Sie unter [Protokolle in TLS/SSL (SChannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/protocols-in-tls-ssl--schannel-ssp-).</p>Bei Anwendungen, die auf eine frühere Version des .NET-Frameworks ausgelegt sind, hängt der Standardwert der <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>-Eigenschaft von der .NET Framework-Zielversion ab. Weitere Informationen finden Sie im [Abschnitt „Netzwerk“ des Artikels „Neuzuweisung von Änderungen für die Migration von .NET Framework 4.5.2 zu 4.6“](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#networking).

#### <a name="suggestion"></a>Vorschlag

Diese Änderung betrifft nur Anwendungen, die auf .NET Framework 4.7 oder höher ausgelegt sind. Wenn Sie lieber ein definiertes Protokoll anstelle des Systemstandards verwenden möchten, können Sie den Wert der <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>-Eigenschaft explizit festlegen. Wenn diese Änderung nicht erwünscht ist, können Sie sich dagegen entscheiden, indem Sie dem Abschnitt [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer Anwendungskonfigurationsdatei eine Konfigurationseinstellung hinzufügen. Im folgenden Beispiel sind sowohl der Abschnitt `<runtime>` als auch die Ablehnungsoption `Switch.System.Net.DontEnableSystemDefaultTlsVersions` dargestellt:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSystemDefaultTlsVersions=true" />
</runtime>
```

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.7         |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>
