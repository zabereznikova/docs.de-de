---
title: HttpCookieSession
ms.date: 03/30/2017
ms.assetid: 101cb624-8303-448a-a3af-933247c1e109
ms.openlocfilehash: df29ae84537cdb7cea40abcdb848ffbb8bbd6b9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253816"
---
# <a name="httpcookiesession"></a><span data-ttu-id="6f3d4-102">HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="6f3d4-102">HttpCookieSession</span></span>

<span data-ttu-id="6f3d4-103">In diesem Beispiel wird das Erstellen eines benutzerdefinierten Protokollkanals für die Verwendung von HTTP-Cookies für die Sitzungsverwaltung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-103">This sample demonstrates how to build a custom protocol channel to use HTTP cookies for session management.</span></span> <span data-ttu-id="6f3d4-104">Dieser Kanal ermöglicht die Kommunikation zwischen Windows Communication Foundation (WCF)-Diensten und ASMX-Clients oder zwischen WCF-Clients und ASMX-Diensten.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-104">This channel enables communication between Windows Communication Foundation (WCF) services and ASMX clients or between WCF clients and ASMX services.</span></span>  
  
 <span data-ttu-id="6f3d4-105">Wenn ein Client eine Webmethode in einem Sitzungs basierten ASMX-Webdienst aufruft, bewirkt die ASP.net-Engine Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6f3d4-105">When a client calls a Web method in an ASMX Web service that is session-based, the ASP.NET engine does the following:</span></span>  
  
- <span data-ttu-id="6f3d4-106">Generiert eine eindeutige ID (Sitzungs-ID).</span><span class="sxs-lookup"><span data-stu-id="6f3d4-106">Generates a unique ID (session ID).</span></span>  
  
- <span data-ttu-id="6f3d4-107">Generiert das Sitzungsobjekt und ordnet es der eindeutigen ID zu.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-107">Generates the session object and associates it with the unique ID.</span></span>  
  
- <span data-ttu-id="6f3d4-108">Fügt die eindeutige ID dem HTTP-Antwortheader Set-Cookie hinzu und sendet diesen an den Client.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-108">Adds the unique ID to a Set-Cookie HTTP response header and sends it to the client.</span></span>  
  
- <span data-ttu-id="6f3d4-109">Identifiziert den Client in nachfolgenden Aufrufen auf Grundlage der an ihn gesendeten Sitzungs-ID.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-109">Identifies the client on subsequent calls based on the session ID it sends to it.</span></span>  
  
 <span data-ttu-id="6f3d4-110">Der Client schließt diese Sitzungs-ID in nachfolgenden Anforderungen an den Server ein.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-110">The client includes this session ID in its subsequent requests to the server.</span></span> <span data-ttu-id="6f3d4-111">Der Server lädt mithilfe der Sitzungs-ID vom Client das entsprechende Sitzungsobjekt für den aktuellen HTTP-Kontext.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-111">The server uses the session ID from the client to load the appropriate session object for the current HTTP context.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6f3d4-112">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6f3d4-113">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-113">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="6f3d4-114">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6f3d4-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6f3d4-115">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-115">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\HttpCookieSession`  
  
## <a name="httpcookiesession-channel-message-exchange-pattern"></a><span data-ttu-id="6f3d4-116">HttpCookieSession-Nachrichtenaustauschmuster für Kanal</span><span class="sxs-lookup"><span data-stu-id="6f3d4-116">HttpCookieSession Channel Message Exchange Pattern</span></span>  

 <span data-ttu-id="6f3d4-117">In diesem Beispiel werden Sitzungen für ASMX-ähnliche Szenarios aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-117">This sample enables sessions for ASMX-like scenarios.</span></span> <span data-ttu-id="6f3d4-118">Unten im Kanalstapel befindet sich der HTTP-Transport, der <xref:System.ServiceModel.Channels.IRequestChannel> und <xref:System.ServiceModel.Channels.IReplyChannel> unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-118">At the bottom of our channel stack, we have the HTTP transport that supports <xref:System.ServiceModel.Channels.IRequestChannel> and <xref:System.ServiceModel.Channels.IReplyChannel>.</span></span> <span data-ttu-id="6f3d4-119">Der Kanal stellt Sitzungen für die höheren Ebenen des Kanalstapels bereit.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-119">It is the job of the channel to provide sessions to the higher levels of the channel stack.</span></span> <span data-ttu-id="6f3d4-120">Im Beispiel werden zwei Kanäle implementiert, die Sitzungen unterstützen (<xref:System.ServiceModel.Channels.IRequestSessionChannel> und <xref:System.ServiceModel.Channels.IReplySessionChannel>).</span><span class="sxs-lookup"><span data-stu-id="6f3d4-120">The sample implements two channels, (<xref:System.ServiceModel.Channels.IRequestSessionChannel> and <xref:System.ServiceModel.Channels.IReplySessionChannel>) that support sessions.</span></span>  
  
