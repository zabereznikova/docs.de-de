---
title: Breaking Changes für Netzwerke
description: Listet die Breaking Changes für Netzwerke in .NET Core auf.
ms.date: 05/05/2020
ms.openlocfilehash: fa5807c882c3bc6f66e8a27361ccc14254e90b3e
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465512"
---
# <a name="networking-breaking-changes"></a><span data-ttu-id="828dc-103">Breaking Changes für Netzwerke</span><span class="sxs-lookup"><span data-stu-id="828dc-103">Networking breaking changes</span></span>

<span data-ttu-id="828dc-104">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="828dc-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="828dc-105">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="828dc-105">Breaking change</span></span> | <span data-ttu-id="828dc-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="828dc-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="828dc-107">Entfernung von WinHttpHandler aus der .NET-Runtime</span><span class="sxs-lookup"><span data-stu-id="828dc-107">WinHttpHandler removed from .NET runtime</span></span>](#winhttphandler-removed-from-net-runtime) | <span data-ttu-id="828dc-108">5.0</span><span class="sxs-lookup"><span data-stu-id="828dc-108">5.0</span></span> |
| [<span data-ttu-id="828dc-109">MulticastOption.Group akzeptiert keine null-Werte</span><span class="sxs-lookup"><span data-stu-id="828dc-109">MulticastOption.Group doesn't accept a null value</span></span>](#multicastoptiongroup-doesnt-accept-a-null-value) | <span data-ttu-id="828dc-110">5.0</span><span class="sxs-lookup"><span data-stu-id="828dc-110">5.0</span></span> |
| [<span data-ttu-id="828dc-111">Verarbeitung von Cookiepfaden jetzt mit RFC 6265 konform</span><span class="sxs-lookup"><span data-stu-id="828dc-111">Cookie Path handling now conforms to RFC 6265</span></span>](#cookie-path-handling-now-conforms-to-rfc-6265) | <span data-ttu-id="828dc-112">5.0</span><span class="sxs-lookup"><span data-stu-id="828dc-112">5.0</span></span> |
| [<span data-ttu-id="828dc-113">Standardwert von HttpRequestMessage.Version wurde in 1.1 geändert</span><span class="sxs-lookup"><span data-stu-id="828dc-113">Default value of HttpRequestMessage.Version changed to 1.1</span></span>](#default-value-of-httprequestmessageversion-changed-to-11) | <span data-ttu-id="828dc-114">3.0</span><span class="sxs-lookup"><span data-stu-id="828dc-114">3.0</span></span> |
| [<span data-ttu-id="828dc-115">WebClient.CancelAsync wird nicht immer sofort abgebrochen</span><span class="sxs-lookup"><span data-stu-id="828dc-115">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately) | <span data-ttu-id="828dc-116">2.0</span><span class="sxs-lookup"><span data-stu-id="828dc-116">2.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="828dc-117">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="828dc-117">.NET 5.0</span></span>

[!INCLUDE [winhttphandler-removed-from-runtime](../../../includes/core-changes/networking/5.0/winhttphandler-removed-from-runtime.md)]

***

[!INCLUDE [multicastoption-group-doesnt-accept-null](../../../includes/core-changes/networking/5.0/multicastoption-group-doesnt-accept-null.md)]

***

[!INCLUDE [cookie-path-conforms-to-rfc6265](../../../includes/core-changes/networking/5.0/cookie-path-conforms-to-rfc6265.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="828dc-118">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="828dc-118">.NET Core 3.0</span></span>

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a><span data-ttu-id="828dc-119">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="828dc-119">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***
