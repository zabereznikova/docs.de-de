---
title: Verwenden des Suchclientchannels
ms.date: 03/30/2017
ms.assetid: 1494242a-1d64-4035-8ecd-eb4f06c8d2ba
ms.openlocfilehash: 2d9dd68d233541f4d8cb3185adc1023cd5a19de1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184267"
---
# <a name="using-the-discovery-client-channel"></a>Verwenden des Suchclientchannels
Beim Schreiben einer WCF-Clientanwendung müssen Sie die Endpunktadresse des Diensts kennen, den Sie aufrufen. In vielen Situationen ist die Endpunktadresse eines Diensts nicht im Voraus bekannt, oder die Adresse des Diensts ändert sich im Laufe der Zeit. Mithilfe des Discovery-Clientchannels können Sie eine WCF-Clientanwendung schreiben und den aufzurufenden Dienst beschreiben. Der Client sendet dann automatisch eine Überprüfungsanforderung. Wenn ein Dienst antwortet, ruft der Discovery-Clientchannel die Endpunktadresse für den Dienst aus der Überprüfungsantwort ab und verwendet diese zum Aufrufen des Diensts.  
  
## <a name="using-the-discovery-client-channel"></a>Verwenden des Suchclientchannels  
 Um den Discovery-Clientchannel zu verwenden, fügen Sie dem Clientchannelstapel eine <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>-Instanz hinzu. Alternativ dazu können Sie das <xref:System.ServiceModel.Discovery.DynamicEndpoint>-Objekt verwenden. Der Bindung wird dann automatisch ein <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>-Objekt hinzugefügt, falls diese nicht bereits vorhanden ist.  
  
> [!CAUTION]
> Es wird empfohlen, das <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>-Objekt im Clientchannelstapel als oberstes Element zu verwenden. Für jedes Bindungselement, das zusätzlich zum <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>-Objekt hinzugefügt wird, muss sichergestellt sein, dass das <xref:System.ServiceModel.ChannelFactory>-Objekt bzw. der erstellte Channel nicht die Endpunktadresse oder die `Via`-Adresse (die an die `CreateChannel`-Methode übergeben wird) verwendet. Es kann nämlich sein, dass darin nicht die richtige Adresse enthalten ist.  
  
 Die <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>-Klasse enthält zwei öffentliche Eigenschaften:  
  
1. <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement.FindCriteria%2A> wird verwendet, um den Dienst zu beschreiben, den Sie aufrufen möchten.  
  
2. <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement.DiscoveryEndpointProvider%2A>die den Ermittlungsendpunkt angibt, an den Ermittlungsnachrichten gesendet werden sollen.  
  
 Mit der <xref:System.ServiceModel.Discovery.FindCriteria.%23ctor%2A>-Eigenschaft können Sie den Dienstvertrag angeben, nach dem Sie suchen, sowie alle erforderlichen Bereichs-URIs und den maximalen Zeitraum, wie lange versucht wird, den Channel zu öffnen. Der Vertragstyp wird durch Aufrufen <xref:System.ServiceModel.Discovery.FindCriteria>des Konstruktors angegeben. Der <xref:System.ServiceModel.Discovery.FindCriteria.Scopes%2A>-Eigenschaft können Bereichs-URIs hinzugefügt werden. Mithilfe der <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A>-Eigenschaft können Sie die maximale Anzahl von Ergebnissen angeben, für die der Client das Herstellen einer Verbindung versucht. Wenn eine Überprüfungsantwort empfangen wird, versucht der Client, den Channel mit der Endpunktadresse aus der Überprüfungsantwort zu öffnen. Wenn eine Ausnahme auftritt, fährt der Client mit der nächsten Überprüfungsantwort fort und wartet auf weitere Antworten, sofern dies erforderlich ist. Dies dauert so lange an, bis der Channel erfolgreich geöffnet oder die maximale Anzahl an Ergebnissen erreicht wurde. Weitere Informationen zu diesen Einstellungen finden Sie unter <xref:System.ServiceModel.Discovery.FindCriteria>.  
  
 Mit der <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement.DiscoveryEndpointProvider%2A>-Eigenschaft können Sie den zu verwendenden Suchendpunkt angeben. Normalerweise ist dies ein <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>-Objekt, aber es kann sich um jeden gültigen Endpunkt handeln.  
  
 Wenn Sie die Bindung für die Kommunikation mit dem Dienst erstellen, müssen Sie darauf achten, genau die gleiche Bindung wie der Dienst zu verwenden. Der einzige Unterschied besteht darin, dass die Clientbindung oben im Stapel über ein <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>-Objekt verfügt. Falls der Dienst eine der vom System bereitgestellten Bindungen verwendet, erstellen Sie ein neues <xref:System.ServiceModel.Channels.CustomBinding>-Objekt und übergeben die vom System bereitgestellte Bindung an den <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A>-Konstruktor. Anschließend können Sie <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> hinzufügen, indem Sie `Insert` für die <xref:System.ServiceModel.Channels.CustomBinding.Elements%2A>-Eigenschaft aufrufen.  
  
 Nachdem Sie <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> der Bindung hinzugefügt und diese konfiguriert haben, können Sie eine Instanz der WCF-Clientklasse erstellen, diese öffnen und ihre Methoden aufrufen. Im folgenden Beispiel wird der Discovery-Clientchannel verwendet, um einen WCF-Dienst zu ermitteln, der die `ICalculator`-Klasse implementiert (verwendet im WCF-Lernprogramm "Erste Schritte") und die dazugehörige `Add`-Methode aufruft.  
  
```csharp
// Create the DiscoveryClientBindingElement  
DiscoveryClientBindingElement bindingElement = new DiscoveryClientBindingElement();  
// Search for a service that implements the ICalculator interface, attempting to open  
// the channel a maximum of 2 times  
bindingElement.FindCriteria = new FindCriteria(typeof(ICalculator)) { MaxResults = 2 };  
// Use the UdpDiscoveryEndpoint  
bindingElement.DiscoveryEndpoint = new UdpDiscoveryEndpoint();  
  
// The service uses the BasicHttpBinding, so use that and insert the DiscoveryClientBindingElement at the
// top of the stack  
CustomBinding binding = new CustomBinding(new BasicHttpBinding());  
binding.Elements.Insert(0,bindingElement);  
  
try  
{  
    // Create the WCF client and call a method  
    CalculatorClient client = new CalculatorClient(binding, new EndpointAddress("http://schemas.microsoft.com/dynamic"));  
    client.Open();  
    client.Add(1, 1);  
}  
catch (EndpointNotFoundException ex)  
{  
    Console.WriteLine("An exception occurred: " + ex.Message);  
}  
```  
  
## <a name="security-and-the-discovery-client-channel"></a>Sicherheit und der Discovery-Clientchannel  
 Bei der Verwendung des Discovery-Clientchannels werden zwei Endpunkte angegeben. Einer wird für Suchnachrichten verwendet, normalerweise <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, und der andere ist der Anwendungsendpunkt. Achten Sie beim Implementieren eines sicheren Diensts besonders auf die Sicherheit der beiden Endpunkte. Weitere Informationen zur Sicherheit finden Sie unter [Sichern von Diensten und Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).
