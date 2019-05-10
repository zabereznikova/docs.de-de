---
title: Übersicht über die Endpunkterstellung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- endpoints [WCF], overview
ms.assetid: f4dce0fb-6f54-47e6-8054-86d7f574b91c
ms.openlocfilehash: fa6486db483c004430e0e8ed75c75a6b25c05d6b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64613588"
---
# <a name="endpoint-creation-overview"></a><span data-ttu-id="b64fc-102">Übersicht über die Endpunkterstellung</span><span class="sxs-lookup"><span data-stu-id="b64fc-102">Endpoint Creation Overview</span></span>
<span data-ttu-id="b64fc-103">Die gesamte Kommunikation mit einem Windows Communication Foundation (WCF)-Dienst erfolgt über die *Endpunkte* des Diensts.</span><span class="sxs-lookup"><span data-stu-id="b64fc-103">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="b64fc-104">Endpunkte ermöglichen Clients den Zugriff auf die Funktionen, die ein WCF-Dienst bietet.</span><span class="sxs-lookup"><span data-stu-id="b64fc-104">Endpoints provide the clients access to the functionality that a WCF service offers.</span></span> <span data-ttu-id="b64fc-105">In diesem Abschnitt wird die Struktur eines Endpunkts beschrieben und dargestellt, wie ein Endpunkt in einer Konfiguration oder im Code definiert wird.</span><span class="sxs-lookup"><span data-stu-id="b64fc-105">This section describes the structure of an endpoint and outlines how to define an endpoint in configuration and in code.</span></span>  
  
## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="b64fc-106">Die Struktur eines Endpunkts</span><span class="sxs-lookup"><span data-stu-id="b64fc-106">The Structure of an Endpoint</span></span>  
 <span data-ttu-id="b64fc-107">Jeder Endpunkt beinhaltet eine Adresse, die angibt, wo sich der Endpunkt befindet, eine Bindung, die angibt, wie ein Client mit dem Endpunkt kommunizieren kann und einen Vertrag angibt, der die verfügbaren Methoden identifiziert.</span><span class="sxs-lookup"><span data-stu-id="b64fc-107">Each endpoint contains an address that indicates where to find the endpoint, a binding that specifies how a client can communicate with the endpoint, and a contract that identifies the methods available.</span></span>  
  
