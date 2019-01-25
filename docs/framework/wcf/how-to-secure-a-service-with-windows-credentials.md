---
title: 'Vorgehensweise: Sichern eines Diensts mit Windows-Anmeldeinformationen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, security
ms.assetid: d171b5ca-96ef-47ff-800c-c138023cf76e
ms.openlocfilehash: 83b55ca42a3cebb6ceb2aec128202f14dc35da0a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657557"
---
# <a name="how-to-secure-a-service-with-windows-credentials"></a><span data-ttu-id="b9818-102">Vorgehensweise: Sichern eines Diensts mit Windows-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="b9818-102">How to: Secure a Service with Windows Credentials</span></span>
<span data-ttu-id="b9818-103">In diesem Thema veranschaulicht, wie transportsicherheit für einen Windows Communication Foundation (WCF)-Dienst zu ermöglichen, sich in einer Windows-Domäne befindet und von Clients in der gleichen Domäne aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b9818-103">This topic shows how to enable transport security on a Windows Communication Foundation (WCF) service that resides in a Windows domain and is called by clients in the same domain.</span></span> <span data-ttu-id="b9818-104">Weitere Informationen zu diesem Szenario finden Sie unter [Transportsicherheit mit Windows-Authentifizierung](../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="b9818-104">For more information about this scenario, see [Transport Security with Windows Authentication](../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md).</span></span> <span data-ttu-id="b9818-105">Eine beispielanwendung finden Sie unter den [WSHttpBinding](../../../docs/framework/wcf/samples/wshttpbinding.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="b9818-105">For a sample application, see the [WSHttpBinding](../../../docs/framework/wcf/samples/wshttpbinding.md) sample.</span></span>  
  
 <span data-ttu-id="b9818-106">In diesem Thema wird vorausgesetzt, dass Sie über eine vorhandene Vertragsschnittstelle verfügen und die Implementierung bereits definiert wurde, da hier auf diese beiden Punkte aufgebaut wird.</span><span class="sxs-lookup"><span data-stu-id="b9818-106">This topic assumes you have an existing contract interface and implementation already defined, and adds on to that.</span></span> <span data-ttu-id="b9818-107">Sie können auch einen vorhandenen Dienst und Client ändern.</span><span class="sxs-lookup"><span data-stu-id="b9818-107">You can also modify an existing service and client.</span></span>  
  
 <span data-ttu-id="b9818-108">Sie können einen Dienst mit Windows-Anmeldeinformationen vollständig im Code sichern.</span><span class="sxs-lookup"><span data-stu-id="b9818-108">You can secure a service with Windows credentials completely in code.</span></span> <span data-ttu-id="b9818-109">Alternativ können Sie bei Verwendung einer Konfigurationsdatei einige Teile des Codes weglassen.</span><span class="sxs-lookup"><span data-stu-id="b9818-109">Alternatively, you can omit some of the code by using a configuration file.</span></span> <span data-ttu-id="b9818-110">In diesem Thema werden beide Methoden gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9818-110">This topic shows both ways.</span></span> <span data-ttu-id="b9818-111">Verwenden Sie jedoch stets nur eine der Methoden.</span><span class="sxs-lookup"><span data-stu-id="b9818-111">Be sure you only use one of the ways, not both.</span></span>  
  
 <span data-ttu-id="b9818-112">In den ersten drei Prozeduren wird gezeigt, wie der Dienst unter Verwendung von Code gesichert wird.</span><span class="sxs-lookup"><span data-stu-id="b9818-112">The first three procedures show how to secure the service using code.</span></span> <span data-ttu-id="b9818-113">Die vierte und fünfte Prozedur zeigen, wie dies mit einer Konfigurationsdatei erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="b9818-113">The fourth and fifth procedure shows how to do it with a configuration file.</span></span>  
  
