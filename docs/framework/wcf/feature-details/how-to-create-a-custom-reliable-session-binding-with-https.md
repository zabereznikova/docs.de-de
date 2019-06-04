---
title: 'Vorgehensweise: Erstellen einer benutzerdefinierten zuverlässigen Sitzungsbindung mit HTTPS'
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: f39325829cf4b548482a6a570a5aa1fd65e61a1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62039532"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a><span data-ttu-id="59115-102">Vorgehensweise: Erstellen einer benutzerdefinierten zuverlässigen Sitzungsbindung mit HTTPS</span><span class="sxs-lookup"><span data-stu-id="59115-102">How to: Create a Custom Reliable Session Binding with HTTPS</span></span>

<span data-ttu-id="59115-103">Dieses Thema veranschaulicht die Verwendung der Secure Sockets Layer (SSL)-Transportsicherheit mit zuverlässigen Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="59115-103">This topic demonstrates the use of Secure Sockets Layer (SSL) transport security with reliable sessions.</span></span> <span data-ttu-id="59115-104">Um eine zuverlässige Sitzung über HTTPS verwenden zu können, müssen Sie eine benutzerdefinierte Bindung erstellen, die eine zuverlässige Sitzung und HTTPS-Transport verwendet.</span><span class="sxs-lookup"><span data-stu-id="59115-104">To use a reliable session over HTTPS, you must create a custom binding that uses a reliable session and the HTTPS transport.</span></span> <span data-ttu-id="59115-105">Sie aktivieren die zuverlässige Sitzung entweder verbindlich durch Verwenden von Code oder deklarativ in der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="59115-105">You enable the reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="59115-106">Diese Prozedur verwendet die Konfigurationsdateien von Client und Dienst, um die zuverlässige Sitzung zu aktivieren und die [  **\<HttpsTransport >** ](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) Element.</span><span class="sxs-lookup"><span data-stu-id="59115-106">This procedure uses the client and service configuration files to enable the reliable session and the [**\<httpsTransport>**](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) element.</span></span>

<span data-ttu-id="59115-107">Der wesentliche Teil dieser Prozedur ist, die die  **\<Endpunkt >** Konfigurationselement enthalten eine `bindingConfiguration` Attribut, das eine benutzerdefinierte Bindungskonfiguration mit dem Namen verweist `reliableSessionOverHttps`.</span><span class="sxs-lookup"><span data-stu-id="59115-107">The key part of this procedure is that the **\<endpoint>** configuration element contain a `bindingConfiguration` attribute that references a custom binding configuration named `reliableSessionOverHttps`.</span></span> <span data-ttu-id="59115-108">Die [  **\<Bindung >** ](../../../../docs/framework/misc/binding.md) Konfigurationselement verweist auf diesen Namen, um anzugeben, dass eine zuverlässige Sitzung und HTTPS-Transport, indem verwendet werden  **\< ReliableSession >** und  **\<HttpsTransport >** Elemente.</span><span class="sxs-lookup"><span data-stu-id="59115-108">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element references this name to specify that a reliable session and the HTTPS transport are used by including **\<reliableSession>** and **\<httpsTransport>** elements.</span></span>

