---
ms.openlocfilehash: 0ea8c4843bb0dfb4e4208f2bfad4c416bfae7a1e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234453"
---
### <a name="tls-1x-by-default-passes-the-schsendauxrecord-flag-to-the-underlying-schannel-api"></a>TLS 1.x übergibt standardmäßig das Flag SCH_SEND_AUX_RECORD an die zugrunde liegende SCHANNEL-API

|   |   |
|---|---|
|Details|Bei Nutzung von TLS 1 verwendet .NET Framework die zugrunde liegende Windows-SCHANNEL-API. Ab .NET Framework 4.6 wird das Flag [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/desktop/api/schannel/ns-schannel-_schannel_cred) standardmäßig an SCHANNEL übergeben. Dies führt dazu, dass SCHANNEL die zu verschlüsselnden Daten in zwei getrennte Datensätze aufteilt, den ersten als Einzelbyte und den zweiten als <em>n</em>-1 Bytes. In seltenen Fällen wird dadurch die Kommunikation zwischen Clients und vorhandenen Servern unterbrochen, die davon ausgehen, dass sich die Daten in einem einzigen Datensatz befinden.|
|Vorschlag|Wenn diese Änderung die Kommunikation mit einem vorhandenen Server unterbricht, können Sie das Senden des [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/desktop/api/schannel/ns-schannel-_schannel_cred)-Flags deaktivieren und das vorherige Verhalten wiederherstellen, Daten nicht in separate Datensätze aufzuteilen, indem Sie den folgenden Schalter zum Element [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) im Abschnitt [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer App-Konfigurationsdatei hinzufügen:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Net.DontEnableSchSendAuxRecord=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre> <blockquote> [!IMPORTANT] Diese Einstellung wird lediglich aus Gründen der Abwärtskompatibilität bereitgestellt. Abgesehen davon wird die Verwendung nicht empfohlen.</blockquote> |
|Bereich|Microsoft Edge|
|Version|4.6|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Net.Security.SslStream?displayProperty=nameWithType></li><li><xref:System.Net.ServicePointManager?displayProperty=nameWithType></li><li><xref:System.Net.Http.HttpClient?displayProperty=nameWithType></li><li><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType></li><li><xref:System.Net.HttpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.FtpWebRequest?displayProperty=nameWithType></li></ul>|
