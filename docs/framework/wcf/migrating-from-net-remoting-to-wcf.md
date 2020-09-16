---
title: Migrieren von .NET-Remoting zu WCF
description: Erfahren Sie, wie Sie eine Anwendung migrieren, die .NET Remoting verwendet, um WCF zu verwenden. Sie können mehrere gängige Remotingszenarios in WCF ausführen.
ms.date: 03/30/2017
ms.assetid: 16902a42-ef80-40e9-8c4c-90e61ddfdfe5
ms.openlocfilehash: 73bdac5d8f4d39694f038bb600828c79e527efb0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90542849"
---
# <a name="migrating-from-net-remoting-to-wcf"></a><span data-ttu-id="da2f9-104">Migrieren von .NET-Remoting zu WCF</span><span class="sxs-lookup"><span data-stu-id="da2f9-104">Migrating from .NET Remoting to WCF</span></span>
<span data-ttu-id="da2f9-105">Dieser Artikel beschreibt die Vorgehensweise zum Migrieren einer Anwendung, die .NET Remoting zur Verwendung von Windows Communication Foundation (WCF) nutzt.</span><span class="sxs-lookup"><span data-stu-id="da2f9-105">This article describes how to migrate an application that uses .NET Remoting to use Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="da2f9-106">Es werden ähnliche Konzepte dieser zwei Produkte verglichen, und es wird beschrieben, wie verschiedene Remoting-Szenarien in WCF realisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="da2f9-106">It compares similar concepts between these products and then describes how to accomplish several common Remoting scenarios in WCF.</span></span>  
  
 <span data-ttu-id="da2f9-107">.NET Remoting ist ein Legacy-Produkt, das nur zur Bereitstellung von Abwärtskompatibilität unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="da2f9-107">.NET Remoting is a legacy product that is supported only for backward compatibility.</span></span> <span data-ttu-id="da2f9-108">Seine Verwendung in Umgebungen mit gemischten Vertrauensstellungen ist nicht sicher, da keine getrennten Vertrauensebenen zwischen Client und Server eingerichtet werden können.</span><span class="sxs-lookup"><span data-stu-id="da2f9-108">It is not secure across mixed-trust environments because it cannot maintain the separate trust levels between client and server.</span></span> <span data-ttu-id="da2f9-109">Beispielsweise sollten Sie nie einen .NET Remoting-Endpunkt für das Internet oder nicht vertrauenswürdige Clients verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-109">For example, you should never expose a .NET Remoting endpoint to the Internet or to untrusted clients.</span></span> <span data-ttu-id="da2f9-110">Es wird empfohlen, vorhandene Remoting-Anwendungen auf neuere und sicherere Technologien zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="da2f9-110">We recommend existing Remoting applications be migrated to newer and more secure technologies.</span></span> <span data-ttu-id="da2f9-111">Wenn das Anwendungsdesign nur HTTP und RESTful verwendet, wird die ASP.NET-Web-API empfohlen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-111">If the application’s design uses only HTTP and is RESTful, we recommend ASP.NET Web API.</span></span> <span data-ttu-id="da2f9-112">Weitere Informationen finden Sie unter "ASP.NET-Web-API".</span><span class="sxs-lookup"><span data-stu-id="da2f9-112">For more information, see ASP.NET Web API.</span></span> <span data-ttu-id="da2f9-113">Wenn die Anwendung auf SOAP basiert oder Nicht-HTTP-Protokolle wie z. B. TCP erfordert, empfehlen wir WCF.</span><span class="sxs-lookup"><span data-stu-id="da2f9-113">If the application is based on SOAP or requires non-Http protocols such as TCP, we recommend WCF.</span></span>  

## <a name="comparing-net-remoting-to-wcf"></a><span data-ttu-id="da2f9-114">Vergleich von .NET Remoting und WCF</span><span class="sxs-lookup"><span data-stu-id="da2f9-114">Comparing .NET Remoting to WCF</span></span>  
 <span data-ttu-id="da2f9-115">In diesem Abschnitt werden die grundlegenden Bausteine von .NET Remoting mit ihren Entsprechungen in WCF verglichen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-115">This section compares the basic building blocks of .NET Remoting with their WCF equivalents.</span></span> <span data-ttu-id="da2f9-116">Diese Bausteine werden später verwendet, um einige gängige Client/Server-Szenarien in WCF zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-116">We will use these building blocks later to create some common client-server scenarios in WCF.</span></span> <span data-ttu-id="da2f9-117">Im folgenden Diagramm werden die Haupt Ähnlichkeiten und Unterschiede zwischen .NET-Remoting und WCF zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="da2f9-117">The following chart summarizes the main similarities and differences between .NET Remoting and WCF.</span></span>  
  
||<span data-ttu-id="da2f9-118">.NET-Remotezugriff</span><span class="sxs-lookup"><span data-stu-id="da2f9-118">.NET Remoting</span></span>|<span data-ttu-id="da2f9-119">WCF</span><span class="sxs-lookup"><span data-stu-id="da2f9-119">WCF</span></span>|  
|-|-------------------|---------|  
|<span data-ttu-id="da2f9-120">Servertyp</span><span class="sxs-lookup"><span data-stu-id="da2f9-120">Server type</span></span>|<span data-ttu-id="da2f9-121">MarshalByRefObject-Unterklasse</span><span class="sxs-lookup"><span data-stu-id="da2f9-121">Subclass MarshalByRefObject</span></span>|<span data-ttu-id="da2f9-122">Markierung mit [ServiceContract]-Attribut</span><span class="sxs-lookup"><span data-stu-id="da2f9-122">Mark with [ServiceContract] attribute</span></span>|  
|<span data-ttu-id="da2f9-123">Dienstvorgänge</span><span class="sxs-lookup"><span data-stu-id="da2f9-123">Service operations</span></span>|<span data-ttu-id="da2f9-124">Öffentliche Methoden für Servertyp</span><span class="sxs-lookup"><span data-stu-id="da2f9-124">Public methods on server type</span></span>|<span data-ttu-id="da2f9-125">Markierung mit [OperationContract]-Attribut</span><span class="sxs-lookup"><span data-stu-id="da2f9-125">Mark with [OperationContract] attribute</span></span>|  
|<span data-ttu-id="da2f9-126">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="da2f9-126">Serialization</span></span>|<span data-ttu-id="da2f9-127">ISerializable oder [Serializable]</span><span class="sxs-lookup"><span data-stu-id="da2f9-127">ISerializable or [Serializable]</span></span>|<span data-ttu-id="da2f9-128">DataContractSerializer oder XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="da2f9-128">DataContractSerializer or XmlSerializer</span></span>|  
|<span data-ttu-id="da2f9-129">Übergebene Objekte</span><span class="sxs-lookup"><span data-stu-id="da2f9-129">Objects passed</span></span>|<span data-ttu-id="da2f9-130">Als Wert oder Verweis</span><span class="sxs-lookup"><span data-stu-id="da2f9-130">By-value or by-reference</span></span>|<span data-ttu-id="da2f9-131">Nur als Wert</span><span class="sxs-lookup"><span data-stu-id="da2f9-131">By-value only</span></span>|  
|<span data-ttu-id="da2f9-132">Fehler/Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="da2f9-132">Errors/exceptions</span></span>|<span data-ttu-id="da2f9-133">Jede serialisierbare Ausnahme</span><span class="sxs-lookup"><span data-stu-id="da2f9-133">Any serializable exception</span></span>|<span data-ttu-id="da2f9-134">FaultContract\<TDetail></span><span class="sxs-lookup"><span data-stu-id="da2f9-134">FaultContract\<TDetail></span></span>|  
|<span data-ttu-id="da2f9-135">Clientproxyobjekte</span><span class="sxs-lookup"><span data-stu-id="da2f9-135">Client proxy objects</span></span>|<span data-ttu-id="da2f9-136">Stark typisierte transparente Proxys werden automatisch über MarshalByRefObjects erstellt</span><span class="sxs-lookup"><span data-stu-id="da2f9-136">Strongly typed transparent proxies are created automatically from MarshalByRefObjects</span></span>|<span data-ttu-id="da2f9-137">Stark typisierte Proxys werden bei Bedarf mithilfe von ChannelFactory generiert.\<TChannel></span><span class="sxs-lookup"><span data-stu-id="da2f9-137">Strongly typed proxies are generated on-demand using ChannelFactory\<TChannel></span></span>|  
|<span data-ttu-id="da2f9-138">Plattform erforderlich</span><span class="sxs-lookup"><span data-stu-id="da2f9-138">Platform required</span></span>|<span data-ttu-id="da2f9-139">Client und Server müssen Microsoft-Betriebssystem und .NET verwenden</span><span class="sxs-lookup"><span data-stu-id="da2f9-139">Both client and server must use Microsoft OS and .NET</span></span>|<span data-ttu-id="da2f9-140">Plattformübergreifend</span><span class="sxs-lookup"><span data-stu-id="da2f9-140">Cross-platform</span></span>|  
|<span data-ttu-id="da2f9-141">Nachrichtenformat</span><span class="sxs-lookup"><span data-stu-id="da2f9-141">Message format</span></span>|<span data-ttu-id="da2f9-142">Private</span><span class="sxs-lookup"><span data-stu-id="da2f9-142">Private</span></span>|<span data-ttu-id="da2f9-143">Industriestandards (SOAP, WS-\* usw.)</span><span class="sxs-lookup"><span data-stu-id="da2f9-143">Industry standards (SOAP, WS-\*, etc.)</span></span>|  
  
### <a name="server-implementation-comparison"></a><span data-ttu-id="da2f9-144">Serverimplementierung im Vergleich</span><span class="sxs-lookup"><span data-stu-id="da2f9-144">Server Implementation Comparison</span></span>  
  
#### <a name="creating-a-server-in-net-remoting"></a><span data-ttu-id="da2f9-145">Erstellen eines Servers in .NET Remoting</span><span class="sxs-lookup"><span data-stu-id="da2f9-145">Creating a Server in .NET Remoting</span></span>  
 <span data-ttu-id="da2f9-146">.NET Remoting-Servertypen müssen von MarshalByRefObject abgeleitet werden und Methoden definieren, die der Client aufrufen kann. Dies wird nachfolgend gezeigt:</span><span class="sxs-lookup"><span data-stu-id="da2f9-146">.NET Remoting server types must derive from MarshalByRefObject and define methods the client can call, like the following:</span></span>  
  
