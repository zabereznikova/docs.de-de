---
title: Migrieren von .NET-Remoting zu WCF
ms.date: 03/30/2017
ms.assetid: 16902a42-ef80-40e9-8c4c-90e61ddfdfe5
ms.openlocfilehash: 8dcc019017195fd55231fbea3493d4c53d500cb3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183961"
---
# <a name="migrating-from-net-remoting-to-wcf"></a>Migrieren von .NET-Remoting zu WCF
Dieser Artikel beschreibt die Vorgehensweise zum Migrieren einer Anwendung, die .NET Remoting zur Verwendung von Windows Communication Foundation (WCF) nutzt. Es werden ähnliche Konzepte dieser zwei Produkte verglichen, und es wird beschrieben, wie verschiedene Remoting-Szenarien in WCF realisiert werden können.  
  
 .NET Remoting ist ein Legacy-Produkt, das nur zur Bereitstellung von Abwärtskompatibilität unterstützt wird. Seine Verwendung in Umgebungen mit gemischten Vertrauensstellungen ist nicht sicher, da keine getrennten Vertrauensebenen zwischen Client und Server eingerichtet werden können. Beispielsweise sollten Sie nie einen .NET Remoting-Endpunkt für das Internet oder nicht vertrauenswürdige Clients verfügbar machen. Es wird empfohlen, vorhandene Remoting-Anwendungen auf neuere und sicherere Technologien zu migrieren. Wenn das Anwendungsdesign nur HTTP und RESTful verwendet, wird die ASP.NET-Web-API empfohlen. Weitere Informationen finden Sie unter "ASP.NET-Web-API". Wenn die Anwendung auf SOAP basiert oder Nicht-HTTP-Protokolle wie z. B. TCP erfordert, empfehlen wir WCF.  

## <a name="comparing-net-remoting-to-wcf"></a>Vergleich von .NET Remoting und WCF  
 In diesem Abschnitt werden die grundlegenden Bausteine von .NET Remoting mit ihren Entsprechungen in WCF verglichen. Wir werden diese Bausteine später verwenden, um einige allgemeine Client-Server-Szenarien in WCF zu erstellen. Das folgende Diagramm fasst die wichtigsten Ähnlichkeiten und Unterschiede zwischen .NET Remoting und WCF zusammen.  
  
||.NET-Remotezugriff|WCF|  
|-|-------------------|---------|  
|Servertyp|MarshalByRefObject-Unterklasse|Markierung mit [ServiceContract]-Attribut|  
|Dienstvorgänge|Öffentliche Methoden für Servertyp|Markierung mit [OperationContract]-Attribut|  
|Serialisierung|ISerializable oder [Serializable]|DataContractSerializer oder XmlSerializer|  
|Übergebene Objekte|Als Wert oder Verweis|Nur als Wert|  
|Fehler/Ausnahmen|Jede serialisierbare Ausnahme|FaultContract\<TDetail>|  
|Clientproxyobjekte|Stark typisierte transparente Proxys werden automatisch über MarshalByRefObjects erstellt|Stark typisierte Proxys werden bei Bedarf\<mit ChannelFactory TChannel>|  
|Plattform erforderlich|Client und Server müssen Microsoft-Betriebssystem und .NET verwenden|Plattformübergreifend|  
|Nachrichtenformat|Privat|Industriestandards (SOAP, WS-* usw.)|  
  
### <a name="server-implementation-comparison"></a>Serverimplementierung im Vergleich  
  
#### <a name="creating-a-server-in-net-remoting"></a>Erstellen eines Servers in .NET Remoting  
 .NET Remoting-Servertypen müssen von MarshalByRefObject abgeleitet werden und Methoden definieren, die der Client aufrufen kann. Dies wird nachfolgend gezeigt:  
  
