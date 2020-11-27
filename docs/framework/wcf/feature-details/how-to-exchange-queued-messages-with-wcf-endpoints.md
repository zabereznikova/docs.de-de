---
title: 'Vorgehensweise: Austauschen von Nachrichten in einer Warteschlange mit WCF-Endpunkten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 938e7825-f63a-4c3d-b603-63772fabfdb3
ms.openlocfilehash: 3f69286a2b4d4ec55f18931f9156c20a38da9c34
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265426"
---
# <a name="how-to-exchange-queued-messages-with-wcf-endpoints"></a>Vorgehensweise: Austauschen von Nachrichten in einer Warteschlange mit WCF-Endpunkten

Warteschlangen stellen sicher, dass zuverlässiges Messaging zwischen einem Client und einem Windows Communication Foundation (WCF)-Dienst erfolgen kann, auch wenn der Dienst zum Zeitpunkt der Kommunikation nicht verfügbar ist. In den folgenden Verfahren wird gezeigt, wie eine permanente Kommunikation zwischen einem Client und einem Dienst mithilfe der standardmäßigen in der Warteschlange befindlichen Bindung bei der Implementierung des WCF-Dienstanbieter sichergestellt  
  
 In diesem Abschnitt wird erläutert, wie <xref:System.ServiceModel.NetMsmqBinding> für die Warteschlangen Kommunikation zwischen einem WCF-Client und einem WCF-Dienst verwendet wird.  
  
### <a name="to-use-queuing-in-a-wcf-service"></a>So verwenden Sie Warteschlangen in einem WCD-Dienst  
  
1. Definieren Sie einen Dienstvertrag mit einer Schnittstelle, die mit dem <xref:System.ServiceModel.ServiceContractAttribute> gekennzeichnet ist. Kennzeichnen Sie die Vorgänge in der Schnittstelle, die Teil des Dienstvertrags mit dem <xref:System.ServiceModel.OperationContractAttribute> sind, und legen Sie sie als einseitig fest, da keine Antwort an die Methode zurückgegeben wird. Im folgenden Codebeispiel wird ein Dienstvertrag mit seiner Vorgangsdefinition dargestellt.  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2. Wenn der Dienstvertrag benutzerdefinierte Typen übergibt, müssen Sie Datenverträge für diese Typen definieren. Der folgende Code stellt zwei Datenverträge dar: `PurchaseOrder` und `PurchaseOrderLineItem`. Die beiden Typen definieren die Daten, die an den Dienst gesendet werden. (Beachten Sie, dass die Klassen, die diesen Datenvertrag definieren, auch verschiedene Methoden definieren. Diese Methoden werden nicht als Teil des Datenvertrags behandelt. Nur Member, die mit dem <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut deklariert werden, sind Teil des Datenvertrags.)  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3. Implementieren Sie die Methoden des Dienstvertrags, die  in der Schnittstelle in einer Klasse definiert sind.  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     Beachten Sie, dass das <xref:System.ServiceModel.OperationBehaviorAttribute> für die `SubmitPurchaseOrder`-Methode festgelegt ist. Hiermit wird angegeben, dass der Vorgang in einer Transaktion aufgerufen werden muss und dass die Transaktion automatisch beendet wird, wenn die Methode beendet wird.  
  
4. Erstellen Sie eine Transaktionswarteschlange mit <xref:System.Messaging>. Sie können die Warteschlange stattdessen auch mit der Microsoft Message Queuing (MSMQ) Microsoft Management Console (MMC) erstellen. Erstellen Sie in diesem Fall unbedingt eine Transaktionswarteschlange.  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5. Definieren Sie einen <xref:System.ServiceModel.Description.ServiceEndpoint> in einer Konfiguration, der die Dienstadresse festlegt und die Standard-<xref:System.ServiceModel.NetMsmqBinding>-Bindung verwendet. Weitere Informationen zur Verwendung der WCF-Konfiguration finden Sie unter [Konfigurieren von WCF-Diensten](../configuring-services.md).  

6. Erstellen Sie einen Host für den `OrderProcessing`-Dienst mit <xref:System.ServiceModel.ServiceHost>, der Nachrichten aus der Warteschlange liest und sie verarbeitet. Öffnen Sie den Diensthost, um den Dienst verfügbar zu machen. Zeigen Sie eine Meldung an, die den Benutzer darüber informiert, dass er den Dienst durch Drücken einer beliebigen Taste beenden kann. Rufen Sie `ReadLine` auf, damit auf das Drücken einer Taste gewartet und dann der Dienst geschlossen wird.  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a>So erstellen Sie einen Client für einen Dienst in der Warteschlange  
  
1. Im folgenden Beispiel wird gezeigt, wie die Host Anwendung ausgeführt wird und wie das Svcutil.exe Tool verwendet wird, um den WCF-Client zu erstellen.  
  
    ```console
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2. Definieren Sie einen <xref:System.ServiceModel.Description.ServiceEndpoint> in einer Konfiguration, die die Adresse festlegt und die Standard-<xref:System.ServiceModel.NetMsmqBinding>-Bindung verwendet, wie im folgenden Beispiel gezeigt.  

3. Erstellen Sie einen Transaktions Bereich zum Schreiben in die Transaktions Warteschlange, rufen Sie den `SubmitPurchaseOrder` -Vorgang auf, und schließen Sie den WCF-Client, wie im folgenden Beispiel gezeigt.  
  
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

## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.NetMsmqBinding>
- [Abgewickelte MSMQ-Bindung](../samples/transacted-msmq-binding.md)
- [Warteschlangen in WCF](queuing-in-wcf.md)
- [Vorgehensweise: Nachrichtenaustausch mit WCF-Endpunkten und Message Queuing-Anwendungen](how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- [Windows Communication Foundation zu Message Queuing](../samples/wcf-to-message-queuing.md)
- [Installieren von Message Queuing (MSMQ)](../samples/installing-message-queuing-msmq.md)
- [Message Queuing zu Windows Communication Foundation](../samples/message-queuing-to-wcf.md)
- [Nachrichtensicherheit über Message Queuing](../samples/message-security-over-message-queuing.md)
