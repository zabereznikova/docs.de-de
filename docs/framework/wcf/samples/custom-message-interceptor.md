---
title: Benutzerdefinierter Nachrichteninterceptor
ms.date: 03/30/2017
ms.assetid: 73f20972-53f8-475a-8bfe-c133bfa225b0
ms.openlocfilehash: 61f9bae24f5edb70430f4f3eaa16e42da221a7b4
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978300"
---
# <a name="custom-message-interceptor"></a><span data-ttu-id="79948-102">Benutzerdefinierter Nachrichteninterceptor</span><span class="sxs-lookup"><span data-stu-id="79948-102">Custom Message Interceptor</span></span>
<span data-ttu-id="79948-103">In diesem Beispiel wird die Verwendung des Kanalerweiterbarkeitsmodells veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="79948-103">This sample demonstrates the use of the channel extensibility model.</span></span> <span data-ttu-id="79948-104">Es zeigt insbesondere, wie ein benutzerdefiniertes Bindungselement implementiert wird, das Kanalfactorys und Kanallistener erstellt, um sämtliche ein- und ausgehenden Nachrichten an einer bestimmten Stelle im Laufzeitstapel abzufangen.</span><span class="sxs-lookup"><span data-stu-id="79948-104">In particular, it shows how to implement a custom binding element that creates channel factories and channel listeners to intercept all incoming and outgoing messages at a particular point in the run-time stack.</span></span> <span data-ttu-id="79948-105">Im Beispiel sind auch ein Client und ein Server, die die Verwendung dieser benutzerdefinierten Factorys veranschaulichen, enthalten.</span><span class="sxs-lookup"><span data-stu-id="79948-105">The sample also includes a client and server that demonstrate the use of these custom factories.</span></span>  
  
 <span data-ttu-id="79948-106">In diesem Beispiel sind sowohl der Client als auch der Dienst Konsolenprogramme (.exe).</span><span class="sxs-lookup"><span data-stu-id="79948-106">In this sample, both the client and the service are console programs (.exe).</span></span> <span data-ttu-id="79948-107">Der Client und der Dienst verwenden beide eine allgemeine Bibliothek (.dll), die das benutzerdefinierte Bindungselement und zugewiesene Laufzeitobjekte enthält.</span><span class="sxs-lookup"><span data-stu-id="79948-107">The client and service both make use of a common library (.dll) that contains the custom binding element and its associated run-time objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="79948-108">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="79948-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="79948-109">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="79948-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="79948-110">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="79948-110">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="79948-111">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="79948-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="79948-112">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="79948-112">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\MessageInterceptor`  
  
 <span data-ttu-id="79948-113">Im Beispiel wird die empfohlene Vorgehensweise zum Erstellen eines benutzerdefinierten geschichteten Kanals in Windows Communication Foundation (WCF) mithilfe des Channel-Frameworks und der folgenden bewährten WCF-Methoden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="79948-113">The sample describes the recommended procedure for creating a custom layered channel in Windows Communication Foundation (WCF), by using the channel framework and following WCF best practices.</span></span> <span data-ttu-id="79948-114">Mit folgenden Schritten wird ein benutzerdefinierter geschichteter Kanal erstellt:</span><span class="sxs-lookup"><span data-stu-id="79948-114">The steps to create a custom layered channel are as follows:</span></span>  
  
1. <span data-ttu-id="79948-115">Legen Sie fest, welche Kanalform die Kanalfactory und der Kanallistener unterstützen sollen.</span><span class="sxs-lookup"><span data-stu-id="79948-115">Decide which of the channel shapes your channel factory and channel listener will support.</span></span>  
  
2. <span data-ttu-id="79948-116">Erstellen Sie eine Kanalfactory und einen Kanallistener, die Ihre Kanalformen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="79948-116">Create a channel factory and a channel listener that support your channel shapes.</span></span>  
  
3. <span data-ttu-id="79948-117">Fügen Sie ein Bindungselement hinzu, das den benutzerdefinierten geschichteten Kanal einem Kanalstapel hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="79948-117">Add a binding element that adds the custom layered channel to a channel stack.</span></span>  
  
