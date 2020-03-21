---
title: 'Gewusst wie: Migrieren von verwaltetem Code DCOM zu WCF'
ms.date: 03/30/2017
ms.assetid: 52961ffc-d1c7-4f83-832c-786444b951ba
ms.openlocfilehash: 2576e88c25ae381e90ec7d613efb648048145b3b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181389"
---
# <a name="how-to-migrate-managed-code-dcom-to-wcf"></a>Gewusst wie: Migrieren von verwaltetem Code DCOM zu WCF
Windows Communication Foundation (WCF) ist für Aufrufe von verwaltetem Code zwischen Servern und Clients in einer verteilten Umgebung die empfohlene und sichere Wahl im Vergleich zu DCOM (Distributed Component Object Model). In diesem Artikel wird für die folgenden Szenarien gezeigt, wie Sie Code aus DCOM zu WCF migrieren.  
  
- Der Remotedienst gibt ein Objekt per Wert an den Client zurück.  
  
- Der Client sendet einen Objekt per Wert an den Remotedienst.  
  
- Der Remotedienst gibt ein Objekt per Verweis an den Client zurück.  
  
 Aus Sicherheitsgründen ist es in WCF nicht zulässig, ein Objekt per Verweis vom Client an den Dienst zu senden. Ist zwischen Client und Server eine Konversation in beide Richtungen erforderlich, kann dies in WCF mit einem Duplexdienst erreicht werden.  Weitere Informationen zu Duplexdiensten finden Sie unter [Duplexdienste](../wcf/feature-details/duplex-services.md).  
  
 Weitere Informationen zum Erstellen von WCF-Diensten und Clients für diese Dienste finden Sie unter [Basis-WCF-Programmierung](../wcf/basic-wcf-programming.md), [Entwerfen und Implementieren von Diensten](../wcf/designing-and-implementing-services.md) und [Erstellen von Clients](../wcf/building-clients.md).  
  
## <a name="dcom-example-code"></a>DCOM-Beispielcode  
 Für diese Szenarien haben die DCOM-Schnittstellen, die für die Verwendung mit WCF veranschaulicht werden, die folgende Struktur:  
  
```csharp  
[ComVisible(true)]  
[Guid("AA9C4CDB-55EA-4413-90D2-843F1A49E6E6")]  
public interface IRemoteService  
{  
   Customer GetObjectByValue();  
   IRemoteObject GetObjectByReference();  
   void SendObjectByValue(Customer customer);  
}  
  
[ComVisible(true)]  
[Guid("A12C98DE-B6A1-463D-8C24-81E4BBC4351B")]  
public interface IRemoteObject  
{  
}  
  
public class Customer  
{  
}  
```  
  
## <a name="the-service-returns-an-object-by-value"></a>Der Dienst gibt ein Objekt per Wert zurück  
 In diesem Szenario rufen Sie einen Dienst auf, und dessen Methode gibt ein Objekt zurück, das per Wert vom Server an den Client übergeben wird. Dieses Szenario entspricht dem folgenden COM-Aufruf:  
  
```csharp  
public interface IRemoteService  
{  
    Customer GetObjectByValue();  
}  
```  
  
 In diesem Szenario empfängt der Client eine deserialisierte Kopie eines Objekts vom Remotedienst. Der Client kann mit dieser lokalen Kopie arbeiten, ohne den Dienst erneut aufzurufen.  Anders ausgedrückt, für den Client ist garantiert, dass der Dienst in keiner Weise beteiligt wird, wenn Methoden der lokalen Kopie aufgerufen werden. WCF gibt Objekte aus dem Dienst immer per Wert zurück, sodass die folgenden Schritte das Erstellen eines ordnungsgemäßen WCF-Diensts beschreiben.  
  
