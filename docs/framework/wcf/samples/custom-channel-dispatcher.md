---
title: "Benutzerdefinierter Kanalverteiler | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 813acf03-9661-4d57-a3c7-eeab497321c6
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Benutzerdefinierter Kanalverteiler
In diesem Beispiel wird gezeigt, wie der Kanalstapel auf benutzerdefinierte Weise erstellt wird, indem <xref:System.ServiceModel.ServiceHostBase> direkt implementiert wird, und wie ein benutzerdefinierter Kanalverteiler in einer Webhostumgebung erstellt wird.Der Kanalverteiler interagiert mit <xref:System.ServiceModel.Channels.IChannelListener>, um Kanäle zu akzeptieren und ruft Nachrichten aus dem Kanalstapel ab.Dieses Beispiel enthält auch ein einfaches Beispiel zur Veranschaulichung, wie ein Kanalstapel in einer Webhostumgebung mithilfe der <xref:System.ServiceModel.Activation.VirtualPathExtension> erstellt wird.  
  
## Benutzerdefinierte ServiceHostBase  
 In diesem Beispiel wird der Basistyp <xref:System.ServiceModel.ServiceHostBase> statt dem <xref:System.ServiceModel.ServiceHost> implementiert, um zu zeigen, wie die [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Stapelimplementierung durch eine benutzerdefinierte Nachrichtenbehandlungsebene über dem Kanalstapel ersetzt wird.Sie überschreiben die virtuelle Methode <xref:System.ServiceModel.ServiceHostBase.InitializeRuntime%2A>, um Kanallistener und den Kanalverteiler zu erstellen.  
  
 Um einen im Internet gehosteten Dienst zu implementieren rufen Sie die Diensterweiterung <xref:System.ServiceModel.Activation.VirtualPathExtension> aus der <xref:System.ServiceModel.ServiceHostBase.Extensions%2A>\-Auflistung ab, und fügen Sie sie zur <xref:System.ServiceModel.Channels.BindingParameterCollection> hinzu, damit die Transportebene den Kanallistener basierend auf den Hostumgebungseinstellungen, d. h. den Einstellungen für die Internetinformationsdienste \(IIS\) und den Windows\-Prozessaktivierungsdienst \(WAS\), konfigurieren kann.  
  
## Benutzerdefinierter Kanalverteiler  
 Der benutzerdefinierte Kanalverteiler erweitert den Typ <xref:System.ServiceModel.Dispatcher.ChannelDispatcherBase>.Dieser Typ implementiert die Programmierlogik auf Kanalebene.In diesem Beispiel wird nur <xref:System.ServiceModel.Channels.IReplyChannel> für das Anforderung\-Antwort\-Nachrichtenaustauschmuster unterstützt, aber der benutzerdefinierte Kanalverteiler kann schnell auf andere Kanaltypen erweitert werden.  
  
 Der Verteiler öffnet zuerst den Kanallistener und akzeptiert dann den Singletonantwortkanal.Er beginnt mit dem Kanal mit dem Senden von Nachrichten \(Anforderungen\) in einer Endlosschleife.Für jede Anforderung erstellt er eine Antwortnachricht und sendet sie an den Client zurück.  
  
## Erstellen einer Antwortnachricht  
 Die Nachrichtenverarbeitung wird im Typ `MyServiceManager` implementiert.In der `HandleRequest`\-Methode wird der `Action`\-Header der Nachricht zuerst daraufhin überprüft, ob die Anforderung unterstützt wird.Eine vordefinierte SOAP\-Aktion "http:\/\/tempuri.org\/HelloWorld\/Hello" wird definiert, um die Nachrichtenfilterung bereitzustellen.Dies ähnelt dem Dienstvertragskonzept in der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Implementierung von <xref:System.ServiceModel.ServiceHost>.  
  
 Im Beispiel werden für den richtigen SOAP\-Aktionsfall die angeforderten Nachrichtendaten abgerufen, und es wird eine entsprechende Antwort auf die Anforderung generiert, ähnlich dem <xref:System.ServiceModel.ServiceHost>\-Fall.  
  
 Sie haben das HTTP\-GET\-Verb in diesem Fall besonders behandelt und eine benutzerdefinierte HTML\-Nachricht zurückgegeben, damit Sie den Dienst in einem Browser durchsuchen können, um sicherzustellen, dass er ordnungsgemäß kompiliert wurde.Wenn die SOAP\-Aktion nicht richtig ist, senden Sie eine Fehlermeldung zurück, die angibt, dass die Anforderung nicht unterstützt wird.  
  
 Der Client dieses Beispiels ist ein normaler [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Client, der nichts vom Dienst übernimmt.Der Dienst wurde also speziell entworfen, um den Ergebnissen einer normalen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.ServiceModel.ServiceHost>\-Implementierung zu entsprechen.Infolgedessen ist auf dem Client nur ein Dienstvertrag erforderlich.  
  
## Verwenden des Beispiels  
 Wenn Sie die Clientanwendung ausführen, wird die folgende Ausgabe direkt erzeugt.  
  
```Output  
Client kommuniziert mit einem Anforderung-Antwort-WCF-Dienst.   
Geben Sie die gewünschte Nachricht für den Server ein: Howdy  
Serverantwort: You said: Howdy.Nachrichten-ID: 1  
Serverantwort: You said: Howdy.Nachrichten-ID: 2  
Serverantwort: You said: Howdy.Nachrichten-ID: 3  
Serverantwort: You said: Howdy.Nachrichten-ID: 4  
Serverantwort: You said: Howdy.Nachrichten-ID: 5  
  
```  
  
 Sie können den Dienst auch in einem Browser durchsuchen, damit eine HTTP\-GET\-Nachricht auf dem Server verarbeitet wird.Auf diese Weise wird wohlgeformter HTML\-Text zurückgegeben.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\CustomChannelDispatcher`