---
title: "Erstellen von Multicastanwendungen mithilfe des UDP-Transports | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7485154a-6e85-4a67-a9d4-9008e741d4df
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Erstellen von Multicastanwendungen mithilfe des UDP-Transports
Multicastanwendungen senden kleine Nachrichten gleichzeitig an eine große Anzahl von Empfängern, ohne dass eine Punkt\-zu\-Punkt\-Verbindung eingerichtet werden muss.Der Schwerpunkt dieser Anwendungen ist Geschwindigkeit vor Zuverlässigkeit.Das heißt, es ist wichtiger, Daten zeitgerecht zu senden als sicherzustellen, dass eine Nachricht auch tatsächlich empfangen wird.WCF unterstützt jetzt das Schreiben von Multicastanwendungen mit <xref:System.ServiceModel.UdpBinding>.Dieser Transport ist in Szenarien nützlich, in denen ein Dienst kleine Nachrichten an eine große Anzahl von Clients gleichzeitig aussenden muss.Eine Börsenticker\-Anwendung ist ein Beispiel eines solchen Diensts.  
  
## Implementieren einer Multicastanwendung  
 Um eine Multicastanwendung zu implementieren, definieren Sie einen Dienstvertrag und implementieren für jede Softwarekomponente, die auf die Multicastmeldungen antworten muss, den Dienstvertrag.Zum Beispiel kann eine Börsenticker\-Anwendung einen Dienstvertrag definieren:  
  
```  
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
  
 Jede Anwendung, die Multicastmeldungen empfangen möchte, muss einen Dienst hosten, der diese Schnittstelle verfügbar macht.Das folgende Beispiel zeigt ein Codebeispiel, das veranschaulicht, wie Multicastmeldungen empfangen werden:  
  
```  
// Service Address  
            string serviceAddress = "soap.udp://224.0.0.1:40000";  
            // Binding  
            UdpBinding myBinding = new UdpBinding();  
            // Host  
            ServiceHost host = new ServiceHost(typeof  
                (StockTickerService), new Uri(serviceAddress));  
            // Add service endpoint  
            host.AddServiceEndpoint(typeof(IStockTicker), myBinding, string.Empty);  
            // Openup the service host  
            host.Open();  
  
            Console.WriteLine("Start receiving stock information");  
            Console.ReadLine();  
  
```  
  
 Die Anwendung gibt die UDP\-Adresse an, auf die alle Dienste lauschen.Ein neuer <xref:System.ServiceModel.ServiceHost> wird erstellt, und ein Dienstendpunkt wird mit dem <xref:System.ServiceModel.UdpBinding> verfügbar gemacht.Der <xref:System.ServiceModel.ServiceHost> wird dann geöffnet und fängt an, eingehende Meldungen zu überwachen.  
  
 In diesem Szenariotyp werden Multicastmeldungen tatsächlich vom Client ausgesendet.Jeder Dienst, der auf die richtige UDP\-Adresse lauscht, empfängt die Multicastnachrichten.Im Folgenden finden Sie ein Beispiel für einen Client, der Multicastmeldungen aussendet:  
  
```  
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
                Console.WriteLine(String.Format("sent stock info at {0}", DateTime.Now));  
                // Wait for one second before sending another update  
                System.Threading.Thread.Sleep(new TimeSpan(0, 0, 1));  
            }  
  
```  
  
 Dieser Code generiert Börseninformationen und verwendet dann den Dienstvertrag IStockTicker, um Multicastnachrichten an Aufrufdienste zu senden, die auf die richtige UDP\-Adresse lauschen.  
  
### UDP und zuverlässiges Messaging  
 Die UDP\-Bindung unterstützt kein zuverlässiges Messaging, was an der Einfachkeit des UDP\-Protokolls liegt.Wenn Sie sicherstellen müssen, dass Nachrichten von einem Remoteendpunkt empfangen wurden, verwenden Sie einen Transport, der zuverlässiges Messaging wie HTTP oder TCP unterstützt.Weitere Informationen zum zuverlässigen Messaging finden Sie unter http:\/\/go.microsoft.com\/fwlink\/?LinkId\=231830 \(möglicherweise in englischer Sprache\).  
  
### Bidirektionales Multicastmessaging  
 Während Multicastnachrichten im Allgemeinen unidirektional sind, unterstützt UdpBinding den Austausch von Anforderungs\-\/Antwortnachrichten.Die mithilfe des UDP\-Transports gesendeten Nachrichten enthalten sowohl Absender\- als auch Empfängeradresse.Besondere Sorgfalt erfordert die Absenderadresse, da sie während der Übertragung möglicherweise böswillig geändert wurde.Die Adresse kann mithilfe des folgenden Codes überprüft werden:  
  
```  
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
  
### Sicherheitsüberlegungen  
 Beim Lauschen auf Multicastnachrichten wird ein ICMP\-Paket an den Router gesendet, um ihn davon in Kenntnis setzen, ob auf die Multicastadresse gelauscht wird.Jeder Benutzer im lokalen Subnetz mit entsprechender Berechtigung kann auf diese Pakettypen lauschen und ermitteln, auf welche Multicastadresse und welchen Port ein Lauschvorgang ausgeführt wird.  
  
 Aus Sicherheitsgründen sollte die IP\-Adresse des Absenders nicht verwendet werden.Diese Informationen können verfälscht werden und dazu führen, dass eine Anwendung Antworten an den falschen Computer sendet.Eine Möglichkeit, dieses Risiko abzuschwächen, ist das Aktiveren der Sicherheit auf Nachrichtenebene.Auf Netzwerkebene kann auch IIPsec \(Internetprotokollsicherheit\) und\/oder NAP \(Netzwerkzugriffsschutz\) verwendet werden.