## <a name="using-code"></a><span data-ttu-id="b9818-114">Mithilfe von Code</span><span class="sxs-lookup"><span data-stu-id="b9818-114">Using Code</span></span>  
 <span data-ttu-id="b9818-115">Den vollständigen Code für Dienst und Client finden Sie im Beispielabschnitt am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="b9818-115">The complete code for the service and the client is in the Example section at the end of this topic.</span></span>  
  
 <span data-ttu-id="b9818-116">Die erste Prozedur führt Sie durch die Schritte zum Erstellen und Konfigurieren einer <xref:System.ServiceModel.WSHttpBinding>-Klasse im Code.</span><span class="sxs-lookup"><span data-stu-id="b9818-116">The first procedure walks through creating and configuring a <xref:System.ServiceModel.WSHttpBinding> class in code.</span></span> <span data-ttu-id="b9818-117">Für die Bindung wird der HTTP-Transport verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9818-117">The binding uses the HTTP transport.</span></span> <span data-ttu-id="b9818-118">Die gleiche Bindung wird auf dem Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9818-118">The same binding is used on the client.</span></span>  
  
#### <a name="to-create-a-wshttpbinding-that-uses-windows-credentials-and-message-security"></a><span data-ttu-id="b9818-119">So erstellen Sie eine WSHttpBinding, die Windows-Anmeldeinformationen und Nachrichtensicherheit verwendet</span><span class="sxs-lookup"><span data-stu-id="b9818-119">To create a WSHttpBinding that uses Windows credentials and message security</span></span>  
  
1.  <span data-ttu-id="b9818-120">Der Code dieser Prozedur wird im Dienstcode des Beispielabschnitts am Anfang der `Run`-Methode der `Test`-Klasse eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b9818-120">This procedure's code is inserted at the beginning of the `Run` method of the `Test` class in the service code in the Example section.</span></span>  
  
2.  <span data-ttu-id="b9818-121">Erstellen Sie eine Instanz der <xref:System.ServiceModel.WSHttpBinding>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="b9818-121">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class.</span></span>  
  
3.  <span data-ttu-id="b9818-122">Legen Sie die <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>-Eigenschaft der <xref:System.ServiceModel.WSHttpSecurity>-Klasse auf <xref:System.ServiceModel.SecurityMode.Message> fest.</span><span class="sxs-lookup"><span data-stu-id="b9818-122">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property of the <xref:System.ServiceModel.WSHttpSecurity> class to <xref:System.ServiceModel.SecurityMode.Message>.</span></span>  
  
4.  <span data-ttu-id="b9818-123">Legen Sie die <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A>-Eigenschaft der <xref:System.ServiceModel.MessageSecurityOverHttp>-Klasse auf <xref:System.ServiceModel.MessageCredentialType.Windows> fest.</span><span class="sxs-lookup"><span data-stu-id="b9818-123">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property of the <xref:System.ServiceModel.MessageSecurityOverHttp> class to <xref:System.ServiceModel.MessageCredentialType.Windows>.</span></span>  
  
