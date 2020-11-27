---
title: Entwickeln von Kanälen
ms.date: 03/30/2017
ms.assetid: 0513af9f-a0c2-457b-9a50-5b6bfee48513
ms.openlocfilehash: 11e7a78282a3c9f7cd221e2ef44bc43c625e447b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286798"
---
# <a name="developing-channels"></a>Entwickeln von Kanälen

Zum Entwickeln eines Protokolls oder Transport Kanals, der mit der Windows Communication Foundation (WCF)-Anwendungsebene verwendet werden kann, sind mehrere Schritte erforderlich. In diesem Thema werden diese Schritte beschrieben, und Sie werden auf bestimmte Themen verwiesen, in denen Sie weitere Informationen erhalten. Informationen zum channelmodell und den verschiedenen Typen, die in diesem Thema erwähnt werden, finden Sie unter [Übersicht über das Kanal Modell](channel-model-overview.md). Ein umfassendes Beispiel für einen Transport Kanal finden Sie unter [Transport: UDP](../samples/transport-udp.md).  
  
## <a name="the-channel-development-task-list"></a>Die Aufgabenliste für die Kanalentwicklung  

 Die Schritte, mit denen ein benutzerdefinierter Kanal wie folgt erstellt wird. Für alle Kanäle gilt Folgendes:  
  
1. Es muss entschieden werden, welche Nachrichtenaustauschmuster des Kanals (<xref:System.ServiceModel.Channels.IOutputChannel>, <xref:System.ServiceModel.Channels.IInputChannel>, <xref:System.ServiceModel.Channels.IDuplexChannel>, <xref:System.ServiceModel.Channels.IRequestChannel> oder <xref:System.ServiceModel.Channels.IReplyChannel>) von <xref:System.ServiceModel.Channels.IChannelFactory> und <xref:System.ServiceModel.Channels.IChannelListener> unterstützt werden und ob die sitzungsbasierten Varianten dieser Schnittstellen unterstützt werden. Weitere Informationen finden Sie unter [Auswählen eines Nachrichtenaustausch Musters](choosing-a-message-exchange-pattern.md).  
  
2. Es müssen eine Kanalfactory und ein Listener (<xref:System.ServiceModel.Channels.IChannelFactory> und <xref:System.ServiceModel.Channels.IChannelListener>) erstellt werden, die das Nachrichtenaustauschmuster unterstützen. Ausführliche Informationen zum Entwickeln von Factorys finden Sie unter [Client: Kanalfactorys und Kanäle](client-channel-factories-and-channels.md). Ausführliche Informationen zum Entwickeln von Listenern finden Sie unter [Service: Kanallistener und Kanäle](service-channel-listeners-and-channels.md).  
  
3. Es muss sichergestellt werden, dass alle netzwerkspezifischen Ausnahmen zu <xref:System.TimeoutException?displayProperty=nameWithType> oder der entsprechenden abgeleiteten Klasse von <xref:System.ServiceModel.CommunicationException> normalisiert werden. Weitere Informationen finden Sie unter [Behandeln von Ausnahmen und Fehlern](handling-exceptions-and-faults.md).  
  
4. Wenn Sie die Verwendung von der Anwendungsebene aktivieren möchten, fügen Sie ein <xref:System.ServiceModel.Channels.BindingElement> hinzu, über das der benutzerdefinierte Kanal einem Kanalstapel hinzugefügt wird. Weitere Informationen finden Sie unter [Erstellen eines BindingElement](creating-a-bindingelement.md).  
  
 Die folgenden zusätzlichen Schritte sind erforderlich, um eine umfassendere Unterstützung auf Anwendungsebene zu aktivieren:  
  
1. Fügen Sie einen Bindungselementerweiterungs-Abschnitt hinzu, um das neue Bindungselement für das Konfigurationssystem verfügbar zu machen. Weitere Informationen finden Sie [unter Unterstützung von Konfigurationen und Metadaten](configuration-and-metadata-support.md).  
  
2. Fügen Sie Metadatenerweiterungen hinzu, um anderen Endpunkten Funktionen mitzuteilen. Weitere Informationen finden Sie [unter Unterstützung von Konfigurationen und Metadaten](configuration-and-metadata-support.md).  
  
3. Fügen Sie eine Bindung hinzu, die einen Stapel mit Bindungselementen entsprechend einem genau definierten Profil vorkonfiguriert. Weitere Informationen finden Sie unter [Erstellen von User-Defined Bindungen](creating-user-defined-bindings.md).  
  
4. Fügen Sie einen Bindungsabschnitt und ein Bindungskonfigurationselement hinzu, um die Bindung für das Konfigurationssystem verfügbar zu machen. Weitere Informationen finden Sie [unter Unterstützung von Konfigurationen und Metadaten](configuration-and-metadata-support.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Erweitern von Bindungen](extending-bindings.md)
