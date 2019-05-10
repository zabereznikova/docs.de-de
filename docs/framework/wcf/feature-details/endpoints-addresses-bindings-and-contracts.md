---
title: 'Endpunkte: Adressen, Bindungen und Verträge'
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: 3d345cfa3169e22e7c5e85cd1c7d11c2feef4f5f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665963"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a><span data-ttu-id="c244c-102">Endpunkte: Adressen, Bindungen und Verträge</span><span class="sxs-lookup"><span data-stu-id="c244c-102">Endpoints: Addresses, Bindings, and Contracts</span></span>
<span data-ttu-id="c244c-103">Die gesamte Kommunikation mit einem Windows Communication Foundation (WCF)-Dienst erfolgt über die *Endpunkte* des Diensts.</span><span class="sxs-lookup"><span data-stu-id="c244c-103">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="c244c-104">Endpunkte ermöglichen Clients den Zugriff auf die von einem WCF-Dienst bereitgestellten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="c244c-104">Endpoints provide clients access to the functionality offered by a WCF service.</span></span>  
  
 <span data-ttu-id="c244c-105">Jeder Endpunkt verfügt über vier Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="c244c-105">Each endpoint consists of four properties:</span></span>  
  
- <span data-ttu-id="c244c-106">Eine Adresse, die angibt, wo der Endpunkt zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="c244c-106">An address that indicates where the endpoint can be found.</span></span>  
  
- <span data-ttu-id="c244c-107">Eine Bindung, die angibt, wie ein Client mit dem Endpunkt kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="c244c-107">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
- <span data-ttu-id="c244c-108">Ein Vertrag, der die verfügbaren Vorgänge identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c244c-108">A contract that identifies the operations available.</span></span>  
  
- <span data-ttu-id="c244c-109">Eine Gruppe von Verhaltensweisen, die lokale Implementierungsdetails des Endpunkts angeben.</span><span class="sxs-lookup"><span data-stu-id="c244c-109">A set of behaviors that specify local implementation details of the endpoint.</span></span>  
  
 <span data-ttu-id="c244c-110">In diesem Thema wird diese endpunktstruktur erläutert, und es wird erläutert, wie sie in der WCF-Objektmodell dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c244c-110">This topic discusses this endpoint structure and explains how it is represented in the WCF object model.</span></span>  
  
## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="c244c-111">Die Struktur eines Endpunkts</span><span class="sxs-lookup"><span data-stu-id="c244c-111">The Structure of an Endpoint</span></span>  
 <span data-ttu-id="c244c-112">Jeder Endpunkt besteht aus Folgendem:</span><span class="sxs-lookup"><span data-stu-id="c244c-112">Each endpoint consists of the following:</span></span>  
  
