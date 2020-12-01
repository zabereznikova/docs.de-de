---
ms.openlocfilehash: 05aec429e28ef74515ef6988d5b064e6d16b7c1b
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032674"
---
### <a name="signalr-handshakeprotocolsuccesshandshakedata-replaced"></a><span data-ttu-id="c1bd1-101">SignalR: HandshakeProtocol.SuccessHandshakeData wurde ersetzt.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-101">SignalR: HandshakeProtocol.SuccessHandshakeData replaced</span></span>

<span data-ttu-id="c1bd1-102">Das Feld [HandshakeProtocol.SuccessHandshakeData](https://github.com/dotnet/aspnetcore/blob/c5b2bc0df2a0027832bf7d01dfb19ca39cd08ae6/src/SignalR/common/SignalR.Common/src/Protocol/HandshakeProtocol.cs#L27) wurde entfernt und durch eine Hilfsmethode ersetzt, die eine erfolgreiche Handshakeantwort für ein bestimmtes `IHubProtocol` generiert.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-102">The [HandshakeProtocol.SuccessHandshakeData](https://github.com/dotnet/aspnetcore/blob/c5b2bc0df2a0027832bf7d01dfb19ca39cd08ae6/src/SignalR/common/SignalR.Common/src/Protocol/HandshakeProtocol.cs#L27) field was removed and replaced with a helper method that generates a successful handshake response given a specific `IHubProtocol`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c1bd1-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="c1bd1-103">Version introduced</span></span>

<span data-ttu-id="c1bd1-104">3.0</span><span class="sxs-lookup"><span data-stu-id="c1bd1-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="c1bd1-105">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="c1bd1-105">Old behavior</span></span>

<span data-ttu-id="c1bd1-106">`HandshakeProtocol.SuccessHandshakeData` war ein `public static ReadOnlyMemory<byte>`-Feld.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-106">`HandshakeProtocol.SuccessHandshakeData` was a `public static ReadOnlyMemory<byte>` field.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="c1bd1-107">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="c1bd1-107">New behavior</span></span>

<span data-ttu-id="c1bd1-108">`HandshakeProtocol.SuccessHandshakeData` wurde durch eine `static` `GetSuccessfulHandshake(IHubProtocol protocol)`-Methode ersetzt, die basierend auf dem angegebenen Protokoll ein `ReadOnlyMemory<byte>`-Element zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-108">`HandshakeProtocol.SuccessHandshakeData` has been replaced by a `static` `GetSuccessfulHandshake(IHubProtocol protocol)` method that returns a `ReadOnlyMemory<byte>` based on the specified protocol.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c1bd1-109">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="c1bd1-109">Reason for change</span></span>

<span data-ttu-id="c1bd1-110">Der _Handshakeantwort_ wurden zusätzliche Felder hinzugefügt, die nicht konstant sind und je nach ausgewähltem Protokoll abweichen.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-110">Additional fields were added to the handshake _response_ that are non-constant and change depending on the selected protocol.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c1bd1-111">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="c1bd1-111">Recommended action</span></span>

<span data-ttu-id="c1bd1-112">Keine</span><span class="sxs-lookup"><span data-stu-id="c1bd1-112">None.</span></span> <span data-ttu-id="c1bd1-113">Dieser Typ ist nicht für die Verwendung in Benutzercode vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-113">This type isn't designed for use from user code.</span></span> <span data-ttu-id="c1bd1-114">Er ist `public`, damit er von SignalR-Server und -Client gemeinsam verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-114">It's `public`, so it can be shared between the SignalR server and client.</span></span> <span data-ttu-id="c1bd1-115">Er kann auch von SignalR-Kundenclients verwendet werden, die in .NET geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-115">It may also be used by customer SignalR clients written in .NET.</span></span> <span data-ttu-id="c1bd1-116">**Benutzer** von SignalR sollten von dieser Änderung nicht betroffen sein.</span><span class="sxs-lookup"><span data-stu-id="c1bd1-116">**Users** of SignalR shouldn't be affected by this change.</span></span>

#### <a name="category"></a><span data-ttu-id="c1bd1-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="c1bd1-117">Category</span></span>

<span data-ttu-id="c1bd1-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c1bd1-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c1bd1-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="c1bd1-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData?displayProperty=nameWithType>

<!--

#### Affected APIs

`F:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData`

-->
