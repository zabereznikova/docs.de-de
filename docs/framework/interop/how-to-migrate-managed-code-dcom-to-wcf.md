---
title: 'Gewusst wie: Migrieren von verwaltetem Code DCOM zu WCF'
ms.date: 03/30/2017
ms.assetid: 52961ffc-d1c7-4f83-832c-786444b951ba
ms.openlocfilehash: 4d814d9c2e62af9aa5cc2a8d1f84738b69e36ad1
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217175"
---
# <a name="how-to-migrate-managed-code-dcom-to-wcf"></a><span data-ttu-id="eb1c3-102">Gewusst wie: Migrieren von verwaltetem Code DCOM zu WCF</span><span class="sxs-lookup"><span data-stu-id="eb1c3-102">How to: Migrate Managed-Code DCOM to WCF</span></span>
<span data-ttu-id="eb1c3-103">Windows Communication Foundation (WCF) ist für Aufrufe von verwaltetem Code zwischen Servern und Clients in einer verteilten Umgebung die empfohlene und sichere Wahl im Vergleich zu DCOM (Distributed Component Object Model).</span><span class="sxs-lookup"><span data-stu-id="eb1c3-103">Windows Communication Foundation (WCF) is the recommended and secure choice over Distributed Component Object Model (DCOM) for managed code calls between servers and clients in a distributed environment.</span></span> <span data-ttu-id="eb1c3-104">In diesem Artikel wird für die folgenden Szenarien gezeigt, wie Sie Code aus DCOM zu WCF migrieren.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-104">This article shows how you to migrate code from DCOM to WCF for the following scenarios.</span></span>  
  
- <span data-ttu-id="eb1c3-105">Der Remotedienst gibt ein Objekt per Wert an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-105">The remote service returns an object by-value to the client</span></span>  
  
- <span data-ttu-id="eb1c3-106">Der Client sendet einen Objekt per Wert an den Remotedienst.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-106">The client sends an object by-value to the remote service</span></span>  
  
- <span data-ttu-id="eb1c3-107">Der Remotedienst gibt ein Objekt per Verweis an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-107">The remote service returns an object by-reference to the client</span></span>  
  
 <span data-ttu-id="eb1c3-108">Aus Sicherheitsgründen ist es in WCF nicht zulässig, ein Objekt per Verweis vom Client an den Dienst zu senden.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-108">For security reasons, sending an object by-reference from the client to the service is not allowed in WCF.</span></span> <span data-ttu-id="eb1c3-109">Ist zwischen Client und Server eine Konversation in beide Richtungen erforderlich, kann dies in WCF mit einem Duplexdienst erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-109">A scenario that requires a conversation back and forth between client and server can be achieved in WCF using a duplex service.</span></span>  <span data-ttu-id="eb1c3-110">Weitere Informationen zu Duplexdiensten finden Sie unter [Duplexdienste](../wcf/feature-details/duplex-services.md).</span><span class="sxs-lookup"><span data-stu-id="eb1c3-110">For more information about duplex services, see [Duplex Services](../wcf/feature-details/duplex-services.md).</span></span>  
  
 <span data-ttu-id="eb1c3-111">Weitere Informationen zum Erstellen von WCF-Diensten und Clients für diese Dienste finden Sie unter [Basis-WCF-Programmierung](../wcf/basic-wcf-programming.md), [Entwerfen und Implementieren von Diensten](../wcf/designing-and-implementing-services.md) und [Erstellen von Clients](../wcf/building-clients.md).</span><span class="sxs-lookup"><span data-stu-id="eb1c3-111">For more details about creating WCF services and clients for those services, see [Basic WCF Programming](../wcf/basic-wcf-programming.md), [Designing and Implementing Services](../wcf/designing-and-implementing-services.md), and [Building Clients](../wcf/building-clients.md).</span></span>  
  
## <a name="dcom-example-code"></a><span data-ttu-id="eb1c3-112">DCOM-Beispielcode</span><span class="sxs-lookup"><span data-stu-id="eb1c3-112">DCOM example code</span></span>  
 <span data-ttu-id="eb1c3-113">Für diese Szenarien haben die DCOM-Schnittstellen, die für die Verwendung mit WCF veranschaulicht werden, die folgende Struktur:</span><span class="sxs-lookup"><span data-stu-id="eb1c3-113">For these scenarios, the DCOM interfaces that are illustrated using WCF have the following structure:</span></span>  
  
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
  