<span data-ttu-id="59115-109">Die Quellkopie dieses Beispiels, finden Sie unter [benutzerdefiniertes Binden von zuverlässigen Sitzung über HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).</span><span class="sxs-lookup"><span data-stu-id="59115-109">For the source copy of this example, see [Custom Binding Reliable Session over HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).</span></span>

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="59115-110">Konfigurieren Sie den Dienst mit ' CustomBinding ' zur Verwendung einer zuverlässigen Sitzungs mit HTTPS</span><span class="sxs-lookup"><span data-stu-id="59115-110">Configure the service with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="59115-111">Definieren Sie einen Dienstvertrag für den Diensttyp.</span><span class="sxs-lookup"><span data-stu-id="59115-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. <span data-ttu-id="59115-112">Implementieren Sie den Dienstvertrag in einer Dienstklasse.</span><span class="sxs-lookup"><span data-stu-id="59115-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="59115-113">Beachten Sie, dass die Adresse oder die Bindungsinformationen Informationen innerhalb der Implementierung des Diensts nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="59115-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="59115-114">Sie sind nicht erforderlich, um das Schreiben von Code, um die Adresse oder die Bindungsinformationen Informationen aus der Konfigurationsdatei abzurufen.</span><span class="sxs-lookup"><span data-stu-id="59115-114">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. <span data-ttu-id="59115-115">Erstellen Sie eine *"Web.config"* Datei so konfigurieren Sie einen Endpunkt für die `CalculatorService` mit einer benutzerdefinierten Bindung mit dem Namen `reliableSessionOverHttps` , die eine zuverlässige Sitzung und HTTPS-Transport verwendet.</span><span class="sxs-lookup"><span data-stu-id="59115-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` with a custom binding named `reliableSessionOverHttps` that uses a reliable session and the HTTPS transport.</span></span>

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. <span data-ttu-id="59115-116">Erstellen Sie eine *"Service.svc"* -Datei, die die Zeile enthält:</span><span class="sxs-lookup"><span data-stu-id="59115-116">Create a *Service.svc* file that contains the line:</span></span>

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. <span data-ttu-id="59115-117">Ort der *"Service.svc"* Datei in das virtuelle Verzeichnis für Internetinformationsdienste (Internet Information Services, IIS).</span><span class="sxs-lookup"><span data-stu-id="59115-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="59115-118">Konfigurieren Sie den Client mit ' CustomBinding ' zur Verwendung einer zuverlässigen Sitzungs mit HTTPS</span><span class="sxs-lookup"><span data-stu-id="59115-118">Configure the client with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="59115-119">Verwenden der [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) über die Befehlszeile, um Code aus Dienstmetadaten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="59115-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata.</span></span>

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="59115-120">Der Client, der generiert wird, enthält die `ICalculator` Schnittstelle, die den Dienstvertrag definiert, die die Clientimplementierung entsprechen muss.</span><span class="sxs-lookup"><span data-stu-id="59115-120">The client that's generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. <span data-ttu-id="59115-121">Die generierte Clientanwendung enthält außerdem die Implementierung von `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="59115-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="59115-122">Beachten Sie, dass die Adresse und Bindung Informationen innerhalb der Implementierung des Diensts nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="59115-122">Note that the address and binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="59115-123">Sie sind nicht erforderlich, um das Schreiben von Code, um die Adresse und Bindung Informationen aus der Konfigurationsdatei abzurufen.</span><span class="sxs-lookup"><span data-stu-id="59115-123">You aren't required to write code to retrieve the address and binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. <span data-ttu-id="59115-124">Konfigurieren Sie eine benutzerdefinierte Bindung mit dem Namen `reliableSessionOverHttps` die HTTPS-Transport und zuverlässige Sitzungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="59115-124">Configure a custom binding named `reliableSessionOverHttps` to use the HTTPS transport and reliable sessions.</span></span>

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. <span data-ttu-id="59115-125">Erstellen Sie eine Instanz von `ClientCalculator` in einer Anwendung, und rufen Sie dann die Dienstvorgänge auf.</span><span class="sxs-lookup"><span data-stu-id="59115-125">Create an instance of the `ClientCalculator` in an application and then call the service operations.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. <span data-ttu-id="59115-126">Kompilieren Sie den Code, und führen Sie den Client aus.</span><span class="sxs-lookup"><span data-stu-id="59115-126">Compile and run the client.</span></span>  

## <a name="net-framework-security"></a><span data-ttu-id="59115-127">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="59115-127">.NET Framework security</span></span>

<span data-ttu-id="59115-128">Da das in diesem Beispiel verwendete Zertifikat ein mit erstelltes Testzertifikat ist *Makecert.exe*, eine sicherheitswarnung angezeigt, wenn Sie versuchen, eine HTTPS-Adresse zugreifen, z.B. `https://localhost/servicemodelsamples/service.svc`, in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="59115-128">Because the certificate used in this sample is a test certificate created with *Makecert.exe*, a security alert appears when you try to access an HTTPS address, such as `https://localhost/servicemodelsamples/service.svc`, from your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="59115-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59115-129">See also</span></span>

- [<span data-ttu-id="59115-130">Zuverlässige Sitzungen</span><span class="sxs-lookup"><span data-stu-id="59115-130">Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
