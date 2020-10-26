---
ms.openlocfilehash: 8de70b0c445aa48fc4c3249ccfc8c095890fb14c
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050518"
---
### <a name="socketlocalendpoint-is-updated-after-calling-sendtoasync"></a><span data-ttu-id="0c363-101">Socket.LocalEndPoint wird nach dem Aufruf von SendToAsync aktualisiert</span><span class="sxs-lookup"><span data-stu-id="0c363-101">Socket.LocalEndPoint is updated after calling SendToAsync</span></span>

<span data-ttu-id="0c363-102"><xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> aktualisiert jetzt den Wert der <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>-Eigenschaft auf die lokale Adresse des Sockets.</span><span class="sxs-lookup"><span data-stu-id="0c363-102"><xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> now updates the value of the <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> property to the socket's local address.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0c363-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="0c363-103">Version introduced</span></span>

<span data-ttu-id="0c363-104">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="0c363-104">5.0 RC1</span></span>

#### <a name="change-description"></a><span data-ttu-id="0c363-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="0c363-105">Change description</span></span>

<span data-ttu-id="0c363-106">In früheren .NET-Versionen wird der Wert der <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>-Eigenschaft der Socketinstanz nicht durch <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> geändert.</span><span class="sxs-lookup"><span data-stu-id="0c363-106">In previous .NET versions, <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> does not alter the value of the <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> property on the socket instance.</span></span> <span data-ttu-id="0c363-107">Ab .NET 5.0 ist der Wert von <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> die lokale Adresse des implizit gebundenen Sockets, wenn <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="0c363-107">Starting in .NET 5.0, when <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> successfully completes, the value of <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> is the implicitly bound socket's local address.</span></span> <span data-ttu-id="0c363-108">Dieses neue Verhalten ist mit dem von <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> und <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)> konsistent.</span><span class="sxs-lookup"><span data-stu-id="0c363-108">This new behavior is consistent with the behavior of <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> and <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="0c363-109">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="0c363-109">Reason for change</span></span>

<span data-ttu-id="0c363-110">Diese Änderung [korrigiert einen Fehler](https://github.com/dotnet/runtime/issues/915) und bewirkt, dass das Verhalten von `SendTo`-Varianten konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="0c363-110">This change [fixes a bug](https://github.com/dotnet/runtime/issues/915) and makes the behavior consistent across `SendTo` variants.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0c363-111">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="0c363-111">Recommended action</span></span>

<span data-ttu-id="0c363-112">Ändern Sie jeglichen Code, der annimmt, dass <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> den Wert von <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> nicht ändert.</span><span class="sxs-lookup"><span data-stu-id="0c363-112">Alter any code that assumes that <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> won't alter the value of <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="0c363-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="0c363-113">Category</span></span>

<span data-ttu-id="0c363-114">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="0c363-114">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0c363-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="0c363-115">Affected APIs</span></span>

- <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)`

-->
