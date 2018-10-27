---
title: 'Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung'
ms.date: 03/30/2017
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
ms.openlocfilehash: 53e5661bf140540cd0fc7a9fcb739b67488b8491
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50038259"
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a><span data-ttu-id="869a8-102">Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung</span><span class="sxs-lookup"><span data-stu-id="869a8-102">How to: Exchange Messages Within a Reliable Session</span></span>

<span data-ttu-id="869a8-103">Dieses Thema enthält einen Überblick über die Schritte zum Aktivieren einer zuverlässigen Sitzung mithilfe einer der vom System bereitgestellten Bindungen, die eine solche Sitzung zwar unterstützen, dies jedoch nicht standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="869a8-103">This topic outlines the steps required to enable a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="869a8-104">Sie ermöglichen, eine zuverlässige Sitzung verbindlich durch Verwenden von Code oder deklarativ in der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="869a8-104">You enable a reliable session imperatively using code or declaratively in your configuration file.</span></span> <span data-ttu-id="869a8-105">Diese Prozedur verwendet die Konfigurationsdateien von Client und Dienst aus, um die zuverlässige Sitzung zu aktivieren und um festzulegen, dass die Nachrichten in der gleichen Reihenfolge eintreffen in der sie gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="869a8-105">This procedure uses the client and service configuration files to enable the reliable session and to stipulate that the messages arrive in the same order in which they were sent.</span></span>

