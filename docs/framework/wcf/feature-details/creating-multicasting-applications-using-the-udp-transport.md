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
# <a name="creating-multicasting-applications-using-the-udp-transport"></a>Erstellen von Multicastanwendungen mithilfe des UDP-Transports
Multicastanwendungen senden kleine Nachrichten gleichzeitig an eine große Anzahl von Empfängern, ohne dass eine Punkt-zu-Punkt-Verbindung eingerichtet werden muss. Bei diesen Anwendungen hat Geschwindigkeit Vorrang vor Zuverlässigkeit. Das heißt, es ist wichtiger, Daten zeitgerecht zu senden, als sicherzustellen, dass eine Nachricht auch tatsächlich empfangen wird. WCF unterstützt jetzt mit der <xref:System.ServiceModel.UdpBinding> das Schreiben von Multicastanwendungen. Dieser Transport ist in Szenarien nützlich, in denen ein Dienst kleine Nachrichten an eine große Anzahl von Clients gleichzeitig senden muss. Eine Börsenticker-Anwendung ist ein Beispiel für einen solchen Dienst.  
  
## <a name="implementing-a-multicast-application"></a>Implementieren einer Multicastanwendung  
 Um eine Multicastanwendung zu implementieren, definieren Sie einen Dienstvertrag und implementieren diesen für jede Softwarekomponente, die auf die Multicastnachrichten antworten muss. Zum Beispiel kann eine Börsenticker-Anwendung einen Dienstvertrag definieren:  
  
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
  
 Jede Anwendung, die Multicastnachrichten empfangen möchte, muss einen Dienst hosten, der diese Schnittstelle verfügbar macht.  Das folgende Codebeispiel veranschaulicht, wie Multicastnachrichten empfangen werden:  
  
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
  
 Die Anwendung gibt die UDP-Adresse an, an der alle Dienste lauschen. Ein neuer <xref:System.ServiceModel.ServiceHost> wird erstellt, und mit der <xref:System.ServiceModel.UdpBinding> wird ein Dienstendpunkt verfügbar gemacht. Anschließend wird der <xref:System.ServiceModel.ServiceHost> geöffnet, und dieser beginnt mit dem Lauschen auf eingehende Meldungen.  
  
 In diesem Szenariotyp werden Multicastnachrichten tatsächlich vom Client gesendet. Jeder Dienst, der an der richtigen UDP-Adresse lauscht, empfängt die Multicastnachrichten. Im Folgenden finden Sie ein Beispiel für einen Client, der Multicastnachrichten sendet:  
  
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
  
 Dieser Code generiert Börseninformationen und verwendet dann den Dienstvertrag IStockTicker, um Multicastnachrichten an Aufrufdienste zu senden, die an der richtigen UDP-Adresse lauschen.  
  
### <a name="udp-and-reliable-messaging"></a>UDP und zuverlässiges Messaging  
  Da es sich bei UDP um ein einfaches Protokoll handelt, unterstützt die UDP-Bindung kein zuverlässiges Messaging. Wenn Sie sicherstellen müssen, dass Nachrichten von einem Remoteendpunkt empfangen werden, verwenden Sie einen Transport, der zuverlässiges Messaging unterstützt, z. B. HTTP oder TCP. Weitere Informationen zu zuverlässigem Messaging finden Sie unter <https://go.microsoft.com/fwlink/?LinkId=231830> .  
  
### <a name="two-way-multicast-messaging"></a>Bidirektionales Multicastmessaging  
 Während Multicastnachrichten im Allgemeinen unidirektional sind, unterstützt UdpBinding den Austausch von Anforderungs-/Antwortnachrichten. Die mithilfe des UDP-Transports gesendeten Nachrichten enthalten eine Absender- und eine Empfängeradresse. Besondere Sorgfalt erfordert die Absenderadresse, da sie während der Übertragung möglicherweise böswillig geändert wurde.  Die Adresse kann mithilfe des folgenden Codes überprüft werden:  
  
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
  
 Der Code überprüft das erste Byte der Absenderadresse, um zu ermitteln, ob sie 0xE0 enthält, was bedeutet, dass es sich um eine Multicastadresse handelt.  
  
### <a name="security-considerations"></a>Überlegungen zur Sicherheit  
 Beim Lauschen auf Multicastnachrichten wird ein ICMP-Paket an den Router gesendet, um ihn davon in Kenntnis setzen, ob an der Multicastadresse gelauscht wird. Jeder Benutzer im lokalen Subnetz mit entsprechender Berechtigung kann auf diese Pakettypen lauschen und ermitteln, an welcher Multicastadresse und welchem Port gelauscht wird.  
  
 Aus Sicherheitsgründen sollte die IP-Adresse des Absenders nicht verwendet werden. Diese Information kann gespooft sein, sodass eine Anwendung Antworten an den falschen Computer sendet. Eine Möglichkeit, dieses Risiko abzuschwächen, ist das Aktivieren der Sicherheit auf Nachrichtenebene. Auf Netzwerkebene kann auch Internetprotokollsicherheit (Internet Protocol Security, IPSec) und/oder Netzwerkzugriffsschutz (Network Access Protection, NAP) verwendet werden.
