---
title: Benutzerdefinierter Nachrichtenfilter
ms.date: 03/30/2017
ms.assetid: 98dd0af8-fce6-4255-ac32-42eb547eea67
ms.openlocfilehash: 24dab723a06c128337c1d956a98a1aa85a258e33
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240926"
---
# <a name="custom-message-filter"></a><span data-ttu-id="95228-102">Benutzerdefinierter Nachrichtenfilter</span><span class="sxs-lookup"><span data-stu-id="95228-102">Custom Message Filter</span></span>

<span data-ttu-id="95228-103">In diesem Beispiel wird veranschaulicht, wie die Nachrichtenfilter ersetzt werden, die Windows Communication Foundation (WCF) verwendet, um Nachrichten an Endpunkte zu senden.</span><span class="sxs-lookup"><span data-stu-id="95228-103">This sample demonstrates how to replace the message filters that Windows Communication Foundation (WCF) uses to dispatch messages to endpoints.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="95228-104">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="95228-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="95228-105">Wenn die erste Nachricht auf einem Kanal beim Server eintrifft, muss der Server bestimmen, welcher der mit diesem URI verknüpften Endpunkte (sofern zutreffend) die Nachricht erhalten soll.</span><span class="sxs-lookup"><span data-stu-id="95228-105">When the first message on a channel arrives at the server, the server must determine which (if any) of the endpoints associated with that URI should receive the message.</span></span> <span data-ttu-id="95228-106">Dieser Prozess wird von den an den <xref:System.ServiceModel.Dispatcher.MessageFilter> angefügten <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>-Objekten kontrolliert.</span><span class="sxs-lookup"><span data-stu-id="95228-106">This process is controlled by the <xref:System.ServiceModel.Dispatcher.MessageFilter> objects attached to the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span></span>  
  
 <span data-ttu-id="95228-107">Jeder Endpunkt eines Diensts hat einen einzelnen <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span><span class="sxs-lookup"><span data-stu-id="95228-107">Each endpoint of a service has a single <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span></span> <span data-ttu-id="95228-108">Der <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> besitzt sowohl einen <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> als auch einen <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>.</span><span class="sxs-lookup"><span data-stu-id="95228-108">The <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> has both an <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> and a <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>.</span></span> <span data-ttu-id="95228-109">Die Verbindung dieser beiden Filter ist der für diesen Endpunkt verwendete Nachrichtenfilter.</span><span class="sxs-lookup"><span data-stu-id="95228-109">The union of these two filters is the message filter used for that endpoint.</span></span>  
  
 <span data-ttu-id="95228-110">Standardmäßig stimmt der <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> für einen Endpunkt mit jeder Nachricht überein, die an eine Adresse gesendet wird, die wiederum mit der <xref:System.ServiceModel.EndpointAddress> des Dienstendpunkts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="95228-110">By default, the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> for an endpoint matches any message that is addressed to an address that matches the service endpoint's <xref:System.ServiceModel.EndpointAddress>.</span></span> <span data-ttu-id="95228-111">Standardmäßig überprüft der <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> für einen Endpunkt die Aktion der eingehenden Nachricht und gleicht jede Nachricht mit einer Aktion ab, die einer der Aktionen der Vorgänge des Dienst Endpunkt Vertrags entspricht (nur `IsInitiating` = `true` Aktionen werden berücksichtigt).</span><span class="sxs-lookup"><span data-stu-id="95228-111">By default, the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> for an endpoint inspects the action of the incoming message and matches any message with an action that corresponds to one of the actions of the service endpoint contract's operations (only `IsInitiating`=`true` actions are considered).</span></span> <span data-ttu-id="95228-112">Demzufolge stimmt der Filter für einen Endpunkt standardmäßig nur überein, wenn sowohl der To-Header der Nachricht die <xref:System.ServiceModel.EndpointAddress> des Endpunkts ist als auch die Aktion der Nachricht mit einer der Aktionen der Endpunktvorgänge übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="95228-112">As a result, by default, the filter for an endpoint only matches if both the message's To header is the <xref:System.ServiceModel.EndpointAddress> of the endpoint and the message's action matches one of the endpoint operation's actions.</span></span>  
  
 <span data-ttu-id="95228-113">Diese Filter können mit einer Verhaltensweise geändert werden.</span><span class="sxs-lookup"><span data-stu-id="95228-113">These filters can be changed using a behavior.</span></span> <span data-ttu-id="95228-114">Im folgenden Beispiel erstellt der Dienst ein <xref:System.ServiceModel.Description.IEndpointBehavior>, das den <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> und den <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> auf dem <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> ersetzt:</span><span class="sxs-lookup"><span data-stu-id="95228-114">In the sample, the service creates an <xref:System.ServiceModel.Description.IEndpointBehavior> that replaces the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> and <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> on the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>:</span></span>  
  
