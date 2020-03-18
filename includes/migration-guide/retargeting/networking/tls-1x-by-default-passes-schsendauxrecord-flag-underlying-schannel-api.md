---
ms.openlocfilehash: fc17efbad63ee43ddcdfd14e2fbd1557d2b3d31c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "72424777"
---
### <a name="tls-1x-by-default-passes-the-sch_send_aux_record-flag-to-the-underlying-schannel-api"></a>TLS 1.x übergibt standardmäßig das Flag SCH_SEND_AUX_RECORD an die zugrunde liegende SCHANNEL-API

|   |   |
|---|---|
|Details|Bei Nutzung von TLS 1 verwendet .NET Framework die zugrunde liegende Windows-SCHANNEL-API. Ab .NET Framework 4.6 wird das Flag [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) standardmäßig an SCHANNEL übergeben. Dies bewirkt, dass SCHANNEL die zu verschlüsselnden Daten auf zwei Datensätze aufteilt, wobei der erste aus einem Einzelbyte und der zweite aus <em>n</em> – 1 Bytes besteht. In seltenen Fällen unterbricht dies die Kommunikation zwischen Clients und vorhandenen Servern, die von der Annahme ausgehen, dass die Daten in einem einzelnen Datensatz gespeichert sind.|
|Vorschlag|Wenn diese Änderung die Kommunikation mit einem vorhandenen Server unterbricht, können Sie das Senden des Flags [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) deaktivieren und das vorherige Verhalten wiederherstellen, mit dem Daten nicht in separate Datensätze aufgeteilt werden, indem Sie dem Element [<](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) den folgenden Parameter im Abschnitt [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer Anwendungskonfigurationsdatei hinzufügen:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Net.DontEnableSchSendAuxRecord=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre> <blockquote> [!IMPORTANT] Diese Einstellung wird lediglich aus Gründen der Abwärtskompatibilität bereitgestellt. Abgesehen davon wird die Verwendung nicht empfohlen.</blockquote> |
|`Scope`|Edge|
|Version|4.6|
|Geben Sie Folgendes ein:|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Net.Security.SslStream?displayProperty=nameWithType></li><li><xref:System.Net.ServicePointManager?displayProperty=nameWithType></li><li><xref:System.Net.Http.HttpClient?displayProperty=nameWithType></li><li><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType></li><li><xref:System.Net.HttpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.FtpWebRequest?displayProperty=nameWithType></li></ul>|
