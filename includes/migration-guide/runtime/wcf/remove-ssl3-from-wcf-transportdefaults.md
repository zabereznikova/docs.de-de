---
ms.openlocfilehash: a5f4047d70276a90c9d72918a2559fd795feb26e
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770914"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a><span data-ttu-id="d7def-101">Entfernen von „Ssl3“ aus der WCF-Klasse „TransportDefaults“</span><span class="sxs-lookup"><span data-stu-id="d7def-101">Remove Ssl3 from the WCF TransportDefaults</span></span>

#### <a name="details"></a><span data-ttu-id="d7def-102">Details</span><span class="sxs-lookup"><span data-stu-id="d7def-102">Details</span></span>

<span data-ttu-id="d7def-103">Bei der Verwendung von NetTcp im Transportsicherheitsmodus und der Einstellung „Zertifikat“ wird das SSL3-Protokoll nicht mehr als eins der Standardprotokolle für das Aushandeln einer sicheren Verbindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7def-103">When using NetTcp with transport security and a credential type of certificate, the SSL 3 protocol is no longer a default protocol used for negotiating a secure connection.</span></span> <span data-ttu-id="d7def-104">In den meisten Fällen sollte es keine Auswirkungen auf vorhandene Apps geben, da TLS 1.0 schon immer in der Protokollliste für „NetTcp“ enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d7def-104">In most cases there should be no impact to existing apps as TLS 1.0 has always been included in the protocol list for NetTcp.</span></span> <span data-ttu-id="d7def-105">Alle vorhandenen Clients sollten in der Lage sein, eine Verbindung mit mindestens TLS 1.0 auszuhandeln.</span><span class="sxs-lookup"><span data-stu-id="d7def-105">All existing clients should be able to negotiate a connection using at least TLS1.0.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d7def-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="d7def-106">Suggestion</span></span>

<span data-ttu-id="d7def-107">Wenn Ssl3 erforderlich ist, verwenden Sie eine der folgenden Konfigurationsmechanismen, um Ssl3 der Liste der ausgehandelten Protokolle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d7def-107">If Ssl3 is required, use one of the following configuration mechanisms to add Ssl3 to the list of negotiated protocols.</span></span>

- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols>
- <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols>
- [<span data-ttu-id="d7def-108">\<transport> von \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="d7def-108">\<transport> of \<netTcpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)
- [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)

| <span data-ttu-id="d7def-109">name</span><span class="sxs-lookup"><span data-stu-id="d7def-109">Name</span></span>    | <span data-ttu-id="d7def-110">Wert</span><span class="sxs-lookup"><span data-stu-id="d7def-110">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="d7def-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="d7def-111">Scope</span></span>   | <span data-ttu-id="d7def-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d7def-112">Edge</span></span>    |
| <span data-ttu-id="d7def-113">Version</span><span class="sxs-lookup"><span data-stu-id="d7def-113">Version</span></span> | <span data-ttu-id="d7def-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="d7def-114">4.6.2</span></span>   |
| <span data-ttu-id="d7def-115">Typ</span><span class="sxs-lookup"><span data-stu-id="d7def-115">Type</span></span>    | <span data-ttu-id="d7def-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="d7def-116">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d7def-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="d7def-117">Affected APIs</span></span>

- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols`
- `P:System.ServiceModel.TcpTransportSecurity.SslProtocols`

-->
