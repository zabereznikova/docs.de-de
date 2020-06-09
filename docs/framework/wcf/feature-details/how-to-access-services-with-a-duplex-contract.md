---
title: 'Vorgehensweise: Zugreifen auf Dienste mit einem Duplex Vertrag'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
ms.openlocfilehash: bc42792b827b49265a0b1addf959de2fa1a041e3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597214"
---
# <a name="how-to-access-services-with-a-duplex-contract"></a><span data-ttu-id="878ec-102">Vorgehensweise: Zugreifen auf Dienste mit einem Duplex Vertrag</span><span class="sxs-lookup"><span data-stu-id="878ec-102">How to: Access services with a duplex contract</span></span>

<span data-ttu-id="878ec-103">Eine Funktion von Windows Communication Foundation (WCF) ist die Möglichkeit, einen Dienst zu erstellen, der ein Duplex Nachrichten Muster verwendet.</span><span class="sxs-lookup"><span data-stu-id="878ec-103">One feature of Windows Communication Foundation (WCF) is the ability to create a service that uses a duplex messaging pattern.</span></span> <span data-ttu-id="878ec-104">Anhand dieses Musters kann ein Dienst mit dem Client über einen Rückruf kommunizieren</span><span class="sxs-lookup"><span data-stu-id="878ec-104">This pattern allows a service to communicate with the client through a callback.</span></span> <span data-ttu-id="878ec-105">In diesem Thema werden die Schritte zum Erstellen eines WCF-Clients in einer Client Klasse gezeigt, die die Rückruf Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="878ec-105">This topic shows the steps to create a WCF client in a client class that implements the callback interface.</span></span>

<span data-ttu-id="878ec-106">Eine Dualbindung macht die IP-Adresse des Clients für den Dienst verfügbar.</span><span class="sxs-lookup"><span data-stu-id="878ec-106">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="878ec-107">Der Client sollte Sicherheit eingestellt haben, um sicherzustellen, dass nur Verbindungen zu vertrauensvollen Diensten hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="878ec-107">The client should use security to ensure that it connects only to services it trusts.</span></span>

<span data-ttu-id="878ec-108">Ein Tutorial zum Erstellen eines einfachen WCF-Dienstanbieter und-Clients finden Sie im [Tutorial zu](../getting-started-tutorial.md)den ersten Schritten.</span><span class="sxs-lookup"><span data-stu-id="878ec-108">For a tutorial on creating a basic WCF service and client, see [Getting Started Tutorial](../getting-started-tutorial.md).</span></span>

## <a name="to-access-a-duplex-service"></a><span data-ttu-id="878ec-109">So greifen Sie auf einen Duplexdienst zu</span><span class="sxs-lookup"><span data-stu-id="878ec-109">To access a duplex service</span></span>

