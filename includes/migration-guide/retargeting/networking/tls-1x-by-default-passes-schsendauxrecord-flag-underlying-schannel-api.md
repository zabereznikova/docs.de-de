---
ms.openlocfilehash: 207dba9327cfd6debd15c5573697f8950b6c2c95
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86218198"
---
### <a name="tls-1x-by-default-passes-the-sch_send_aux_record-flag-to-the-underlying-schannel-api"></a>TLS 1.x übergibt standardmäßig das Flag SCH_SEND_AUX_RECORD an die zugrunde liegende SCHANNEL-API

#### <a name="details"></a>Details

Bei Nutzung von TLS 1 verwendet .NET Framework die zugrunde liegende Windows-SCHANNEL-API. Ab .NET Framework 4.6 wird das Flag [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) standardmäßig an SCHANNEL übergeben. Dies bewirkt, dass SCHANNEL die zu verschlüsselnden Daten auf zwei Datensätze aufteilt, wobei der erste aus einem Einzelbyte und der zweite aus <em>n</em> – 1 Bytes besteht. In seltenen Fällen unterbricht dies die Kommunikation zwischen Clients und vorhandenen Servern, die von der Annahme ausgehen, dass die Daten in einem einzelnen Datensatz gespeichert sind.

#### <a name="suggestion"></a>Vorschlag

Wenn diese Änderung die Kommunikation mit einem vorhandenen Server unterbricht, können Sie das Senden des Flags [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) deaktivieren und das vorherige Verhalten wiederherstellen, mit dem Daten nicht in separate Datensätze aufgeteilt werden, indem Sie dem Element [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) den folgenden Parameter im Abschnitt [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer Anwendungskonfigurationsdatei hinzufügen:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchSendAuxRecord=true" />
</runtime>
```

> [!IMPORTANT]
> Diese Einstellung wird lediglich aus Gründen der Abwärtskompatibilität bereitgestellt. Abgesehen davon wird die Verwendung nicht empfohlen.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.6         |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.ServicePointManager?displayProperty=nameWithType>
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