```csharp
public class RemotingServer : MarshalByRefObject  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 Die öffentlichen Methoden dieses Servertyps werden zum öffentlichen Vertrag, der für Clients zur Verfügung steht.  Es gibt keine Trennung zwischen der öffentlichen Serverschnittstelle und deren Implementierung – beide werden durch einen Typ behandelt.  
  
 Nachdem der Servertyp definiert wurde, kann er für Clients verfügbar gemacht werden, wie im folgenden Beispiel gezeigt:  
  
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
  
 Es gibt viele Möglichkeiten, den Remoting-Typ als Server verfügbar zu machen, einschließlich der Verwendung von Konfigurationsdateien. Dies ist nur ein Beispiel.  
  
#### <a name="creating-a-server-in-wcf"></a>Erstellen eines Servers in WCF  
 Der entsprechende Schritt in WCF umfasst das Erstellen von zwei Typen – des öffentlichen "Dienstvertrags" und der konkreten Implementierung. Der erste Typ wird als eine mit [ServiceContract] markierte Schnittstelle deklariert. Für Clients verfügbare Methoden sind mit [OperationContract] markiert:  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 Die serverseitige Implementierung ist in einer separaten konkreten Klasse definiert, wie im folgenden Beispiel gezeigt:  
  
```csharp
public class WCFServer : IWCFServer  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 Sobald diese Typen definiert wurden, kann der WCF-Server für Clients verfügbar gemacht werden, wie im folgenden Beispiel gezeigt:  
  
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
> Es wird in beiden Fällen TCP verwendet, um die Beispiele so ähnlich wie möglich zu halten. Beispiele mit Verwendung von HTTP finden Sie weiter unten in diesem Thema in den Szenariobeschreibungen.  
  
 Es gibt viele Möglichkeiten zum Konfigurieren und Hosten von WCF-Diensten. Dies ist lediglich ein Beispiel, bezeichnet als "selbst gehosteter Dienst". Weitere Informationen finden Sie in den folgenden Themen:  
  
- [Vorgehensweise: Definieren eines Dienstvertrags](how-to-define-a-wcf-service-contract.md)  
  
- [Konfigurieren von Diensten mit Konfigurationsdateien](configuring-services-using-configuration-files.md)  
  
- [Hosting-Dienste](hosting-services.md)  
  
### <a name="client-implementation-comparison"></a>Clientimplementierung im Vergleich  
  
#### <a name="creating-a-client-in-net-remoting"></a>Erstellen eines Clients in .NET Remoting  
 Sobald ein .NET Remoting-Serverobjekt verfügbar gemacht wurde, kann es von Clients genutzt werden, wie im folgenden Beispiel gezeigt:  
  
```csharp
TcpChannel channel = new TcpChannel();  
ChannelServices.RegisterChannel(channel, ensureSecurity : true);  
RemotingServer server = (RemotingServer)Activator.GetObject(  
                            typeof(RemotingServer),
                            "tcp://localhost:8080/RemotingServer");  
  
RemotingCustomer customer = server.GetCustomer(42);  
Console.WriteLine($"Customer {customer.FirstName} {customer.LastName} received.");
```  
  
 Die von Activator.GetObject() zurückgegebene RemotingServer-Instanz wird als "transparenter Proxy" bezeichnet. Diese Instanz implementiert die öffentliche API für den RemotingServer-Typ auf dem Client, sämtliche Methoden rufen jedoch das Serverobjekt auf, das in einem anderen Prozess oder auf einem anderen Computer ausgeführt wird.  
  
#### <a name="creating-a-client-in-wcf"></a>Erstellen eines Clients in WCF  
 Der entsprechende Schritt in WCF umfasst die Verwendung einer Kanalfactory zur expliziten Erstellung des Proxys. Wie Remoting kann das Proxyobjekt zum Auslösen von Vorgängen auf dem Server verwendet werden, wie im folgenden Beispiel gezeigt:  
  
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
  
 Dieses Beispiel zeigt die Programmierung auf Kanalebene, da sie dem Remoting-Beispiel am ähnlichsten ist. Ebenfalls verfügbar ist der **Ansatz "Dienstreferenz hinzufügen"** in Visual Studio, der Code generiert, um die Clientprogrammierung zu vereinfachen. Weitere Informationen finden Sie in den folgenden Themen:  
  
- [Client-Kanalebenenprogrammierung](./extending/client-channel-level-programming.md)  
  
- [Vorgehensweise: Hinzufügen, Aktualisieren oder Entfernen eines Dienstverweises](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference)  
  
### <a name="serialization-usage"></a>Verwenden der Serialisierung  
 Sowohl .NET Remoting als auch WCF verwenden Serialisierung, um Objekte zwischen Client und Server zu senden. Es gelten jedoch folgende wichtige Unterschiede:  
  
1. Sie verwenden verschiedene Serialisierer und Konventionen, um anzugeben, was serialisiert werden soll.  
  
2. .NET Remoting unterstützt die Serialisierung "nach Verweis", bei der ein Methoden- oder Eigenschaftenzugriff auf einer Ebene die Ausführung von Code auf einer anderen Ebene zulässt, also über Sicherheitsgrenzen hinweg. Diese Funktion birgt Sicherheitsrisiken und ist einer der Hauptgründe dafür, warum Remoting-Endpunkte niemals für nicht vertrauenswürdige Clients verfügbar gemacht werden sollten.  
  
