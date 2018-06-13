---
title: 'Vorgehensweise: Nachrichtenaustausch mit WCF-Endpunkten und Message Queuing-Anwendungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
ms.openlocfilehash: 807a34ac50ea317ace42ec12eddcd9ec7cf3736b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491078"
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a><span data-ttu-id="f5b84-102">Vorgehensweise: Nachrichtenaustausch mit WCF-Endpunkten und Message Queuing-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="f5b84-102">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>
<span data-ttu-id="f5b84-103">Sie können vorhandene Message Queuing (MSMQ)-Anwendungen in Windows Communication Foundation (WCF)-Anwendungen integrieren, mit der Bindung für die MSMQ-Integration MSMQ-Nachrichten an und von WCF-Nachrichten konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f5b84-103">You can integrate existing Message Queuing (MSMQ) applications with Windows Communication Foundation (WCF) applications by using the MSMQ integration binding to convert MSMQ messages to and from WCF messages.</span></span> <span data-ttu-id="f5b84-104">Dadurch können Sie einen Aufruf an die MSMQ-empfängeranwendungen von WCF-Clients als auch in WCF-Dienste sendeanwendungen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f5b84-104">This allows you to call into MSMQ receiver applications from WCF clients as well as call into WCF services from MSMQ sender applications.</span></span>  
  
 <span data-ttu-id="f5b84-105">In diesem Abschnitt wird erläutert, wie mit <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> für eine warteschlangenkommunikation zwischen (1) einen WCF-Client und einen MSMQ-Anwendungsdienst mit System.Messaging und (2) eine MSMQ-Anwendungsclient und einem WCF-Dienst geschrieben.</span><span class="sxs-lookup"><span data-stu-id="f5b84-105">In this section, we explain how to use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> for queued communication between (1) a WCF client and an MSMQ application service written using System.Messaging and (2) an MSMQ application client and a WCF service.</span></span>  
  
 <span data-ttu-id="f5b84-106">Ein vollständiges Beispiel, das veranschaulicht, wie eine MSMQ-empfängeranwendung von einem WCF-Client aufgerufen wird, finden Sie unter der [Windows Communication Foundation zu Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="f5b84-106">For a complete sample that demonstrates how to call a MSMQ receiver application from a WCF client, see the [Windows Communication Foundation to Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) sample.</span></span>  
  
 <span data-ttu-id="f5b84-107">Ein vollständiges Beispiel, das veranschaulicht, wie einen WCF-Dienst von einem MSMQ-Client aufgerufen wird, finden Sie unter der [Message Queuing zu Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="f5b84-107">For a complete sample that demonstrates how to call a WCF service from a MSMQ client, see the [Message Queuing to Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) sample.</span></span>  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a><span data-ttu-id="f5b84-108">So erstellen Sie einen WCF-Dienst, der Nachrichten von einem MSMQ-Client empfängt</span><span class="sxs-lookup"><span data-stu-id="f5b84-108">To create a WCF service that receives messages from a MSMQ client</span></span>  
  
1.  <span data-ttu-id="f5b84-109">Definieren Sie eine Schnittstelle, die den Dienstvertrag für den WCF-Dienst, der in der Warteschlange Nachrichten aus einer MSMQ-sendeanwendung empfängt definiert, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5b84-109">Define an interface that defines the service contract for the WCF service that receives queued messages from a MSMQ sender application, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2.  <span data-ttu-id="f5b84-110">Implementieren Sie die Schnittstelle, und wenden Sie das <xref:System.ServiceModel.ServiceBehaviorAttribute>-Attribut wie im folgenden Beispielcode gezeigt auf die Klasse an.</span><span class="sxs-lookup"><span data-stu-id="f5b84-110">Implement the interface and apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to the class, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3.  <span data-ttu-id="f5b84-111">Erstellen Sie eine Konfigurationsdatei, die die <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> angibt.</span><span class="sxs-lookup"><span data-stu-id="f5b84-111">Create a configuration file that specifies the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span></span>  
  
  
  
4.  <span data-ttu-id="f5b84-112">Instanziieren Sie ein <xref:System.ServiceModel.ServiceHost>-Objekt, das die konfigurierte Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="f5b84-112">Instantiate a <xref:System.ServiceModel.ServiceHost> object that uses the configured binding.</span></span>  
  
  
  
### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a><span data-ttu-id="f5b84-113">So erstellen Sie einen WCF-Client, der Nachrichten an eine MSMQ-Empfängeranwendung sendet</span><span class="sxs-lookup"><span data-stu-id="f5b84-113">To create a WCF client that sends messages to a MSMQ receiver application</span></span>  
  
1.  <span data-ttu-id="f5b84-114">Definieren Sie eine Schnittstelle, die den Dienstvertrag für den WCF-Client, sendet Nachrichten an den MSMQ-Empfänger in der Warteschlange definiert, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5b84-114">Define an interface that defines the service contract for the WCF client that sends queued messages to the MSMQ receiver, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2.  <span data-ttu-id="f5b84-115">Definieren Sie eine Clientklasse, die der WCF-Client verwendet wird, um die MSMQ-Empfänger aufruft.</span><span class="sxs-lookup"><span data-stu-id="f5b84-115">Define a client class that the WCF client uses to call the MSMQ receiver.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3.  <span data-ttu-id="f5b84-116">Erstellen Sie eine Konfiguration, die die Verwendung der MsmqIntegrationBinding-Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="f5b84-116">Create a configuration that specifies use of the MsmqIntegrationBinding binding.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4.  <span data-ttu-id="f5b84-117">Erstellen Sie eine Instanz der Clientklasse, und rufen Sie die vom Nachrichten empfangenden Dienst definierte Methode auf.</span><span class="sxs-lookup"><span data-stu-id="f5b84-117">Create an instance of the client class and call the method defined by the message receiving service.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="f5b84-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5b84-118">See Also</span></span>  
 [<span data-ttu-id="f5b84-119">Warteschlangenübersicht</span><span class="sxs-lookup"><span data-stu-id="f5b84-119">Queues Overview</span></span>](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 [<span data-ttu-id="f5b84-120">Vorgehensweise: Austauschen von Nachrichten in einer Warteschlange mit WCD-Endpunkten</span><span class="sxs-lookup"><span data-stu-id="f5b84-120">How to: Exchange Queued Messages with WCF Endpoints</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 [<span data-ttu-id="f5b84-121">Windows Communication Foundation zu Message Queuing</span><span class="sxs-lookup"><span data-stu-id="f5b84-121">Windows Communication Foundation to Message Queuing</span></span>](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [<span data-ttu-id="f5b84-122">Installieren von Message Queuing (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="f5b84-122">Installing Message Queuing (MSMQ)</span></span>](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [<span data-ttu-id="f5b84-123">Message Queuing zu Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="f5b84-123">Message Queuing to Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [<span data-ttu-id="f5b84-124">Nachrichtensicherheit über Message Queuing</span><span class="sxs-lookup"><span data-stu-id="f5b84-124">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
