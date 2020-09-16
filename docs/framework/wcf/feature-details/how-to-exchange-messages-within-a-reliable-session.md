---
title: 'Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung'
ms.date: 03/30/2017
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
ms.openlocfilehash: 97371f8572d5d0db633ab8dd1ca82067d9d55c3f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550188"
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a><span data-ttu-id="da81b-102">Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung</span><span class="sxs-lookup"><span data-stu-id="da81b-102">How to: Exchange Messages Within a Reliable Session</span></span>

<span data-ttu-id="da81b-103">Dieses Thema enthält einen Überblick über die Schritte zum Aktivieren einer zuverlässigen Sitzung mithilfe einer der vom System bereitgestellten Bindungen, die eine solche Sitzung zwar unterstützen, dies jedoch nicht standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="da81b-103">This topic outlines the steps required to enable a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="da81b-104">Sie können eine zuverlässige Sitzung Imperativ mithilfe von Code oder deklarativ in der Konfigurationsdatei aktivieren.</span><span class="sxs-lookup"><span data-stu-id="da81b-104">You enable a reliable session imperatively using code or declaratively in your configuration file.</span></span> <span data-ttu-id="da81b-105">In diesem Verfahren werden die Client-und Dienst Konfigurationsdateien verwendet, um die zuverlässige Sitzung zu aktivieren und festzulegen, dass die Nachrichten in derselben Reihenfolge eintreffen, in der Sie gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="da81b-105">This procedure uses the client and service configuration files to enable the reliable session and to stipulate that the messages arrive in the same order in which they were sent.</span></span>

