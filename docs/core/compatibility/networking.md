---
title: Breaking Changes für Netzwerke
description: Liste der Breaking Changes für Netzwerke in .NET Core 2.0 und 3.0
ms.date: 05/05/2020
ms.openlocfilehash: 761c6481888bcb8e91f7b4212355aca067632495
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689211"
---
# <a name="networking-breaking-changes-in-net-core-20-and-30"></a><span data-ttu-id="7e2e6-103">Breaking Changes für Netzwerke in .NET Core 2.0 und 3.0</span><span class="sxs-lookup"><span data-stu-id="7e2e6-103">Networking breaking changes in .NET Core 2.0 and 3.0</span></span>

<span data-ttu-id="7e2e6-104">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="7e2e6-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="7e2e6-105">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="7e2e6-105">Breaking change</span></span> | <span data-ttu-id="7e2e6-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="7e2e6-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="7e2e6-107">Standardwert von HttpRequestMessage.Version wurde in 1.1 geändert</span><span class="sxs-lookup"><span data-stu-id="7e2e6-107">Default value of HttpRequestMessage.Version changed to 1.1</span></span>](#default-value-of-httprequestmessageversion-changed-to-11) | <span data-ttu-id="7e2e6-108">3.0</span><span class="sxs-lookup"><span data-stu-id="7e2e6-108">3.0</span></span> |
| [<span data-ttu-id="7e2e6-109">WebClient.CancelAsync wird nicht immer sofort abgebrochen</span><span class="sxs-lookup"><span data-stu-id="7e2e6-109">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately) | <span data-ttu-id="7e2e6-110">2.0</span><span class="sxs-lookup"><span data-stu-id="7e2e6-110">2.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="7e2e6-111">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="7e2e6-111">.NET Core 3.0</span></span>

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a><span data-ttu-id="7e2e6-112">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="7e2e6-112">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***
