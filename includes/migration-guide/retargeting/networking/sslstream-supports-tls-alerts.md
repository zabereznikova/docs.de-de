---
ms.openlocfilehash: 5b566dd89801caff7a253abc2fb62c5fd79591f7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606637"
---
### <a name="sslstream-supports-tls-alerts"></a>SslStream unterstützt TLS-Warnungen

#### <a name="details"></a>Details

Nach einem fehlgeschlagenen TLS-Handshake wird eine <xref:System.IO.IOException?displayProperty=fullName> mit einer inneren <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> von dem ersten E/A-Lese-/Schreibvorgang ausgelöst. Der <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=fullName>-Code für die <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> kann der TLS-Warnung von der Remotepartei mit den [Schannel-Fehlercodes für TLS- und SSL-Warnungen](/windows/desktop/SecAuthN/schannel-error-codes-for-tls-and-ssl-alerts) zugeordnet werden. Weitere Informationen finden Sie unter [RFC 2246: Abschnitt 7.2.2, Fehlerwarnungen](https://tools.ietf.org/html/rfc2246#section-7.2.2). <br/>Das Verhalten in .NET Framework 4.6.2 und früheren Versionen besteht darin, dass für den Transportkanal (in der Regel eine TCP-Verbindung) ein Timeout während des Schreib- oder Lesevorgangs auftritt, wenn beim Handshake bei der anderen Partei ein Fehler aufgetreten ist und die Verbindung unmittelbar danach zurückgewiesen wurde.

#### <a name="suggestion"></a>Vorschlag

Anwendungen, die Netzwerk-E/A-APIs aufrufen (z.B. <xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)>) sollten <xref:System.IO.IOException> oder <xref:System.TimeoutException?displayProperty=fullName> verarbeiten.<br/>Die TLS-Warnfunktion ist ab .NET Framework 4.7 standardmäßig aktiviert. Für Anwendungen für Versionen von .NET Framework von 4.0 bis 4.6.2, die auf einem System mit .NET Framework 4.7 oder höher ausgeführt werden, ist diese Funktion deaktiviert, um die Kompatibilität zu erhalten. <br/>Die folgende Konfigurations-API ist zum Aktivieren oder Deaktivieren des Features für .NET Framework 4.6- oder höhere Anwendungen, die unter .NET Framework 4.7 oder höher ausgeführt werden, verfügbar.

- Programmgesteuert:   Die folgenden Methoden müssen unmittelbar nach dem Anwendungsstart aufgerufen werden, da ServicePointManager nur einmal initialisiert wird:

    ```csharp
    AppContext.SetSwitch("TestSwitch.LocalAppContext.DisableCaching", true);

    // Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2.
    AppContext.SetSwitch("Switch.System.Net.DontEnableTlsAlerts", true);
    ```

- AppConfig:

    ```xml
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Net.DontEnableTlsAlerts=true"/>
      <!-- Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2. -->
    </runtime>
    ```

- Registrierungsschlüssel (globaler Wert für einen Computer):   Legen Sie den Wert auf `false` fest, um das Feature in .NET Framework 4.6 bis 4.6.2 zu aktivieren.

    ```ini
    Key: HKLM\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\AppContext\Switch.System.Net.DontEnableTlsAlerts
    - Type: String
    - Value: "true"
    ```

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.7         |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.WebRequest?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Http?displayProperty=nameWithType>
