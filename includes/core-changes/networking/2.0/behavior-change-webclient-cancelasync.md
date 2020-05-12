---
ms.openlocfilehash: 80d4bbbfe52ab9685d7ca54f21b80d4b1773da22
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859619"
---
### <a name="webclientcancelasync-doesnt-always-cancel-immediately"></a><span data-ttu-id="4324e-101">WebClient.CancelAsync wird nicht immer sofort abgebrochen</span><span class="sxs-lookup"><span data-stu-id="4324e-101">WebClient.CancelAsync doesn't always cancel immediately</span></span>

<span data-ttu-id="4324e-102">Ab .NET Core 2.0 wird die Anforderung beim Aufrufen von <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> nicht sofort abgebrochen, wenn die Antwort mit dem Abrufen begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="4324e-102">Starting in .NET Core 2.0, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> doesn't cancel the request immediately if the response has started to fetch.</span></span>

#### <a name="change-description"></a><span data-ttu-id="4324e-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="4324e-103">Change description</span></span>

<span data-ttu-id="4324e-104">Zuvor wurde durch Aufrufen von <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> die Anforderung sofort abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="4324e-104">Previously, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> canceled the request immediately.</span></span> <span data-ttu-id="4324e-105">Ab .NET Core 2.0 wird die Anforderung beim Aufrufen von <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> nur dann sofort abgebrochen, wenn die Antwort mit dem Abrufen noch nicht begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="4324e-105">Starting in .NET Core 2.0, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> cancels the request immediately only if the response hasn't started fetching.</span></span> <span data-ttu-id="4324e-106">Wenn die Antwort mit dem Abrufen begonnen hat, wird die Anforderung erst abgebrochen, nachdem eine vollständige Antwort gelesen wurde.</span><span class="sxs-lookup"><span data-stu-id="4324e-106">If the response has started to fetch, the request is cancelled only after a complete response is read.</span></span>

<span data-ttu-id="4324e-107">Diese Änderung wurde implementiert, weil die <xref:System.Net.WebClient>-API zugunsten von <xref:System.Net.Http.HttpClient> eingestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4324e-107">This change was implemented because the <xref:System.Net.WebClient> API is deprecated in favor of <xref:System.Net.Http.HttpClient>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4324e-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="4324e-108">Version introduced</span></span>

<span data-ttu-id="4324e-109">2.0</span><span class="sxs-lookup"><span data-stu-id="4324e-109">2.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4324e-110">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="4324e-110">Recommended action</span></span>

<span data-ttu-id="4324e-111">Verwenden Sie die <xref:System.Net.Http.HttpClient?displayProperty=fullName>-Klasse anstelle von <xref:System.Net.WebClient?displayProperty=fullName>, die veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="4324e-111">Use the <xref:System.Net.Http.HttpClient?displayProperty=fullName> class instead of <xref:System.Net.WebClient?displayProperty=fullName>, which is deprecated.</span></span>

#### <a name="category"></a><span data-ttu-id="4324e-112">Kategorie</span><span class="sxs-lookup"><span data-stu-id="4324e-112">Category</span></span>

<span data-ttu-id="4324e-113">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="4324e-113">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4324e-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="4324e-114">Affected APIs</span></span>

- <xref:System.Net.WebClient.CancelAsync?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Net.WebClient.CancelAsync`

-->