### <a name="step-1-define-the-wcf-service-interface"></a>Schritt 1: Definieren der Schnittstelle des WCF-Diensts  
 Definieren Sie eine öffentliche Schnittstelle für den WCF-Dienst, und kennzeichnen Sie sie mit dem [<xref:System.ServiceModel.ServiceContractAttribute>]-Attribut.  Kennzeichnen Sie die Methoden, die Sie für Clients verfügbar machen möchten, mit dem [<xref:System.ServiceModel.OperationContractAttribute>]-Attribut. Im folgenden Beispiel wird gezeigt, wie diese Attribute verwendet werden, um die serverseitige Schnittstelle und die Schnittstellenmethoden zu bestimmen, die ein Client aufrufen kann. Die für dieses Szenario verwendete Methode ist fett dargestellt.  
  
```csharp  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Web;
. . .  
[ServiceContract]  
public interface ICustomerManager  
{  
    [OperationContract]  
    void StoreCustomer(Customer customer);  
  
    [OperationContract]     Customer GetCustomer(string firstName, string lastName);
  
}  
```  
  
### <a name="step-2-define-the-data-contract"></a>Schritt 2: Definieren des Datenvertrags  
 Als Nächstes sollten Sie einen Datenvertrag für den Dienst erstellen. In diesem Vertrag wird beschrieben, wie die Daten zwischen dem Dienst und seinen Clients ausgetauscht werden.  Klassen, die in dem Datenvertrag beschrieben sind, müssen mit dem [<xref:System.Runtime.Serialization.DataContractAttribute>]-Attribut gekennzeichnet werden. Die einzelnen Eigenschaften oder Felder, die für Client und Server sichtbar sein sollen, müssen mit dem [<xref:System.Runtime.Serialization.DataMemberAttribute>]-Attribut markiert werden. Möchten Sie im Datenvertrag Typen zulassen, die aus einer Klasse abgeleitet wurden, müssen Sie diese mit dem [<xref:System.Runtime.Serialization.KnownTypeAttribute>]-Attribut kennzeichnen. WCF serialisiert oder deserialisiert nur Typen in der Dienstschnittstelle sowie Typen, die als bekannte Typen gekennzeichnet sind. Wenn Sie versuchen, einen Typ zu verwenden, der kein bekannter Typ ist, wird eine Ausnahme ausgelöst.  
  
 Weitere Informationen zu Datenverträgen finden Sie unter [Datenverträge](../wcf/samples/data-contracts.md).  
  
```csharp  
[DataContract]  
[KnownType(typeof(PremiumCustomer))]  
public class Customer  
{  
    [DataMember]  
    public string Firstname;  
    [DataMember]  
    public string Lastname;  
    [DataMember]  
    public Address DefaultDeliveryAddress;  
    [DataMember]  
    public Address DefaultBillingAddress;  
}  
 [DataContract]  
public class PremiumCustomer : Customer  
{  
    [DataMember]  
    public int AccountID;  
}  
  
 [DataContract]  
public class Address  
{  
    [DataMember]  
    public string Street;  
    [DataMember]  
    public string Zipcode;  
    [DataMember]  
    public string City;  
    [DataMember]  
    public string State;  
    [DataMember]  
    public string Country;  
}  
```  
  
### <a name="step-3-implement-the-wcf-service"></a>Schritt 3: Implementieren des WCF-Diensts  
 Als Nächstes müssen Sie die WCF-Dienstklasse implementieren, in der die Schnittstelle implementiert ist, die Sie im vorherigen Schritt definiert haben.  
  
```csharp  
public class CustomerService: ICustomerManager
{  
    public void StoreCustomer(Customer customer)  
    {  
        // write to a database  
    }  
    public Customer GetCustomer(string firstName, string lastName)  
    {  
        // read from a database  
    }  
}  
```  
  
