---
title: Adressheader
ms.date: 03/30/2017
ms.assetid: b0c94d4a-3bde-4b4d-bb6d-9f12bc3a6940
ms.openlocfilehash: 4ccb309178251b32068d6cdbb81874322f991bb9
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57673235"
---
# <a name="address-headers"></a><span data-ttu-id="a3cbb-102">Adressheader</span><span class="sxs-lookup"><span data-stu-id="a3cbb-102">Address Headers</span></span>

<span data-ttu-id="a3cbb-103">Beispiel zu Adressheadern wird veranschaulicht, wie Clients Verweisparameter mit einem Dienst mit Windows Communication Foundation (WCF) übergeben können.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-103">The Address Headers sample demonstrates how clients can pass reference parameters to a service using Windows Communication Foundation (WCF).</span></span>

> [!NOTE]
> <span data-ttu-id="a3cbb-104">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="a3cbb-105">In der WS-Adressierungsspezifikation wird ein Endpunktverweis als Möglichkeit definiert, einen bestimmten Webdienstendpunkt zu adressieren.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-105">The WS-Addressing specification defines the notion of an endpoint reference as a way to address a particular Web service endpoint.</span></span> <span data-ttu-id="a3cbb-106">In WCF werden Endpunktverweise mit der `EndpointAddress` -Klasse – `EndpointAddress` ist der Typ des Address-Felds von der `ServiceEndpoint` Klasse.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-106">In WCF, endpoint references are modeled using the `EndpointAddress` class - `EndpointAddress` is the type of the Address field of the `ServiceEndpoint` class.</span></span>

<span data-ttu-id="a3cbb-107">Bestandteil des Endpunktverweismodells ist, dass jeder Verweis einige Verweisparameter enthalten kann, die weitere identifizierende Informationen liefern.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-107">Part of the endpoint reference model is that each reference can carry some reference parameters that add extra identifying information.</span></span> <span data-ttu-id="a3cbb-108">In WCF diese Endpunktverweise als Instanzen der `AddressHeader` Klasse.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-108">In WCF, these reference parameters are modeled as instances of `AddressHeader` class.</span></span>

<span data-ttu-id="a3cbb-109">In diesem Beispiel fügt der Client der `EndpointAddress` des Clientendpunkts einen Verweisparameter hinzu.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-109">In this sample, the client adds a reference parameter to the `EndpointAddress` of the client endpoint.</span></span> <span data-ttu-id="a3cbb-110">Der Dienst sucht diesen Verweisparameter und verwendet seinen Wert in der Logik des "Hello"-Dienstvorgangs.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-110">The service looks for this reference parameter and uses its value in the logic of its "Hello" service operation.</span></span>

## <a name="client"></a><span data-ttu-id="a3cbb-111">Client</span><span class="sxs-lookup"><span data-stu-id="a3cbb-111">Client</span></span>

<span data-ttu-id="a3cbb-112">Damit der Client einen Verweisparameter senden kann, muss er der `AddressHeader` von `EndpointAddress` einen `ServiceEndpoint` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-112">For the client to send a reference parameter, it must add an `AddressHeader` to the `EndpointAddress` of the `ServiceEndpoint`.</span></span> <span data-ttu-id="a3cbb-113">Da die `EndpointAddress`-Klasse unveränderlich ist, muss das Ändern einer Endpunktadresse mithilfe der `EndpointAddressBuilder`-Klasse erfolgen.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-113">Because the `EndpointAddress` class is immutable, modification of an endpoint address must be done using the `EndpointAddressBuilder` class.</span></span> <span data-ttu-id="a3cbb-114">Im folgenden Code wird der Client zum Senden eines Verweisparameters als Teil der Nachricht initialisiert.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-114">The following code initializes the client to send a reference parameter as part of its message.</span></span>

```csharp
HelloClient client = new HelloClient();
EndpointAddressBuilder builder =
    new EndpointAddressBuilder(client.Endpoint.Address);
AddressHeader header =
    AddressHeader.CreateAddressHeader(IDName, IDNamespace, "John");
builder.Headers.Add(header);
client.Endpoint.Address = builder.ToEndpointAddress();
```

