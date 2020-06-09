---
title: 'Vorgehensweise: Nachrichtenaustausch mit WCF-Endpunkten und Message Queuing-Anwendungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
ms.openlocfilehash: 0775de90903aed27a8d0006614a4b6f2d857eee3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597097"
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a>Vorgehensweise: Nachrichtenaustausch mit WCF-Endpunkten und Message Queuing-Anwendungen
Sie können vorhandene Message Queuing (MSMQ)-Anwendungen mit Windows Communication Foundation (WCF)-Anwendungen integrieren, indem Sie die MSMQ-Integrations Bindung verwenden, um MSMQ-Nachrichten in und aus WCF-Nachrichten zu konvertieren. Dies ermöglicht es Ihnen, MSMQ-Empfänger Anwendungen von WCF-Clients aus aufzurufen und WCF-Dienste von MSMQ-Absender Anwendungen aufzurufen.  
  
 In diesem Abschnitt wird erläutert, wie Sie <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> für die Warteschlangen Kommunikation zwischen (1) einem WCF-Client und einem MSMQ-Anwendungs Dienst, der mithilfe von System. Messaging geschrieben wurde, und (2) einen MSMQ-Anwendungs Client und einen WCF-Dienst verwenden.  
  
 Ein umfassendes Beispiel, das veranschaulicht, wie eine MSMQ-Empfänger Anwendung von einem WCF-Client aufgerufen wird, finden Sie im Beispiel [Windows Communication Foundation to Message Queuing](../samples/wcf-to-message-queuing.md) .  
  
 Ein umfassendes Beispiel, das veranschaulicht, wie ein WCF-Dienst von einem MSMQ-Client aufgerufen wird, finden Sie im Beispiel [Message Queuing to Windows Communication Foundation](../samples/message-queuing-to-wcf.md) .  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a>So erstellen Sie einen WCF-Dienst, der Nachrichten von einem MSMQ-Client empfängt  
  
1. Definieren Sie eine Schnittstelle, die den Dienstvertrag für den WCF-Dienst definiert, der in der Warteschlange befindliche Nachrichten von einer MSMQ-Absender Anwendung empfängt, wie im folgenden Beispielcode gezeigt.  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2. Implementieren Sie die Schnittstelle, und wenden Sie das <xref:System.ServiceModel.ServiceBehaviorAttribute>-Attribut wie im folgenden Beispielcode gezeigt auf die Klasse an.  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3. Erstellen Sie eine Konfigurationsdatei, die die <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> angibt.  

4. Instanziieren Sie ein <xref:System.ServiceModel.ServiceHost>-Objekt, das die konfigurierte Bindung verwendet.  

### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a>So erstellen Sie einen WCF-Client, der Nachrichten an eine MSMQ-Empfängeranwendung sendet  
  
1. Definieren Sie eine Schnittstelle, die den Dienstvertrag für den WCF-Client definiert, der Nachrichten in der Warteschlange an den MSMQ-Empfänger sendet, wie im folgenden Beispielcode gezeigt.  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2. Definieren Sie eine Client Klasse, die der WCF-Client verwendet, um den MSMQ-Empfänger aufzurufen.  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3. Erstellen Sie eine Konfiguration, die die Verwendung der MsmqIntegrationBinding-Bindung angibt.  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4. Erstellen Sie eine Instanz der Clientklasse, und rufen Sie die vom Nachrichten empfangenden Dienst definierte Methode auf.  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Warteschlangenübersicht](queues-overview.md)
- [Vorgehensweise: Austauschen von Nachrichten in einer Warteschlange mit WCF-Endpunkten](how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [Windows Communication Foundation zu Message Queuing](../samples/wcf-to-message-queuing.md)
- [Installieren von Message Queuing (MSMQ)](../samples/installing-message-queuing-msmq.md)
- [Message Queuing zu Windows Communication Foundation](../samples/message-queuing-to-wcf.md)
- [Nachrichtensicherheit über Message Queuing](../samples/message-security-over-message-queuing.md)
