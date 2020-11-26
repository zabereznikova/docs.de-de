---
title: WCF-Fehlerbehandlung
ms.date: 03/30/2017
ms.assetid: 1e4b1e0f-9598-449d-9d73-90bda62305b8
ms.openlocfilehash: 72db5db9f6b4a3cd2ba62fe938fcfeed2dfda1e5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240939"
---
# <a name="wcf-error-handling"></a><span data-ttu-id="6f3a5-102">WCF-Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="6f3a5-102">WCF Error Handling</span></span>

<span data-ttu-id="6f3a5-103">Die bei einer WCF-Anwendung aufgetretenen Fehler gehören zu einer von drei Gruppen:</span><span class="sxs-lookup"><span data-stu-id="6f3a5-103">The errors encountered by a WCF application belong to one of three groups:</span></span>  
  
1. <span data-ttu-id="6f3a5-104">Kommunikationsfehler</span><span class="sxs-lookup"><span data-stu-id="6f3a5-104">Communication Errors</span></span>  
  
2. <span data-ttu-id="6f3a5-105">Proxy-/Channelfehler</span><span class="sxs-lookup"><span data-stu-id="6f3a5-105">Proxy/Channel Errors</span></span>  
  
3. <span data-ttu-id="6f3a5-106">Anwendungsfehler</span><span class="sxs-lookup"><span data-stu-id="6f3a5-106">Application Errors</span></span>  
  
 <span data-ttu-id="6f3a5-107">Kommunikationsfehler treten auf, wenn ein Netzwerk nicht verfügbar ist, ein Client eine falsche Adresse verwendet oder der Diensthost keine eingehende Nachrichten überwacht.</span><span class="sxs-lookup"><span data-stu-id="6f3a5-107">Communication errors occur when a network is unavailable, a client uses an incorrect address, or the service host is not listening for incoming messages.</span></span> <span data-ttu-id="6f3a5-108">An den Client werden Fehler dieses Typs als <xref:System.ServiceModel.CommunicationException>-Klasse oder abgeleitete <xref:System.ServiceModel.CommunicationException>-Klasse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6f3a5-108">Errors of this type are returned to the client as <xref:System.ServiceModel.CommunicationException> or <xref:System.ServiceModel.CommunicationException>-derived classes.</span></span>  
  
 <span data-ttu-id="6f3a5-109">Proxy-/Channelfehler sind Fehler, die innerhalb des Channels oder des Proxys selbst auftreten.</span><span class="sxs-lookup"><span data-stu-id="6f3a5-109">Proxy/Channel errors are errors that occur within the channel or proxy itself.</span></span> <span data-ttu-id="6f3a5-110">Fehler dieses Typs sind unter anderem: Versuche, einen Proxy oder Channel zu verwenden, der geschlossen wurde, ein Vertragskonflikt zwischen Client und Dienst oder die Ablehnung der Anmeldeinformationen des Clients durch den Dienst.</span><span class="sxs-lookup"><span data-stu-id="6f3a5-110">Errors of this type include: attempting to use a proxy or channel that has been closed, a contract mismatch exists between the client and service, or the client’s credentials are rejected by the service.</span></span> <span data-ttu-id="6f3a5-111">Es gibt viele andere Fehlertypen in dieser Kategorie, die hier nicht alle aufgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="6f3a5-111">There are many different types of errors in this category, too many to list here.</span></span> <span data-ttu-id="6f3a5-112">An den Client werden Fehler dieses Typs unverändert zurückgegeben (es wird keine Transformation für die Ausnahmeobjekte ausgeführt).</span><span class="sxs-lookup"><span data-stu-id="6f3a5-112">Errors of this type are returned to the client as-is (no transformation is performed on the exception objects).</span></span>  
  
 <span data-ttu-id="6f3a5-113">Anwendungsfehler treten während der Ausführung eines Dienstvorgangs auf.</span><span class="sxs-lookup"><span data-stu-id="6f3a5-113">Application errors occur during the execution of a service operation.</span></span> <span data-ttu-id="6f3a5-114">Fehler dieser Art werden an den Client als <xref:System.ServiceModel.FaultException> oder <xref:System.ServiceModel.FaultException%601> gesendet.</span><span class="sxs-lookup"><span data-stu-id="6f3a5-114">Errors of this kind are sent to the client as <xref:System.ServiceModel.FaultException> or <xref:System.ServiceModel.FaultException%601>.</span></span>  
  
 <span data-ttu-id="6f3a5-115">Die Fehlerbehandlung in WCF wird durch einen oder mehrere der folgenden Schritte ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="6f3a5-115">Error handling in WCF is performed by one or more of the following:</span></span>  
  
- <span data-ttu-id="6f3a5-116">Direkte Behandlung der ausgelösten Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="6f3a5-116">Directly handling the exception thrown.</span></span> <span data-ttu-id="6f3a5-117">Dies erfolgt nur für Kommunikations- und Proxy-/Channelfehler.</span><span class="sxs-lookup"><span data-stu-id="6f3a5-117">This is only done for communication and proxy/channel errors.</span></span>  
  
- <span data-ttu-id="6f3a5-118">Verwenden von Fehlerverträgen</span><span class="sxs-lookup"><span data-stu-id="6f3a5-118">Using fault contracts</span></span>  
  
