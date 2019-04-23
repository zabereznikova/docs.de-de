---
title: 'Vorgehensweise: Testen des Suchproxys'
ms.date: 03/30/2017
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
ms.openlocfilehash: 856b86241299585b80d58c6d37582463736a5935
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316393"
---
# <a name="how-to-test-the-discovery-proxy"></a>Vorgehensweise: Testen des Suchproxys
Dies ist das vierte von vier Themen, in denen beschrieben wird, wie Sie einen Suchproxy implementieren. Im vorherigen Thema [Vorgehensweise: Implementieren einer Clientanwendung, die den Suchproxy zum Suchen nach einem Dienst verwendet](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), Sie eine WCF-Clientanwendung, die den suchproxy zum Suchen nach einem Dienst verwendet, und ruft dann den Dienst implementiert. In diesem Thema wird beschrieben, wie Sie überprüfen, ob der Suchproxy, der Dienst und die Clientanwendung ordnungsgemäß funktionieren.  
  
### <a name="run-the-discovery-proxy"></a>Ausführen des Suchproxys  
  
1. Öffnen Sie eine Eingabeaufforderung als Administrator.  
  
2. Möglicherweise wird ein Dialogfeld angezeigt, die besagt: Windows-Firewall hat einige Funktionen dieses Programms blockiert. Wenn diese Meldung angezeigt wird, klicken Sie auf die **Unblock** Schaltfläche.  
  
3. Führen Sie innerhalb der Eingabeaufforderung den Suchproxy "DiscoveryProxy.exe" aus.  
  
4. Die Anwendung sollte den folgenden Text anzeigen: `Proxy started. Hit Enter to exit`.  
  
### <a name="run-the-discoverable-service"></a>Ausführen des erkennbaren Diensts  
  
1. Öffnen Sie eine Eingabeaufforderung als Administrator.  
  
2. Führen Sie innerhalb der Eingabeaufforderung den erkennbaren Dienst "Service.exe" aus.  
  
3. Die DiscoveryProxy.exe sollte den folgenden Text anzeigen: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .  
  
### <a name="run-the-client-application"></a>Ausführen der Clientanwendung  
  
1. Öffnen Sie eine Eingabeaufforderung.  
  
2. Führen Sie innerhalb der Eingabeaufforderung die Anwendung "client.exe" aus.  
  
3. Nach wenigen Sekunden zeigt die Clientanwendung den folgenden Text: Verbindung mit [Dienstendpunkt].  
  
4. Der service.exe zeigt dann den folgenden Text: Begrüßungsanforderung empfangen, werden ich Antworten.  
  
5. Die client.exe zeigt dann den folgenden Text: Hello Client!  
  
### <a name="shut-down-the-applications"></a>Herunterfahren der Anwendungen  
  
1. Fahren Sie die Clientanwendung herunter.  
  
2. Beenden Sie den Dienst. Der Suchproxy zeigt den folgenden Text an: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.  
  
3. Fahren Sie den Suchproxy herunter.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die WCF-Suche](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [Vorgehensweise: Implementieren eines Suchproxys](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)
- [Vorgehensweise: Implementieren eines ermittelbaren Diensts, das beim Suchproxy registriert.](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)
- [Vorgehensweise: Implementieren einer Clientanwendung, die den Suchproxy zum Suchen nach einem Dienst verwendet](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)