<span data-ttu-id="a3cbb-115">Im Code wird ein `EndpointAddressBuilder` mit der ursprünglichen `EndpointAddress` als Anfangswert erstellt.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-115">The code creates an `EndpointAddressBuilder` using the original `EndpointAddress` as an initial value.</span></span> <span data-ttu-id="a3cbb-116">Anschließend wird ein neu erstellter Adressheader hinzugefügt; der Aufruf von `CreateAddressHeader` erstellt einen Header mit einem bestimmten Namen, Namespace und Wert.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-116">It then adds a newly created address header; the call to `CreateAddressHeader` creates a header with a particular name, namespace, and value.</span></span> <span data-ttu-id="a3cbb-117">Hier lautet der Wert "John".</span><span class="sxs-lookup"><span data-stu-id="a3cbb-117">Here the value is "John".</span></span> <span data-ttu-id="a3cbb-118">Nach dem Hinzufügen des Headers zum Builder konvertiert die `ToEndpointAddress()`-Methode den (änderbaren) Builder zurück in eine (unveränderliche) Endpunktadresse. Diese wird dann wieder dem Address-Feld des Clientendpunkts zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-118">Once the header is added to the builder, the `ToEndpointAddress()` method converts the (mutable) builder back into an (immutable) endpoint address, which is assigned back to the client endpoint's Address field.</span></span>

<span data-ttu-id="a3cbb-119">Wenn der Client nun `Console.WriteLine(client.Hello());` aufruft, kann der Dienst den Wert dieses Adressparameters abrufen, wie in der Ausgabe des Clients angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-119">Now when the client calls `Console.WriteLine(client.Hello());`, the service is able to get the value of this address parameter, as seen in the resulting output of the client.</span></span>

`Hello, John`

## <a name="server"></a><span data-ttu-id="a3cbb-120">Server</span><span class="sxs-lookup"><span data-stu-id="a3cbb-120">Server</span></span>

<span data-ttu-id="a3cbb-121">Bei der Implementierung des Servervorgangs `Hello()` wird der aktuelle `OperationContext` verwendet, um die Werte der Header in der eingehenden Nachricht zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-121">The implementation of the service operation `Hello()` uses the current `OperationContext` to inspect the values of the headers on the incoming message.</span></span>

```csharp
string id = null;
// look at headers on incoming message
for (int i = 0;
     i < OperationContext.Current.IncomingMessageHeaders.Count;
     ++i)
{
    MessageHeaderInfo h = OperationContext.Current.IncomingMessageHeaders[i];
    // for any reference parameters with the correct name & namespace
    if (h.IsReferenceParameter &&
        h.Name == IDName &&
        h.Namespace == IDNamespace)
    {
        // read the value of that header
        XmlReader xr = OperationContext.Current.IncomingMessageHeaders.GetReaderAtHeader(i);
        id = xr.ReadElementContentAsString();
    }
}
return "Hello, " + id;
```

<span data-ttu-id="a3cbb-122">Der Code durchläuft alle Header in der eingehenden Nachricht und sucht Header, bei denen es sich um Verweisparameter mit einem bestimmten Namen handelt.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-122">The code iterates over all the headers on the incoming message, looking for headers that are reference parameters with the particular name and.</span></span> <span data-ttu-id="a3cbb-123">Wenn der Parameter gefunden wird, wird der Wert des Parameters gelesen und in der "id"-Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-123">When the parameter is found, it reads the value of the parameter and stores it in the "id" variable.</span></span>

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a3cbb-124">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="a3cbb-124">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="a3cbb-125">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a3cbb-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="a3cbb-126">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="a3cbb-127">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a3cbb-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3cbb-128">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-128">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a3cbb-129">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-129">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="a3cbb-130">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-130">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a3cbb-131">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a3cbb-131">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\AddressHeaders`
