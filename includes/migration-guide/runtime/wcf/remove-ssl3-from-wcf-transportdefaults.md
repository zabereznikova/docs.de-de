---
ms.openlocfilehash: 9b734fe960165b6d4b97b861cb3e8f31979f25c5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621210"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a><span data-ttu-id="bb17f-101">Entfernen von „Ssl3“ aus der WCF-Klasse „TransportDefaults“</span><span class="sxs-lookup"><span data-stu-id="bb17f-101">Remove Ssl3 from the WCF TransportDefaults</span></span>

#### <a name="details"></a><span data-ttu-id="bb17f-102">Details</span><span class="sxs-lookup"><span data-stu-id="bb17f-102">Details</span></span>

<span data-ttu-id="bb17f-103">Bei der Verwendung von NetTcp im Transportsicherheitsmodus und der Einstellung „Zertifikat“ wird das SSL3-Protokoll nicht mehr als eins der Standardprotokolle für das Aushandeln einer sicheren Verbindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="bb17f-103">When using NetTcp with transport security and a credential type of certificate, the SSL 3 protocol is no longer a default protocol used for negotiating a secure connection.</span></span> <span data-ttu-id="bb17f-104">In den meisten Fällen sollte es keine Auswirkungen auf vorhandene Apps geben, da TLS 1.0 schon immer in der Protokollliste für „NetTcp“ enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="bb17f-104">In most cases there should be no impact to existing apps as TLS 1.0 has always been included in the protocol list for NetTcp.</span></span> <span data-ttu-id="bb17f-105">Alle vorhandenen Clients sollten in der Lage sein, eine Verbindung mit mindestens TLS 1.0 auszuhandeln.</span><span class="sxs-lookup"><span data-stu-id="bb17f-105">All existing clients should be able to negotiate a connection using at least TLS1.0.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bb17f-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="bb17f-106">Suggestion</span></span>

<span data-ttu-id="bb17f-107">Wenn Ssl3 erforderlich ist, verwenden Sie eine der folgenden Konfigurationsmechanismen, um Ssl3 der Liste der ausgehandelten Protokolle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="bb17f-107">If Ssl3 is required, use one of the following configuration mechanisms to add Ssl3 to the list of negotiated protocols.</span></span><ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols></li><li>[<](~/docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)</li><li><span data-ttu-id="bb17f-108">[&lt;sslStreamSecurity&gt; section of &lt;customBinding&gt;]~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</span><span class="sxs-lookup"><span data-stu-id="bb17f-108">[&lt;sslStreamSecurity&gt; section of &lt;customBinding&gt;]~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</span></span></li></ul>

| <span data-ttu-id="bb17f-109">Name</span><span class="sxs-lookup"><span data-stu-id="bb17f-109">Name</span></span>    | <span data-ttu-id="bb17f-110">Wert</span><span class="sxs-lookup"><span data-stu-id="bb17f-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bb17f-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="bb17f-111">Scope</span></span>   |<span data-ttu-id="bb17f-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bb17f-112">Edge</span></span>|
|<span data-ttu-id="bb17f-113">Version</span><span class="sxs-lookup"><span data-stu-id="bb17f-113">Version</span></span>|<span data-ttu-id="bb17f-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="bb17f-114">4.6.2</span></span>|
|<span data-ttu-id="bb17f-115">Typ</span><span class="sxs-lookup"><span data-stu-id="bb17f-115">Type</span></span>|<span data-ttu-id="bb17f-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="bb17f-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bb17f-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="bb17f-117">Affected APIs</span></span>

-<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType></li></ul>|
