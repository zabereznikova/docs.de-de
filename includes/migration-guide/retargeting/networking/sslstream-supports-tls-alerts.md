---
ms.openlocfilehash: 5b566dd89801caff7a253abc2fb62c5fd79591f7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606637"
---
### <a name="sslstream-supports-tls-alerts"></a><span data-ttu-id="8626a-101">SslStream unterstützt TLS-Warnungen</span><span class="sxs-lookup"><span data-stu-id="8626a-101">SslStream supports TLS Alerts</span></span>

#### <a name="details"></a><span data-ttu-id="8626a-102">Details</span><span class="sxs-lookup"><span data-stu-id="8626a-102">Details</span></span>

<span data-ttu-id="8626a-103">Nach einem fehlgeschlagenen TLS-Handshake wird eine <xref:System.IO.IOException?displayProperty=fullName> mit einer inneren <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> von dem ersten E/A-Lese-/Schreibvorgang ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="8626a-103">After a failed TLS handshake, an <xref:System.IO.IOException?displayProperty=fullName> with an inner <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> exception will be thrown by the first I/O Read/Write operation.</span></span> <span data-ttu-id="8626a-104">Der <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=fullName>-Code für die <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> kann der TLS-Warnung von der Remotepartei mit den [Schannel-Fehlercodes für TLS- und SSL-Warnungen](/windows/desktop/SecAuthN/schannel-error-codes-for-tls-and-ssl-alerts) zugeordnet werden. Weitere Informationen finden Sie unter [RFC 2246: Abschnitt 7.2.2, Fehlerwarnungen](https://tools.ietf.org/html/rfc2246#section-7.2.2).</span><span class="sxs-lookup"><span data-stu-id="8626a-104">The <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=fullName> code for the <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> can be mapped to the TLS Alert from the remote party using the [Schannel error codes for TLS and SSL alerts](/windows/desktop/SecAuthN/schannel-error-codes-for-tls-and-ssl-alerts).For more information, see [RFC 2246: Section 7.2.2 Error alerts](https://tools.ietf.org/html/rfc2246#section-7.2.2).</span></span> <br/><span data-ttu-id="8626a-105">Das Verhalten in .NET Framework 4.6.2 und früheren Versionen besteht darin, dass für den Transportkanal (in der Regel eine TCP-Verbindung) ein Timeout während des Schreib- oder Lesevorgangs auftritt, wenn beim Handshake bei der anderen Partei ein Fehler aufgetreten ist und die Verbindung unmittelbar danach zurückgewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="8626a-105">The behavior in .NET Framework 4.6.2 and earlier is that the transport channel (usually TCP connection) will timeout during either Write or Read if the other party failed the handshake and immediately afterwards rejected the connection.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8626a-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="8626a-106">Suggestion</span></span>

<span data-ttu-id="8626a-107">Anwendungen, die Netzwerk-E/A-APIs aufrufen (z.B. <xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)>) sollten <xref:System.IO.IOException> oder <xref:System.TimeoutException?displayProperty=fullName> verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="8626a-107">Applications calling network I/O APIs such as <xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)> should handle <xref:System.IO.IOException> or <xref:System.TimeoutException?displayProperty=fullName>.</span></span><br/><span data-ttu-id="8626a-108">Die TLS-Warnfunktion ist ab .NET Framework 4.7 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8626a-108">The TLS Alerts feature is enabled by default starting with .NET Framework 4.7.</span></span> <span data-ttu-id="8626a-109">Für Anwendungen für Versionen von .NET Framework von 4.0 bis 4.6.2, die auf einem System mit .NET Framework 4.7 oder höher ausgeführt werden, ist diese Funktion deaktiviert, um die Kompatibilität zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8626a-109">Applications targeting versions of the .NET Framework from 4.0 through 4.6.2 running on a .NET Framework 4.7 or higher system will have the feature disabled to preserve compatibility.</span></span> <br/><span data-ttu-id="8626a-110">Die folgende Konfigurations-API ist zum Aktivieren oder Deaktivieren des Features für .NET Framework 4.6- oder höhere Anwendungen, die unter .NET Framework 4.7 oder höher ausgeführt werden, verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8626a-110">The following configuration API is available to enable or disable the feature for .NET Framework 4.6 and later applications running on .NET Framework 4.7 or later.</span></span>

- <span data-ttu-id="8626a-111">Programmgesteuert:   Die folgenden Methoden müssen unmittelbar nach dem Anwendungsstart aufgerufen werden, da ServicePointManager nur einmal initialisiert wird:</span><span class="sxs-lookup"><span data-stu-id="8626a-111">Programmatically:   Must be the very first thing the application does since ServicePointManager will initialize only once:</span></span>

    ```csharp
    AppContext.SetSwitch("TestSwitch.LocalAppContext.DisableCaching", true);

    // Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2.
    AppContext.SetSwitch("Switch.System.Net.DontEnableTlsAlerts", true);
    ```

- <span data-ttu-id="8626a-112">AppConfig:</span><span class="sxs-lookup"><span data-stu-id="8626a-112">AppConfig:</span></span>

    ```xml
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Net.DontEnableTlsAlerts=true"/>
      <!-- Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2. -->
    </runtime>
    ```

- <span data-ttu-id="8626a-113">Registrierungsschlüssel (globaler Wert für einen Computer):   Legen Sie den Wert auf `false` fest, um das Feature in .NET Framework 4.6 bis 4.6.2 zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8626a-113">Registry key (machine global):   Set the Value to `false` to enable the feature in .NET Framework 4.6 - 4.6.2.</span></span>

    ```ini
    Key: HKLM\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\AppContext\Switch.System.Net.DontEnableTlsAlerts
    - Type: String
    - Value: "true"
    ```

| <span data-ttu-id="8626a-114">name</span><span class="sxs-lookup"><span data-stu-id="8626a-114">Name</span></span>    | <span data-ttu-id="8626a-115">Wert</span><span class="sxs-lookup"><span data-stu-id="8626a-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8626a-116">Bereich</span><span class="sxs-lookup"><span data-stu-id="8626a-116">Scope</span></span>   | <span data-ttu-id="8626a-117">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8626a-117">Edge</span></span>        |
| <span data-ttu-id="8626a-118">Version</span><span class="sxs-lookup"><span data-stu-id="8626a-118">Version</span></span> | <span data-ttu-id="8626a-119">4.7</span><span class="sxs-lookup"><span data-stu-id="8626a-119">4.7</span></span>         |
| <span data-ttu-id="8626a-120">Typ</span><span class="sxs-lookup"><span data-stu-id="8626a-120">Type</span></span>    | <span data-ttu-id="8626a-121">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="8626a-121">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="8626a-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="8626a-122">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.WebRequest?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Http?displayProperty=nameWithType>