## <a name="service-channel"></a><span data-ttu-id="6f3d4-121">Dienstkanal</span><span class="sxs-lookup"><span data-stu-id="6f3d4-121">Service Channel</span></span>  

 <span data-ttu-id="6f3d4-122">Im Beispiel wird ein Dienstkanal in der `HttpCookieReplySessionChannelListener`-Klasse bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-122">The sample provides a service channel in the `HttpCookieReplySessionChannelListener` class.</span></span> <span data-ttu-id="6f3d4-123">Diese Klasse implementiert die <xref:System.ServiceModel.Channels.IChannelListener>-Schnittstelle und konvertiert den <xref:System.ServiceModel.Channels.IReplyChannel>-Kanal weiter unten im Kanalstapel in <xref:System.ServiceModel.Channels.IReplySessionChannel>.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-123">This class implements the <xref:System.ServiceModel.Channels.IChannelListener> interface and converts the <xref:System.ServiceModel.Channels.IReplyChannel> channel from lower in the channel stack to a <xref:System.ServiceModel.Channels.IReplySessionChannel>.</span></span> <span data-ttu-id="6f3d4-124">Dieser Prozess kann folgendermaßen unterteilt werden:</span><span class="sxs-lookup"><span data-stu-id="6f3d4-124">This process can be divided into the following parts:</span></span>  
  
- <span data-ttu-id="6f3d4-125">Wenn der Kanallistener geöffnet wird, akzeptiert er einen inneren Kanal vom inneren Listener.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-125">When the channel listener is opened, it accepts an inner channel from its inner listener.</span></span> <span data-ttu-id="6f3d4-126">Da es sich bei dem inneren Listener um einen Datagrammlistener handelt und die Lebensdauer eines akzeptierten Kanals unabhängig von der Lebensdauer des Listeners ist, kann der innere Listener geschlossen und nur der innere Kanal beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-126">Because the inner listener is a datagram listener and the lifetime of an accepted channel is decoupled from the lifetime of the listener, we can close the inner listener and only hold on to the inner channel</span></span>  
  
    ```csharp  
                this.innerChannelListener.Open(timeoutHelper.RemainingTime());  
    this.innerChannel = this.innerChannelListener.AcceptChannel(timeoutHelper.RemainingTime());  
    this.innerChannel.Open(timeoutHelper.RemainingTime());  
    this.innerChannelListener.Close(timeoutHelper.RemainingTime());  
    ```  
  
- <span data-ttu-id="6f3d4-127">Wenn der Prozess zum Öffnen abgeschlossen ist, wird eine Nachrichtenschleife zum Empfangen von Nachrichten vom inneren Kanal eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-127">When the open process completes, we set up a message loop to receive messages from the inner channel.</span></span>  
  
    ```csharp  
    IAsyncResult result = BeginInnerReceiveRequest();  
    if (result != null && result.CompletedSynchronously)  
    {  
       // do not block the user thread  
       this.completeReceiveCallback ??= new WaitCallback(CompleteReceiveCallback);
       ThreadPool.QueueUserWorkItem(this.completeReceiveCallback, result);  
    }  
    ```  
  
- <span data-ttu-id="6f3d4-128">Wenn eine Nachricht eingeht, prüft der Dienstkanal die Sitzungs-ID und führt ein De-Multiplexing für den entsprechenden Sitzungskanal durch.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-128">When a message arrives, the service channel examines the session identifier and de-multiplexes to the appropriate session channel.</span></span> <span data-ttu-id="6f3d4-129">Der Kanallistener verwaltet ein Wörterbuch, das die Sitzungs-IDs den Sitzungskanalinstanzen zuordnet.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-129">The channel listener maintains a dictionary that maps the session identifiers to the session channel instances.</span></span>  
  
    ```csharp  
    Dictionary<string, IReplySessionChannel> channelMapping;  
    ```  
  
 <span data-ttu-id="6f3d4-130">Die- `HttpCookieReplySessionChannel` Klasse implementiert <xref:System.ServiceModel.Channels.IReplySessionChannel> .</span><span class="sxs-lookup"><span data-stu-id="6f3d4-130">The `HttpCookieReplySessionChannel` class implements <xref:System.ServiceModel.Channels.IReplySessionChannel>.</span></span> <span data-ttu-id="6f3d4-131">In höheren Ebenen des Kanalstapels wird die <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A>-Methode aufgerufen, um Anforderungen für diese Sitzung zu lesen.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-131">Higher levels of the channel stack call the <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> method to read requests for this session.</span></span> <span data-ttu-id="6f3d4-132">Jeder Sitzungskanal verfügt über eine private Meldungswarteschlange, die vom Dienstkanal aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-132">Each session channel has a private message queue that is populated by the service channel.</span></span>  
  
