---
title: 'Breaking Change: NegotiateStream und SslStream lassen aufeinanderfolgende Begin-Vorgänge zu'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den Fehler auf Sicherheitsstreams anders gehandhabt werden und aufeinander folgende Aufrufe von BeginAuthenticateAsServer oder BeginAuthenticateAsClient nicht mehr fehlschlagen.
ms.date: 10/18/2020
ms.openlocfilehash: e0226d0f5586efca050ca3497ca1490fa21fd943
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759385"
---
# <a name="negotiatestream-and-sslstream-allow-successive-begin-operations"></a><span data-ttu-id="20487-103">NegotiateStream und SslStream lassen aufeinanderfolgende Begin-Vorgänge zu</span><span class="sxs-lookup"><span data-stu-id="20487-103">NegotiateStream and SslStream allow successive Begin operations</span></span>

<span data-ttu-id="20487-104">Fehler in Sicherheitsstreams werden anders gehandhabt, und aufeinanderfolgende Aufrufe von `BeginAuthenticateAsServer` oder `BeginAuthenticateAsClient` sollten nicht mehr fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="20487-104">Error cases on security streams are handled differently, and successive calls to `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` may no longer fail.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="20487-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="20487-105">Version introduced</span></span>

<span data-ttu-id="20487-106">5.0</span><span class="sxs-lookup"><span data-stu-id="20487-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="20487-107">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="20487-107">Change description</span></span>

<span data-ttu-id="20487-108">In früheren .NET-Versionen führten aufeinanderfolgende Aufrufe von `BeginAuthenticateAsServer` oder `BeginAuthenticateAsClient` ohne vorheriges Aufrufen von `EndAuthenticateAsServer` oder `EndAuthenticateAsClient` zu einer <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="20487-108">In previous .NET versions, calling `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` successively without first calling `EndAuthenticateAsServer` or `EndAuthenticateAsClient` results in a <xref:System.NotSupportedException>.</span></span> <span data-ttu-id="20487-109">Ab .NET 5.0 führen aufeinanderfolgende Aufrufe von `BeginAuthenticateAsServer` oder `BeginAuthenticateAsClient` nicht mehr zu einer <xref:System.NotSupportedException>, da diese APIs von einer <xref:System.Threading.Tasks.Task>-basierten Implementierung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="20487-109">Starting in .NET 5.0, successive calls to `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` no longer result in a <xref:System.NotSupportedException>, because these APIs are backed by a <xref:System.Threading.Tasks.Task>-based implementation.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="20487-110">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="20487-110">Reason for change</span></span>

<span data-ttu-id="20487-111">Wenn Sie bei der internen Implementierung vom asynchronen Programmiermodell zur <xref:System.Threading.Tasks.Task>-basierten Implementierung wechseln, wird die Leistung verbessert, und der Code ist weniger komplex.</span><span class="sxs-lookup"><span data-stu-id="20487-111">Switching the internal implementation from asynchronous programming model (APM) to <xref:System.Threading.Tasks.Task>-based improves performance and decreases code complexity.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="20487-112">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="20487-112">Recommended action</span></span>

<span data-ttu-id="20487-113">Auf der Seite des Entwicklers ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="20487-113">No action is required on the part of the developer.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="20487-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="20487-114">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.SslStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsClient`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient`

### Category

Networking

-->
