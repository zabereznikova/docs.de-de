---
title: 'Gewusst wie: Austauschen von Nachrichten in einer Warteschlange mit WCD-Endpunkten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 938e7825-f63a-4c3d-b603-63772fabfdb3
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a6c50d9c6740b0c680e349a71bf4b3bdece2b34f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-exchange-queued-messages-with-wcf-endpoints"></a>Gewusst wie: Austauschen von Nachrichten in einer Warteschlange mit WCD-Endpunkten
Warteschlangen stellen sicher, dass ein zuverlässiger Nachrichtenaustausch zwischen einem Client und einem [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienst stattfinden kann, selbst wenn der Dienst zum Zeitpunkt der Kommunikation nicht verfügbar ist. Die folgenden Vorgänge zeigen, wie Sie eine stabile Kommunikation zwischen einem Client und einem Dienst sicherstellen können, indem Sie die Standardbindung in der Warteschlange beim Implementieren des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensts verwenden.  
  
 Dieser Abschnitt erläutert die Verwendung der <xref:System.ServiceModel.NetMsmqBinding> für die Kommunikation in einer Warteschlange zwischen einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client und einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst.  
  
### <a name="to-use-queuing-in-a-wcf-service"></a>So verwenden Sie Warteschlangen in einem WCD-Dienst  
  
1.  Definieren Sie einen Dienstvertrag mit einer Schnittstelle, die mit dem <xref:System.ServiceModel.ServiceContractAttribute> gekennzeichnet ist. Kennzeichnen Sie die Vorgänge in der Schnittstelle, die Teil des Dienstvertrags mit dem <xref:System.ServiceModel.OperationContractAttribute> sind, und legen Sie sie als einseitig fest, da keine Antwort an die Methode zurückgegeben wird. Im folgenden Codebeispiel wird ein Dienstvertrag mit seiner Vorgangsdefinition dargestellt.  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2.  Wenn der Dienstvertrag benutzerdefinierte Typen übergibt, müssen Sie Datenverträge für diese Typen definieren. Der folgende Code stellt zwei Datenverträge dar: `PurchaseOrder` und `PurchaseOrderLineItem`. Die beiden Typen definieren die Daten, die an den Dienst gesendet werden. (Beachten Sie, dass die Klassen, die diesen Datenvertrag definieren, auch verschiedene Methoden definieren. Diese Methoden werden nicht als Teil des Datenvertrags behandelt. Nur Member, die mit dem `DataMember`-Attribut deklariert werden, sind Teil des Datenvertrags.)  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3.  Implementieren Sie die Methoden des Dienstvertrags, die  in der Schnittstelle in einer Klasse definiert sind.  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     Beachten Sie, dass das <xref:System.ServiceModel.OperationBehaviorAttribute> für die `SubmitPurchaseOrder`-Methode festgelegt ist. Hiermit wird angegeben, dass der Vorgang in einer Transaktion aufgerufen werden muss und dass die Transaktion automatisch beendet wird, wenn die Methode beendet wird.  
  
4.  Erstellen Sie eine Transaktionswarteschlange mit <xref:System.Messaging>. Sie können die Warteschlange stattdessen auch mit der Microsoft Message Queuing (MSMQ) Microsoft Management Console (MMC) erstellen. Erstellen Sie in diesem Fall unbedingt eine Transaktionswarteschlange.  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5.  Definieren Sie einen <xref:System.ServiceModel.Description.ServiceEndpoint> in einer Konfiguration, der die Dienstadresse festlegt und die Standard-<xref:System.ServiceModel.NetMsmqBinding>-Bindung verwendet. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Konfiguration finden Sie unter [Konfigurieren von Windows Communication Foundation-Anwendungen](http://msdn.microsoft.com/en-us/13cb368e-88d4-4c61-8eed-2af0361c6d7a).  
  
  
  
6.  Erstellen Sie einen Host für den `OrderProcessing`-Dienst mit <xref:System.ServiceModel.ServiceHost>, der Nachrichten aus der Warteschlange liest und sie verarbeitet. Öffnen Sie den Diensthost, um den Dienst verfügbar zu machen. Zeigen Sie eine Meldung an, die den Benutzer darüber informiert, dass er den Dienst durch Drücken einer beliebigen Taste beenden kann. Rufen Sie `ReadLine` auf, damit auf das Drücken einer Taste gewartet und dann der Dienst geschlossen wird.  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a>So erstellen Sie einen Client für einen Dienst in der Warteschlange  
  
1.  Das folgende Beispiel veranschaulicht, wie die Hostinganwendung ausgeführt und das Tool "Svcutil.exe" verwendet wird, um den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client zu erstellen.  
  
    ```  
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2.  Definieren Sie einen <xref:System.ServiceModel.Description.ServiceEndpoint> in einer Konfiguration, die die Adresse festlegt und die Standard-<xref:System.ServiceModel.NetMsmqBinding>-Bindung verwendet, wie im folgenden Beispiel gezeigt.  
  
  
  
3.  Erstellen Sie einen Transaktionsbereich zum Schreiben in die Transaktionswarteschlange, rufen Sie den `SubmitPurchaseOrder`-Vorgang auf, und schließen Sie den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client, wie im folgenden Beispiel gezeigt.  
  
     [!code-csharp[S_Msmq_Transacted#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#8)]
     [!code-vb[S_Msmq_Transacted#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#8)]  
  
## <a name="example"></a>Beispiel  
 Die folgenden Beispiele veranschaulichen den Dienstcode, die Hostinganwendung, die App.config-Datei und den Clientcode, die für dieses Beispiel eingeschlossen werden.  
  
 [!code-csharp[S_Msmq_Transacted#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#9)]
 [!code-vb[S_Msmq_Transacted#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#9)]  
  
 [!code-csharp[S_Msmq_Transacted#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#10)]
 [!code-vb[S_Msmq_Transacted#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#10)]  
  
  
  
 [!code-csharp[S_Msmq_Transacted#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#12)]
 [!code-vb[S_Msmq_Transacted#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#12)]  
  
  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.NetMsmqBinding>  
 [Abgewickelte MSMQ-Bindung](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)  
 [Warteschlangen in WCF](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [Vorgehensweise: Nachrichtenaustausch mit WCF-Endpunkten und Message Queuing-Anwendungen](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 [Windows Communication Foundation zu Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [Installieren von Message Queuing (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [Message Queuing-Integration Bindung-Beispiele](http://msdn.microsoft.com/en-us/997d11cb-f2c5-4ba0-9209-92843d4d0e1a)  
 [Message Queuing zu Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [Nachrichtensicherheit über Message Queuing](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