- <span data-ttu-id="b64fc-108">**Adresse**.</span><span class="sxs-lookup"><span data-stu-id="b64fc-108">**Address**.</span></span> <span data-ttu-id="b64fc-109">Die Adresse gewährleistet eine eindeutige Identifizierung des Endpunkts und teilt potenziellen Consumern den Standort des Diensts mit.</span><span class="sxs-lookup"><span data-stu-id="b64fc-109">The address uniquely identifies the endpoint and tells potential consumers where the service is located.</span></span> <span data-ttu-id="b64fc-110">Es wird dargestellt, in dem WCF-Objektmodell durch die <xref:System.ServiceModel.EndpointAddress> Adresse, die enthält einen Uniform Resource Identifier (URI) und Adresseigenschaften, die eine Identität, einige Web Services Description Language (WSDL)-Elemente und eine Auflistung der optionalen enthalten. Header.</span><span class="sxs-lookup"><span data-stu-id="b64fc-110">It is represented in the WCF object model by the <xref:System.ServiceModel.EndpointAddress> address, which contains a Uniform Resource Identifier (URI) and address properties that include an identity, some Web Services Description Language (WSDL) elements, and a collection of optional headers.</span></span> <span data-ttu-id="b64fc-111">Die optionalen Header stellen zusätzliche ausführliche Adressinformationen bereit, um den Endpunkt zu identifizieren oder damit zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="b64fc-111">The optional headers provide additional detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="b64fc-112">Weitere Informationen finden Sie unter [angeben einer Endpunktadresse](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="b64fc-112">For more information, see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
- <span data-ttu-id="b64fc-113">**Binden von**.</span><span class="sxs-lookup"><span data-stu-id="b64fc-113">**Binding**.</span></span> <span data-ttu-id="b64fc-114">Die Bindung gibt an, wie eine Kommunikation mit dem Endpunkt stattfindet.</span><span class="sxs-lookup"><span data-stu-id="b64fc-114">The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="b64fc-115">Die Bindung gibt an, wie der Endpunkt mit der Außenwelt kommuniziert (einschließlich des zu verwendenden Transportprotokolls, beispielsweise TCP oder HTTP), welche Codierung für die Nachrichten zu verwenden ist (beispielsweise Text- oder Binärcodierung) und welche Sicherheitsanforderungen erforderlich sind (beispielsweise Secure Sockets Layer [SSL] oder SOAP-Nachrichtensicherheit).</span><span class="sxs-lookup"><span data-stu-id="b64fc-115">The binding specifies how the endpoint communicates with the world, including which transport protocol to use (for example, TCP or HTTP), which encoding to use for the messages (for example, text or binary), and which security requirements are necessary (for example, Secure Sockets Layer [SSL] or SOAP message security).</span></span> <span data-ttu-id="b64fc-116">Weitere Informationen finden Sie unter [Verwendung von Bindungen zum Konfigurieren von Diensten und Clients](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="b64fc-116">For more information, see [Using Bindings to Configure Services and Clients](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).</span></span>  
  
- <span data-ttu-id="b64fc-117">**Dienstvertrag**.</span><span class="sxs-lookup"><span data-stu-id="b64fc-117">**Service contract**.</span></span> <span data-ttu-id="b64fc-118">Der Dienstvertrag zeigt, welche Funktionen der Endpunkt dem Client zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="b64fc-118">The service contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="b64fc-119">In einem Vertrag wird Folgendes angegeben: die Vorgänge, die ein Client aufrufen kann, die Form der Nachricht und der Typ der Eingabeparameter oder die Daten, die zum Aufrufen des Vorgangs erforderlich sind, sowie die Art der Verarbeitung oder die Antwortnachricht, die der Client erwarten kann.</span><span class="sxs-lookup"><span data-stu-id="b64fc-119">A contract specifies the operations that a client can call, the form of the message and the type of input parameters or data required to call the operation, and the kind of processing or response message the client can expect.</span></span> <span data-ttu-id="b64fc-120">Drei grundlegende Vertragstypen entsprechen grundlegenden Nachrichtenaustauschmustern: Datagramm (unidirektional), Anforderung/Antwort und Duplex (bidirektional).</span><span class="sxs-lookup"><span data-stu-id="b64fc-120">Three basic types of contracts correspond to basic message exchange patterns (MEPs): datagram (one-way), request/reply, and duplex (bidirectional).</span></span> <span data-ttu-id="b64fc-121">Für den Dienstvertrag können zudem Daten- und Nachrichtenverträge verwendet werden, um beim Zugriff bestimmte Datentypen und Nachrichtenformate zu fordern.</span><span class="sxs-lookup"><span data-stu-id="b64fc-121">The service contract can also employ data and message contracts to require specific data types and message formats when being accessed.</span></span> <span data-ttu-id="b64fc-122">Weitere Informationen über das Definieren eines Dienstvertrags finden Sie unter [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="b64fc-122">For more information about how to define a service contract, see [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).</span></span> <span data-ttu-id="b64fc-123">Ein Client kann ggf. auch dazu aufgefordert werden, einen vom Dienst definierten Vertrag zu implementieren (wird als Rückrufvertrag bezeichnet), um vom Dienst in einem Duplexnachrichten-Austauschmuster Nachrichten zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="b64fc-123">Note that a client may also be required to implement a service-defined contract, called a callback contract, to receive messages from the service in a duplex MEP.</span></span> <span data-ttu-id="b64fc-124">Weitere Informationen finden Sie unter [Duplexdienste](../../../docs/framework/wcf/feature-details/duplex-services.md).</span><span class="sxs-lookup"><span data-stu-id="b64fc-124">For more information, see [Duplex Services](../../../docs/framework/wcf/feature-details/duplex-services.md).</span></span>  
  
 <span data-ttu-id="b64fc-125">Der Endpunkt für einen Dienst kann entweder verbindlich durch Verwenden von Code oder deklarativ durch Konfiguration angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b64fc-125">The endpoint for a service can be specified either imperatively by using code or declaratively through configuration.</span></span> <span data-ttu-id="b64fc-126">Wenn keine Endpunkte angegeben sind, stellt die Runtime Standardendpunkte bereit, indem ein Standardendpunkt für alle Basisadressen in jedem Dienstvertrag, der vom Dienst implementiert wird, hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b64fc-126">If no endpoints are specified then the runtime provides default endpoints by adding one default endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="b64fc-127">Die Definition von Endpunkten im Code ist normalerweise nicht geeignet, da die Bindungen und Adressen für einen bereitgestellten Dienst sich in der Regel von denen unterscheiden, die während der Entwicklung des Diensts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b64fc-127">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="b64fc-128">Im Allgemeinen ist es praktischer, Dienstendpunkte nicht mit Code, sondern mit Konfiguration zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b64fc-128">Generally, it is more practical to define service endpoints using configuration rather than code.</span></span> <span data-ttu-id="b64fc-129">Werden die Bindung und die Adressinformationen nicht in den Code integriert, ist eine Änderung ohne Neukompilierung und erneute Bereitstellung der Anwendung möglich.</span><span class="sxs-lookup"><span data-stu-id="b64fc-129">Keeping the binding and addressing information out of the code allows them to change without having to recompile and redeploy the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b64fc-130">Beim Hinzufügen eines Dienstendpunkts, der einen Identitätswechsel ausführt, muss entweder eine der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methoden oder die <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29>-Methode verwendet werden, um den Vertrag ordnungsgemäß in ein neues <xref:System.ServiceModel.Description.ServiceDescription>-Objekt zu laden.</span><span class="sxs-lookup"><span data-stu-id="b64fc-130">When adding a service endpoint that performs impersonation, you must either use one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods or the <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29> method to properly load the contract into a new <xref:System.ServiceModel.Description.ServiceDescription> object.</span></span>  
  
## <a name="defining-endpoints-in-code"></a><span data-ttu-id="b64fc-131">Definieren von Endpunkten in Code</span><span class="sxs-lookup"><span data-stu-id="b64fc-131">Defining Endpoints in Code</span></span>  
 <span data-ttu-id="b64fc-132">Im folgenden Beispiel wird die Angabe eines Endpunkts in Code veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="b64fc-132">The following example illustrates how to specify an endpoint in code with the following:</span></span>  
  
- <span data-ttu-id="b64fc-133">Definieren eines Dienstvertrags für eine `IEcho` Typ des Diensts, die akzeptiert ein Name und die Antwort "Hello \<Name >!".</span><span class="sxs-lookup"><span data-stu-id="b64fc-133">Define a contract for an `IEcho` type of service that accepts someone's name and echo with the response "Hello \<name>!".</span></span>  
  
- <span data-ttu-id="b64fc-134">Implementieren Sie einen `Echo`-Dienst des Typs, der durch den `IEcho`-Vertrag definiert wird.</span><span class="sxs-lookup"><span data-stu-id="b64fc-134">Implement an `Echo` service of the type defined by the `IEcho` contract.</span></span>  
  
- <span data-ttu-id="b64fc-135">Geben Sie die Endpunktadresse `http://localhost:8000/Echo` für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="b64fc-135">Specify an endpoint address of `http://localhost:8000/Echo` for the service.</span></span>  
  
- <span data-ttu-id="b64fc-136">Konfigurieren Sie den `Echo`-Dienst mithilfe einer <xref:System.ServiceModel.WSHttpBinding>-Bindung.</span><span class="sxs-lookup"><span data-stu-id="b64fc-136">Configure the `Echo` service using a <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
```csharp  
Namespace Echo  
{  
   // Define the contract for the IEcho service   
   [ServiceContract]  
   public interface IEcho  
   {  
       [OperationContract]  
       String Hello(string name)  
   }  
  
   // Create an Echo service that implements IEcho contract  
   class Echo : IEcho  
   {  
      public string Hello(string name)  
      {  
         return "Hello" + name + "!";  
      }  
      public static void Main ()  
      {  
          //Specify the base address for Echo service.  
          Uri echoUri = new Uri("http://localhost:8000/");  
  
          //Create a ServiceHost for the Echo service.  
          ServiceHost serviceHost = new ServiceHost(typeof(Echo),echoUri);  
  
          // Use a predefined WSHttpBinding to configure the service.  
          WSHttpBinding binding = new WSHttpBinding();  
  
          // Add the endpoint for this service to the service host.  
          serviceHost.AddServiceEndpoint(  
             typeof(IEcho),   
             binding,   
             echoUri  
           );  
  
          // Open the service host to run it.  
          serviceHost.Open();  
     }  
  }  
}  
```  
  
```vb  
' Define the contract for the IEcho service  
    <ServiceContract()> _  
    Public Interface IEcho  
        <OperationContract()> _  
        Function Hello(ByVal name As String) As String  
    End Interface  
  
' Create an Echo service that implements IEcho contract  
    Public Class Echo   
        Implements IEcho  
        Public Function Hello(ByVal name As String) As String _  
 Implements ICalculator.Hello  
            Dim result As String = "Hello" + name + "!"  
            Return result  
        End Function  
  
' Specify the base address for Echo service.  
Dim echoUri As Uri = New Uri("http://localhost:8000/")  
  
' Create a ServiceHost for the Echo service.  
Dim svcHost As ServiceHost = New ServiceHost(GetType(HelloWorld), echoUri)  
  
' Use a predefined WSHttpBinding to configure the service.  
Dim binding As New WSHttpBinding()  
  
' Add the endpoint for this service to the service host.  
serviceHost.AddServiceEndpoint(GetType(IEcho), binding, echoUri)  
  
' Open the service host to run it.  
serviceHost.Open()  
```  
  
> [!NOTE]
>  <span data-ttu-id="b64fc-137">Der Diensthost wird mit einer Basisadresse erstellt. Anschließend wird der Rest der Adresse relativ zur Basisadresse als Teil eines Endpunkts angegeben.</span><span class="sxs-lookup"><span data-stu-id="b64fc-137">The service host is created with a base address and then the rest of the address, relative to the base address, is specified as part of an endpoint.</span></span> <span data-ttu-id="b64fc-138">Diese Partitionierung der Adresse ermöglicht die einfachere Definition von mehreren Endpunkten für Dienste an einem Host.</span><span class="sxs-lookup"><span data-stu-id="b64fc-138">This partitioning of the address allows multiple endpoints to be defined more conveniently for services at a host.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b64fc-139">Eigenschaften von <xref:System.ServiceModel.Description.ServiceDescription> in der Dienstanwendung dürfen nicht im Anschluss an die <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A>-Methode auf <xref:System.ServiceModel.ServiceHostBase> geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b64fc-139">Properties of <xref:System.ServiceModel.Description.ServiceDescription> in the service application must not be modified subsequent to the <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> method on <xref:System.ServiceModel.ServiceHostBase>.</span></span> <span data-ttu-id="b64fc-140">Einige Member, wie die <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>-Eigenschaft und die `AddServiceEndpoint`-Methoden auf <xref:System.ServiceModel.ServiceHostBase> und <xref:System.ServiceModel.ServiceHost>, lösen eine Ausnahme aus, wenn eine Änderung über diesen Punkt hinaus stattfindet.</span><span class="sxs-lookup"><span data-stu-id="b64fc-140">Some members, such as the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property and the `AddServiceEndpoint` methods on <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.ServiceHost>, throw an exception if modified past that point.</span></span> <span data-ttu-id="b64fc-141">Andere Member können geändert werden, wobei das Ergebnis jedoch nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b64fc-141">Others permit you to modify them, but the result is undefined.</span></span>  
>   
>  <span data-ttu-id="b64fc-142">Ähnlich verhält es sich mit den <xref:System.ServiceModel.Description.ServiceEndpoint>-Werten, die auf dem Client nach dem Aufruf von <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> auf <xref:System.ServiceModel.ChannelFactory> nicht geändert werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="b64fc-142">Similarly, on the client the <xref:System.ServiceModel.Description.ServiceEndpoint> values must not be modified after the call to <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> on the <xref:System.ServiceModel.ChannelFactory>.</span></span> <span data-ttu-id="b64fc-143">Die <xref:System.ServiceModel.ChannelFactory.Credentials%2A>-Eigenschaft löst eine Ausnahme aus, wenn sie über diesen Punkt hinaus geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b64fc-143">The <xref:System.ServiceModel.ChannelFactory.Credentials%2A> property throws an exception if modified past that point.</span></span> <span data-ttu-id="b64fc-144">Die anderen Clientbeschreibungswerte können ohne Fehler geändert werden, aber das Ergebnis ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="b64fc-144">The other client description values can be modified without error, but the result is undefined.</span></span>  
>   
>  <span data-ttu-id="b64fc-145">Sowohl für den Dienst als auch den Client wird empfohlen, die Beschreibung vor dem Aufruf von <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b64fc-145">Whether for the service or client, it is recommended that you modify the description prior to calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span>  
  
## <a name="defining-endpoints-in-configuration"></a><span data-ttu-id="b64fc-146">Definieren von Endpunkten in der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b64fc-146">Defining Endpoints in Configuration</span></span>  
 <span data-ttu-id="b64fc-147">Beim Erstellen einer Anwendung sollen dem Administrator, der die Anwendung bereitstellt, Entscheidungen häufig verzögert mitgeteilt werden.</span><span class="sxs-lookup"><span data-stu-id="b64fc-147">When creating an application, you often want to defer decisions to the administrator who is deploying the application.</span></span> <span data-ttu-id="b64fc-148">Beispielsweise weiß man häufig nicht, welche Dienstadresse (URI) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b64fc-148">For example, there is often no way of knowing in advance what a service address (a URI) will be.</span></span> <span data-ttu-id="b64fc-149">Anstatt eine Adresse fest zu programmieren, sollte diese Aufgabe einem Administrator nach dem Erstellen eines Diensts übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="b64fc-149">Instead of hard-coding an address, it is preferable to allow an administrator to do so after creating a service.</span></span> <span data-ttu-id="b64fc-150">Diese Flexibilität wird durch Konfiguration ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="b64fc-150">This flexibility is accomplished through configuration.</span></span> <span data-ttu-id="b64fc-151">Weitere Informationen finden Sie unter [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="b64fc-151">For details, see [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b64fc-152">Verwenden der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) mit der `/config:` *Filename*`[,`*Filename* `]` wechseln Sie zu Erstellen Sie schnell die Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="b64fc-152">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) with the `/config:`*filename*`[,`*filename*`]` switch to quickly create configuration files.</span></span>  
  
## <a name="using-default-endpoints"></a><span data-ttu-id="b64fc-153">Verwenden von Standardendpunkten</span><span class="sxs-lookup"><span data-stu-id="b64fc-153">Using Default Endpoints</span></span>  
 <span data-ttu-id="b64fc-154">Wenn im Code oder in der Konfiguration keine Endpunkte angegeben sind, stellt die Runtime Standardendpunkte bereit, indem ein Standardendpunkt für alle Basisadressen in jedem Dienstvertrag, der vom Dienst implementiert wird, hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b64fc-154">If no endpoints are specified in code or in configuration then the runtime provides default endpoints by adding one default endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="b64fc-155">Die Basisadresse kann im Code oder in der Konfiguration angegeben werden, und die Standardendpunkte werden hinzugefügt, wenn <xref:System.ServiceModel.ICommunicationObject.Open> auf dem <xref:System.ServiceModel.ServiceHost> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b64fc-155">The base address can be specified in code or in configuration, and the default endpoints are added when <xref:System.ServiceModel.ICommunicationObject.Open> is called on the <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="b64fc-156">Dieses Beispiel entspricht dem Beispiel aus dem vorherigen Abschnitt. Da aber keine Endpunkte angegeben sind, werden die Standardendpunkte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b64fc-156">This example is the same example from the previous section, but since no endpoints are specified, the default endpoints are added.</span></span>  
  
```csharp  
Namespace Echo  
{  
   // Define the contract for the IEcho service   
   [ServiceContract]  
   Interface IEcho  
   {  
       [OperationContract]  
       String Hello(string name)  
   }  
  
   // Create an Echo service that implements IEcho contract  
   Class Echo : IEcho  
   {  
      Public string Hello(string name)  
      {  
         return "Hello" + name + "!";  
      }  
      static void Main ()  
      {  
          //Specify the base address for Echo service.  
          Uri echoUri = new Uri("http://localhost:8000/");  
  
          //Create a ServiceHost for the Echo service.  
          ServiceHost serviceHost = new ServiceHost(typeof(Echo),echoUri);  
  
          // Open the service host to run it. Default endpoints  
          // are added when the service is opened.  
          serviceHost.Open();  
     }  
  }  
}  
```  
  
```vb  
' Define the contract for the IEcho service  
    <ServiceContract()> _  
    Public Interface IEcho  
        <OperationContract()> _  
        Function Hello(ByVal name As String) As String  
    End Interface  
  
' Create an Echo service that implements IEcho contract  
    Public Class Echo   
        Implements IEcho  
        Public Function Hello(ByVal name As String) As String _  
 Implements ICalculator.Hello  
            Dim result As String = "Hello" + name + "!"  
            Return result  
        End Function  
  
' Specify the base address for Echo service.  
Dim echoUri As Uri = New Uri("http://localhost:8000/")  
  
' Open the service host to run it. Default endpoints  
' are added when the service is opened.  
serviceHost.Open()  
```  
  
 <span data-ttu-id="b64fc-157">Wenn Endpunkte explizit bereitgestellt werden, können die Standardpunkte dennoch hinzugefügt werden, indem <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> auf dem <xref:System.ServiceModel.ServiceHost> aufgerufen wird, bevor <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b64fc-157">If endpoints are explicitly provided, the default endpoints can still be added by calling <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> on the <xref:System.ServiceModel.ServiceHost> before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span> <span data-ttu-id="b64fc-158">Weitere Informationen zu Standardendpunkten, finden Sie unter [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="b64fc-158">For more information about default endpoints, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b64fc-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b64fc-159">See also</span></span>

- [<span data-ttu-id="b64fc-160">Implementieren von Dienstverträgen</span><span class="sxs-lookup"><span data-stu-id="b64fc-160">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)
