---
title: Entwickeln von Kanälen
ms.date: 03/30/2017
ms.assetid: 0513af9f-a0c2-457b-9a50-5b6bfee48513
ms.openlocfilehash: def60ec0cce8da71e7e2d98ff456420949360aed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="developing-channels"></a>Entwickeln von Kanälen
Um ein Protokoll oder einen Transportkanal Kanal zu entwickeln, der mit der Windows Communication Foundation (WCF) verwendet werden können sind Anwendungsebene mehrere Schritte erforderlich. In diesem Thema werden diese Schritte beschrieben, und Sie werden auf bestimmte Themen verwiesen, in denen Sie weitere Informationen erhalten. Um zu verstehen, Kanal-Modells und die verschiedenen Typen, die in diesem Thema erwähnt wurden, finden Sie unter [Übersicht über das Kanalmodell](../../../../docs/framework/wcf/extending/channel-model-overview.md). Eine vollständige Transport-Kanal-Beispiel finden Sie unter [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md).  
  
## <a name="the-channel-development-task-list"></a>Die Aufgabenliste für die Kanalentwicklung  
 Die Schritte, mit denen ein benutzerdefinierter Kanal wie folgt erstellt wird. Für alle Kanäle gilt Folgendes:  
  
1.  Es muss entschieden werden, welche Nachrichtenaustauschmuster des Kanals (<xref:System.ServiceModel.Channels.IOutputChannel>, <xref:System.ServiceModel.Channels.IInputChannel>, <xref:System.ServiceModel.Channels.IDuplexChannel>, <xref:System.ServiceModel.Channels.IRequestChannel> oder <xref:System.ServiceModel.Channels.IReplyChannel>) von <xref:System.ServiceModel.Channels.IChannelFactory> und <xref:System.ServiceModel.Channels.IChannelListener> unterstützt werden und ob die sitzungsbasierten Varianten dieser Schnittstellen unterstützt werden. Weitere Informationen finden Sie unter [Auswählen eines Nachrichtenaustauschmusters](../../../../docs/framework/wcf/extending/choosing-a-message-exchange-pattern.md).  
  
2.  Es müssen eine Kanalfactory und ein Listener (<xref:System.ServiceModel.Channels.IChannelFactory> und <xref:System.ServiceModel.Channels.IChannelListener>) erstellt werden, die das Nachrichtenaustauschmuster unterstützen. Ausführliche Informationen zum Entwickeln von Factorys finden Sie unter [Client: Kanalfactorys und Kanäle](../../../../docs/framework/wcf/extending/client-channel-factories-and-channels.md). Ausführliche Informationen zum Entwickeln von Listenern finden Sie unter [Dienst: Kanallistener und Kanäle](../../../../docs/framework/wcf/extending/service-channel-listeners-and-channels.md).  
  
3.  Es muss sichergestellt werden, dass alle netzwerkspezifischen Ausnahmen zu <xref:System.TimeoutException?displayProperty=nameWithType> oder der entsprechenden abgeleiteten Klasse von <xref:System.ServiceModel.CommunicationException> normalisiert werden. Weitere Informationen finden Sie unter [Behandlung von Ausnahmen und Fehlern](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md).  
  
4.  Wenn Sie die Verwendung von der Anwendungsebene aktivieren möchten, fügen Sie ein <xref:System.ServiceModel.Channels.BindingElement> hinzu, über das der benutzerdefinierte Kanal einem Kanalstapel hinzugefügt wird. Weitere Informationen finden Sie unter [Erstellen eines BindingElement](../../../../docs/framework/wcf/extending/creating-a-bindingelement.md).  
  
 Die folgenden zusätzlichen Schritte sind erforderlich, um eine umfassendere Unterstützung auf Anwendungsebene zu aktivieren:  
  
1.  Fügen Sie einen Bindungselementerweiterungs-Abschnitt hinzu, um das neue Bindungselement für das Konfigurationssystem verfügbar zu machen. Weitere Informationen finden Sie unter [Konfigurations- und Metadatenunterstützung](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).  
  
2.  Fügen Sie Metadatenerweiterungen hinzu, um anderen Endpunkten Funktionen mitzuteilen. Weitere Informationen finden Sie unter [Konfigurations- und Metadatenunterstützung](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).  
  
3.  Fügen Sie eine Bindung hinzu, die einen Stapel mit Bindungselementen entsprechend einem genau definierten Profil vorkonfiguriert. Weitere Informationen finden Sie unter [Erstellen benutzerdefinierter Bindungen](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
4.  Fügen Sie einen Bindungsabschnitt und ein Bindungskonfigurationselement hinzu, um die Bindung für das Konfigurationssystem verfügbar zu machen. Weitere Informationen finden Sie unter [Konfigurations- und Metadatenunterstützung](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erweitern von Bindungen](../../../../docs/framework/wcf/extending/extending-bindings.md)