3. Die von Remoting eingesetzte Serialisierung erfolgt nach dem Ausschlussverfahren (expliziter Ausschluss der Elemente, die nicht serialisiert werden sollen), WCF verwendet eine Serialisierung nach dem Einschlussverfahren (explizite Markierung der Elemente, die serialisiert werden sollen).  
  
#### <a name="serialization-in-net-remoting"></a>Serialisierung in .NET Remoting  
 .NET Remoting unterstützt zwei Möglichkeiten zum Serialisieren und Deserialisieren von Objekten zwischen Client und Server:  
  
- *Nach Wert* – Die Werte des Objekts werden über Ebenengrenzen hinweg serialisiert, und eine neue Instanz dieses Objekts wird auf der anderen Ebene erstellt. Alle Aufrufe von Methoden oder Eigenschaften der neuen Instanz werden ausschließlich lokal ausgeführt und wirken sich nicht auf das ursprüngliche Objekt oder die ursprüngliche Ebene aus.  
  
- *Als Referenz* – eine spezielle "Objektreferenz" wird über Ebenengrenzen hinweg serialisiert. Wenn eine Ebene mit Methoden oder Eigenschaften des Objekts interagiert, erfolgt die Kommunikation zurück an das ursprüngliche Objekt oder die ursprüngliche Ebene. Als-Verweis-Objekte können in beide Richtungen übertragen werden – vom Server an den Client oder vom Client an den Server.  
  
 Als-Wert-Typen werden in Remoting mit dem [Serializable]-Attribut gekennzeichnet oder implementieren "ISerializable", wie im folgenden Beispiel gezeigt:  
  
```csharp
[Serializable]  
public class RemotingCustomer  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 Als Verweis-Typen werden von der MarshalByRefObject-Klasse abgeleitet, wie im folgenden Beispiel gezeigt:  
  
```csharp
public class RemotingCustomerReference : MarshalByRefObject  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 Es ist äußerst wichtig, die Auswirkung von Verweisobjekten in Remoting zu verstehen. Wenn eine der beiden Ebenen (Client oder Server) ein Verweisobjekt an die andere Ebene sendet, werden alle Methodenaufrufe auf der Ebene ausgeführt, zu der das Objekt gehört. Beispiel: Wenn ein Client Methoden für ein vom Server zurückgegebenes Verweisobjekt aufruft, führt dies zur Ausführung von Code auf dem Server. Auf ähnliche Weise wird beim Aufruf von durch den Client bereitgestellten Verweisobjekten durch den Server Code auf dem Client ausgeführt. Aus diesem Grund empfiehlt sich die Verwendung von .NET Remoting nur in vollständig vertrauenswürdigen Umgebungen. Das Offenlegen eines öffentlichen .NET Remoting-Endpunkts für nicht vertrauenswürdige Clients macht einen Remoting-Server anfällig für Angriffe.  
  
#### <a name="serialization-in-wcf"></a>Serialisierung in WCF  
 WCF unterstützt nur die Serialisierung nach Wert. Die gängigste Methode zum Definieren eines Typs für den Austausch zwischen Client und Server wird im folgenden Beispiel gezeigt:  
  
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
  
 Das [DataContract]-Attribut gibt an, dass dieser Typ zwischen Client und Server serialisiert und deserialisiert werden kann. Das Attribut [DataMember] identifiziert die einzelnen Eigenschaften oder Felder für die Serialisierung.  
  
 Wenn WCF ein Objekt über Ebenen hinweg sendet, werden nur die Werte serialisiert, und es wird eine neue Instanz des Objekts auf der anderen Ebene erstellt. Sämtliche Interaktionen mit den Werten des Objekts erfolgen nur lokal – es findet im Gegensatz zu den Als-Verweis-Objekten in .NET Remoting keine Kommunikation mit der anderen Ebene statt. Weitere Informationen finden Sie unter [Serialisierung und Deserialisierung](./feature-details/serialization-and-deserialization.md).  
  
### <a name="exception-handling-capabilities"></a>Funktionen für die Ausnahmebehandlung  
  
