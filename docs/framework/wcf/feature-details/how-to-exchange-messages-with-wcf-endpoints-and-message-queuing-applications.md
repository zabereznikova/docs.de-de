---
title: 'Vorgehensweise: Nachrichtenaustausch mit WCF-Endpunkten und Message Queuing-Anwendungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
ms.openlocfilehash: 8f8baf345059c01b0fef3b61ef85556151269118
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96246419"
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a><span data-ttu-id="8a389-102">Vorgehensweise: Nachrichtenaustausch mit WCF-Endpunkten und Message Queuing-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="8a389-102">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>

<span data-ttu-id="8a389-103">Sie können vorhandene Message Queuing (MSMQ)-Anwendungen mit Windows Communication Foundation (WCF)-Anwendungen integrieren, indem Sie die MSMQ-Integrations Bindung verwenden, um MSMQ-Nachrichten in und aus WCF-Nachrichten zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="8a389-103">You can integrate existing Message Queuing (MSMQ) applications with Windows Communication Foundation (WCF) applications by using the MSMQ integration binding to convert MSMQ messages to and from WCF messages.</span></span> <span data-ttu-id="8a389-104">Dies ermöglicht es Ihnen, MSMQ-Empfänger Anwendungen von WCF-Clients aus aufzurufen und WCF-Dienste von MSMQ-Absender Anwendungen aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="8a389-104">This allows you to call into MSMQ receiver applications from WCF clients as well as call into WCF services from MSMQ sender applications.</span></span>  
  
 <span data-ttu-id="8a389-105">In diesem Abschnitt wird erläutert, wie Sie <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> für die Warteschlangen Kommunikation zwischen (1) einem WCF-Client und einem MSMQ-Anwendungs Dienst, der mithilfe von System. Messaging geschrieben wurde, und (2) einen MSMQ-Anwendungs Client und einen WCF-Dienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="8a389-105">In this section, we explain how to use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> for queued communication between (1) a WCF client and an MSMQ application service written using System.Messaging and (2) an MSMQ application client and a WCF service.</span></span>  
  
 <span data-ttu-id="8a389-106">Ein umfassendes Beispiel, das veranschaulicht, wie eine MSMQ-Empfänger Anwendung von einem WCF-Client aufgerufen wird, finden Sie im Beispiel [Windows Communication Foundation to Message Queuing](../samples/wcf-to-message-queuing.md) .</span><span class="sxs-lookup"><span data-stu-id="8a389-106">For a complete sample that demonstrates how to call a MSMQ receiver application from a WCF client, see the [Windows Communication Foundation to Message Queuing](../samples/wcf-to-message-queuing.md) sample.</span></span>  
  
 <span data-ttu-id="8a389-107">Ein umfassendes Beispiel, das veranschaulicht, wie ein WCF-Dienst von einem MSMQ-Client aufgerufen wird, finden Sie im Beispiel [Message Queuing to Windows Communication Foundation](../samples/message-queuing-to-wcf.md) .</span><span class="sxs-lookup"><span data-stu-id="8a389-107">For a complete sample that demonstrates how to call a WCF service from a MSMQ client, see the [Message Queuing to Windows Communication Foundation](../samples/message-queuing-to-wcf.md) sample.</span></span>  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a><span data-ttu-id="8a389-108">So erstellen Sie einen WCF-Dienst, der Nachrichten von einem MSMQ-Client empfängt</span><span class="sxs-lookup"><span data-stu-id="8a389-108">To create a WCF service that receives messages from a MSMQ client</span></span>  
  
1. <span data-ttu-id="8a389-109">Definieren Sie eine Schnittstelle, die den Dienstvertrag für den WCF-Dienst definiert, der in der Warteschlange befindliche Nachrichten von einer MSMQ-Absender Anwendung empfängt, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8a389-109">Define an interface that defines the service contract for the WCF service that receives queued messages from a MSMQ sender application, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2. <span data-ttu-id="8a389-110">Implementieren Sie die Schnittstelle, und wenden Sie das <xref:System.ServiceModel.ServiceBehaviorAttribute>-Attribut wie im folgenden Beispielcode gezeigt auf die Klasse an.</span><span class="sxs-lookup"><span data-stu-id="8a389-110">Implement the interface and apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to the class, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3. <span data-ttu-id="8a389-111">Erstellen Sie eine Konfigurationsdatei, die die <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> angibt.</span><span class="sxs-lookup"><span data-stu-id="8a389-111">Create a configuration file that specifies the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span></span>  

4. <span data-ttu-id="8a389-112">Instanziieren Sie ein <xref:System.ServiceModel.ServiceHost>-Objekt, das die konfigurierte Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="8a389-112">Instantiate a <xref:System.ServiceModel.ServiceHost> object that uses the configured binding.</span></span>  

### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a><span data-ttu-id="8a389-113">So erstellen Sie einen WCF-Client, der Nachrichten an eine MSMQ-Empfängeranwendung sendet</span><span class="sxs-lookup"><span data-stu-id="8a389-113">To create a WCF client that sends messages to a MSMQ receiver application</span></span>  
  
1. <span data-ttu-id="8a389-114">Definieren Sie eine Schnittstelle, die den Dienstvertrag für den WCF-Client definiert, der Nachrichten in der Warteschlange an den MSMQ-Empfänger sendet, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8a389-114">Define an interface that defines the service contract for the WCF client that sends queued messages to the MSMQ receiver, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2. <span data-ttu-id="8a389-115">Definieren Sie eine Client Klasse, die der WCF-Client verwendet, um den MSMQ-Empfänger aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="8a389-115">Define a client class that the WCF client uses to call the MSMQ receiver.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3. <span data-ttu-id="8a389-116">Erstellen Sie eine Konfiguration, die die Verwendung der MsmqIntegrationBinding-Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="8a389-116">Create a configuration that specifies use of the MsmqIntegrationBinding binding.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4. <span data-ttu-id="8a389-117">Erstellen Sie eine Instanz der Clientklasse, und rufen Sie die vom Nachrichten empfangenden Dienst definierte Methode auf.</span><span class="sxs-lookup"><span data-stu-id="8a389-117">Create an instance of the client class and call the method defined by the message receiving service.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="8a389-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a389-118">See also</span></span>

- [<span data-ttu-id="8a389-119">Warteschlangenübersicht</span><span class="sxs-lookup"><span data-stu-id="8a389-119">Queues Overview</span></span>](queues-overview.md)
- [<span data-ttu-id="8a389-120">Vorgehensweise: Austauschen von Nachrichten in einer Warteschlange mit WCF-Endpunkten</span><span class="sxs-lookup"><span data-stu-id="8a389-120">How to: Exchange Queued Messages with WCF Endpoints</span></span>](how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [<span data-ttu-id="8a389-121">Windows Communication Foundation zu Message Queuing</span><span class="sxs-lookup"><span data-stu-id="8a389-121">Windows Communication Foundation to Message Queuing</span></span>](../samples/wcf-to-message-queuing.md)
- [<span data-ttu-id="8a389-122">Installieren von Message Queuing (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="8a389-122">Installing Message Queuing (MSMQ)</span></span>](../samples/installing-message-queuing-msmq.md)
- [<span data-ttu-id="8a389-123">Message Queuing zu Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="8a389-123">Message Queuing to Windows Communication Foundation</span></span>](../samples/message-queuing-to-wcf.md)
- [<span data-ttu-id="8a389-124">Nachrichtensicherheit über Message Queuing</span><span class="sxs-lookup"><span data-stu-id="8a389-124">Message Security over Message Queuing</span></span>](../samples/message-security-over-message-queuing.md)