### <a name="step-4-configure-the-service-and-the-client"></a>Schritt 4: Konfigurieren des Diensts und des Clients  
 Um einen WCF-Dienst auszuführen, müssen Sie einen Endpunkt deklarieren, der diese Dienstschnittstelle unter einer bestimmten URL über eine bestimmte WCF-Bindung verfügbar macht. Eine Bindung gibt die Transport-, Codierungs- und Protokolldetails an, die für die Kommunikation zwischen Clients und Server erforderlich sind. Bindungen fügen Sie üblicherweise in der Konfigurationsdatei (web.config) des Dienstprojekts hinzu. Nachstehend ist ein Bindungseintrag für den Beispieldienst gezeigt:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Server.CustomerService">  
        <endpoint address="http://localhost:8083/CustomerManager"
                  binding="basicHttpBinding"  
                  contract="Shared.ICustomerManager" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 Als Nächstes müssen Sie den Client entsprechend den Bindungsinformationen konfigurieren, die durch den Dienst angegeben sind. Fügen Sie hierzu Folgendes in der Anwendungskonfigurationsdatei (app.config) des Clients hinzu.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint name="customermanager"
                address="http://localhost:8083/CustomerManager"
                binding="basicHttpBinding"
                contract="Shared.ICustomerManager"/>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="step-5-run-the-service"></a>Schritt 5: Ausführen des Diensts  
 Schließlich können Sie den Dienst über Selfhosting in einer Konsolenanwendung bereitstellen, indem Sie der Dienstanwendung die folgenden Zeilen hinzufügen und die Anwendung starten. Weitere Informationen zu anderen Möglichkeiten zum Hosten einer WCF-Dienstanwendung finden Sie unter [Hosting-Dienste](../wcf/hosting-services.md).  
  
```csharp  
ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
customerServiceHost.Open();  
```  
  
### <a name="step-6-call-the-service-from-the-client"></a>Schritt 6: Aufrufen des Diensts aus dem Client  
 Um den Dienst aus dem Client aufzurufen, müssen Sie eine Kanalfactory für den Dienst erstellen und einen Kanal anfordern, wodurch es Ihnen ermöglicht wird, die `GetCustomer`-Methode direkt aus dem Client aufzurufen. Der Kanal implementiert die Schnittstelle des Diensts und verarbeitet die zugrunde liegende Anforderung/Antwort-Logik für Sie.  Der Rückgabewert von diesem Methodenaufruf ist die deserialisierte Kopie der Antwort des Diensts.  
  
```csharp  
ChannelFactory<ICustomerManager> factory =
     new ChannelFactory<ICustomerManager>("customermanager");  
ICustomerManager service = factory.CreateChannel();  
Customer customer = service.GetCustomer("Mary", "Smith");  
```  
  
## <a name="the-client-sends-a-by-value-object-to-the-server"></a>Der Client sendet ein Per-Wert-Objekt an den Server  
 In diesem Szenario sendet der Client ein Objekt per Wert an den Server. Dies bedeutet, dass der Server eine deserialisierte Kopie des Objekts empfängt.  Der Server kann Methoden aus dieser Kopie aufrufen und kann sicher sein, dass es keinen Rückruf in den Clientcode gibt. Wie bereits erwähnt, erfolgen die normalen WCF-Austauschvorgänge von Daten per Wert.  Dadurch ist sichergestellt, dass Methoden, die für eines dieser Objekte aufgerufen werden, nur lokal ausgeführt werden –  es wird kein Code auf dem Client aufgerufen.  
  
 Dieses Szenario entspricht dem folgenden COM-Methodenaufruf:  
  
```csharp  
public interface IRemoteService  
{  
    void SendObjectByValue(Customer customer);  
}  
```  
  
 In diesem Szenario werden dieselbe Schnittstelle und derselbe Dienstvertrag verwendet wie im ersten Beispiel. Darüber hinaus werden der Client und der Dienst auf die gleiche Weise konfiguriert. In diesem Beispiel wird ein Kanal erstellt, um das Objekt zu senden aus in gleicher Weise ausgeführt zu werden. Allerdings erstellen Sie für dieses Beispiel einen Client, der den Dienst aufruft, wobei ein Objekt per Wert übergeben wird. Die Dienstmethode, die der Client im Dienstvertrag aufruft, ist fett dargestellt:  
  