#### <a name="exceptions-in-net-remoting"></a>Ausnahmen in .NET Remoting  
 Von einem Remoting-Server ausgelöste Ausnahmen werden serialisiert, an den Client gesendet und lokal auf dem Client wie jede andere Ausnahme ausgelöst. Benutzerdefinierte Ausnahmen können durch das Erstellen einer Unterklasse für den Ausnahmetyp und Markierung mit [Serializable] erstellt werden.   Die meisten Framework-Ausnahmen sind bereits in dieser Weise markiert. Deshalb können die meisten von ihnen durch den Server ausgelöst, serialisiert und erneut auf dem Client ausgelöst werden. Wenngleich dieses Design bei der Entwicklung praktisch ist, werden so möglicherweise unbeabsichtigt Informationen gegenüber dem Client offengelegt. Dies ist einer der vielen Gründe, aus denen Remoting nur in vollständig vertrauenswürdigen Umgebungen eingesetzt werden sollte.  
  
#### <a name="exceptions-and-faults-in-wcf"></a>Ausnahmen und Fehler in WCF  
 WCF lässt keine Rückgabe zufälliger Ausnahmetypen vom Server an den Client zu, da dies zu einer unbeabsichtigten Offenlegung von Informationen führen kann. Wenn ein Dienstvorgang eine unerwartete Ausnahme ausgelöst wird, führt dies dazu, dass auf dem Client eine allgemeine FaultException ausgelöst wird. Diese Ausnahme enthält keinerlei Informationen dazu, warum oder wo das Problem aufgetreten ist, und für einige Anwendungen reicht dies aus. Anwendungen, die ausführlichere Fehlerinformationen an den Client kommunizieren müssen, definieren zu diesem Zweck einen Fehlervertrag.  
  
 Hierzu erstellen Sie zunächst einen [DataContract]-Typ, der die Fehlerinformationen enthält.  
  
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
  
 Geben Sie den Fehlervertrag an, der für jeden Dienstvorgang zu verwenden ist.  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    [FaultContract(typeof(CustomerServiceFault))]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 Der Server meldet Fehlerbedingungen durch das Auslösen einer FaultException.  
  
```csharp
throw new FaultException<CustomerServiceFault>(  
    new CustomerServiceFault() {
        CustomerId = customerId,
        ErrorMessage = "Illegal customer Id"
    });  
```  
  
 Und wenn der Client eine Anforderung an den Server sendet, können Fehler als normale Ausnahmen abgefangen werden.  
  
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
  
 Weitere Informationen zu Fehlerverträgen finden Sie unter <xref:System.ServiceModel.FaultException>.  
  
### <a name="security-considerations"></a>Überlegungen zur Sicherheit  
  
#### <a name="security-in-net-remoting"></a>Sicherheit in .NET Remoting  
 Einige .NET Remoting-Kanäle unterstützen Sicherheitsfunktionen wie beispielsweise Authentifizierung und Verschlüsselung auf Kanalebene (IPC und TCP). Der HTTP-Kanal nutzt sowohl für die Authentifizierung als auch für die Verschlüsselung Internetinformationsdienste (IIS). Trotz dieser Unterstützung sollten Sie .NET Remoting als unsicheres Kommunikationsprotokoll betrachten und nur in vollständig vertrauenswürdigen Umgebungen einsetzen. Machen Sie niemals einen öffentlichen Remoting-Endpunkt für das Internet oder nicht vertrauenswürdige Clients verfügbar.  
  
#### <a name="security-in-wcf"></a>Sicherheit in WCF  
 WCF wurde unter dem Gesichtspunkt der Sicherheit entworfen, teilweise auch deshalb, um die Schwachstellen in .NET Remoting zu beheben. WCF bietet Sicherheit auf Transport- und Nachrichtenebene und bietet zahlreiche Optionen für Authentifizierung, Autorisierung, Verschlüsselung usw. Weitere Informationen finden Sie in den folgenden Themen:  
  
- [Sicherheit](./feature-details/security.md)  
  
- [WCF-Sicherheitsleitfaden](./feature-details/security-guidance-and-best-practices.md)  
  
## <a name="migrating-to-wcf"></a>Migration nach WCF  
  
### <a name="why-migrate-from-remoting-to-wcf"></a>Welche Vorteile bietet die Migration von Remoting nach WCF?  
  
- **.NET Remoting ist ein Legacy-Produkt.** Wie in [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507%28v=vs.100%29)beschrieben, gilt es als älteres Produkt und wird nicht für Neuentwicklungen empfohlen. Für neue und vorhandene Anwendungen wird der Einsatz von WCF oder ASP.NET-Web-API empfohlen.  
  
