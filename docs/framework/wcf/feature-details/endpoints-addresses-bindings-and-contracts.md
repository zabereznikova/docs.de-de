---
title: 'Endpunkte: Adressen, Bindungen und Verträge'
description: Erfahren Sie, wie die gesamte Kommunikation mit einem WCF-Dienst über die Dienst Endpunkte erfolgt, die Clients Zugriff auf die vom Dienst angebotenen Funktionen bieten.
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: ce0874bfed716716b6fd1801b35a4266095cd752
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247311"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a><span data-ttu-id="1a7ac-103">Endpunkte: Adressen, Bindungen und Verträge</span><span class="sxs-lookup"><span data-stu-id="1a7ac-103">Endpoints: Addresses, Bindings, and Contracts</span></span>

<span data-ttu-id="1a7ac-104">Die gesamte Kommunikation mit einem Windows Communication Foundation (WCF)-Dienst erfolgt über die *Endpunkte* des Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-104">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="1a7ac-105">Endpunkte ermöglichen Clients den Zugriff auf die Funktionalität, die von einem WCF-Dienst angeboten wird.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-105">Endpoints provide clients access to the functionality offered by a WCF service.</span></span>

<span data-ttu-id="1a7ac-106">Jeder Endpunkt verfügt über vier Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="1a7ac-106">Each endpoint consists of four properties:</span></span>

- <span data-ttu-id="1a7ac-107">Eine Adresse, die angibt, wo der Endpunkt zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-107">An address that indicates where the endpoint can be found.</span></span>

- <span data-ttu-id="1a7ac-108">Eine Bindung, die angibt, wie ein Client mit dem Endpunkt kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-108">A binding that specifies how a client can communicate with the endpoint.</span></span>

- <span data-ttu-id="1a7ac-109">Ein Vertrag, der die verfügbaren Vorgänge identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-109">A contract that identifies the operations available.</span></span>

- <span data-ttu-id="1a7ac-110">Eine Gruppe von Verhaltensweisen, die lokale Implementierungsdetails des Endpunkts angeben.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-110">A set of behaviors that specify local implementation details of the endpoint.</span></span>

<span data-ttu-id="1a7ac-111">In diesem Thema wird diese Endpunkt Struktur behandelt und erläutert, wie Sie im WCF-Objektmodell dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-111">This topic discusses this endpoint structure and explains how it is represented in the WCF object model.</span></span>

## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="1a7ac-112">Die Struktur eines Endpunkts</span><span class="sxs-lookup"><span data-stu-id="1a7ac-112">The Structure of an Endpoint</span></span>

<span data-ttu-id="1a7ac-113">Jeder Endpunkt besteht aus Folgendem:</span><span class="sxs-lookup"><span data-stu-id="1a7ac-113">Each endpoint consists of the following:</span></span>

