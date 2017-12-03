---
title: 'Vorgehensweise: Testen des Suchproxys'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 55a7fe72b34fc8c099d921e7e295c184817825a3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-test-the-discovery-proxy"></a>Vorgehensweise: Testen des Suchproxys
Dies ist das vierte von vier Themen, in denen beschrieben wird, wie Sie einen Suchproxy implementieren. Im vorherigen Thema [wie: Implementieren einer Clientanwendung, die den Suchproxy zum Suchen nach einem Dienst verwendet](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), Sie implementiert eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Clientanwendung, die den suchproxy zum Suchen nach einem Dienst verwendet und ruft dann die -Dienst. In diesem Thema wird beschrieben, wie Sie überprüfen, ob der Suchproxy, der Dienst und die Clientanwendung ordnungsgemäß funktionieren.  
  
### <a name="run-the-discovery-proxy"></a>Ausführen des Suchproxys  
  
1.  Öffnen Sie eine Eingabeaufforderung als Administrator.  
  
2.  Ggf. wird ein Dialogfeld mit folgendem Hinweis angezeigt: Die Windows-Firewall hat einige Funktionen dieses Programms geblockt. Wenn Sie diese Meldung angezeigt wird, klicken Sie auf die **zum Aufheben der Sperre** Schaltfläche.  
  
3.  Führen Sie innerhalb der Eingabeaufforderung den Suchproxy "DiscoveryProxy.exe" aus.  
  
4.  Die Anwendung sollte den folgenden Text anzeigen: `Proxy started. Hit Enter to exit`.  
  
### <a name="run-the-discoverable-service"></a>Ausführen des erkennbaren Diensts  
  
1.  Öffnen Sie eine Eingabeaufforderung als Administrator.  
  
2.  Führen Sie innerhalb der Eingabeaufforderung den erkennbaren Dienst "Service.exe" aus.  
  
3.  Die DiscoveryProxy.exe sollte den folgenden Text anzeigen: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .  
  
### <a name="run-the-client-application"></a>Ausführen der Clientanwendung  
  
1.  Öffnen Sie eine Eingabeaufforderung.  
  
2.  Führen Sie innerhalb der Eingabeaufforderung die Anwendung "client.exe" aus.  
  
3.  Nach einigen Sekunden zeigt die Clientanwendung den folgenden Text an: Verbindung mit [Dienstendpunkt] wird hergestellt.  
  
4.  "service.exe" sollte dann den folgenden Text anzeigen: Begrüßungsanforderung empfangen, Antwort folgt.  
  
5.  "client.exe" zeigt dann den folgenden Text an: Hello Client!  
  
### <a name="shut-down-the-applications"></a>Herunterfahren der Anwendungen  
  
1.  Fahren Sie die Clientanwendung herunter.  
  
2.  Beenden Sie den Dienst. Der Suchproxy zeigt den folgenden Text an: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.  
  
3.  Fahren Sie den Suchproxy herunter.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über den WCF-Ermittlung](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [Vorgehensweise: Implementieren eines Suchproxys](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 [Vorgehensweise: Implementieren eines ermittelbaren Diensts, der beim Suchproxy registriert](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 [Vorgehensweise: Implementieren einer Clientanwendung, die den Suchproxy zum Suchen nach einem Dienst verwendet](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)