- **WCF verwendet plattformübergreifende Standards.** WCF wurde unter dem Gesichtspunkt einer plattformübergreifenden Interoperabilität entwickelt und unterstützt zahlreiche Industriestandards (SOAP, WS-Security, WS-Trust, usw.). Ein WCF-Dienst kann mit Clients interagieren, auf denen andere Betriebssysteme als Windows ausgeführt werden. Remoting wurde in erster Linie für Umgebungen entwickelt, in denen sowohl die Server- als auch die Clientanwendung mit .NET Framework unter einem Windows-Betriebssystem ausgeführt werden.
  
- **WCF bietet integrierte Sicherheit.** WCF wurde unter Berücksichtigung der Sicherheit entwickelt und bietet viele Optionen für Authentifizierung, Sicherheit auf Transportebene, Sicherheit auf Nachrichtenebene usw. Remoting wurde entwickelt, um anwendungen die Zusammenarbeit zu erleichtern, aber nicht für die Sicherheit in nicht vertrauenswürdigen Umgebungen. WCF wurde entworfen, um sowohl in vertrauenswürdigen als auch in nicht vertrauenswürdigen Umgebungen eingesetzt zu werden.  
  
### <a name="migration-recommendations"></a>Empfehlungen für die Migration  
 Für die Migration von .NET Remoting nach WCF werden die folgenden Schritte empfohlen:  
  
- **Erstellen des Dienstvertrags.** Definieren Sie Ihre Dienstschnittstellentypen, und markieren Sie diese mit dem [ServiceContract]-Attribut. Markieren Sie alle Methoden, die der Client mit [OperationContract] aufrufen darf.  
  
- **Erstellen Sie den Datenvertrag.** Definieren Sie die Datentypen, die zwischen Server und Client ausgetauscht werden, und markieren Sie diese mit dem Attribut [DataContract]. Markieren Sie alle Felder und Eigenschaften, die der Client mit [DataMember] verwenden darf.  
  
- **Erstellen des Fehlervertrags (optional).** Erstellen Sie die Typen, die zwischen Server und Client ausgetauscht werden, wenn Fehler auftreten. Markieren Sie diese Typen mit [DataContract] und [DataMember], um sie serialisierbar zu machen. Markieren Sie alle Dienstvorgänge, die Sie mit [OperationContract] markiert haben, auch mit [FaultContract], um die Fehler festzulegen, die zurückgegeben werden können.  
  
- **Konfigurieren und Hosten des Diensts.** Sobald der Dienstvertrag erstellt wurde, besteht der nächste Schritt darin, eine Bindung zu konfigurieren, die für den Dienst an einem Endpunkt verfügbar gemacht wird. Weitere Informationen finden Sie unter [Endpunkte: Adressen, Bindungen und Verträge](./feature-details/endpoints-addresses-bindings-and-contracts.md).  
  
 Nach der Migration einer Remoting-Anwendung nach WCF ist es wichtig, Abhängigkeiten mit .NET Remoting zu entfernen. Auf diese Weise wird sichergestellt, dass alle Remoing-Sicherheitsanfälligkeiten aus der Anwendung entfernt werden. Folgende Schritte müssen ausgeführt werden:  
  
- **Beenden Sie die Verwendung von "MarshalByRefObject".** Der MarshalByRefObject-Typ ist nur in Remoting vorhanden und wird von WCF nicht verwendet. Alle Anwendungstypen, die Unterklassen von MarshalByRefObject verwenden, sollten entfernt oder geändert werden.  
  
- **Beenden Sie die Verwendung von [Serializable] und ISerializable.** Das [Serializable]-Attribut und die ISerializable-Schnittstelle wurden ursprünglich zum Serialisieren von Typen in vertrauenswürdigen Umgebungen entworfen und werden von Remoting verwendet. Die WCF-Serialisierung beruht auf Typen, die mit [DataContract] und [DataMember] markiert sind. Die von einer Anwendung verwendeten Datentypen sollten geändert werden, um [DataContract] zu verwenden und nicht ISerializable oder [Serializable].  
  
### <a name="migration-scenarios"></a>Migrationsszenarien  
 Betrachten wir nun, wie die folgenden gängigen Remoting-Szenarien in WCF realisiert werden:  
  
1. Server gibt ein Objekt als Wert an den Client zurück  
  
2. Server gibt ein Objekt als Verweis an den Client zurück  
  
3. Client sendet ein Objekt als Wert an den Server  
  
