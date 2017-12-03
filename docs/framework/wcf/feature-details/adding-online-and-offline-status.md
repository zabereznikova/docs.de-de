---
title: "Hinzufügen von Online- und Offlinestatus"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05e5f51d-81b6-4c17-b364-9dda447a5fce
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d5b6c858b5aa5918498ba8fccee41f7392ac32e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="adding-online-and-offline-status"></a>Hinzufügen von Online- und Offlinestatus
In vielen Fällen ist es wichtig, dass eine Anwendung bestimmte Details über den Status einer Peerkanalverbindung überwachen kann. Diese Informationen erhalten Sie durch Aufrufen der `GetProperty`-Methode bei der Implementierung der <xref:System.ServiceModel.IOnlineStatus>-Schnittstelle. Ein Objekt mit einer Implementierung dieser Schnittstelle kann den Verbindungsstatus überwachen oder für Ereignishandler wie `OnOnline` und `OnOffline` registrieren und sofort reagieren, sobald Änderungen des Onlinestatus auftreten.  
  
 In der Peerkanalinfrastruktur wird ein Client als online angesehen, wenn er mit mindestens einem anderen Peer verbunden ist. Andernfalls wird er als offline betrachtet. Dies kann sowohl beim Debuggen von Entwicklungsanwendungen als auch beim Anzeigen ausführlicher Informationen für den Endbenutzer besonders nützlich sein.  
  
> [!NOTE]
>  Ein Onlineereignishandler sollte vor dem Senden von Nachrichten zuerst sicherstellen, dass der Knoten offen ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen einer Peerkanalanwendung](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