1. <span data-ttu-id="878ec-110">Erstellen Sie einen Dienst, der zwei Schnittstellen enthält.</span><span class="sxs-lookup"><span data-stu-id="878ec-110">Create a service that contains two interfaces.</span></span> <span data-ttu-id="878ec-111">Die erste Schnittstelle ist dem Dienst vorbehalten, die zweite Schnittstelle wird für den Rückruf verwendet.</span><span class="sxs-lookup"><span data-stu-id="878ec-111">The first interface is for the service, the second is for the callback.</span></span> <span data-ttu-id="878ec-112">Weitere Informationen zum Erstellen eines Duplex Dienstanbieter finden [Sie unter Gewusst wie: Erstellen eines Duplex Vertrags](how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="878ec-112">For more information about creating a duplex service, see [How to: Create a Duplex Contract](how-to-create-a-duplex-contract.md).</span></span>

2. <span data-ttu-id="878ec-113">Führen Sie den Dienst aus.</span><span class="sxs-lookup"><span data-stu-id="878ec-113">Run the service.</span></span>

3. <span data-ttu-id="878ec-114">Verwenden Sie das [Service Model Metadata Utility-Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , um Verträge (Schnittstellen) für den Client zu generieren.</span><span class="sxs-lookup"><span data-stu-id="878ec-114">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to generate contracts (interfaces) for the client.</span></span> <span data-ttu-id="878ec-115">Weitere Informationen hierzu finden Sie unter Gewusst [wie: Erstellen eines Clients](../how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="878ec-115">For information about how to do this, see  [How to: Create a Client](../how-to-create-a-wcf-client.md).</span></span>

4. <span data-ttu-id="878ec-116">Implementieren Sie die Rückrufschnittstelle in der Client-Klasse, wie im nachfolgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="878ec-116">Implement the callback interface in the client class, as shown in the following example.</span></span>

    ```csharp
    public class CallbackHandler : ICalculatorDuplexCallback
    {
        public void Result(double result)
        {
            Console.WriteLine("Result ({0})", result);
        }
        public void Equation(string equation)
        {
            Console.WriteLine("Equation({0})", equation);
        }
    }
    ```

    ```vb
    Public Class CallbackHandler
    Implements ICalculatorDuplexCallback
       Public Sub Result (ByVal result As Double)
          Console.WriteLine("Result ({0})", result)
       End Sub
        Public Sub Equation(ByVal equation As String)
            Console.WriteLine("Equation({0})", equation)
        End Sub
    End Class
    ```

5. <span data-ttu-id="878ec-117">Erstellen Sie eine Instanz der <xref:System.ServiceModel.InstanceContext>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="878ec-117">Create an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="878ec-118">Der Konstruktor benötigt eine Instanz der Client-Klasse.</span><span class="sxs-lookup"><span data-stu-id="878ec-118">The constructor requires an instance of the client class.</span></span>

    ```csharp
    InstanceContext site = new InstanceContext(new CallbackHandler());
    ```

    ```vb
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())
    ```

6. <span data-ttu-id="878ec-119">Erstellen Sie eine Instanz des WCF-Clients mithilfe des Konstruktors, für den ein-Objekt erforderlich ist <xref:System.ServiceModel.InstanceContext> .</span><span class="sxs-lookup"><span data-stu-id="878ec-119">Create an instance of the WCF client using the constructor that requires an <xref:System.ServiceModel.InstanceContext> object.</span></span> <span data-ttu-id="878ec-120">Der zweite Parameter des Konstruktors ist der Name eines Endpunkts in der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="878ec-120">The second parameter of the constructor is the name of an endpoint found in the configuration file.</span></span>

    ```csharp
    CalculatorDuplexClient wcfClient = new CalculatorDuplexClient(site, "default");
    ```

    ```vb
    Dim wcfClient As New CalculatorDuplexClient(site, "default")
    ```

7. <span data-ttu-id="878ec-121">Nennen Sie die Methoden des WCF-Clients nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="878ec-121">Call the methods of the WCF client as required.</span></span>

## <a name="example"></a><span data-ttu-id="878ec-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="878ec-122">Example</span></span>

<span data-ttu-id="878ec-123">Im folgenden Codebeispiel wird das Erstellen einer Client-Klasse veranschaulicht, die auf einen Duplexvertrag zugreift.</span><span class="sxs-lookup"><span data-stu-id="878ec-123">The following code example demonstrates how to create a client class that accesses a duplex contract.</span></span>

[!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
[!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]

## <a name="see-also"></a><span data-ttu-id="878ec-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="878ec-124">See also</span></span>

- [<span data-ttu-id="878ec-125">Tutorial zu den ersten Schritten</span><span class="sxs-lookup"><span data-stu-id="878ec-125">Getting Started Tutorial</span></span>](../getting-started-tutorial.md)
- [<span data-ttu-id="878ec-126">Vorgehensweise: Erstellen eines Duplexvertrags</span><span class="sxs-lookup"><span data-stu-id="878ec-126">How to: Create a Duplex Contract</span></span>](how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="878ec-127">ServiceModel Metadata Utility-Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="878ec-127">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="878ec-128">Vorgehensweise: Erstellen eines Clients</span><span class="sxs-lookup"><span data-stu-id="878ec-128">How to: Create a Client</span></span>](../how-to-create-a-wcf-client.md)
- [<span data-ttu-id="878ec-129">Vorgehensweise: Verwenden der ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="878ec-129">How to: Use the ChannelFactory</span></span>](how-to-use-the-channelfactory.md)
