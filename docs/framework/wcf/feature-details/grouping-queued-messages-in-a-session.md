---
title: Gruppieren von Nachrichten in der Warteschlange einer Sitzung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- queues [WCF]. grouping messages
ms.assetid: 63b23b36-261f-4c37-99a2-cc323cd72a1a
ms.openlocfilehash: 66f51267f20f8cdad8feeedf37435ccfa733146e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597357"
---
# <a name="grouping-queued-messages-in-a-session"></a>Gruppieren von Nachrichten in der Warteschlange einer Sitzung
Windows Communication Foundation (WCF) stellt eine Sitzung bereit, mit der Sie einen Satz verwandter Nachrichten zur Verarbeitung durch eine einzelne empfangende Anwendung gruppieren können. Die Nachrichten in einer Sitzung müssen Teil der gleichen Transaktion sein. Da alle Nachrichten Teil der gleichen Transaktion sind, wird die gesamte Sitzung zurückgesetzt, wenn eine Nachricht nicht verarbeitet werden kann. Sitzungen weisen ähnliche Verhaltensweisen bezüglich Warteschlangen für unzustellbare Nachrichten und Warteschlangen für potenziell schädliche Nachrichten auf. Die Time to Live (TTL)-Eigenschaft einer Bindung in der Warteschlange, die für Sitzungen konfiguriert wurde, wird auf die gesamte Sitzung angewendet. Wenn nur ein Teil der Nachrichten in der Sitzung vor Ablauf der TTL gesendet wird, wird die gesamte Sitzung in der Warteschlange für unzustellbare Nachrichten abgelegt. Analog wird ggf. die gesamte Sitzung in der Warteschlange für potenziell schädliche Nachrichten abgelegt, wenn Nachrichten in einer Sitzung nicht von der Anwendungswarteschlange an eine Anwendung gesendet werden können.  
  
## <a name="message-grouping-example"></a>Beispiel für das Gruppieren von Nachrichten  
 Ein Beispiel für das Gruppieren von Nachrichten ist die Implementierung einer Anwendung zur Auftrags Verarbeitung als WCF-Dienst. Angenommen, ein Client sendet einen Auftrag an diese Anwendung, die eine Anzahl von Elementen enthält. Der Client ruft für jedes Element den Dienst auf. Dadurch wird jeweils eine separate Nachricht gesendet. Es kann sein, dass Server A das erste Element empfängt und Server B das zweite. Immer, wenn ein Element hinzugefügt wird, muss der Server, der das Element verarbeitet, die entsprechende Reihenfolge ermitteln, und das Element muss hinzugefügt werden. Dieser Vorgang ist nicht sehr effizient. Dieses Problem tritt auch dann auf, wenn alle Anfragen nur von einem Server behandelt werden, da der Server alle Aufträge überwachen muss, die derzeit verarbeitet werden, und das neue Element einem Auftrag zugeordnet werden muss. Durch das Gruppieren aller Anforderungen für einen Auftrag wird die Implementierung einer solchen Anwendung stark vereinfacht. Alle Elemente für einen Auftrag werden von der Clientanwendung in einer Sitzung gesendet, sodass der Auftrag vom Dienst in einer Sitzung verarbeitet werden kann. \  
  
## <a name="procedures"></a>Prozeduren  
  
#### <a name="to-set-up-a-service-contract-to-use-sessions"></a>So richten Sie einen Dienstvertrag für Sitzungen ein  
  
1. Definieren Sie einen Dienstvertrag, der eine Sitzung erfordert. Verwenden Sie hierzu das-Attribut, indem Sie Folgendes <xref:System.ServiceModel.ServiceContractAttribute> angeben:  
  
    ```csharp
    SessionMode=SessionMode.Required  
    ```  
  
2. Markieren Sie die Vorgänge im Vertrag als unidirektional, da von diesen Methoden nichts zurückgegeben wird. Dies erfolgt mit dem- <xref:System.ServiceModel.OperationContractAttribute> Attribut, indem Folgendes angegeben wird:  
  
    ```csharp  
    [OperationContract(IsOneWay = true)]  
    ```  
  
3. Implementieren Sie den Dienstvertrag, und geben Sie einen <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode> von <xref:System.ServiceModel.InstanceContextMode.PerSession?displayProperty=nameWithType> an. Dadurch wird der Dienst für jede Sitzung nur einmal instanziiert.  
  
    ```csharp  
    [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
    ```  
  
4. Jeder Dienstvorgang erfordert eine Transaktion. Verwenden Sie das <xref:System.ServiceModel.OperationBehaviorAttribute>-Attribut für die Angabe. Der Vorgang, mit dem die Transaktion abgeschlossen wird, sollte auch <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete> auf `true` festlegen.  
  
    ```csharp  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    ```  
  
5. Konfigurieren Sie einen Endpunkt, der die vom System bereitgestellte `NetMsmqBinding`-Bindung verwendet.  
  
6. Erstellen Sie eine Transaktionswarteschlange mit <xref:System.Messaging>. Sie können die Warteschlange auch mit Message Queuing (MSMQ) oder MMC erstellen. Erstellen Sie in diesem Fall eine Transaktionswarteschlange.  
  
7. Erstellen Sie mit <xref:System.ServiceModel.ServiceHost> einen Host für den Dienst.  
  
8. Öffnen Sie den Diensthost, um den Dienst verfügbar zu machen.  
  
9. Schließen Sie den Diensthost.  
  
#### <a name="to-set-up-a-client"></a>So richten Sie einen Client ein  
  
1. Erstellen Sie einen Transaktionsbereich zum Schreiben in die Transaktionswarteschlange.  
  
2. Erstellen Sie den WCF-Client mit dem [Service Model Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) Tool.  
  
3. Platzieren Sie den Auftrag.  
  
4. Schließen Sie den WCF-Client.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>BESCHREIBUNG  
 Im folgenden Beispiel wird der Code für den `IProcessOrder`-Dienst sowie für einen Client bereitgestellt, der diesen Dienst verwendet. Es zeigt, wie WCF Warteschlangen Sitzungen verwendet, um das Gruppierungs Verhalten bereitzustellen.  
  
### <a name="code-for-the-service"></a>Code für den Dienst  
 [!code-csharp[S_Msmq_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/service.cs#1)]
 [!code-vb[S_Msmq_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/service.vb#1)]  

### <a name="code-for-the-client"></a>Code für den Client  
 [!code-csharp[S_Msmq_Session#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/client.cs#3)]
 [!code-vb[S_Msmq_Session#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/client.vb#3)]  

## <a name="see-also"></a>Weitere Informationen

- [Sitzungen und Warteschlangen](../samples/sessions-and-queues.md)
- [Warteschlangenübersicht](queues-overview.md)
