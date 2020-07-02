---
ms.openlocfilehash: 0e949cbdeda99dd7b94e919b903a21171a57f527
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614490"
---
### <a name="wcf-binding-with-the-transportwithmessagecredential-security-mode"></a><span data-ttu-id="16a63-101">WCF-Bindung mit dem TransportWithMessageCredential-Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="16a63-101">WCF binding with the TransportWithMessageCredential security mode</span></span>

#### <a name="details"></a><span data-ttu-id="16a63-102">Details</span><span class="sxs-lookup"><span data-stu-id="16a63-102">Details</span></span>

<span data-ttu-id="16a63-103">Ab .NET Framework 4.6.1 kann die WCF-Bindung, die den TransportWithMessageCredential-Sicherheitsmodus verwendet, so eingerichtet werden, dass Nachrichten mit nicht signierten &quot;to&quot;-Headern für asymmetrische Sicherheitsschlüssel empfangen werden. Standardmäßig werden nicht signierte &quot;to&quot;-Header in .NET Framework 4.6.1 weiter abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="16a63-103">Beginning in the .NET Framework 4.6.1, WCF binding that uses the TransportWithMessageCredential security mode can be set up to receive messages with unsigned &quot;to&quot; headers for asymmetric security keys.By default, unsigned &quot;to&quot; headers will continue to be rejected in .NET Framework 4.6.1.</span></span> <span data-ttu-id="16a63-104">Sie werden nur akzeptiert, wenn eine Anwendung unter Verwendung des Switch.System.ServiceModel.AllowUnsignedToHeader-Konfigurationsschalters diesen neuen Vorgangsmodus aktiviert.</span><span class="sxs-lookup"><span data-stu-id="16a63-104">They will only be accepted if an application opts into this new mode of operation using the Switch.System.ServiceModel.AllowUnsignedToHeader configuration switch.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="16a63-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="16a63-105">Suggestion</span></span>

<span data-ttu-id="16a63-106">Da diese Einstellung eine Opt-in-Funktion ist, sollte sie sich nicht auf das Verhalten vorhandener Apps auswirken.</span><span class="sxs-lookup"><span data-stu-id="16a63-106">Because this is an opt-in feature, it should not affect the behavior of existing apps.</span></span><br/><span data-ttu-id="16a63-107">Verwenden Sie die folgende Konfigurationseinstellung, um zu steuern, ob das neue Verhalten verwendet werden soll:</span><span class="sxs-lookup"><span data-stu-id="16a63-107">To control whether the new behavior is used or not, use the following configuration setting:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.ServiceModel.AllowUnsignedToHeader=true" />
</runtime>
```

| <span data-ttu-id="16a63-108">name</span><span class="sxs-lookup"><span data-stu-id="16a63-108">Name</span></span>    | <span data-ttu-id="16a63-109">Wert</span><span class="sxs-lookup"><span data-stu-id="16a63-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="16a63-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="16a63-110">Scope</span></span>   | <span data-ttu-id="16a63-111">Transparent</span><span class="sxs-lookup"><span data-stu-id="16a63-111">Transparent</span></span> |
| <span data-ttu-id="16a63-112">Version</span><span class="sxs-lookup"><span data-stu-id="16a63-112">Version</span></span> | <span data-ttu-id="16a63-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="16a63-113">4.6.1</span></span>       |
| <span data-ttu-id="16a63-114">Typ</span><span class="sxs-lookup"><span data-stu-id="16a63-114">Type</span></span>    | <span data-ttu-id="16a63-115">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="16a63-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="16a63-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="16a63-116">Affected APIs</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpsSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