> [!NOTE]
> Das Senden eines Objekts als Verweis vom Client an den Server ist in WCF nicht zulässig.  
  
 Nehmen Sie beim Durcharbeiten dieser Szenarien an, dass die Baseline-Schnittstellen für .NET Remoting wie im folgenden Beispiel aussehen. Die .NET Remoting-Implementierung ist hier nicht wichtig, da nur dargestellt werden soll, wie WCF zur Implementierung einer äquivalenten Funktionalität genutzt wird.  
  
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
  
#### <a name="scenario-1-service-returns-an-object-by-value"></a>Szenario 1: Der Dienst gibt ein Objekt per Wert zurück  
 In diesem Szenario wird gezeigt, wie ein Server ein Objekt per Wert an den Client zurückgibt. WCF gibt Objekte immer per Wert an den Server zurück, daher beschreiben die folgenden Schritte lediglich, wie ein normaler WCF-Dienst erstellt wird.  
  
1. Zuerst definieren Sie eine öffentliche Schnittstelle für den WCF-Dienst und markieren ihn mit dem [ServiceContract]-Attribut. [OperationContract] wird verwendet, um die serverseitigen Methoden zu identifizieren, die der Client aufruft.  
  
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
  
2. Im nächsten Schritt wird der Datenvertrag für diesen Dienst erstellt. Dazu werden Klassen (keine Schnittstellen) erstellt, die mit dem [DataContract]-Attribut markiert werden. Die einzelnen Eigenschaften oder Felder, die für Client und Server sichtbar sein sollen, werden mit [DataMember] markiert. Wenn abgeleitete Typen zulässig sein sollen, müssen diese mit dem [KnownType]-Attribut identifiziert werden. Die einzigen Typen, für die WCF eine Serialisierung oder Deserialisierung zulässt, sind die in der Dienstschnittstelle enthaltenen Typen sowie diese "bekannten Typen". Jeder Versuch, andere als in dieser Liste enthaltene Typen zu verwenden, wird zurückgewiesen.  
  
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
  
3. Als Nächstes stellen wir die Implementierung für die Dienstschnittstelle bereit.  
  
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
  
4. Um den WCF-Dienst auszuführen, müssen Sie einen Endpunkt deklarieren, der diese Dienstschnittstelle an einer bestimmten URL über eine bestimmte WCF-Bindung verfügbar macht. Dies wird üblicherweise erreicht, indem die folgenden Abschnitte in die web.config-Datei des Serverprojekts eingefügt werden.  
  
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
  
5. Der WCF-Dienst kann anschließend mit dem folgenden Code gestartet werden:  
  
   ```csharp
   ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
       customerServiceHost.Open();  
   ```  
  
     Wird dieser ServiceHost gestartet, ermittelt er mithilfe der web.config-Datei den richtigen Vertrag sowie die Bindung und den Endpunkt. Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurieren von Diensten mithilfe von Konfigurationsdateien](./configuring-services-using-configuration-files.md). Diese Art des Serverstarts wird als Selbsthosting bezeichnet. Weitere Informationen zu anderen Optionen für das Hosten von WCF-Diensten finden Sie unter [Hostingservices](./hosting-services.md).  
  
6. Die Datei „app.config“ des Clientprojekts muss übereinstimmende Bindungsinformationen für den Dienstendpunkt deklarieren. Die einfachste Möglichkeit, dies in Visual Studio zu tun, besteht darin, **Dienstreferenz hinzufügen**zu verwenden, wodurch die Datei app.config automatisch aktualisiert wird. Alternativ können dieselben Änderungen manuell hinzugefügt werden.  
  
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
  
     Weitere Informationen zur Verwendung von **Dienstreferenz hinzufügen**finden Sie unter [Gewusst wie: Hinzufügen, Aktualisieren oder Entfernen einer Dienstreferenz](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference).  
  
7. Jetzt können wir den WCF-Dienst vom Client aufrufen. Dazu erstellen wir eine Kanalfactory für diesen Dienst, fordern einen Kanal an und rufen direkt die gewünschte Methode im Kanal auf. Dies ist möglich, da der Kanal die Dienstschnittstelle implementiert und die zugrunde liegende Logik für Anforderungen/Antworten verwaltet. Der Rückgabewert für diesen Methodenaufruf ist die deserialisierte Kopie der Serverantwort.  
  
   ```csharp
   ChannelFactory<ICustomerService> factory =  
       new ChannelFactory<ICustomerService>("customerservice");  
   ICustomerService service = factory.CreateChannel();  
   Customer customer = service.GetCustomer(42);  
   Console.WriteLine($"  Customer {customer.FirstName} {customer.LastName} received.");
   ```  
  
 WCF gibt Objekte vom Server an den Client immer als Wert zurück. Die Objekte sind deserialisierte Kopien der Daten, die vom Server gesendet wurden. Der Client kann Methoden für diese lokalen Kopien aufrufen, ohne Gefahr zu laufen, durch Rückruffunktionen Servercode aufzurufen.  
  
