---
title: Hinzufügen von Online- und Offlinestatus
ms.date: 03/30/2017
ms.assetid: 05e5f51d-81b6-4c17-b364-9dda447a5fce
ms.openlocfilehash: 74b113d64003756982a6b5701d9601c3116a9046
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960647"
---
# <a name="adding-online-and-offline-status"></a><span data-ttu-id="d7a58-102">Hinzufügen von Online- und Offlinestatus</span><span class="sxs-lookup"><span data-stu-id="d7a58-102">Adding Online and Offline Status</span></span>
<span data-ttu-id="d7a58-103">In vielen Fällen ist es wichtig, dass eine Anwendung bestimmte Details über den Status einer Peerkanalverbindung überwachen kann.</span><span class="sxs-lookup"><span data-stu-id="d7a58-103">In many cases, it is important for an application to monitor specific details about the status of a Peer Channel connection.</span></span> <span data-ttu-id="d7a58-104">Diese Informationen erhalten Sie durch Aufrufen der `GetProperty`-Methode bei der Implementierung der <xref:System.ServiceModel.IOnlineStatus>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d7a58-104">You can obtain this information by calling the `GetProperty` method on an implementation of the <xref:System.ServiceModel.IOnlineStatus> interface.</span></span> <span data-ttu-id="d7a58-105">Ein Objekt mit einer Implementierung dieser Schnittstelle kann den Verbindungsstatus überwachen oder für Ereignishandler wie `OnOnline` und `OnOffline` registrieren und sofort reagieren, sobald Änderungen des Onlinestatus auftreten.</span><span class="sxs-lookup"><span data-stu-id="d7a58-105">An object with an implementation of this interface can monitor connection status or register for event handlers, such as `OnOnline` and `OnOffline`, and react immediately as changes to online status occur.</span></span>  
  
 <span data-ttu-id="d7a58-106">In der Peerkanalinfrastruktur wird ein Client als online angesehen, wenn er mit mindestens einem anderen Peer verbunden ist. Andernfalls wird er als offline betrachtet.</span><span class="sxs-lookup"><span data-stu-id="d7a58-106">In the Peer Channel infrastructure, a client is considered to be online if it is connected to at least one other peer and offline otherwise.</span></span> <span data-ttu-id="d7a58-107">Dies kann sowohl beim Debuggen von Entwicklungsanwendungen als auch beim Anzeigen ausführlicher Informationen für den Endbenutzer besonders nützlich sein.</span><span class="sxs-lookup"><span data-stu-id="d7a58-107">This can be particularly useful in both debugging a developing applications or displaying detailed information to the end user.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7a58-108">Ein Onlineereignishandler sollte vor dem Senden von Nachrichten zuerst sicherstellen, dass der Knoten offen ist.</span><span class="sxs-lookup"><span data-stu-id="d7a58-108">An online event handler should first ensure that the node is open before sending any messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7a58-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7a58-109">See also</span></span>

- [<span data-ttu-id="d7a58-110">Erstellen einer Peerkanalanwendung</span><span class="sxs-lookup"><span data-stu-id="d7a58-110">Building a Peer Channel Application</span></span>](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
