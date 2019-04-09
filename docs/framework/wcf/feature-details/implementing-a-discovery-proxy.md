---
title: Implementieren eines Suchproxys
ms.date: 03/30/2017
ms.assetid: dda20e79-8df3-438e-a281-69d779d978ec
ms.openlocfilehash: 5d9296d8ba70d4c9e8d8339fa3a032d9c4c62826
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140998"
---
# <a name="implementing-a-discovery-proxy"></a>Implementieren eines Suchproxys
In diesem Thema werden die Schritte beschrieben, die zum Implementieren eines Suchproxys erforderlich sind. Ein Suchproxy ist ein eigenständiger Dienst, der ein Repository mit Diensten enthält. Clients können einen Suchproxy abfragen, um nach erkennbaren Diensten, die für den Proxy verfügbar sind. Die Art und Weise, wie ein Proxy mit Diensten aufgefüllt wird, hängt von der Implementierung ab. Ein Suchproxy kann z. B. eine Verbindung zu einem vorhandenen Dienstrepository herstellen und diese Informationen erkennbar machen, ein Administrator kann einem Proxy erkennbare Dienste mithilfe einer Verwaltungs-API hinzufügen, oder ein Suchproxy kann seinen internen Cache mithilfe der Ankündigungsfunktionalität aktualisieren.  
  
 Die WCF-Implementierung stellt Basisklassen bereit, mit denen problemlos ein Proxy erstellt werden kann. Sie können mit diesen APIs einen Suchproxy für das vorhandene Repository erstellen.  
  
 Der hier implementierte Suchproxy gleicht allen anderen WCF-Diensten. Sie können den Suchproxy auch erkennbar machen und die Clients nach seinen Endpunkten suchen lassen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Implementieren eines Suchproxys](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 Beschreibt, wie Sie einen Suchproxy implementieren.  
  
 [Vorgehensweise: Implementieren eines ermittelbaren Diensts, der beim Suchproxy registriert ist](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 Beschreibt, wie einen WCF-Dienst erkennbaren zu implementieren, der beim suchproxy registriert.  
  
 [Vorgehensweise: Implementieren einer Clientanwendung, die den Suchproxy zum Suchen nach einem Dienst verwendet](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)  
 Beschreibt, wie eine WCF-Clientanwendung implementieren, die den suchproxy, die zum Suchen nach einem Dienst verwendet.  
  
 [Vorgehensweise: Testen des Suchproxys](../../../../docs/framework/wcf/feature-details/how-to-test-the-discovery-proxy.md)  
 Beschreibt, wie Sie den Code testen, den Sie in den vorherigen drei Themen geschrieben haben.  
  
## <a name="see-also"></a>Siehe auch

- [WCF-Suche](../../../../docs/framework/wcf/feature-details/wcf-discovery.md)
- [Vorgehensweise: Programmgesteuertes Hinzufügen der Ermittelbarkeit zu einem WCF-Dienst und -Client](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)