```csharp
public class RemotingServer : MarshalByRefObject  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 <span data-ttu-id="da2f9-147">Die öffentlichen Methoden dieses Servertyps werden zum öffentlichen Vertrag, der für Clients zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="da2f9-147">The public methods of this server type become the public contract available to clients.</span></span>  <span data-ttu-id="da2f9-148">Es gibt keine Trennung zwischen der öffentlichen Serverschnittstelle und deren Implementierung – beide werden durch einen Typ behandelt.</span><span class="sxs-lookup"><span data-stu-id="da2f9-148">There is no separation between the server’s public interface and its implementation – one type handles both.</span></span>  
  
 <span data-ttu-id="da2f9-149">Nachdem der Servertyp definiert wurde, kann er für Clients verfügbar gemacht werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="da2f9-149">Once the server type has been defined, it can be made available to clients, like in the following example:</span></span>  
  
```csharp
TcpChannel channel = new TcpChannel(8080);  
ChannelServices.RegisterChannel(channel, ensureSecurity : true);  
RemotingConfiguration.RegisterWellKnownServiceType(  
    typeof(RemotingServer),
    "RemotingServer",
    WellKnownObjectMode.Singleton);  
Console.WriteLine("RemotingServer is running.  Press ENTER to terminate...");  
Console.ReadLine();  
```  
  
 <span data-ttu-id="da2f9-150">Es gibt viele Möglichkeiten, den Remoting-Typ als Server verfügbar zu machen, einschließlich der Verwendung von Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="da2f9-150">There are many ways to make the Remoting type available as a server, including using configuration files.</span></span> <span data-ttu-id="da2f9-151">Dies ist nur ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="da2f9-151">This is just one example.</span></span>  
  
#### <a name="creating-a-server-in-wcf"></a><span data-ttu-id="da2f9-152">Erstellen eines Servers in WCF</span><span class="sxs-lookup"><span data-stu-id="da2f9-152">Creating a Server in WCF</span></span>  
 <span data-ttu-id="da2f9-153">Der entsprechende Schritt in WCF umfasst das Erstellen von zwei Typen – des öffentlichen "Dienstvertrags" und der konkreten Implementierung.</span><span class="sxs-lookup"><span data-stu-id="da2f9-153">The equivalent step in WCF involves creating two types -- the public "service contract" and the concrete implementation.</span></span> <span data-ttu-id="da2f9-154">Der erste Typ wird als eine mit [ServiceContract] markierte Schnittstelle deklariert.</span><span class="sxs-lookup"><span data-stu-id="da2f9-154">The first is declared as an interface marked with [ServiceContract].</span></span> <span data-ttu-id="da2f9-155">Für Clients verfügbare Methoden sind mit [OperationContract] markiert:</span><span class="sxs-lookup"><span data-stu-id="da2f9-155">Methods available to clients are marked with [OperationContract]:</span></span>  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 <span data-ttu-id="da2f9-156">Die serverseitige Implementierung ist in einer separaten konkreten Klasse definiert, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="da2f9-156">The server’s implementation is defined in a separate concrete class, like in the following example:</span></span>  
  
```csharp
public class WCFServer : IWCFServer  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 <span data-ttu-id="da2f9-157">Sobald diese Typen definiert wurden, kann der WCF-Server für Clients verfügbar gemacht werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="da2f9-157">Once these types have been defined, the WCF server can be made available to clients, like in the following example:</span></span>  
  
```csharp
NetTcpBinding binding = new NetTcpBinding();  
Uri baseAddress = new Uri("net.tcp://localhost:8000/wcfserver");  
  
using (ServiceHost serviceHost = new ServiceHost(typeof(WCFServer), baseAddress))  
{  
    serviceHost.AddServiceEndpoint(typeof(IWCFServer), binding, baseAddress);  
    serviceHost.Open();  
  
    Console.WriteLine($"The WCF server is ready at {baseAddress}.");
    Console.WriteLine("Press <ENTER> to terminate service...");  
    Console.WriteLine();  
    Console.ReadLine();  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="da2f9-158">Es wird in beiden Fällen TCP verwendet, um die Beispiele so ähnlich wie möglich zu halten.</span><span class="sxs-lookup"><span data-stu-id="da2f9-158">TCP is used in both examples to keep them as similar as possible.</span></span> <span data-ttu-id="da2f9-159">Beispiele mit Verwendung von HTTP finden Sie weiter unten in diesem Thema in den Szenariobeschreibungen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-159">Refer to the scenario walk-throughs later in this topic for examples using HTTP.</span></span>  
  
 <span data-ttu-id="da2f9-160">Es gibt viele Möglichkeiten zum Konfigurieren und Hosten von WCF-Diensten.</span><span class="sxs-lookup"><span data-stu-id="da2f9-160">There are many ways to configure and to host WCF services.</span></span> <span data-ttu-id="da2f9-161">Dies ist lediglich ein Beispiel, bezeichnet als "selbst gehosteter Dienst".</span><span class="sxs-lookup"><span data-stu-id="da2f9-161">This is just one example, known as "self-hosted".</span></span> <span data-ttu-id="da2f9-162">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="da2f9-162">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="da2f9-163">Vorgehensweise: Definieren eines Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="da2f9-163">How to: Define a Service Contract</span></span>](how-to-define-a-wcf-service-contract.md)  
  
- [<span data-ttu-id="da2f9-164">Konfigurieren von Diensten mit Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="da2f9-164">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)  
  
- [<span data-ttu-id="da2f9-165">Hosting-Dienste</span><span class="sxs-lookup"><span data-stu-id="da2f9-165">Hosting Services</span></span>](hosting-services.md)  
  
### <a name="client-implementation-comparison"></a><span data-ttu-id="da2f9-166">Clientimplementierung im Vergleich</span><span class="sxs-lookup"><span data-stu-id="da2f9-166">Client Implementation Comparison</span></span>  
  
#### <a name="creating-a-client-in-net-remoting"></a><span data-ttu-id="da2f9-167">Erstellen eines Clients in .NET Remoting</span><span class="sxs-lookup"><span data-stu-id="da2f9-167">Creating a Client in .NET Remoting</span></span>  
 <span data-ttu-id="da2f9-168">Sobald ein .NET Remoting-Serverobjekt verfügbar gemacht wurde, kann es von Clients genutzt werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="da2f9-168">Once a .NET Remoting server object has been made available, it can be consumed by clients, like in the following example:</span></span>  
  
```csharp
TcpChannel channel = new TcpChannel();  
ChannelServices.RegisterChannel(channel, ensureSecurity : true);  
RemotingServer server = (RemotingServer)Activator.GetObject(  
                            typeof(RemotingServer),
                            "tcp://localhost:8080/RemotingServer");  
  
RemotingCustomer customer = server.GetCustomer(42);  
Console.WriteLine($"Customer {customer.FirstName} {customer.LastName} received.");
```  
  
 <span data-ttu-id="da2f9-169">Die von Activator.GetObject() zurückgegebene RemotingServer-Instanz wird als "transparenter Proxy" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="da2f9-169">The RemotingServer instance returned from Activator.GetObject() is known as a "transparent proxy."</span></span> <span data-ttu-id="da2f9-170">Diese Instanz implementiert die öffentliche API für den RemotingServer-Typ auf dem Client, sämtliche Methoden rufen jedoch das Serverobjekt auf, das in einem anderen Prozess oder auf einem anderen Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="da2f9-170">It implements the public API for the RemotingServer type on the client, but all the methods call the server object running in a different process or machine.</span></span>  
  
#### <a name="creating-a-client-in-wcf"></a><span data-ttu-id="da2f9-171">Erstellen eines Clients in WCF</span><span class="sxs-lookup"><span data-stu-id="da2f9-171">Creating a Client in WCF</span></span>  
 <span data-ttu-id="da2f9-172">Der entsprechende Schritt in WCF umfasst die Verwendung einer Kanalfactory zur expliziten Erstellung des Proxys.</span><span class="sxs-lookup"><span data-stu-id="da2f9-172">The equivalent step in WCF involves using a channel factory to create the proxy explicitly.</span></span> <span data-ttu-id="da2f9-173">Wie Remoting kann das Proxyobjekt zum Auslösen von Vorgängen auf dem Server verwendet werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="da2f9-173">Like Remoting, the proxy object can be used to invoke operations on the server, like in the following example:</span></span>  
  
```csharp
NetTcpBinding binding = new NetTcpBinding();  
String url = "net.tcp://localhost:8000/wcfserver";  
EndpointAddress address = new EndpointAddress(url);  
ChannelFactory<IWCFServer> channelFactory =
    new ChannelFactory<IWCFServer>(binding, address);  
IWCFServer server = channelFactory.CreateChannel();  
  