```csharp  
InputQueue<RequestContext> requestQueue;  
```  
  
 <span data-ttu-id="6f3d4-133">Wenn die <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A>-Methode aufgerufen wird und sich keine Meldungen in der Meldungswarteschlange befinden, wartet der Kanal für einen angegebenen Zeitraum und beendet sich dann selbst.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-133">In the case when someone calls the <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> method and there are no messages in the message queue, the channel waits for a specified amount of time before shutting itself down.</span></span> <span data-ttu-id="6f3d4-134">Dadurch werden die Sitzungskanäle bereinigt, die für nicht-WCF-Clients erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-134">This cleans up the session channels created for non-WCF clients.</span></span>  
  
 <span data-ttu-id="6f3d4-135">Mit `channelMapping` wird `ReplySessionChannels` nachverfolgt. Außerdem wird der zugrunde liegende `innerChannel` erst geschlossen, wenn alle akzeptierten Kanäle geschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-135">We use the `channelMapping` to track the `ReplySessionChannels`, and we do not close our underlying `innerChannel` until all the accepted channels have been closed.</span></span> <span data-ttu-id="6f3d4-136">So kann `HttpCookieReplySessionChannel` über die Lebensdauer von `HttpCookieReplySessionChannelListener` hinaus vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-136">This way `HttpCookieReplySessionChannel` can exist beyond the lifetime of `HttpCookieReplySessionChannelListener`.</span></span> <span data-ttu-id="6f3d4-137">Außerdem besteht nicht die Gefahr, dass der Listener durch die Garbage Collection entfernt wird, da die akzeptierten Kanäle über den `OnClosed`-Rückruf einen Verweis auf den Listener beibehalten.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-137">We also do not have to worry about the listener getting garbage collected underneath us because the accepted channels keep a reference to their listener through the `OnClosed` callback.</span></span>  
  
## <a name="client-channel"></a><span data-ttu-id="6f3d4-138">Clientkanal</span><span class="sxs-lookup"><span data-stu-id="6f3d4-138">Client channel</span></span>  

 <span data-ttu-id="6f3d4-139">Der entsprechende Clientkanal befindet sich in der `HttpCookieSessionChannelFactory`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-139">The corresponding client channel is in the `HttpCookieSessionChannelFactory` class.</span></span> <span data-ttu-id="6f3d4-140">Bei der Kanalerstellung schließt die Kanalfactory den inneren Anforderungskanal mit einem `HttpCookieRequestSessionChannel` ein.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-140">During channel creation, the channel factory wraps the inner request channel with an `HttpCookieRequestSessionChannel`.</span></span> <span data-ttu-id="6f3d4-141">Die `HttpCookieRequestSessionChannel`-Klasse leitet die Aufrufe des zugrunde liegenden Anforderungskanals weiter.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-141">The `HttpCookieRequestSessionChannel` class forwards the calls to the underlying request channel.</span></span> <span data-ttu-id="6f3d4-142">Wenn der Client den Proxy schließt, sendet `HttpCookieRequestSessionChannel` eine Meldung an den Dienst, mit der angegeben wird, dass der Kanal geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-142">When the client closes the proxy, `HttpCookieRequestSessionChannel` sends a message to the service that indicates that the channel is being closed.</span></span> <span data-ttu-id="6f3d4-143">So kann der Dienstkanalstapel den verwendeten Sitzungskanal ordnungsgemäß beenden.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-143">Thus, the service channel stack can gracefully shutdown the session channel that is in use.</span></span>  
  