<span data-ttu-id="da81b-106">Der wesentliche Teil dieser Prozedur ist, dass das Endpunkt Konfigurationselement ein- `bindingConfiguration` Attribut enthält, das auf eine Bindungs Konfiguration mit dem Namen verweist `Binding1` .</span><span class="sxs-lookup"><span data-stu-id="da81b-106">The key part of this procedure is that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="da81b-107">Das [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) Configuration-Element verweist auf diesen Namen, um zuverlässige Sitzungen zu aktivieren, indem das- `enabled` Attribut des-Elements auf festgelegt wird [**\<reliableSession>**](/previous-versions/dotnet/netframework-4.0/ms731302(v=vs.100)) `true` .</span><span class="sxs-lookup"><span data-stu-id="da81b-107">The [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) configuration element references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](/previous-versions/dotnet/netframework-4.0/ms731302(v=vs.100)) element to `true`.</span></span> <span data-ttu-id="da81b-108">Sie geben die Zusicherung einer Zustellung in der richtigen Reihenfolge für die zuverlässige Sitzung an, indem Sie das `ordered`-Attribut auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="da81b-108">You specify the ordered delivery assurances for the reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="da81b-109">Die Quell Kopie dieses Beispiels finden Sie unter [zuverlässige WS-Sitzung](../samples/ws-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="da81b-109">For the source copy of this example, see [WS Reliable Session](../samples/ws-reliable-session.md).</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="da81b-110">Konfigurieren Sie den Dienst mit einer wsHttpBinding, um eine zuverlässige Sitzung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="da81b-110">Configure the service with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="da81b-111">Definieren Sie einen Dienstvertrag für den Diensttyp.</span><span class="sxs-lookup"><span data-stu-id="da81b-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. <span data-ttu-id="da81b-112">Implementieren Sie den Dienstvertrag in einer Dienstklasse.</span><span class="sxs-lookup"><span data-stu-id="da81b-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="da81b-113">Beachten Sie, dass die Adresse oder die Bindungs Informationen nicht in der Implementierung des Dienstanbieter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="da81b-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="da81b-114">Sie müssen keinen Code schreiben, um die Adresse oder die Bindungs Informationen aus der Konfigurationsdatei abzurufen.</span><span class="sxs-lookup"><span data-stu-id="da81b-114">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. <span data-ttu-id="da81b-115">Erstellen Sie eine *Web.config* -Datei, um einen Endpunkt für die zu konfigurieren `CalculatorService` , die <xref:System.ServiceModel.WSHttpBinding> mit aktivierter zuverlässiger Sitzung und geordneter Übermittlung von Nachrichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="da81b-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` that uses the <xref:System.ServiceModel.WSHttpBinding> with reliable session enabled and ordered delivery of messages required.</span></span>

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. <span data-ttu-id="da81b-116">Erstellen Sie eine *Service. svc* -Datei, die die folgende Zeile enthält:</span><span class="sxs-lookup"><span data-stu-id="da81b-116">Create a *Service.svc* file that contains the line:</span></span>

   ```aspx-csharp
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. <span data-ttu-id="da81b-117">Platzieren Sie die Datei " *Service. svc* " in Ihrem virtuellen Verzeichnis für Internetinformationsdienste (IIS).</span><span class="sxs-lookup"><span data-stu-id="da81b-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="da81b-118">Konfigurieren des Clients mit WSHttpBinding zur Verwendung einer zuverlässigen Sitzung</span><span class="sxs-lookup"><span data-stu-id="da81b-118">Configure the client with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="da81b-119">Verwenden Sie das [Service Model Metadata Utility-Tool (*Svcutil.exe*)](../servicemodel-metadata-utility-tool-svcutil-exe.md) von der Befehlszeile aus, um Code aus Dienst Metadaten zu generieren:</span><span class="sxs-lookup"><span data-stu-id="da81b-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata:</span></span>

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="da81b-120">Der generierte Client enthält die `ICalculator` Schnittstelle, die den Dienstvertrag definiert, den die Client Implementierung erfüllen muss.</span><span class="sxs-lookup"><span data-stu-id="da81b-120">The generated client contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. <span data-ttu-id="da81b-121">Die generierte Clientanwendung enthält außerdem die Implementierung von `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="da81b-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="da81b-122">Beachten Sie, dass die Adress-und Bindungs Informationen nicht in der Implementierung des Dienstanbieter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="da81b-122">Note that the address and binding information isn't specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="da81b-123">Sie müssen keinen Code schreiben, um die Adresse oder die Bindungs Informationen aus der Konfigurationsdatei abzurufen.</span><span class="sxs-lookup"><span data-stu-id="da81b-123">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. <span data-ttu-id="da81b-124">*Svcutil.exe* generiert auch die Konfiguration für den Client, der die- <xref:System.ServiceModel.WSHttpBinding> Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="da81b-124">*Svcutil.exe* also generates the configuration for the client that uses the <xref:System.ServiceModel.WSHttpBinding> class.</span></span> <span data-ttu-id="da81b-125">Benennen Sie die Konfigurationsdatei *App.config* , wenn Sie Visual Studio verwenden.</span><span class="sxs-lookup"><span data-stu-id="da81b-125">Name the configuration file *App.config* when using Visual Studio.</span></span>

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. <span data-ttu-id="da81b-126">Erstellen Sie eine Instanz von `ClientCalculator` in einer Anwendung, und rufen Sie die Dienst Vorgänge auf.</span><span class="sxs-lookup"><span data-stu-id="da81b-126">Create an instance of the `ClientCalculator` in an application and call the service operations.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. <span data-ttu-id="da81b-127">Kompilieren Sie den Code, und führen Sie den Client aus.</span><span class="sxs-lookup"><span data-stu-id="da81b-127">Compile and run the client.</span></span>

## <a name="example"></a><span data-ttu-id="da81b-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="da81b-128">Example</span></span>

<span data-ttu-id="da81b-129">Mehrere der vom System bereitgestellten Bindungen unterstützen standardmäßig zuverlässige Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="da81b-129">Several of the system-provided bindings support reliable sessions by default.</span></span> <span data-ttu-id="da81b-130">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="da81b-130">These include:</span></span>

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

<span data-ttu-id="da81b-131">Ein Beispiel für das Erstellen einer benutzerdefinierten Bindung, die zuverlässige Sitzungen unterstützt, finden Sie unter Gewusst [wie: Erstellen einer benutzerdefinierten zuverlässigen Sitzungs Bindung mit HTTPS](how-to-create-a-custom-reliable-session-binding-with-https.md).</span><span class="sxs-lookup"><span data-stu-id="da81b-131">For an example of how to create a custom binding that supports reliable sessions, see [How to: Create a Custom Reliable Session Binding with HTTPS](how-to-create-a-custom-reliable-session-binding-with-https.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="da81b-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da81b-132">See also</span></span>

- [<span data-ttu-id="da81b-133">Zuverlässige Sitzungen</span><span class="sxs-lookup"><span data-stu-id="da81b-133">Reliable Sessions</span></span>](reliable-sessions.md)