#### <a name="scenario-2-server-returns-an-object-by-reference"></a>Szenario 2: Server gibt ein Objekt als Verweis zurück  
 Dieses Szenario zeigt, wie der Server ein Objekt als Verweis an den Client zurückgibt. In .NET Remoting erfolgt dies für jeden von "MarshalByRefObject" abgeleiteten Typ automatisch, da diese als Verweis serialisiert werden. Ein Beispiel für dieses Szenario besteht darin, mehreren Clients zu gestatten, unabhängige, sitzungsbasierte, serverseitige Objekte zu verwalten. Wie bereits erwähnt, gibt der WCF-Dienst Objekte immer als Wert zurück, es gibt also keine direkte Entsprechung für ein Per-Verweis-Objekt. Es ist aber möglich, durch eine Verweissemantik mit Verwendung eines <xref:System.ServiceModel.EndpointAddress10>-Objekts etwas ähnliches zu erreichen. Es handelt sich um ein serialisierbares Per-Wert-Objekt, das vom Client dazu verwendet werden kann, ein sitzungsbasiertes Per-Verweis-Objekt auf dem Server abzurufen. Dadurch wird das Szenario ermöglicht, über mehrere Clients mit unabhängigen, sitzungsbasierten, serverseitigen Objekten zu verfügen.  
  
1. Zunächst muss ein WCF-Dienstvertrag definiert werden, der dem sitzungsbasierten Objekt selbst entspricht.  
  
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
    > Beachten Sie, dass das sitzungsbasierte Objekt mit [ServiceContract] markiert ist, es handelt sich also um eine normale WCF-Dienstschnittstelle. Durch Festlegen der SessionMode-Eigenschaft wird angegeben, dass es sich um einen sitzungsbasierten Dienst handelt. In WCF ist eine Sitzung eine Möglichkeit, mehrere Nachrichten zuzuordnen, die zwischen zwei Endpunkten gesendet werden. Dies bedeutet, dass zwischen dem Client und dem Server eine Sitzung eingerichtet wird, sobald der Client eine Verbindung mit diesem Dienst hergestellt hat. Der Client verwendet eine einzelne eindeutige Instanz des serverseitigen Objekts für alle Interaktionen innerhalb dieser einzelnen Sitzung.  
  
2. Als Nächstes muss die Implementierung dieser Schnittstelle bereitgestellt werden. Durch eine Kennzeichnung mit [ServiceBehavior] und Festlegen von InstanceContextMode wird WCF angewiesen, eine eindeutige Instanz dieses Typs für jede Sitzung zu verwenden.  
  
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
  
3. Nun benötigen wir eine Möglichkeit, eine Instanz dieses sitzungsbasierten Objekts abzurufen. Hierzu erstellen wir eine weitere WCF-Dienstschnittstelle, die ein EndpointAddress10-Objekt zurückgibt. Dies ist eine serialisierbare Form eines Endpunkts, die vom Server dazu verwendet werden kann, ein sitzungsbasiertes Objekt zu erstellen.  
  
   ```csharp
   [ServiceContract]  
       public interface ISessionBoundFactory  
       {  
           [OperationContract]  
           EndpointAddress10 GetInstanceAddress();  
       }  
   ```  
  
     Und wir implementieren diesen WCF-Dienst:  
  
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
  
     Diese Implementierung verwaltet eine Singleton-Kanalfactory, um sitzungsbasierte Objekte zu erstellen. Beim Aufruf von GetInstanceAddress() werden ein Kanal sowie ein EndpointAddress10-Objekt erstellt, das effektiv auf die diesem Kanal zugeordnete Remoteadresse verweist. EndpointAddress10 ist einfach ein Datentyp, der als Wert an den Client zurückgegeben werden kann.  
  
4. Die Konfigurationsdatei des Servers muss durch Ausführen von zwei Schritten geändert werden, wie im folgenden Beispiel gezeigt:  
  
    1. Deklarieren Sie einen \<Client> Abschnitt, der den Endpunkt für das sitzungsvolle Objekt beschreibt. Dies ist notwendig, da der Server in diesem Fall auch als Client fungiert.  
  
    2. Deklarieren Sie Endpunkte für die Factory und das sitzungsbasierte Objekt. Dies ist erforderlich, damit der Client mit den Dienstendpunkten kommunizieren kann, um EndpointAddress10 abzurufen und den sitzungsbasierten Kanal zu erstellen.  
  
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
  
     Anschließend können diese Dienste gestartet werden:  
  
   ```csharp
   ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
   factoryHost.Open();  
  
   ServiceHost sessionHost = new ServiceHost(typeof(MySessionBoundObject));  
   sessionHost.Open();  
   ```  
  