## <a name="the-service-returns-an-object-by-value"></a><span data-ttu-id="eb1c3-114">Der Dienst gibt ein Objekt per Wert zurück</span><span class="sxs-lookup"><span data-stu-id="eb1c3-114">The service returns an object by-value</span></span>  
 <span data-ttu-id="eb1c3-115">In diesem Szenario rufen Sie einen Dienst auf, und dessen Methode gibt ein Objekt zurück, das per Wert vom Server an den Client übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-115">For this scenario, you make a call to a service and it method returns an object, which is passed by-value from the server to the client.</span></span> <span data-ttu-id="eb1c3-116">Dieses Szenario entspricht dem folgenden COM-Aufruf:</span><span class="sxs-lookup"><span data-stu-id="eb1c3-116">This scenario represents the following COM call:</span></span>  
  
```csharp  
public interface IRemoteService  
{  
    Customer GetObjectByValue();  
}  
```  
  
 <span data-ttu-id="eb1c3-117">In diesem Szenario empfängt der Client eine deserialisierte Kopie eines Objekts vom Remotedienst.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-117">In this scenario, the client receives a deserialized copy of an object from the remote service.</span></span> <span data-ttu-id="eb1c3-118">Der Client kann mit dieser lokalen Kopie arbeiten, ohne den Dienst erneut aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-118">The client can interact with this local copy without calling back to the service.</span></span>  <span data-ttu-id="eb1c3-119">Anders ausgedrückt, für den Client ist garantiert, dass der Dienst in keiner Weise beteiligt wird, wenn Methoden der lokalen Kopie aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-119">In other words, the client is guaranteed the service will not be involved in any way when methods on the local copy are called.</span></span> <span data-ttu-id="eb1c3-120">WCF gibt Objekte aus dem Dienst immer per Wert zurück, sodass die folgenden Schritte das Erstellen eines ordnungsgemäßen WCF-Diensts beschreiben.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-120">WCF always returns objects from the service by value, so the following steps describe creating a regular WCF service.</span></span>  
  
### <a name="step-1-define-the-wcf-service-interface"></a><span data-ttu-id="eb1c3-121">Schritt 1: Definieren der Schnittstelle des WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="eb1c3-121">Step 1: Define the WCF service interface</span></span>  
 <span data-ttu-id="eb1c3-122">Definieren Sie eine öffentliche Schnittstelle für den WCF-Dienst, und kennzeichnen Sie sie mit dem [<xref:System.ServiceModel.ServiceContractAttribute>]-Attribut.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-122">Define a public interface for the WCF service and mark it with the [<xref:System.ServiceModel.ServiceContractAttribute>] attribute.</span></span>  <span data-ttu-id="eb1c3-123">Kennzeichnen Sie die Methoden, die Sie für Clients verfügbar machen möchten, mit dem [<xref:System.ServiceModel.OperationContractAttribute>]-Attribut.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-123">Mark the methods you want to expose to clients with the [<xref:System.ServiceModel.OperationContractAttribute>] attribute.</span></span> <span data-ttu-id="eb1c3-124">Im folgenden Beispiel wird gezeigt, wie diese Attribute verwendet werden, um die serverseitige Schnittstelle und die Schnittstellenmethoden zu bestimmen, die ein Client aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-124">The following example shows using these attributes to identify the server-side interface and interface methods a client can call.</span></span> <span data-ttu-id="eb1c3-125">Die für dieses Szenario verwendete Methode ist fett dargestellt.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-125">The method used for this scenario is shown in bold.</span></span>  
  
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
  
