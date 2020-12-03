---
title: 'Breaking Change: Socket.LocalEndPoint wird nach dem Aufruf von SendToAsync aktualisiert'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den SendToAsync jetzt den Wert der lokalen Endpunkteigenschaft auf die lokale Adresse des Sockets aktualisiert.
ms.date: 10/18/2020
ms.openlocfilehash: 53d7da350eac6e65832012331044427fd90fe796
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759390"
---
# <a name="socketlocalendpoint-is-updated-after-calling-sendtoasync"></a><span data-ttu-id="d9ee7-103">Socket.LocalEndPoint wird nach dem Aufruf von SendToAsync aktualisiert</span><span class="sxs-lookup"><span data-stu-id="d9ee7-103">Socket.LocalEndPoint is updated after calling SendToAsync</span></span>

<span data-ttu-id="d9ee7-104"><xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> aktualisiert jetzt den Wert der <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>-Eigenschaft auf die lokale Adresse des Sockets.</span><span class="sxs-lookup"><span data-stu-id="d9ee7-104"><xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> now updates the value of the <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> property to the socket's local address.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="d9ee7-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d9ee7-105">Version introduced</span></span>

<span data-ttu-id="d9ee7-106">5.0</span><span class="sxs-lookup"><span data-stu-id="d9ee7-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="d9ee7-107">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="d9ee7-107">Change description</span></span>

<span data-ttu-id="d9ee7-108">In früheren .NET-Versionen wird der Wert der <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>-Eigenschaft der Socketinstanz nicht durch <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> geändert.</span><span class="sxs-lookup"><span data-stu-id="d9ee7-108">In previous .NET versions, <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> does not alter the value of the <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> property on the socket instance.</span></span> <span data-ttu-id="d9ee7-109">Ab .NET 5.0 ist der Wert von <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> die lokale Adresse des implizit gebundenen Sockets, wenn <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="d9ee7-109">Starting in .NET 5.0, when <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> successfully completes, the value of <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> is the implicitly bound socket's local address.</span></span> <span data-ttu-id="d9ee7-110">Dieses neue Verhalten ist mit dem von <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> und <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)> konsistent.</span><span class="sxs-lookup"><span data-stu-id="d9ee7-110">This new behavior is consistent with the behavior of <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> and <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)>.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="d9ee7-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="d9ee7-111">Reason for change</span></span>

<span data-ttu-id="d9ee7-112">Diese Änderung [korrigiert einen Fehler](https://github.com/dotnet/runtime/issues/915) und bewirkt, dass das Verhalten von `SendTo`-Varianten konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="d9ee7-112">This change [fixes a bug](https://github.com/dotnet/runtime/issues/915) and makes the behavior consistent across `SendTo` variants.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d9ee7-113">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="d9ee7-113">Recommended action</span></span>

<span data-ttu-id="d9ee7-114">Ändern Sie jeglichen Code, der annimmt, dass <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> den Wert von <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> nicht ändert.</span><span class="sxs-lookup"><span data-stu-id="d9ee7-114">Alter any code that assumes that <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> won't alter the value of <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="d9ee7-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="d9ee7-115">Affected APIs</span></span>

- <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)`

### Category

Networking

-->