4. <span data-ttu-id="79948-118">Fügen Sie einen Bindungselementerweiterungs-Abschnitt hinzu, um das neue Bindungselement für das Konfigurationssystem verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="79948-118">Add a binding element extension section to expose the new binding element to the configuration system.</span></span>  
  
## <a name="channel-shapes"></a><span data-ttu-id="79948-119">Kanalformen</span><span class="sxs-lookup"><span data-stu-id="79948-119">Channel Shapes</span></span>  
 <span data-ttu-id="79948-120">Der erste Schritt beim Schreiben eines benutzerdefinierten geschichteten Kanals besteht darin zu entscheiden, welche Formen für den Kanal erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="79948-120">The first step in writing a custom layered channel is to decide which shapes are required for the channel.</span></span> <span data-ttu-id="79948-121">Bei unserem Nachrichteninspektor wird jede Form unterstützt, die die Schicht unterhalb unterstützt (wenn die Schicht unterhalb beispielsweise <xref:System.ServiceModel.Channels.IOutputChannel> und <xref:System.ServiceModel.Channels.IDuplexSessionChannel> erstellen kann, werden ebenfalls <xref:System.ServiceModel.Channels.IOutputChannel> und <xref:System.ServiceModel.Channels.IDuplexSessionChannel> verfügbar gemacht).</span><span class="sxs-lookup"><span data-stu-id="79948-121">For our message inspector, we support any shape that the layer below us supports (for example, if the layer below us can build <xref:System.ServiceModel.Channels.IOutputChannel> and <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, then we also expose <xref:System.ServiceModel.Channels.IOutputChannel> and <xref:System.ServiceModel.Channels.IDuplexSessionChannel>).</span></span>  
  
## <a name="channel-factory-and-listener-factory"></a><span data-ttu-id="79948-122">Kanalfactory und Listenerfactory</span><span class="sxs-lookup"><span data-stu-id="79948-122">Channel Factory and Listener Factory</span></span>  
 <span data-ttu-id="79948-123">Der nächste Schritt beim Schreiben eines benutzerdefinierten geschichteten Kanals besteht im Erstellen einer Implementierung von <xref:System.ServiceModel.Channels.IChannelFactory> für Clientkanäle und von <xref:System.ServiceModel.Channels.IChannelListener> für Dienstkanäle.</span><span class="sxs-lookup"><span data-stu-id="79948-123">The next step in writing a custom layered channel is to create an implementation of <xref:System.ServiceModel.Channels.IChannelFactory> for client channels and of <xref:System.ServiceModel.Channels.IChannelListener> for service channels.</span></span>  
  
 <span data-ttu-id="79948-124">Diese Klassen nehmen eine innere Factory und einen inneren Listener und delegieren alle Aufrufe außer den `OnCreateChannel`- und `OnAcceptChannel`-Aufrufen an die innere Factory und den inneren Listener.</span><span class="sxs-lookup"><span data-stu-id="79948-124">These classes take an inner factory and listener, and delegate all but the `OnCreateChannel` and `OnAcceptChannel` calls to the inner factory and listener.</span></span>  
  
```csharp
class InterceptingChannelFactory<TChannel> : ChannelFactoryBase<TChannel>  
{ 
    //... 
}

class InterceptingChannelListener<TChannel> : ListenerFactoryBase<TChannel>  
{ 
    //...
}  
```  
  
