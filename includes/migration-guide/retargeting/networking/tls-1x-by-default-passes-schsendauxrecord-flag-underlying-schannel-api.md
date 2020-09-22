---
ms.openlocfilehash: 9fd4e570d9476f5ac4c310759113d72b354a3060
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606940"
---
### <a name="tls-1x-by-default-passes-the-sch_send_aux_record-flag-to-the-underlying-schannel-api"></a><span data-ttu-id="7bbb2-101">TLS 1.x übergibt standardmäßig das Flag SCH_SEND_AUX_RECORD an die zugrunde liegende SCHANNEL-API</span><span class="sxs-lookup"><span data-stu-id="7bbb2-101">TLS 1.x by default passes the SCH_SEND_AUX_RECORD flag to the underlying SCHANNEL API</span></span>

#### <a name="details"></a><span data-ttu-id="7bbb2-102">Details</span><span class="sxs-lookup"><span data-stu-id="7bbb2-102">Details</span></span>

<span data-ttu-id="7bbb2-103">Bei Nutzung von TLS 1 verwendet .NET Framework die zugrunde liegende Windows-SCHANNEL-API.</span><span class="sxs-lookup"><span data-stu-id="7bbb2-103">When using TLS 1.x, the .NET Framework relies on the underlying Windows SCHANNEL API.</span></span> <span data-ttu-id="7bbb2-104">Ab .NET Framework 4.6 wird das Flag [SCH_SEND_AUX_RECORD](/windows/win32/api/schannel/ns-schannel-schannel_cred) standardmäßig an SCHANNEL übergeben.</span><span class="sxs-lookup"><span data-stu-id="7bbb2-104">Starting with .NET Framework 4.6, the [SCH_SEND_AUX_RECORD](/windows/win32/api/schannel/ns-schannel-schannel_cred) flag is passed by default to SCHANNEL.</span></span> <span data-ttu-id="7bbb2-105">Dies bewirkt, dass SCHANNEL die zu verschlüsselnden Daten auf zwei Datensätze aufteilt, wobei der erste aus einem Einzelbyte und der zweite aus <em>n</em> – 1 Bytes besteht. In seltenen Fällen unterbricht dies die Kommunikation zwischen Clients und vorhandenen Servern, die von der Annahme ausgehen, dass die Daten in einem einzelnen Datensatz gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="7bbb2-105">This causes SCHANNEL to split data to be encrypted into two separate records, the first as a single byte and the second as <em>n</em>-1 bytes.In rare cases, this breaks communication between clients and existing servers that make the assumption that the data resides in a single record.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7bbb2-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="7bbb2-106">Suggestion</span></span>

<span data-ttu-id="7bbb2-107">Wenn diese Änderung die Kommunikation mit einem vorhandenen Server unterbricht, können Sie das Senden des Flags [SCH_SEND_AUX_RECORD](/windows/win32/api/schannel/ns-schannel-schannel_cred) deaktivieren und das vorherige Verhalten wiederherstellen, mit dem Daten nicht in separate Datensätze aufgeteilt werden, indem Sie dem Element [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) den folgenden Parameter im Abschnitt [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer Anwendungskonfigurationsdatei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="7bbb2-107">If this change breaks communication with an existing server, you can disable sending the [SCH_SEND_AUX_RECORD](/windows/win32/api/schannel/ns-schannel-schannel_cred) flag and restore the previous behavior of not splitting data into separate records by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchSendAuxRecord=true" />
</runtime>
```

> [!IMPORTANT]
> <span data-ttu-id="7bbb2-108">Diese Einstellung wird lediglich aus Gründen der Abwärtskompatibilität bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7bbb2-108">This setting is provided for backward compatibility only.</span></span> <span data-ttu-id="7bbb2-109">Abgesehen davon wird die Verwendung nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="7bbb2-109">Its use is otherwise not recommended.</span></span>

| <span data-ttu-id="7bbb2-110">name</span><span class="sxs-lookup"><span data-stu-id="7bbb2-110">Name</span></span>    | <span data-ttu-id="7bbb2-111">Wert</span><span class="sxs-lookup"><span data-stu-id="7bbb2-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7bbb2-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="7bbb2-112">Scope</span></span>   | <span data-ttu-id="7bbb2-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7bbb2-113">Edge</span></span>        |
| <span data-ttu-id="7bbb2-114">Version</span><span class="sxs-lookup"><span data-stu-id="7bbb2-114">Version</span></span> | <span data-ttu-id="7bbb2-115">4.6</span><span class="sxs-lookup"><span data-stu-id="7bbb2-115">4.6</span></span>         |
| <span data-ttu-id="7bbb2-116">Typ</span><span class="sxs-lookup"><span data-stu-id="7bbb2-116">Type</span></span>    | <span data-ttu-id="7bbb2-117">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="7bbb2-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="7bbb2-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="7bbb2-118">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.ServicePointManager?displayProperty=nameWithType>
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
