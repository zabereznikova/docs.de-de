---
title: "Entwickeln von Kan&#228;len | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0513af9f-a0c2-457b-9a50-5b6bfee48513
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# Entwickeln von Kan&#228;len
Wenn Sie ein Protokoll oder einen Transportkanal erstellen möchten, der mit der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Anwendungsebene verwendet werden kann, müssen Sie mehrere Schritte befolgen.In diesem Thema werden diese Schritte beschrieben, und Sie werden auf bestimmte Themen verwiesen, in denen Sie weitere Informationen erhalten.Um das Kanalmodell und die verschiedenen Typen zu verstehen, die in diesem Thema erwähnt werden, lesen Sie [Übersicht über das Kanalmodell](../../../../docs/framework/wcf/extending/channel-model-overview.md).Ein vollständiges Beispiel eines Transportkanals finden Sie unter [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md).  
  
## Die Aufgabenliste für die Kanalentwicklung  
 Die Schritte, mit denen ein benutzerdefinierter Kanal wie folgt erstellt wird.Für alle Kanäle gilt Folgendes:  
  
1.  Es muss entschieden werden, welche Nachrichtenaustauschmuster des Kanals \(<xref:System.ServiceModel.Channels.IOutputChannel>, <xref:System.ServiceModel.Channels.IInputChannel>, <xref:System.ServiceModel.Channels.IDuplexChannel>, <xref:System.ServiceModel.Channels.IRequestChannel> oder <xref:System.ServiceModel.Channels.IReplyChannel>\) von <xref:System.ServiceModel.Channels.IChannelFactory> und <xref:System.ServiceModel.Channels.IChannelListener> unterstützt werden und ob die sitzungsbasierten Varianten dieser Schnittstellen unterstützt werden.Ausführliche Informationen finden Sie unter [Auswählen eines Nachrichtenaustauschmusters](../../../../docs/framework/wcf/extending/choosing-a-message-exchange-pattern.md).  
  
2.  Es müssen eine Kanalfactory und ein Listener \(<xref:System.ServiceModel.Channels.IChannelFactory> und <xref:System.ServiceModel.Channels.IChannelListener>\) erstellt werden, die das Nachrichtenaustauschmuster unterstützen.Ausführliche Informationen zum Entwickeln von Factorys finden Sie unter [Client: Kanalfactorys und Kanäle](../../../../docs/framework/wcf/extending/client-channel-factories-and-channels.md).Ausführliche Informationen zum Entwickeln von Listenern finden Sie unter [Dienst: Kanallistener und Kanäle](../../../../docs/framework/wcf/extending/service-channel-listeners-and-channels.md).  
  
3.  Es muss sichergestellt werden, dass alle netzwerkspezifischen Ausnahmen zu <xref:System.TimeoutException?displayProperty=fullName> oder der entsprechenden abgeleiteten Klasse von <xref:System.ServiceModel.CommunicationException> normalisiert werden.Ausführliche Informationen finden Sie unter [Behandeln von Ausnahmen und Fehlern](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md).  
  
4.  Wenn Sie die Verwendung von der Anwendungsebene aktivieren möchten, fügen Sie ein <xref:System.ServiceModel.Channels.BindingElement> hinzu, über das der benutzerdefinierte Kanal einem Kanalstapel hinzugefügt wird.Weitere Informationen finden Sie unter [Erstellen eines BindingElement](../../../../docs/framework/wcf/extending/creating-a-bindingelement.md).  
  
 Die folgenden zusätzlichen Schritte sind erforderlich, um eine umfassendere Unterstützung auf Anwendungsebene zu aktivieren:  
  
1.  Fügen Sie einen Bindungselementerweiterungs\-Abschnitt hinzu, um dem Konfigurationssystem das neue Bindungselement verfügbar zu machen.Weitere Informationen finden Sie unter [Konfiguration und Metadatenunterstützung](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).  
  
2.  Fügen Sie Metadatenerweiterungen hinzu, um anderen Endpunkten Funktionen mitzuteilen.Weitere Informationen finden Sie unter [Konfiguration und Metadatenunterstützung](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).  
  
3.  Fügen Sie eine Bindung hinzu, die einen Stapel mit Bindungselementen entsprechend einem genau definierten Profil vorkonfiguriert.Weitere Informationen finden Sie unter [Erstellen benutzerdefinierter Bindungen](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
4.  Fügen Sie einen Bindungabschnitt und ein Bindungskonfigurationselement hinzu, um dem Konfigurationssystem die Bindung verfügbar zu machen.Weitere Informationen finden Sie unter [Konfiguration und Metadatenunterstützung](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).  
  
## Siehe auch  
 [Erweitern von Bindungen](../../../../docs/framework/wcf/extending/extending-bindings.md)