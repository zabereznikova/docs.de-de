---
title: Hinzufügen von Online- und Offlinestatus
ms.date: 03/30/2017
ms.assetid: 05e5f51d-81b6-4c17-b364-9dda447a5fce
ms.openlocfilehash: da170bbc22d04dcbf5f7cd4ac084a004bb4b026e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597682"
---
# <a name="adding-online-and-offline-status"></a>Hinzufügen von Online- und Offlinestatus
In vielen Fällen ist es wichtig, dass eine Anwendung bestimmte Details über den Status einer Peerkanalverbindung überwachen kann. Diese Informationen erhalten Sie durch Aufrufen der `GetProperty`-Methode bei der Implementierung der <xref:System.ServiceModel.IOnlineStatus>-Schnittstelle. Ein Objekt mit einer Implementierung dieser Schnittstelle kann den Verbindungsstatus überwachen oder für Ereignishandler wie `OnOnline` und `OnOffline` registrieren und sofort reagieren, sobald Änderungen des Onlinestatus auftreten.  
  
 In der Peerkanalinfrastruktur wird ein Client als online angesehen, wenn er mit mindestens einem anderen Peer verbunden ist. Andernfalls wird er als offline betrachtet. Dies kann sowohl beim Debuggen von Entwicklungsanwendungen als auch beim Anzeigen ausführlicher Informationen für den Endbenutzer besonders nützlich sein.  
  
> [!NOTE]
> Ein Onlineereignishandler sollte vor dem Senden von Nachrichten zuerst sicherstellen, dass der Knoten offen ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [Erstellen einer Peerkanalanwendung](building-a-peer-channel-application.md)