### <a name="step-2-define-the-data-contract"></a><span data-ttu-id="eb1c3-126">Schritt 2: Definieren des Datenvertrags</span><span class="sxs-lookup"><span data-stu-id="eb1c3-126">Step 2: Define the data contract</span></span>  
 <span data-ttu-id="eb1c3-127">Als Nächstes sollten Sie einen Datenvertrag für den Dienst erstellen. In diesem Vertrag wird beschrieben, wie die Daten zwischen dem Dienst und seinen Clients ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-127">Next you should create a data contract for the service, which will describe how the data will be exchanged between the service and its clients.</span></span>  <span data-ttu-id="eb1c3-128">Klassen, die in dem Datenvertrag beschrieben sind, müssen mit dem [<xref:System.Runtime.Serialization.DataContractAttribute>]-Attribut gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-128">Classes described in the data contract should be marked with the [<xref:System.Runtime.Serialization.DataContractAttribute>] attribute.</span></span> <span data-ttu-id="eb1c3-129">Die einzelnen Eigenschaften oder Felder, die für Client und Server sichtbar sein sollen, müssen mit dem [<xref:System.Runtime.Serialization.DataMemberAttribute>]-Attribut markiert werden.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-129">The individual properties or fields you want visible to both client and server should be marked with the [<xref:System.Runtime.Serialization.DataMemberAttribute>] attribute.</span></span> <span data-ttu-id="eb1c3-130">Möchten Sie im Datenvertrag Typen zulassen, die aus einer Klasse abgeleitet wurden, müssen Sie diese mit dem [<xref:System.Runtime.Serialization.KnownTypeAttribute>]-Attribut kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-130">If you want types derived from a class in the data contract to be allowed, you must identify them with the [<xref:System.Runtime.Serialization.KnownTypeAttribute>] attribute.</span></span> <span data-ttu-id="eb1c3-131">WCF serialisiert oder deserialisiert nur Typen in der Dienstschnittstelle sowie Typen, die als bekannte Typen gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-131">WCF will only serialize or deserialize types in the service interface and types identified as known types.</span></span> <span data-ttu-id="eb1c3-132">Wenn Sie versuchen, einen Typ zu verwenden, der kein bekannter Typ ist, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-132">If you attempt to use a type that is not a known type, an exception will occur.</span></span>  
  
 <span data-ttu-id="eb1c3-133">Weitere Informationen zu Datenverträgen finden Sie unter [Datenverträge](../wcf/samples/data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="eb1c3-133">For more information about data contracts, see [Data Contracts](../wcf/samples/data-contracts.md).</span></span>  
  
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
  
### <a name="step-3-implement-the-wcf-service"></a><span data-ttu-id="eb1c3-134">Schritt 3: Implementieren des WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="eb1c3-134">Step 3: Implement the WCF service</span></span>  
 <span data-ttu-id="eb1c3-135">Als Nächstes müssen Sie die WCF-Dienstklasse implementieren, in der die Schnittstelle implementiert ist, die Sie im vorherigen Schritt definiert haben.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-135">Next, you should implement the WCF service class that implements the interface you defined in the previous step.</span></span>  
  
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
  
### <a name="step-4-configure-the-service-and-the-client"></a><span data-ttu-id="eb1c3-136">Schritt 4: Konfigurieren des Diensts und des Clients</span><span class="sxs-lookup"><span data-stu-id="eb1c3-136">Step 4: Configure the service and the client</span></span>  
 <span data-ttu-id="eb1c3-137">Um einen WCF-Dienst auszuführen, müssen Sie einen Endpunkt deklarieren, der diese Dienstschnittstelle unter einer bestimmten URL über eine bestimmte WCF-Bindung verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-137">To run a WCF service, you need to declare an endpoint that exposes that service interface at a specific URL using a specific WCF binding.</span></span> <span data-ttu-id="eb1c3-138">Eine Bindung gibt die Transport-, Codierungs- und Protokolldetails an, die für die Kommunikation zwischen Clients und Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-138">A binding specifies the transport, encoding and protocol details for the clients and server to communicate.</span></span> <span data-ttu-id="eb1c3-139">Bindungen fügen Sie üblicherweise in der Konfigurationsdatei (web.config) des Dienstprojekts hinzu.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-139">You typically add bindings to the service project’s configuration file (web.config).</span></span> <span data-ttu-id="eb1c3-140">Nachstehend ist ein Bindungseintrag für den Beispieldienst gezeigt:</span><span class="sxs-lookup"><span data-stu-id="eb1c3-140">The following shows a binding entry for the example service:</span></span>  
  
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
  
 <span data-ttu-id="eb1c3-141">Als Nächstes müssen Sie den Client entsprechend den Bindungsinformationen konfigurieren, die durch den Dienst angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-141">Next, you need to configure the client to match the binding information specified by the service.</span></span> <span data-ttu-id="eb1c3-142">Fügen Sie hierzu Folgendes in der Anwendungskonfigurationsdatei (app.config) des Clients hinzu.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-142">To do so, add the following to the client’s application configuration (app.config) file.</span></span>  
  
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
  
### <a name="step-5-run-the-service"></a><span data-ttu-id="eb1c3-143">Schritt 5: Ausführen des Diensts</span><span class="sxs-lookup"><span data-stu-id="eb1c3-143">Step 5: Run the service</span></span>  
 <span data-ttu-id="eb1c3-144">Schließlich können Sie den Dienst über Selfhosting in einer Konsolenanwendung bereitstellen, indem Sie der Dienstanwendung die folgenden Zeilen hinzufügen und die Anwendung starten.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-144">Finally, you can self-host it in a console application by adding the following lines to the service app, and starting the app.</span></span> <span data-ttu-id="eb1c3-145">Weitere Informationen zu anderen Möglichkeiten zum Hosten einer WCF-Dienstanwendung finden Sie unter [Hosting-Dienste](../wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="eb1c3-145">For more information about other ways to host a WCF service application, [Hosting Services](../wcf/hosting-services.md).</span></span>  
  
```csharp  
ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
customerServiceHost.Open();  
```  
  
### <a name="step-6-call-the-service-from-the-client"></a><span data-ttu-id="eb1c3-146">Schritt 6: Aufrufen des Diensts aus dem Client</span><span class="sxs-lookup"><span data-stu-id="eb1c3-146">Step 6: Call the service from the client</span></span>  
 <span data-ttu-id="eb1c3-147">Um den Dienst aus dem Client aufzurufen, müssen Sie eine Kanalfactory für den Dienst erstellen und einen Kanal anfordern, wodurch es Ihnen ermöglicht wird, die `GetCustomer`-Methode direkt aus dem Client aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-147">To call the service from the client, you need to create a channel factory for the service, and request a channel, which will enable you to directly call the `GetCustomer` method directly from the client.</span></span> <span data-ttu-id="eb1c3-148">Der Kanal implementiert die Schnittstelle des Diensts und verarbeitet die zugrunde liegende Anforderung/Antwort-Logik für Sie.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-148">The channel implements the service’s interface and handles the underlying request/reply logic for you.</span></span>  <span data-ttu-id="eb1c3-149">Der Rückgabewert von diesem Methodenaufruf ist die deserialisierte Kopie der Antwort des Diensts.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-149">The return value from that method call is the deserialized copy of the service response.</span></span>  
  
```csharp  
ChannelFactory<ICustomerManager> factory =   
     new ChannelFactory<ICustomerManager>("customermanager");  
ICustomerManager service = factory.CreateChannel();  
Customer customer = service.GetCustomer("Mary", "Smith");  
```  
  
## <a name="the-client-sends-a-by-value-object-to-the-server"></a><span data-ttu-id="eb1c3-150">Der Client sendet ein Per-Wert-Objekt an den Server</span><span class="sxs-lookup"><span data-stu-id="eb1c3-150">The client sends a by-value object to the server</span></span>  
 <span data-ttu-id="eb1c3-151">In diesem Szenario sendet der Client ein Objekt per Wert an den Server.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-151">In this scenario, the client sends an object to the server, by-value.</span></span> <span data-ttu-id="eb1c3-152">Dies bedeutet, dass der Server eine deserialisierte Kopie des Objekts empfängt.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-152">This means that the server will receive a deserialized copy of the object.</span></span>  <span data-ttu-id="eb1c3-153">Der Server kann Methoden aus dieser Kopie aufrufen und kann sicher sein, dass es keinen Rückruf in den Clientcode gibt.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-153">The server can call methods on that copy and be guaranteed there is no callback into client code.</span></span> <span data-ttu-id="eb1c3-154">Wie bereits erwähnt, erfolgen die normalen WCF-Austauschvorgänge von Daten per Wert.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-154">As mentioned previously, normal WCF exchanges of data are by-value.</span></span>  <span data-ttu-id="eb1c3-155">Dadurch ist sichergestellt, dass Methoden, die für eines dieser Objekte aufgerufen werden, nur lokal ausgeführt werden –  es wird kein Code auf dem Client aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-155">This guarantees that calling methods on one of these objects executes locally only – it will not invoke code on the client.</span></span>  
  
 <span data-ttu-id="eb1c3-156">Dieses Szenario entspricht dem folgenden COM-Methodenaufruf:</span><span class="sxs-lookup"><span data-stu-id="eb1c3-156">This scenario represents the following COM method call:</span></span>  
  
```csharp  
public interface IRemoteService  
{  
    void SendObjectByValue(Customer customer);  
}  
```  
  
 <span data-ttu-id="eb1c3-157">In diesem Szenario werden dieselbe Schnittstelle und derselbe Dienstvertrag verwendet wie im ersten Beispiel.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-157">This scenario uses the same service interface and data contract as shown in the first example.</span></span> <span data-ttu-id="eb1c3-158">Darüber hinaus werden der Client und der Dienst auf die gleiche Weise konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-158">In addition, the client and service will be configured in the same way.</span></span> <span data-ttu-id="eb1c3-159">In diesem Beispiel wird ein Kanal erstellt, um das Objekt zu senden aus in gleicher Weise ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-159">In this example, a channel is created to send the object and run the same way.</span></span> <span data-ttu-id="eb1c3-160">Allerdings erstellen Sie für dieses Beispiel einen Client, der den Dienst aufruft, wobei ein Objekt per Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-160">However, for this example, you will create a client that calls the service, passing an object by-value.</span></span> <span data-ttu-id="eb1c3-161">Die Dienstmethode, die der Client im Dienstvertrag aufruft, ist fett dargestellt:</span><span class="sxs-lookup"><span data-stu-id="eb1c3-161">The service method the client will call in the service contract is shown in bold:</span></span>  
  
```csharp  
[ServiceContract]  
public interface ICustomerManager  
{  
    [OperationContract]     void StoreCustomer(Customer customer);  
  
    [OperationContract]  
    Customer GetCustomer(string firstName, string lastName);  
}  
```  
  
### <a name="add-code-to-the-client-that-sends-a-by-value-object"></a><span data-ttu-id="eb1c3-162">Hinzufügen von Code zum Client, der ein Per-Wert-Objekt sendet</span><span class="sxs-lookup"><span data-stu-id="eb1c3-162">Add code to the client that sends a by-value object</span></span>  
 <span data-ttu-id="eb1c3-163">Der folgende Code zeigt, wie der Client ein neues benutzerdefiniertes Per-Wert-Objekt erstellt, einen Kanal erstellt, um mit dem `ICustomerManager`-Dienst kommunizieren zu können, und das benutzerdefinierte Objekt an den Dienst sendet.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-163">The following code shows how the client creates a new by-value customer object, creates a channel to communicate with the `ICustomerManager` service, and sends the customer object to it.</span></span>  
  
 <span data-ttu-id="eb1c3-164">Das benutzerdefinierte Objekt wird serialisiert und an den Dienst gesendet, der das Objekt in eine neue Objektkopie deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-164">The customer object will be serialized, and sent to the service, where it is deserialized by the service into a new copy of that object.</span></span>  <span data-ttu-id="eb1c3-165">Alle Methoden, die der Dienst für dieses Objekt aufruft, werden nur lokal auf dem Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-165">Any methods the service calls on this object will execute only locally on the server.</span></span> <span data-ttu-id="eb1c3-166">Es ist wichtig zu beachten, dass dieser Code das Senden eines abgeleiteten Typs (`PremiumCustomer`) veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-166">It’s important to note that this code illustrates sending a derived type (`PremiumCustomer`).</span></span>  <span data-ttu-id="eb1c3-167">Der Dienstvertrag erwartet ein `Customer`-Objekt, aber der Dienstdatenvertrag verwendet das [<xref:System.Runtime.Serialization.KnownTypeAttribute>]-Attribut, um anzugeben, dass `PremiumCustomer` ebenfalls zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-167">The service contract expects a `Customer` object, but the service data contract uses the [<xref:System.Runtime.Serialization.KnownTypeAttribute>] attribute to indicate that `PremiumCustomer` is also allowed.</span></span>  <span data-ttu-id="eb1c3-168">WCF verursacht einen Fehler, wenn versucht wird, irgendeinen anderen Typ über diese Dienstschnittstelle zu serialisieren oder zu deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-168">WCF will fail attempts to serialize or deserialize any other type via this service interface.</span></span>  
  
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
  
## <a name="the-service-returns-an-object-by-reference"></a><span data-ttu-id="eb1c3-169">Der Dienst gibt ein Objekt per Verweis zurück</span><span class="sxs-lookup"><span data-stu-id="eb1c3-169">The service returns an object by reference</span></span>  
 <span data-ttu-id="eb1c3-170">In diesem Szenario ruft die Clientanwendung den Remotedienst auf, und die Methode gibt ein Objekt zurück, das per Verweis vom Dienst an den Client übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-170">For this scenario, the client app makes a call to the remote service and the method returns an object, which is passed by reference from the service to the client.</span></span>  
  
 <span data-ttu-id="eb1c3-171">Wie bereits erwähnt, geben WCF-Dienste Objekte immer per Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-171">As mentioned previously, WCF services always return object by value.</span></span>  <span data-ttu-id="eb1c3-172">Sie können allerdings ein ähnliches Ergebnis erzielen, indem Sie die <xref:System.ServiceModel.EndpointAddress10>-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-172">However, you can achieve a similar result by using the <xref:System.ServiceModel.EndpointAddress10> class.</span></span>  <span data-ttu-id="eb1c3-173">Die <xref:System.ServiceModel.EndpointAddress10>-Klasse ist ein serialisierbares Per-Wert-Objekt, das vom Client dazu verwendet werden kann, ein sitzungsbasiertes Per-Verweis-Objekt auf dem Server abzurufen.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-173">The <xref:System.ServiceModel.EndpointAddress10> is a serializable by-value object that can be used by the client to obtain a sessionful by-reference object on the server.</span></span>  
  
 <span data-ttu-id="eb1c3-174">Das Verhalten des Per-Verweis-Objekts in WCF, das in diesem Szenario dargestellt ist, unterscheidet sich von dem in DCOM.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-174">The behavior of the by-reference object in WCF shown in this scenario is different than DCOM.</span></span>  <span data-ttu-id="eb1c3-175">In DCOM kann der Server ein Per-Verweis-Objekt direkt an den Client zurückgeben, und der Client kann die Methoden dieses Objekts aufrufen, die auf dem Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-175">In DCOM, the server can return a by-reference object to the client directly, and the client can call that object’s methods, which execute on the server.</span></span>  <span data-ttu-id="eb1c3-176">In WCF ist das zurückgegebene Objekt dagegen immer ein Per-Wert-Objekt.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-176">In WCF, however, the object returned is always by-value.</span></span>  <span data-ttu-id="eb1c3-177">Der Client muss dieses Per-Wert-Objekt, das durch <xref:System.ServiceModel.EndpointAddress10> dargestellt ist, übernehmen und aus dem Objekt sein eigenes sitzungsbasiertes Per-Verweis-Objekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-177">The client must take that by-value object, represented by <xref:System.ServiceModel.EndpointAddress10> and use it to create its own sessionful by-reference object.</span></span>  <span data-ttu-id="eb1c3-178">Die Clientmethodenaufrufe für das sitzungsbasierte Objekt werden auf dem Server ausgeführt. Mit anderen Worten, dieses Per-Verweis-Objekt in WCF ist ein normaler WCF-Dienst, der als sitzungsbasiert konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-178">The client method calls on the sessionful object execute on the server.In other words, this by-reference object in WCF is a normal WCF service that is configured to be sessionful.</span></span>  
  
 <span data-ttu-id="eb1c3-179">In WCF ist eine Sitzung eine Möglichkeit, mehrere Nachrichten zuzuordnen, die zwischen zwei Endpunkten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-179">In WCF, a session is a way of correlating multiple messages sent between two endpoints.</span></span>  <span data-ttu-id="eb1c3-180">Dies bedeutet, dass zwischen dem Client und dem Server eine Sitzung eingerichtet wird, sobald der Client eine Verbindung mit diesem Dienst hergestellt hat.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-180">This means that once a client obtains a connection to this service, a session will be established between the client and the server.</span></span>  <span data-ttu-id="eb1c3-181">Der Client verwendet eine einzelne eindeutige Instanz des serverseitigen Objekts für alle Interaktionen innerhalb dieser einzelnen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-181">The client will use a single unique instance of the server-side object for all its interactions within this single session.</span></span> <span data-ttu-id="eb1c3-182">Sitzungsbasierte WCF-Verträge sind vergleichbar mit verbindungsorientierten Netzwerkanforderung/Antwort-Mustern.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-182">Sessionful WCF contracts are similar to connection-oriented network request/response patterns.</span></span>  
  
 <span data-ttu-id="eb1c3-183">Dieses Szenario wird durch die folgenden DCOM-Methode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-183">This scenario is represented by the following DCOM method.</span></span>  
  
```csharp  
public interface IRemoteService  
{  
    IRemoteObject GetObjectByReference();  
}  
```  
  
### <a name="step-1-define-the-sessionful-wcf-service-interface-and-implementation"></a><span data-ttu-id="eb1c3-184">Schritt 1: Definieren der sitzungsbasierten WCF-Dienstschnittstelle und -Implementierung</span><span class="sxs-lookup"><span data-stu-id="eb1c3-184">Step 1: Define the Sessionful WCF service interface and implementation</span></span>  
 <span data-ttu-id="eb1c3-185">Als erstes definieren Sie eine WCF-Dienstschnittstelle, die ein sitzungsbasiertes Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-185">First, define a WCF service interface that contains the sessionful object.</span></span>  
  
 <span data-ttu-id="eb1c3-186">In diesem Code wird das sitzungsbasierte Objekt mit dem `ServiceContract`-Attribut gekennzeichnet, wodurch das Objekt als ordnungsgemäße WCF-Dienstschnittstelle bestimmt ist.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-186">In this code, the sessionful object is marked with the `ServiceContract` attribute, which identifies it as a regular WCF service interface.</span></span>  <span data-ttu-id="eb1c3-187">Außerdem wird die <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A>-Eigenschaft festgelegt, um anzugeben, dass das Objekt ein sitzungsbasierter Dienst ist.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-187">In addition, the <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A> property is set to indicate it will be a sessionful service.</span></span>  
  
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
  
 <span data-ttu-id="eb1c3-188">Im folgenden Codebeispiel wird die Dienstimplementierung veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="eb1c3-188">The following code shows the service implementation.</span></span>  
  
 <span data-ttu-id="eb1c3-189">Der Dienst wird mit dem [ServiceBehavior]-Attribut gekennzeichnet, und seine InstanceContextMode-Eigenschaft wird auf "InstanceContextMode.PerSessions" festgelegt, um anzugeben, dass für jede Sitzung eine eindeutige Instanz dieses Typs erstellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-189">The service is marked with the [ServiceBehavior] attribute, and its InstanceContextMode property set to InstanceContextMode.PerSessions to indicate that a unique instance of this type should be created for each session.</span></span>  
  
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
  
### <a name="step-2-define-the-wcf-factory-service-for-the-sessionful-object"></a><span data-ttu-id="eb1c3-190">Schritt 2: Definieren des WCF-Factorydiensts für das sitzungsbasierte Objekt</span><span class="sxs-lookup"><span data-stu-id="eb1c3-190">Step 2: Define the WCF factory service for the sessionful object</span></span>  
 <span data-ttu-id="eb1c3-191">Der Dienst, der das sitzungsbasierte-Objekt erstellt, muss definiert und implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-191">The service that creates the sessionful object must be defined and implemented.</span></span> <span data-ttu-id="eb1c3-192">Dies wird im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-192">The following code shows how to do this.</span></span> <span data-ttu-id="eb1c3-193">Dieser Code erstellt einen weiteren WCF-Dienst, der ein <xref:System.ServiceModel.EndpointAddress10>-Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-193">This code creates another WCF service that returns an <xref:System.ServiceModel.EndpointAddress10> object.</span></span>  <span data-ttu-id="eb1c3-194">Dies ist eine serialisierbare Form eines Endpunkts, die vom Server dazu verwendet werden kann, ein sitzungsbasiertes Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-194">This is a serializable form of an endpoint the can use to create the session-full object.</span></span>  
  
```csharp  
[ServiceContract]  
    public interface ISessionBoundFactory  
    {  
        [OperationContract]  
        EndpointAddress10 GetInstanceAddress();  
    }  
```  
  
 <span data-ttu-id="eb1c3-195">Im folgenden finden Sie die Implementierung dieses Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-195">The following is the implementation of this service.</span></span> <span data-ttu-id="eb1c3-196">Diese Implementierung verwaltet eine Singleton-Kanalfactory, um sitzungsbasierte Objekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-196">This implementation maintains a singleton channel factory to create sessionful objects.</span></span>  <span data-ttu-id="eb1c3-197">Wenn `GetInstanceAddress` aufgerufen wird, werden ein Kanal und ein <xref:System.ServiceModel.EndpointAddress10>-Objekt erstellt, das auf die Remoteadresse verweist, die diesem Kanal zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-197">When `GetInstanceAddress` is called, it creates a channel and creates an <xref:System.ServiceModel.EndpointAddress10> object that points to the remote address associated with this channel.</span></span>   <span data-ttu-id="eb1c3-198"><xref:System.ServiceModel.EndpointAddress10> ist ein Datentyp, der per Wert an den Client zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-198"><xref:System.ServiceModel.EndpointAddress10> is a data type that can be returned to the client by-value.</span></span>
  
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
  
### <a name="step-3-configure-and-start-the-wcf-services"></a><span data-ttu-id="eb1c3-199">Schritt 3: Konfigurieren und Starten Sie der WCF-Dienste</span><span class="sxs-lookup"><span data-stu-id="eb1c3-199">Step 3: Configure and start the WCF services</span></span>  
 <span data-ttu-id="eb1c3-200">Damit diese Dienste gehostet werden können, müssen Sie die folgenden Erweiterungen in die Konfigurationsdatei (web.config) des Servers einfügen.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-200">To host these services, you will need to make the following additions to the server’s configuration file (web.config).</span></span>  
  
1. <span data-ttu-id="eb1c3-201">Fügen Sie einen `<client>`-Abschnitt hinzu, in dem der Endpunkt für das sitzungsbasierte Objekts beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-201">Add a `<client>` section that describes the endpoint for the sessionful object.</span></span>  <span data-ttu-id="eb1c3-202">In diesem Szenario fungiert der Server auch als Client und muss konfiguriert werden, um dies zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-202">In this scenario, the server also acts as a client and must be configured to enable this.</span></span>  
  
2. <span data-ttu-id="eb1c3-203">Deklarieren Sie im `<services>`-Abschnitt Dienstendpunkte für die Factory und das sitzungsbasierte Objekt.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-203">In the `<services>` section, declare service endpoints for the factory and sessionful object.</span></span>  <span data-ttu-id="eb1c3-204">Dadurch wird es dem Client ermöglicht, mit den Dienstendpunkten zu kommunizieren, die <xref:System.ServiceModel.EndpointAddress10>-Instanz abzurufen und den sitzungsbasierten Kanal zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-204">This enables the client to communicate with the service endpoints, acquire the <xref:System.ServiceModel.EndpointAddress10> and create the sessionful channel.</span></span>  
  
 <span data-ttu-id="eb1c3-205">Im folgenden finden Sie eine Beispielkonfigurationsdatei mit diesen Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="eb1c3-205">The following is an example configuration file with these settings:</span></span>  
  
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
  
 <span data-ttu-id="eb1c3-206">Fügen Sie die folgenden Zeilen zu einer Konsolenanwendung, hinzu um den Dienst mit Selfhosting auszuführen, und starten Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-206">Add the following lines to a console application, to self-host the service, and start the app.</span></span>  
  
```csharp  
ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
factoryHost.Open();  
  
ServiceHost sessionBoundServiceHost = new ServiceHost(  
typeof(MySessionBoundObject));  
sessionBoundServiceHost.Open();  
```  
  
### <a name="step-4-configure-the-client-and-call-the-service"></a><span data-ttu-id="eb1c3-207">Schritt 4: Konfigurieren des Clients und Aufrufen des Diensts</span><span class="sxs-lookup"><span data-stu-id="eb1c3-207">Step 4: Configure the client and call the service</span></span>  
 <span data-ttu-id="eb1c3-208">Konfigurieren Sie den Client so, dass er mit den WCF-Dienste kommunizieren kann. Schreiben Sie dazu die folgenden Einträge in die Anwendungskonfigurationsdatei (app.config) des Projekts.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-208">Configure the client to communicate with the WCF services by making the following entries in the project’s application configuration file (app.config).</span></span>  
  
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
  
 <span data-ttu-id="eb1c3-209">Um den Dienst aufzurufen, fügen Sie dem Client den Code hinzu, der Folgendes ausführt:</span><span class="sxs-lookup"><span data-stu-id="eb1c3-209">To call the service, add the code to the client to do the following:</span></span>  
  
1. <span data-ttu-id="eb1c3-210">Erstellen eines Kanals zu dem `ISessionBoundFactory`-Dienst.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-210">Create a channel to the `ISessionBoundFactory` service.</span></span>  
  
2. <span data-ttu-id="eb1c3-211">Verwenden des Kanals, um den `ISessionBoundFactory`-Dienst aufzurufen und ein <xref:System.ServiceModel.EndpointAddress10>-Objekt zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-211">Use the channel to invoke the `ISessionBoundFactory` service an obtain an <xref:System.ServiceModel.EndpointAddress10> object.</span></span>  
  
3. <span data-ttu-id="eb1c3-212">Verwenden des <xref:System.ServiceModel.EndpointAddress10>-Objekts, um einen Kanal zu erstellen, um ein sitzungsbasiertes Objekt zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-212">Use the <xref:System.ServiceModel.EndpointAddress10> to create a channel to obtain a sessionful object.</span></span>  
  
4. <span data-ttu-id="eb1c3-213">Aufrufen der Methoden `SetCurrentValue` und `GetCurrentValue`, um zu veranschaulichen, dass über mehrere Aufrufe hinweg dieselbe Objektinstanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-213">Call the `SetCurrentValue` and `GetCurrentValue` methods to demonstrate it remains the same object instance is used across multiple calls.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eb1c3-214">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb1c3-214">See also</span></span>

- [<span data-ttu-id="eb1c3-215">Einfache WCF-Programmierung</span><span class="sxs-lookup"><span data-stu-id="eb1c3-215">Basic WCF Programming</span></span>](../wcf/basic-wcf-programming.md)
- [<span data-ttu-id="eb1c3-216">Entwerfen und Implementieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="eb1c3-216">Designing and Implementing Services</span></span>](../wcf/designing-and-implementing-services.md)
- [<span data-ttu-id="eb1c3-217">Erstellen von Clients</span><span class="sxs-lookup"><span data-stu-id="eb1c3-217">Building Clients</span></span>](../wcf/building-clients.md)
- [<span data-ttu-id="eb1c3-218">Duplexdienste</span><span class="sxs-lookup"><span data-stu-id="eb1c3-218">Duplex Services</span></span>](../wcf/feature-details/duplex-services.md)
