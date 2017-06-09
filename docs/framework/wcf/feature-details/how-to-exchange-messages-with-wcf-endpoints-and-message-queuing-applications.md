---
title: "Vorgehensweise: Nachrichtenaustausch mit WCF-Endpunkten und Message Queuing-Anwendungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Vorgehensweise: Nachrichtenaustausch mit WCF-Endpunkten und Message Queuing-Anwendungen
Sie können vorhandene Message Queuing (MSMQ)- Anwendungen mit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Anwendungen integrieren, indem Sie mithilfe der Bindung für die MSMQ-Integration MSMQ-Nachrichten in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Nachrichten und WCF-Nachrichten in MSMQ-Nachrichten konvertieren. So können Sie mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients MSMQ-Empfängeranwendungen und mit MSMQ-Sendeanwendungen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste aufrufen.  
  
 In diesem Abschnitt wird erläutert, wie mit <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> für die warteschlangenkommunikation zwischen (1) ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Client und ein MSMQ-Anwendungsdienst mit System.Messaging und (2) einem MSMQ-Anwendungsclient geschrieben und ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Service.  
  
 Ein vollständiges Beispiel, das veranschaulicht, wie eine MSMQ-empfängeranwendung von einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Client finden Sie unter der [Windows Communication Foundation zu Message Queuing-](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) Beispiel.  
  
 Ein vollständiges Beispiel, das veranschaulicht, wie eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service aus einem MSMQ-Client, finden Sie unter der [Message Queuing zu Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) Beispiel.  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a>So erstellen Sie einen WCF-Dienst, der Nachrichten von einem MSMQ-Client empfängt  
  
1.  Definieren Sie wie im folgenden Beispielcode gezeigt eine Schnittstelle, die den Dienstvertrag für den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst definiert, der die über eine Warteschlange geleiteten Nachrichten einer MSMQ-Sendeanwendung empfängt:  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2.  Die-Schnittstelle implementieren und Anwenden der <xref:System.ServiceModel.ServiceBehaviorAttribute> -Attribut auf die Klasse, wie im folgenden Beispielcode gezeigt.  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3.  Eine Konfigurationsdatei erstellen, die angibt, die <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.  
  
  
  
4.  Instanziieren einer <xref:System.ServiceModel.ServiceHost> -Objekt, das die konfigurierte Bindung verwendet.  
  
  
  
### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a>So erstellen Sie einen WCF-Client, der Nachrichten an eine MSMQ-Empfängeranwendung sendet  
  
1.  Definieren Sie wie im folgenden Beispielcode gezeigt eine Schnittstelle, die den Dienstvertrag für den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client definiert, der über eine Warteschlange geleitete Nachrichten an den MSMQ-Empfänger sendet:  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2.  Definieren Sie eine Clientklasse, über die der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client den MSMQ-Empfänger aufruft.  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3.  Erstellen Sie eine Konfiguration, die die Verwendung der MsmqIntegrationBinding-Bindung angibt.  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4.  Erstellen Sie eine Instanz der Clientklasse, und rufen Sie die vom Nachrichten empfangenden Dienst definierte Methode auf.  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a>Siehe auch  
 [Nachrichtenwarteschlangen (Übersicht)](../../../../docs/framework/wcf/feature-details/queues-overview.md)   
 [Gewusst wie: Austauschen in einer Warteschlange Nachrichten mit WCF-Endpunkten](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)   
 [Windows Communication Foundation zu Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)   
 [Installieren von Message Queuing (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)   
 [Message Queuing zu Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)   
 [Nachrichtensicherheit über Message Queuing](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)