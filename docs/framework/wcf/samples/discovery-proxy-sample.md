---
title: Suchproxybeispiel
ms.date: 03/30/2017
ms.assetid: 1dfa02df-15b1-4e97-9c8e-f5f2772711b0
ms.openlocfilehash: e9cbfcb717f502a849d4d508d13df6c00b95db58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="discovery-proxy-sample"></a>Suchproxybeispiel
In diesem Beispiel wird gezeigt, wie eine Implementierung eines Suchproxys erstellt wird, um Informationen zu vorhandenen Diensten zu speichern, und wie Clients Informationen von diesem Proxy abfragen können. Dieses Beispiel umfasst drei Projekte:  
  
-   **Dienst**: eine einfache Windows Communication Foundation (WCF)-rechnerdienst, der sich der beim suchproxy registriert.  
  
-   **Suchproxy**: die Implementierung eines suchproxydiensts.  
  
-   **Client**: ein WCF-Clientanwendung, die den suchproxy zum Suchen nach Diensten aufruft.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Implementierung eines Suchproxys  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryProxy`  
  
## <a name="discoveryproxy"></a>DiscoveryProxy  
 Im Beispiel wird in der `Main`-Methode der Datei Program.cs gezeigt, wie ein Dienst des Typs <xref:System.ServiceModel.Discovery.DiscoveryProxy> gehostet wird. Zwei Endpunkte, einer vom Typ <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> und einer vom Typ <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>, werden verfügbar gemacht. Beide Endpunkte verwenden TCP als Transport. Der <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> hört den durch den `probeEndpointAddress`-Parameter festgelegten URI ab. An dieser Stelle können Clients Überprüfungsnachrichten senden, um Daten vom Proxy abzufragen. Der <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> hört den durch den `announcementEndpointAddress`-Parameter festgelegten URI ab. An dieser Stelle lauscht der Proxy auf Ankündigungen. Wenn eine Onlineankündigung empfangen wird, fügt der Proxy den Dienst zum Cache hinzu, und wenn eine Offlineankündigung empfangen wird, entfernt er den Dienst aus seinem Cache.  
  
 Die Datei DiscoveryProxy.cs enthält die <xref:System.ServiceModel.Discovery.DiscoveryProxy>-Implementierung. Der Proxy muss von der <xref:System.Object>-Klasse erben und erfordert eine <xref:System.Runtime.Remoting.Messaging.AsyncResult>-Implementierung. Bei der Instanziierung erstellt der Proxy ein neues <xref:System.Collections.Generic.Dictionary%602>, mit dem er bekannte Elemente speichert.  
  
 Die Datei ist in zwei Bereiche, Proxy Cache Methods und Discovery Proxy Implementation, unterteilt. Die im Bereich Proxy Cache Methods enthaltenen Methoden werden verwendet, um das <xref:System.Collections.Generic.Dictionary%602> zu aktualisieren, <xref:System.Collections.Generic.Dictionary%602>-Abfragen durchzuführen und die Daten für die Benutzer zu drucken. Im Bereich Discovery Proxy Implementation sind die überschriebenen Methoden enthalten, die für die Ankündigungs- und Untersuchungsfunktionen erforderlich sind. Sie definieren die Aktionen, die von einem Proxy durchgeführt werden, nachdem eine Onlineankündigung, Offlineankündigung oder Überprüfungsnachricht empfangen wurde.  
  
## <a name="service"></a>Dienst  
 In der Datei Program.cs im Dienstprojekt wird der gleiche URI für den Ankündigungsendpunkt als Suchproxy verwendet. Das liegt daran, dass der Dienst den Endpunkt zum Senden der Ankündigungen und der Proxy zum Empfangen der Ankündigungen verwendet. Der Dienst verwendet das <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> und fügt einen Ankündigungsendpunkt hinzu.  
  
## <a name="client"></a>Client  
 Das Clientprojekt verwendet den gleichen URI für den Überprüfungsendpunkt wie der Proxy. Das liegt daran, dass die Überprüfungen in diesem Szenario auch per Unicast ausdrücklich an den Endpunkt im Proxy gesendet werden. Der Client stellt eine Verbindung mit dieser bekannten Adresse her und führt dann eine Abfrage nach dem Dienst durch. Sobald der Dienst gefunden wurde, wird eine Verbindung zu dem Dienst hergestellt.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Laden Sie die Projektmappe in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], und erstellen Sie das Projekt.  
  
2.  Führen Sie zunächst die unter [Projektmappenbasisverzeichnis]\DiscoveryProxy\bin\debug generierte Suchproxyanwendung aus. Der Suchproxy muss zuerst ausgeführt werden, da TCP-Ankündigungsendpunkte für den Dienst bereit sein müssen, damit die Ankündigungen gesendet werden können.  
  
3.  Führen Sie als Nächstes die unter [Projektmappenbasisverzeichnis] \Service\bin\debug generierte Dienstanwendung aus. Beim Start sendet der Dienst eine Ankündigung an den Ankündigungsendpunkt des Suchproxys und wird im Cache des Proxys registriert.  
  
4.  Führen Sie anschließend die unter [Projektmappenbasisverzeichnis] \Client\bin\debug generierte Clientanwendung aus. Der Client führt die Proxyabfrage durch, ruft die Dienstadresse ab und stellt dann eine Verbindung mit dem Dienst her.  
  
5.  Beenden Sie schließlich den Client, den Dienst und dann den Proxy. Der Proxy muss ausgeführt werden, damit er die Offlineankündigung des Diensts empfangen kann.  
  
## <a name="see-also"></a>Siehe auch