Customer customer = server.GetCustomer(42);  
Console.WriteLine($"  Customer {customer.FirstName} {customer.LastName} received.");
```  
  
 <span data-ttu-id="da2f9-174">Dieses Beispiel zeigt die Programmierung auf Kanalebene, da sie dem Remoting-Beispiel am ähnlichsten ist.</span><span class="sxs-lookup"><span data-stu-id="da2f9-174">This example shows programming at the channel level because it is most similar to the Remoting example.</span></span> <span data-ttu-id="da2f9-175">Außerdem ist der **Dienstverweis hinzufügen** Ansatz in Visual Studio verfügbar, der Code generiert, um die Client Programmierung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-175">Also available is the **Add Service Reference** approach in Visual Studio that generates code to simplify client programming.</span></span> <span data-ttu-id="da2f9-176">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="da2f9-176">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="da2f9-177">Client-Kanalebenenprogrammierung</span><span class="sxs-lookup"><span data-stu-id="da2f9-177">Client Channel-Level Programming</span></span>](./extending/client-channel-level-programming.md)  
  
- [<span data-ttu-id="da2f9-178">Vorgehensweise: Hinzufügen, Aktualisieren oder Entfernen eines Dienstverweises</span><span class="sxs-lookup"><span data-stu-id="da2f9-178">How to: Add, Update, or Remove a Service Reference</span></span>](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference)  
  
### <a name="serialization-usage"></a><span data-ttu-id="da2f9-179">Verwenden der Serialisierung</span><span class="sxs-lookup"><span data-stu-id="da2f9-179">Serialization Usage</span></span>  
 <span data-ttu-id="da2f9-180">Sowohl .NET Remoting als auch WCF verwenden Serialisierung, um Objekte zwischen Client und Server zu senden. Es gelten jedoch folgende wichtige Unterschiede:</span><span class="sxs-lookup"><span data-stu-id="da2f9-180">Both .NET Remoting and WCF use serialization to send objects between client and server, but they differ in these important ways:</span></span>  
  
1. <span data-ttu-id="da2f9-181">Sie verwenden verschiedene Serialisierer und Konventionen, um anzugeben, was serialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="da2f9-181">They use different serializers and conventions to indicate what to serialize.</span></span>  
  
2. <span data-ttu-id="da2f9-182">.NET Remoting unterstützt die Serialisierung "nach Verweis", bei der ein Methoden- oder Eigenschaftenzugriff auf einer Ebene die Ausführung von Code auf einer anderen Ebene zulässt, also über Sicherheitsgrenzen hinweg.</span><span class="sxs-lookup"><span data-stu-id="da2f9-182">.NET Remoting supports "by reference" serialization that allows method or property access on one tier to execute code on the other tier, which is across security boundaries.</span></span> <span data-ttu-id="da2f9-183">Diese Funktion birgt Sicherheitsrisiken und ist einer der Hauptgründe dafür, warum Remoting-Endpunkte niemals für nicht vertrauenswürdige Clients verfügbar gemacht werden sollten.</span><span class="sxs-lookup"><span data-stu-id="da2f9-183">This capability exposes security vulnerabilities and is one of the main reasons why Remoting endpoints should never be exposed to untrusted clients.</span></span>  
  
3. <span data-ttu-id="da2f9-184">Die von Remoting eingesetzte Serialisierung erfolgt nach dem Ausschlussverfahren (expliziter Ausschluss der Elemente, die nicht serialisiert werden sollen), WCF verwendet eine Serialisierung nach dem Einschlussverfahren (explizite Markierung der Elemente, die serialisiert werden sollen).</span><span class="sxs-lookup"><span data-stu-id="da2f9-184">Serialization used by Remoting is opt-out (explicitly exclude what not to serialize) and WCF serialization is opt-in (explicitly mark which members to serialize).</span></span>  
  
#### <a name="serialization-in-net-remoting"></a><span data-ttu-id="da2f9-185">Serialisierung in .NET Remoting</span><span class="sxs-lookup"><span data-stu-id="da2f9-185">Serialization in .NET Remoting</span></span>  
 <span data-ttu-id="da2f9-186">.NET Remoting unterstützt zwei Möglichkeiten zum Serialisieren und Deserialisieren von Objekten zwischen Client und Server:</span><span class="sxs-lookup"><span data-stu-id="da2f9-186">.NET Remoting supports two ways to serialize and deserialize objects between the client and server:</span></span>  
  
- <span data-ttu-id="da2f9-187">*Nach Wert* – die Werte des Objekts werden über Ebenengrenzen hinweg serialisiert, und eine neue Instanz dieses Objekts wird auf der anderen Ebene erstellt.</span><span class="sxs-lookup"><span data-stu-id="da2f9-187">*By value* – the values of the object are serialized across tier boundaries, and a new instance of that object is created on the other tier.</span></span> <span data-ttu-id="da2f9-188">Alle Aufrufe von Methoden oder Eigenschaften der neuen Instanz werden ausschließlich lokal ausgeführt und wirken sich nicht auf das ursprüngliche Objekt oder die ursprüngliche Ebene aus.</span><span class="sxs-lookup"><span data-stu-id="da2f9-188">Any calls to methods or properties of that new instance execute only locally and do not affect the original object or tier.</span></span>  
  
- <span data-ttu-id="da2f9-189">Als *Verweis* – ein spezieller "Objekt Verweis" wird über Ebenengrenzen hinweg serialisiert.</span><span class="sxs-lookup"><span data-stu-id="da2f9-189">*By reference* – a special "object reference" is serialized across tier boundaries.</span></span> <span data-ttu-id="da2f9-190">Wenn eine Ebene mit Methoden oder Eigenschaften des Objekts interagiert, erfolgt die Kommunikation zurück an das ursprüngliche Objekt oder die ursprüngliche Ebene.</span><span class="sxs-lookup"><span data-stu-id="da2f9-190">When one tier interacts with methods or properties of that object, it communicates back to the original object on the original tier.</span></span> <span data-ttu-id="da2f9-191">Als-Verweis-Objekte können in beide Richtungen übertragen werden – vom Server an den Client oder vom Client an den Server.</span><span class="sxs-lookup"><span data-stu-id="da2f9-191">By-reference objects can flow in either direction – server to client, or client to server.</span></span>  
  
 <span data-ttu-id="da2f9-192">Als-Wert-Typen werden in Remoting mit dem [Serializable]-Attribut gekennzeichnet oder implementieren "ISerializable", wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="da2f9-192">By-value types in Remoting are marked with the [Serializable] attribute or implement ISerializable, like in the following example:</span></span>  
  
```csharp
[Serializable]  
public class RemotingCustomer  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="da2f9-193">Als Verweis-Typen werden von der MarshalByRefObject-Klasse abgeleitet, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="da2f9-193">By-reference types derive from the MarshalByRefObject class, like in the following example:</span></span>  
  
```csharp
public class RemotingCustomerReference : MarshalByRefObject  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="da2f9-194">Es ist äußerst wichtig, die Auswirkung von Verweisobjekten in Remoting zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-194">It is extremely important to understand the implications of Remoting’s by-reference objects.</span></span> <span data-ttu-id="da2f9-195">Wenn eine der beiden Ebenen (Client oder Server) ein Verweisobjekt an die andere Ebene sendet, werden alle Methodenaufrufe auf der Ebene ausgeführt, zu der das Objekt gehört.</span><span class="sxs-lookup"><span data-stu-id="da2f9-195">If either tier (client or server) sends a by-reference object to the other tier, all method calls execute back on the tier owning the object.</span></span> <span data-ttu-id="da2f9-196">Beispiel: Wenn ein Client Methoden für ein vom Server zurückgegebenes Verweisobjekt aufruft, führt dies zur Ausführung von Code auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="da2f9-196">For example, a client calling methods on a by-reference object returned by the server will execute code on the server.</span></span> <span data-ttu-id="da2f9-197">Auf ähnliche Weise wird beim Aufruf von durch den Client bereitgestellten Verweisobjekten durch den Server Code auf dem Client ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="da2f9-197">Similarly, a server calling methods on a by-reference object provided by the client will execute code back on the client.</span></span> <span data-ttu-id="da2f9-198">Aus diesem Grund empfiehlt sich die Verwendung von .NET Remoting nur in vollständig vertrauenswürdigen Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-198">For this reason, the use of .NET Remoting is recommended only within fully-trusted environments.</span></span> <span data-ttu-id="da2f9-199">Das Offenlegen eines öffentlichen .NET Remoting-Endpunkts für nicht vertrauenswürdige Clients macht einen Remoting-Server anfällig für Angriffe.</span><span class="sxs-lookup"><span data-stu-id="da2f9-199">Exposing a public .NET Remoting endpoint to untrusted clients will make a Remoting server vulnerable to attack.</span></span>  
  
#### <a name="serialization-in-wcf"></a><span data-ttu-id="da2f9-200">Serialisierung in WCF</span><span class="sxs-lookup"><span data-stu-id="da2f9-200">Serialization in WCF</span></span>  
 <span data-ttu-id="da2f9-201">WCF unterstützt nur die Serialisierung nach Wert.</span><span class="sxs-lookup"><span data-stu-id="da2f9-201">WCF supports only by-value serialization.</span></span> <span data-ttu-id="da2f9-202">Die gängigste Methode zum Definieren eines Typs für den Austausch zwischen Client und Server wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="da2f9-202">The most common way to define a type to exchange between client and server is like in the following example:</span></span>  
  
```csharp
[DataContract]  
public class WCFCustomer  
{  
    [DataMember]  
    public string FirstName { get; set; }  
  
    [DataMember]  
    public string LastName { get; set; }  
  
    [DataMember]  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="da2f9-203">Das [DataContract]-Attribut gibt an, dass dieser Typ zwischen Client und Server serialisiert und deserialisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="da2f9-203">The [DataContract] attribute identifies this type as one that can be serialized and deserialized between client and server.</span></span> <span data-ttu-id="da2f9-204">Das Attribut [DataMember] identifiziert die einzelnen Eigenschaften oder Felder für die Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="da2f9-204">The [DataMember] attribute identifies the individual properties or fields to serialize.</span></span>  
  
