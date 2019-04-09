---
title: 'Vorgehensweise: Nachrichtenaustausch mit WCF-Endpunkten und Message Queuing-Anwendungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
ms.openlocfilehash: 7fdcebe7ab9ee82a7283add9e0200af2ea5c94bd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198971"
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a>Vorgehensweise: Nachrichtenaustausch mit WCF-Endpunkten und Message Queuing-Anwendungen
Sie können vorhandene Message Queuing (MSMQ)-Anwendungen mit Windows Communication Foundation (WCF)-Anwendungen integrieren, mithilfe der Bindung der MSMQ-Integration MSMQ-Nachrichten an und von WCF-Nachrichten konvertiert. Dadurch können Sie einen Aufruf an die MSMQ-empfängeranwendungen von WCF-Clients sowie zum Aufrufen von WCF-Dienste aus der Sender MSMQ-Anwendungen.  
  
 In diesem Abschnitt wird erläutert, wie mit <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> für eine warteschlangenkommunikation zwischen (1) eine WCF-Client und einem MSMQ-Anwendungsdienst mit System.Messaging und (2) eine MSMQ-Anwendungsclient und einem WCF-Dienst geschrieben.  
  
 Ein vollständiges Beispiel, das veranschaulicht, wie eine MSMQ-empfängeranwendung von einem WCF-Client aufgerufen wird, finden Sie unter den [Windows Communication Foundation zu Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) Beispiel.  
  
 Ein vollständiges Beispiel, das veranschaulicht, wie Sie einen WCF-Dienst von einem MSMQ-Client aufrufen, finden Sie unter den [Message Queuing zu Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) Beispiel.  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a>So erstellen Sie einen WCF-Dienst, der Nachrichten von einem MSMQ-Client empfängt  
  
1.  Definieren Sie eine Schnittstelle, die den Dienstvertrag für den WCF-Dienst, der in der Warteschlange Nachrichten aus einer MSMQ-sendeanwendung empfängt definiert, wie im folgenden Beispielcode gezeigt.  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2.  Implementieren Sie die Schnittstelle, und wenden Sie das <xref:System.ServiceModel.ServiceBehaviorAttribute>-Attribut wie im folgenden Beispielcode gezeigt auf die Klasse an.  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3.  Erstellen Sie eine Konfigurationsdatei, die die <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> angibt.  

4.  Instanziieren Sie ein <xref:System.ServiceModel.ServiceHost>-Objekt, das die konfigurierte Bindung verwendet.  

### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a>So erstellen Sie einen WCF-Client, der Nachrichten an eine MSMQ-Empfängeranwendung sendet  
  
1.  Definieren Sie eine Schnittstelle, die den Dienstvertrag für den WCF-Client, sendet die Nachrichten an den MSMQ-Empfänger in der Warteschlange definiert, wie im folgenden Beispielcode gezeigt.  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2.  Definieren Sie eine Clientklasse, die der WCF-Client verwendet wird, um den MSMQ-Empfänger aufzurufen.  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3.  Erstellen Sie eine Konfiguration, die die Verwendung der MsmqIntegrationBinding-Bindung angibt.  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4.  Erstellen Sie eine Instanz der Clientklasse, und rufen Sie die vom Nachrichten empfangenden Dienst definierte Methode auf.  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a>Siehe auch

- [Warteschlangenübersicht](../../../../docs/framework/wcf/feature-details/queues-overview.md)
- [Vorgehensweise: Austauschen von Nachrichten in einer Warteschlange mit WCF-Endpunkten](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [Windows Communication Foundation zu Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)
- [Installieren von Message Queuing (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)
- [Message Queuing zu Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)
- [Nachrichtensicherheit über Message Queuing](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
