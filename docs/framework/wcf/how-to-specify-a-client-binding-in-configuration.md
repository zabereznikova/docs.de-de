---
title: 'Vorgehensweise: Angeben einer Clientbindung in einer Konfiguration'
description: Erfahren Sie, wie Sie die Bindung für einen WCF-Client deklarativ in einer Konfigurationsdatei angeben können. Der Client greift in diesem Beispiel auf einen Dienst zu.
ms.date: 03/30/2017
ms.assetid: 4a7c79aa-50ee-4991-891e-adc0599323a7
ms.openlocfilehash: e8a552211b28c1323b2afd595c5b060db6b2824a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236506"
---
# <a name="how-to-specify-a-client-binding-in-configuration"></a><span data-ttu-id="d193e-104">Vorgehensweise: Angeben einer Clientbindung in einer Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d193e-104">How to: Specify a Client Binding in Configuration</span></span>

<span data-ttu-id="d193e-105">In diesem Beispiel wird eine Client-Konsolenanwendung erstellt, um einen Rechnerdienst zu nutzen, und die Bindung dieses Clients wird deklarativ in der Konfiguration angegeben.</span><span class="sxs-lookup"><span data-stu-id="d193e-105">In this example, a client console application is created to use a calculator service, and the binding for that client is specified declaratively in configuration.</span></span> <span data-ttu-id="d193e-106">Der Client greift auf den `CalculatorService` zu, der die `ICalculator`-Schnittstelle implementiert, und sowohl der Dienst als auch der Client verwenden die Klasse <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="d193e-106">The client accesses the `CalculatorService`, which implements the `ICalculator` interface, and both the service and the client use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="d193e-107">In der umrissenen Prozedur wird davon ausgegangen, dass der Rechnerdienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d193e-107">The procedure outlined assumes that the calculator service is running.</span></span> <span data-ttu-id="d193e-108">Weitere Informationen zum Erstellen des Dienstanbieter finden Sie unter Gewusst [wie: Angeben einer Dienst Bindung in der Konfiguration](how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="d193e-108">For information about how to build the service, see [How to: Specify a Service Binding in Configuration](how-to-specify-a-service-binding-in-configuration.md).</span></span> <span data-ttu-id="d193e-109">Außerdem wird das [Service Model Metadata Utility-Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) verwendet, das Windows Communication Foundation (WCF) bereitstellt, um die Client Komponenten automatisch zu generieren.</span><span class="sxs-lookup"><span data-stu-id="d193e-109">It also uses the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) that Windows Communication Foundation (WCF) provides to automatically generate the client components.</span></span> <span data-ttu-id="d193e-110">Das Tool generiert den Clientcode und die Konfiguration zum Zugreifen auf den Dienst.</span><span class="sxs-lookup"><span data-stu-id="d193e-110">The tool generates the client code and configuration for accessing the service.</span></span>  
  
 <span data-ttu-id="d193e-111">Der Client wird in zwei Schritten erstellt.</span><span class="sxs-lookup"><span data-stu-id="d193e-111">The client is built in two parts.</span></span> <span data-ttu-id="d193e-112">Svcutil.exe generiert den `ClientCalculator`, der die `ICalculator`-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="d193e-112">Svcutil.exe generates the `ClientCalculator` that implements the `ICalculator` interface.</span></span> <span data-ttu-id="d193e-113">Diese Clientanwendung wird dann durch das Erstellen einer Instanz von `ClientCalculator` erstellt.</span><span class="sxs-lookup"><span data-stu-id="d193e-113">This client application is then constructed by constructing an instance of `ClientCalculator`.</span></span>  
  
 <span data-ttu-id="d193e-114">Normalerweise ist es die bewährte Methode, die Bindung anzugeben und die Informationen deklarativ in der Konfiguration anzusprechen anstatt imperativ im Code.</span><span class="sxs-lookup"><span data-stu-id="d193e-114">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="d193e-115">Die Definition von Endpunkten im Code ist normalerweise nicht geeignet, da die Bindungen und Adressen für einen bereitgestellten Dienst sich in der Regel von denen unterscheiden, die während der Entwicklung des Diensts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d193e-115">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="d193e-116">Allgemeiner gesagt ist es durch die Trennung von Bindungs- und Adressierungsinformationen vom Code möglich, diese zu ändern, ohne die Anwendung neu kompilieren oder erneut bereitstellen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="d193e-116">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="d193e-117">Mit dem [Konfigurations-Editor-Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md)können Sie alle folgenden Konfigurationsschritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="d193e-117">You can perform all of the following configuration steps by using the [Configuration Editor Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="d193e-118">Die Quell Kopie dieses Beispiels finden Sie im Beispiel " [BasicBinding](./samples/basicbinding.md) ".</span><span class="sxs-lookup"><span data-stu-id="d193e-118">For the source copy of this example, see the [BasicBinding](./samples/basicbinding.md) sample.</span></span>  
  
### <a name="specifying-a-client-binding-in-configuration"></a><span data-ttu-id="d193e-119">Eine Clientbindung in einer Konfiguration angeben</span><span class="sxs-lookup"><span data-stu-id="d193e-119">Specifying a client binding in configuration</span></span>  
  
1. <span data-ttu-id="d193e-120">Verwenden Sie Svcutil.exe in der Befehlszeile, um Code von Dienstmetadaten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="d193e-120">Use Svcutil.exe from the command line to generate code from service metadata.</span></span>  
  
    ```console  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. <span data-ttu-id="d193e-121">Der generierte Client enthält die `ICalculator`-Schnittstelle, die den Dienstvertrag definiert, dem die Clientimplementierung entsprechen muss.</span><span class="sxs-lookup"><span data-stu-id="d193e-121">The client that is generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#1)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#1)]  
  
3. <span data-ttu-id="d193e-122">Der generierte Client enthält außerdem die Implementierung vom `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="d193e-122">The generated client also contains the implementation of the `ClientCalculator`.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#2)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#2)]  
  
4. <span data-ttu-id="d193e-123">Svcutil.exe generiert auch die Konfiguration für den Client, der die <xref:System.ServiceModel.BasicHttpBinding>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="d193e-123">Svcutil.exe also generates the configuration for the client that uses the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span> <span data-ttu-id="d193e-124">Wenn Sie Visual Studio verwenden, benennen Sie diese Datei App.config. Beachten Sie, dass die Adress-und Bindungs Informationen nicht an einer beliebigen Stelle in der Implementierung des Dienstanbieter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d193e-124">When using Visual Studio, name this file App.config. Note that the address and binding information are not specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="d193e-125">Es muss auch kein Code geschrieben werden, um Informationen aus der Konfigurationsdatei abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d193e-125">Also, code does not have to be written to retrieve that information from the configuration file.</span></span>  
  
     [!code-xml[C_HowTo_ConfigureClientBinding#100](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/common/client.exe.config#100)]

5. <span data-ttu-id="d193e-126">Erstellen Sie eine Instanz des `ClientCalculator` in einer Anwendung, und rufen Sie dann die Dienstvorgänge auf.</span><span class="sxs-lookup"><span data-stu-id="d193e-126">Create an instance of the `ClientCalculator` in an application, and then call the service operations.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/client.cs#3)]  
  
6. <span data-ttu-id="d193e-127">Kompilieren Sie den Code, und führen Sie den Client aus.</span><span class="sxs-lookup"><span data-stu-id="d193e-127">Compile and run the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d193e-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d193e-128">See also</span></span>

- [<span data-ttu-id="d193e-129">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="d193e-129">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