5. Wir konfigurieren den Client, indem dieselben Endpunkte in der zugehörigen app.config-Datei des Projekts deklariert werden.  
  
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
  
6. Zum Erstellen und Nutzen dieses sitzungsbasierten Objekts muss der Client die folgenden Schritte ausführen:  
  
    1. Erstellen eines Kanals zum ISessionBoundFactory-Dienst.  
  
    2. Verwenden dieses Kanals, um den Dienst zum Abrufen von EndpointAddress10 aufzurufen.  
  
    3. Verwenden von EndpointAddress10 zum Erstellen eines Kanals für den Abruf eines sitzungsbasierten Objekts.  
  
    4. Interaktion mit dem sitzungsbasierten Objekt, um zu veranschaulichen, dass auch bei mehreren Aufrufen dieselbe Instanz verwendet wird.  
  
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
  
 WCF gibt Objekte immer als Wert zurück. Es ist jedoch möglich, die entsprechende Verweissemantik durch Verwenden von EndpointAddress10 zu unterstützen. Dies ermöglicht dem Client, eine sitzungsbasierte WCF-Dienstinstanz anzufordern, um anschließend mit dieser wie mit jedem anderen WCF-Dienst zu interagieren.  
  
#### <a name="scenario-3-client-sends-server-a-by-value-instance"></a>Szenario 3: Client sendet eine Per-Wert-Instanz an den Server  
 Dieses Szenario zeigt, wie der Client eine nicht primitive Objektinstanz als Wert an den Server sendet. Da WCF Objekte nur als Wert übergibt, veranschaulicht dieses Szenario die normale WCF-Verwendung.  
  
1. Verwenden Sie den gleichen WCF-Dienst wie in Szenario 1.  
  
2. Verwenden Sie den Client, um ein neues Per-Wert-Objekt (Customer) sowie einen Kanal zur Kommunikation mit dem ICustomerService-Dienst zu erstellen und das Objekt an diesen zu senden.  
  
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
  
     Das Customer-Objekt wird serialisiert und an den Dienst gesendet und anschließend in eine neue Kopie dieses Objekts deserialisiert.  
  
    > [!NOTE]
    > Dieser Code zeigt auch das Senden eines abgeleiteten Typs (PremiumCustomer). Die Dienstschnittstelle erwartet ein Customer-Objekt, aber das [KnownType]-Attribut für die Customer-Klasse zeigt an, dass auch PremiumCustomer zulässig ist. WCF lässt keine Serialisierung oder Deserialisierung von anderen Typen über diese Dienstschnittstelle zu.  
  
 Der normale WCF-Datenaustausch erfolgt per Wert. Auf diese Weise wird sichergestellt, dass Methodenaufrufe für diese Datenobjekte nur lokal erfolgen – es wird kein Code auf der anderen Ebene aufgerufen. Obwohl es möglich ist, so etwas wie By-Reference-Objekte zu erreichen, die *vom* Server zurückgegeben werden, ist es für einen Client nicht möglich, ein By-Reference-Objekt an den Server *zu* übergeben. Ist zwischen Client und Server eine Konversation in beide Richtungen erforderlich, kann dies in WCF mit einem Duplexdienst erreicht werden. Weitere Informationen finden Sie unter [Duplexdienste](./feature-details/duplex-services.md).  
  
## <a name="summary"></a>Zusammenfassung  
 .NET Remoting ist ein Kommunikationsframework, das ausschließlich in vollständig vertrauenswürdigen Umgebungen eingesetzt werden sollte. Es handelt sich um ein Legacy-Produkt, das nur zur Bereitstellung von Abwärtskompatibilität unterstützt wird. Es sollte nicht verwendet werden, um neue Anwendungen zu erstellen. Im Gegensatz dazu wurde WCF unter Berücksichtigung von Sicherheitsaspekten entworfen und wird für neue und vorhandene Anwendungen empfohlen. Microsoft empfiehlt, vorhandene Remoting-Anwendungen zu migrieren, um stattdessen WCF oder die ASP.NET-Web-API zu verwenden.
