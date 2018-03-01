---
title: "Übersicht über die Endpunkterstellung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- endpoints [WCF], overview
ms.assetid: f4dce0fb-6f54-47e6-8054-86d7f574b91c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fa20edd8fa43fb1e6a28f7b1ec18f83fedd96bca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="endpoint-creation-overview"></a><span data-ttu-id="4b883-102">Übersicht über die Endpunkterstellung</span><span class="sxs-lookup"><span data-stu-id="4b883-102">Endpoint Creation Overview</span></span>
<span data-ttu-id="4b883-103">Die gesamte Kommunikation mit einem [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] -Dienst verläuft über die *Endpunkte* des Diensts.</span><span class="sxs-lookup"><span data-stu-id="4b883-103">All communication with a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="4b883-104">Endpunkte ermöglichen Clients den Zugriff auf die Funktionalität, die ein [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="4b883-104">Endpoints provide the clients access to the functionality that a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service offers.</span></span> <span data-ttu-id="4b883-105">In diesem Abschnitt wird die Struktur eines Endpunkts beschrieben und dargestellt, wie ein Endpunkt in einer Konfiguration oder im Code definiert wird.</span><span class="sxs-lookup"><span data-stu-id="4b883-105">This section describes the structure of an endpoint and outlines how to define an endpoint in configuration and in code.</span></span>  
  
## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="4b883-106">Die Struktur eines Endpunkts</span><span class="sxs-lookup"><span data-stu-id="4b883-106">The Structure of an Endpoint</span></span>  
 <span data-ttu-id="4b883-107">Jeder Endpunkt beinhaltet eine Adresse, die angibt, wo sich der Endpunkt befindet, eine Bindung, die angibt, wie ein Client mit dem Endpunkt kommunizieren kann und einen Vertrag angibt, der die verfügbaren Methoden identifiziert.</span><span class="sxs-lookup"><span data-stu-id="4b883-107">Each endpoint contains an address that indicates where to find the endpoint, a binding that specifies how a client can communicate with the endpoint, and a contract that identifies the methods available.</span></span>  
  
-   <span data-ttu-id="4b883-108">**Adresse**.</span><span class="sxs-lookup"><span data-stu-id="4b883-108">**Address**.</span></span> <span data-ttu-id="4b883-109">Die Adresse gewährleistet eine eindeutige Identifizierung des Endpunkts und teilt potenziellen Consumern den Standort des Diensts mit.</span><span class="sxs-lookup"><span data-stu-id="4b883-109">The address uniquely identifies the endpoint and tells potential consumers where the service is located.</span></span> <span data-ttu-id="4b883-110">Die Adresse wird im [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Objektmodell durch die <xref:System.ServiceModel.EndpointAddress>-Adresse dargestellt, die einen Uniform Resource Identifier (URI) und Adresseigenschaften beinhaltet, die wiederum eine Identität, einige Web Services Description Language (WSDL)-Elemente und eine Auflistung der optionalen Header enthalten.</span><span class="sxs-lookup"><span data-stu-id="4b883-110">It is represented in the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] object model by the <xref:System.ServiceModel.EndpointAddress> address, which contains a Uniform Resource Identifier (URI) and address properties that include an identity, some Web Services Description Language (WSDL) elements, and a collection of optional headers.</span></span> <span data-ttu-id="4b883-111">Die optionalen Header stellen zusätzliche ausführliche Adressinformationen bereit, um den Endpunkt zu identifizieren oder damit zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="4b883-111">The optional headers provide additional detailed addressing information to identify or interact with the endpoint.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="4b883-112">[Angeben einer Endpunktadresse](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="4b883-112"> [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
-   <span data-ttu-id="4b883-113">**Binden von**.</span><span class="sxs-lookup"><span data-stu-id="4b883-113">**Binding**.</span></span> <span data-ttu-id="4b883-114">Die Bindung gibt an, wie eine Kommunikation mit dem Endpunkt stattfindet.</span><span class="sxs-lookup"><span data-stu-id="4b883-114">The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="4b883-115">Die Bindung gibt an, wie der Endpunkt mit der Außenwelt kommuniziert (einschließlich des zu verwendenden Transportprotokolls, beispielsweise TCP oder HTTP), welche Codierung für die Nachrichten zu verwenden ist (beispielsweise Text- oder Binärcodierung) und welche Sicherheitsanforderungen erforderlich sind (beispielsweise Secure Sockets Layer [SSL] oder SOAP-Nachrichtensicherheit).</span><span class="sxs-lookup"><span data-stu-id="4b883-115">The binding specifies how the endpoint communicates with the world, including which transport protocol to use (for example, TCP or HTTP), which encoding to use for the messages (for example, text or binary), and which security requirements are necessary (for example, Secure Sockets Layer [SSL] or SOAP message security).</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="4b883-116">[Verwenden von Bindungen, um Dienste und Clients konfigurieren](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="4b883-116"> [Using Bindings to Configure Services and Clients](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).</span></span>  
  
-   <span data-ttu-id="4b883-117">**Dienstvertrag**.</span><span class="sxs-lookup"><span data-stu-id="4b883-117">**Service contract**.</span></span> <span data-ttu-id="4b883-118">Der Dienstvertrag zeigt, welche Funktionen der Endpunkt dem Client zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="4b883-118">The service contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="4b883-119">In einem Vertrag wird Folgendes angegeben: die Vorgänge, die ein Client aufrufen kann, die Form der Nachricht und der Typ der Eingabeparameter oder die Daten, die zum Aufrufen des Vorgangs erforderlich sind, sowie die Art der Verarbeitung oder die Antwortnachricht, die der Client erwarten kann.</span><span class="sxs-lookup"><span data-stu-id="4b883-119">A contract specifies the operations that a client can call, the form of the message and the type of input parameters or data required to call the operation, and the kind of processing or response message the client can expect.</span></span> <span data-ttu-id="4b883-120">Drei grundlegende Vertragstypen entsprechen grundlegenden Nachrichtenaustauschmustern: Datagramm (unidirektional), Anforderung/Antwort und Duplex (bidirektional).</span><span class="sxs-lookup"><span data-stu-id="4b883-120">Three basic types of contracts correspond to basic message exchange patterns (MEPs): datagram (one-way), request/reply, and duplex (bidirectional).</span></span> <span data-ttu-id="4b883-121">Für den Dienstvertrag können zudem Daten- und Nachrichtenverträge verwendet werden, um beim Zugriff bestimmte Datentypen und Nachrichtenformate zu fordern.</span><span class="sxs-lookup"><span data-stu-id="4b883-121">The service contract can also employ data and message contracts to require specific data types and message formats when being accessed.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="4b883-122">zum Definieren eines Dienstvertrags finden Sie unter [Entwerfen von Dienstverträgen](../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="4b883-122"> how to define a service contract, see [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).</span></span> <span data-ttu-id="4b883-123">Ein Client kann ggf. auch dazu aufgefordert werden, einen vom Dienst definierten Vertrag zu implementieren (wird als Rückrufvertrag bezeichnet), um vom Dienst in einem Duplexnachrichten-Austauschmuster Nachrichten zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="4b883-123">Note that a client may also be required to implement a service-defined contract, called a callback contract, to receive messages from the service in a duplex MEP.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="4b883-124">[Duplexdienste](../../../docs/framework/wcf/feature-details/duplex-services.md).</span><span class="sxs-lookup"><span data-stu-id="4b883-124"> [Duplex Services](../../../docs/framework/wcf/feature-details/duplex-services.md).</span></span>  
  
 <span data-ttu-id="4b883-125">Der Endpunkt für einen Dienst kann entweder verbindlich durch Verwenden von Code oder deklarativ durch Konfiguration angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4b883-125">The endpoint for a service can be specified either imperatively by using code or declaratively through configuration.</span></span> <span data-ttu-id="4b883-126">Wenn keine Endpunkte angegeben sind, stellt die Runtime Standardendpunkte bereit, indem ein Standardendpunkt für alle Basisadressen in jedem Dienstvertrag, der vom Dienst implementiert wird, hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="4b883-126">If no endpoints are specified then the runtime provides default endpoints by adding one default endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="4b883-127">Die Definition von Endpunkten im Code ist normalerweise nicht geeignet, da die Bindungen und Adressen für einen bereitgestellten Dienst sich in der Regel von denen unterscheiden, die während der Entwicklung des Diensts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4b883-127">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="4b883-128">Im Allgemeinen ist es praktischer, Dienstendpunkte nicht mit Code, sondern mit Konfiguration zu definieren.</span><span class="sxs-lookup"><span data-stu-id="4b883-128">Generally, it is more practical to define service endpoints using configuration rather than code.</span></span> <span data-ttu-id="4b883-129">Werden die Bindung und die Adressinformationen nicht in den Code integriert, ist eine Änderung ohne Neukompilierung und erneute Bereitstellung der Anwendung möglich.</span><span class="sxs-lookup"><span data-stu-id="4b883-129">Keeping the binding and addressing information out of the code allows them to change without having to recompile and redeploy the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b883-130">Beim Hinzufügen eines Dienstendpunkts, der einen Identitätswechsel ausführt, muss entweder eine der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methoden oder die <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29>-Methode verwendet werden, um den Vertrag ordnungsgemäß in ein neues <xref:System.ServiceModel.Description.ServiceDescription>-Objekt zu laden.</span><span class="sxs-lookup"><span data-stu-id="4b883-130">When adding a service endpoint that performs impersonation, you must either use one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods or the <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29> method to properly load the contract into a new <xref:System.ServiceModel.Description.ServiceDescription> object.</span></span>  
  
## <a name="defining-endpoints-in-code"></a><span data-ttu-id="4b883-131">Definieren von Endpunkten in Code</span><span class="sxs-lookup"><span data-stu-id="4b883-131">Defining Endpoints in Code</span></span>  
 <span data-ttu-id="4b883-132">Im folgenden Beispiel wird die Angabe eines Endpunkts in Code veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="4b883-132">The following example illustrates how to specify an endpoint in code with the following:</span></span>  
  
-   <span data-ttu-id="4b883-133">Definieren Sie einen Vertrag für eine `IEcho` Typ des Diensts, der sich bei einem Namen und mit der Antwort Echo akzeptiert "Hello \<Name >!".</span><span class="sxs-lookup"><span data-stu-id="4b883-133">Define a contract for an `IEcho` type of service that accepts someone's name and echo with the response "Hello \<name>!".</span></span>  
  
-   <span data-ttu-id="4b883-134">Implementieren Sie einen `Echo`-Dienst des Typs, der durch den `IEcho`-Vertrag definiert wird.</span><span class="sxs-lookup"><span data-stu-id="4b883-134">Implement an `Echo` service of the type defined by the `IEcho` contract.</span></span>  
  
-   <span data-ttu-id="4b883-135">Geben Sie für den Dienst die Endpunktadresse http://localhost:8000/Echo an.</span><span class="sxs-lookup"><span data-stu-id="4b883-135">Specify an endpoint address of http://localhost:8000/Echo for the service.</span></span>  
  
-   <span data-ttu-id="4b883-136">Konfigurieren Sie den `Echo`-Dienst mithilfe einer <xref:System.ServiceModel.WSHttpBinding>-Bindung.</span><span class="sxs-lookup"><span data-stu-id="4b883-136">Configure the `Echo` service using a <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
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
>  <span data-ttu-id="4b883-137">Der Diensthost wird mit einer Basisadresse erstellt. Anschließend wird der Rest der Adresse relativ zur Basisadresse als Teil eines Endpunkts angegeben.</span><span class="sxs-lookup"><span data-stu-id="4b883-137">The service host is created with a base address and then the rest of the address, relative to the base address, is specified as part of an endpoint.</span></span> <span data-ttu-id="4b883-138">Diese Partitionierung der Adresse ermöglicht die einfachere Definition von mehreren Endpunkten für Dienste an einem Host.</span><span class="sxs-lookup"><span data-stu-id="4b883-138">This partitioning of the address allows multiple endpoints to be defined more conveniently for services at a host.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b883-139">Eigenschaften von <xref:System.ServiceModel.Description.ServiceDescription> in der Dienstanwendung dürfen nicht im Anschluss an die <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A>-Methode auf <xref:System.ServiceModel.ServiceHostBase> geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4b883-139">Properties of <xref:System.ServiceModel.Description.ServiceDescription> in the service application must not be modified subsequent to the <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> method on <xref:System.ServiceModel.ServiceHostBase>.</span></span> <span data-ttu-id="4b883-140">Einige Member, wie die <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>-Eigenschaft und die `AddServiceEndpoint`-Methoden auf <xref:System.ServiceModel.ServiceHostBase> und <xref:System.ServiceModel.ServiceHost>, lösen eine Ausnahme aus, wenn eine Änderung über diesen Punkt hinaus stattfindet.</span><span class="sxs-lookup"><span data-stu-id="4b883-140">Some members, such as the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property and the `AddServiceEndpoint` methods on <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.ServiceHost>, throw an exception if modified past that point.</span></span> <span data-ttu-id="4b883-141">Andere Member können geändert werden, wobei das Ergebnis jedoch nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="4b883-141">Others permit you to modify them, but the result is undefined.</span></span>  
>   
>  <span data-ttu-id="4b883-142">Ähnlich verhält es sich mit den <xref:System.ServiceModel.Description.ServiceEndpoint>-Werten, die auf dem Client nach dem Aufruf von <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> auf <xref:System.ServiceModel.ChannelFactory> nicht geändert werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="4b883-142">Similarly, on the client the <xref:System.ServiceModel.Description.ServiceEndpoint> values must not be modified after the call to <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> on the <xref:System.ServiceModel.ChannelFactory>.</span></span> <span data-ttu-id="4b883-143">Die <xref:System.ServiceModel.ChannelFactory.Credentials%2A>-Eigenschaft löst eine Ausnahme aus, wenn sie über diesen Punkt hinaus geändert wird.</span><span class="sxs-lookup"><span data-stu-id="4b883-143">The <xref:System.ServiceModel.ChannelFactory.Credentials%2A> property throws an exception if modified past that point.</span></span> <span data-ttu-id="4b883-144">Die anderen Clientbeschreibungswerte können ohne Fehler geändert werden, aber das Ergebnis ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="4b883-144">The other client description values can be modified without error, but the result is undefined.</span></span>  
>   
>  <span data-ttu-id="4b883-145">Sowohl für den Dienst als auch den Client wird empfohlen, die Beschreibung vor dem Aufruf von <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4b883-145">Whether for the service or client, it is recommended that you modify the description prior to calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span>  
  
## <a name="defining-endpoints-in-configuration"></a><span data-ttu-id="4b883-146">Definieren von Endpunkten in der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="4b883-146">Defining Endpoints in Configuration</span></span>  
 <span data-ttu-id="4b883-147">Beim Erstellen einer Anwendung sollen dem Administrator, der die Anwendung bereitstellt, Entscheidungen häufig verzögert mitgeteilt werden.</span><span class="sxs-lookup"><span data-stu-id="4b883-147">When creating an application, you often want to defer decisions to the administrator who is deploying the application.</span></span> <span data-ttu-id="4b883-148">Beispielsweise weiß man häufig nicht, welche Dienstadresse (URI) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4b883-148">For example, there is often no way of knowing in advance what a service address (a URI) will be.</span></span> <span data-ttu-id="4b883-149">Anstatt eine Adresse fest zu programmieren, sollte diese Aufgabe einem Administrator nach dem Erstellen eines Diensts übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="4b883-149">Instead of hard-coding an address, it is preferable to allow an administrator to do so after creating a service.</span></span> <span data-ttu-id="4b883-150">Diese Flexibilität wird durch Konfiguration ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="4b883-150">This flexibility is accomplished through configuration.</span></span> <span data-ttu-id="4b883-151">Weitere Informationen finden Sie unter [Konfigurieren von Services](../../../docs/framework/wcf/configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="4b883-151">For details, see [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b883-152">Verwenden der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) mit der `/config:` *Filename*`[,`*Filename* `]` wechseln Sie zu Erstellen Sie schnell Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="4b883-152">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) with the `/config:`*filename*`[,`*filename*`]` switch to quickly create configuration files.</span></span>  
  
## <a name="using-default-endpoints"></a><span data-ttu-id="4b883-153">Verwenden von Standardendpunkten</span><span class="sxs-lookup"><span data-stu-id="4b883-153">Using Default Endpoints</span></span>  
 <span data-ttu-id="4b883-154">Wenn im Code oder in der Konfiguration keine Endpunkte angegeben sind, stellt die Runtime Standardendpunkte bereit, indem ein Standardendpunkt für alle Basisadressen in jedem Dienstvertrag, der vom Dienst implementiert wird, hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="4b883-154">If no endpoints are specified in code or in configuration then the runtime provides default endpoints by adding one default endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="4b883-155">Die Basisadresse kann im Code oder in der Konfiguration angegeben werden, und die Standardendpunkte werden hinzugefügt, wenn <xref:System.ServiceModel.ICommunicationObject.Open> auf dem <xref:System.ServiceModel.ServiceHost> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4b883-155">The base address can be specified in code or in configuration, and the default endpoints are added when <xref:System.ServiceModel.ICommunicationObject.Open> is called on the <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="4b883-156">Dieses Beispiel entspricht dem Beispiel aus dem vorherigen Abschnitt. Da aber keine Endpunkte angegeben sind, werden die Standardendpunkte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4b883-156">This example is the same example from the previous section, but since no endpoints are specified, the default endpoints are added.</span></span>  
  
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
  
 <span data-ttu-id="4b883-157">Wenn Endpunkte explizit bereitgestellt werden, können die Standardpunkte dennoch hinzugefügt werden, indem <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> auf dem <xref:System.ServiceModel.ServiceHost> aufgerufen wird, bevor <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4b883-157">If endpoints are explicitly provided, the default endpoints can still be added by calling <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> on the <xref:System.ServiceModel.ServiceHost> before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="4b883-158">Standardendpunkte, finden Sie unter [vereinfachte Konfiguration](../../../docs/framework/wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="4b883-158"> default endpoints, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b883-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b883-159">See Also</span></span>  
 [<span data-ttu-id="4b883-160">Implementieren von Dienstverträgen</span><span class="sxs-lookup"><span data-stu-id="4b883-160">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)