## <a name="binding-and-binding-element"></a><span data-ttu-id="6f3d4-144">Bindung und Bindungselement</span><span class="sxs-lookup"><span data-stu-id="6f3d4-144">Binding and Binding Element</span></span>  

 <span data-ttu-id="6f3d4-145">Nachdem Sie den Dienst und die Client Kanäle erstellt haben, besteht der nächste Schritt darin, Sie in die WCF-Laufzeit zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-145">After creating the service and client channels, the next step is to integrate them into the WCF runtime.</span></span> <span data-ttu-id="6f3d4-146">Kanäle werden über Bindungen und Bindungs Elemente für WCF verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-146">Channels are exposed to WCF through bindings and binding elements.</span></span> <span data-ttu-id="6f3d4-147">Eine Bindung besteht aus einem oder mehreren Bindungselementen.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-147">A binding consists of one or many binding elements.</span></span> <span data-ttu-id="6f3d4-148">WCF bietet mehrere System definierte Bindungen. beispielsweise BasicHttpBinding oder WSHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-148">WCF offers several system-defined bindings; for example, BasicHttpBinding or WSHttpBinding.</span></span> <span data-ttu-id="6f3d4-149">Die `HttpCookieSessionBindingElement`-Klasse enthält die Implementierung des Bindungselements.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-149">The `HttpCookieSessionBindingElement` class contains the implementation for the binding element.</span></span> <span data-ttu-id="6f3d4-150">Sie überschreibt die Methoden zur Kanallistener- und Kanalfactoryerstellung, um die erforderlichen Instanziierungen des Kanallisteners und der Kanalfactory auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-150">It overrides the channel listener and channel factory creation methods to do the necessary channel listener or channel factory instantiations.</span></span>  
  
 <span data-ttu-id="6f3d4-151">Im Beispiel werden Richtlinienassertionen für die Dienstbeschreibung verwendet.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-151">The sample uses policy assertions for the service description.</span></span> <span data-ttu-id="6f3d4-152">So können im Beispiel die Kanalanforderungen für andere Clients veröffentlicht werden, die den Dienst verwenden können.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-152">This allows the sample to publish its channel requirements to other clients that can consume the service.</span></span> <span data-ttu-id="6f3d4-153">Dieses Bindungselement veröffentlicht beispielsweise Richtlinienassertionen, damit potenzielle Clients wissen, dass Sitzungen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-153">For example, this binding element publishes policy assertions to let potential clients know that it supports sessions.</span></span> <span data-ttu-id="6f3d4-154">Da im Beispiel die `ExchangeTerminateMessage`-Eigenschaft in der Bindungselementkonfiguration aktiviert wird, werden die erforderlichen Assertionen hinzugefügt, um zu zeigen, dass der Dienst eine zusätzliche Meldungsaustauschaktion zum Beenden der Sitzungskommunikation unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-154">Because the sample enables the `ExchangeTerminateMessage` property in the binding element configuration, it adds the necessary assertions to show that the service supports an extra message exchange action to terminate the session conversation.</span></span> <span data-ttu-id="6f3d4-155">Clients können diese Aktion dann verwenden.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-155">Clients can then use this action.</span></span> <span data-ttu-id="6f3d4-156">Im folgenden WSDL-Code werden die aus `HttpCookieSessionBindingElement` erstellten Richtlinienassertionen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-156">The following WSDL code shows the policy assertions created from the `HttpCookieSessionBindingElement`.</span></span>  
  