```csharp
class FilteringEndpointBehavior : IEndpointBehavior
{
    //...
}
```  
  
 <span data-ttu-id="95228-115">Es werden zwei Adressfilter definiert:</span><span class="sxs-lookup"><span data-stu-id="95228-115">Two address filters are defined:</span></span>  
  
```csharp
// Matches any message whose To address contains the letter 'e'  
class MatchEAddressFilter : MessageFilter { }
// Matches any message whose To address does not contain the letter 'e'  
class MatchNoEAddressFilter : MessageFilter { }  
```  
  
 <span data-ttu-id="95228-116">Das `FilteringEndpointBehavior` wird konfigurierbar gemacht und ermöglicht zwei verschiedene Varianten.</span><span class="sxs-lookup"><span data-stu-id="95228-116">The `FilteringEndpointBehavior` is made configurable and allows for two different variations.</span></span>  
  
```csharp
public class FilteringEndpointBehaviorExtension : BehaviorExtensionElement { }
```  
  
 <span data-ttu-id="95228-117">Variante&#160;1 gleicht nur Adressen ab, die ein "e" (aber eine beliebige Aktion) enthalten, wohingegen Variante&#160;2 nur die Adressen ohne "e" abgleicht:</span><span class="sxs-lookup"><span data-stu-id="95228-117">Variation 1 matches only addresses that contain an 'e' (but that have any Action) whereas Variation 2 matches only addresses that lack an 'e':</span></span>  
  
```csharp
if (Variation == 1)  
    return new FilteringEndpointBehavior(  
        new MatchEAddressFilter(), new MatchAllMessageFilter());  
else  
    return new FilteringEndpointBehavior(  
        new MatchNoEAddressFilter(), new MatchAllMessageFilter());  
```  
  
 <span data-ttu-id="95228-118">Der Dienst registriert das neue Verhalten in der Konfigurationsdatei:</span><span class="sxs-lookup"><span data-stu-id="95228-118">In the configuration file, the service registers the new behavior:</span></span>  
  
```xml  
<extensions>  
    <behaviorExtensions>  
        <add name="filteringEndpointBehavior" type="Microsoft.ServiceModel.Samples.FilteringEndpointBehaviorExtension, service" />  
    </behaviorExtensions>  
</extensions>
```  
  
 <span data-ttu-id="95228-119">Anschließend erstellt der Dienst `endpointBehavior`-Konfigurationen für jede Variante:</span><span class="sxs-lookup"><span data-stu-id="95228-119">Then the service creates `endpointBehavior` configurations for each variation:</span></span>  
  
```xml  
<endpointBehaviors>  
    <behavior name="endpoint1">  
        <filteringEndpointBehavior variation="1" />  
    </behavior>  
    <behavior name="endpoint2">  
        <filteringEndpointBehavior variation="2" />  
    </behavior>  
</endpointBehaviors>  
```  
  
 <span data-ttu-id="95228-120">Schließlich verweist der Endpunkt des Diensts auf eine der `behaviorConfigurations`:</span><span class="sxs-lookup"><span data-stu-id="95228-120">Finally, the service's endpoint references one of the `behaviorConfigurations`:</span></span>  
  