## <a name="adding-a-binding-element"></a><span data-ttu-id="79948-125">Hinzufügen eines Bindungselements</span><span class="sxs-lookup"><span data-stu-id="79948-125">Adding a Binding Element</span></span>  
 <span data-ttu-id="79948-126">Das Beispiel definiert ein benutzerdefiniertes Bindungselement: `InterceptingBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="79948-126">The sample defines a custom binding element: `InterceptingBindingElement`.</span></span> <span data-ttu-id="79948-127">`InterceptingBindingElement` nimmt eine `ChannelMessageInterceptor` als Eingabe an und verwendet diese `ChannelMessageInterceptor` zum Bearbeiten von Nachrichten, die Sie durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="79948-127">`InterceptingBindingElement` takes a `ChannelMessageInterceptor` as an input, and uses this `ChannelMessageInterceptor` to manipulate messages that pass through it.</span></span> <span data-ttu-id="79948-128">Dies ist die einzige Klasse, die öffentlich sein muss.</span><span class="sxs-lookup"><span data-stu-id="79948-128">This is the only class that must be public.</span></span> <span data-ttu-id="79948-129">Die Factory, der Listener und die Kanäle können alle interne Implementierungen der öffentlichen Laufzeitschnittstellen sein.</span><span class="sxs-lookup"><span data-stu-id="79948-129">The factory, listener, and channels can all be internal implementations of the public run-time interfaces.</span></span>  
  
```csharp
public class InterceptingBindingElement : BindingElement
{
}
```  
  
## <a name="adding-configuration-support"></a><span data-ttu-id="79948-130">Hinzufügen von Konfigurationsunterstützung</span><span class="sxs-lookup"><span data-stu-id="79948-130">Adding Configuration Support</span></span>  
 <span data-ttu-id="79948-131">Die Bibliothek definiert einen Konfigurationsabschnittshandler als Bindungselementerweiterungs-Abschnitt, um die Bindungskonfiguration zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="79948-131">To integrate with binding configuration, the library defines a configuration section handler as a binding element extension section.</span></span> <span data-ttu-id="79948-132">Die Client- und Serverkonfigurationsdateien müssen die Bindungselementerweiterung auf dem Konfigurationssystem registrieren.</span><span class="sxs-lookup"><span data-stu-id="79948-132">The client and server configuration files must register the binding element extension with the configuration system.</span></span> <span data-ttu-id="79948-133">Implementierer, die ihr Bindungselement auf dem Konfigurationssystem verfügbar machen möchten, können von dieser Klasse ableiten.</span><span class="sxs-lookup"><span data-stu-id="79948-133">Implementers that want to expose their binding element to the configuration system can derive from this class.</span></span>  
  
```csharp
public abstract class InterceptingElement : BindingElementExtensionElement 
{ 
    //... 
}
```  
  
## <a name="adding-policy"></a><span data-ttu-id="79948-134">Hinzufügen einer Richtlinie</span><span class="sxs-lookup"><span data-stu-id="79948-134">Adding Policy</span></span>  
 <span data-ttu-id="79948-135">Zum Integrieren mit unserem Richtliniensystem implementiert `InterceptingBindingElement` IPolicyExportExtension, um die Teilnahme beim Generieren der Richtlinie zu signalisieren.</span><span class="sxs-lookup"><span data-stu-id="79948-135">To integrate with our policy system, `InterceptingBindingElement` implements IPolicyExportExtension to signal that we should participate in generating policy.</span></span> <span data-ttu-id="79948-136">Damit das Importieren einer Richtlinie auf einem generierten Client unterstützt wird, kann der Benutzer eine abgeleitete Klasse von `InterceptingBindingElementImporter` registrieren und `CreateMessageInterceptor`() überschreiben, um die richtlinienfähige `ChannelMessageInterceptor`-Klasse zu generieren.</span><span class="sxs-lookup"><span data-stu-id="79948-136">To support importing policy on a generated client, the user can register a derived class of `InterceptingBindingElementImporter` and override `CreateMessageInterceptor`() to generate their policy-enabled `ChannelMessageInterceptor` class.</span></span>  
  
## <a name="example-droppable-message-inspector"></a><span data-ttu-id="79948-137">Beispiel: Zu verwerfender Nachrichteninspektor</span><span class="sxs-lookup"><span data-stu-id="79948-137">Example: Droppable Message Inspector</span></span>  
 <span data-ttu-id="79948-138">Das Beispiel umfasst eine Beispielimplementierung von `ChannelMessageInspector`, der Meldungen verwirft.</span><span class="sxs-lookup"><span data-stu-id="79948-138">Included in the sample is an example implementation of `ChannelMessageInspector` which drops messages.</span></span>  
  
```csharp
class DroppingServerElement : InterceptingElement  
{  
    protected override ChannelMessageInterceptor CreateMessageInterceptor()  
    {  
        return new DroppingServerInterceptor();  
    }  
}  
```  
  
 <span data-ttu-id="79948-139">Sie rufen es wie folgt über die Konfiguration auf:</span><span class="sxs-lookup"><span data-stu-id="79948-139">You can access it from configuration as follows:</span></span>  
  
```xml  
<configuration>  
    ...  
    <system.serviceModel>  
        ...  
        <extensions>  
            <bindingElementExtensions>  
                <add name="droppingInterceptor"   
                   type=  
          "Microsoft.ServiceModel.Samples.DroppingServerElement, library"/>  
            </bindingElementExtensions>  
        </extensions>  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="79948-140">Sowohl der Client als auch der Server verwenden den neu erstellten Konfigurationsabschnitt, um die benutzerdefinierten Factorys in die unterste Schicht ihrer Laufzeit-Kanalstapel (über der Transportebene) einzufügen.</span><span class="sxs-lookup"><span data-stu-id="79948-140">The client and server both use this newly created configuration section to insert the custom factories into the lowest-level of their run-time channel stacks (above the transport level).</span></span>  
  