```csharp  
[ServiceContract]  
public interface ICustomerManager  
{  
    [OperationContract]     void StoreCustomer(Customer customer);  
  
    [OperationContract]  
    Customer GetCustomer(string firstName, string lastName);  
}  
```  
  
### <a name="add-code-to-the-client-that-sends-a-by-value-object"></a>Hinzufügen von Code zum Client, der ein Per-Wert-Objekt sendet  
 Der folgende Code zeigt, wie der Client ein neues benutzerdefiniertes Per-Wert-Objekt erstellt, einen Kanal erstellt, um mit dem `ICustomerManager`-Dienst kommunizieren zu können, und das benutzerdefinierte Objekt an den Dienst sendet.  
  
 Das benutzerdefinierte Objekt wird serialisiert und an den Dienst gesendet, der das Objekt in eine neue Objektkopie deserialisiert.  Alle Methoden, die der Dienst für dieses Objekt aufruft, werden nur lokal auf dem Server ausgeführt. Es ist wichtig zu beachten, dass dieser Code das Senden eines abgeleiteten Typs (`PremiumCustomer`) veranschaulicht.  Der Dienstvertrag erwartet ein `Customer`-Objekt, aber der Dienstdatenvertrag verwendet das [<xref:System.Runtime.Serialization.KnownTypeAttribute>]-Attribut, um anzugeben, dass `PremiumCustomer` ebenfalls zulässig ist.  WCF verursacht einen Fehler, wenn versucht wird, irgendeinen anderen Typ über diese Dienstschnittstelle zu serialisieren oder zu deserialisieren.  
  
```csharp  
PremiumCustomer customer = new PremiumCustomer();  
customer.Firstname = "John";  
customer.Lastname = "Doe";  
customer.DefaultBillingAddress = new Address();  
customer.DefaultBillingAddress.Street = "One Microsoft Way";  
customer.DefaultDeliveryAddress = customer.DefaultBillingAddress;  
customer.AccountID = 42;  
  
ChannelFactory<ICustomerManager> factory =  
   new ChannelFactory<ICustomerManager>("customermanager");  
ICustomerManager customerManager = factory.CreateChannel();  
customerManager.StoreCustomer(customer);  
```  
  
## <a name="the-service-returns-an-object-by-reference"></a>Der Dienst gibt ein Objekt per Verweis zurück  
 In diesem Szenario ruft die Clientanwendung den Remotedienst auf, und die Methode gibt ein Objekt zurück, das per Verweis vom Dienst an den Client übergeben wird.  
  
 Wie bereits erwähnt, geben WCF-Dienste Objekte immer per Wert zurück.  Sie können allerdings ein ähnliches Ergebnis erzielen, indem Sie die <xref:System.ServiceModel.EndpointAddress10>-Klasse verwenden.  Die <xref:System.ServiceModel.EndpointAddress10>-Klasse ist ein serialisierbares Per-Wert-Objekt, das vom Client dazu verwendet werden kann, ein sitzungsbasiertes Per-Verweis-Objekt auf dem Server abzurufen.  
  
 Das Verhalten des Per-Verweis-Objekts in WCF, das in diesem Szenario dargestellt ist, unterscheidet sich von dem in DCOM.  In DCOM kann der Server ein Per-Verweis-Objekt direkt an den Client zurückgeben, und der Client kann die Methoden dieses Objekts aufrufen, die auf dem Server ausgeführt werden.  In WCF ist das zurückgegebene Objekt dagegen immer ein Per-Wert-Objekt.  Der Client muss dieses Per-Wert-Objekt, das durch <xref:System.ServiceModel.EndpointAddress10> dargestellt ist, übernehmen und aus dem Objekt sein eigenes sitzungsbasiertes Per-Verweis-Objekt erstellen.  Die Clientmethodenaufrufe für das sitzungsbasierte Objekt werden auf dem Server ausgeführt. Mit anderen Worten, dieses Per-Verweis-Objekt in WCF ist ein normaler WCF-Dienst, der als sitzungsbasiert konfiguriert ist.  
  
 In WCF ist eine Sitzung eine Möglichkeit, mehrere Nachrichten zuzuordnen, die zwischen zwei Endpunkten gesendet werden.  Dies bedeutet, dass zwischen dem Client und dem Server eine Sitzung eingerichtet wird, sobald der Client eine Verbindung mit diesem Dienst hergestellt hat.  Der Client verwendet eine einzelne eindeutige Instanz des serverseitigen Objekts für alle Interaktionen innerhalb dieser einzelnen Sitzung. Sitzungsbasierte WCF-Verträge sind vergleichbar mit verbindungsorientierten Netzwerkanforderung/Antwort-Mustern.  
  
 Dieses Szenario wird durch die folgenden DCOM-Methode dargestellt.  
  