- <span data-ttu-id="1a7ac-114">Adresse: Die Adresse gewährleistet eine eindeutige Identifizierung des Endpunkts und teilt potenziellen Consumern des Diensts den Standort des Diensts mit.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-114">Address: The address uniquely identifies the endpoint and tells potential consumers of the service where it is located.</span></span> <span data-ttu-id="1a7ac-115">Sie wird im WCF-Objektmodell durch die- <xref:System.ServiceModel.EndpointAddress> Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-115">It is represented in the WCF object model by the <xref:System.ServiceModel.EndpointAddress> class.</span></span> <span data-ttu-id="1a7ac-116">Eine <xref:System.ServiceModel.EndpointAddress>-Klasse enthält:</span><span class="sxs-lookup"><span data-stu-id="1a7ac-116">An <xref:System.ServiceModel.EndpointAddress> class contains:</span></span>

  - <span data-ttu-id="1a7ac-117">Eine <xref:System.ServiceModel.EndpointAddress.Uri%2A>-Eigenschaft, die die Adresse des Diensts darstellt.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-117">A <xref:System.ServiceModel.EndpointAddress.Uri%2A> property, which represents the address of the service.</span></span>

  - <span data-ttu-id="1a7ac-118">Eine <xref:System.ServiceModel.EndpointAddress.Identity%2A>-Eigenschaft, die die Sicherheits-ID des Diensts und eine Auflistung optionaler Nachrichtenheader darstellt.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-118">An <xref:System.ServiceModel.EndpointAddress.Identity%2A> property, which represents the security identity of the service and a collection of optional message headers.</span></span> <span data-ttu-id="1a7ac-119">Die optionalen Nachrichtenheader werden verwendet, um zusätzliche und ausführlichere Adressinformationen bereitzustellen, um den Endpunkt zu identifizieren oder damit zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-119">The optional message headers are used to provide additional and more detailed addressing information to identify or interact with the endpoint.</span></span>

  <span data-ttu-id="1a7ac-120">Weitere Informationen finden Sie unter [Angeben einer Endpunkt Adresse](../specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="1a7ac-120">For more information, see [Specifying an Endpoint Address](../specifying-an-endpoint-address.md).</span></span>

- <span data-ttu-id="1a7ac-121">Bindung: Die Bindung gibt an, wie eine Kommunikation mit dem Endpunkt stattfindet.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-121">Binding: The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="1a7ac-122">Dies schließt Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1a7ac-122">This includes:</span></span>

  - <span data-ttu-id="1a7ac-123">Das Transportprotokoll, das verwendet werden soll (z.&#160;B. TCP oder HTTP).</span><span class="sxs-lookup"><span data-stu-id="1a7ac-123">The transport protocol to use (for example, TCP or HTTP).</span></span>

  - <span data-ttu-id="1a7ac-124">Die Codierung, die für die Nachrichten verwendet werden soll (z.&#160;B. Text oder binär).</span><span class="sxs-lookup"><span data-stu-id="1a7ac-124">The encoding to use for the messages (for example, text or binary).</span></span>

  - <span data-ttu-id="1a7ac-125">Die erforderlichen Sicherheitsanforderungen (z.&#160;B. SSL- oder SOAP-Nachrichtensicherheit).</span><span class="sxs-lookup"><span data-stu-id="1a7ac-125">The necessary security requirements (for example, SSL or SOAP message security).</span></span>

  <span data-ttu-id="1a7ac-126">Weitere Informationen finden Sie unter [Übersicht über WCF-Bindungen](../bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1a7ac-126">For more information, see [WCF Bindings Overview](../bindings-overview.md).</span></span> <span data-ttu-id="1a7ac-127">Eine Bindung wird im WCF-Objektmodell durch die abstrakte Basisklasse dargestellt <xref:System.ServiceModel.Channels.Binding> .</span><span class="sxs-lookup"><span data-stu-id="1a7ac-127">A binding is represented in the WCF object model by the abstract base class <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="1a7ac-128">Für die meisten Szenarien können Benutzer eine der vom System bereitgestellten Bindungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-128">For most scenarios, users can use one of the system-provided bindings.</span></span> <span data-ttu-id="1a7ac-129">Weitere Informationen finden Sie unter vom [System bereitgestellte Bindungen](../system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="1a7ac-129">For more information, see [System-Provided Bindings](../system-provided-bindings.md).</span></span>

- <span data-ttu-id="1a7ac-130">Verträge: Der Dienstvertrag zeigt, welche Funktionen der Endpunkt dem Client zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-130">Contracts: The contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="1a7ac-131">Ein Vertrag gibt Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="1a7ac-131">A contract specifies:</span></span>

  - <span data-ttu-id="1a7ac-132">Welche Vorgänge von einem Client aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-132">What operations can be called by a client.</span></span>

  - <span data-ttu-id="1a7ac-133">Die Form der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-133">The form of the message.</span></span>

  - <span data-ttu-id="1a7ac-134">Der Typ der Eingabeparameter oder Daten, die zum Aufrufen des Vorgangs erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-134">The type of input parameters or data required to call the operation.</span></span>

  - <span data-ttu-id="1a7ac-135">Den Typ der Verarbeitung oder der Antwortnachricht, den der Client erwarten kann.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-135">What type of processing or response message the client can expect.</span></span>

  <span data-ttu-id="1a7ac-136">Weitere Informationen zum Definieren eines Vertrags finden Sie unter [Entwerfen von Dienstverträgen](../designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="1a7ac-136">For more information about defining a contract, see [Designing Service Contracts](../designing-service-contracts.md).</span></span>

- <span data-ttu-id="1a7ac-137">Verhaltensweisen: Sie können das lokale Verhalten des Dienstendpunkts mithilfe von Endpunktverhaltensweisen anpassen.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-137">Behaviors: You can use endpoint behaviors to customize the local behavior of the service endpoint.</span></span> <span data-ttu-id="1a7ac-138">Endpunkt Verhaltensweisen erreichen dies durch die Teilnahme an der Einrichtung einer WCF-Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-138">Endpoint behaviors achieve this by participating in the process of building a WCF runtime.</span></span> <span data-ttu-id="1a7ac-139">Ein Beispiel für ein Endpunktverhalten ist die <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A>-Eigenschaft, mit der Sie eine andere Listeningadresse als die SOAP- oder die WSDL-Adresse (WSDL = Web Services Description Language) angeben können.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-139">An example of an endpoint behavior is the <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> property, which allows you to specify a different listening address than the SOAP or Web Services Description Language (WSDL) address.</span></span> <span data-ttu-id="1a7ac-140">Weitere Informationen finden Sie unter [ClientViaBehavior](../diagnostics/wmi/clientviabehavior.md).</span><span class="sxs-lookup"><span data-stu-id="1a7ac-140">For more information, see [ClientViaBehavior](../diagnostics/wmi/clientviabehavior.md).</span></span>

## <a name="defining-endpoints"></a><span data-ttu-id="1a7ac-141">Definieren von Endpunkten</span><span class="sxs-lookup"><span data-stu-id="1a7ac-141">Defining Endpoints</span></span>

<span data-ttu-id="1a7ac-142">Sie können den Endpunkt für einen Dienst entweder verbindlich durch Verwenden von Code oder deklarativ durch Konfiguration angeben.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-142">You can specify the endpoint for a service either imperatively using code or declaratively through configuration.</span></span> <span data-ttu-id="1a7ac-143">Weitere Informationen finden Sie unter Gewusst [wie: Erstellen eines Dienst Endpunkts in der Konfiguration](how-to-create-a-service-endpoint-in-configuration.md) und Gewusst [wie: Erstellen eines Dienst Endpunkts im Code](how-to-create-a-service-endpoint-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="1a7ac-143">For more information, see [How to: Create a Service Endpoint in Configuration](how-to-create-a-service-endpoint-in-configuration.md) and [How to: Create a Service Endpoint in Code](how-to-create-a-service-endpoint-in-code.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1a7ac-144">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1a7ac-144">In This Section</span></span>

<span data-ttu-id="1a7ac-145">In diesem Abschnitt wird der Zweck von Bindungen, Endpunkten und Adressen erläutert. Darüber hinaus wird gezeigt, wie Sie eine Bindung und einen Endpunkt konfigurieren und wie Sie das `ClientVia`-Verhalten und die `ListenUri`-Eigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-145">This section explains the purpose of bindings, endpoints, and addresses; shows how to configure a binding and an endpoint; and demonstrates how to use the `ClientVia` behavior and `ListenUri` property.</span></span>

<span data-ttu-id="1a7ac-146">[Setzt](endpoint-addresses.md)</span><span class="sxs-lookup"><span data-stu-id="1a7ac-146">[Addresses](endpoint-addresses.md)</span></span>\
<span data-ttu-id="1a7ac-147">Beschreibt, wie Endpunkte in WCF adressiert werden.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-147">Describes how endpoints are addressed in WCF.</span></span>

<span data-ttu-id="1a7ac-148">[Land](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="1a7ac-148">[Bindings](bindings.md)</span></span>\
<span data-ttu-id="1a7ac-149">Beschreibt, wie mit Bindungen Transport, Codierung und Protokolldetails angegeben werden, die für die Kommunikation zwischen Clients und Diensten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-149">Describes how bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.</span></span>

<span data-ttu-id="1a7ac-150">[Verträge](contracts.md)</span><span class="sxs-lookup"><span data-stu-id="1a7ac-150">[Contracts](contracts.md)</span></span>\
<span data-ttu-id="1a7ac-151">Beschreibt, wie Verträge die Methoden eines Diensts definieren.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-151">Describes how contracts define the methods of a service.</span></span>

<span data-ttu-id="1a7ac-152">[Vorgehensweise: Erstellen eines Dienst Endpunkts in der Konfiguration](how-to-create-a-service-endpoint-in-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="1a7ac-152">[How to: Create a Service Endpoint in Configuration](how-to-create-a-service-endpoint-in-configuration.md)</span></span>\
<span data-ttu-id="1a7ac-153">Beschreibt, wie Sie einen Dienstendpunkt in einer Konfiguration erstellen.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-153">Describes how to create a service endpoint in configuration.</span></span>

<span data-ttu-id="1a7ac-154">[Vorgehensweise: Erstellen eines Dienst Endpunkts im Code](how-to-create-a-service-endpoint-in-code.md)</span><span class="sxs-lookup"><span data-stu-id="1a7ac-154">[How to: Create a Service Endpoint in Code](how-to-create-a-service-endpoint-in-code.md)</span></span>\
<span data-ttu-id="1a7ac-155">Beschreibt, wie Sie einen Dienstendpunkt im Code erstellen.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-155">Describes how to create a service endpoint in code.</span></span>

<span data-ttu-id="1a7ac-156">[Gewusst wie: Verwenden von Svcutil.exe zum Überprüfen von kompiliertem Dienst Code](how-to-use-svcutil-exe-to-validate-compiled-service-code.md)</span><span class="sxs-lookup"><span data-stu-id="1a7ac-156">[How to: Use Svcutil.exe to Validate Compiled Service Code](how-to-use-svcutil-exe-to-validate-compiled-service-code.md)</span></span>\
<span data-ttu-id="1a7ac-157">Beschreibt, wie Fehler in Dienst Implementierungen und Konfigurationen erkannt werden, ohne dass der Dienst mit dem Service [Model Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="1a7ac-157">Describes how to detect errors in service implementations and configurations without hosting the service using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1a7ac-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a7ac-158">See also</span></span>

- [<span data-ttu-id="1a7ac-159">Konfigurieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="1a7ac-159">Configuring Services</span></span>](../configuring-services.md)
- [<span data-ttu-id="1a7ac-160">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="1a7ac-160">Extending Bindings</span></span>](../extending/extending-bindings.md)