```xml  
<customBinding>  
  <binding name="sampleBinding">  
    <droppingInterceptor/>  
    <httpTransport/>  
  </binding>  
</customBinding>  
```  
  
 <span data-ttu-id="79948-141">Der Client verwendet die `MessageInterceptor`-Bibliothek, um einen benutzerdefinierten Header für Meldungen mit geraden Zahlen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="79948-141">The client uses the `MessageInterceptor` library to add a custom header to even numbered messages.</span></span> <span data-ttu-id="79948-142">Der Dienst hingegen verwendet die `MessageInterceptor`-Bibliothek, um alle Meldungen zu verwerfen, die diesen Header nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="79948-142">The service on the other hand uses `MessageInterceptor` library to drop any messages that do not have this special header.</span></span>  
  
 <span data-ttu-id="79948-143">Nach Ausführen des Diensts und anschließendem Ausführen des Clients sollte folgende Clientausgabe angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="79948-143">You should see the following client output after running the service and then the client.</span></span>  
  
```console  
Reporting the next 10 wind speed  
100 kph  
Server dropped a message.  
90 kph  
80 kph  
Server dropped a message.  
70 kph  
60 kph  
Server dropped a message.  
50 kph  
40 kph  
Server dropped a message.  
30 kph  
20 kph  
Server dropped a message.  
10 kph  
Press ENTER to shut down client  
```  
  
 <span data-ttu-id="79948-144">Der Client meldet 10 verschiedene Windgeschwindigkeiten an den Dienst, aber nur die Hälfte der Meldungen wird mit dem speziellen Header gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="79948-144">The client reports 10 different wind speeds to the service, but only tags half of them with the special header.</span></span>  
  
 <span data-ttu-id="79948-145">Auf dem Dienst sollten Sie die folgende Ausgabe erhalten:</span><span class="sxs-lookup"><span data-stu-id="79948-145">On the service, you should see the following output:</span></span>  
  
```console  
Press ENTER to exit.  
Dangerous wind detected! Reported speed (90) is greater than 64 kph.  
Dangerous wind detected! Reported speed (70) is greater than 64 kph.  
5 wind speed reports have been received.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="79948-146">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="79948-146">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="79948-147">Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="79948-147">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="79948-148">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="79948-148">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="79948-149">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="79948-149">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="79948-150">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="79948-150">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
5. <span data-ttu-id="79948-151">Führen Sie zuerst "Service.exe" und dann "Client.exe" aus, und sehen Sie sich die Ausgabe in beiden Konsolenfenstern an.</span><span class="sxs-lookup"><span data-stu-id="79948-151">Run Service.exe first then run Client.exe and watch both console windows for output.</span></span>  