```csharp  
public interface IRemoteService  
{  
    IRemoteObject GetObjectByReference();  
}  
```  
  
### <a name="step-1-define-the-sessionful-wcf-service-interface-and-implementation"></a>Schritt 1: Definieren der sitzungsbasierten WCF-Dienstschnittstelle und -Implementierung  
 Als erstes definieren Sie eine WCF-Dienstschnittstelle, die ein sitzungsbasiertes Objekt enthält.  
  
 In diesem Code wird das sitzungsbasierte Objekt mit dem `ServiceContract`-Attribut gekennzeichnet, wodurch das Objekt als ordnungsgemäße WCF-Dienstschnittstelle bestimmt ist.  Außerdem wird die <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A>-Eigenschaft festgelegt, um anzugeben, dass das Objekt ein sitzungsbasierter Dienst ist.  
  
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
  
 Im folgenden Codebeispiel wird die Dienstimplementierung veranschaulicht:  
  
 Der Dienst wird mit dem [ServiceBehavior]-Attribut gekennzeichnet, und seine InstanceContextMode-Eigenschaft wird auf "InstanceContextMode.PerSessions" festgelegt, um anzugeben, dass für jede Sitzung eine eindeutige Instanz dieses Typs erstellt werden muss.  
  
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
  
### <a name="step-2-define-the-wcf-factory-service-for-the-sessionful-object"></a>Schritt 2: Definieren des WCF-Factorydiensts für das sitzungsbasierte Objekt  
 Der Dienst, der das sitzungsbasierte-Objekt erstellt, muss definiert und implementiert werden. Dies wird im folgenden Code veranschaulicht. Dieser Code erstellt einen weiteren WCF-Dienst, der ein <xref:System.ServiceModel.EndpointAddress10>-Objekt zurückgibt.  Dies ist eine serialisierbare Form eines Endpunkts, die vom Server dazu verwendet werden kann, ein sitzungsbasiertes Objekt zu erstellen.  
  
```csharp  
[ServiceContract]  
    public interface ISessionBoundFactory  
    {  
        [OperationContract]  
        EndpointAddress10 GetInstanceAddress();  
    }  
```  
  
 Im Folgenden finden Sie die Implementierung dieses Dienstes. Diese Implementierung verwaltet eine Singleton-Kanalfactory, um sitzungsbasierte Objekte zu erstellen.  Wenn `GetInstanceAddress` aufgerufen wird, werden ein Kanal und ein <xref:System.ServiceModel.EndpointAddress10>-Objekt erstellt, das auf die Remoteadresse verweist, die diesem Kanal zugeordnet ist.   <xref:System.ServiceModel.EndpointAddress10> ist ein Datentyp, der per Wert an den Client zurückgegeben werden kann.
  
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
  
