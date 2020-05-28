---
title: Erstellen von Multicastanwendungen mithilfe des UDP-Transports
ms.date: 03/30/2017
ms.assetid: 7485154a-6e85-4a67-a9d4-9008e741d4df
ms.openlocfilehash: 40944129ce3b01d8422d5aba4cfbf913c56265ed
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144629"
---
# <a name="creating-multicasting-applications-using-the-udp-transport"></a><span data-ttu-id="66272-102">Erstellen von Multicastanwendungen mithilfe des UDP-Transports</span><span class="sxs-lookup"><span data-stu-id="66272-102">Creating Multicasting Applications using the UDP Transport</span></span>
<span data-ttu-id="66272-103">Multicastanwendungen senden kleine Nachrichten gleichzeitig an eine große Anzahl von Empfängern, ohne dass eine Punkt-zu-Punkt-Verbindung eingerichtet werden muss.</span><span class="sxs-lookup"><span data-stu-id="66272-103">Multicasting applications send small messages to a large number of recipients at the same time without the need to establish point to point connections.</span></span> <span data-ttu-id="66272-104">Bei diesen Anwendungen hat Geschwindigkeit Vorrang vor Zuverlässigkeit.</span><span class="sxs-lookup"><span data-stu-id="66272-104">The emphasis of such applications is speed over reliability.</span></span> <span data-ttu-id="66272-105">Das heißt, es ist wichtiger, Daten zeitgerecht zu senden, als sicherzustellen, dass eine Nachricht auch tatsächlich empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="66272-105">In other words, it is more important to send timely data than to ensure any specific message is actually received.</span></span> <span data-ttu-id="66272-106">WCF unterstützt jetzt mit der <xref:System.ServiceModel.UdpBinding> das Schreiben von Multicastanwendungen.</span><span class="sxs-lookup"><span data-stu-id="66272-106">WCF now supports writing multicasting applications using the <xref:System.ServiceModel.UdpBinding>.</span></span> <span data-ttu-id="66272-107">Dieser Transport ist in Szenarien nützlich, in denen ein Dienst kleine Nachrichten an eine große Anzahl von Clients gleichzeitig senden muss.</span><span class="sxs-lookup"><span data-stu-id="66272-107">This transport is useful in scenarios where a service needs to send out small messages to a number of clients simultaneously.</span></span> <span data-ttu-id="66272-108">Eine Börsenticker-Anwendung ist ein Beispiel für einen solchen Dienst.</span><span class="sxs-lookup"><span data-stu-id="66272-108">A stock ticker application is an example of such a service.</span></span>  
  
## <a name="implementing-a-multicast-application"></a><span data-ttu-id="66272-109">Implementieren einer Multicastanwendung</span><span class="sxs-lookup"><span data-stu-id="66272-109">Implementing a Multicast Application</span></span>  
 <span data-ttu-id="66272-110">Um eine Multicastanwendung zu implementieren, definieren Sie einen Dienstvertrag und implementieren diesen für jede Softwarekomponente, die auf die Multicastnachrichten antworten muss.</span><span class="sxs-lookup"><span data-stu-id="66272-110">To implement a multicast application, define a service contract and for each software component that needs to respond to the multicast messages, implement the service contract.</span></span> <span data-ttu-id="66272-111">Zum Beispiel kann eine Börsenticker-Anwendung einen Dienstvertrag definieren:</span><span class="sxs-lookup"><span data-stu-id="66272-111">For example, a stock ticker application might define a service contract:</span></span>  
  
```csharp
// Shared contracts between the client and the service  
[ServiceContract]
interface IStockTicker
{
    [OperationContract(IsOneWay = true)]
    void SendStockInfo(StockInfo[] stockInfo);
}

[DataContract]
class StockInfo
{
    [DataMember]
    public string Symbol;

    [DataMember]
    public float Price;

    public StockInfo(string symbol, float price)
    {
        this.Symbol = symbol;
        this.Price = price;
    }
}
```  
  
 <span data-ttu-id="66272-112">Jede Anwendung, die Multicastnachrichten empfangen möchte, muss einen Dienst hosten, der diese Schnittstelle verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="66272-112">Each application that wants to receive multicast messages must host a service that exposes this interface.</span></span>  <span data-ttu-id="66272-113">Das folgende Codebeispiel veranschaulicht, wie Multicastnachrichten empfangen werden:</span><span class="sxs-lookup"><span data-stu-id="66272-113">For example, here is a code sample that illustrates how to receive multicast messages:</span></span>  
  
