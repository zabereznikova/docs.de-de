---
title: Breaking Changes für Netzwerke
description: Listet die Breaking Changes für Netzwerke in .NET Core auf.
ms.date: 05/05/2020
ms.openlocfilehash: fdbd3f3bdcae5048b4f01e4d827f8a0e876c5c15
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050516"
---
# <a name="networking-breaking-changes"></a><span data-ttu-id="acc61-103">Breaking Changes für Netzwerke</span><span class="sxs-lookup"><span data-stu-id="acc61-103">Networking breaking changes</span></span>

<span data-ttu-id="acc61-104">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="acc61-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="acc61-105">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="acc61-105">Breaking change</span></span> | <span data-ttu-id="acc61-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="acc61-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="acc61-107">NegotiateStream und SslStream lassen aufeinanderfolgende Begin-Vorgänge zu</span><span class="sxs-lookup"><span data-stu-id="acc61-107">NegotiateStream and SslStream allow successive Begin operations</span></span>](#negotiatestream-and-sslstream-allow-successive-begin-operations) | <span data-ttu-id="acc61-108">5.0</span><span class="sxs-lookup"><span data-stu-id="acc61-108">5.0</span></span> |
| [<span data-ttu-id="acc61-109">Socket.LocalEndPoint wird nach dem Aufruf von SendToAsync aktualisiert</span><span class="sxs-lookup"><span data-stu-id="acc61-109">Socket.LocalEndPoint is updated after calling SendToAsync</span></span>](#socketlocalendpoint-is-updated-after-calling-sendtoasync) | <span data-ttu-id="acc61-110">5.0</span><span class="sxs-lookup"><span data-stu-id="acc61-110">5.0</span></span> |
| [<span data-ttu-id="acc61-111">Entfernung von WinHttpHandler aus der .NET-Runtime</span><span class="sxs-lookup"><span data-stu-id="acc61-111">WinHttpHandler removed from .NET runtime</span></span>](#winhttphandler-removed-from-net-runtime) | <span data-ttu-id="acc61-112">5.0</span><span class="sxs-lookup"><span data-stu-id="acc61-112">5.0</span></span> |
| [<span data-ttu-id="acc61-113">MulticastOption.Group akzeptiert keine null-Werte</span><span class="sxs-lookup"><span data-stu-id="acc61-113">MulticastOption.Group doesn't accept a null value</span></span>](#multicastoptiongroup-doesnt-accept-a-null-value) | <span data-ttu-id="acc61-114">5.0</span><span class="sxs-lookup"><span data-stu-id="acc61-114">5.0</span></span> |
| [<span data-ttu-id="acc61-115">Verarbeitung von Cookiepfaden jetzt mit RFC 6265 konform</span><span class="sxs-lookup"><span data-stu-id="acc61-115">Cookie Path handling now conforms to RFC 6265</span></span>](#cookie-path-handling-now-conforms-to-rfc-6265) | <span data-ttu-id="acc61-116">5.0</span><span class="sxs-lookup"><span data-stu-id="acc61-116">5.0</span></span> |
| [<span data-ttu-id="acc61-117">Standardwert von HttpRequestMessage.Version wurde in 1.1 geändert</span><span class="sxs-lookup"><span data-stu-id="acc61-117">Default value of HttpRequestMessage.Version changed to 1.1</span></span>](#default-value-of-httprequestmessageversion-changed-to-11) | <span data-ttu-id="acc61-118">3.0</span><span class="sxs-lookup"><span data-stu-id="acc61-118">3.0</span></span> |
| [<span data-ttu-id="acc61-119">WebClient.CancelAsync wird nicht immer sofort abgebrochen</span><span class="sxs-lookup"><span data-stu-id="acc61-119">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately) | <span data-ttu-id="acc61-120">2.0</span><span class="sxs-lookup"><span data-stu-id="acc61-120">2.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="acc61-121">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="acc61-121">.NET 5.0</span></span>

[!INCLUDE [negotiatestream-sslstream-dont-fail-on-successive-begin-calls](../../../includes/core-changes/networking/5.0/negotiatestream-sslstream-dont-fail-on-successive-begin-calls.md)]

***

[!INCLUDE [localendpoint-updated-on-sendtoasync](../../../includes/core-changes/networking/5.0/localendpoint-updated-on-sendtoasync.md)]

***

[!INCLUDE [winhttphandler-removed-from-runtime](../../../includes/core-changes/networking/5.0/winhttphandler-removed-from-runtime.md)]

***

[!INCLUDE [multicastoption-group-doesnt-accept-null](../../../includes/core-changes/networking/5.0/multicastoption-group-doesnt-accept-null.md)]

***

[!INCLUDE [cookie-path-conforms-to-rfc6265](../../../includes/core-changes/networking/5.0/cookie-path-conforms-to-rfc6265.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="acc61-122">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="acc61-122">.NET Core 3.0</span></span>

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a><span data-ttu-id="acc61-123">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="acc61-123">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***