 <span data-ttu-id="da2f9-205">Wenn WCF ein Objekt über Ebenen hinweg sendet, werden nur die Werte serialisiert, und es wird eine neue Instanz des Objekts auf der anderen Ebene erstellt.</span><span class="sxs-lookup"><span data-stu-id="da2f9-205">When WCF sends an object across tiers, it serializes only the values and creates a new instance of the object on the other tier.</span></span> <span data-ttu-id="da2f9-206">Sämtliche Interaktionen mit den Werten des Objekts erfolgen nur lokal – es findet im Gegensatz zu den Als-Verweis-Objekten in .NET Remoting keine Kommunikation mit der anderen Ebene statt.</span><span class="sxs-lookup"><span data-stu-id="da2f9-206">Any interactions with the values of the object occur only locally – they do not communicate with the other tier the way .NET Remoting by-reference objects do.</span></span> <span data-ttu-id="da2f9-207">Weitere Informationen finden Sie unter [Serialisierung und Deserialisierung](./feature-details/serialization-and-deserialization.md).</span><span class="sxs-lookup"><span data-stu-id="da2f9-207">For more information, see [Serialization and Deserialization](./feature-details/serialization-and-deserialization.md).</span></span>  
  
### <a name="exception-handling-capabilities"></a><span data-ttu-id="da2f9-208">Funktionen für die Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="da2f9-208">Exception Handling Capabilities</span></span>  
  
#### <a name="exceptions-in-net-remoting"></a><span data-ttu-id="da2f9-209">Ausnahmen in .NET Remoting</span><span class="sxs-lookup"><span data-stu-id="da2f9-209">Exceptions in .NET Remoting</span></span>  
 <span data-ttu-id="da2f9-210">Von einem Remoting-Server ausgelöste Ausnahmen werden serialisiert, an den Client gesendet und lokal auf dem Client wie jede andere Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="da2f9-210">Exceptions thrown by a Remoting server are serialized, sent to the client, and thrown locally on the client like any other exception.</span></span> <span data-ttu-id="da2f9-211">Benutzerdefinierte Ausnahmen können durch das Erstellen einer Unterklasse für den Ausnahmetyp und Markierung mit [Serializable] erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-211">Custom exceptions can be created by sub-classing the Exception type and marking it with [Serializable].</span></span>   <span data-ttu-id="da2f9-212">Die meisten Framework-Ausnahmen sind bereits in dieser Weise markiert. Deshalb können die meisten von ihnen durch den Server ausgelöst, serialisiert und erneut auf dem Client ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-212">Most framework exceptions are already marked in this way, allowing most to be thrown by the server, serialized, and re-thrown on the client.</span></span> <span data-ttu-id="da2f9-213">Wenngleich dieses Design bei der Entwicklung praktisch ist, werden so möglicherweise unbeabsichtigt Informationen gegenüber dem Client offengelegt.</span><span class="sxs-lookup"><span data-stu-id="da2f9-213">Though this design is convenient during development, server-side information can inadvertently be disclosed to the client.</span></span> <span data-ttu-id="da2f9-214">Dies ist einer der vielen Gründe, aus denen Remoting nur in vollständig vertrauenswürdigen Umgebungen eingesetzt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="da2f9-214">This is one of many reasons Remoting should be used only in fully-trusted environments.</span></span>  
  
#### <a name="exceptions-and-faults-in-wcf"></a><span data-ttu-id="da2f9-215">Ausnahmen und Fehler in WCF</span><span class="sxs-lookup"><span data-stu-id="da2f9-215">Exceptions and Faults in WCF</span></span>  
 <span data-ttu-id="da2f9-216">WCF lässt keine Rückgabe zufälliger Ausnahmetypen vom Server an den Client zu, da dies zu einer unbeabsichtigten Offenlegung von Informationen führen kann.</span><span class="sxs-lookup"><span data-stu-id="da2f9-216">WCF does not allow arbitrary exception types to be returned from the server to the client because it could lead to inadvertent information disclosure.</span></span> <span data-ttu-id="da2f9-217">Wenn ein Dienstvorgang eine unerwartete Ausnahme ausgelöst wird, führt dies dazu, dass auf dem Client eine allgemeine FaultException ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="da2f9-217">If a service operation throws an unexpected exception, it causes a general purpose FaultException to be thrown on the client.</span></span> <span data-ttu-id="da2f9-218">Diese Ausnahme enthält keinerlei Informationen dazu, warum oder wo das Problem aufgetreten ist, und für einige Anwendungen reicht dies aus.</span><span class="sxs-lookup"><span data-stu-id="da2f9-218">This exception does not carry any information why or where the problem occurred, and for some applications this is sufficient.</span></span> <span data-ttu-id="da2f9-219">Anwendungen, die ausführlichere Fehlerinformationen an den Client kommunizieren müssen, definieren zu diesem Zweck einen Fehlervertrag.</span><span class="sxs-lookup"><span data-stu-id="da2f9-219">Applications that need to communicate richer error information to the client do this by defining a fault contract.</span></span>  
  
 <span data-ttu-id="da2f9-220">Hierzu erstellen Sie zunächst einen [DataContract]-Typ, der die Fehlerinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="da2f9-220">To do this, first create a [DataContract] type to carry the fault information.</span></span>  
  
```csharp
[DataContract]  
public class CustomerServiceFault  
{  
    [DataMember]  
    public string ErrorMessage { get; set; }  
  
    [DataMember]  
    public int CustomerId {get;set;}  
}  
```  
  
 <span data-ttu-id="da2f9-221">Geben Sie den Fehlervertrag an, der für jeden Dienstvorgang zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="da2f9-221">Specify the fault contract to use for each service operation.</span></span>  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    [FaultContract(typeof(CustomerServiceFault))]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 <span data-ttu-id="da2f9-222">Der Server meldet Fehlerbedingungen durch das Auslösen einer FaultException.</span><span class="sxs-lookup"><span data-stu-id="da2f9-222">The server reports error conditions by throwing a FaultException.</span></span>  
  
```csharp
throw new FaultException<CustomerServiceFault>(  
    new CustomerServiceFault() {
        CustomerId = customerId,
        ErrorMessage = "Illegal customer Id"
    });  
```  
  
 <span data-ttu-id="da2f9-223">Und wenn der Client eine Anforderung an den Server sendet, können Fehler als normale Ausnahmen abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-223">And whenever the client makes a request to the server, it can catch faults as normal exceptions.</span></span>  
  
```csharp
try  
{  
    Customer customer = server.GetCustomer(-1);  
}  
catch (FaultException<CustomerServiceFault> fault)  
{  
    Console.WriteLine($"Fault received: {fault.Detail.ErrorMessage}");
}  
```  
  
 <span data-ttu-id="da2f9-224">Weitere Informationen zu Fehlerverträgen finden Sie unter <xref:System.ServiceModel.FaultException>.</span><span class="sxs-lookup"><span data-stu-id="da2f9-224">For more information about fault contracts, see <xref:System.ServiceModel.FaultException>.</span></span>  
  
### <a name="security-considerations"></a><span data-ttu-id="da2f9-225">Sicherheitsüberlegungen</span><span class="sxs-lookup"><span data-stu-id="da2f9-225">Security Considerations</span></span>  
  
#### <a name="security-in-net-remoting"></a><span data-ttu-id="da2f9-226">Sicherheit in .NET Remoting</span><span class="sxs-lookup"><span data-stu-id="da2f9-226">Security in .NET Remoting</span></span>  
 <span data-ttu-id="da2f9-227">Einige .NET Remoting-Kanäle unterstützen Sicherheitsfunktionen wie beispielsweise Authentifizierung und Verschlüsselung auf Kanalebene (IPC und TCP).</span><span class="sxs-lookup"><span data-stu-id="da2f9-227">Some .NET Remoting channels support security features such as authentication and encryption at the channel layer (IPC and TCP).</span></span> <span data-ttu-id="da2f9-228">Der HTTP-Kanal nutzt sowohl für die Authentifizierung als auch für die Verschlüsselung Internetinformationsdienste (IIS).</span><span class="sxs-lookup"><span data-stu-id="da2f9-228">The HTTP channel relies on Internet Information Services (IIS) for both authentication and encryption.</span></span> <span data-ttu-id="da2f9-229">Trotz dieser Unterstützung sollten Sie .NET Remoting als unsicheres Kommunikationsprotokoll betrachten und nur in vollständig vertrauenswürdigen Umgebungen einsetzen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-229">Despite this support, you should consider .NET Remoting an unsecure communication protocol and use it only within fully-trusted environments.</span></span> <span data-ttu-id="da2f9-230">Machen Sie niemals einen öffentlichen Remoting-Endpunkt für das Internet oder nicht vertrauenswürdige Clients verfügbar.</span><span class="sxs-lookup"><span data-stu-id="da2f9-230">Never expose a public Remoting endpoint to the Internet or untrusted clients.</span></span>  
  
#### <a name="security-in-wcf"></a><span data-ttu-id="da2f9-231">Sicherheit in WCF</span><span class="sxs-lookup"><span data-stu-id="da2f9-231">Security in WCF</span></span>  
 <span data-ttu-id="da2f9-232">WCF wurde unter dem Gesichtspunkt der Sicherheit entworfen, teilweise auch deshalb, um die Schwachstellen in .NET Remoting zu beheben.</span><span class="sxs-lookup"><span data-stu-id="da2f9-232">WCF was designed with security in mind, in part to address the kinds of vulnerabilities found in .NET Remoting.</span></span> <span data-ttu-id="da2f9-233">WCF bietet Sicherheit auf Transport- und Nachrichtenebene und bietet zahlreiche Optionen für Authentifizierung, Autorisierung, Verschlüsselung usw.</span><span class="sxs-lookup"><span data-stu-id="da2f9-233">WCF offers security at both the transport and message level, and offers many options for authentication, authorization, encryption, and so on.</span></span> <span data-ttu-id="da2f9-234">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="da2f9-234">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="da2f9-235">Security</span><span class="sxs-lookup"><span data-stu-id="da2f9-235">Security</span></span>](./feature-details/security.md)  
  
- [<span data-ttu-id="da2f9-236">WCF-Sicherheits Leit Faden</span><span class="sxs-lookup"><span data-stu-id="da2f9-236">WCF Security Guidance</span></span>](./feature-details/security-guidance-and-best-practices.md)  
  
## <a name="migrating-to-wcf"></a><span data-ttu-id="da2f9-237">Migration nach WCF</span><span class="sxs-lookup"><span data-stu-id="da2f9-237">Migrating to WCF</span></span>  
  
### <a name="why-migrate-from-remoting-to-wcf"></a><span data-ttu-id="da2f9-238">Welche Vorteile bietet die Migration von Remoting nach WCF?</span><span class="sxs-lookup"><span data-stu-id="da2f9-238">Why Migrate from Remoting to WCF?</span></span>  
  
- <span data-ttu-id="da2f9-239">**.NET Remoting ist ein Legacy-Produkt.**</span><span class="sxs-lookup"><span data-stu-id="da2f9-239">**.NET Remoting is a legacy product.**</span></span> <span data-ttu-id="da2f9-240">Wie in [.NET Remoting](/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))beschrieben, wird es als Legacy-Produkt betrachtet und wird nicht für die neue Entwicklung empfohlen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-240">As described in [.NET Remoting](/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)), it is considered a legacy product and is not recommended for new development.</span></span> <span data-ttu-id="da2f9-241">Für neue und vorhandene Anwendungen wird der Einsatz von WCF oder ASP.NET-Web-API empfohlen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-241">WCF or ASP.NET Web API are recommended for new and existing applications.</span></span>  
  
- <span data-ttu-id="da2f9-242">**WCF verwendet plattformübergreifende Standards.**</span><span class="sxs-lookup"><span data-stu-id="da2f9-242">**WCF uses cross-platform standards.**</span></span> <span data-ttu-id="da2f9-243">WCF wurde unter dem Gesichtspunkt einer plattformübergreifenden Interoperabilität entwickelt und unterstützt zahlreiche Industriestandards (SOAP, WS-Security, WS-Trust, usw.).</span><span class="sxs-lookup"><span data-stu-id="da2f9-243">WCF was designed with cross-platform interoperability in mind and supports many industry standards (SOAP, WS-Security, WS-Trust, etc.).</span></span> <span data-ttu-id="da2f9-244">Ein WCF-Dienst kann mit Clients interagieren, auf denen andere Betriebssysteme als Windows ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-244">A WCF service can interoperate with clients running on operating systems other than Windows.</span></span> <span data-ttu-id="da2f9-245">Remoting wurde hauptsächlich für Umgebungen entwickelt, in denen Server-und Client Anwendungen mit .NET Framework auf einem Windows-Betriebssystem ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-245">Remoting was designed primarily for environments where both the server and client applications run using .NET Framework on a Windows operating system.</span></span>
  
