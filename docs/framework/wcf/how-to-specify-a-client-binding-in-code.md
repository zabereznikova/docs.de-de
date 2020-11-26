---
title: 'Vorgehensweise: Angeben einer Clientbindung im Code'
description: Erfahren Sie, wie Sie die Bindung für einen WCF-Client Imperativ im Code angeben. Der Client greift in diesem Beispiel auf einen Dienst zu.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6bee5da4-adf7-42e6-8f78-63a9e5c6dbad
ms.openlocfilehash: f9a56c631d841fe60923c05a19bdec9db989ac60
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236571"
---
# <a name="how-to-specify-a-client-binding-in-code"></a><span data-ttu-id="eff3c-104">Vorgehensweise: Angeben einer Clientbindung im Code</span><span class="sxs-lookup"><span data-stu-id="eff3c-104">How to: Specify a Client Binding in Code</span></span>

<span data-ttu-id="eff3c-105">In diesem Beispiel wird ein Client erstellt, um einen Rechnerdienst zu nutzen, und die Bindung des Clients wird imperativ im Code angegeben.</span><span class="sxs-lookup"><span data-stu-id="eff3c-105">In this example, a client is created to use a calculator service and the binding for that client is specified imperatively in code.</span></span> <span data-ttu-id="eff3c-106">Der Client greift auf den `CalculatorService` zu, der die `ICalculator`-Schnittstelle implementiert, und sowohl der Dienst als auch der Client verwenden die Klasse <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="eff3c-106">The client accesses the `CalculatorService`, which implements the `ICalculator` interface, and both the service and the client use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="eff3c-107">In dieser Prozedur wird davon ausgegangen, dass der Rechnerdienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eff3c-107">This procedure assumes that the calculator service is running.</span></span> <span data-ttu-id="eff3c-108">Informationen zum Aufbau des Dienstanbieter finden [Sie unter Gewusst wie: Angeben einer Dienst Bindung in der Konfiguration](how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="eff3c-108">For information about building the service, see [How to: Specify a Service Binding in Configuration](how-to-specify-a-service-binding-in-configuration.md).</span></span> <span data-ttu-id="eff3c-109">Außerdem wird das [Service Model Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)Windows Communication Foundation (WCF) bereitstellt, um die Client Komponenten automatisch zu generieren.</span><span class="sxs-lookup"><span data-stu-id="eff3c-109">It also uses the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)Windows Communication Foundation (WCF) provides to automatically generate the client components.</span></span> <span data-ttu-id="eff3c-110">Das Tool generiert den Clientcode für den Zugriff auf den Dienst.</span><span class="sxs-lookup"><span data-stu-id="eff3c-110">The tool generates the client code for accessing the service.</span></span>  
  
 <span data-ttu-id="eff3c-111">Der Client wird in zwei Schritten erstellt.</span><span class="sxs-lookup"><span data-stu-id="eff3c-111">The client is built in two parts.</span></span> <span data-ttu-id="eff3c-112">Svcutil.exe generiert den `ClientCalculator`, der die `ICalculator`-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="eff3c-112">Svcutil.exe generates the `ClientCalculator` that implements the `ICalculator` interface.</span></span> <span data-ttu-id="eff3c-113">Anschließend wird die Clientanwendung erstellt, indem eine Instanz von `ClientCalculator` erstellt wird und dann die Bindung und die Adresse für den Dienst im Code angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="eff3c-113">This client application is then constructed by constructing an instance of `ClientCalculator` and then specifying the binding and the address for the service in code.</span></span>  
  
 <span data-ttu-id="eff3c-114">Die Quell Kopie dieses Beispiels finden Sie im Beispiel " [BasicBinding](./samples/basicbinding.md) ".</span><span class="sxs-lookup"><span data-stu-id="eff3c-114">For the source copy of this example, see the [BasicBinding](./samples/basicbinding.md) sample.</span></span>  
  
### <a name="to-specify-a-custom-binding-in-code"></a><span data-ttu-id="eff3c-115">So geben Sie eine benutzerdefinierte Bindung im Code an</span><span class="sxs-lookup"><span data-stu-id="eff3c-115">To specify a custom binding in code</span></span>  
  
1. <span data-ttu-id="eff3c-116">Verwenden Sie Svcutil.exe in der Befehlszeile, um Code von Dienstmetadaten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="eff3c-116">Use Svcutil.exe from the command line to generate code from service metadata.</span></span>  
  
    ```console  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. <span data-ttu-id="eff3c-117">Der generierte Client enthält die `ICalculator`-Schnittstelle, die den Dienstvertrag definiert, dem die Clientimplementierung entsprechen muss.</span><span class="sxs-lookup"><span data-stu-id="eff3c-117">The client that is generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#1)]
     [!code-vb[C_HowTo_CodeClientBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#1)]  
  
3. <span data-ttu-id="eff3c-118">Der generierte Client enthält außerdem die Implementierung vom `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="eff3c-118">The generated client also contains the implementation of the `ClientCalculator`.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#2)]
     [!code-vb[C_HowTo_CodeClientBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#2)]  
  
4. <span data-ttu-id="eff3c-119">Erstellen Sie eine Instanz des `ClientCalculator`, der die <xref:System.ServiceModel.BasicHttpBinding>-Klasse in einer Clientanwendung verwendet, und rufen Sie anschließend die Dienstvorgänge an der angegebenen Adresse auf.</span><span class="sxs-lookup"><span data-stu-id="eff3c-119">Create an instance of the `ClientCalculator` that uses the <xref:System.ServiceModel.BasicHttpBinding> class in a client application, and then call the service operations at the specified address.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#3)]
     [!code-vb[C_HowTo_CodeClientBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#3)]  
  
5. <span data-ttu-id="eff3c-120">Kompilieren Sie den Code, und führen Sie den Client aus.</span><span class="sxs-lookup"><span data-stu-id="eff3c-120">Compile and run the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eff3c-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eff3c-121">See also</span></span>

- [<span data-ttu-id="eff3c-122">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="eff3c-122">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