- <span data-ttu-id="c244c-113">Adresse: Die Adresse eine eindeutige Identifikation des Endpunkts und teilt potenziellen Consumern des Diensts, in dem es gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="c244c-113">Address: The address uniquely identifies the endpoint and tells potential consumers of the service where it is located.</span></span> <span data-ttu-id="c244c-114">Es wird dargestellt, in dem WCF-Objektmodell durch die <xref:System.ServiceModel.EndpointAddress> Klasse.</span><span class="sxs-lookup"><span data-stu-id="c244c-114">It is represented in the WCF object model by the <xref:System.ServiceModel.EndpointAddress> class.</span></span> <span data-ttu-id="c244c-115">Eine <xref:System.ServiceModel.EndpointAddress>-Klasse enthält:</span><span class="sxs-lookup"><span data-stu-id="c244c-115">An <xref:System.ServiceModel.EndpointAddress> class contains:</span></span>  
  
    - <span data-ttu-id="c244c-116">Eine <xref:System.ServiceModel.EndpointAddress.Uri%2A>-Eigenschaft, die die Adresse des Diensts darstellt.</span><span class="sxs-lookup"><span data-stu-id="c244c-116">A <xref:System.ServiceModel.EndpointAddress.Uri%2A> property, which represents the address of the service.</span></span>  
  
    - <span data-ttu-id="c244c-117">Eine <xref:System.ServiceModel.EndpointAddress.Identity%2A>-Eigenschaft, die die Sicherheits-ID des Diensts und eine Auflistung optionaler Nachrichtenheader darstellt.</span><span class="sxs-lookup"><span data-stu-id="c244c-117">An <xref:System.ServiceModel.EndpointAddress.Identity%2A> property, which represents the security identity of the service and a collection of optional message headers.</span></span> <span data-ttu-id="c244c-118">Die optionalen Nachrichtenheader werden verwendet, um zusätzliche und ausführlichere Adressinformationen bereitzustellen, um den Endpunkt zu identifizieren oder damit zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="c244c-118">The optional message headers are used to provide additional and more detailed addressing information to identify or interact with the endpoint.</span></span>  
  
     <span data-ttu-id="c244c-119">Weitere Informationen finden Sie unter [angeben einer Endpunktadresse](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="c244c-119">For more information, see [Specifying an Endpoint Address](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
- <span data-ttu-id="c244c-120">Bindung: Die Bindung gibt an, wie eine Kommunikation mit dem Endpunkt stattfindet.</span><span class="sxs-lookup"><span data-stu-id="c244c-120">Binding: The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="c244c-121">Dies umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c244c-121">This includes:</span></span>  
  
    - <span data-ttu-id="c244c-122">Das Transportprotokoll, das verwendet werden soll (z.&amp;#160;B. TCP oder HTTP).</span><span class="sxs-lookup"><span data-stu-id="c244c-122">The transport protocol to use (for example, TCP or HTTP).</span></span>  
  
    - <span data-ttu-id="c244c-123">Die Codierung, die für die Nachrichten verwendet werden soll (z.&amp;#160;B. Text oder binär).</span><span class="sxs-lookup"><span data-stu-id="c244c-123">The encoding to use for the messages (for example, text or binary).</span></span>  
  
    - <span data-ttu-id="c244c-124">Die erforderlichen Sicherheitsanforderungen (z.&amp;#160;B. SSL- oder SOAP-Nachrichtensicherheit).</span><span class="sxs-lookup"><span data-stu-id="c244c-124">The necessary security requirements (for example, SSL or SOAP message security).</span></span>  
  
     <span data-ttu-id="c244c-125">Weitere Informationen finden Sie unter [WCF-Bindungsübersicht](../../../../docs/framework/wcf/bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c244c-125">For more information, see [WCF Bindings Overview](../../../../docs/framework/wcf/bindings-overview.md).</span></span> <span data-ttu-id="c244c-126">Eine Bindung wird durch die abstrakte Basisklasse im WCF-Objektmodell dargestellt <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="c244c-126">A binding is represented in the WCF object model by the abstract base class <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="c244c-127">Für die meisten Szenarien können Benutzer eine der vom System bereitgestellten Bindungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c244c-127">For most scenarios, users can use one of the system-provided bindings.</span></span> <span data-ttu-id="c244c-128">Weitere Informationen finden Sie unter [System-provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="c244c-128">For more information, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
- <span data-ttu-id="c244c-129">Verträge: Der Dienstvertrag zeigt, welche Funktionen der Endpunkt, an den Client verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="c244c-129">Contracts: The contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="c244c-130">Ein Vertrag gibt Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="c244c-130">A contract specifies:</span></span>  
  
    - <span data-ttu-id="c244c-131">Welche Vorgänge von einem Client aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="c244c-131">What operations can be called by a client.</span></span>  
  
    - <span data-ttu-id="c244c-132">Die Form der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="c244c-132">The form of the message.</span></span>  
  
    - <span data-ttu-id="c244c-133">Der Typ der Eingabeparameter oder Daten, die zum Aufrufen des Vorgangs erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c244c-133">The type of input parameters or data required to call the operation.</span></span>  
  
    - <span data-ttu-id="c244c-134">Den Typ der Verarbeitung oder der Antwortnachricht, den der Client erwarten kann.</span><span class="sxs-lookup"><span data-stu-id="c244c-134">What type of processing or response message the client can expect.</span></span>  
  
     <span data-ttu-id="c244c-135">Weitere Informationen zum Definieren eines Vertrags finden Sie unter [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="c244c-135">For more information about defining a contract, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
- <span data-ttu-id="c244c-136">Verhaltensweisen: Sie können die Endpunktverhalten verwenden, um das lokale Verhalten des Dienstendpunkts anzupassen.</span><span class="sxs-lookup"><span data-stu-id="c244c-136">Behaviors: You can use endpoint behaviors to customize the local behavior of the service endpoint.</span></span> <span data-ttu-id="c244c-137">Endpunktverhaltensweisen erreichen dies, indem Sie im Prozess der Erstellung einer WCFruntime an.</span><span class="sxs-lookup"><span data-stu-id="c244c-137">Endpoint behaviors achieve this by participating in the process of building a WCFruntime.</span></span> <span data-ttu-id="c244c-138">Ein Beispiel für ein Endpunktverhalten ist die <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A>-Eigenschaft, mit der Sie eine andere Listeningadresse als die SOAP- oder die WSDL-Adresse (WSDL = Web Services Description Language) angeben können.</span><span class="sxs-lookup"><span data-stu-id="c244c-138">An example of an endpoint behavior is the <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> property, which allows you to specify a different listening address than the SOAP or Web Services Description Language (WSDL) address.</span></span> <span data-ttu-id="c244c-139">Weitere Informationen finden Sie unter ["ClientViaBehavior"](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).</span><span class="sxs-lookup"><span data-stu-id="c244c-139">For more information, see [ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).</span></span>  
  
## <a name="defining-endpoints"></a><span data-ttu-id="c244c-140">Definieren von Endpunkten</span><span class="sxs-lookup"><span data-stu-id="c244c-140">Defining Endpoints</span></span>  
 <span data-ttu-id="c244c-141">Sie können den Endpunkt für einen Dienst entweder verbindlich durch Verwenden von Code oder deklarativ durch Konfiguration angeben.</span><span class="sxs-lookup"><span data-stu-id="c244c-141">You can specify the endpoint for a service either imperatively using code or declaratively through configuration.</span></span> <span data-ttu-id="c244c-142">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines Dienstendpunkts in der Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) und [Vorgehensweise: Erstellen eines Dienstendpunkts im Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="c244c-142">For more information, see [How to: Create a Service Endpoint in Configuration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) and [How to: Create a Service Endpoint in Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c244c-143">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c244c-143">In This Section</span></span>  
 <span data-ttu-id="c244c-144">In diesem Abschnitt wird der Zweck von Bindungen, Endpunkten und Adressen erläutert. Darüber hinaus wird gezeigt, wie Sie eine Bindung und einen Endpunkt konfigurieren und wie Sie das `ClientVia`-Verhalten und die `ListenUri`-Eigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="c244c-144">This section explains the purpose of bindings, endpoints, and addresses; shows how to configure a binding and an endpoint; and demonstrates how to use the `ClientVia` behavior and `ListenUri` property.</span></span>  
  
 [<span data-ttu-id="c244c-145">Adressen</span><span class="sxs-lookup"><span data-stu-id="c244c-145">Addresses</span></span>](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
 <span data-ttu-id="c244c-146">Beschreibt, wie Endpunkte in WCF behoben werden.</span><span class="sxs-lookup"><span data-stu-id="c244c-146">Describes how endpoints are addressed in WCF.</span></span>  
  
 [<span data-ttu-id="c244c-147">Bindungen</span><span class="sxs-lookup"><span data-stu-id="c244c-147">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 <span data-ttu-id="c244c-148">Beschreibt, wie mit Bindungen Transport, Codierung und Protokolldetails angegeben werden, die für die Kommunikation zwischen Clients und Diensten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c244c-148">Describes how bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.</span></span>  
  
 [<span data-ttu-id="c244c-149">Verträge</span><span class="sxs-lookup"><span data-stu-id="c244c-149">Contracts</span></span>](../../../../docs/framework/wcf/feature-details/contracts.md)  
 <span data-ttu-id="c244c-150">Beschreibt, wie Verträge die Methoden eines Diensts definieren.</span><span class="sxs-lookup"><span data-stu-id="c244c-150">Describes how contracts define the methods of a service.</span></span>  
  
 [<span data-ttu-id="c244c-151">Vorgehensweise: Erstellen eines Dienstendpunkts in der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c244c-151">How to: Create a Service Endpoint in Configuration</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="c244c-152">Beschreibt, wie Sie einen Dienstendpunkt in einer Konfiguration erstellen.</span><span class="sxs-lookup"><span data-stu-id="c244c-152">Describes how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="c244c-153">Vorgehensweise: Erstellen eines Dienstendpunkts im Code</span><span class="sxs-lookup"><span data-stu-id="c244c-153">How to: Create a Service Endpoint in Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="c244c-154">Beschreibt, wie Sie einen Dienstendpunkt im Code erstellen.</span><span class="sxs-lookup"><span data-stu-id="c244c-154">Describes how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="c244c-155">Vorgehensweise: Verwenden von Svcutil.exe zum Überprüfen von kompiliertem Dienstcode</span><span class="sxs-lookup"><span data-stu-id="c244c-155">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)  
 <span data-ttu-id="c244c-156">Beschreibt, wie Sie Fehler in dienstimplementierungen und Konfigurationen zu erkennen, ohne zu hosten, den Dienst mithilfe der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c244c-156">Describes how to detect errors in service implementations and configurations without hosting the service using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c244c-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c244c-157">See also</span></span>

- [<span data-ttu-id="c244c-158">Konfigurieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="c244c-158">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)
- [<span data-ttu-id="c244c-159">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="c244c-159">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
