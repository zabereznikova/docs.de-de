---
ms.openlocfilehash: 16994e9cd97b31a30c8c5ce49d2042ff79b3f60b
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050517"
---
### <a name="negotiatestream-and-sslstream-allow-successive-begin-operations"></a><span data-ttu-id="f377f-101">NegotiateStream und SslStream lassen aufeinanderfolgende Begin-Vorgänge zu</span><span class="sxs-lookup"><span data-stu-id="f377f-101">NegotiateStream and SslStream allow successive Begin operations</span></span>

<span data-ttu-id="f377f-102">Fehler in Sicherheitsstreams werden anders gehandhabt, und aufeinanderfolgende Aufrufe von `BeginAuthenticateAsServer` oder `BeginAuthenticateAsClient` sollten nicht mehr fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="f377f-102">Error cases on security streams are handled differently, and successive calls to `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` may no longer fail.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f377f-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="f377f-103">Version introduced</span></span>

<span data-ttu-id="f377f-104">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="f377f-104">5.0 RC1</span></span>

#### <a name="change-description"></a><span data-ttu-id="f377f-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="f377f-105">Change description</span></span>

<span data-ttu-id="f377f-106">In früheren .NET-Versionen führten aufeinanderfolgende Aufrufe von `BeginAuthenticateAsServer` oder `BeginAuthenticateAsClient` ohne vorheriges Aufrufen von `EndAuthenticateAsServer` oder `EndAuthenticateAsClient` zu einer <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="f377f-106">In previous .NET versions, calling `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` successively without first calling `EndAuthenticateAsServer` or `EndAuthenticateAsClient` results in a <xref:System.NotSupportedException>.</span></span> <span data-ttu-id="f377f-107">Ab .NET 5.0 führen aufeinanderfolgende Aufrufe von `BeginAuthenticateAsServer` oder `BeginAuthenticateAsClient` nicht mehr zu einer <xref:System.NotSupportedException>, da diese APIs von einer <xref:System.Threading.Tasks.Task>-basierten Implementierung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="f377f-107">Starting in .NET 5.0, successive calls to `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` no longer result in a <xref:System.NotSupportedException>, because these APIs are backed by a <xref:System.Threading.Tasks.Task>-based implementation.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f377f-108">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="f377f-108">Reason for change</span></span>

<span data-ttu-id="f377f-109">Wenn Sie bei der internen Implementierung vom asynchronen Programmiermodell zur <xref:System.Threading.Tasks.Task>-basierten Implementierung wechseln, wird die Leistung verbessert, und der Code ist weniger komplex.</span><span class="sxs-lookup"><span data-stu-id="f377f-109">Switching the internal implementation from asynchronous programming model (APM) to <xref:System.Threading.Tasks.Task>-based improves performance and decreases code complexity.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f377f-110">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="f377f-110">Recommended action</span></span>

<span data-ttu-id="f377f-111">Auf der Seite des Entwicklers ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f377f-111">No action is required on the part of the developer.</span></span>

#### <a name="category"></a><span data-ttu-id="f377f-112">Kategorie</span><span class="sxs-lookup"><span data-stu-id="f377f-112">Category</span></span>

<span data-ttu-id="f377f-113">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="f377f-113">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f377f-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="f377f-114">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.SslStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsClient`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient`

-->