- <span data-ttu-id="da2f9-246">**WCF bietet integrierte Sicherheit.**</span><span class="sxs-lookup"><span data-stu-id="da2f9-246">**WCF has built-in security.**</span></span> <span data-ttu-id="da2f9-247">WCF wurde unter Berücksichtigung der Sicherheit entwickelt und bietet viele Optionen für Authentifizierung, Sicherheit auf Transport Ebene, Sicherheit auf Nachrichten Ebene usw. Remoting wurde entwickelt, um die Interoperabilität von Anwendungen zu vereinfachen, war aber nicht für die Sicherheit in nicht vertrauenswürdigen Umgebungen konzipiert.</span><span class="sxs-lookup"><span data-stu-id="da2f9-247">WCF was designed with security in mind and offers many options for authentication, transport level security, message level security, etc. Remoting was designed to make it easy for applications to interoperate but was not designed to be secure in non-trusted environments.</span></span> <span data-ttu-id="da2f9-248">WCF wurde entworfen, um sowohl in vertrauenswürdigen als auch in nicht vertrauenswürdigen Umgebungen eingesetzt zu werden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-248">WCF was designed to work in both trusted and non-trusted environments.</span></span>  
  
### <a name="migration-recommendations"></a><span data-ttu-id="da2f9-249">Empfehlungen für die Migration</span><span class="sxs-lookup"><span data-stu-id="da2f9-249">Migration Recommendations</span></span>  
 <span data-ttu-id="da2f9-250">Für die Migration von .NET Remoting nach WCF werden die folgenden Schritte empfohlen:</span><span class="sxs-lookup"><span data-stu-id="da2f9-250">The following are the recommended steps to migrate from .NET Remoting to WCF:</span></span>  
  
- <span data-ttu-id="da2f9-251">**Erstellen des Dienstvertrags.**</span><span class="sxs-lookup"><span data-stu-id="da2f9-251">**Create the service contract.**</span></span> <span data-ttu-id="da2f9-252">Definieren Sie Ihre Dienstschnittstellentypen, und markieren Sie diese mit dem [ServiceContract]-Attribut. Markieren Sie alle Methoden, die der Client mit [OperationContract] aufrufen darf.</span><span class="sxs-lookup"><span data-stu-id="da2f9-252">Define your service interface types, and mark them with the [ServiceContract] attribute.Mark all the methods the clients will be allowed to call with [OperationContract].</span></span>  
  
- <span data-ttu-id="da2f9-253">**Erstellen Sie den Datenvertrag.**</span><span class="sxs-lookup"><span data-stu-id="da2f9-253">**Create the data contract.**</span></span> <span data-ttu-id="da2f9-254">Definieren Sie die Datentypen, die zwischen Server und Client ausgetauscht werden, und markieren Sie diese mit dem Attribut [DataContract].</span><span class="sxs-lookup"><span data-stu-id="da2f9-254">Define the data types that will be exchanged between server and client, and mark them with the [DataContract] attribute.</span></span> <span data-ttu-id="da2f9-255">Markieren Sie alle Felder und Eigenschaften, die der Client mit [DataMember] verwenden darf.</span><span class="sxs-lookup"><span data-stu-id="da2f9-255">Mark all the fields and properties the client will be allowed to use with [DataMember].</span></span>  
  
- <span data-ttu-id="da2f9-256">**Erstellen des Fehlervertrags (optional).**</span><span class="sxs-lookup"><span data-stu-id="da2f9-256">**Create the fault contract (optional).**</span></span> <span data-ttu-id="da2f9-257">Erstellen Sie die Typen, die zwischen Server und Client ausgetauscht werden, wenn Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="da2f9-257">Create the types that will be exchanged between server and client when errors are encountered.</span></span> <span data-ttu-id="da2f9-258">Markieren Sie diese Typen mit [DataContract] und [DataMember], um sie serialisierbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-258">Mark these types with [DataContract] and [DataMember] to make them serializable.</span></span> <span data-ttu-id="da2f9-259">Markieren Sie alle Dienstvorgänge, die Sie mit [OperationContract] markiert haben, auch mit [FaultContract], um die Fehler festzulegen, die zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="da2f9-259">For all service operations you marked with [OperationContract], also mark them with [FaultContract] to indicate which errors they may return.</span></span>  
  