- <span data-ttu-id="6f3a5-119">Implementieren der <xref:System.ServiceModel.Dispatcher.IErrorHandler>-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f3a5-119">Implementing the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface</span></span>  
  
- <span data-ttu-id="6f3a5-120">Behandlung von <xref:System.ServiceModel.ServiceHost>-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="6f3a5-120">Handling <xref:System.ServiceModel.ServiceHost> events</span></span>  
  
## <a name="fault-contracts"></a><span data-ttu-id="6f3a5-121">Fehlerverträge</span><span class="sxs-lookup"><span data-stu-id="6f3a5-121">Fault Contracts</span></span>  

 <span data-ttu-id="6f3a5-122">Mithilfe von Fehlerverträgen können Sie die Fehler, die während eines Dienstvorgangs auftreten können, auf plattformunabhängige Weise definieren.</span><span class="sxs-lookup"><span data-stu-id="6f3a5-122">Fault contracts allow you to define the errors that can occur during service operation in a platform independent way.</span></span> <span data-ttu-id="6f3a5-123">Standardmäßig werden alle innerhalb eines Dienstvorgangs ausgelösten Ausnahmen an den Client als <xref:System.ServiceModel.FaultException>-Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6f3a5-123">By default all exceptions thrown from within a service operation will be returned to the client as a <xref:System.ServiceModel.FaultException> object.</span></span> <span data-ttu-id="6f3a5-124">Das <xref:System.ServiceModel.FaultException>-Objekt enthält sehr wenig Informationen.</span><span class="sxs-lookup"><span data-stu-id="6f3a5-124">The <xref:System.ServiceModel.FaultException> object will contain very little information.</span></span> <span data-ttu-id="6f3a5-125">Sie können die an den Client gesendeten Informationen durch Definieren eines Fehlervertrags und Zurückgeben des Fehlers als <xref:System.ServiceModel.FaultException%601> steuern.</span><span class="sxs-lookup"><span data-stu-id="6f3a5-125">You can control the information sent to the client by defining a fault contract and returning the error as a <xref:System.ServiceModel.FaultException%601>.</span></span> <span data-ttu-id="6f3a5-126">Weitere Informationen finden Sie unter [angeben und behandeln von Fehlern in Verträgen und Diensten](specifying-and-handling-faults-in-contracts-and-services.md).</span><span class="sxs-lookup"><span data-stu-id="6f3a5-126">For more information, see [Specifying and Handling Faults in Contracts and Services](specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
## <a name="ierrorhandler"></a><span data-ttu-id="6f3a5-127">IErrorHandler</span><span class="sxs-lookup"><span data-stu-id="6f3a5-127">IErrorHandler</span></span>  

 <span data-ttu-id="6f3a5-128">Die <xref:System.ServiceModel.Dispatcher.IErrorHandler>-Schnittstelle ermöglicht Ihnen mehr Kontrolle darüber, wie die WCF-Anwendung auf Fehler reagiert.</span><span class="sxs-lookup"><span data-stu-id="6f3a5-128">The <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface allows you more control over how your WCF application responds to errors.</span></span>  <span data-ttu-id="6f3a5-129">Sie gibt Ihnen volle Kontrolle über die Fehlermeldung, die an den Client zurückgegeben wird, und ermöglicht Ihnen, die benutzerdefinierte Fehlerverarbeitung auszuführen, z. B. die Protokollierung.</span><span class="sxs-lookup"><span data-stu-id="6f3a5-129">It gives you full control over the fault message that is returned to the client and allows you to perform custom error processing such as logging.</span></span>  <span data-ttu-id="6f3a5-130">Weitere Informationen zu <xref:System.ServiceModel.Dispatcher.IErrorHandler> und zur [Erweiterung der Kontrolle über Fehlerbehandlung und Bericht](./samples/extending-control-over-error-handling-and-reporting.md) Erstellung</span><span class="sxs-lookup"><span data-stu-id="6f3a5-130">For more information about <xref:System.ServiceModel.Dispatcher.IErrorHandler> and [Extending Control Over Error Handling and Reporting](./samples/extending-control-over-error-handling-and-reporting.md)</span></span>  
  
## <a name="servicehost-events"></a><span data-ttu-id="6f3a5-131">ServiceHost-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="6f3a5-131">ServiceHost Events</span></span>  

 <span data-ttu-id="6f3a5-132">Die <xref:System.ServiceModel.ServiceHost>-Klasse hostet Dienste und definiert mehrere Ereignisse, die möglicherweise zur Fehlerbehandlung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="6f3a5-132">The <xref:System.ServiceModel.ServiceHost> class hosts services and defines several events that may be needed for handling errors.</span></span> <span data-ttu-id="6f3a5-133">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6f3a5-133">For example:</span></span>  
  
1. <xref:System.ServiceModel.Channels.CommunicationObject.Faulted>
  
2. <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived>
  
 <span data-ttu-id="6f3a5-134">Weitere Informationen finden Sie unter <xref:System.ServiceModel.ServiceHost></span><span class="sxs-lookup"><span data-stu-id="6f3a5-134">For more information, see <xref:System.ServiceModel.ServiceHost></span></span>
