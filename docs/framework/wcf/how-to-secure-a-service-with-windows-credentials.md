---
title: 'Vorgehensweise: Sichern eines Diensts mit Windows-Anmeldeinformationen'
description: Erfahren Sie, wie Sie die Transportsicherheit für einen WCF-Dienst aktivieren, der sich in einer Windows-Domäne befindet und von Clients in derselben Domäne aufgerufen wird.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, security
ms.assetid: d171b5ca-96ef-47ff-800c-c138023cf76e
ms.openlocfilehash: 8ef164e1475bfd5f047a99426a2bed43a7aa7353
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244632"
---
# <a name="how-to-secure-a-service-with-windows-credentials"></a><span data-ttu-id="87473-103">Vorgehensweise: Sichern eines Diensts mit Windows-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="87473-103">How to: Secure a Service with Windows Credentials</span></span>

<span data-ttu-id="87473-104">In diesem Thema wird gezeigt, wie die Transportsicherheit für einen Windows Communication Foundation (WCF)-Dienst aktiviert wird, der sich in einer Windows-Domäne befindet und von Clients in derselben Domäne aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="87473-104">This topic shows how to enable transport security on a Windows Communication Foundation (WCF) service that resides in a Windows domain and is called by clients in the same domain.</span></span> <span data-ttu-id="87473-105">Weitere Informationen zu diesem Szenario finden Sie unter [Transport Sicherheit mit Windows-Authentifizierung](./feature-details/transport-security-with-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="87473-105">For more information about this scenario, see [Transport Security with Windows Authentication](./feature-details/transport-security-with-windows-authentication.md).</span></span> <span data-ttu-id="87473-106">Eine Beispielanwendung finden Sie im [WSHttpBinding](./samples/wshttpbinding.md) -Beispiel.</span><span class="sxs-lookup"><span data-stu-id="87473-106">For a sample application, see the [WSHttpBinding](./samples/wshttpbinding.md) sample.</span></span>

<span data-ttu-id="87473-107">In diesem Thema wird vorausgesetzt, dass Sie über eine vorhandene Vertragsschnittstelle verfügen und die Implementierung bereits definiert wurde, da hier auf diese beiden Punkte aufgebaut wird.</span><span class="sxs-lookup"><span data-stu-id="87473-107">This topic assumes you have an existing contract interface and implementation already defined, and adds on to that.</span></span> <span data-ttu-id="87473-108">Sie können auch einen vorhandenen Dienst und Client ändern.</span><span class="sxs-lookup"><span data-stu-id="87473-108">You can also modify an existing service and client.</span></span>

<span data-ttu-id="87473-109">Sie können einen Dienst mit Windows-Anmeldeinformationen vollständig im Code sichern.</span><span class="sxs-lookup"><span data-stu-id="87473-109">You can secure a service with Windows credentials completely in code.</span></span> <span data-ttu-id="87473-110">Alternativ können Sie bei Verwendung einer Konfigurationsdatei einige Teile des Codes weglassen.</span><span class="sxs-lookup"><span data-stu-id="87473-110">Alternatively, you can omit some of the code by using a configuration file.</span></span> <span data-ttu-id="87473-111">In diesem Thema werden beide Methoden gezeigt.</span><span class="sxs-lookup"><span data-stu-id="87473-111">This topic shows both ways.</span></span> <span data-ttu-id="87473-112">Verwenden Sie jedoch stets nur eine der Methoden.</span><span class="sxs-lookup"><span data-stu-id="87473-112">Be sure you only use one of the ways, not both.</span></span>

<span data-ttu-id="87473-113">In den ersten drei Prozeduren wird gezeigt, wie der Dienst unter Verwendung von Code gesichert wird.</span><span class="sxs-lookup"><span data-stu-id="87473-113">The first three procedures show how to secure the service using code.</span></span> <span data-ttu-id="87473-114">Die vierte und fünfte Prozedur zeigen, wie dies mit einer Konfigurationsdatei erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="87473-114">The fourth and fifth procedure shows how to do it with a configuration file.</span></span>

## <a name="using-code"></a><span data-ttu-id="87473-115">Mithilfe von Code</span><span class="sxs-lookup"><span data-stu-id="87473-115">Using Code</span></span>

<span data-ttu-id="87473-116">Den vollständigen Code für Dienst und Client finden Sie im Beispielabschnitt am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="87473-116">The complete code for the service and the client is in the Example section at the end of this topic.</span></span>

<span data-ttu-id="87473-117">Die erste Prozedur führt Sie durch die Schritte zum Erstellen und Konfigurieren einer <xref:System.ServiceModel.WSHttpBinding>-Klasse im Code.</span><span class="sxs-lookup"><span data-stu-id="87473-117">The first procedure walks through creating and configuring a <xref:System.ServiceModel.WSHttpBinding> class in code.</span></span> <span data-ttu-id="87473-118">Für die Bindung wird der HTTP-Transport verwendet.</span><span class="sxs-lookup"><span data-stu-id="87473-118">The binding uses the HTTP transport.</span></span> <span data-ttu-id="87473-119">Die gleiche Bindung wird auf dem Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="87473-119">The same binding is used on the client.</span></span>

#### <a name="to-create-a-wshttpbinding-that-uses-windows-credentials-and-message-security"></a><span data-ttu-id="87473-120">So erstellen Sie eine WSHttpBinding, die Windows-Anmeldeinformationen und Nachrichtensicherheit verwendet</span><span class="sxs-lookup"><span data-stu-id="87473-120">To create a WSHttpBinding that uses Windows credentials and message security</span></span>

1. <span data-ttu-id="87473-121">Der Code dieser Prozedur wird im Dienstcode des Beispielabschnitts am Anfang der `Run`-Methode der `Test`-Klasse eingefügt.</span><span class="sxs-lookup"><span data-stu-id="87473-121">This procedure's code is inserted at the beginning of the `Run` method of the `Test` class in the service code in the Example section.</span></span>

2. <span data-ttu-id="87473-122">Erstellen Sie eine Instanz der <xref:System.ServiceModel.WSHttpBinding>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="87473-122">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class.</span></span>

3. <span data-ttu-id="87473-123">Legen Sie die <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>-Eigenschaft der <xref:System.ServiceModel.WSHttpSecurity>-Klasse auf <xref:System.ServiceModel.SecurityMode.Message> fest.</span><span class="sxs-lookup"><span data-stu-id="87473-123">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property of the <xref:System.ServiceModel.WSHttpSecurity> class to <xref:System.ServiceModel.SecurityMode.Message>.</span></span>

4. <span data-ttu-id="87473-124">Legen Sie die <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A>-Eigenschaft der <xref:System.ServiceModel.MessageSecurityOverHttp>-Klasse auf <xref:System.ServiceModel.MessageCredentialType.Windows> fest.</span><span class="sxs-lookup"><span data-stu-id="87473-124">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property of the <xref:System.ServiceModel.MessageSecurityOverHttp> class to <xref:System.ServiceModel.MessageCredentialType.Windows>.</span></span>

5. <span data-ttu-id="87473-125">Für diese Prozedur wird der folgende Code verwendet:</span><span class="sxs-lookup"><span data-stu-id="87473-125">The code for this procedure is as follows:</span></span>

    [!code-csharp[c_SecureWindowsService#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#1)]
    [!code-vb[c_SecureWindowsService#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#1)]

### <a name="using-the-binding-in-a-service"></a><span data-ttu-id="87473-126">Verwenden der Bindung in einem Dienst</span><span class="sxs-lookup"><span data-stu-id="87473-126">Using the Binding in a Service</span></span>

<span data-ttu-id="87473-127">Dies ist die zweite Prozedur; in dieser Prozedur wird die Verwendung der Bindung in einem selbst gehosteten Dient veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="87473-127">This is the second procedure, which shows how to use the binding in a self-hosted service.</span></span> <span data-ttu-id="87473-128">Weitere Informationen zu Hostingdiensten finden Sie unter [Hosting-Dienste](hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="87473-128">For more information about hosting services see [Hosting Services](hosting-services.md).</span></span>

##### <a name="to-use-a-binding-in-a-service"></a><span data-ttu-id="87473-129">So verwenden Sie eine Bindung in einem Dienst</span><span class="sxs-lookup"><span data-stu-id="87473-129">To use a binding in a service</span></span>

1. <span data-ttu-id="87473-130">Fügen Sie den Code dieser Prozedur nach dem Code der vorherigen Prozedur ein.</span><span class="sxs-lookup"><span data-stu-id="87473-130">Insert this procedure's code after the code from the preceding procedure.</span></span>

2. <span data-ttu-id="87473-131">Erstellen Sie eine <xref:System.Type>-Variable mit der Bezeichnung `contractType`, und weisen Sie ihr den Typ der Schnittstelle (`ICalculator`) zu.</span><span class="sxs-lookup"><span data-stu-id="87473-131">Create a <xref:System.Type> variable named `contractType` and assign it the type of the interface (`ICalculator`).</span></span> <span data-ttu-id="87473-132">Wenn Sie Visual Basic verwenden, verwenden Sie den- `GetType` Operator; Wenn Sie c# verwenden, verwenden Sie das- `typeof` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="87473-132">When using Visual Basic, use the `GetType` operator; when using C#, use the `typeof` keyword.</span></span>

3. <span data-ttu-id="87473-133">Erstellen Sie eine zweite <xref:System.Type>-Variable mit der Bezeichnung `serviceType`, und weisen Sie ihr den Typ des implementierten Vertrags (`Calculator`) zu.</span><span class="sxs-lookup"><span data-stu-id="87473-133">Create a second <xref:System.Type> variable named `serviceType` and assign it the type of the implemented contract (`Calculator`).</span></span>

4. <span data-ttu-id="87473-134">Erstellen Sie eine Instanz der <xref:System.Uri>-Klasse mit der Bezeichnung `baseAddress` mit der Basisadresse des Dienstes.</span><span class="sxs-lookup"><span data-stu-id="87473-134">Create an instance of the <xref:System.Uri> class named `baseAddress` with the base address of the service.</span></span> <span data-ttu-id="87473-135">Die Basisadresse muss ein Schema haben, das mit dem Transport übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="87473-135">The base address must have a scheme that matches the transport.</span></span> <span data-ttu-id="87473-136">In diesem Fall ist das Transport Schema "http", und die Adresse enthält den speziellen Uniform Resource Identifier (URI) "localhost" und eine Portnummer (8036) sowie eine Basis Endpunkt Adresse ("Service Model Samples/"): `http://localhost:8036/serviceModelSamples/` .</span><span class="sxs-lookup"><span data-stu-id="87473-136">In this case, the transport scheme is HTTP, and the address includes the special Uniform Resource Identifier (URI) "localhost" and a port number (8036) as well as a base endpoint address ("serviceModelSamples/): `http://localhost:8036/serviceModelSamples/`.</span></span>

5. <span data-ttu-id="87473-137">Erstellen Sie eine Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse mit der `serviceType`-Variablen und der `baseAddress`-Variablen.</span><span class="sxs-lookup"><span data-stu-id="87473-137">Create an instance of the <xref:System.ServiceModel.ServiceHost> class with the `serviceType` and `baseAddress` variables.</span></span>

6. <span data-ttu-id="87473-138">Fügen Sie dem Dienst einen Endpunkt mit `contractType`, Bindung und einem Endpunktnamen (secureCalculator) hinzu.</span><span class="sxs-lookup"><span data-stu-id="87473-138">Add an endpoint to the service using the `contractType`, binding, and an endpoint name (secureCalculator).</span></span> <span data-ttu-id="87473-139">Ein Client muss beim Initiieren eines Aufrufs zum Dienst die Basisadresse und den Endpunktnamen verketten.</span><span class="sxs-lookup"><span data-stu-id="87473-139">A client must concatenate the base address and the endpoint name when initiating a call to the service.</span></span>

7. <span data-ttu-id="87473-140">Starten Sie den Dienst, indem Sie die <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="87473-140">Call the <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> method to start the service.</span></span> <span data-ttu-id="87473-141">Der Code für diese Prozedur wird hier gezeigt:</span><span class="sxs-lookup"><span data-stu-id="87473-141">The code for this procedure is shown here:</span></span>

    [!code-csharp[c_SecureWindowsService#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#2)]
    [!code-vb[c_SecureWindowsService#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#2)]

### <a name="using-the-binding-in-a-client"></a><span data-ttu-id="87473-142">Verwenden der Bindung in einem Client</span><span class="sxs-lookup"><span data-stu-id="87473-142">Using the Binding in a Client</span></span>

<span data-ttu-id="87473-143">Diese Prozedur zeigt die Generierung eines Proxys, der mit dem Dienst kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="87473-143">This procedure shows how to generate a proxy that communicates with the service.</span></span> <span data-ttu-id="87473-144">Der Proxy wird mit dem Service [Model Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) generiert, das die Dienst Metadaten zum Erstellen des Proxys verwendet.</span><span class="sxs-lookup"><span data-stu-id="87473-144">The proxy is generated with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) which uses the service metadata to create the proxy.</span></span>

<span data-ttu-id="87473-145">Durch diese Prozedur wird auch eine Instanz der <xref:System.ServiceModel.WSHttpBinding>-Klasse erstellt, um mit dem Dienst zu kommunizieren. Anschließend wird der Dienst aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="87473-145">This procedure also creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class to communicate with the service, and then calls the service.</span></span>

<span data-ttu-id="87473-146">In diesem Beispiel wird zum Erstellen des Clients nur Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="87473-146">This example uses only code to create the client.</span></span> <span data-ttu-id="87473-147">Alternativ können Sie eine Konfigurationsdatei verwenden. Dies wird im Abschnitt nach dieser Prozedur veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="87473-147">As an alternative, you can use a configuration file, which is shown in the section following this procedure.</span></span>

#### <a name="to-use-a-binding-in-a-client-with-code"></a><span data-ttu-id="87473-148">So verwenden Sie eine Bindung in einem Client mit Code</span><span class="sxs-lookup"><span data-stu-id="87473-148">To use a binding in a client with code</span></span>

1. <span data-ttu-id="87473-149">Verwenden Sie das SvcUtil.exe-Tool, um den Proxycode aus den Metadaten des Diensts zu generieren.</span><span class="sxs-lookup"><span data-stu-id="87473-149">Use the SvcUtil.exe tool to generate the proxy code from the service's metadata.</span></span> <span data-ttu-id="87473-150">Weitere Informationen finden Sie unter Gewusst [wie: Erstellen eines Clients](how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="87473-150">For more information, see [How to: Create a Client](how-to-create-a-wcf-client.md).</span></span> <span data-ttu-id="87473-151">Der generierte Proxy Code erbt von der- <xref:System.ServiceModel.ClientBase%601> Klasse, wodurch sichergestellt wird, dass jeder Client über die erforderlichen Konstruktoren, Methoden und Eigenschaften für die Kommunikation mit einem WCF-Dienst verfügt.</span><span class="sxs-lookup"><span data-stu-id="87473-151">The generated proxy code inherits from the <xref:System.ServiceModel.ClientBase%601> class, which ensures that every client has the necessary constructors, methods, and properties to communicate with a WCF service.</span></span> <span data-ttu-id="87473-152">In diesem Beispiel enthält der generierte Code die `CalculatorClient`-Klasse, die die `ICalculator`-Schnittstelle für die Kompatibilität mit dem Dienstcode implementiert.</span><span class="sxs-lookup"><span data-stu-id="87473-152">In this example, the generated code includes the `CalculatorClient` class, which implements the `ICalculator` interface, enabling compatibility with the service code.</span></span>

2. <span data-ttu-id="87473-153">Der Code dieser Prozedur wird am Anfang der `Main`-Methode des Clientprogramms eingefügt.</span><span class="sxs-lookup"><span data-stu-id="87473-153">This procedure's code is inserted at the beginning of the `Main` method of the client program.</span></span>

3. <span data-ttu-id="87473-154">Erstellen Sie eine Instanz der <xref:System.ServiceModel.WSHttpBinding>-Klasse und legen Sie ihren Sicherheitsmodus auf `Message` und ihren Clientanmeldeinformationstyp auf `Windows` fest.</span><span class="sxs-lookup"><span data-stu-id="87473-154">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set its security mode to `Message` and its client credential type to `Windows`.</span></span> <span data-ttu-id="87473-155">Im Beispiel wird die Variable `clientBinding` genannt.</span><span class="sxs-lookup"><span data-stu-id="87473-155">The example names the variable `clientBinding`.</span></span>

4. <span data-ttu-id="87473-156">Erstellen Sie eine Instanz der <xref:System.ServiceModel.EndpointAddress>-Klasse mit der Bezeichnung `serviceAddress`.</span><span class="sxs-lookup"><span data-stu-id="87473-156">Create an instance of the <xref:System.ServiceModel.EndpointAddress> class named `serviceAddress`.</span></span> <span data-ttu-id="87473-157">Initialisieren Sie die Instanz mit der mit dem Endpunktnamen verketteten Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="87473-157">Initialize the instance with the base address concatenated with the endpoint name.</span></span>

5. <span data-ttu-id="87473-158">Erstellen Sie eine Instanz der generierten Clientklasse mit der `serviceAddress`-Variablen und der `clientBinding`-Variablen.</span><span class="sxs-lookup"><span data-stu-id="87473-158">Create an instance of the generated client class with the `serviceAddress` and the `clientBinding` variables.</span></span>

6. <span data-ttu-id="87473-159">Rufen Sie die <xref:System.ServiceModel.ClientBase%601.Open%2A>-Methode auf, wie im folgenden Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="87473-159">Call the <xref:System.ServiceModel.ClientBase%601.Open%2A> method, as shown in the following code.</span></span>

7. <span data-ttu-id="87473-160">Rufen Sie den Dienst auf, und zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="87473-160">Call the service and display the results.</span></span>

    [!code-csharp[c_secureWindowsClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#1)]
    [!code-vb[c_secureWindowsClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#1)]

## <a name="using-the-configuration-file"></a><span data-ttu-id="87473-161">Verwenden der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="87473-161">Using the Configuration File</span></span>

<span data-ttu-id="87473-162">Anstelle der Erstellung der Bindung mithilfe von prozeduralem Code können Sie auch den folgenden Code für den Bindungsabschnitt der Konfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="87473-162">Instead of creating the binding with procedural code, you can use the following code shown for the bindings section of the configuration file.</span></span>

<span data-ttu-id="87473-163">Wenn Sie noch keinen Dienst definiert haben, finden Sie weitere Informationen unter [Entwerfen und Implementieren von Diensten](designing-and-implementing-services.md)und [Konfigurieren von Diensten](configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="87473-163">If you do not already have a service defined, see [Designing and Implementing Services](designing-and-implementing-services.md), and [Configuring Services](configuring-services.md).</span></span>

> [!NOTE]
> <span data-ttu-id="87473-164">Dieser Konfigurations Code wird sowohl in den Dienst-als auch in den Client Konfigurationsdateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="87473-164">This configuration code is used in both the service and client configuration files.</span></span>

#### <a name="to-enable-transfer-security-on-a-service-in-a-windows-domain-using-configuration"></a><span data-ttu-id="87473-165">So aktivieren Sie mit der Konfiguration Übertragungssicherheit für einen Dienst in einer Windows-Domäne</span><span class="sxs-lookup"><span data-stu-id="87473-165">To enable transfer security on a service in a Windows domain using configuration</span></span>

1. <span data-ttu-id="87473-166">Fügen Sie [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) dem- [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) Element Abschnitt der Konfigurationsdatei ein-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="87473-166">Add a [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element to the [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) element section of the configuration file.</span></span>

2. <span data-ttu-id="87473-167">Fügen Sie `binding` dem <> Element ein <>-Element hinzu, `WSHttpBinding` und legen Sie das- `configurationName` Attribut auf einen für Ihre Anwendung geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="87473-167">Add a <`binding`> element to the <`WSHttpBinding`> element and set the `configurationName` attribute to a value appropriate to your application.</span></span>

3. <span data-ttu-id="87473-168">Fügen Sie ein <`security`> Element hinzu, und legen Sie das- `mode` Attribut auf Message fest.</span><span class="sxs-lookup"><span data-stu-id="87473-168">Add a <`security`> element and set the `mode` attribute to Message.</span></span>

4. <span data-ttu-id="87473-169">Fügen Sie ein <`message`> Element hinzu, und legen Sie das- `clientCredentialType` Attribut auf Windows fest.</span><span class="sxs-lookup"><span data-stu-id="87473-169">Add a <`message`> element and set the `clientCredentialType` attribute to Windows.</span></span>

5. <span data-ttu-id="87473-170">Ersetzen Sie in der Konfigurationsdatei des Diensts den `<bindings>`-Abschnitt durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="87473-170">In the service's configuration file, replace the `<bindings>` section with the following code.</span></span> <span data-ttu-id="87473-171">Wenn Sie nicht bereits über eine Dienst Konfigurationsdatei verfügen, finden Sie weitere Informationen unter [Verwenden von Bindungen zum Konfigurieren von Diensten und Clients](using-bindings-to-configure-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="87473-171">If you do not already have a service configuration file, see [Using Bindings to Configure Services and Clients](using-bindings-to-configure-services-and-clients.md).</span></span>

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

### <a name="using-the-binding-in-a-client"></a><span data-ttu-id="87473-172">Verwenden der Bindung in einem Client</span><span class="sxs-lookup"><span data-stu-id="87473-172">Using the Binding in a Client</span></span>

<span data-ttu-id="87473-173">In dieser Prozedur wird die Generierung zweier Dateien veranschaulicht: einem Proxy, der mit dem Dienst kommuniziert, und einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="87473-173">This procedure shows how to generate two files: a proxy that communicates with the service and a configuration file.</span></span> <span data-ttu-id="87473-174">Darüber hinaus werden auch Änderungen am Clientprogramm beschrieben &#8211; der dritten Datei, die auf dem Client verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="87473-174">It also describes changes to the client program, which is the third file used on the client.</span></span>

#### <a name="to-use-a-binding-in-a-client-with-configuration"></a><span data-ttu-id="87473-175">So verwenden Sie eine Bindung für einen Client mit Konfiguration</span><span class="sxs-lookup"><span data-stu-id="87473-175">To use a binding in a client with configuration</span></span>

1. <span data-ttu-id="87473-176">Verwenden Sie das SvcUtil.exe-Tool, um den Proxycode und die Konfigurationsdatei aus den Metadaten des Diensts zu generieren.</span><span class="sxs-lookup"><span data-stu-id="87473-176">Use the SvcUtil.exe tool to generate the proxy code and configuration file from the service's metadata.</span></span> <span data-ttu-id="87473-177">Weitere Informationen finden Sie unter Gewusst [wie: Erstellen eines Clients](how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="87473-177">For more information, see [How to: Create a Client](how-to-create-a-wcf-client.md).</span></span>

2. <span data-ttu-id="87473-178">Ersetzen Sie den- [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) Abschnitt der generierten Konfigurationsdatei durch den Konfigurations Code aus dem vorherigen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="87473-178">Replace the [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) section of the generated configuration file with the configuration code from the preceding section.</span></span>

3. <span data-ttu-id="87473-179">Prozeduraler Code wird am Anfang der `Main`-Methode des Clientprogramms eingefügt.</span><span class="sxs-lookup"><span data-stu-id="87473-179">Procedural code is inserted at the beginning of the `Main` method of the client program.</span></span>

4. <span data-ttu-id="87473-180">Erstellen Sie eine Instanz der generierten Clientklasse, und geben Sie den Namen der Bindung in der Konfigurationsdatei als Eingabeparameter weiter.</span><span class="sxs-lookup"><span data-stu-id="87473-180">Create an instance of the generated client class passing the name of the binding in the configuration file as an input parameter.</span></span>

5. <span data-ttu-id="87473-181">Rufen Sie die <xref:System.ServiceModel.ClientBase%601.Open%2A>-Methode auf, wie im folgenden Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="87473-181">Call the <xref:System.ServiceModel.ClientBase%601.Open%2A> method, as shown in the following code.</span></span>

6. <span data-ttu-id="87473-182">Rufen Sie den Dienst auf, und zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="87473-182">Call the service and display the results.</span></span>

    [!code-csharp[c_secureWindowsClient#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#2)]

## <a name="example"></a><span data-ttu-id="87473-183">Beispiel</span><span class="sxs-lookup"><span data-stu-id="87473-183">Example</span></span>

[!code-csharp[c_SecureWindowsService#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#0)]

[!code-csharp[c_SecureWindowsClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#0)]
[!code-vb[c_SecureWindowsClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#0)]

## <a name="see-also"></a><span data-ttu-id="87473-184">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="87473-184">See also</span></span>

- <xref:System.ServiceModel.WSHttpBinding>
- [<span data-ttu-id="87473-185">ServiceModel Metadata Utility-Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="87473-185">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="87473-186">Vorgehensweise: Erstellen eines Clients</span><span class="sxs-lookup"><span data-stu-id="87473-186">How to: Create a Client</span></span>](how-to-create-a-wcf-client.md)
- [<span data-ttu-id="87473-187">Sichern von Diensten</span><span class="sxs-lookup"><span data-stu-id="87473-187">Securing Services</span></span>](securing-services.md)
- [<span data-ttu-id="87473-188">Sicherheitsübersicht</span><span class="sxs-lookup"><span data-stu-id="87473-188">Security Overview</span></span>](./feature-details/security-overview.md)