### <a name="step-3-configure-and-start-the-wcf-services"></a>Schritt 3: Konfigurieren und Starten Sie der WCF-Dienste  
 Damit diese Dienste gehostet werden können, müssen Sie die folgenden Erweiterungen in die Konfigurationsdatei (web.config) des Servers einfügen.  
  
1. Fügen Sie einen `<client>`-Abschnitt hinzu, in dem der Endpunkt für das sitzungsbasierte Objekts beschrieben wird.  In diesem Szenario fungiert der Server auch als Client und muss konfiguriert werden, um dies zu ermöglichen.  
  
2. Deklarieren Sie im `<services>`-Abschnitt Dienstendpunkte für die Factory und das sitzungsbasierte Objekt.  Dadurch wird es dem Client ermöglicht, mit den Dienstendpunkten zu kommunizieren, die <xref:System.ServiceModel.EndpointAddress10>-Instanz abzurufen und den sitzungsbasierten Kanal zu erstellen.  
  
 Im Folgenden finden Sie eine Beispielkonfigurationsdatei mit den folgenden Einstellungen:  
  
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
  
 Fügen Sie die folgenden Zeilen zu einer Konsolenanwendung, hinzu um den Dienst mit Selfhosting auszuführen, und starten Sie die Anwendung.  
  
```csharp  
ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
factoryHost.Open();  
  
ServiceHost sessionBoundServiceHost = new ServiceHost(  
typeof(MySessionBoundObject));  
sessionBoundServiceHost.Open();  
```  
  
### <a name="step-4-configure-the-client-and-call-the-service"></a>Schritt 4: Konfigurieren des Clients und Aufrufen des Diensts  
 Konfigurieren Sie den Client so, dass er mit den WCF-Dienste kommunizieren kann. Schreiben Sie dazu die folgenden Einträge in die Anwendungskonfigurationsdatei (app.config) des Projekts.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
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
  
 Um den Dienst aufzurufen, fügen Sie dem Client den Code hinzu, der Folgendes ausführt:  
  
1. Erstellen eines Kanals zu dem `ISessionBoundFactory`-Dienst.  
  
2. Verwenden des Kanals, um den `ISessionBoundFactory`-Dienst aufzurufen und ein <xref:System.ServiceModel.EndpointAddress10>-Objekt zu erhalten.  
  
3. Verwenden des <xref:System.ServiceModel.EndpointAddress10>-Objekts, um einen Kanal zu erstellen, um ein sitzungsbasiertes Objekt zu erhalten.  
  
4. Aufrufen der Methoden `SetCurrentValue` und `GetCurrentValue`, um zu veranschaulichen, dass über mehrere Aufrufe hinweg dieselbe Objektinstanz verwendet wird.  
  
```csharp  
ChannelFactory<ISessionBoundFactory> factory =  
        new ChannelFactory<ISessionBoundFactory>("factory");  
  
ISessionBoundFactory sessionBoundFactory = factory.CreateChannel();  
  
EndpointAddress10 address = sessionBoundFactory.GetInstanceAddress();  
  
ChannelFactory<ISessionBoundObject> sessionBoundObjectFactory =  
    new ChannelFactory<ISessionBoundObject>(  
        new NetTcpBinding(),  
        address.ToEndpointAddress());  
  
ISessionBoundObject sessionBoundObject =  
        sessionBoundObjectFactory.CreateChannel();  
  
sessionBoundObject.SetCurrentValue("Hello");  
if (sessionBoundObject.GetCurrentValue() == "Hello")  
{  
    Console.WriteLine("Session-full instance management works as expected");  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Einfache WCF-Programmierung](../wcf/basic-wcf-programming.md)
- [Entwerfen und Implementieren von Diensten](../wcf/designing-and-implementing-services.md)
- [Erstellen von Clients](../wcf/building-clients.md)
- [Duplexdienste](../wcf/feature-details/duplex-services.md)