```xml  
<wsp:Policy wsu:Id="HttpCookieSessionBinding_IWcfCookieSessionService_policy" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
<wsp:ExactlyOne>  
<wsp:All>  
<wspe:Utf816FFFECharacterEncoding xmlns:wspe="http://schemas.xmlsoap.org/ws/2004/09/policy/encoding"/>  
<mhsc:httpSessionCookie xmlns:mhsc="http://samples.microsoft.com/wcf/mhsc/policy"/>  
</wsp:All>  
</wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="6f3d4-157">Die `HttpCookieSessionBinding`-Klasse ist eine vom System bereitgestellte Bindung, die das zuvor beschriebene Bindungselement verwendet.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-157">The `HttpCookieSessionBinding` class is a system-provided binding that uses the binding element described previously.</span></span>  
  
## <a name="adding-the-channel-to-the-configuration-system"></a><span data-ttu-id="6f3d4-158">Hinzufügen des Kanals zum Konfigurationssystem</span><span class="sxs-lookup"><span data-stu-id="6f3d4-158">Adding the Channel to the Configuration System</span></span>  

 <span data-ttu-id="6f3d4-159">Im Beispiel werden zwei Klassen bereitgestellt, die den Beispielkanal durch Konfiguration verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-159">The sample provides two classes that expose the sample channel through configuration.</span></span> <span data-ttu-id="6f3d4-160">Die erste ist ein <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> für das `HttpCookieSessionBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-160">The first is a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> for the `HttpCookieSessionBindingElement`.</span></span> <span data-ttu-id="6f3d4-161">Dem `HttpCookieSessionBindingConfigurationElement`, das sich von <xref:System.ServiceModel.Configuration.StandardBindingElement> herleitet, wird der Großteil der Implementierung übertragen.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-161">The bulk of the implementation is delegated to the `HttpCookieSessionBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="6f3d4-162">`HttpCookieSessionBindingConfigurationElement` verfügt über Eigenschaften, die den Eigenschaften von `HttpCookieSessionBindingElement` entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-162">The `HttpCookieSessionBindingConfigurationElement` has properties that correspond to the properties on `HttpCookieSessionBindingElement`.</span></span>  
  
### <a name="binding-element-extension-section"></a><span data-ttu-id="6f3d4-163">Abschnitt für Bindungselementerweiterungen</span><span class="sxs-lookup"><span data-stu-id="6f3d4-163">Binding Element Extension Section</span></span>  

 <span data-ttu-id="6f3d4-164">Der Abschnitt `HttpCookieSessionBindingElementSection` ist ein <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>, das die `HttpCookieSessionBindingElement` für das Konfigurationssystem verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-164">The section `HttpCookieSessionBindingElementSection` is a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> that exposes `HttpCookieSessionBindingElement` to the configuration system.</span></span> <span data-ttu-id="6f3d4-165">Mit wenigen Überschreibungen werden der Konfigurationsabschnittsname, der Typ des Bindungselements und das Erstellen des Bindungselements definiert.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-165">With a few overrides the configuration section name, the type of the binding element and how to create the binding element are defined.</span></span> <span data-ttu-id="6f3d4-166">Danach kann der Erweiterungsabschnitt wie folgt in einer Konfigurationsdatei registriert werden:</span><span class="sxs-lookup"><span data-stu-id="6f3d4-166">We can then register the extension section in a configuration file as follows:</span></span>  
  
```xml  
<configuration>
    <system.serviceModel>
      <extensions>
        <bindingElementExtensions>
          <add name="httpCookieSession"
               type=  
"Microsoft.ServiceModel.Samples.HttpCookieSessionBindingElementElement,
                    HttpCookieSessionExtension, Version=1.0.0.0,
                    Culture=neutral, PublicKeyToken=null"/>  
        </bindingElementExtensions >  
      </extensions>  
  
      <bindings>  
      <customBinding>  
        <binding name="allowCookiesBinding">  
          <textMessageEncoding messageVersion="Soap11WSAddressing10" />  
          <httpCookieSession sessionTimeout="10" exchangeTerminateMessage="true" />  
          <httpTransport allowCookies="true" />  
        </binding>  
      </customBinding>  
      </bindings>
    </system.serviceModel>
</configuration>  
```  
  
## <a name="test-code"></a><span data-ttu-id="6f3d4-167">Testcode</span><span class="sxs-lookup"><span data-stu-id="6f3d4-167">Test Code</span></span>  

 <span data-ttu-id="6f3d4-168">Testcode für die Verwendung dieses Beispieltransports ist in den Client- und Dienstverzeichnissen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-168">Test code for using this sample transport is available in the Client and Service directories.</span></span> <span data-ttu-id="6f3d4-169">Sie besteht aus zwei Tests – bei einem Test wird eine Bindung verwendet `allowCookies` , bei `true` der auf dem Client auf festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-169">It consists of two tests—one test uses a binding with `allowCookies` set to `true` on the client.</span></span> <span data-ttu-id="6f3d4-170">Im zweiten Test wird das explizite Herunterfahren (mit abschließenden Meldungsaustausch) für die Bindung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-170">The second test enables explicit shutdown (using the terminate message exchange) on the binding.</span></span>  
  
 <span data-ttu-id="6f3d4-171">Wenn Sie das Beispiel ausführen, sollten Sie folgende Ausgabe erhalten:</span><span class="sxs-lookup"><span data-stu-id="6f3d4-171">When you run the sample, you should see the following output:</span></span>  
  
```console  
Simple binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
Smart binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6f3d4-172">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="6f3d4-172">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="6f3d4-173">Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-173">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="6f3d4-174">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-174">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="6f3d4-175">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6f3d4-175">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="6f3d4-176">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6f3d4-176">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