5.  <span data-ttu-id="b9818-124">Für diese Prozedur wird der folgende Code verwendet:</span><span class="sxs-lookup"><span data-stu-id="b9818-124">The code for this procedure is as follows:</span></span>  
  
     [!code-csharp[c_SecureWindowsService#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#1)]
     [!code-vb[c_SecureWindowsService#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#1)]  
  
### <a name="using-the-binding-in-a-service"></a><span data-ttu-id="b9818-125">Verwenden der Bindung in einem Dienst</span><span class="sxs-lookup"><span data-stu-id="b9818-125">Using the Binding in a Service</span></span>  
 <span data-ttu-id="b9818-126">Dies ist die zweite Prozedur; in dieser Prozedur wird die Verwendung der Bindung in einem selbst gehosteten Dient veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b9818-126">This is the second procedure, which shows how to use the binding in a self-hosted service.</span></span> <span data-ttu-id="b9818-127">Weitere Informationen zum Hosten von Diensten finden Sie unter [Hostingdienste](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="b9818-127">For more information about hosting services see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
##### <a name="to-use-a-binding-in-a-service"></a><span data-ttu-id="b9818-128">So verwenden Sie eine Bindung in einem Dienst</span><span class="sxs-lookup"><span data-stu-id="b9818-128">To use a binding in a service</span></span>  
  
1.  <span data-ttu-id="b9818-129">Fügen Sie den Code dieser Prozedur nach dem Code der vorherigen Prozedur ein.</span><span class="sxs-lookup"><span data-stu-id="b9818-129">Insert this procedure's code after the code from the preceding procedure.</span></span>  
  
2.  <span data-ttu-id="b9818-130">Erstellen Sie eine <xref:System.Type>-Variable mit der Bezeichnung `contractType`, und weisen Sie ihr den Typ der Schnittstelle (`ICalculator`) zu.</span><span class="sxs-lookup"><span data-stu-id="b9818-130">Create a <xref:System.Type> variable named `contractType` and assign it the type of the interface (`ICalculator`).</span></span> <span data-ttu-id="b9818-131">Verwenden Sie bei der Verwendung von Visual Basic die `GetType` Operator ist; bei Verwendung von c#, verwenden die `typeof` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="b9818-131">When using Visual Basic, use the `GetType` operator; when using C#, use the `typeof` keyword.</span></span>  
  
3.  <span data-ttu-id="b9818-132">Erstellen Sie eine zweite `Type`-Variable mit der Bezeichnung `serviceType`, und weisen Sie ihr den Typ des implementierten Vertrags (`Calculator`) zu.</span><span class="sxs-lookup"><span data-stu-id="b9818-132">Create a second `Type` variable named `serviceType` and assign it the type of the implemented contract (`Calculator`).</span></span>  
  
4.  <span data-ttu-id="b9818-133">Erstellen Sie eine Instanz der <xref:System.Uri>-Klasse mit der Bezeichnung `baseAddress` mit der Basisadresse des Dienstes.</span><span class="sxs-lookup"><span data-stu-id="b9818-133">Create an instance of the <xref:System.Uri> class named `baseAddress` with the base address of the service.</span></span> <span data-ttu-id="b9818-134">Die Basisadresse muss ein Schema haben, das mit dem Transport übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="b9818-134">The base address must have a scheme that matches the transport.</span></span> <span data-ttu-id="b9818-135">In diesem Fall das Transportschema HTTP, und die Adresse enthält den speziellen Uniform Resource Identifier (URI) "Localhost" und einen Port-Nummer (8036) sowie eine basisendpunktadresse ("ServiceModelSamples /): `http://localhost:8036/serviceModelSamples/`.</span><span class="sxs-lookup"><span data-stu-id="b9818-135">In this case, the transport scheme is HTTP, and the address includes the special Uniform Resource Identifier (URI) "localhost" and a port number (8036) as well as a base endpoint address ("serviceModelSamples/): `http://localhost:8036/serviceModelSamples/`.</span></span>  
  
5.  <span data-ttu-id="b9818-136">Erstellen Sie eine Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse mit der `serviceType`-Variablen und der `baseAddress`-Variablen.</span><span class="sxs-lookup"><span data-stu-id="b9818-136">Create an instance of the <xref:System.ServiceModel.ServiceHost> class with the `serviceType` and `baseAddress` variables.</span></span>  
  
6.  <span data-ttu-id="b9818-137">Fügen Sie dem Dienst einen Endpunkt mit `contractType`, Bindung und einem Endpunktnamen (secureCalculator) hinzu.</span><span class="sxs-lookup"><span data-stu-id="b9818-137">Add an endpoint to the service using the `contractType`, binding, and an endpoint name (secureCalculator).</span></span> <span data-ttu-id="b9818-138">Ein Client muss beim Initiieren eines Aufrufs zum Dienst die Basisadresse und den Endpunktnamen verketten.</span><span class="sxs-lookup"><span data-stu-id="b9818-138">A client must concatenate the base address and the endpoint name when initiating a call to the service.</span></span>  
  
7.  <span data-ttu-id="b9818-139">Starten Sie den Dienst, indem Sie die <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b9818-139">Call the <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> method to start the service.</span></span> <span data-ttu-id="b9818-140">Der Code für diese Prozedur wird hier gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b9818-140">The code for this procedure is shown here:</span></span>  
  
     [!code-csharp[c_SecureWindowsService#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#2)]
     [!code-vb[c_SecureWindowsService#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#2)]  
  
### <a name="using-the-binding-in-a-client"></a><span data-ttu-id="b9818-141">Verwenden der Bindung in einem Client</span><span class="sxs-lookup"><span data-stu-id="b9818-141">Using the Binding in a Client</span></span>  
 <span data-ttu-id="b9818-142">Diese Prozedur zeigt die Generierung eines Proxys, der mit dem Dienst kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="b9818-142">This procedure shows how to generate a proxy that communicates with the service.</span></span> <span data-ttu-id="b9818-143">Der Proxy wird generiert, mit der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) die Metadaten des Diensts verwendet, um den Proxy zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b9818-143">The proxy is generated with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) which uses the service metadata to create the proxy.</span></span>  
  
 <span data-ttu-id="b9818-144">Durch diese Prozedur wird auch eine Instanz der <xref:System.ServiceModel.WSHttpBinding>-Klasse erstellt, um mit dem Dienst zu kommunizieren. Anschließend wird der Dienst aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b9818-144">This procedure also creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class to communicate with the service, and then calls the service.</span></span>  
  
 <span data-ttu-id="b9818-145">In diesem Beispiel wird zum Erstellen des Clients nur Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9818-145">This example uses only code to create the client.</span></span> <span data-ttu-id="b9818-146">Alternativ können Sie eine Konfigurationsdatei verwenden. Dies wird im Abschnitt nach dieser Prozedur veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b9818-146">As an alternative, you can use a configuration file, which is shown in the section following this procedure.</span></span>  
  
##### <a name="to-use-a-binding-in-a-client-with-code"></a><span data-ttu-id="b9818-147">So verwenden Sie eine Bindung in einem Client mit Code</span><span class="sxs-lookup"><span data-stu-id="b9818-147">To use a binding in a client with code</span></span>  
  
1.  <span data-ttu-id="b9818-148">Verwenden Sie das SvcUtil.exe-Tool, um den Proxycode aus den Metadaten des Diensts zu generieren.</span><span class="sxs-lookup"><span data-stu-id="b9818-148">Use the SvcUtil.exe tool to generate the proxy code from the service's metadata.</span></span> <span data-ttu-id="b9818-149">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie einen Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="b9818-149">For more information, see [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span> <span data-ttu-id="b9818-150">Der generierte Proxycode erbt von der <xref:System.ServiceModel.ClientBase%601> -Klasse, die wird sichergestellt, dass jeder Client die erforderlichen Konstruktoren, Methoden und Eigenschaften für die Kommunikation mit einem WCF-Dienst.</span><span class="sxs-lookup"><span data-stu-id="b9818-150">The generated proxy code inherits from the <xref:System.ServiceModel.ClientBase%601> class, which ensures that every client has the necessary constructors, methods, and properties to communicate with a WCF service.</span></span> <span data-ttu-id="b9818-151">In diesem Beispiel enthält der generierte Code die `CalculatorClient`-Klasse, die die `ICalculator`-Schnittstelle für die Kompatibilität mit dem Dienstcode implementiert.</span><span class="sxs-lookup"><span data-stu-id="b9818-151">In this example, the generated code includes the `CalculatorClient` class, which implements the `ICalculator` interface, enabling compatibility with the service code.</span></span>  
  
2.  <span data-ttu-id="b9818-152">Der Code dieser Prozedur wird am Anfang der `Main`-Methode des Clientprogramms eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b9818-152">This procedure's code is inserted at the beginning of the `Main` method of the client program.</span></span>  
  
3.  <span data-ttu-id="b9818-153">Erstellen Sie eine Instanz der <xref:System.ServiceModel.WSHttpBinding>-Klasse und legen Sie ihren Sicherheitsmodus auf `Message` und ihren Clientanmeldeinformationstyp auf `Windows` fest.</span><span class="sxs-lookup"><span data-stu-id="b9818-153">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set its security mode to `Message` and its client credential type to `Windows`.</span></span> <span data-ttu-id="b9818-154">Im Beispiel wird die Variable `clientBinding` genannt.</span><span class="sxs-lookup"><span data-stu-id="b9818-154">The example names the variable `clientBinding`.</span></span>  
  
4.  <span data-ttu-id="b9818-155">Erstellen Sie eine Instanz der <xref:System.ServiceModel.EndpointAddress>-Klasse mit der Bezeichnung `serviceAddress`.</span><span class="sxs-lookup"><span data-stu-id="b9818-155">Create an instance of the <xref:System.ServiceModel.EndpointAddress> class named `serviceAddress`.</span></span> <span data-ttu-id="b9818-156">Initialisieren Sie die Instanz mit der mit dem Endpunktnamen verketteten Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="b9818-156">Initialize the instance with the base address concatenated with the endpoint name.</span></span>  
  
5.  <span data-ttu-id="b9818-157">Erstellen Sie eine Instanz der generierten Clientklasse mit der `serviceAddress`-Variablen und der `clientBinding`-Variablen.</span><span class="sxs-lookup"><span data-stu-id="b9818-157">Create an instance of the generated client class with the `serviceAddress` and the `clientBinding` variables.</span></span>  
  
6.  <span data-ttu-id="b9818-158">Rufen Sie die <xref:System.ServiceModel.ClientBase%601.Open%2A>-Methode auf, wie im folgenden Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="b9818-158">Call the <xref:System.ServiceModel.ClientBase%601.Open%2A> method, as shown in the following code.</span></span>  
  
7.  <span data-ttu-id="b9818-159">Rufen Sie den Dienst auf, und zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="b9818-159">Call the service and display the results.</span></span>  
  
     [!code-csharp[c_secureWindowsClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#1)]
     [!code-vb[c_secureWindowsClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#1)]  
  
## <a name="using-the-configuration-file"></a><span data-ttu-id="b9818-160">Verwenden der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="b9818-160">Using the Configuration File</span></span>  
 <span data-ttu-id="b9818-161">Anstelle der Erstellung der Bindung mithilfe von prozeduralem Code können Sie auch den folgenden Code für den Bindungsabschnitt der Konfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9818-161">Instead of creating the binding with procedural code, you can use the following code shown for the bindings section of the configuration file.</span></span>  
  
 <span data-ttu-id="b9818-162">Wenn Sie nicht bereits über einen definierten Dienst verfügen, finden Sie unter [entwerfen und Implementieren von Diensten](../../../docs/framework/wcf/designing-and-implementing-services.md), und [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="b9818-162">If you do not already have a service defined, see [Designing and Implementing Services](../../../docs/framework/wcf/designing-and-implementing-services.md), and [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
 <span data-ttu-id="b9818-163">**Beachten Sie** dieser Konfigurationscode wird in den Dienst und Client-Konfigurationsdateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9818-163">**Note** This configuration code is used in both the service and client configuration files.</span></span>  
  
#### <a name="to-enable-transfer-security-on-a-service-in-a-windows-domain-using-configuration"></a><span data-ttu-id="b9818-164">So aktivieren Sie mit der Konfiguration Übertragungssicherheit für einen Dienst in einer Windows-Domäne</span><span class="sxs-lookup"><span data-stu-id="b9818-164">To enable transfer security on a service in a Windows domain using configuration</span></span>  
  
1.  <span data-ttu-id="b9818-165">Hinzufügen einer [ \<WsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) Element, das [ \<Bindungen >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) -Elementabschnitt der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b9818-165">Add a [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element to the [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element section of the configuration file.</span></span>  
  
2.  <span data-ttu-id="b9818-166">Fügen Sie dem <`binding`>-Element ein <`WSHttpBinding`>-Element hinzu, und legen Sie das `configurationName`-Attribut auf einen für Ihre Anwendung geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="b9818-166">Add a <`binding`> element to the <`WSHttpBinding`> element and set the `configurationName` attribute to a value appropriate to your application.</span></span>  
  
3.  <span data-ttu-id="b9818-167">Fügen Sie ein <`security`>-Element hinzu, und legen Sie das `mode`-Attribut auf "Message" fest.</span><span class="sxs-lookup"><span data-stu-id="b9818-167">Add a <`security`> element and set the `mode` attribute to Message.</span></span>  
  
4.  <span data-ttu-id="b9818-168">Fügen Sie ein <`message`>-Element hinzu, und legen Sie das `clientCredentialType`-Attribut auf "Windows" fest.</span><span class="sxs-lookup"><span data-stu-id="b9818-168">Add a <`message`> element and set the `clientCredentialType` attribute to Windows.</span></span>  
  
5.  <span data-ttu-id="b9818-169">Ersetzen Sie in der Konfigurationsdatei des Diensts den `<bindings>`-Abschnitt durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="b9818-169">In the service's configuration file, replace the `<bindings>` section with the following code.</span></span> <span data-ttu-id="b9818-170">Wenn Sie nicht bereits über eine Dienstkonfigurationsdatei verfügen, finden Sie unter [Verwendung von Bindungen zum Konfigurieren von Diensten und Clients](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="b9818-170">If you do not already have a service configuration file, see [Using Bindings to Configure Services and Clients](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).</span></span>  
  
    ```xml  
    <bindings>  
      <wsHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    ```  
  
### <a name="using-the-binding-in-a-client"></a><span data-ttu-id="b9818-171">Verwenden der Bindung in einem Client</span><span class="sxs-lookup"><span data-stu-id="b9818-171">Using the Binding in a Client</span></span>  
 <span data-ttu-id="b9818-172">In dieser Prozedur wird die Generierung zweier Dateien veranschaulicht: einem Proxy, der mit dem Dienst kommuniziert, und einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b9818-172">This procedure shows how to generate two files: a proxy that communicates with the service and a configuration file.</span></span> <span data-ttu-id="b9818-173">Darüber hinaus werden auch Änderungen am Clientprogramm beschrieben &#8211; der dritten Datei, die auf dem Client verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b9818-173">It also describes changes to the client program, which is the third file used on the client.</span></span>  
  
##### <a name="to-use-a-binding-in-a-client-with-configuration"></a><span data-ttu-id="b9818-174">So verwenden Sie eine Bindung für einen Client mit Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b9818-174">To use a binding in a client with configuration</span></span>  
  
1.  <span data-ttu-id="b9818-175">Verwenden Sie das SvcUtil.exe-Tool, um den Proxycode und die Konfigurationsdatei aus den Metadaten des Diensts zu generieren.</span><span class="sxs-lookup"><span data-stu-id="b9818-175">Use the SvcUtil.exe tool to generate the proxy code and configuration file from the service's metadata.</span></span> <span data-ttu-id="b9818-176">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie einen Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="b9818-176">For more information, see [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
2.  <span data-ttu-id="b9818-177">Ersetzen Sie die [ \<Bindungen >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Abschnitt der generierten Konfigurationsdatei durch den Konfigurationscode aus dem vorherigen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b9818-177">Replace the [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) section of the generated configuration file with the configuration code from the preceding section.</span></span>  
  
3.  <span data-ttu-id="b9818-178">Prozeduraler Code wird am Anfang der `Main`-Methode des Clientprogramms eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b9818-178">Procedural code is inserted at the beginning of the `Main` method of the client program.</span></span>  
  
4.  <span data-ttu-id="b9818-179">Erstellen Sie eine Instanz der generierten Clientklasse, und geben Sie den Namen der Bindung in der Konfigurationsdatei als Eingabeparameter weiter.</span><span class="sxs-lookup"><span data-stu-id="b9818-179">Create an instance of the generated client class passing the name of the binding in the configuration file as an input parameter.</span></span>  
  
5.  <span data-ttu-id="b9818-180">Rufen Sie die <xref:System.ServiceModel.ClientBase%601.Open%2A>-Methode auf, wie im folgenden Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="b9818-180">Call the <xref:System.ServiceModel.ClientBase%601.Open%2A> method, as shown in the following code.</span></span>  
  
6.  <span data-ttu-id="b9818-181">Rufen Sie den Dienst auf, und zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="b9818-181">Call the service and display the results.</span></span>  
  
     [!code-csharp[c_secureWindowsClient#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#2)]  
  
## <a name="example"></a><span data-ttu-id="b9818-182">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9818-182">Example</span></span>  
 [!code-csharp[c_SecureWindowsService#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#0)]  
  
 [!code-csharp[c_SecureWindowsClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#0)] 
 [!code-vb[c_SecureWindowsClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#0)]      
  
## <a name="see-also"></a><span data-ttu-id="b9818-183">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9818-183">See also</span></span>
- <xref:System.ServiceModel.WSHttpBinding>
- [<span data-ttu-id="b9818-184">ServiceModel Metadata Utility-Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="b9818-184">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="b9818-185">Vorgehensweise: Erstellen Sie einen Client</span><span class="sxs-lookup"><span data-stu-id="b9818-185">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [<span data-ttu-id="b9818-186">Sichern von Diensten</span><span class="sxs-lookup"><span data-stu-id="b9818-186">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)
- [<span data-ttu-id="b9818-187">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b9818-187">Security Overview</span></span>](../../../docs/framework/wcf/feature-details/security-overview.md)