```csharp
// Service Address
string serviceAddress = "soap.udp://224.0.0.1:40000";
// Binding
UdpBinding myBinding = new UdpBinding();
// Host
ServiceHost host = new ServiceHost(typeof(StockTickerService), new Uri(serviceAddress));
// Add service endpoint
host.AddServiceEndpoint(typeof(IStockTicker), myBinding, string.Empty);
// Openup the service host
host.Open();

Console.WriteLine("Start receiving stock information");
Console.ReadLine();
```  
  
 <span data-ttu-id="66272-114">Die Anwendung gibt die UDP-Adresse an, an der alle Dienste lauschen.</span><span class="sxs-lookup"><span data-stu-id="66272-114">The application specifies the UDP address that all services will be listening on.</span></span> <span data-ttu-id="66272-115">Ein neuer <xref:System.ServiceModel.ServiceHost> wird erstellt, und mit der <xref:System.ServiceModel.UdpBinding> wird ein Dienstendpunkt verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="66272-115">A new <xref:System.ServiceModel.ServiceHost> is created and a service endpoint is exposed using the <xref:System.ServiceModel.UdpBinding>.</span></span> <span data-ttu-id="66272-116">Anschließend wird der <xref:System.ServiceModel.ServiceHost> geöffnet, und dieser beginnt mit dem Lauschen auf eingehende Meldungen.</span><span class="sxs-lookup"><span data-stu-id="66272-116">The <xref:System.ServiceModel.ServiceHost> is then opened and will start listening for incoming messages.</span></span>  
  
 <span data-ttu-id="66272-117">In diesem Szenariotyp werden Multicastnachrichten tatsächlich vom Client gesendet.</span><span class="sxs-lookup"><span data-stu-id="66272-117">In this type of a scenario it is the client that actually sends out multicast messages.</span></span> <span data-ttu-id="66272-118">Jeder Dienst, der an der richtigen UDP-Adresse lauscht, empfängt die Multicastnachrichten.</span><span class="sxs-lookup"><span data-stu-id="66272-118">Each service that is listening at the correct UDP address will receive the multicast messages.</span></span> <span data-ttu-id="66272-119">Im Folgenden finden Sie ein Beispiel für einen Client, der Multicastnachrichten sendet:</span><span class="sxs-lookup"><span data-stu-id="66272-119">Here is an example of a client that sends out multicast messages:</span></span>  
  
```csharp
// Multicast Address
string serviceAddress = "soap.udp://224.0.0.1:40000";

// Binding
UdpBinding myBinding = new UdpBinding();

// Channel factory
ChannelFactory<IStockTicker> factory
    = new ChannelFactory<IStockTicker>(myBinding,
                new EndpointAddress(serviceAddress));

// Call service
IStockTicker proxy = factory.CreateChannel();

while (true)
{
    // This will continue to mulicast stock information
    proxy.SendStockInfo(GetStockInfo());
    Console.WriteLine($"sent stock info at {DateTime.Now}");
    // Wait for one second before sending another update
    System.Threading.Thread.Sleep(new TimeSpan(0, 0, 1));
}
```  
  
 <span data-ttu-id="66272-120">Dieser Code generiert Börseninformationen und verwendet dann den Dienstvertrag IStockTicker, um Multicastnachrichten an Aufrufdienste zu senden, die an der richtigen UDP-Adresse lauschen.</span><span class="sxs-lookup"><span data-stu-id="66272-120">This code generates stock information and then uses the service contract IStockTicker to send multicast messages to call services listening on the correct UDP address.</span></span>  
  
### <a name="udp-and-reliable-messaging"></a><span data-ttu-id="66272-121">UDP und zuverlässiges Messaging</span><span class="sxs-lookup"><span data-stu-id="66272-121">UDP and Reliable Messaging</span></span>  
  <span data-ttu-id="66272-122">Da es sich bei UDP um ein einfaches Protokoll handelt, unterstützt die UDP-Bindung kein zuverlässiges Messaging.</span><span class="sxs-lookup"><span data-stu-id="66272-122">The UDP binding does not support reliable messaging because of the lightweight nature of the UDP protocol.</span></span> <span data-ttu-id="66272-123">Wenn Sie sicherstellen müssen, dass Nachrichten von einem Remoteendpunkt empfangen werden, verwenden Sie einen Transport, der zuverlässiges Messaging unterstützt, z. B. HTTP oder TCP.</span><span class="sxs-lookup"><span data-stu-id="66272-123">If you need to confirm that messages are received by a remote endpoint, use a transport that supports reliable messaging like  HTTP or TCP.</span></span> <span data-ttu-id="66272-124">Weitere Informationen zu zuverlässigem Messaging finden Sie unter <https://go.microsoft.com/fwlink/?LinkId=231830> .</span><span class="sxs-lookup"><span data-stu-id="66272-124">For more information about reliable messaging, see <https://go.microsoft.com/fwlink/?LinkId=231830>.</span></span>  
  