```xml  
<endpoint address=""  
        bindingConfiguration="ws"  
        listenUri=""
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.IHello"
        behaviorConfiguration="endpoint2" />  
```  
  
 <span data-ttu-id="95228-121">Die Implementierung der Clientanwendung ist einfach. Sie erstellt zwei Kanäle zum URI des Diensts (indem der Wert als der zweite (`via`)-Parameter an <xref:System.ServiceModel.Channels.IChannelFactory%601.CreateChannel%28System.ServiceModel.EndpointAddress%29> übergeben wird) und sendet eine einzelne Nachricht auf jedem Kanal, verwendet aber jeweils verschiedene Endpunktadressen.</span><span class="sxs-lookup"><span data-stu-id="95228-121">The implementation of the client application is straightforward; it creates two channels to the service's URI (by passing in that value as the second (`via`) parameter to <xref:System.ServiceModel.Channels.IChannelFactory%601.CreateChannel%28System.ServiceModel.EndpointAddress%29> and sends a single message on each channel, but it uses different endpoint addresses for each.</span></span> <span data-ttu-id="95228-122">Infolgedessen besitzen die vom Client ausgehenden Nachrichten unterschiedliche To-Ziele, und der Server antwortet entsprechend, wie von der Ausgabe des Clients veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="95228-122">As a result, the outbound messages from the client have different To designations, and the server responds accordingly, as demonstrated by the client's output:</span></span>  
  
```console  
Sending message to urn:e...  
Exception: The message with To 'urn:e' cannot be processed at the receiver, due to an AddressFilter mismatch at the EndpointDispatcher.  Check that the sender and receiver's EndpointAddresses agree.  
  
Sending message to urn:a...  
Hello  
```  
  
 <span data-ttu-id="95228-123">Durch einen Wechsel der Variante in der Konfigurationsdatei des Servers wird der Filter getauscht, und der Client sieht das andere Verhalten (die Nachricht an `urn:e` ist erfolgreich, die Nachricht an `urn:a` jedoch nicht).</span><span class="sxs-lookup"><span data-stu-id="95228-123">Switching the variation in the server's configuration file causes the filter to be swapped and the client sees the opposite behavior (the message to `urn:e` succeeds, whereas the message to `urn:a` fails).</span></span>  
  
```xml  
<endpoint address=""  
          bindingConfiguration="ws"  
          listenUri=""
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.IHello"
          behaviorConfiguration="endpoint1" />  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="95228-124">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="95228-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="95228-125">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="95228-125">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="95228-126">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="95228-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="95228-127">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="95228-127">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageFilter`  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="95228-128">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="95228-128">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="95228-129">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="95228-129">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="95228-130">Um das Beispiel in einer Konfiguration mit einem einzelnen Computer auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="95228-130">To run the sample in a single-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
3. <span data-ttu-id="95228-131">Um das Beispiel in einer Computer übergreifenden Konfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md) , und ändern Sie die folgende Zeile in Client.cs.</span><span class="sxs-lookup"><span data-stu-id="95228-131">To run the sample in a cross-machine configuration, follow the instructions at [Running the Windows Communication Foundation Samples](running-the-samples.md) and change the following line in Client.cs.</span></span>  
  
    ```csharp
    Uri serviceVia = new Uri("http://localhost/ServiceModelSamples/service.svc");  
    ```  
  
     <span data-ttu-id="95228-132">Ersetzen Sie "localhost" mit dem Namen des Servers.</span><span class="sxs-lookup"><span data-stu-id="95228-132">Replace localhost with the name of server.</span></span>  
  
    ```csharp
    Uri serviceVia = new Uri("http://servermachinename/ServiceModelSamples/service.svc");  
    ```  