- <span data-ttu-id="da2f9-260">**Konfigurieren und Hosten des Diensts.**</span><span class="sxs-lookup"><span data-stu-id="da2f9-260">**Configure and host the service.**</span></span> <span data-ttu-id="da2f9-261">Sobald der Dienstvertrag erstellt wurde, besteht der nächste Schritt darin, eine Bindung zu konfigurieren, die für den Dienst an einem Endpunkt verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="da2f9-261">Once the service contract has been created, the next step is to configure a binding to expose the service at an endpoint.</span></span> <span data-ttu-id="da2f9-262">Weitere Informationen finden Sie unter [Endpunkte: Adressen, Bindungen und Verträge](./feature-details/endpoints-addresses-bindings-and-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="da2f9-262">For more information, see [Endpoints: Addresses, Bindings, and Contracts](./feature-details/endpoints-addresses-bindings-and-contracts.md).</span></span>  
  
 <span data-ttu-id="da2f9-263">Nach der Migration einer Remoting-Anwendung nach WCF ist es wichtig, Abhängigkeiten mit .NET Remoting zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-263">Once a Remoting application has been migrated to WCF, it is still important to remove dependencies on .NET Remoting.</span></span> <span data-ttu-id="da2f9-264">Auf diese Weise wird sichergestellt, dass alle Remoing-Sicherheitsanfälligkeiten aus der Anwendung entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-264">This ensures that any Remoting vulnerabilities are removed from the application.</span></span> <span data-ttu-id="da2f9-265">Folgende Schritte müssen ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="da2f9-265">These steps include the following:</span></span>  
  
- <span data-ttu-id="da2f9-266">**Beenden Sie die Verwendung von "MarshalByRefObject".**</span><span class="sxs-lookup"><span data-stu-id="da2f9-266">**Discontinue use of MarshalByRefObject.**</span></span> <span data-ttu-id="da2f9-267">Der MarshalByRefObject-Typ ist nur in Remoting vorhanden und wird von WCF nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="da2f9-267">The MarshalByRefObject type exists only for Remoting and is not used by WCF.</span></span> <span data-ttu-id="da2f9-268">Alle Anwendungstypen, die Unterklassen von MarshalByRefObject verwenden, sollten entfernt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-268">Any application types that sub-class MarshalByRefObject should be removed or changed.</span></span>  
  
- <span data-ttu-id="da2f9-269">**Beenden Sie die Verwendung von [Serializable] und ISerializable.**</span><span class="sxs-lookup"><span data-stu-id="da2f9-269">**Discontinue use of [Serializable] and ISerializable.**</span></span> <span data-ttu-id="da2f9-270">Das [Serializable]-Attribut und die ISerializable-Schnittstelle wurden ursprünglich zum Serialisieren von Typen in vertrauenswürdigen Umgebungen entworfen und werden von Remoting verwendet.</span><span class="sxs-lookup"><span data-stu-id="da2f9-270">The [Serializable] attribute and ISerializable interface were originally designed to serialize types within trusted environments, and they are used by Remoting.</span></span> <span data-ttu-id="da2f9-271">Die WCF-Serialisierung beruht auf Typen, die mit [DataContract] und [DataMember] markiert sind.</span><span class="sxs-lookup"><span data-stu-id="da2f9-271">WCF serialization relies on types being marked with [DataContract] and [DataMember].</span></span> <span data-ttu-id="da2f9-272">Die von einer Anwendung verwendeten Datentypen sollten geändert werden, um [DataContract] zu verwenden und nicht ISerializable oder [Serializable].</span><span class="sxs-lookup"><span data-stu-id="da2f9-272">Data types used by an application should be modified to use [DataContract] and not to use ISerializable or [Serializable].</span></span>  
  
### <a name="migration-scenarios"></a><span data-ttu-id="da2f9-273">Migrationsszenarios</span><span class="sxs-lookup"><span data-stu-id="da2f9-273">Migration Scenarios</span></span>  
 <span data-ttu-id="da2f9-274">Betrachten wir nun, wie die folgenden gängigen Remoting-Szenarien in WCF realisiert werden:</span><span class="sxs-lookup"><span data-stu-id="da2f9-274">Now let’s see how to accomplish the following common Remoting scenarios in WCF:</span></span>  
  
1. <span data-ttu-id="da2f9-275">Server gibt ein Objekt als Wert an den Client zurück</span><span class="sxs-lookup"><span data-stu-id="da2f9-275">Server returns an object by-value to the client</span></span>  
  
2. <span data-ttu-id="da2f9-276">Server gibt ein Objekt als Verweis an den Client zurück</span><span class="sxs-lookup"><span data-stu-id="da2f9-276">Server returns an object by-reference to the client</span></span>  
  
3. <span data-ttu-id="da2f9-277">Client sendet ein Objekt als Wert an den Server</span><span class="sxs-lookup"><span data-stu-id="da2f9-277">Client sends an object by-value to the server</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da2f9-278">Das Senden eines Objekts als Verweis vom Client an den Server ist in WCF nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="da2f9-278">Sending an object by-reference from the client to the server is not allowed in WCF.</span></span>  
  
 <span data-ttu-id="da2f9-279">Nehmen Sie beim Durcharbeiten dieser Szenarien an, dass die Baseline-Schnittstellen für .NET Remoting wie im folgenden Beispiel aussehen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-279">When reading through these scenarios, assume our baseline interfaces for .NET Remoting look like the following example.</span></span> <span data-ttu-id="da2f9-280">Die .NET Remoting-Implementierung ist hier nicht wichtig, da nur dargestellt werden soll, wie WCF zur Implementierung einer äquivalenten Funktionalität genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="da2f9-280">The .NET Remoting implementation is not important here because we want to illustrate only how to use WCF to implement equivalent functionality.</span></span>  
  
```csharp
public class RemotingServer : MarshalByRefObject  
{  
    // Demonstrates server returning object by-value  
    public Customer GetCustomer(int customerId) {…}  
  
    // Demonstrates server returning object by-reference  
    public CustomerReference GetCustomerReference(int customerId) {…}  
  
    // Demonstrates client passing object to server by-value  
    public bool UpdateCustomer(Customer customer) {…}  
}  
```  
  
#### <a name="scenario-1-service-returns-an-object-by-value"></a><span data-ttu-id="da2f9-281">Szenario 1: Der Dienst gibt ein Objekt per Wert zurück</span><span class="sxs-lookup"><span data-stu-id="da2f9-281">Scenario 1: Service Returns an Object by Value</span></span>  
 <span data-ttu-id="da2f9-282">In diesem Szenario wird gezeigt, wie ein Server ein Objekt per Wert an den Client zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="da2f9-282">This scenario demonstrates a server returning an object to the client by value.</span></span> <span data-ttu-id="da2f9-283">WCF gibt Objekte immer per Wert an den Server zurück, daher beschreiben die folgenden Schritte lediglich, wie ein normaler WCF-Dienst erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="da2f9-283">WCF always returns objects from the server by value, so the following steps simply describe how to build a normal WCF service.</span></span>  
  
1. <span data-ttu-id="da2f9-284">Zuerst definieren Sie eine öffentliche Schnittstelle für den WCF-Dienst und markieren ihn mit dem [ServiceContract]-Attribut.</span><span class="sxs-lookup"><span data-stu-id="da2f9-284">Start by defining a public interface for the WCF service and mark it with the [ServiceContract] attribute.</span></span> <span data-ttu-id="da2f9-285">[OperationContract] wird verwendet, um die serverseitigen Methoden zu identifizieren, die der Client aufruft.</span><span class="sxs-lookup"><span data-stu-id="da2f9-285">We use [OperationContract] to identify the server-side methods our client will call.</span></span>  
  
   ```csharp
   [ServiceContract]  
   public interface ICustomerService  
   {  
       [OperationContract]  
       Customer GetCustomer(int customerId);  
  
       [OperationContract]  
       bool UpdateCustomer(Customer customer);  
   }  
   ```  
  
2. <span data-ttu-id="da2f9-286">Im nächsten Schritt wird der Datenvertrag für diesen Dienst erstellt.</span><span class="sxs-lookup"><span data-stu-id="da2f9-286">The next step is to create the data contract for this service.</span></span> <span data-ttu-id="da2f9-287">Dazu werden Klassen (keine Schnittstellen) erstellt, die mit dem [DataContract]-Attribut markiert werden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-287">We do this by creating classes (not interfaces) marked with the [DataContract] attribute.</span></span> <span data-ttu-id="da2f9-288">Die einzelnen Eigenschaften oder Felder, die für Client und Server sichtbar sein sollen, werden mit [DataMember] markiert.</span><span class="sxs-lookup"><span data-stu-id="da2f9-288">The individual properties or fields we want visible to both client and server are marked with [DataMember].</span></span> <span data-ttu-id="da2f9-289">Wenn abgeleitete Typen zulässig sein sollen, müssen diese mit dem [KnownType]-Attribut identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-289">If we want derived types to be allowed, we must use the [KnownType] attribute to identify them.</span></span> <span data-ttu-id="da2f9-290">Die einzigen Typen, für die WCF eine Serialisierung oder Deserialisierung zulässt, sind die in der Dienstschnittstelle enthaltenen Typen sowie diese "bekannten Typen".</span><span class="sxs-lookup"><span data-stu-id="da2f9-290">The only types WCF will allow to be serialized or deserialized for this service are those in the service interface and these "known types".</span></span> <span data-ttu-id="da2f9-291">Jeder Versuch, andere als in dieser Liste enthaltene Typen zu verwenden, wird zurückgewiesen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-291">Attempting to exchange any other type not in this list will be rejected.</span></span>  
  
   ```csharp
   [DataContract]  
   [KnownType(typeof(PremiumCustomer))]  
   public class Customer  
   {  
       [DataMember]  
       public string FirstName { get; set; }  
  
       [DataMember]  
       public string LastName { get; set; }  
  
       [DataMember]  
       public int CustomerId { get; set; }  
   }  
  
   [DataContract]  
   public class PremiumCustomer : Customer
   {  
       [DataMember]  
       public int AccountId { get; set; }  
   }  
   ```  
  
3. <span data-ttu-id="da2f9-292">Als Nächstes stellen wir die Implementierung für die Dienstschnittstelle bereit.</span><span class="sxs-lookup"><span data-stu-id="da2f9-292">Next, we provide the implementation for the service interface.</span></span>  
  
   ```csharp  
   public class CustomerService : ICustomerService  
   {  
       public Customer GetCustomer(int customerId)  
       {  
           // read from database  
       }  
  
       public bool UpdateCustomer(Customer customer)  
       {  
           // write to database  
       }  
   }  
   ```  
  
4. <span data-ttu-id="da2f9-293">Um den WCF-Dienst auszuführen, müssen Sie einen Endpunkt deklarieren, der diese Dienstschnittstelle an einer bestimmten URL über eine bestimmte WCF-Bindung verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="da2f9-293">To run the WCF service, we need to declare an endpoint that exposes that service interface at a specific URL using a specific WCF binding.</span></span> <span data-ttu-id="da2f9-294">Dies wird üblicherweise erreicht, indem die folgenden Abschnitte in die web.config-Datei des Serverprojekts eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-294">This is typically done by adding the following sections to the server project’s web.config file.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name="Server.CustomerService">  
            <endpoint address="http://localhost:8083/CustomerService"  
                      binding="basicHttpBinding"  
                      contract="Shared.ICustomerService" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
5. <span data-ttu-id="da2f9-295">Der WCF-Dienst kann anschließend mit dem folgenden Code gestartet werden:</span><span class="sxs-lookup"><span data-stu-id="da2f9-295">The WCF service can then be started with the following code:</span></span>  
  
   ```csharp
   ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
       customerServiceHost.Open();  
   ```  
  
     <span data-ttu-id="da2f9-296">Wird dieser ServiceHost gestartet, ermittelt er mithilfe der web.config-Datei den richtigen Vertrag sowie die Bindung und den Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="da2f9-296">When this ServiceHost is started, it uses the web.config file to establish the proper contract, binding and endpoint.</span></span> <span data-ttu-id="da2f9-297">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurieren von Diensten mithilfe von Konfigurationsdateien](./configuring-services-using-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="da2f9-297">For more information about configuration files, see [Configuring Services Using Configuration Files](./configuring-services-using-configuration-files.md).</span></span> <span data-ttu-id="da2f9-298">Diese Art des Serverstarts wird als Selbsthosting bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="da2f9-298">This style of starting the server is known as self-hosting.</span></span> <span data-ttu-id="da2f9-299">Weitere Informationen zu anderen Optionen für das Hosting von WCF-Diensten finden Sie unter [Hostingdienste](./hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="da2f9-299">To learn more about other choices for hosting WCF services, see [Hosting Services](./hosting-services.md).</span></span>  
  
6. <span data-ttu-id="da2f9-300">Die Datei „app.config“ des Clientprojekts muss übereinstimmende Bindungsinformationen für den Dienstendpunkt deklarieren.</span><span class="sxs-lookup"><span data-stu-id="da2f9-300">The client project’s app.config must declare matching binding information for the service’s endpoint.</span></span> <span data-ttu-id="da2f9-301">Die einfachste Möglichkeit, dies in Visual Studio zu erreichen, ist die Verwendung von **Dienstverweis hinzufügen**, die die app.config-Datei automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="da2f9-301">The easiest way to do this in Visual Studio is to use **Add Service Reference**, which will automatically update the app.config file.</span></span> <span data-ttu-id="da2f9-302">Alternativ können dieselben Änderungen manuell hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-302">Alternatively, these same changes can be added manually.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint name="customerservice"  
                    address="http://localhost:8083/CustomerService"  
                    binding="basicHttpBinding"  
                    contract="Shared.ICustomerService"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="da2f9-303">Weitere Informationen zum Verwenden von **Dienstverweis hinzufügen**finden Sie unter Vorgehens [Weise: Hinzufügen, aktualisieren oder Entfernen eines Dienst Verweises](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference).</span><span class="sxs-lookup"><span data-stu-id="da2f9-303">For more information about using **Add Service Reference**, see [How to: Add, Update, or Remove a Service Reference](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference).</span></span>  
  
7. <span data-ttu-id="da2f9-304">Jetzt können wir den WCF-Dienst vom Client aufrufen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-304">Now we can call the WCF service from the client.</span></span> <span data-ttu-id="da2f9-305">Dazu erstellen wir eine Kanalfactory für diesen Dienst, fordern einen Kanal an und rufen direkt die gewünschte Methode im Kanal auf.</span><span class="sxs-lookup"><span data-stu-id="da2f9-305">We do this by creating a channel factory for that service, asking it for a channel, and directly calling the method we want on that channel.</span></span> <span data-ttu-id="da2f9-306">Dies ist möglich, da der Kanal die Dienstschnittstelle implementiert und die zugrunde liegende Logik für Anforderungen/Antworten verwaltet.</span><span class="sxs-lookup"><span data-stu-id="da2f9-306">We can do this because the channel implements the service’s interface and handles the underlying request/reply logic for us.</span></span> <span data-ttu-id="da2f9-307">Der Rückgabewert für diesen Methodenaufruf ist die deserialisierte Kopie der Serverantwort.</span><span class="sxs-lookup"><span data-stu-id="da2f9-307">The return value from that method call is the deserialized copy of the server’s response.</span></span>  
  
   ```csharp
   ChannelFactory<ICustomerService> factory =  
       new ChannelFactory<ICustomerService>("customerservice");  
   ICustomerService service = factory.CreateChannel();  
   Customer customer = service.GetCustomer(42);  
   Console.WriteLine($"  Customer {customer.FirstName} {customer.LastName} received.");
   ```  
  
 <span data-ttu-id="da2f9-308">WCF gibt Objekte vom Server an den Client immer als Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="da2f9-308">Objects returned by WCF from the server to the client are always by value.</span></span> <span data-ttu-id="da2f9-309">Die Objekte sind deserialisierte Kopien der Daten, die vom Server gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-309">The objects are deserialized copies of the data sent by the server.</span></span> <span data-ttu-id="da2f9-310">Der Client kann Methoden für diese lokalen Kopien aufrufen, ohne Gefahr zu laufen, durch Rückruffunktionen Servercode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-310">The client can call methods on these local copies without any danger of invoking server code through callbacks.</span></span>  
  
#### <a name="scenario-2-server-returns-an-object-by-reference"></a><span data-ttu-id="da2f9-311">Szenario 2: Server gibt ein Objekt als Verweis zurück</span><span class="sxs-lookup"><span data-stu-id="da2f9-311">Scenario 2: Server Returns an Object By Reference</span></span>  
 <span data-ttu-id="da2f9-312">Dieses Szenario zeigt, wie der Server ein Objekt als Verweis an den Client zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="da2f9-312">This scenario demonstrates the server providing an object to the client by reference.</span></span> <span data-ttu-id="da2f9-313">In .NET Remoting erfolgt dies für jeden von "MarshalByRefObject" abgeleiteten Typ automatisch, da diese als Verweis serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-313">In .NET Remoting, this is handled automatically for any type derived from MarshalByRefObject, which is serialized by-reference.</span></span> <span data-ttu-id="da2f9-314">Ein Beispiel für dieses Szenario besteht darin, mehreren Clients zu gestatten, unabhängige, sitzungsbasierte, serverseitige Objekte zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="da2f9-314">An example of this scenario is allowing multiple clients to have independent sessionful server-side objects.</span></span> <span data-ttu-id="da2f9-315">Wie bereits erwähnt, gibt der WCF-Dienst Objekte immer als Wert zurück, es gibt also keine direkte Entsprechung für ein Per-Verweis-Objekt. Es ist aber möglich, durch eine Verweissemantik mit Verwendung eines <xref:System.ServiceModel.EndpointAddress10>-Objekts etwas ähnliches zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-315">As previously mentioned, objects returned by a WCF service are always by value, so there is no direct equivalent of a by-reference object, but it is possible to achieve something similar to by-reference semantics using an <xref:System.ServiceModel.EndpointAddress10> object.</span></span> <span data-ttu-id="da2f9-316">Es handelt sich um ein serialisierbares Per-Wert-Objekt, das vom Client dazu verwendet werden kann, ein sitzungsbasiertes Per-Verweis-Objekt auf dem Server abzurufen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-316">This is a serializable by-value object that can be used by the client to obtain a sessionful by-reference object on the server.</span></span> <span data-ttu-id="da2f9-317">Dadurch wird das Szenario ermöglicht, über mehrere Clients mit unabhängigen, sitzungsbasierten, serverseitigen Objekten zu verfügen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-317">This enables the scenario of having multiple clients with independent sessionful server-side objects.</span></span>  
  
1. <span data-ttu-id="da2f9-318">Zunächst muss ein WCF-Dienstvertrag definiert werden, der dem sitzungsbasierten Objekt selbst entspricht.</span><span class="sxs-lookup"><span data-stu-id="da2f9-318">First, we need to define a WCF service contract that corresponds to the sessionful object itself.</span></span>  
  
   ```csharp
   [ServiceContract(SessionMode = SessionMode.Allowed)]  
       public interface ISessionBoundObject  
       {  
           [OperationContract]  
           string GetCurrentValue();  
  
           [OperationContract]  
           void SetCurrentValue(string value);  
       }  
   ```  
  
    > [!TIP]
    > <span data-ttu-id="da2f9-319">Beachten Sie, dass das sitzungsbasierte Objekt mit [ServiceContract] markiert ist, es handelt sich also um eine normale WCF-Dienstschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="da2f9-319">Notice that the sessionful object is marked with [ServiceContract], making it a normal WCF service interface.</span></span> <span data-ttu-id="da2f9-320">Durch Festlegen der SessionMode-Eigenschaft wird angegeben, dass es sich um einen sitzungsbasierten Dienst handelt.</span><span class="sxs-lookup"><span data-stu-id="da2f9-320">Setting the SessionMode property indicates it will be a sessionful service.</span></span> <span data-ttu-id="da2f9-321">In WCF ist eine Sitzung eine Möglichkeit, mehrere Nachrichten zuzuordnen, die zwischen zwei Endpunkten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-321">In WCF, a session is a way of correlating multiple messages sent between two endpoints.</span></span> <span data-ttu-id="da2f9-322">Dies bedeutet, dass zwischen dem Client und dem Server eine Sitzung eingerichtet wird, sobald der Client eine Verbindung mit diesem Dienst hergestellt hat.</span><span class="sxs-lookup"><span data-stu-id="da2f9-322">This means that once a client obtains a connection to this service, a session will be established between the client and the server.</span></span> <span data-ttu-id="da2f9-323">Der Client verwendet eine einzelne eindeutige Instanz des serverseitigen Objekts für alle Interaktionen innerhalb dieser einzelnen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="da2f9-323">The client will use a single unique instance of the server-side object for all its interactions within this single session.</span></span>  
  
2. <span data-ttu-id="da2f9-324">Als Nächstes muss die Implementierung dieser Schnittstelle bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-324">Next, we need to provide the implementation of this service interface.</span></span> <span data-ttu-id="da2f9-325">Durch eine Kennzeichnung mit [ServiceBehavior] und Festlegen von InstanceContextMode wird WCF angewiesen, eine eindeutige Instanz dieses Typs für jede Sitzung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-325">By denoting it with [ServiceBehavior] and setting the InstanceContextMode, we tell WCF we want to use a unique instance of this type for an each session.</span></span>  
  
   ```csharp
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
       public class MySessionBoundObject : ISessionBoundObject  
       {  
           private string _value;  
  
           public string GetCurrentValue()  
           {  
               return _value;  
           }  
  
           public void SetCurrentValue(string val)  
           {  
               _value = val;  
           }  
  
       }  
   ```  
  
3. <span data-ttu-id="da2f9-326">Nun benötigen wir eine Möglichkeit, eine Instanz dieses sitzungsbasierten Objekts abzurufen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-326">Now we need a way to obtain an instance of this sessionful object.</span></span> <span data-ttu-id="da2f9-327">Hierzu erstellen wir eine weitere WCF-Dienstschnittstelle, die ein EndpointAddress10-Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="da2f9-327">We do this by creating another WCF service interface that returns an EndpointAddress10 object.</span></span> <span data-ttu-id="da2f9-328">Dies ist eine serialisierbare Form eines Endpunkts, die vom Server dazu verwendet werden kann, ein sitzungsbasiertes Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-328">This is a serializable form of an endpoint that the client can use to create the sessionful object.</span></span>  
  
   ```csharp
   [ServiceContract]  
       public interface ISessionBoundFactory  
       {  
           [OperationContract]  
           EndpointAddress10 GetInstanceAddress();  
       }  
   ```  
  
     <span data-ttu-id="da2f9-329">Und wir implementieren diesen WCF-Dienst:</span><span class="sxs-lookup"><span data-stu-id="da2f9-329">And we implement this WCF service:</span></span>  
  
   ```csharp
   public class SessionBoundFactory : ISessionBoundFactory  
       {  
           public static ChannelFactory<ISessionBoundObject> _factory =
               new ChannelFactory<ISessionBoundObject>("sessionbound");  

           public SessionBoundFactory()  
           {  
           }  
  
           public EndpointAddress10 GetInstanceAddress()  
           {  
               IClientChannel channel = (IClientChannel)_factory.CreateChannel();  
               return EndpointAddress10.FromEndpointAddress(channel.RemoteAddress);  
           }  
       }  
   ```  
  
     <span data-ttu-id="da2f9-330">Diese Implementierung verwaltet eine Singleton-Kanalfactory, um sitzungsbasierte Objekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-330">This implementation maintains a singleton channel factory to create sessionful objects.</span></span> <span data-ttu-id="da2f9-331">Beim Aufruf von GetInstanceAddress() werden ein Kanal sowie ein EndpointAddress10-Objekt erstellt, das effektiv auf die diesem Kanal zugeordnete Remoteadresse verweist.</span><span class="sxs-lookup"><span data-stu-id="da2f9-331">When GetInstanceAddress() is called, it creates a channel and creates an EndpointAddress10 object that effectively points to the remote address associated with this channel.</span></span> <span data-ttu-id="da2f9-332">EndpointAddress10 ist einfach ein Datentyp, der als Wert an den Client zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="da2f9-332">EndpointAddress10 is simply a data type that can be returned to the client by-value.</span></span>  
  
4. <span data-ttu-id="da2f9-333">Die Konfigurationsdatei des Servers muss durch Ausführen von zwei Schritten geändert werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="da2f9-333">We need to modify the server’s configuration file by doing the following two things as shown in the example below:</span></span>  
  
    1. <span data-ttu-id="da2f9-334">Deklarieren Sie einen \<client> Abschnitt, in dem der Endpunkt für das Sitzungs basierte Objekt beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="da2f9-334">Declare a \<client> section that describes the endpoint for the sessionful object.</span></span> <span data-ttu-id="da2f9-335">Dies ist notwendig, da der Server in diesem Fall auch als Client fungiert.</span><span class="sxs-lookup"><span data-stu-id="da2f9-335">This is necessary because the server also acts as a client in this situation.</span></span>  
  
    2. <span data-ttu-id="da2f9-336">Deklarieren Sie Endpunkte für die Factory und das sitzungsbasierte Objekt.</span><span class="sxs-lookup"><span data-stu-id="da2f9-336">Declare endpoints for the factory and sessionful object.</span></span> <span data-ttu-id="da2f9-337">Dies ist erforderlich, damit der Client mit den Dienstendpunkten kommunizieren kann, um EndpointAddress10 abzurufen und den sitzungsbasierten Kanal zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-337">This is necessary to allow the client to communicate with the service endpoints to acquire the EndpointAddress10 and to create the sessionful channel.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
         <client>  
          <endpoint name="sessionbound"  
                    address="net.tcp://localhost:8081/SessionBoundObject"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundObject"/>  
        </client>  
        <services>  
          <service name="Server.CustomerService">  
            <endpoint address="http://localhost:8083/CustomerService"  
                      binding="basicHttpBinding"  
                      contract="Shared.ICustomerService" />  
          </service>  
          <service name="Server.MySessionBoundObject">  
            <endpoint address="net.tcp://localhost:8081/SessionBoundObject"  
                      binding="netTcpBinding"  
                      contract="Shared.ISessionBoundObject" />  
          </service>  
          <service name="Server.SessionBoundFactory">  
            <endpoint address="net.tcp://localhost:8081/SessionBoundFactory"  
                      binding="netTcpBinding"  
                      contract="Shared.ISessionBoundFactory" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="da2f9-338">Anschließend können diese Dienste gestartet werden:</span><span class="sxs-lookup"><span data-stu-id="da2f9-338">And then we can start these services:</span></span>  
  
   ```csharp
   ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
   factoryHost.Open();  
  
   ServiceHost sessionHost = new ServiceHost(typeof(MySessionBoundObject));  
   sessionHost.Open();  
   ```  
  
5. <span data-ttu-id="da2f9-339">Wir konfigurieren den Client, indem dieselben Endpunkte in der zugehörigen app.config-Datei des Projekts deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-339">We configure the client by declaring these same endpoints in its project’s app.config file.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint name="customerservice"  
                    address="http://localhost:8083/CustomerService"  
                    binding="basicHttpBinding"  
                    contract="Shared.ICustomerService"/>  
          <endpoint name="sessionbound"  
                    address="net.tcp://localhost:8081/SessionBoundObject"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundObject"/>  
          <endpoint name="factory"  
                    address="net.tcp://localhost:8081/SessionBoundFactory"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundFactory"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
6. <span data-ttu-id="da2f9-340">Zum Erstellen und Nutzen dieses sitzungsbasierten Objekts muss der Client die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="da2f9-340">In order to create and use this sessionful object, the client must do the following steps:</span></span>  
  
    1. <span data-ttu-id="da2f9-341">Erstellen eines Kanals zum ISessionBoundFactory-Dienst.</span><span class="sxs-lookup"><span data-stu-id="da2f9-341">Create a channel to the ISessionBoundFactory service.</span></span>  
  
    2. <span data-ttu-id="da2f9-342">Verwenden dieses Kanals, um den Dienst zum Abrufen von EndpointAddress10 aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-342">Use that channel to invoke that service to obtain an EndpointAddress10.</span></span>  
  
    3. <span data-ttu-id="da2f9-343">Verwenden von EndpointAddress10 zum Erstellen eines Kanals für den Abruf eines sitzungsbasierten Objekts.</span><span class="sxs-lookup"><span data-stu-id="da2f9-343">Use the EndpointAddress10 to create a channel to obtain a sessionful object.</span></span>  
  
    4. <span data-ttu-id="da2f9-344">Interaktion mit dem sitzungsbasierten Objekt, um zu veranschaulichen, dass auch bei mehreren Aufrufen dieselbe Instanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="da2f9-344">Interact with the sessionful object to demonstrate it remains the same instance across multiple calls.</span></span>  
  
   ```csharp
   ChannelFactory<ISessionBoundFactory> channelFactory =
       new ChannelFactory<ISessionBoundFactory>("factory");  
   ISessionBoundFactory sessionFactory = channelFactory.CreateChannel();  
  
   EndpointAddress10 address1 = sessionFactory.GetInstanceAddress();  
   EndpointAddress10 address2 = sessionFactory.GetInstanceAddress();  
  
   ChannelFactory<ISessionBoundObject> sessionObjectFactory1 =
       new ChannelFactory<ISessionBoundObject>(new NetTcpBinding(),
                                               address1.ToEndpointAddress());  
   ChannelFactory<ISessionBoundObject> sessionObjectFactory2 =
       new ChannelFactory<ISessionBoundObject>(new NetTcpBinding(),
                                               address2.ToEndpointAddress());  
  
   ISessionBoundObject sessionInstance1 = sessionObjectFactory1.CreateChannel();  
   ISessionBoundObject sessionInstance2 = sessionObjectFactory2.CreateChannel();  
  
   sessionInstance1.SetCurrentValue("Hello");  
   sessionInstance2.SetCurrentValue("World");  
  
   if (sessionInstance1.GetCurrentValue() == "Hello" &&  
       sessionInstance2.GetCurrentValue() == "World")  
   {  
       Console.WriteLine("sessionful server object works as expected");  
   }  
   ```  
  
 <span data-ttu-id="da2f9-345">WCF gibt Objekte immer als Wert zurück. Es ist jedoch möglich, die entsprechende Verweissemantik durch Verwenden von EndpointAddress10 zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-345">WCF always returns objects by value, but it is possible to support the equivalent of by-reference semantics through the use of EndpointAddress10.</span></span> <span data-ttu-id="da2f9-346">Dies ermöglicht dem Client, eine sitzungsbasierte WCF-Dienstinstanz anzufordern, um anschließend mit dieser wie mit jedem anderen WCF-Dienst zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="da2f9-346">This permits the client to request a sessionful WCF service instance, after which it can interact with it like any other WCF service.</span></span>  
  
#### <a name="scenario-3-client-sends-server-a-by-value-instance"></a><span data-ttu-id="da2f9-347">Szenario 3: Client sendet eine Per-Wert-Instanz an den Server</span><span class="sxs-lookup"><span data-stu-id="da2f9-347">Scenario 3: Client Sends Server a By-Value Instance</span></span>  
 <span data-ttu-id="da2f9-348">Dieses Szenario zeigt, wie der Client eine nicht primitive Objektinstanz als Wert an den Server sendet.</span><span class="sxs-lookup"><span data-stu-id="da2f9-348">This scenario demonstrates the client sending a non-primitive object instance to the server by value.</span></span> <span data-ttu-id="da2f9-349">Da WCF Objekte nur als Wert übergibt, veranschaulicht dieses Szenario die normale WCF-Verwendung.</span><span class="sxs-lookup"><span data-stu-id="da2f9-349">Because WCF only sends objects by value, this scenario demonstrates normal WCF usage.</span></span>  
  
1. <span data-ttu-id="da2f9-350">Verwenden Sie den gleichen WCF-Dienst wie in Szenario 1.</span><span class="sxs-lookup"><span data-stu-id="da2f9-350">Use the same WCF Service from Scenario 1.</span></span>  
  
2. <span data-ttu-id="da2f9-351">Verwenden Sie den Client, um ein neues Per-Wert-Objekt (Customer) sowie einen Kanal zur Kommunikation mit dem ICustomerService-Dienst zu erstellen und das Objekt an diesen zu senden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-351">Use the client to create a new by-value object (Customer), create a channel to communicate with the ICustomerService service, and send the object to it.</span></span>  
  
   ```csharp
   ChannelFactory<ICustomerService> factory =  
       new ChannelFactory<ICustomerService>("customerservice");  
   ICustomerService service = factory.CreateChannel();  
   PremiumCustomer customer = new PremiumCustomer {
   FirstName = "Bob",
   LastName = "Jones",
   CustomerId = 43,
   AccountId = 99};  
   bool success = service.UpdateCustomer(customer);  
   Console.WriteLine($"  Server returned {success}.");
   ```  
  
     <span data-ttu-id="da2f9-352">Das Customer-Objekt wird serialisiert und an den Dienst gesendet und anschließend in eine neue Kopie dieses Objekts deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="da2f9-352">The customer object will be serialized, and sent to the server, where it is deserialized into a new copy of that object.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="da2f9-353">Dieser Code zeigt auch das Senden eines abgeleiteten Typs (PremiumCustomer).</span><span class="sxs-lookup"><span data-stu-id="da2f9-353">This code also illustrates sending a derived type (PremiumCustomer).</span></span> <span data-ttu-id="da2f9-354">Die Dienstschnittstelle erwartet ein Customer-Objekt, aber das [KnownType]-Attribut für die Customer-Klasse zeigt an, dass auch PremiumCustomer zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="da2f9-354">The service interface expects a Customer object, but the [KnownType] attribute on the Customer class indicated PremiumCustomer was also allowed.</span></span> <span data-ttu-id="da2f9-355">WCF lässt keine Serialisierung oder Deserialisierung von anderen Typen über diese Dienstschnittstelle zu.</span><span class="sxs-lookup"><span data-stu-id="da2f9-355">WCF will fail any attempt to serialize or deserialize any other type through this service interface.</span></span>  
  
 <span data-ttu-id="da2f9-356">Der normale WCF-Datenaustausch erfolgt per Wert.</span><span class="sxs-lookup"><span data-stu-id="da2f9-356">Normal WCF exchanges of data are by value.</span></span> <span data-ttu-id="da2f9-357">Auf diese Weise wird sichergestellt, dass Methodenaufrufe für diese Datenobjekte nur lokal erfolgen – es wird kein Code auf der anderen Ebene aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-357">This guarantees that invoking methods on one of these data objects executes only locally – it will not invoke code on the other tier.</span></span> <span data-ttu-id="da2f9-358">Obwohl es möglich ist *, vom Server zurückgegebene* durch Verweis Objekte zu erreichen, ist es nicht möglich, dass ein Client ein per-Verweis-Objekt *an* den Server übergibt.</span><span class="sxs-lookup"><span data-stu-id="da2f9-358">While it is possible to achieve something like by-reference objects returned *from* the server, it is not possible for a client to pass a by-reference object *to* the server.</span></span> <span data-ttu-id="da2f9-359">Ist zwischen Client und Server eine Konversation in beide Richtungen erforderlich, kann dies in WCF mit einem Duplexdienst erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-359">A scenario that requires a conversation back and forth between client and server can be achieved in WCF using a duplex service.</span></span> <span data-ttu-id="da2f9-360">Weitere Informationen finden Sie unter [Duplex Dienste](./feature-details/duplex-services.md).</span><span class="sxs-lookup"><span data-stu-id="da2f9-360">For more information, see [Duplex Services](./feature-details/duplex-services.md).</span></span>  
  
## <a name="summary"></a><span data-ttu-id="da2f9-361">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="da2f9-361">Summary</span></span>  
 <span data-ttu-id="da2f9-362">.NET Remoting ist ein Kommunikationsframework, das ausschließlich in vollständig vertrauenswürdigen Umgebungen eingesetzt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="da2f9-362">.NET Remoting is a communication framework intended to be used only within fully-trusted environments.</span></span> <span data-ttu-id="da2f9-363">Es handelt sich um ein Legacy-Produkt, das nur zur Bereitstellung von Abwärtskompatibilität unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="da2f9-363">It is a legacy product and supported only for backward compatibility.</span></span> <span data-ttu-id="da2f9-364">Es sollte nicht verwendet werden, um neue Anwendungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-364">It should not be used to build new applications.</span></span> <span data-ttu-id="da2f9-365">Im Gegensatz dazu wurde WCF unter Berücksichtigung von Sicherheitsaspekten entworfen und wird für neue und vorhandene Anwendungen empfohlen.</span><span class="sxs-lookup"><span data-stu-id="da2f9-365">Conversely, WCF was designed with security in mind and is recommended for new and existing applications.</span></span> <span data-ttu-id="da2f9-366">Microsoft empfiehlt, vorhandene Remoting-Anwendungen zu migrieren, um stattdessen WCF oder die ASP.NET-Web-API zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="da2f9-366">Microsoft recommends that existing Remoting applications be migrated to use WCF or ASP.NET Web API instead.</span></span>