### <a name="two-way-multicast-messaging"></a><span data-ttu-id="66272-125">Bidirektionales Multicastmessaging</span><span class="sxs-lookup"><span data-stu-id="66272-125">Two-way Multicast Messaging</span></span>  
 <span data-ttu-id="66272-126">Während Multicastnachrichten im Allgemeinen unidirektional sind, unterstützt UdpBinding den Austausch von Anforderungs-/Antwortnachrichten.</span><span class="sxs-lookup"><span data-stu-id="66272-126">While multicast messages are generally one-way, the UdpBinding does support request/reply message exchange.</span></span> <span data-ttu-id="66272-127">Die mithilfe des UDP-Transports gesendeten Nachrichten enthalten eine Absender- und eine Empfängeradresse.</span><span class="sxs-lookup"><span data-stu-id="66272-127">Messages sent using the UDP transport contain both a From and To address.</span></span> <span data-ttu-id="66272-128">Besondere Sorgfalt erfordert die Absenderadresse, da sie während der Übertragung möglicherweise böswillig geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="66272-128">Care must be taken when using the From address as it could be maliciously changed en-route.</span></span>  <span data-ttu-id="66272-129">Die Adresse kann mithilfe des folgenden Codes überprüft werden:</span><span class="sxs-lookup"><span data-stu-id="66272-129">The address can be checked using the following code:</span></span>  
  
```csharp
if (address.AddressFamily == AddressFamily.InterNetwork)
{
    // IPv4
    byte[] addressBytes = address.GetAddressBytes();
    return ((addressBytes[0] & 0xE0) == 0xE0);
}
else
{
    // IPv6
    return address.IsIPv6Multicast;
}
```  
  
 <span data-ttu-id="66272-130">Der Code überprüft das erste Byte der Absenderadresse, um zu ermitteln, ob sie 0xE0 enthält, was bedeutet, dass es sich um eine Multicastadresse handelt.</span><span class="sxs-lookup"><span data-stu-id="66272-130">This code checks the first byte of the From address to see if it contains 0xE0 which signifies that the address is a multi-cast address.</span></span>  
  
### <a name="security-considerations"></a><span data-ttu-id="66272-131">Überlegungen zur Sicherheit</span><span class="sxs-lookup"><span data-stu-id="66272-131">Security Considerations</span></span>  
 <span data-ttu-id="66272-132">Beim Lauschen auf Multicastnachrichten wird ein ICMP-Paket an den Router gesendet, um ihn davon in Kenntnis setzen, ob an der Multicastadresse gelauscht wird.</span><span class="sxs-lookup"><span data-stu-id="66272-132">When listening for multicast messages an ICMP packet is sent to the router notifying it you are listening on the multicast address.</span></span> <span data-ttu-id="66272-133">Jeder Benutzer im lokalen Subnetz mit entsprechender Berechtigung kann auf diese Pakettypen lauschen und ermitteln, an welcher Multicastadresse und welchem Port gelauscht wird.</span><span class="sxs-lookup"><span data-stu-id="66272-133">Anyone on the local subnet who has permissions could listen for these types of packets and determine which multicast address and port you are listening on.</span></span>  
  
 <span data-ttu-id="66272-134">Aus Sicherheitsgründen sollte die IP-Adresse des Absenders nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="66272-134">Do not use the IP address of the sender for any security purposes.</span></span> <span data-ttu-id="66272-135">Diese Information kann gespooft sein, sodass eine Anwendung Antworten an den falschen Computer sendet.</span><span class="sxs-lookup"><span data-stu-id="66272-135">This information can be spoofed and can cause an application to send responses to the wrong machine.</span></span> <span data-ttu-id="66272-136">Eine Möglichkeit, dieses Risiko abzuschwächen, ist das Aktivieren der Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="66272-136">One way to mitigate this threat is to enable message level security.</span></span> <span data-ttu-id="66272-137">Auf Netzwerkebene kann auch Internetprotokollsicherheit (Internet Protocol Security, IPSec) und/oder Netzwerkzugriffsschutz (Network Access Protection, NAP) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="66272-137">At the network level IPSec  (Internet Protocol Security) and/or NAP (Network Access Protection) could also be used.</span></span>