<span data-ttu-id="869a8-106">Der wesentliche Teil dieser Prozedur ist, dass der Endpunkt-Konfigurationselement enthalten eine `bindingConfiguration` -Attribut, das auf die Bindungskonfiguration mit dem Namen `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="869a8-106">The key part of this procedure is that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="869a8-107">Die [  **\<Bindung >** ](../../../../docs/framework/misc/binding.md) Konfigurationselement verweist auf diesen Namen, um zuverlässige Sitzungen zu aktivieren, indem Sie die Einstellung der `enabled` Attribut der [  **\<ReliableSession >** ](https://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) Element `true`.</span><span class="sxs-lookup"><span data-stu-id="869a8-107">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](https://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) element to `true`.</span></span> <span data-ttu-id="869a8-108">Sie geben die Zusicherung einer Zustellung in der richtigen Reihenfolge für die zuverlässige Sitzung an, indem Sie das `ordered`-Attribut auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="869a8-108">You specify the ordered delivery assurances for the reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="869a8-109">Die Quellkopie dieses Beispiels, finden Sie unter [zuverlässige WS-Sitzung](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="869a8-109">For the source copy of this example, see [WS Reliable Session](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="869a8-110">Konfigurieren Sie den Dienst mit WSHttpBinding zur Verwendung einer zuverlässigen Sitzung</span><span class="sxs-lookup"><span data-stu-id="869a8-110">Configure the service with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="869a8-111">Definieren Sie einen Dienstvertrag für den Diensttyp.</span><span class="sxs-lookup"><span data-stu-id="869a8-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. <span data-ttu-id="869a8-112">Implementieren Sie den Dienstvertrag in einer Dienstklasse.</span><span class="sxs-lookup"><span data-stu-id="869a8-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="869a8-113">Beachten Sie, dass die Adresse oder die Bindungsinformationen Informationen innerhalb der Implementierung des Diensts nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="869a8-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="869a8-114">Sie sind nicht erforderlich, um das Schreiben von Code, um die Adresse oder die Bindungsinformationen Informationen aus der Konfigurationsdatei abzurufen.</span><span class="sxs-lookup"><span data-stu-id="869a8-114">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. <span data-ttu-id="869a8-115">Erstellen Sie eine *"Web.config"* Datei so konfigurieren Sie einen Endpunkt für die `CalculatorService` , verwendet der <xref:System.ServiceModel.WSHttpBinding> mit aktivierter zuverlässiger Sitzung und geordnete Übermittlung von Nachrichten, die erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="869a8-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` that uses the <xref:System.ServiceModel.WSHttpBinding> with reliable session enabled and ordered delivery of messages required.</span></span>

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. <span data-ttu-id="869a8-116">Erstellen Sie eine *"Service.svc"* -Datei, die die Zeile enthält:</span><span class="sxs-lookup"><span data-stu-id="869a8-116">Create a *Service.svc* file that contains the line:</span></span>

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1.  <span data-ttu-id="869a8-117">Ort der *"Service.svc"* Datei in das virtuelle Verzeichnis für Internetinformationsdienste (Internet Information Services, IIS).</span><span class="sxs-lookup"><span data-stu-id="869a8-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="869a8-118">Konfigurieren Sie den Client mit WSHttpBinding zur Verwendung einer zuverlässigen Sitzung</span><span class="sxs-lookup"><span data-stu-id="869a8-118">Configure the client with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="869a8-119">Verwenden der [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) über die Befehlszeile, um Code aus Dienstmetadaten zu generieren:</span><span class="sxs-lookup"><span data-stu-id="869a8-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata:</span></span>

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="869a8-120">Der generierte Client enthält den `ICalculator` Schnittstelle, die den Dienstvertrag definiert, die die Clientimplementierung entsprechen muss.</span><span class="sxs-lookup"><span data-stu-id="869a8-120">The generated client contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. <span data-ttu-id="869a8-121">Die generierte Clientanwendung enthält außerdem die Implementierung von `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="869a8-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="869a8-122">Beachten Sie, dass die Adresse und Bindung Informationen an einer beliebigen Stelle innerhalb der Implementierung des Diensts angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="869a8-122">Note that the address and binding information isn't specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="869a8-123">Sie sind nicht erforderlich, um das Schreiben von Code, um die Adresse oder die Bindungsinformationen Informationen aus der Konfigurationsdatei abzurufen.</span><span class="sxs-lookup"><span data-stu-id="869a8-123">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. <span data-ttu-id="869a8-124">*Svcutil.exe* generiert auch die Konfiguration für den Client, verwendet der <xref:System.ServiceModel.WSHttpBinding> Klasse.</span><span class="sxs-lookup"><span data-stu-id="869a8-124">*Svcutil.exe* also generates the configuration for the client that uses the <xref:System.ServiceModel.WSHttpBinding> class.</span></span> <span data-ttu-id="869a8-125">Benennen Sie die Konfigurationsdatei *"App.config"* bei Verwendung von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="869a8-125">Name the configuration file *App.config* when using Visual Studio.</span></span>

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. <span data-ttu-id="869a8-126">Erstellen Sie eine Instanz von der `ClientCalculator` in einer Anwendung, und rufen Sie Dienstvorgänge.</span><span class="sxs-lookup"><span data-stu-id="869a8-126">Create an instance of the `ClientCalculator` in an application and call the service operations.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. <span data-ttu-id="869a8-127">Kompilieren Sie den Code, und führen Sie den Client aus.</span><span class="sxs-lookup"><span data-stu-id="869a8-127">Compile and run the client.</span></span>

## <a name="example"></a><span data-ttu-id="869a8-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="869a8-128">Example</span></span>

<span data-ttu-id="869a8-129">Mehrere der vom System bereitgestellten Bindungen unterstützen standardmäßig zuverlässige Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="869a8-129">Several of the system-provided bindings support reliable sessions by default.</span></span> <span data-ttu-id="869a8-130">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="869a8-130">These include:</span></span>

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

<span data-ttu-id="869a8-131">Ein Beispiel dafür, wie Sie eine benutzerdefinierte Bindung zu erstellen, zuverlässige Sitzungen unterstützt, finden Sie unter [Vorgehensweise: Erstellen einer benutzerdefinierten zuverlässigen Sitzungsbindung mit HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).</span><span class="sxs-lookup"><span data-stu-id="869a8-131">For an example of how to create a custom binding that supports reliable sessions, see [How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="869a8-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="869a8-132">See also</span></span>

[<span data-ttu-id="869a8-133">Zuverlässige Sitzungen</span><span class="sxs-lookup"><span data-stu-id="869a8-133">Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
