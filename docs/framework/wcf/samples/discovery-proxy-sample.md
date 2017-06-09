---
title: "Suchproxy-Beispiel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1dfa02df-15b1-4e97-9c8e-f5f2772711b0
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Suchproxy-Beispiel
In diesem Beispiel wird gezeigt, wie eine Implementierung eines Suchproxys erstellt wird, um Informationen zu vorhandenen Diensten zu speichern, und wie Clients Informationen von diesem Proxy abfragen können.Dieses Beispiel umfasst drei Projekte:  
  
-   **Dienst**: Ein einfacher [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Rechnerdienst, der sich beim Suchproxy registriert.  
  
-   **Suchproxy**: Die Implementierung eines Suchproxydiensts.  
  
-   **Client**: Eine WCF\-Clientanwendung, die den Suchproxy aufruft, um nach Diensten zu suchen.  
  
## Veranschaulicht  
 Implementierung eines Suchproxys  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryProxy`  
  
## DiscoveryProxy  
 Im Beispiel wird in der `Main`\-Methode der Datei Program.cs gezeigt, wie ein Dienst des Typs <xref:System.ServiceModel.Discovery.DiscoveryProxy> gehostet wird.Zwei Endpunkte, einer vom Typ <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> und einer vom Typ <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>, werden verfügbar gemacht.Beide Endpunkte verwenden TCP als Transport.Der <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> hört den durch den `probeEndpointAddress`\-Parameter festgelegten URI ab. An dieser Stelle können Clients Überprüfungsnachrichten senden, um Daten vom Proxy abzufragen.Der <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> hört den durch den `announcementEndpointAddress`\-Parameter festgelegten URI ab.An dieser Stelle lauscht der Proxy auf Ankündigungen.Wenn eine Onlineankündigung empfangen wird, fügt der Proxy den Dienst zum Cache hinzu, und wenn eine Offlineankündigung empfangen wird, entfernt er den Dienst aus seinem Cache.  
  
 Die Datei DiscoveryProxy.cs enthält die <xref:System.ServiceModel.Discovery.DiscoveryProxy>\-Implementierung.Der Proxy muss von der <xref:System.ServiceModel.Discovery.DiscoveryProxyBase>\-Klasse erben und erfordert eine <xref:System.Runtime.Remoting.Messaging.AsyncResult>\-Implementierung.Bei der Instanziierung erstellt der Proxy ein neues <xref:Systems.Collections.Generic.Dictionary%601>, mit dem er bekannte Elemente speichert.  
  
 Die Datei ist in zwei Bereiche, Proxy Cache Methods und Discovery Proxy Implementation, unterteilt.Die im Bereich Proxy Cache Methods enthaltenen Methoden werden verwendet, um das <xref:Systems.Collections.Generic.Dictionary%601> zu aktualisieren, <xref:Systems.Collections.Generic.Dictionary%601>\-Abfragen durchzuführen und die Daten für die Benutzer zu drucken.Im Bereich Discovery Proxy Implementation sind die überschriebenen Methoden enthalten, die für die Ankündigungs\- und Untersuchungsfunktionen erforderlich sind.Sie definieren die Aktionen, die von einem Proxy durchgeführt werden, nachdem eine Onlineankündigung, Offlineankündigung oder Überprüfungsnachricht empfangen wurde.  
  
## Dienst  
 In der Datei Program.cs im Dienstprojekt wird der gleiche URI für den Ankündigungsendpunkt als Suchproxy verwendet.Das liegt daran, dass der Dienst den Endpunkt zum Senden der Ankündigungen und der Proxy zum Empfangen der Ankündigungen verwendet.Der Dienst verwendet das <xref:System.ServiceModel.Discovery.DiscoveryBehavior> und fügt einen Ankündigungsendpunkt hinzu.  
  
## Client  
 Das Clientprojekt verwendet den gleichen URI für den Überprüfungsendpunkt wie der Proxy.Das liegt daran, dass die Überprüfungen in diesem Szenario auch per Unicast ausdrücklich an den Endpunkt im Proxy gesendet werden.Der Client stellt eine Verbindung mit dieser bekannten Adresse her und führt dann eine Abfrage nach dem Dienst durch.Sobald der Dienst gefunden wurde, wird eine Verbindung zu dem Dienst hergestellt.  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Laden Sie die Projektmappe in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], und erstellen Sie das Projekt.  
  
2.  Führen Sie zunächst die unter \[Projektmappenbasisverzeichnis\]\\DiscoveryProxy\\bin\\debug generierte Suchproxyanwendung aus.Der Suchproxy muss zuerst ausgeführt werden, da TCP\-Ankündigungsendpunkte für den Dienst bereit sein müssen, damit die Ankündigungen gesendet werden können.  
  
3.  Führen Sie als Nächstes die unter \[Projektmappenbasisverzeichnis\] \\Service\\bin\\debug generierte Dienstanwendung aus.Beim Start sendet der Dienst eine Ankündigung an den Ankündigungsendpunkt des Suchproxys und wird im Cache des Proxys registriert.  
  
4.  Führen Sie anschließend die unter \[Projektmappenbasisverzeichnis\] \\Client\\bin\\debug generierte Clientanwendung aus.Der Client führt die Proxyabfrage durch, ruft die Dienstadresse ab und stellt dann eine Verbindung mit dem Dienst her.  
  
5.  Beenden Sie schließlich den Client, den Dienst und dann den Proxy.Der Proxy muss ausgeführt werden, damit er die Offlineankündigung des Diensts empfangen kann.  
  
## Siehe auch