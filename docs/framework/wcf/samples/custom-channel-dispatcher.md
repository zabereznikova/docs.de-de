---
title: Benutzerdefinierter Kanalverteiler
ms.date: 03/30/2017
ms.assetid: 813acf03-9661-4d57-a3c7-eeab497321c6
ms.openlocfilehash: 38d39cbba15c95a43444108d634d3c30524c70f4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241771"
---
# <a name="custom-channel-dispatcher"></a>Benutzerdefinierter Kanalverteiler

In diesem Beispiel wird gezeigt, wie der Kanalstapel auf benutzerdefinierte Weise erstellt wird, indem <xref:System.ServiceModel.ServiceHostBase> direkt implementiert wird, und wie ein benutzerdefinierter Kanalverteiler in einer Webhostumgebung erstellt wird. Der Kanalverteiler interagiert mit <xref:System.ServiceModel.Channels.IChannelListener>, um Kanäle zu akzeptieren und ruft Nachrichten aus dem Kanalstapel ab. Dieses Beispiel enthält auch ein einfaches Beispiel zur Veranschaulichung, wie ein Kanalstapel in einer Webhostumgebung mithilfe der <xref:System.ServiceModel.Activation.VirtualPathExtension> erstellt wird.  
  
## <a name="custom-servicehostbase"></a>Benutzerdefinierte ServiceHostBase  

 In diesem Beispiel wird der Basistyp <xref:System.ServiceModel.ServiceHostBase> anstelle von implementiert <xref:System.ServiceModel.ServiceHost> , um zu veranschaulichen, wie die Windows Communication Foundation (WCF)-Stapel Implementierung durch eine benutzerdefinierte Meldungs Behandlungs Ebene oberhalb des Kanal Stapels ersetzt wird. Sie überschreiben die virtuelle Methode <xref:System.ServiceModel.ServiceHostBase.InitializeRuntime%2A>, um Kanallistener und den Kanalverteiler zu erstellen.  
  
 Um einen im Internet gehosteten Dienst zu implementieren rufen Sie die Diensterweiterung <xref:System.ServiceModel.Activation.VirtualPathExtension> aus der <xref:System.ServiceModel.ServiceHostBase.Extensions%2A>-Auflistung ab, und fügen Sie sie zur <xref:System.ServiceModel.Channels.BindingParameterCollection> hinzu, damit die Transportebene den Kanallistener basierend auf den Hostumgebungseinstellungen, d. h. den Einstellungen für die Internetinformationsdienste (IIS) und den Windows-Prozessaktivierungsdienst (WAS), konfigurieren kann.  
  
## <a name="custom-channel-dispatcher"></a>Benutzerdefinierter Kanalverteiler  

 Der benutzerdefinierte Kanalverteiler erweitert den Typ <xref:System.ServiceModel.Dispatcher.ChannelDispatcherBase>. Dieser Typ implementiert die Programmierlogik auf Kanalebene. In diesem Beispiel wird nur <xref:System.ServiceModel.Channels.IReplyChannel> für das Anforderung-Antwort-Nachrichtenaustauschmuster unterstützt, aber der benutzerdefinierte Kanalverteiler kann schnell auf andere Kanaltypen erweitert werden.  
  
 Der Verteiler öffnet zuerst den Kanallistener und akzeptiert dann den Singletonantwortkanal. Er beginnt mit dem Kanal mit dem Senden von Nachrichten (Anforderungen) in einer Endlosschleife. Für jede Anforderung erstellt er eine Antwortnachricht und sendet sie an den Client zurück.  
  
## <a name="creating-a-response-message"></a>Erstellen einer Antwortnachricht  

 Die Nachrichtenverarbeitung wird im Typ `MyServiceManager` implementiert. In der `HandleRequest`-Methode wird der `Action`-Header der Nachricht zuerst daraufhin überprüft, ob die Anforderung unterstützt wird. Eine vordefinierte SOAP-Aktion "" http://tempuri.org/HelloWorld/Hello ist für die Nachrichtenfilterung definiert. Dies ähnelt dem Dienstvertrags Konzept in der WCF-Implementierung von <xref:System.ServiceModel.ServiceHost> .  
  
 Im Beispiel werden für den richtigen SOAP-Aktionsfall die angeforderten Nachrichtendaten abgerufen, und es wird eine entsprechende Antwort auf die Anforderung generiert, ähnlich dem <xref:System.ServiceModel.ServiceHost>-Fall.  
  
 Sie haben das HTTP-GET-Verb in diesem Fall besonders behandelt und eine benutzerdefinierte HTML-Nachricht zurückgegeben, damit Sie den Dienst in einem Browser durchsuchen können, um sicherzustellen, dass er ordnungsgemäß kompiliert wurde. Wenn die SOAP-Aktion nicht richtig ist, senden Sie eine Fehlermeldung zurück, die angibt, dass die Anforderung nicht unterstützt wird.  
  
 Bei dem Client dieses Beispiels handelt es sich um einen normalen WCF-Client, der nicht von dem Dienst ausgeht. Daher ist der Dienst speziell so konzipiert, dass er dem entspricht, was Sie von einer normalen WCF- <xref:System.ServiceModel.ServiceHost> Implementierung erhalten. Infolgedessen ist auf dem Client nur ein Dienstvertrag erforderlich.  
  
## <a name="using-the-sample"></a>Verwenden des Beispiels  

 Wenn Sie die Clientanwendung ausführen, wird die folgende Ausgabe direkt erzeugt.  
  
```output  
Client is talking to a request/reply WCF service.
Type what you want to say to the server: Howdy  
Server replied: You said: Howdy. Message id: 1  
Server replied: You said: Howdy. Message id: 2  
Server replied: You said: Howdy. Message id: 3  
Server replied: You said: Howdy. Message id: 4  
Server replied: You said: Howdy. Message id: 5  
```  
  
 Sie können den Dienst auch in einem Browser durchsuchen, damit eine HTTP-GET-Nachricht auf dem Server verarbeitet wird. Auf diese Weise wird wohlgeformter HTML-Text zurückgegeben.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\CustomChannelDispatcher`
