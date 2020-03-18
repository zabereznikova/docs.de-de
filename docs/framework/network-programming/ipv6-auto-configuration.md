---
title: Automatische IPv6-Konfiguration
ms.date: 03/30/2017
ms.assetid: 581c1d21-1013-43a3-bf3e-2d9ead62b79c
ms.openlocfilehash: 95d9dce36c70b8f6c6b9f963c0842305a111d436
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047809"
---
# <a name="ipv6-auto-configuration"></a>Automatische IPv6-Konfiguration
Ein wichtiges Ziel von IPv6 ist die Unterstützung von Plug & Play für Knoten. Das bedeutet, dass es möglich sein soll, dass ein Knoten in ein IPv6-Netzwerk eingeführt und dann automatisch ohne Benutzereingriff konfiguriert wird.  
  
## <a name="type-of-auto-configuration"></a>Typen der automatischen Konfiguration  
 IPv6 unterstützt die folgenden Typen der automatischen Konfiguration:  
  
- **Stateful auto-configuration (Zustandsbehaftete automatische Konfiguration)** . Diese Art der Konfiguration erfordert ein gewisses Maß an Benutzereingriff, da ein Server mit einem Dynamic Host Configuration-Protokoll für IPv6 (DHCPv6) für die Installation und Verwaltung der Knoten benötigt wird. Der DHCPv6-Server führt eine Liste von Knoten, für die er Konfigurationsinformationen bereitstellt. Er verwaltet auch Statusinformationen, sodass der Server weiß, wie lange jede Adresse verwendet wird und wann diese für eine Neuzuweisung verfügbar ist.  
  
- **Stateless auto-configuration (Zustandslose automatische Konfiguration)** . Diese Art der Konfiguration ist für kleine Organisationen und Einzelpersonen geeignet. In diesem Fall bestimmt jeder Host seine Adressen aus den Inhalten der empfangenen Routerankündigungen. Wenn der IEEE EUI-64-Standard verwendet wird, um die Netzwerk-ID einer Adresse zu definieren, empfiehlt es sich, die Eindeutigkeit der Hostadresse auf dem Link anzunehmen.  
  
 Unabhängig davon, wie die Adresse bestimmt wird, muss der Knoten überprüfen, dass die potenzielle Adresse für den lokalen Link eindeutig ist. Dies erfolgt, indem eine Nachbaranfrage eine Nachricht an die potenzielle Adresse sendet. Wenn der Knoten eine Antwort empfängt, weiß er, dass die Adresse bereits verwendet wird und er eine andere Adresse bestimmen muss.  
  
## <a name="ipv6-mobility"></a>IPv6-Mobilität  
 Die Verbreitung von Mobilgeräten hat eine neue Anforderung eingeführt: Ein Gerät muss dazu in der Lage sein, seinen Standort beliebig im IPv6-Internet zu ändern und dennoch seine bestehenden Verbindungen beizubehalten. Zur Gewährleistung dieser Funktionalität wird einem mobilen Knoten eine Privatadresse zugewiesen, über die er immer erreicht werden kann. Wenn der mobile Knoten zuhause ist, verbindet er sich mit dem Privatlink und verwendet seine Privatadresse. Wenn der mobile Knoten nicht zuhause ist, überträgt ein eigener Agent, bei dem es sich üblicherweise um einen Router handelt, Nachrichten zwischen dem mobilen Knoten und den Knoten, mit denen er kommuniziert.  
  
## <a name="see-also"></a>Weitere Informationen

- [Internetprotokoll Version 6](internet-protocol-version-6.md)
- [Sockets](sockets.md)
